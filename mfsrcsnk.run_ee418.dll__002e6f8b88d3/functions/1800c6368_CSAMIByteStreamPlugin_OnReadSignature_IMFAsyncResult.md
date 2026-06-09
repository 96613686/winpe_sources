# CSAMIByteStreamPlugin::OnReadSignature(IMFAsyncResult *)

- ea: `0x1800c6368`
- end: `0x1800c692b`
- name: `?OnReadSignature@CSAMIByteStreamPlugin@@IEAAJPEAUIMFAsyncResult@@@Z`
- size: `1475`
- prototype: `__int64 __fastcall(CSAMIByteStreamPlugin *__hidden this, struct IMFAsyncResult *)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18010fc60`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180034d10`
- `0x180073b14`
- `0x1800c6368`
- `0x1800c6934`
- `0x1800e043c`
- `0x1801099f0`
- `0x18011728c`
- `0x180117374`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c68c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c68c0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800c68b2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800c68b2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800c68ec`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800c68ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c68e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c68e2`
- `MFPlat!MFPutWorkItemEx2` at `0x1800c6899`
- `MFPlat!MFPutWorkItemEx2` at `0x1800c6899`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c63d1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c649b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c653c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c65f4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c66b0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c67b5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c63d1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c649b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c653c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c65f4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c66b0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c67b5`

## string_xrefs

- `0x1800c6391`: `CSAMIByteStreamPlugin::OnReadSignature`

## pseudocode

