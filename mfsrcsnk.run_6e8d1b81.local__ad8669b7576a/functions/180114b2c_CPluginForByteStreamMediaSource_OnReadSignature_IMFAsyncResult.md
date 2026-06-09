# CPluginForByteStreamMediaSource::OnReadSignature(IMFAsyncResult *)

- ea: `0x180114b2c`
- end: `0x180115041`
- name: `?OnReadSignature@CPluginForByteStreamMediaSource@@IEAAJPEAUIMFAsyncResult@@@Z`
- size: `1301`
- prototype: `__int64 __fastcall(CPluginForByteStreamMediaSource *__hidden this, struct IMFAsyncResult *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180114af0`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180034d10`
- `0x180073b14`
- `0x180114b2c`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180114fee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180114fee`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180114fe0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180114fe0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18011501a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18011501a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180115010`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180115010`
- `MFPlat!MFPutWorkItemEx2` at `0x180114fc7`
- `MFPlat!MFPutWorkItemEx2` at `0x180114fc7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180114b7d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180114c46`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180114ce6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180114da1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180114e3c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180114ef2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180114b7d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180114c46`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180114ce6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180114da1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180114e3c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180114ef2`

## string_xrefs

- `0x180114b3f`: `CPluginForByteStreamMediaSource::OnReadSignature`

## pseudocode

