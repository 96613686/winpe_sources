# CAVIIAVSStreamParser::ParseStreamFormatChunk(CLISTChunkEnumerator *)

- ea: `0x180074b70`
- end: `0x1800754f2`
- name: `?ParseStreamFormatChunk@CAVIIAVSStreamParser@@EEAAJPEAVCLISTChunkEnumerator@@@Z`
- size: `2434`
- prototype: `__int64 __fastcall(CAVIIAVSStreamParser *__hidden this, struct CLISTChunkEnumerator *)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x1800355ac`
- `0x180073b14`
- `0x180074b70`
- `0x1800beb74`
- `0x180109590`
- `0x1801095a8`
- `0x1801099f0`
- `0x1801398a8`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180074c29`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180074cd2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180074d7b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180074e24`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180074ecd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180074f76`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007501f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800750c8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180075171`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007526f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180075326`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800753e4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180074c29`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180074cd2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180074d7b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180074e24`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180074ecd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180074f76`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007501f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800750c8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180075171`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007526f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180075326`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800753e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075484`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075495`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800754a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075484`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075495`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800754a6`

## pseudocode

```c
__int64 __fastcall CAVIIAVSStreamParser::ParseStreamFormatChunk(
        CAVIIAVSStreamParser *this,
        struct CLISTChunkEnumerator *a2)
{
  LPVOID *v4; // r15
  void *v5; // rcx
  LPVOID *v6; // r14
  void *v7; // rcx
  _QWORD *v8; // r12
  void *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  wchar_t *v13; // rcx
  int Data; // ebx
  CallStackTracing *v15; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  wchar_t *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // r9
  wchar_t *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // r9
  wchar_t *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // r9
  wchar_t *v39; // rcx
  CallStackTracing *v40; // rax
  struct CallStackContext *v41; // rax
  __int64 v42; // rdx
  __int64 v43; // r8
  __int64 v44; // r9
  wchar_t *v45; // rcx
  CallStackTracing *v46; // rax
  struct CallStackContext *v47; // rax
  __int64 v48; // rdx
  __int64 v49; // r8
  __int64 v50; // r9
  wchar_t *v51; // rcx
  CallStackTracing *v52; // rax
  struct CallStackContext *v53; // rax
  __int64 v54; // rdx
  __int64 v55; // r8
  __int64 v56; // r9
  wchar_t *v57; // rcx
  CallStackTracing *v58; // rax
  struct CallStackContext *v59; // rax
  __int64 v60; // rdx
  __int64 v61; // r8
  __int64 v62; // r9
  wchar_t *v63; // rcx
  CallStackTracing *v64; // rax
  struct CallStackContext *v65; // rax
  __int64 v66; // rdx
  __int64 v67; // r8
  __int64 v68; // r9
  wchar_t *v69; // rcx
  CallStackTracing *v70; // rax
  struct CallStackContext *v71; // rax
  wchar_t *v72; // rcx
  CallStackTracing *v73; // rax
  struct CallStackContext *v74; // rax
  struct DVINFO *v75; // rax
  __int64 v76; // rdx
  __int64 v77; // r8
  __int64 v78; // r9
  wchar_t *v79; // rcx
  CallStackTracing *v80; // rax
  struct CallStackContext *v81; // rax
  int v83; // [rsp+20h] [rbp-60h]
  _BYTE v84[8]; // [rsp+50h] [rbp-30h] BYREF
  struct DVINFO v85; // [rsp+58h] [rbp-28h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v84,
    "CAVIIAVSStreamParser::ParseStreamFormatChunk",
    328);
  v4 = (LPVOID *)((char *)this + 640);
  v5 = (void *)*((_QWORD *)this + 80);
  memset(&v85, 0, sizeof(v85));
  operator delete(v5);
  v6 = (LPVOID *)((char *)this + 1608);
  v7 = (void *)*((_QWORD *)this + 201);
  *((_QWORD *)this + 80) = 0;
  operator delete(v7);
  v8 = (_QWORD *)((char *)this + 1616);
  *((_QWORD *)this + 201) = 0;
  operator delete(*((void **)this + 202));
  v9 = (void *)*((_QWORD *)this + 198);
  *((_QWORD *)this + 202) = 0;
  operator delete(v9);
  *((_QWORD *)this + 198) = 0;
  if ( *((_QWORD *)a2 + 7) < 0x20u )
  {
    v13 = (wchar_t *)CallStackTracing::s_wpInstance;
    Data = -1072875842;
    if ( !CallStackTracing::s_wpInstance )
    {
      v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10, v11, v12);
      CallStackTracing::s_wpInstance = v15;
      if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
      {
        v13 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v13 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v13 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072875842 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CAVIIAVSStreamParser::ParseStreamFormatChunk",
          348,
          -1072875842);
    }
    if ( !g_wppLevels )
      goto LABEL_139;
    v17 = 43;
    goto LABEL_138;
  }
  Data = ReadDataType<unsigned int,unsigned long>(*((_QWORD *)a2 + 1), v10, &v85);
  if ( Data < 0 )
  {
    v21 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18, v19, v20);
      CallStackTracing::s_wpInstance = v22;
      if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
      {
        v21 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v21 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v21 + 8) )
    {
      v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
      if ( *((_DWORD *)v23 + 499) != Data )
        CallStackContext::TraceFailure(v23, "CAVIIAVSStreamParser::ParseStreamFormatChunk", 351, Data);
    }
    if ( !g_wppLevels )
      goto LABEL_139;
    v17 = 44;
    goto LABEL_138;
  }
  Data = ReadDataType<unsigned int,unsigned long>(*((_QWORD *)a2 + 1), v18, &v85.dwDVAAuxCtl);
  if ( Data < 0 )
  {
    v27 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24, v25, v26);
      CallStackTracing::s_wpInstance = v28;
      if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
      {
        v27 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v27 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v27 + 8) )
    {
      v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
      if ( *((_DWORD *)v29 + 499) != Data )
        CallStackContext::TraceFailure(v29, "CAVIIAVSStreamParser::ParseStreamFormatChunk", 352, Data);
    }
    if ( !g_wppLevels )
      goto LABEL_139;
    v17 = 45;
    goto LABEL_138;
  }
  Data = ReadDataType<unsigned int,unsigned long>(*((_QWORD *)a2 + 1), v24, &v85.dwDVAAuxSrc1);
  if ( Data < 0 )
  {
    v33 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30, v31, v32);
      CallStackTracing::s_wpInstance = v34;
      if ( v34 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
      {
        v33 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v33 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v33 + 8) )
    {
      v35 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
      if ( *((_DWORD *)v35 + 499) != Data )
        CallStackContext::TraceFailure(v35, "CAVIIAVSStreamParser::ParseStreamFormatChunk", 353, Data);
    }
    if ( !g_wppLevels )
      goto LABEL_139;
    v17 = 46;
    goto LABEL_138;
  }
  Data = ReadDataType<unsigned int,unsigned long>(*((_QWORD *)a2 + 1), v30, &v85.dwDVAAuxCtl1);
  if ( Data < 0 )
  {
    v39 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v36, v37, v38);
      CallStackTracing::s_wpInstance = v40;
      if ( v40 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
      {
        v39 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v39 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v39 + 8) )
    {
      v41 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v39);
      if ( *((_DWORD *)v41 + 499) != Data )
        CallStackContext::TraceFailure(v41, "CAVIIAVSStreamParser::ParseStreamFormatChunk", 354, Data);
    }
    if ( !g_wppLevels )
      goto LABEL_139;
    v17 = 47;
    goto LABEL_138;
  }
  Data = ReadDataType<unsigned int,unsigned long>(*((_QWORD *)a2 + 1), v36, &v85.dwDVVAuxSrc);
  if ( Data < 0 )
  {
    v45 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v42, v43, v44);
      CallStackTracing::s_wpInstance = v46;
      if ( v46 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v46 + 8LL))(v46, 2032) )
      {
        v45 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v45 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v45 + 8) )
    {
      v47 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v45);
      if ( *((_DWORD *)v47 + 499) != Data )
        CallStackContext::TraceFailure(v47, "CAVIIAVSStreamParser::ParseStreamFormatChunk", 355, Data);
    }
    if ( !g_wppLevels )
      goto LABEL_139;
    v17 = 48;
    goto LABEL_138;
  }
  Data = ReadDataType<unsigned int,unsigned long>(*((_QWORD *)a2 + 1), v42, &v85.dwDVVAuxCtl);
  if ( Data < 0 )
  {
    v51 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v52 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v48, v49, v50);
      CallStackTracing::s_wpInstance = v52;
      if ( v52 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v52 + 8LL))(v52, 2032) )
      {
        v51 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v51 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v51 + 8) )
    {
      v53 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v51);
      if ( *((_DWORD *)v53 + 499) != Data )
        CallStackContext::TraceFailure(v53, "CAVIIAVSStreamParser::ParseStreamFormatChunk", 356, Data);
    }
    if ( !g_wppLevels )
      goto LABEL_139;
    v17 = 49;
    goto LABEL_138;
  }
  Data = ReadDataType<unsigned int,unsigned long>(*((_QWORD *)a2 + 1), v48, v85.dwDVReserved);
  if ( Data < 0 )
  {
    v57 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v58 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v54, v55, v56);
      CallStackTracing::s_wpInstance = v58;
      if ( v58 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v58 + 8LL))(v58, 2032) )
      {
        v57 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v57 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v57 + 8) )
    {
      v59 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v57);
      if ( *((_DWORD *)v59 + 499) != Data )
        CallStackContext::TraceFailure(v59, "CAVIIAVSStreamParser::ParseStreamFormatChunk", 357, Data);
    }
    if ( !g_wppLevels )
      goto LABEL_139;
    v17 = 50;
    goto LABEL_138;
  }
  Data = ReadDataType<unsigned int,unsigned long>(*((_QWORD *)a2 + 1), v54, &v85.dwDVReserved[1]);
  if ( Data < 0 )
  {
    v63 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v64 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v60, v61, v62);
      CallStackTracing::s_wpInstance = v64;
      if ( v64 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v64 + 8LL))(v64, 2032) )
      {
        v63 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v63 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v63 + 8) )
    {
      v65 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v63);
      if ( *((_DWORD *)v65 + 499) != Data )
        CallStackContext::TraceFailure(v65, "CAVIIAVSStreamParser::ParseStreamFormatChunk", 358, Data);
    }
    if ( !g_wppLevels )
      goto LABEL_139;
    v17 = 51;
    goto LABEL_138;
  }
  if ( (unsigned __int8)byte_1801B1109 >= 0x20u )
    WPP_SF_dddddd(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      52,
      &WPP_0c6b2006a0443a18a2b9fa7547964932_Traceguids,
      v85.dwDVAAuxSrc,
      v85.dwDVAAuxCtl,
      v85.dwDVAAuxSrc1,
      v85.dwDVAAuxCtl1,
      v85.dwDVVAuxSrc,
      v85.dwDVVAuxCtl);
  Data = getMediaTypesFromIAVSStream(&v85, v83, (__int64)this + 1608, (__int64)this + 1616);
  if ( Data < 0 )
  {
    v69 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v70 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v66, v67, v68);
      CallStackTracing::s_wpInstance = v70;
      if ( v70 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v70 + 8LL))(v70, 2032) )
      {
        v69 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v69 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v69 + 8) )
    {
      v71 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v69);
      if ( *((_DWORD *)v71 + 499) != Data )
        CallStackContext::TraceFailure(v71, "CAVIIAVSStreamParser::ParseStreamFormatChunk", 378, Data);
    }
    if ( !g_wppLevels )
      goto LABEL_139;
    v17 = 53;
    goto LABEL_138;
  }
  if ( *v4 && *(_DWORD *)*v4 != 40 || !*v6 && *v8 )
  {
    v72 = (wchar_t *)CallStackTracing::s_wpInstance;
    Data = -1072873844;
    if ( !CallStackTracing::s_wpInstance )
    {
      v73 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v66, v67, v68);
      CallStackTracing::s_wpInstance = v73;
      if ( v73 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v73 + 8LL))(v73, 2032) )
      {
        v72 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v72 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v72 + 8) )
    {
      v74 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v72);
      if ( *((_DWORD *)v74 + 499) != -1072873844 )
        CallStackContext::TraceFailure(v74, "CAVIIAVSStreamParser::ParseStreamFormatChunk", 383, -1072873844);
    }
    if ( !g_wppLevels )
      goto LABEL_139;
    v17 = 54;
    goto LABEL_138;
  }
  *((_DWORD *)this + 398) = 65537;
  v75 = (struct DVINFO *)operator new(0x20u);
  *((_QWORD *)this + 198) = v75;
  if ( v75 )
  {
    *v75 = v85;
    goto LABEL_146;
  }
  v79 = (wchar_t *)CallStackTracing::s_wpInstance;
  Data = -2147024882;
  if ( !CallStackTracing::s_wpInstance )
  {
    v80 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v76, v77, v78);
    CallStackTracing::s_wpInstance = v80;
    if ( v80 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v80 + 8LL))(v80, 2032) )
    {
      v79 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v79 = &qword_1801B07E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
    }
  }
  if ( *((_BYTE *)v79 + 8) )
  {
    v81 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v79);
    if ( *((_DWORD *)v81 + 499) != -2147024882 )
      CallStackContext::TraceFailure(v81, "CAVIIAVSStreamParser::ParseStreamFormatChunk", 393, -2147024882);
  }
  if ( g_wppLevels )
  {
    v17 = 55;
LABEL_138:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, &WPP_0c6b2006a0443a18a2b9fa7547964932_Traceguids, this, Data);
  }
