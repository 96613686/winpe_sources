# CAVIIAVSStreamParser::ParseStreamFormatChunk(CLISTChunkEnumerator *)

- ea: `0x18007a5d0`
- end: `0x18007afad`
- name: `?ParseStreamFormatChunk@CAVIIAVSStreamParser@@EEAAJPEAVCLISTChunkEnumerator@@@Z`
- size: `2525`
- prototype: `__int64 __fastcall(CAVIIAVSStreamParser *__hidden this, struct CLISTChunkEnumerator *)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x1800333a4`
- `0x180079680`
- `0x18007a5d0`
- `0x1800c47ec`
- `0x180110a7c`
- `0x180110a94`
- `0x180110ed0`
- `0x180141218`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007a689`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007a738`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007a7e7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007a896`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007a945`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007a9f4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007aaa3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007ab52`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007ac01`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007ad05`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007adc2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007ae86`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007a689`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007a738`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007a7e7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007a896`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007a945`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007a9f4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007aaa3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007ab52`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007ac01`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007ad05`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007adc2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007ae86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007af2c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007af43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007af5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007af2c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007af43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007af5a`

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
  __int64 v45; // r8
  __int64 v46; // r9
  wchar_t *v47; // rcx
  CallStackTracing *v48; // rax
  struct CallStackContext *v49; // rax
  __int64 v50; // rdx
  wchar_t *v51; // rcx
  CallStackTracing *v52; // rax
  struct CallStackContext *v53; // rax
  wchar_t *v54; // rcx
  CallStackTracing *v55; // rax
  struct CallStackContext *v56; // rax
  struct DVINFO *v57; // rax
  __int64 v58; // rdx
  wchar_t *v59; // rcx
  CallStackTracing *v60; // rax
  struct CallStackContext *v61; // rax
  DWORD dwDVAAuxCtl; // [rsp+20h] [rbp-60h]
  _BYTE v64[8]; // [rsp+50h] [rbp-30h] BYREF
  struct DVINFO v65; // [rsp+58h] [rbp-28h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v64,
    "CAVIIAVSStreamParser::ParseStreamFormatChunk",
    328);
  v4 = (LPVOID *)((char *)this + 640);
  v5 = (void *)*((_QWORD *)this + 80);
  memset(&v65, 0, sizeof(v65));
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
        v11 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
  Data = ReadDataType<unsigned int,unsigned long>(*((_QWORD *)a2 + 1), v10, &v65);
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
        v17 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
  Data = ReadDataType<unsigned int,unsigned long>(*((_QWORD *)a2 + 1), v16, &v65.dwDVAAuxCtl);
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
        v21 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
  Data = ReadDataType<unsigned int,unsigned long>(*((_QWORD *)a2 + 1), v20, &v65.dwDVAAuxSrc1);
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
        v25 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
  Data = ReadDataType<unsigned int,unsigned long>(*((_QWORD *)a2 + 1), v24, &v65.dwDVAAuxCtl1);
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
        v29 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
  Data = ReadDataType<unsigned int,unsigned long>(*((_QWORD *)a2 + 1), v28, &v65.dwDVVAuxSrc);
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
        v33 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
  Data = ReadDataType<unsigned int,unsigned long>(*((_QWORD *)a2 + 1), v32, &v65.dwDVVAuxCtl);
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
        v37 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
  Data = ReadDataType<unsigned int,unsigned long>(*((_QWORD *)a2 + 1), v36, v65.dwDVReserved);
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
        v41 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
  Data = ReadDataType<unsigned int,unsigned long>(*((_QWORD *)a2 + 1), v40, &v65.dwDVReserved[1]);
  if ( Data < 0 )
  {
    v47 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v48 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v44);
      CallStackTracing::s_wpInstance = v48;
      if ( v48 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v48 + 8LL))(v48, 2032) )
      {
        v47 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v47 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v47 + 8) )
    {
      v49 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v47);
      if ( *((_DWORD *)v49 + 499) != Data )
        CallStackContext::TraceFailure(v49, "CAVIIAVSStreamParser::ParseStreamFormatChunk", 358, Data);
    }
    if ( !g_wppLevels )
      goto LABEL_139;
    v15 = 51;
    goto LABEL_138;
  }
  if ( (unsigned __int8)byte_1801BA109 >= 0x20u )
  {
    dwDVAAuxCtl = v65.dwDVAAuxCtl;
    WPP_SF_dddddd(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      52,
      WPP_0c6b2006a0443a18a2b9fa7547964932_Traceguids,
      v65.dwDVAAuxSrc);
  }
  Data = getMediaTypesFromIAVSStream(
           &v65,
           (_QWORD *)this + 80,
           v45,
           v46,
           dwDVAAuxCtl,
           (_QWORD *)this + 201,
           (_QWORD *)this + 202);
  if ( Data < 0 )
  {
    v51 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v52 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v50);
      CallStackTracing::s_wpInstance = v52;
      if ( v52 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v52 + 8LL))(v52, 2032) )
      {
        v51 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v51 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v51 + 8) )
    {
      v53 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v51);
      if ( *((_DWORD *)v53 + 499) != Data )
        CallStackContext::TraceFailure(v53, "CAVIIAVSStreamParser::ParseStreamFormatChunk", 378, Data);
    }
    if ( !g_wppLevels )
      goto LABEL_139;
    v15 = 53;
    goto LABEL_138;
  }
  if ( *v4 && *(_DWORD *)*v4 != 40 || !*v6 && *v8 )
  {
    v54 = (wchar_t *)CallStackTracing::s_wpInstance;
    Data = -1072873844;
    if ( !CallStackTracing::s_wpInstance )
    {
      v55 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v50);
      CallStackTracing::s_wpInstance = v55;
      if ( v55 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v55 + 8LL))(v55, 2032) )
      {
        v54 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v54 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v54 + 8) )
    {
      v56 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v54);
      if ( *((_DWORD *)v56 + 499) != -1072873844 )
        CallStackContext::TraceFailure(v56, "CAVIIAVSStreamParser::ParseStreamFormatChunk", 383, -1072873844);
    }
    if ( !g_wppLevels )
      goto LABEL_139;
    v15 = 54;
    goto LABEL_138;
  }
  *((_DWORD *)this + 398) = 65537;
  v57 = (struct DVINFO *)operator new(0x20u);
  *((_QWORD *)this + 198) = v57;
  if ( v57 )
  {
    *v57 = v65;
    goto LABEL_146;
  }
  v59 = (wchar_t *)CallStackTracing::s_wpInstance;
  Data = -2147024882;
  if ( !CallStackTracing::s_wpInstance )
  {
    v60 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v58);
    CallStackTracing::s_wpInstance = v60;
    if ( v60 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v60 + 8LL))(v60, 2032) )
    {
      v59 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v59 = &qword_1801B97E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
    }
  }
  if ( *((_BYTE *)v59 + 8) )
  {
    v61 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v59);
    if ( *((_DWORD *)v61 + 499) != -2147024882 )
      CallStackContext::TraceFailure(v61, "CAVIIAVSStreamParser::ParseStreamFormatChunk", 393, -2147024882);
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
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v64);
  return (unsigned int)Data;
}

