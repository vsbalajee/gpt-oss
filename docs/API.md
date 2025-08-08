# API Documentation

## Endpoints

### POST /api/generate

Generates text based on the provided prompt.

- **Request**:
  - **Headers**:
    - `Content-Type: application/json`
  - **Body**:
    - `prompt` (string, required): The input prompt for text generation.
    - `maxTokens` (integer, optional): The maximum number of tokens to generate. Default is 50.
    - `temperature` (float, optional): The sampling temperature. Higher values make the output more random. Default is 0.7.

- **Response**:
  - **Status Codes**:
    - `200 OK`: Successful response.
    - `400 Bad Request`: Invalid request, missing required parameters.
    - `500 Internal Server Error`: An error occurred on the server.
  - **Body**:
    - `text` (string): The generated text.
    - `tokensUsed` (integer): The number of tokens used in the generation.

### GET /api/models

Lists all available models.

- **Request**:
  - **Headers**:
    - `Content-Type: application/json`

- **Response**:
  - **Status Codes**:
    - `200 OK`: Successful response.
  - **Body**:
    - `models` (array of objects): An array of available models.
      - `name` (string): The name of the model.
      - `description` (string): A brief description of the model.

## Data Models

### GenerateRequest

- **prompt** (string, required): The input prompt for text generation.
- **maxTokens** (integer, optional): The maximum number of tokens to generate. Default is 50.
- **temperature** (float, optional): The sampling temperature. Higher values make the output more random. Default is 0.7.

### GenerateResponse

- **text** (string): The generated text.
- **tokensUsed** (integer): The number of tokens used in the generation.

### ModelListResponse

- **models** (array of objects): An array of available models.
  - **name** (string): The name of the model.
  - **description** (string): A brief description of the model.