```c
__int64 __fastcall CSAMIByteStreamPlugin::OnReadSignature(CSAMIByteStreamPlugin *this, struct IMFAsyncResult *a2)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9
  wchar_t *v7; // rcx
  int v8; // ebx
  CallStackTracing *v9; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  wchar_t *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  IMFAsyncResult *v18; // rsi
  wchar_t *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  wchar_t *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  DWORD v28; // edi
  __int64 v29; // rdx
  wchar_t *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  const char *v33; // rax
  const char *v34; // rdx
  __int64 v35; // r8
  __int64 v36; // r9
  wchar_t *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  struct IMFAsyncResultVtbl *lpVtbl; // rcx
  HANDLE EventW; // rax
  signed int LastError; // eax
  bool v43; // sf
  _BYTE v45[4]; // [rsp+30h] [rbp-99h] BYREF
  int v46; // [rsp+34h] [rbp-95h] BYREF
  unsigned int v47; // [rsp+38h] [rbp-91h] BYREF
  IMFAsyncResult *pResult; // [rsp+40h] [rbp-89h] BYREF
  int v49; // [rsp+48h] [rbp-81h] BYREF
  __int64 v50; // [rsp+50h] [rbp-79h] BYREF
  int v51; // [rsp+58h] [rbp-71h]
  int v52; // [rsp+5Ch] [rbp-6Dh]
  char *v53; // [rsp+60h] [rbp-69h]
  char v54; // [rsp+68h] [rbp-61h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v45, "CSAMIByteStreamPlugin::OnReadSignature", 145);
  pResult = 0;
  if ( !a2 )
  {
    v7 = (wchar_t *)CallStackTracing::s_wpInstance;
    v8 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v5, v6);
      CallStackTracing::s_wpInstance = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
      {
        v7 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467261 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CSAMIByteStreamPlugin::OnReadSignature",
          155,
          -2147467261);
    }
    if ( g_wppLevels )
    {
      v11 = 22;
LABEL_12:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_dc4445c74a623006578798248b483e8b_Traceguids, this, v8);
      goto LABEL_89;
    }
    goto LABEL_89;
  }
  v8 = ((__int64 (__fastcall *)(struct IMFAsyncResult *, IMFAsyncResult **))a2->lpVtbl->GetState)(a2, &pResult);
  if ( v8 >= 0 )
  {
    v18 = pResult;
    if ( !pResult )
    {
      v19 = (wchar_t *)CallStackTracing::s_wpInstance;
      v8 = -2147024809;
      if ( !CallStackTracing::s_wpInstance )
      {
        v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v13, v14);
        CallStackTracing::s_wpInstance = v20;
        if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
        {
          v19 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v19 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v19 + 8) )
      {
        v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
        if ( *((_DWORD *)v21 + 499) != -2147024809 )
          CallStackContext::TraceFailure(v21, "CSAMIByteStreamPlugin::OnReadSignature", 163, -2147024809);
      }
      if ( g_wppLevels )
      {
        v11 = 24;
        goto LABEL_12;
      }
      goto LABEL_89;
    }
    v47 = 0;
    v8 = (*((__int64 (__fastcall **)(struct IMFAsyncResultVtbl *, struct IMFAsyncResult *, unsigned int *))pResult[14].lpVtbl->QueryInterface
          + 11))(
           pResult[14].lpVtbl,
           a2,
           &v47);
    if ( v8 >= 0 )
    {
      if ( v47 >= 6 )
      {
        v52 = 128;
        v51 = 0;
        v28 = 1;
        v50 = v50 & 0xFFFFFFF8 | 1;
        v53 = &v54;
        if ( v18 != (IMFAsyncResult *)-136LL )
          CMFBaseStringT<char>::_Append(&v50, &v18[17], 6);
        v33 = (const char *)CMFBaseStringT<char>::PContents(&v50);
        if ( (int)v36 < 0 || (_DWORD)v35 != 6 || !v33 || !wms_ncmp(v33, v34, 6) )
        {
          v37 = (wchar_t *)CallStackTracing::s_wpInstance;
          v8 = -1072875842;
          if ( !CallStackTracing::s_wpInstance )
          {
            v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v34, v35, v36);
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
            if ( *((_DWORD *)v39 + 499) != -1072875842 )
              CallStackContext::TraceFailure(v39, "CSAMIByteStreamPlugin::OnReadSignature", 183, -1072875842);
          }
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              27,
              &WPP_dc4445c74a623006578798248b483e8b_Traceguids,
              this,
              -1072875842);
        }
        CMFBaseStringT<char>::~CMFBaseStringT<char>(&v50);
      }
      else
      {
        v30 = (wchar_t *)CallStackTracing::s_wpInstance;
        v8 = -1072875792;
        if ( !CallStackTracing::s_wpInstance )
        {
          v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22, v23, v24);
          CallStackTracing::s_wpInstance = v31;
          if ( v31 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
          {
            v30 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v30 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v30 + 8) )
        {
          v32 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
          if ( *((_DWORD *)v32 + 499) != -1072875792 )
            CallStackContext::TraceFailure(v32, "CSAMIByteStreamPlugin::OnReadSignature", 174, -1072875792);
        }
        v28 = 1;
        if ( g_wppLevels )
        {
          v29 = 26;
          goto LABEL_46;
        }
      }
    }
    else
    {
      v25 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22, v23, v24);
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
        if ( *((_DWORD *)v27 + 499) != v8 )
          CallStackContext::TraceFailure(v27, "CSAMIByteStreamPlugin::OnReadSignature", 171, v8);
      }
      v28 = 1;
      if ( g_wppLevels )
      {
        v29 = 25;
LABEL_46:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v29, &WPP_dc4445c74a623006578798248b483e8b_Traceguids, this, v8);
      }
    }
    lpVtbl = v18[5].lpVtbl;
    LODWORD(v18[6].lpVtbl) = v8;
    if ( lpVtbl )
    {
      v49 = 0;
      v46 = 0;
      if ( (*((int (__fastcall **)(struct IMFAsyncResultVtbl *, int *, int *))lpVtbl->QueryInterface + 3))(
             lpVtbl,
             &v49,
             &v46) >= 0 )
        v28 = v46;
      else
        v46 = 1;
      MFPutWorkItemEx2(v28, 0, v18);
      goto LABEL_89;
    }
    if ( !v18[7].lpVtbl )
    {
      EventW = CreateEventW(0, 1, 0, 0);
      if ( EventW )
      {
        if ( _InterlockedCompareExchange64((volatile signed __int64 *)&v18[7], (signed __int64)EventW, 0) )
          CloseHandle(EventW);
      }
      else
      {
        LastError = GetLastError();
        v43 = LastError < 0;
        if ( LastError > 0 )
          v43 = 1;
        if ( v43 )
          goto LABEL_89;
      }
    }
    SetEvent(v18[7].lpVtbl);
    goto LABEL_89;
  }
  v15 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v13, v14);
    CallStackTracing::s_wpInstance = v16;
    if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
    {
      v15 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v15 = &qword_1801B07E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
    }
  }
  if ( *((_BYTE *)v15 + 8) )
  {
    v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
    if ( *((_DWORD *)v17 + 499) != v8 )
      CallStackContext::TraceFailure(v17, "CSAMIByteStreamPlugin::OnReadSignature", 161, v8);
  }
  if ( g_wppLevels )
  {
    v11 = 23;
    goto LABEL_12;
  }
LABEL_89:
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&pResult);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v45);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800c6368  mov     [rsp-8+arg_10], rbx
0x1800c636d  push    rbp
0x1800c636e  push    rsi
0x1800c636f  push    rdi
0x1800c6370  push    r13
0x1800c6372  push    r14
0x1800c6374  lea     rbp, [rsp-37h]
0x1800c6379  sub     rsp, 100h
0x1800c6380  mov     rax, cs:__security_cookie
0x1800c6387  xor     rax, rsp
0x1800c638a  mov     [rbp+57h+var_30], rax
0x1800c638e  mov     rdi, rdx
0x1800c6391  lea     r13, aCsamibytestrea_0; "CSAMIByteStreamPlugin::OnReadSignature"
0x1800c6398  mov     r14, rcx
0x1800c639b  mov     rdx, r13; char *
0x1800c639e  mov     r8d, 91h; int
0x1800c63a4  lea     rcx, [rsp+120h+var_F0]; this
0x1800c63a9  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800c63ae  mov     [rsp+120h+pResult], 0
0x1800c63b7  test    rdi, rdi
0x1800c63ba  jnz     loc_1800C6471
0x1800c63c0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c63c7  mov     ebx, 80004003h
0x1800c63cc  test    rcx, rcx
0x1800c63cf  jnz     short loc_1800C6412
0x1800c63d1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800c63d7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c63de  mov     rcx, rax
0x1800c63e1  test    rax, rax
0x1800c63e4  jz      short loc_1800C6404
0x1800c63e6  mov     rax, [rax]
0x1800c63e9  mov     edx, 7F0h
0x1800c63ee  mov     rax, [rax+8]
0x1800c63f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c63f7  test    eax, eax
0x1800c63f9  jz      short loc_1800C6404
0x1800c63fb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c6402  jmp     short loc_1800C6412
0x1800c6404  lea     rcx, qword_1801B07E0; this
0x1800c640b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c6412  cmp     byte ptr [rcx+8], 0
0x1800c6416  jz      short loc_1800C6439
0x1800c6418  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800c641d  cmp     [rax+7CCh], ebx
0x1800c6423  jz      short loc_1800C6439
0x1800c6425  mov     r9d, ebx; int
0x1800c6428  mov     r8d, 9Bh; int
0x1800c642e  mov     rdx, r13; char *
0x1800c6431  mov     rcx, rax; this
0x1800c6434  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800c6439  mov     edi, 1
0x1800c643e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800c6445  jb      loc_1800C68F2
0x1800c644b  lea     edx, [rdi+15h]
0x1800c644e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c6455  lea     r8, WPP_dc4445c74a623006578798248b483e8b_Traceguids
0x1800c645c  mov     r9, r14
0x1800c645f  mov     [rsp+120h+var_100], ebx
0x1800c6463  mov     rcx, [rcx+10h]
0x1800c6467  call    WPP_SF_qD
0x1800c646c  jmp     loc_1800C68F2
0x1800c6471  mov     rax, [rdi]
0x1800c6474  lea     rdx, [rsp+120h+pResult]
0x1800c6479  mov     rcx, rdi
0x1800c647c  mov     rax, [rax+18h]
0x1800c6480  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6485  mov     ebx, eax
0x1800c6487  test    eax, eax
0x1800c6489  jns     loc_1800C651D
0x1800c648f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c6496  test    rcx, rcx
0x1800c6499  jnz     short loc_1800C64DC
0x1800c649b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800c64a1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c64a8  mov     rcx, rax
0x1800c64ab  test    rax, rax
0x1800c64ae  jz      short loc_1800C64CE
0x1800c64b0  mov     rax, [rax]
0x1800c64b3  mov     edx, 7F0h
0x1800c64b8  mov     rax, [rax+8]
0x1800c64bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c64c1  test    eax, eax
0x1800c64c3  jz      short loc_1800C64CE
0x1800c64c5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c64cc  jmp     short loc_1800C64DC
0x1800c64ce  lea     rcx, qword_1801B07E0; this
0x1800c64d5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c64dc  cmp     byte ptr [rcx+8], 0
0x1800c64e0  jz      short loc_1800C6503
0x1800c64e2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800c64e7  cmp     [rax+7CCh], ebx
0x1800c64ed  jz      short loc_1800C6503
0x1800c64ef  mov     r9d, ebx; int
0x1800c64f2  mov     r8d, 0A1h; int
0x1800c64f8  mov     rdx, r13; char *
0x1800c64fb  mov     rcx, rax; this
0x1800c64fe  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800c6503  mov     edi, 1
0x1800c6508  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800c650f  jb      loc_1800C68F2
0x1800c6515  lea     edx, [rdi+16h]
0x1800c6518  jmp     loc_1800C644E
0x1800c651d  mov     rsi, [rsp+120h+pResult]
0x1800c6522  test    rsi, rsi
0x1800c6525  jnz     loc_1800C65BE
0x1800c652b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c6532  mov     ebx, 80070057h
0x1800c6537  test    rcx, rcx
0x1800c653a  jnz     short loc_1800C657D
0x1800c653c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800c6542  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c6549  mov     rcx, rax
0x1800c654c  test    rax, rax
0x1800c654f  jz      short loc_1800C656F
0x1800c6551  mov     rax, [rax]
0x1800c6554  mov     edx, 7F0h
0x1800c6559  mov     rax, [rax+8]
0x1800c655d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6562  test    eax, eax
0x1800c6564  jz      short loc_1800C656F
0x1800c6566  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c656d  jmp     short loc_1800C657D
0x1800c656f  lea     rcx, qword_1801B07E0; this
0x1800c6576  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c657d  cmp     byte ptr [rcx+8], 0
0x1800c6581  jz      short loc_1800C65A4
0x1800c6583  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800c6588  cmp     [rax+7CCh], ebx
0x1800c658e  jz      short loc_1800C65A4
0x1800c6590  mov     r9d, ebx; int
0x1800c6593  mov     r8d, 0A3h; int
0x1800c6599  mov     rdx, r13; char *
0x1800c659c  mov     rcx, rax; this
0x1800c659f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800c65a4  mov     edi, 1
0x1800c65a9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800c65b0  jb      loc_1800C68F2
0x1800c65b6  lea     edx, [rdi+17h]
0x1800c65b9  jmp     loc_1800C644E
0x1800c65be  mov     [rsp+120h+var_E8], 0
0x1800c65c6  lea     r8, [rsp+120h+var_E8]
0x1800c65cb  mov     rcx, [rsi+70h]
0x1800c65cf  mov     rdx, rdi
0x1800c65d2  mov     rax, [rcx]
0x1800c65d5  mov     rax, [rax+58h]
0x1800c65d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c65de  mov     ebx, eax
0x1800c65e0  test    eax, eax
0x1800c65e2  jns     loc_1800C6694
0x1800c65e8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c65ef  test    rcx, rcx
0x1800c65f2  jnz     short loc_1800C6635
0x1800c65f4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800c65fa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c6601  mov     rcx, rax
0x1800c6604  test    rax, rax
0x1800c6607  jz      short loc_1800C6627
0x1800c6609  mov     rax, [rax]
0x1800c660c  mov     edx, 7F0h
0x1800c6611  mov     rax, [rax+8]
0x1800c6615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c661a  test    eax, eax
0x1800c661c  jz      short loc_1800C6627
0x1800c661e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c6625  jmp     short loc_1800C6635
0x1800c6627  lea     rcx, qword_1801B07E0; this
0x1800c662e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c6635  cmp     byte ptr [rcx+8], 0
0x1800c6639  jz      short loc_1800C665C
0x1800c663b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800c6640  cmp     [rax+7CCh], ebx
0x1800c6646  jz      short loc_1800C665C
0x1800c6648  mov     r9d, ebx; int
0x1800c664b  mov     r8d, 0ABh; int
0x1800c6651  mov     rdx, r13; char *
0x1800c6654  mov     rcx, rax; this
0x1800c6657  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800c665c  mov     edi, 1
0x1800c6661  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800c6668  jb      loc_1800C6852
0x1800c666e  lea     edx, [rdi+18h]
0x1800c6671  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c6678  lea     r8, WPP_dc4445c74a623006578798248b483e8b_Traceguids
0x1800c667f  mov     r9, r14
0x1800c6682  mov     [rsp+120h+var_100], ebx
0x1800c6686  mov     rcx, [rcx+10h]
0x1800c668a  call    WPP_SF_qD
0x1800c668f  jmp     loc_1800C6852
0x1800c6694  cmp     [rsp+120h+var_E8], 6
0x1800c6699  jnb     loc_1800C6732
0x1800c669f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c66a6  mov     ebx, 0C00D36F0h
0x1800c66ab  test    rcx, rcx
0x1800c66ae  jnz     short loc_1800C66F1
0x1800c66b0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800c66b6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c66bd  mov     rcx, rax
0x1800c66c0  test    rax, rax
0x1800c66c3  jz      short loc_1800C66E3
0x1800c66c5  mov     rax, [rax]
0x1800c66c8  mov     edx, 7F0h
0x1800c66cd  mov     rax, [rax+8]
0x1800c66d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c66d6  test    eax, eax
0x1800c66d8  jz      short loc_1800C66E3
0x1800c66da  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c66e1  jmp     short loc_1800C66F1
0x1800c66e3  lea     rcx, qword_1801B07E0; this
0x1800c66ea  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c66f1  cmp     byte ptr [rcx+8], 0
0x1800c66f5  jz      short loc_1800C6718
0x1800c66f7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800c66fc  cmp     [rax+7CCh], ebx
0x1800c6702  jz      short loc_1800C6718
0x1800c6704  mov     r9d, ebx; int
0x1800c6707  mov     r8d, 0AEh; int
0x1800c670d  mov     rdx, r13; char *
0x1800c6710  mov     rcx, rax; this
0x1800c6713  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800c6718  mov     edi, 1
0x1800c671d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800c6724  jb      loc_1800C6852
0x1800c672a  lea     edx, [rdi+19h]
0x1800c672d  jmp     loc_1800C6671
0x1800c6732  mov     eax, [rbp+57h+var_D0]
0x1800c6735  lea     rdx, [rsi+88h]
0x1800c673c  xor     r9d, r9d
0x1800c673f  mov     [rbp+57h+var_C4], 80h
0x1800c6746  and     eax, 0FFFFFFF9h
0x1800c6749  mov     [rbp+57h+var_CC], r9
0x1800c674d  xor     r8d, r8d
0x1800c6750  lea     edi, [r9+1]
0x1800c6754  or      eax, edi
0x1800c6756  mov     [rbp+57h+var_D0], eax
0x1800c6759  lea     rax, [rbp+57h+var_B8]
0x1800c675d  mov     [rbp+57h+var_C0], rax
0x1800c6761  test    rdx, rdx
0x1800c6764  jz      short loc_1800C677B
0x1800c6766  lea     r8d, [r9+6]
0x1800c676a  lea     rcx, [rbp+57h+var_D0]
0x1800c676e  call    ?_Append@?$CMFBaseStringT@D@@IEAAJPEBDJ@Z; CMFBaseStringT<char>::_Append(char const *,long)
0x1800c6773  mov     r8d, dword ptr [rbp+57h+var_CC+4]
0x1800c6777  mov     r9d, dword ptr [rbp+57h+var_CC]
0x1800c677b  lea     rcx, [rbp+57h+var_D0]
0x1800c677f  call    ?PContents@?$CMFBaseStringT@D@@QEBAPEBDXZ; CMFBaseStringT<char>::PContents(void)
0x1800c6784  test    r9d, r9d
0x1800c6787  js      short loc_1800C67A4
0x1800c6789  cmp     r8d, 6
0x1800c678d  jnz     short loc_1800C67A4
0x1800c678f  test    rax, rax
0x1800c6792  jz      short loc_1800C67A4
0x1800c6794  mov     rcx, rax; char *
0x1800c6797  call    ?wms_ncmp@@YA_NPEBD0J@Z; wms_ncmp(char const *,char const *,long)
0x1800c679c  test    al, al
0x1800c679e  jnz     loc_1800C6849
0x1800c67a4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c67ab  mov     ebx, 0C00D36BEh
0x1800c67b0  test    rcx, rcx
0x1800c67b3  jnz     short loc_1800C67F6
0x1800c67b5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800c67bb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c67c2  mov     rcx, rax
0x1800c67c5  test    rax, rax
0x1800c67c8  jz      short loc_1800C67E8
0x1800c67ca  mov     rax, [rax]
0x1800c67cd  mov     edx, 7F0h
0x1800c67d2  mov     rax, [rax+8]
0x1800c67d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c67db  test    eax, eax
0x1800c67dd  jz      short loc_1800C67E8
0x1800c67df  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c67e6  jmp     short loc_1800C67F6
0x1800c67e8  lea     rcx, qword_1801B07E0; this
0x1800c67ef  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c67f6  cmp     byte ptr [rcx+8], 0
0x1800c67fa  jz      short loc_1800C681D
0x1800c67fc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800c6801  cmp     [rax+7CCh], ebx
0x1800c6807  jz      short loc_1800C681D
0x1800c6809  mov     r9d, ebx; int
0x1800c680c  mov     r8d, 0B7h; int
0x1800c6812  mov     rdx, r13; char *
0x1800c6815  mov     rcx, rax; this
0x1800c6818  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800c681d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800c6824  jb      short loc_1800C6849
0x1800c6826  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c682d  lea     r8, WPP_dc4445c74a623006578798248b483e8b_Traceguids
0x1800c6834  mov     edx, 1Bh
0x1800c6839  mov     [rsp+120h+var_100], ebx
0x1800c683d  mov     r9, r14
0x1800c6840  mov     rcx, [rcx+10h]
0x1800c6844  call    WPP_SF_qD
0x1800c6849  lea     rcx, [rbp+57h+var_D0]
0x1800c684d  call    ??1?$CMFBaseStringT@D@@QEAA@XZ; CMFBaseStringT<char>::~CMFBaseStringT<char>(void)
0x1800c6852  mov     rcx, [rsi+28h]
0x1800c6856  mov     [rsi+30h], ebx
0x1800c6859  test    rcx, rcx
0x1800c685c  jz      short loc_1800C68A1
0x1800c685e  mov     [rsp+120h+var_D8], 0
  ... truncated ...
```