```

## disassembly

```asm
0x18007a5d0  mov     [rsp-38h+arg_10], rbx
0x18007a5d5  push    rbp
0x18007a5d6  push    rsi
0x18007a5d7  push    rdi
0x18007a5d8  push    r12
0x18007a5da  push    r13
0x18007a5dc  push    r14
0x18007a5de  push    r15
0x18007a5e0  mov     rbp, rsp
0x18007a5e3  sub     rsp, 80h
0x18007a5ea  mov     rax, cs:__security_cookie
0x18007a5f1  xor     rax, rsp
0x18007a5f4  mov     [rbp+var_8], rax
0x18007a5f8  mov     rdi, rdx
0x18007a5fb  mov     rsi, rcx
0x18007a5fe  lea     rdx, aCaviiavsstream_2; "CAVIIAVSStreamParser::ParseStreamFormat"...
0x18007a605  mov     r8d, 148h; int
0x18007a60b  lea     rcx, [rbp+var_30]; this
0x18007a60f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18007a614  xorps   xmm0, xmm0
0x18007a617  lea     r15, [rsi+280h]
0x18007a61e  mov     rcx, [r15]; Block
0x18007a621  movups  xmmword ptr [rbp+var_28.dwDVAAuxSrc], xmm0
0x18007a625  movups  xmmword ptr [rbp+var_28.dwDVVAuxSrc], xmm0
0x18007a629  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007a62e  lea     r14, [rsi+648h]
0x18007a635  xor     r13d, r13d
0x18007a638  mov     rcx, [r14]; Block
0x18007a63b  mov     [r15], r13
0x18007a63e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007a643  lea     r12, [rsi+650h]
0x18007a64a  mov     [r14], r13
0x18007a64d  mov     rcx, [r12]; Block
0x18007a651  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007a656  mov     rcx, [rsi+630h]; Block
0x18007a65d  mov     [r12], r13
0x18007a661  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007a666  mov     [rsi+630h], r13
0x18007a66d  cmp     qword ptr [rdi+38h], 20h ; ' '
0x18007a672  jnb     loc_18007A715
0x18007a678  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a67f  mov     ebx, 0C00D36BEh
0x18007a684  test    rcx, rcx
0x18007a687  jnz     short loc_18007A6D0
0x18007a689  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007a690  nop     dword ptr [rax+rax+00h]
0x18007a695  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a69c  mov     rcx, rax
0x18007a69f  test    rax, rax
0x18007a6a2  jz      short loc_18007A6C2
0x18007a6a4  mov     rax, [rax]
0x18007a6a7  mov     edx, 7F0h
0x18007a6ac  mov     rax, [rax+8]
0x18007a6b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a6b5  test    eax, eax
0x18007a6b7  jz      short loc_18007A6C2
0x18007a6b9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a6c0  jmp     short loc_18007A6D0
0x18007a6c2  lea     rcx, qword_1801B97E0; this
0x18007a6c9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a6d0  cmp     [rcx+8], r13b
0x18007a6d4  jz      short loc_18007A6FB
0x18007a6d6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007a6db  cmp     [rax+7CCh], ebx
0x18007a6e1  jz      short loc_18007A6FB
0x18007a6e3  mov     r9d, ebx; int
0x18007a6e6  lea     rdx, aCaviiavsstream_2; "CAVIIAVSStreamParser::ParseStreamFormat"...
0x18007a6ed  mov     r8d, 15Ch; int
0x18007a6f3  mov     rcx, rax; this
0x18007a6f6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007a6fb  mov     edi, 1
0x18007a700  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18007a707  jb      loc_18007AF24
0x18007a70d  lea     edx, [rdi+2Ah]
0x18007a710  jmp     loc_18007AF06
0x18007a715  mov     rcx, [rdi+8]
0x18007a719  lea     r8, [rbp+var_28]
0x18007a71d  call    ??$ReadDataType@IK@@YAJPEAVCSourcePluginBufferReader@@W4DATA_TYPE_BYTE_ORDERING@@PEAK@Z; ReadDataType<uint,ulong>(CSourcePluginBufferReader *,DATA_TYPE_BYTE_ORDERING,ulong *)
0x18007a722  mov     ebx, eax
0x18007a724  test    eax, eax
0x18007a726  jns     loc_18007A7C4
0x18007a72c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a733  test    rcx, rcx
0x18007a736  jnz     short loc_18007A77F
0x18007a738  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007a73f  nop     dword ptr [rax+rax+00h]
0x18007a744  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a74b  mov     rcx, rax
0x18007a74e  test    rax, rax
0x18007a751  jz      short loc_18007A771
0x18007a753  mov     rax, [rax]
0x18007a756  mov     edx, 7F0h
0x18007a75b  mov     rax, [rax+8]
0x18007a75f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a764  test    eax, eax
0x18007a766  jz      short loc_18007A771
0x18007a768  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a76f  jmp     short loc_18007A77F
0x18007a771  lea     rcx, qword_1801B97E0; this
0x18007a778  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a77f  cmp     [rcx+8], r13b
0x18007a783  jz      short loc_18007A7AA
0x18007a785  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007a78a  cmp     [rax+7CCh], ebx
0x18007a790  jz      short loc_18007A7AA
0x18007a792  mov     r9d, ebx; int
0x18007a795  lea     rdx, aCaviiavsstream_2; "CAVIIAVSStreamParser::ParseStreamFormat"...
0x18007a79c  mov     r8d, 15Fh; int
0x18007a7a2  mov     rcx, rax; this
0x18007a7a5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007a7aa  mov     edi, 1
0x18007a7af  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18007a7b6  jb      loc_18007AF24
0x18007a7bc  lea     edx, [rdi+2Bh]
0x18007a7bf  jmp     loc_18007AF06
0x18007a7c4  mov     rcx, [rdi+8]
0x18007a7c8  lea     r8, [rbp+var_28.dwDVAAuxCtl]
0x18007a7cc  call    ??$ReadDataType@IK@@YAJPEAVCSourcePluginBufferReader@@W4DATA_TYPE_BYTE_ORDERING@@PEAK@Z; ReadDataType<uint,ulong>(CSourcePluginBufferReader *,DATA_TYPE_BYTE_ORDERING,ulong *)
0x18007a7d1  mov     ebx, eax
0x18007a7d3  test    eax, eax
0x18007a7d5  jns     loc_18007A873
0x18007a7db  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a7e2  test    rcx, rcx
0x18007a7e5  jnz     short loc_18007A82E
0x18007a7e7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007a7ee  nop     dword ptr [rax+rax+00h]
0x18007a7f3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a7fa  mov     rcx, rax
0x18007a7fd  test    rax, rax
0x18007a800  jz      short loc_18007A820
0x18007a802  mov     rax, [rax]
0x18007a805  mov     edx, 7F0h
0x18007a80a  mov     rax, [rax+8]
0x18007a80e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a813  test    eax, eax
0x18007a815  jz      short loc_18007A820
0x18007a817  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a81e  jmp     short loc_18007A82E
0x18007a820  lea     rcx, qword_1801B97E0; this
0x18007a827  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a82e  cmp     [rcx+8], r13b
0x18007a832  jz      short loc_18007A859
0x18007a834  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007a839  cmp     [rax+7CCh], ebx
0x18007a83f  jz      short loc_18007A859
0x18007a841  mov     r9d, ebx; int
0x18007a844  lea     rdx, aCaviiavsstream_2; "CAVIIAVSStreamParser::ParseStreamFormat"...
0x18007a84b  mov     r8d, 160h; int
0x18007a851  mov     rcx, rax; this
0x18007a854  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007a859  mov     edi, 1
0x18007a85e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18007a865  jb      loc_18007AF24
0x18007a86b  lea     edx, [rdi+2Ch]
0x18007a86e  jmp     loc_18007AF06
0x18007a873  mov     rcx, [rdi+8]
0x18007a877  lea     r8, [rbp+var_28.dwDVAAuxSrc1]
0x18007a87b  call    ??$ReadDataType@IK@@YAJPEAVCSourcePluginBufferReader@@W4DATA_TYPE_BYTE_ORDERING@@PEAK@Z; ReadDataType<uint,ulong>(CSourcePluginBufferReader *,DATA_TYPE_BYTE_ORDERING,ulong *)
0x18007a880  mov     ebx, eax
0x18007a882  test    eax, eax
0x18007a884  jns     loc_18007A922
0x18007a88a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a891  test    rcx, rcx
0x18007a894  jnz     short loc_18007A8DD
0x18007a896  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007a89d  nop     dword ptr [rax+rax+00h]
0x18007a8a2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a8a9  mov     rcx, rax
0x18007a8ac  test    rax, rax
0x18007a8af  jz      short loc_18007A8CF
0x18007a8b1  mov     rax, [rax]
0x18007a8b4  mov     edx, 7F0h
0x18007a8b9  mov     rax, [rax+8]
0x18007a8bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a8c2  test    eax, eax
0x18007a8c4  jz      short loc_18007A8CF
0x18007a8c6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a8cd  jmp     short loc_18007A8DD
0x18007a8cf  lea     rcx, qword_1801B97E0; this
0x18007a8d6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a8dd  cmp     [rcx+8], r13b
0x18007a8e1  jz      short loc_18007A908
0x18007a8e3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007a8e8  cmp     [rax+7CCh], ebx
0x18007a8ee  jz      short loc_18007A908
0x18007a8f0  mov     r9d, ebx; int
0x18007a8f3  lea     rdx, aCaviiavsstream_2; "CAVIIAVSStreamParser::ParseStreamFormat"...
0x18007a8fa  mov     r8d, 161h; int
0x18007a900  mov     rcx, rax; this
0x18007a903  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007a908  mov     edi, 1
0x18007a90d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18007a914  jb      loc_18007AF24
0x18007a91a  lea     edx, [rdi+2Dh]
0x18007a91d  jmp     loc_18007AF06
0x18007a922  mov     rcx, [rdi+8]
0x18007a926  lea     r8, [rbp+var_28.dwDVAAuxCtl1]
0x18007a92a  call    ??$ReadDataType@IK@@YAJPEAVCSourcePluginBufferReader@@W4DATA_TYPE_BYTE_ORDERING@@PEAK@Z; ReadDataType<uint,ulong>(CSourcePluginBufferReader *,DATA_TYPE_BYTE_ORDERING,ulong *)
0x18007a92f  mov     ebx, eax
0x18007a931  test    eax, eax
0x18007a933  jns     loc_18007A9D1
0x18007a939  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a940  test    rcx, rcx
0x18007a943  jnz     short loc_18007A98C
0x18007a945  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007a94c  nop     dword ptr [rax+rax+00h]
0x18007a951  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a958  mov     rcx, rax
0x18007a95b  test    rax, rax
0x18007a95e  jz      short loc_18007A97E
0x18007a960  mov     rax, [rax]
0x18007a963  mov     edx, 7F0h
0x18007a968  mov     rax, [rax+8]
0x18007a96c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a971  test    eax, eax
0x18007a973  jz      short loc_18007A97E
0x18007a975  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a97c  jmp     short loc_18007A98C
0x18007a97e  lea     rcx, qword_1801B97E0; this
0x18007a985  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a98c  cmp     [rcx+8], r13b
0x18007a990  jz      short loc_18007A9B7
0x18007a992  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007a997  cmp     [rax+7CCh], ebx
0x18007a99d  jz      short loc_18007A9B7
0x18007a99f  mov     r9d, ebx; int
0x18007a9a2  lea     rdx, aCaviiavsstream_2; "CAVIIAVSStreamParser::ParseStreamFormat"...
0x18007a9a9  mov     r8d, 162h; int
0x18007a9af  mov     rcx, rax; this
0x18007a9b2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007a9b7  mov     edi, 1
0x18007a9bc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18007a9c3  jb      loc_18007AF24
0x18007a9c9  lea     edx, [rdi+2Eh]
0x18007a9cc  jmp     loc_18007AF06
0x18007a9d1  mov     rcx, [rdi+8]
0x18007a9d5  lea     r8, [rbp+var_28.dwDVVAuxSrc]
0x18007a9d9  call    ??$ReadDataType@IK@@YAJPEAVCSourcePluginBufferReader@@W4DATA_TYPE_BYTE_ORDERING@@PEAK@Z; ReadDataType<uint,ulong>(CSourcePluginBufferReader *,DATA_TYPE_BYTE_ORDERING,ulong *)
0x18007a9de  mov     ebx, eax
0x18007a9e0  test    eax, eax
0x18007a9e2  jns     loc_18007AA80
0x18007a9e8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a9ef  test    rcx, rcx
0x18007a9f2  jnz     short loc_18007AA3B
0x18007a9f4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007a9fb  nop     dword ptr [rax+rax+00h]
0x18007aa00  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007aa07  mov     rcx, rax
0x18007aa0a  test    rax, rax
0x18007aa0d  jz      short loc_18007AA2D
0x18007aa0f  mov     rax, [rax]
0x18007aa12  mov     edx, 7F0h
0x18007aa17  mov     rax, [rax+8]
0x18007aa1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007aa20  test    eax, eax
0x18007aa22  jz      short loc_18007AA2D
0x18007aa24  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007aa2b  jmp     short loc_18007AA3B
0x18007aa2d  lea     rcx, qword_1801B97E0; this
0x18007aa34  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007aa3b  cmp     [rcx+8], r13b
0x18007aa3f  jz      short loc_18007AA66
0x18007aa41  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007aa46  cmp     [rax+7CCh], ebx
0x18007aa4c  jz      short loc_18007AA66
0x18007aa4e  mov     r9d, ebx; int
0x18007aa51  lea     rdx, aCaviiavsstream_2; "CAVIIAVSStreamParser::ParseStreamFormat"...
0x18007aa58  mov     r8d, 163h; int
0x18007aa5e  mov     rcx, rax; this
0x18007aa61  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007aa66  mov     edi, 1
0x18007aa6b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18007aa72  jb      loc_18007AF24
0x18007aa78  lea     edx, [rdi+2Fh]
0x18007aa7b  jmp     loc_18007AF06
0x18007aa80  mov     rcx, [rdi+8]
0x18007aa84  lea     r8, [rbp+var_28.dwDVVAuxCtl]
0x18007aa88  call    ??$ReadDataType@IK@@YAJPEAVCSourcePluginBufferReader@@W4DATA_TYPE_BYTE_ORDERING@@PEAK@Z; ReadDataType<uint,ulong>(CSourcePluginBufferReader *,DATA_TYPE_BYTE_ORDERING,ulong *)
0x18007aa8d  mov     ebx, eax
0x18007aa8f  test    eax, eax
0x18007aa91  jns     loc_18007AB2F
0x18007aa97  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007aa9e  test    rcx, rcx
0x18007aaa1  jnz     short loc_18007AAEA
0x18007aaa3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007aaaa  nop     dword ptr [rax+rax+00h]
0x18007aaaf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007aab6  mov     rcx, rax
0x18007aab9  test    rax, rax
0x18007aabc  jz      short loc_18007AADC
0x18007aabe  mov     rax, [rax]
0x18007aac1  mov     edx, 7F0h
0x18007aac6  mov     rax, [rax+8]
0x18007aaca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007aacf  test    eax, eax
0x18007aad1  jz      short loc_18007AADC
0x18007aad3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007aada  jmp     short loc_18007AAEA
0x18007aadc  lea     rcx, qword_1801B97E0; this
0x18007aae3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
  ... truncated ...
```
