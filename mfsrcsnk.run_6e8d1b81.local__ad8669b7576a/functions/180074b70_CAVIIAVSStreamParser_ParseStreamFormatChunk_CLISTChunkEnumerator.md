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
  wchar_t *v11; // rcx
  int Data; // ebx
  CallStackTracing *v13; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v15; // rdx
  __int64 v16; // rdx
  wchar_t *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  __int64 v20; // rdx
  wchar_t *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 v24; // rdx
  wchar_t *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  __int64 v28; // rdx
  wchar_t *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  __int64 v32; // rdx
  wchar_t *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  __int64 v36; // rdx
  wchar_t *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  __int64 v40; // rdx
  wchar_t *v41; // rcx
  CallStackTracing *v42; // rax
  struct CallStackContext *v43; // rax
  __int64 v44; // rdx
  wchar_t *v45; // rcx
  CallStackTracing *v46; // rax
  struct CallStackContext *v47; // rax
  __int64 v48; // rdx
  wchar_t *v49; // rcx
  CallStackTracing *v50; // rax
  struct CallStackContext *v51; // rax
  wchar_t *v52; // rcx
  CallStackTracing *v53; // rax
  struct CallStackContext *v54; // rax
  struct DVINFO *v55; // rax
  __int64 v56; // rdx
  wchar_t *v57; // rcx
  CallStackTracing *v58; // rax
  struct CallStackContext *v59; // rax
  int v61; // [rsp+20h] [rbp-60h]
  _BYTE v62[8]; // [rsp+50h] [rbp-30h] BYREF
  struct DVINFO v63; // [rsp+58h] [rbp-28h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v62,
    "CAVIIAVSStreamParser::ParseStreamFormatChunk",
    328);
  v4 = (LPVOID *)((char *)this + 640);
  v5 = (void *)*((_QWORD *)this + 80);
  memset(&v63, 0, sizeof(v63));
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
    v11 = (wchar_t *)CallStackTracing::s_wpInstance;
    Data = -1072875842;
    if ( !CallStackTracing::s_wpInstance )
    {
      v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
      CallStackTracing::s_wpInstance = v13;
      if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
      {
        v11 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v11 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v11 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072875842 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CAVIIAVSStreamParser::ParseStreamFormatChunk",
          348,
          -1072875842);
    }
    if ( !g_wppLevels )
      goto LABEL_139;
    v15 = 43;
    goto LABEL_138;
  }
  Data = ReadDataType<unsigned int,unsigned long>(*((_QWORD *)a2 + 1), v10, &v63);
  if ( Data < 0 )
  {
    v17 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16);
      CallStackTracing::s_wpInstance = v18;
      if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
      {
        v17 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v17 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v17 + 8) )
    {
      v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
      if ( *((_DWORD *)v19 + 499) != Data )
        CallStackContext::TraceFailure(v19, "CAVIIAVSStreamParser::ParseStreamFormatChunk", 351, Data);
    }
    if ( !g_wppLevels )
      goto LABEL_139;
    v15 = 44;
    goto LABEL_138;
  }
  Data = ReadDataType<unsigned int,unsigned long>(*((_QWORD *)a2 + 1), v16, &v63.dwDVAAuxCtl);
  if ( Data < 0 )
  {
    v21 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20);
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
        CallStackContext::TraceFailure(v23, "CAVIIAVSStreamParser::ParseStreamFormatChunk", 352, Data);
    }
    if ( !g_wppLevels )
      goto LABEL_139;
    v15 = 45;
    goto LABEL_138;
  }
  Data = ReadDataType<unsigned int,unsigned long>(*((_QWORD *)a2 + 1), v20, &v63.dwDVAAuxSrc1);
  if ( Data < 0 )
  {
    v25 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24);
      CallStackTracing::s_wpInstance = v26;
      if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
      {
        v25 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v25 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v25 + 8) )
    {
      v27 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
      if ( *((_DWORD *)v27 + 499) != Data )
        CallStackContext::TraceFailure(v27, "CAVIIAVSStreamParser::ParseStreamFormatChunk", 353, Data);
    }
    if ( !g_wppLevels )
      goto LABEL_139;
    v15 = 46;
    goto LABEL_138;
  }
  Data = ReadDataType<unsigned int,unsigned long>(*((_QWORD *)a2 + 1), v24, &v63.dwDVAAuxCtl1);
  if ( Data < 0 )
  {
    v29 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28);
      CallStackTracing::s_wpInstance = v30;
      if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
      {
        v29 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v29 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v29 + 8) )
    {
      v31 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
      if ( *((_DWORD *)v31 + 499) != Data )
        CallStackContext::TraceFailure(v31, "CAVIIAVSStreamParser::ParseStreamFormatChunk", 354, Data);
    }
    if ( !g_wppLevels )
      goto LABEL_139;
    v15 = 47;
    goto LABEL_138;
  }
  Data = ReadDataType<unsigned int,unsigned long>(*((_QWORD *)a2 + 1), v28, &v63.dwDVVAuxSrc);
  if ( Data < 0 )
  {
    v33 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32);
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
        CallStackContext::TraceFailure(v35, "CAVIIAVSStreamParser::ParseStreamFormatChunk", 355, Data);
    }
    if ( !g_wppLevels )
      goto LABEL_139;
    v15 = 48;
    goto LABEL_138;
  }
  Data = ReadDataType<unsigned int,unsigned long>(*((_QWORD *)a2 + 1), v32, &v63.dwDVVAuxCtl);
  if ( Data < 0 )
  {
    v37 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v36);
      CallStackTracing::s_wpInstance = v38;
      if ( v38 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
      {
        v37 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v37 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v37 + 8) )
    {
      v39 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
      if ( *((_DWORD *)v39 + 499) != Data )
        CallStackContext::TraceFailure(v39, "CAVIIAVSStreamParser::ParseStreamFormatChunk", 356, Data);
    }
    if ( !g_wppLevels )
      goto LABEL_139;
    v15 = 49;
    goto LABEL_138;
  }
  Data = ReadDataType<unsigned int,unsigned long>(*((_QWORD *)a2 + 1), v36, v63.dwDVReserved);
  if ( Data < 0 )
  {
    v41 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v40);
      CallStackTracing::s_wpInstance = v42;
      if ( v42 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
      {
        v41 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v41 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v41 + 8) )
    {
      v43 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v41);
      if ( *((_DWORD *)v43 + 499) != Data )
        CallStackContext::TraceFailure(v43, "CAVIIAVSStreamParser::ParseStreamFormatChunk", 357, Data);
    }
    if ( !g_wppLevels )
      goto LABEL_139;
    v15 = 50;
    goto LABEL_138;
  }
  Data = ReadDataType<unsigned int,unsigned long>(*((_QWORD *)a2 + 1), v40, &v63.dwDVReserved[1]);
  if ( Data < 0 )
  {
    v45 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v44);
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
        CallStackContext::TraceFailure(v47, "CAVIIAVSStreamParser::ParseStreamFormatChunk", 358, Data);
    }
    if ( !g_wppLevels )
      goto LABEL_139;
    v15 = 51;
    goto LABEL_138;
  }
  if ( (unsigned __int8)byte_1801B1109 >= 0x20u )
    WPP_SF_dddddd(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      52,
      WPP_0c6b2006a0443a18a2b9fa7547964932_Traceguids,
      v63.dwDVAAuxSrc,
      v63.dwDVAAuxCtl,
      v63.dwDVAAuxSrc1,
      v63.dwDVAAuxCtl1,
      v63.dwDVVAuxSrc,
      v63.dwDVVAuxCtl);
  Data = getMediaTypesFromIAVSStream(&v63, v61, (__int64)this + 1608, (__int64)this + 1616);
  if ( Data < 0 )
  {
    v49 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v48);
      CallStackTracing::s_wpInstance = v50;
      if ( v50 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
      {
        v49 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v49 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v49 + 8) )
    {
      v51 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v49);
      if ( *((_DWORD *)v51 + 499) != Data )
        CallStackContext::TraceFailure(v51, "CAVIIAVSStreamParser::ParseStreamFormatChunk", 378, Data);
    }
    if ( !g_wppLevels )
      goto LABEL_139;
    v15 = 53;
    goto LABEL_138;
  }
  if ( *v4 && *(_DWORD *)*v4 != 40 || !*v6 && *v8 )
  {
    v52 = (wchar_t *)CallStackTracing::s_wpInstance;
    Data = -1072873844;
    if ( !CallStackTracing::s_wpInstance )
    {
      v53 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v48);
      CallStackTracing::s_wpInstance = v53;
      if ( v53 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v53 + 8LL))(v53, 2032) )
      {
        v52 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v52 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v52 + 8) )
    {
      v54 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v52);
      if ( *((_DWORD *)v54 + 499) != -1072873844 )
        CallStackContext::TraceFailure(v54, "CAVIIAVSStreamParser::ParseStreamFormatChunk", 383, -1072873844);
    }
    if ( !g_wppLevels )
      goto LABEL_139;
    v15 = 54;
    goto LABEL_138;
  }
  *((_DWORD *)this + 398) = 65537;
  v55 = (struct DVINFO *)operator new(0x20u);
  *((_QWORD *)this + 198) = v55;
  if ( v55 )
  {
    *v55 = v63;
    goto LABEL_146;
  }
  v57 = (wchar_t *)CallStackTracing::s_wpInstance;
  Data = -2147024882;
  if ( !CallStackTracing::s_wpInstance )
  {
    v58 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v56);
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
    if ( *((_DWORD *)v59 + 499) != -2147024882 )
      CallStackContext::TraceFailure(v59, "CAVIIAVSStreamParser::ParseStreamFormatChunk", 393, -2147024882);
  }
  if ( g_wppLevels )
  {
    v15 = 55;
LABEL_138:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, WPP_0c6b2006a0443a18a2b9fa7547964932_Traceguids, this, Data);
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
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v62);
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