LABEL_139:
  if ( *v4 )
  {
    CoTaskMemFree(*v4);
    *v4 = 0;
  }
  if ( *v6 )
  {
    CoTaskMemFree(*v6);
    *v6 = 0;
  }
  if ( *v8 )
  {
    CoTaskMemFree(0);
    *v6 = 0;
  }
LABEL_146:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v84);
  return (unsigned int)Data;
}

```

## disassembly

```asm
0x180074b70  mov     [rsp-38h+arg_10], rbx
0x180074b75  push    rbp
0x180074b76  push    rsi
0x180074b77  push    rdi
0x180074b78  push    r12
0x180074b7a  push    r13
0x180074b7c  push    r14
0x180074b7e  push    r15
0x180074b80  mov     rbp, rsp
0x180074b83  sub     rsp, 80h
0x180074b8a  mov     rax, cs:__security_cookie
0x180074b91  xor     rax, rsp
0x180074b94  mov     [rbp+var_8], rax
0x180074b98  mov     rdi, rdx
0x180074b9b  mov     rsi, rcx
0x180074b9e  lea     rdx, aCaviiavsstream_2; "CAVIIAVSStreamParser::ParseStreamFormat"...
0x180074ba5  mov     r8d, 148h; int
0x180074bab  lea     rcx, [rbp+var_30]; this
0x180074baf  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180074bb4  xorps   xmm0, xmm0
0x180074bb7  lea     r15, [rsi+280h]
0x180074bbe  mov     rcx, [r15]; Block
0x180074bc1  movups  xmmword ptr [rbp+var_28.dwDVAAuxSrc], xmm0
0x180074bc5  movups  xmmword ptr [rbp+var_28.dwDVVAuxSrc], xmm0
0x180074bc9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180074bce  lea     r14, [rsi+648h]
0x180074bd5  xor     r13d, r13d
0x180074bd8  mov     rcx, [r14]; Block
0x180074bdb  mov     [r15], r13
0x180074bde  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180074be3  lea     r12, [rsi+650h]
0x180074bea  mov     [r14], r13
0x180074bed  mov     rcx, [r12]; Block
0x180074bf1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180074bf6  mov     rcx, [rsi+630h]; Block
0x180074bfd  mov     [r12], r13
0x180074c01  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180074c06  mov     [rsi+630h], r13
0x180074c0d  cmp     qword ptr [rdi+38h], 20h ; ' '
0x180074c12  jnb     loc_180074CAF
0x180074c18  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180074c1f  mov     ebx, 0C00D36BEh
0x180074c24  test    rcx, rcx
0x180074c27  jnz     short loc_180074C6A
0x180074c29  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180074c2f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180074c36  mov     rcx, rax
0x180074c39  test    rax, rax
0x180074c3c  jz      short loc_180074C5C
0x180074c3e  mov     rax, [rax]
0x180074c41  mov     edx, 7F0h
0x180074c46  mov     rax, [rax+8]
0x180074c4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074c4f  test    eax, eax
0x180074c51  jz      short loc_180074C5C
0x180074c53  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180074c5a  jmp     short loc_180074C6A
0x180074c5c  lea     rcx, qword_1801B07E0; this
0x180074c63  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180074c6a  cmp     [rcx+8], r13b
0x180074c6e  jz      short loc_180074C95
0x180074c70  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180074c75  cmp     [rax+7CCh], ebx
0x180074c7b  jz      short loc_180074C95
0x180074c7d  mov     r9d, ebx; int
0x180074c80  lea     rdx, aCaviiavsstream_2; "CAVIIAVSStreamParser::ParseStreamFormat"...
0x180074c87  mov     r8d, 15Ch; int
0x180074c8d  mov     rcx, rax; this
0x180074c90  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180074c95  mov     edi, 1
0x180074c9a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180074ca1  jb      loc_18007547C
0x180074ca7  lea     edx, [rdi+2Ah]
0x180074caa  jmp     loc_18007545E
0x180074caf  mov     rcx, [rdi+8]
0x180074cb3  lea     r8, [rbp+var_28]
0x180074cb7  call    ??$ReadDataType@IK@@YAJPEAVCSourcePluginBufferReader@@W4DATA_TYPE_BYTE_ORDERING@@PEAK@Z; ReadDataType<uint,ulong>(CSourcePluginBufferReader *,DATA_TYPE_BYTE_ORDERING,ulong *)
0x180074cbc  mov     ebx, eax
0x180074cbe  test    eax, eax
0x180074cc0  jns     loc_180074D58
0x180074cc6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180074ccd  test    rcx, rcx
0x180074cd0  jnz     short loc_180074D13
0x180074cd2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180074cd8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180074cdf  mov     rcx, rax
0x180074ce2  test    rax, rax
0x180074ce5  jz      short loc_180074D05
0x180074ce7  mov     rax, [rax]
0x180074cea  mov     edx, 7F0h
0x180074cef  mov     rax, [rax+8]
0x180074cf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074cf8  test    eax, eax
0x180074cfa  jz      short loc_180074D05
0x180074cfc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180074d03  jmp     short loc_180074D13
0x180074d05  lea     rcx, qword_1801B07E0; this
0x180074d0c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180074d13  cmp     [rcx+8], r13b
0x180074d17  jz      short loc_180074D3E
0x180074d19  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180074d1e  cmp     [rax+7CCh], ebx
0x180074d24  jz      short loc_180074D3E
0x180074d26  mov     r9d, ebx; int
0x180074d29  lea     rdx, aCaviiavsstream_2; "CAVIIAVSStreamParser::ParseStreamFormat"...
0x180074d30  mov     r8d, 15Fh; int
0x180074d36  mov     rcx, rax; this
0x180074d39  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180074d3e  mov     edi, 1
0x180074d43  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180074d4a  jb      loc_18007547C
0x180074d50  lea     edx, [rdi+2Bh]
0x180074d53  jmp     loc_18007545E
0x180074d58  mov     rcx, [rdi+8]
0x180074d5c  lea     r8, [rbp+var_28.dwDVAAuxCtl]
0x180074d60  call    ??$ReadDataType@IK@@YAJPEAVCSourcePluginBufferReader@@W4DATA_TYPE_BYTE_ORDERING@@PEAK@Z; ReadDataType<uint,ulong>(CSourcePluginBufferReader *,DATA_TYPE_BYTE_ORDERING,ulong *)
0x180074d65  mov     ebx, eax
0x180074d67  test    eax, eax
0x180074d69  jns     loc_180074E01
0x180074d6f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180074d76  test    rcx, rcx
0x180074d79  jnz     short loc_180074DBC
0x180074d7b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180074d81  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180074d88  mov     rcx, rax
0x180074d8b  test    rax, rax
0x180074d8e  jz      short loc_180074DAE
0x180074d90  mov     rax, [rax]
0x180074d93  mov     edx, 7F0h
0x180074d98  mov     rax, [rax+8]
0x180074d9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074da1  test    eax, eax
0x180074da3  jz      short loc_180074DAE
0x180074da5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180074dac  jmp     short loc_180074DBC
0x180074dae  lea     rcx, qword_1801B07E0; this
0x180074db5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180074dbc  cmp     [rcx+8], r13b
0x180074dc0  jz      short loc_180074DE7
0x180074dc2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180074dc7  cmp     [rax+7CCh], ebx
0x180074dcd  jz      short loc_180074DE7
0x180074dcf  mov     r9d, ebx; int
0x180074dd2  lea     rdx, aCaviiavsstream_2; "CAVIIAVSStreamParser::ParseStreamFormat"...
0x180074dd9  mov     r8d, 160h; int
0x180074ddf  mov     rcx, rax; this
0x180074de2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180074de7  mov     edi, 1
0x180074dec  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180074df3  jb      loc_18007547C
0x180074df9  lea     edx, [rdi+2Ch]
0x180074dfc  jmp     loc_18007545E
0x180074e01  mov     rcx, [rdi+8]
0x180074e05  lea     r8, [rbp+var_28.dwDVAAuxSrc1]
0x180074e09  call    ??$ReadDataType@IK@@YAJPEAVCSourcePluginBufferReader@@W4DATA_TYPE_BYTE_ORDERING@@PEAK@Z; ReadDataType<uint,ulong>(CSourcePluginBufferReader *,DATA_TYPE_BYTE_ORDERING,ulong *)
0x180074e0e  mov     ebx, eax
0x180074e10  test    eax, eax
0x180074e12  jns     loc_180074EAA
0x180074e18  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180074e1f  test    rcx, rcx
0x180074e22  jnz     short loc_180074E65
0x180074e24  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180074e2a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180074e31  mov     rcx, rax
0x180074e34  test    rax, rax
0x180074e37  jz      short loc_180074E57
0x180074e39  mov     rax, [rax]
0x180074e3c  mov     edx, 7F0h
0x180074e41  mov     rax, [rax+8]
0x180074e45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074e4a  test    eax, eax
0x180074e4c  jz      short loc_180074E57
0x180074e4e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180074e55  jmp     short loc_180074E65
0x180074e57  lea     rcx, qword_1801B07E0; this
0x180074e5e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180074e65  cmp     [rcx+8], r13b
0x180074e69  jz      short loc_180074E90
0x180074e6b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180074e70  cmp     [rax+7CCh], ebx
0x180074e76  jz      short loc_180074E90
0x180074e78  mov     r9d, ebx; int
0x180074e7b  lea     rdx, aCaviiavsstream_2; "CAVIIAVSStreamParser::ParseStreamFormat"...
0x180074e82  mov     r8d, 161h; int
0x180074e88  mov     rcx, rax; this
0x180074e8b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180074e90  mov     edi, 1
0x180074e95  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180074e9c  jb      loc_18007547C
0x180074ea2  lea     edx, [rdi+2Dh]
0x180074ea5  jmp     loc_18007545E
0x180074eaa  mov     rcx, [rdi+8]
0x180074eae  lea     r8, [rbp+var_28.dwDVAAuxCtl1]
0x180074eb2  call    ??$ReadDataType@IK@@YAJPEAVCSourcePluginBufferReader@@W4DATA_TYPE_BYTE_ORDERING@@PEAK@Z; ReadDataType<uint,ulong>(CSourcePluginBufferReader *,DATA_TYPE_BYTE_ORDERING,ulong *)
0x180074eb7  mov     ebx, eax
0x180074eb9  test    eax, eax
0x180074ebb  jns     loc_180074F53
0x180074ec1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180074ec8  test    rcx, rcx
0x180074ecb  jnz     short loc_180074F0E
0x180074ecd  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180074ed3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180074eda  mov     rcx, rax
0x180074edd  test    rax, rax
0x180074ee0  jz      short loc_180074F00
0x180074ee2  mov     rax, [rax]
0x180074ee5  mov     edx, 7F0h
0x180074eea  mov     rax, [rax+8]
0x180074eee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074ef3  test    eax, eax
0x180074ef5  jz      short loc_180074F00
0x180074ef7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180074efe  jmp     short loc_180074F0E
0x180074f00  lea     rcx, qword_1801B07E0; this
0x180074f07  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180074f0e  cmp     [rcx+8], r13b
0x180074f12  jz      short loc_180074F39
0x180074f14  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180074f19  cmp     [rax+7CCh], ebx
0x180074f1f  jz      short loc_180074F39
0x180074f21  mov     r9d, ebx; int
0x180074f24  lea     rdx, aCaviiavsstream_2; "CAVIIAVSStreamParser::ParseStreamFormat"...
0x180074f2b  mov     r8d, 162h; int
0x180074f31  mov     rcx, rax; this
0x180074f34  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180074f39  mov     edi, 1
0x180074f3e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180074f45  jb      loc_18007547C
0x180074f4b  lea     edx, [rdi+2Eh]
0x180074f4e  jmp     loc_18007545E
0x180074f53  mov     rcx, [rdi+8]
0x180074f57  lea     r8, [rbp+var_28.dwDVVAuxSrc]
0x180074f5b  call    ??$ReadDataType@IK@@YAJPEAVCSourcePluginBufferReader@@W4DATA_TYPE_BYTE_ORDERING@@PEAK@Z; ReadDataType<uint,ulong>(CSourcePluginBufferReader *,DATA_TYPE_BYTE_ORDERING,ulong *)
0x180074f60  mov     ebx, eax
0x180074f62  test    eax, eax
0x180074f64  jns     loc_180074FFC
0x180074f6a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180074f71  test    rcx, rcx
0x180074f74  jnz     short loc_180074FB7
0x180074f76  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180074f7c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180074f83  mov     rcx, rax
0x180074f86  test    rax, rax
0x180074f89  jz      short loc_180074FA9
0x180074f8b  mov     rax, [rax]
0x180074f8e  mov     edx, 7F0h
0x180074f93  mov     rax, [rax+8]
0x180074f97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074f9c  test    eax, eax
0x180074f9e  jz      short loc_180074FA9
0x180074fa0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180074fa7  jmp     short loc_180074FB7
0x180074fa9  lea     rcx, qword_1801B07E0; this
0x180074fb0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180074fb7  cmp     [rcx+8], r13b
0x180074fbb  jz      short loc_180074FE2
0x180074fbd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180074fc2  cmp     [rax+7CCh], ebx
0x180074fc8  jz      short loc_180074FE2
0x180074fca  mov     r9d, ebx; int
0x180074fcd  lea     rdx, aCaviiavsstream_2; "CAVIIAVSStreamParser::ParseStreamFormat"...
0x180074fd4  mov     r8d, 163h; int
0x180074fda  mov     rcx, rax; this
0x180074fdd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180074fe2  mov     edi, 1
0x180074fe7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180074fee  jb      loc_18007547C
0x180074ff4  lea     edx, [rdi+2Fh]
0x180074ff7  jmp     loc_18007545E
0x180074ffc  mov     rcx, [rdi+8]
0x180075000  lea     r8, [rbp+var_28.dwDVVAuxCtl]
0x180075004  call    ??$ReadDataType@IK@@YAJPEAVCSourcePluginBufferReader@@W4DATA_TYPE_BYTE_ORDERING@@PEAK@Z; ReadDataType<uint,ulong>(CSourcePluginBufferReader *,DATA_TYPE_BYTE_ORDERING,ulong *)
0x180075009  mov     ebx, eax
0x18007500b  test    eax, eax
0x18007500d  jns     loc_1800750A5
0x180075013  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007501a  test    rcx, rcx
0x18007501d  jnz     short loc_180075060
0x18007501f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180075025  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007502c  mov     rcx, rax
0x18007502f  test    rax, rax
0x180075032  jz      short loc_180075052
0x180075034  mov     rax, [rax]
0x180075037  mov     edx, 7F0h
0x18007503c  mov     rax, [rax+8]
0x180075040  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075045  test    eax, eax
0x180075047  jz      short loc_180075052
0x180075049  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180075050  jmp     short loc_180075060
0x180075052  lea     rcx, qword_1801B07E0; this
0x180075059  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180075060  cmp     [rcx+8], r13b
0x180075064  jz      short loc_18007508B
0x180075066  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007506b  cmp     [rax+7CCh], ebx
0x180075071  jz      short loc_18007508B
0x180075073  mov     r9d, ebx; int
0x180075076  lea     rdx, aCaviiavsstream_2; "CAVIIAVSStreamParser::ParseStreamFormat"...
  ... truncated ...
```
