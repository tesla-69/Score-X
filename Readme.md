# AI Resume Matcher

AI-powered recruitment platform for matching candidate resumes (CVs) to job descriptions using NLP and ML. Visualizes match results with graphs and word clouds.

---

## Features

- Upload and manage job descriptions and candidate CVs
- Automated resume parsing and job matching using TF-IDF and cosine similarity
- Visual match analytics: bar charts and word clouds
- REST API backend with FastAPI
- Modern React frontend with Tailwind CSS

---

## Tech Stack

### Frontend

- [React](https://react.dev/)
- [Vite](https://vitejs.dev/)
- [Tailwind CSS](https://tailwindcss.com/)
- [React Router](https://reactrouter.com/)
- [React Dropzone](https://react-dropzone.js.org/)
- [Headless UI](https://headlessui.com/)
- [Heroicons](https://heroicons.com/)

### Backend

- [FastAPI](https://fastapi.tiangolo.com/)
- [Uvicorn](https://www.uvicorn.org/)
- [Pandas](https://pandas.pydata.org/)
- [python-multipart](https://andrew-d.github.io/python-multipart/)
- [PyPDF2](https://pypdf2.readthedocs.io/)
- [scikit-learn](https://scikit-learn.org/)
- [matplotlib](https://matplotlib.org/)
- [wordcloud](https://github.com/amueller/word_cloud/)

---

## Project Structure

```
.
├── backend/
│   ├── app.py
│   └── requirements.txt
├── frontend/
│   ├── src/
│   ├── public/
│   ├── package.json
│   └── ...
├── model.py
├── jd.csv
├── output.csv
├── match1/
│   ├── results.csv
│   ├── graph.png
│   └── wordcloud.png
├── match2/
│   └── ...
├── match3/
│   └── ...
```

---

## Getting Started

### Prerequisites

- Python 3.8+
- Node.js 18+

### 1. Backend Setup

```sh
cd backend
pip install -r requirements.txt
```

#### Additional Python dependencies (for `model.py`):

```sh
pip install PyPDF2 scikit-learn matplotlib wordcloud
```

### 2. Frontend Setup

```sh
cd frontend
npm install
```

---

## Running the Project

### 1. Run Resume Matching Script

Place resumes (PDFs) in a folder named `resume/` at the project root.  
Edit `jd.csv` for your job description.

```sh
python model.py
```

This generates `output.csv` and populates `match1/`, `match2/`, `match3/` with results and images.

### 2. Start Backend API

```sh
cd backend
uvicorn app:app --reload
```

API runs at [http://localhost:8000](http://localhost:8000).

### 3. Start Frontend

```sh
cd frontend
npm run dev
```

Frontend runs at [http://localhost:5173](http://localhost:5173).

---

## API Endpoints

- `GET /api/top-matches` — List top 3 candidates
- `GET /api/results/{match_number}` — Detailed results for a match (1-3)
- `GET /api/graph/{match_number}` — Bar chart image
- `GET /api/wordcloud/{match_number}` — Word cloud image

---

## Customization

- Edit `jd.csv` for your job description fields.
- Place candidate resumes in `resume/` folder.
- Adjust frontend UI in [`frontend/src/components`](frontend/src/components).

---

## License

MIT License

---

## Acknowledgements

- Inspired by modern AI recruitment workflows.
- Built with open-source tools and libraries.