```c
__int64 __fastcall CPluginForByteStreamMediaSource::OnReadSignature(
        CPluginForByteStreamMediaSource *this,
        struct IMFAsyncResult *a2)
{
  __int64 v4; // rdx
  wchar_t *v5; // rcx
  int v6; // ebx
  CallStackTracing *v7; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v9; // rdx
  __int64 v10; // rdx
  wchar_t *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  IMFAsyncResult *v14; // rsi
  wchar_t *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rdx
  DWORD v19; // edi
  wchar_t *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  __int64 v23; // rdx
  wchar_t *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  __int64 v27; // r8
  __int64 v28; // rdx
  wchar_t *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  struct IMFAsyncResultVtbl *lpVtbl; // rcx
  HANDLE EventW; // rax
  signed int LastError; // eax
  bool v35; // sf
  int v37; // [rsp+70h] [rbp+38h] BYREF
  unsigned int v38; // [rsp+78h] [rbp+40h] BYREF
  int v39; // [rsp+80h] [rbp+48h] BYREF
  IMFAsyncResult *pResult; // [rsp+88h] [rbp+50h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v37,
    "CPluginForByteStreamMediaSource::OnReadSignature",
    105);
  pResult = 0;
  if ( !a2 )
  {
    v5 = (wchar_t *)CallStackTracing::s_wpInstance;
    v6 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
      CallStackTracing::s_wpInstance = v7;
      if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
      {
        v5 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v5 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v5 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v5);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467261 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CPluginForByteStreamMediaSource::OnReadSignature",
          114,
          -2147467261);
    }
    if ( g_wppLevels )
    {
      v9 = 19;
LABEL_12:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, WPP_7480abd032773c8d3cc81d2ec55f9c51_Traceguids, this, v6);
      goto LABEL_85;
    }
    goto LABEL_85;
  }
  v6 = ((__int64 (__fastcall *)(struct IMFAsyncResult *, IMFAsyncResult **))a2->lpVtbl->GetState)(a2, &pResult);
  if ( v6 >= 0 )
  {
    v14 = pResult;
    if ( !pResult )
    {
      v15 = (wchar_t *)CallStackTracing::s_wpInstance;
      v6 = -2147024809;
      if ( !CallStackTracing::s_wpInstance )
      {
        v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
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
        if ( *((_DWORD *)v17 + 499) != -2147024809 )
          CallStackContext::TraceFailure(v17, "CPluginForByteStreamMediaSource::OnReadSignature", 122, -2147024809);
      }
      if ( g_wppLevels )
      {
        v9 = 21;
        goto LABEL_12;
      }
      goto LABEL_85;
    }
    v38 = 0;
    v6 = (*((__int64 (__fastcall **)(struct IMFAsyncResultVtbl *, struct IMFAsyncResult *, unsigned int *))pResult[14].lpVtbl->QueryInterface
          + 11))(
           pResult[14].lpVtbl,
           a2,
           &v38);
    v19 = 1;
    if ( v6 >= 0 )
    {
      if ( v38 )
      {
        v27 = *((unsigned int *)this + 12);
        if ( v38 < (unsigned int)v27 )
          v27 = v38;
        v6 = (*(__int64 (__fastcall **)(CPluginForByteStreamMediaSource *, struct IMFAsyncResultVtbl *, __int64))(*(_QWORD *)this + 96LL))(
               this,
               v14[17].lpVtbl,
               v27);
        if ( v6 < 0 )
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
            if ( *((_DWORD *)v31 + 499) != v6 )
              CallStackContext::TraceFailure(v31, "CPluginForByteStreamMediaSource::OnReadSignature", 137, v6);
          }
          if ( g_wppLevels )
          {
            v23 = 24;
            goto LABEL_70;
          }
        }
      }
      else
      {
        v24 = (wchar_t *)CallStackTracing::s_wpInstance;
        v6 = -1072875792;
        if ( !CallStackTracing::s_wpInstance )
        {
          v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18);
          CallStackTracing::s_wpInstance = v25;
          if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
          {
            v24 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v24 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v24 + 8) )
        {
          v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
          if ( *((_DWORD *)v26 + 499) != -1072875792 )
            CallStackContext::TraceFailure(v26, "CPluginForByteStreamMediaSource::OnReadSignature", 133, -1072875792);
        }
        if ( g_wppLevels )
        {
          v23 = 23;
          goto LABEL_70;
        }
      }
    }
    else
    {
      v20 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18);
        CallStackTracing::s_wpInstance = v21;
        if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
        {
          v20 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v20 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v20 + 8) )
      {
        v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
        if ( *((_DWORD *)v22 + 499) != v6 )
          CallStackContext::TraceFailure(v22, "CPluginForByteStreamMediaSource::OnReadSignature", 129, v6);
      }
      if ( g_wppLevels )
      {
        v23 = 22;
LABEL_70:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v23, WPP_7480abd032773c8d3cc81d2ec55f9c51_Traceguids, this, v6);
      }
    }
    lpVtbl = v14[5].lpVtbl;
    LODWORD(v14[6].lpVtbl) = v6;
    if ( lpVtbl )
    {
      v39 = 0;
      v37 = 0;
      if ( (*((int (__fastcall **)(struct IMFAsyncResultVtbl *, int *, int *))lpVtbl->QueryInterface + 3))(
             lpVtbl,
             &v39,
             &v37) >= 0 )
        v19 = v37;
      else
        v37 = 1;
      MFPutWorkItemEx2(v19, 0, v14);
      goto LABEL_85;
    }
    if ( !v14[7].lpVtbl )
    {
      EventW = CreateEventW(0, 1, 0, 0);
      if ( EventW )
      {
        if ( _InterlockedCompareExchange64((volatile signed __int64 *)&v14[7], (signed __int64)EventW, 0) )
          CloseHandle(EventW);
      }
      else
      {
        LastError = GetLastError();
        v35 = LastError < 0;
        if ( LastError > 0 )
          v35 = 1;
        if ( v35 )
          goto LABEL_85;
      }
    }
    SetEvent(v14[7].lpVtbl);
    goto LABEL_85;
  }
  v11 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
    CallStackTracing::s_wpInstance = v12;
    if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
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
    v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
    if ( *((_DWORD *)v13 + 499) != v6 )
      CallStackContext::TraceFailure(v13, "CPluginForByteStreamMediaSource::OnReadSignature", 119, v6);
  }
  if ( g_wppLevels )
  {
    v9 = 20;
    goto LABEL_12;
  }
LABEL_85:
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&pResult);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v37);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180114b2c  push    rbp
0x180114b2e  push    rbx
0x180114b2f  push    rsi
0x180114b30  push    rdi
0x180114b31  push    r12
0x180114b33  push    r14
0x180114b35  mov     rbp, rsp
0x180114b38  sub     rsp, 38h
0x180114b3c  mov     rdi, rdx
0x180114b3f  lea     r12, aCpluginforbyte_4; "CPluginForByteStreamMediaSource::OnRead"...
0x180114b46  mov     r14, rcx
0x180114b49  mov     rdx, r12; char *
0x180114b4c  mov     r8d, 69h ; 'i'; int
0x180114b52  lea     rcx, [rbp+arg_0]; this
0x180114b56  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180114b5b  mov     [rbp+pResult], 0
0x180114b63  test    rdi, rdi
0x180114b66  jnz     loc_180114C1D
0x180114b6c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180114b73  mov     ebx, 80004003h
0x180114b78  test    rcx, rcx
0x180114b7b  jnz     short loc_180114BBE
0x180114b7d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180114b83  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180114b8a  mov     rcx, rax
0x180114b8d  test    rax, rax
0x180114b90  jz      short loc_180114BB0
0x180114b92  mov     rax, [rax]
0x180114b95  mov     edx, 7F0h
0x180114b9a  mov     rax, [rax+8]
0x180114b9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114ba3  test    eax, eax
0x180114ba5  jz      short loc_180114BB0
0x180114ba7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180114bae  jmp     short loc_180114BBE
0x180114bb0  lea     rcx, qword_1801B07E0; this
0x180114bb7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180114bbe  cmp     byte ptr [rcx+8], 0
0x180114bc2  jz      short loc_180114BE5
0x180114bc4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180114bc9  cmp     [rax+7CCh], ebx
0x180114bcf  jz      short loc_180114BE5
0x180114bd1  mov     r9d, ebx; int
0x180114bd4  mov     r8d, 72h ; 'r'; int
0x180114bda  mov     rdx, r12; char *
0x180114bdd  mov     rcx, rax; this
0x180114be0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180114be5  mov     edi, 1
0x180114bea  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180114bf1  jb      loc_180115020
0x180114bf7  lea     edx, [rdi+12h]
0x180114bfa  mov     rcx, cs:WPP_GLOBAL_Control
0x180114c01  lea     r8, WPP_7480abd032773c8d3cc81d2ec55f9c51_Traceguids
0x180114c08  mov     r9, r14
0x180114c0b  mov     [rsp+38h+var_18], ebx
0x180114c0f  mov     rcx, [rcx+10h]
0x180114c13  call    WPP_SF_qD
0x180114c18  jmp     loc_180115020
0x180114c1d  mov     rax, [rdi]
0x180114c20  lea     rdx, [rbp+pResult]
0x180114c24  mov     rcx, rdi
0x180114c27  mov     rax, [rax+18h]
0x180114c2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114c30  mov     ebx, eax
0x180114c32  test    eax, eax
0x180114c34  jns     loc_180114CC8
0x180114c3a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180114c41  test    rcx, rcx
0x180114c44  jnz     short loc_180114C87
0x180114c46  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180114c4c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180114c53  mov     rcx, rax
0x180114c56  test    rax, rax
0x180114c59  jz      short loc_180114C79
0x180114c5b  mov     rax, [rax]
0x180114c5e  mov     edx, 7F0h
0x180114c63  mov     rax, [rax+8]
0x180114c67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114c6c  test    eax, eax
0x180114c6e  jz      short loc_180114C79
0x180114c70  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180114c77  jmp     short loc_180114C87
0x180114c79  lea     rcx, qword_1801B07E0; this
0x180114c80  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180114c87  cmp     byte ptr [rcx+8], 0
0x180114c8b  jz      short loc_180114CAE
0x180114c8d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180114c92  cmp     [rax+7CCh], ebx
0x180114c98  jz      short loc_180114CAE
0x180114c9a  mov     r9d, ebx; int
0x180114c9d  mov     r8d, 77h ; 'w'; int
0x180114ca3  mov     rdx, r12; char *
0x180114ca6  mov     rcx, rax; this
0x180114ca9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180114cae  mov     edi, 1
0x180114cb3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180114cba  jb      loc_180115020
0x180114cc0  lea     edx, [rdi+13h]
0x180114cc3  jmp     loc_180114BFA
0x180114cc8  mov     rsi, [rbp+pResult]
0x180114ccc  test    rsi, rsi
0x180114ccf  jnz     loc_180114D68
0x180114cd5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180114cdc  mov     ebx, 80070057h
0x180114ce1  test    rcx, rcx
0x180114ce4  jnz     short loc_180114D27
0x180114ce6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180114cec  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180114cf3  mov     rcx, rax
0x180114cf6  test    rax, rax
0x180114cf9  jz      short loc_180114D19
0x180114cfb  mov     rax, [rax]
0x180114cfe  mov     edx, 7F0h
0x180114d03  mov     rax, [rax+8]
0x180114d07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114d0c  test    eax, eax
0x180114d0e  jz      short loc_180114D19
0x180114d10  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180114d17  jmp     short loc_180114D27
0x180114d19  lea     rcx, qword_1801B07E0; this
0x180114d20  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180114d27  cmp     byte ptr [rcx+8], 0
0x180114d2b  jz      short loc_180114D4E
0x180114d2d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180114d32  cmp     [rax+7CCh], ebx
0x180114d38  jz      short loc_180114D4E
0x180114d3a  mov     r9d, ebx; int
0x180114d3d  mov     r8d, 7Ah ; 'z'; int
0x180114d43  mov     rdx, r12; char *
0x180114d46  mov     rcx, rax; this
0x180114d49  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180114d4e  mov     edi, 1
0x180114d53  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180114d5a  jb      loc_180115020
0x180114d60  lea     edx, [rdi+14h]
0x180114d63  jmp     loc_180114BFA
0x180114d68  mov     [rbp+arg_8], 0
0x180114d6f  lea     r8, [rbp+arg_8]
0x180114d73  mov     rcx, [rsi+70h]
0x180114d77  mov     rdx, rdi
0x180114d7a  mov     rax, [rcx]
0x180114d7d  mov     rax, [rax+58h]
0x180114d81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114d86  mov     ebx, eax
0x180114d88  mov     edi, 1
0x180114d8d  test    eax, eax
0x180114d8f  jns     loc_180114E20
0x180114d95  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180114d9c  test    rcx, rcx
0x180114d9f  jnz     short loc_180114DE2
0x180114da1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180114da7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180114dae  mov     rcx, rax
0x180114db1  test    rax, rax
0x180114db4  jz      short loc_180114DD4
0x180114db6  mov     rax, [rax]
0x180114db9  mov     edx, 7F0h
0x180114dbe  mov     rax, [rax+8]
0x180114dc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114dc7  test    eax, eax
0x180114dc9  jz      short loc_180114DD4
0x180114dcb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180114dd2  jmp     short loc_180114DE2
0x180114dd4  lea     rcx, qword_1801B07E0; this
0x180114ddb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180114de2  cmp     byte ptr [rcx+8], 0
0x180114de6  jz      short loc_180114E09
0x180114de8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180114ded  cmp     [rax+7CCh], ebx
0x180114df3  jz      short loc_180114E09
0x180114df5  mov     r9d, ebx; int
0x180114df8  mov     r8d, 81h; int
0x180114dfe  mov     rdx, r12; char *
0x180114e01  mov     rcx, rax; this
0x180114e04  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180114e09  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180114e10  jb      loc_180114F86
0x180114e16  mov     edx, 16h
0x180114e1b  jmp     loc_180114F68
0x180114e20  mov     ecx, [rbp+arg_8]
0x180114e23  test    ecx, ecx
0x180114e25  jnz     loc_180114EBB
0x180114e2b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180114e32  mov     ebx, 0C00D36F0h
0x180114e37  test    rcx, rcx
0x180114e3a  jnz     short loc_180114E7D
0x180114e3c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180114e42  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180114e49  mov     rcx, rax
0x180114e4c  test    rax, rax
0x180114e4f  jz      short loc_180114E6F
0x180114e51  mov     rax, [rax]
0x180114e54  mov     edx, 7F0h
0x180114e59  mov     rax, [rax+8]
0x180114e5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114e62  test    eax, eax
0x180114e64  jz      short loc_180114E6F
0x180114e66  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180114e6d  jmp     short loc_180114E7D
0x180114e6f  lea     rcx, qword_1801B07E0; this
0x180114e76  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180114e7d  cmp     byte ptr [rcx+8], 0
0x180114e81  jz      short loc_180114EA4
0x180114e83  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180114e88  cmp     [rax+7CCh], ebx
0x180114e8e  jz      short loc_180114EA4
0x180114e90  mov     r9d, ebx; int
0x180114e93  mov     r8d, 85h; int
0x180114e99  mov     rdx, r12; char *
0x180114e9c  mov     rcx, rax; this
0x180114e9f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180114ea4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180114eab  jb      loc_180114F86
0x180114eb1  mov     edx, 17h
0x180114eb6  jmp     loc_180114F68
0x180114ebb  mov     r8d, [r14+30h]
0x180114ebf  cmp     ecx, r8d
0x180114ec2  mov     rax, [r14]
0x180114ec5  mov     rdx, [rsi+88h]
0x180114ecc  cmovb   r8d, ecx
0x180114ed0  mov     rcx, r14
0x180114ed3  mov     rax, [rax+60h]
0x180114ed7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114edc  mov     ebx, eax
0x180114ede  test    eax, eax
0x180114ee0  jns     loc_180114F86
0x180114ee6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180114eed  test    rcx, rcx
0x180114ef0  jnz     short loc_180114F33
0x180114ef2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180114ef8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180114eff  mov     rcx, rax
0x180114f02  test    rax, rax
0x180114f05  jz      short loc_180114F25
0x180114f07  mov     rax, [rax]
0x180114f0a  mov     edx, 7F0h
0x180114f0f  mov     rax, [rax+8]
0x180114f13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114f18  test    eax, eax
0x180114f1a  jz      short loc_180114F25
0x180114f1c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180114f23  jmp     short loc_180114F33
0x180114f25  lea     rcx, qword_1801B07E0; this
0x180114f2c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180114f33  cmp     byte ptr [rcx+8], 0
0x180114f37  jz      short loc_180114F5A
0x180114f39  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180114f3e  cmp     [rax+7CCh], ebx
0x180114f44  jz      short loc_180114F5A
0x180114f46  mov     r9d, ebx; int
0x180114f49  mov     r8d, 89h; int
0x180114f4f  mov     rdx, r12; char *
0x180114f52  mov     rcx, rax; this
0x180114f55  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180114f5a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180114f61  jb      short loc_180114F86
0x180114f63  mov     edx, 18h
0x180114f68  mov     rcx, cs:WPP_GLOBAL_Control
0x180114f6f  lea     r8, WPP_7480abd032773c8d3cc81d2ec55f9c51_Traceguids
0x180114f76  mov     r9, r14
0x180114f79  mov     [rsp+38h+var_18], ebx
0x180114f7d  mov     rcx, [rcx+10h]
0x180114f81  call    WPP_SF_qD
0x180114f86  mov     rcx, [rsi+28h]
0x180114f8a  mov     [rsi+30h], ebx
0x180114f8d  test    rcx, rcx
0x180114f90  jz      short loc_180114FCF
0x180114f92  mov     [rbp+arg_10], 0
0x180114f99  lea     r8, [rbp+arg_0]
0x180114f9d  mov     [rbp+arg_0], 0
0x180114fa4  lea     rdx, [rbp+arg_10]
0x180114fa8  mov     rax, [rcx]
0x180114fab  mov     rax, [rax+18h]
0x180114faf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114fb4  test    eax, eax
0x180114fb6  jns     short loc_180114FBD
0x180114fb8  mov     [rbp+arg_0], edi
0x180114fbb  jmp     short loc_180114FC0
0x180114fbd  mov     edi, [rbp+arg_0]
0x180114fc0  mov     r8, rsi; pResult
0x180114fc3  xor     edx, edx; Priority
0x180114fc5  mov     ecx, edi; dwQueue
0x180114fc7  call    cs:__imp_MFPutWorkItemEx2
0x180114fcd  jmp     short loc_180115020
0x180114fcf  cmp     qword ptr [rsi+38h], 0
0x180114fd4  jnz     short loc_180115016
0x180114fd6  xor     r9d, r9d; lpName
0x180114fd9  xor     r8d, r8d; bInitialState
0x180114fdc  mov     edx, edi; bManualReset
0x180114fde  xor     ecx, ecx; lpEventAttributes
0x180114fe0  call    cs:__imp_CreateEventW
0x180114fe6  mov     rcx, rax; hObject
0x180114fe9  test    rax, rax
0x180114fec  jnz     short loc_180115006
0x180114fee  call    cs:__imp_GetLastError
0x180114ff4  test    eax, eax
0x180114ff6  jle     short loc_180115002
0x180114ff8  movzx   eax, ax
0x180114ffb  or      eax, 80070000h
0x180115000  test    eax, eax
  ... truncated ...
```
