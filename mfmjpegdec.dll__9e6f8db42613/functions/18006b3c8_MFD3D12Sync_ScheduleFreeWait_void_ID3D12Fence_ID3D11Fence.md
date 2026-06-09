# MFD3D12Sync::ScheduleFreeWait(void * &,ID3D12Fence *,ID3D11Fence *)

- ea: `0x18006b3c8`
- end: `0x18006b867`
- name: `?ScheduleFreeWait@MFD3D12Sync@@IEAAJAEAPEAXPEAUID3D12Fence@@PEAUID3D11Fence@@@Z`
- size: `1183`
- prototype: `int(MFD3D12Sync *__hidden this, void **, struct ID3D12Fence *, struct ID3D11Fence *)`
- caller_count: `4`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180068700`
- `0x180069010`
- `0x18006a440`
- `0x18006bee0`

## callees

- `0x18002312c`
- `0x180023df0`
- `0x180045060`
- `0x18004a0f8`
- `0x18004a11c`
- `0x180056638`
- `0x180067380`
- `0x1800673ac`
- `0x18006b3c8`
- `0x18006dc78`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006b4dd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006b5c8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006b6a5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006b787`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006b4dd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006b5c8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006b6a5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006b787`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b488`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b4a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b575`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b590`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b652`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b66d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b732`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b74e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b488`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b4a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b575`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b590`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b652`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b66d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b732`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b74e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18006b494`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18006b580`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18006b65d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18006b73e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18006b494`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18006b580`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18006b65d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18006b73e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006b7e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006b7e5`
- `RTWorkQ!RtwqCreateAsyncResult` at `0x18006b53a`
- `RTWorkQ!RtwqCreateAsyncResult` at `0x18006b53a`
- `RTWorkQ!RtwqPutWaitingWorkItem` at `0x18006b617`
- `RTWorkQ!RtwqPutWaitingWorkItem` at `0x18006b617`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MFD3D12Sync::ScheduleFreeWait(
        IRtwqAsyncCallback *this,
        void **a2,
        IUnknown *a3,
        struct ID3D11Fence *a4)
{
  _QWORD *v8; // r14
  unsigned int v9; // edx
  HRESULT v10; // ebx
  CallStackTracing *v11; // rdi
  CallStackContext *v12; // rbp
  DWORD LastError; // r12d
  CallStackContext *Value; // rax
  CallStackTracing *v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rdx
  CallStackTracing *v18; // rdi
  CallStackContext *v19; // rsi
  DWORD v20; // ebp
  CallStackContext *v21; // rax
  CallStackTracing *v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rdx
  CallStackTracing *v25; // rdi
  CallStackContext *v26; // rsi
  DWORD v27; // ebp
  CallStackContext *v28; // rax
  CallStackTracing *v29; // rcx
  __int64 v30; // rax
  CallStackTracing *v31; // rdi
  CallStackContext *v32; // rbp
  DWORD v33; // r12d
  CallStackContext *v34; // rax
  CallStackTracing *v35; // rcx
  __int64 v36; // rax
  IUnknown **v37; // r9
  __int64 v38; // rdx
  char v40[8]; // [rsp+30h] [rbp-68h] BYREF
  IRtwqAsyncResult *asyncResult; // [rsp+38h] [rbp-60h] BYREF
  IUnknown **v42; // [rsp+40h] [rbp-58h] BYREF

  asyncResult = 0;
  v8 = operator new(0x20u);
  v42 = (IUnknown **)v8;
  if ( v8 )
  {
    *v8 = *a2;
    v8[1] = a3;
    Microsoft::WRL::ComPtr<ID3D12Resource>::InternalAddRef(v8 + 1);
    v8[2] = a4;
    if ( a4 )
      ((void (__fastcall *)(struct ID3D11Fence *))a4->lpVtbl->AddRef)(a4);
  }
  else
  {
    v8 = 0;
  }
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v40, "MFD3D12Sync::ScheduleFreeWait", 206);
  if ( !v8 )
  {
    v10 = -2147024882;
    v11 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v11 = (CallStackTracing *)&qword_18009CF60;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
    }
    if ( *((_BYTE *)v11 + 8) )
    {
      v12 = (CallStackTracing *)((char *)v11 + 208);
      LastError = GetLastError();
      Value = (CallStackContext *)TlsGetValue(*((_DWORD *)v11 + 3));
      if ( Value )
      {
        v12 = Value;
      }
      else if ( !GetLastError() )
      {
        v15 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v15 = (CallStackTracing *)&qword_18009CF60;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
        }
        v16 = (**(__int64 (__fastcall ***)(CallStackTracing *))v15)(v15);
        if ( v16 )
          v12 = (CallStackContext *)v16;
      }
      SetLastError(LastError);
      if ( *((_DWORD *)v12 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v12, "MFD3D12Sync::ScheduleFreeWait", 206, -2147024882);
    }
    if ( !g_wppLevels )
      goto LABEL_68;
    v17 = 44;
    goto LABEL_67;
  }
  *a2 = 0;
  Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&asyncResult);
  v10 = RtwqCreateAsyncResult(a3, this + 3, 0, &asyncResult);
  if ( v10 < 0 )
  {
    v18 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v18 = (CallStackTracing *)&qword_18009CF60;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
    }
    if ( *((_BYTE *)v18 + 8) )
    {
      v19 = (CallStackTracing *)((char *)v18 + 208);
      v20 = GetLastError();
      v21 = (CallStackContext *)TlsGetValue(*((_DWORD *)v18 + 3));
      if ( v21 )
      {
        v19 = v21;
      }
      else if ( !GetLastError() )
      {
        v22 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v22 = (CallStackTracing *)&qword_18009CF60;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
        }
        v23 = (**(__int64 (__fastcall ***)(CallStackTracing *))v22)(v22);
        if ( v23 )
          v19 = (CallStackContext *)v23;
      }
      SetLastError(v20);
      if ( *((_DWORD *)v19 + 499) != v10 )
        CallStackContext::TraceFailure(v19, "MFD3D12Sync::ScheduleFreeWait", 217, v10);
    }
    if ( !g_wppLevels )
      goto LABEL_68;
    v24 = 47;
    goto LABEL_36;
  }
  v10 = RtwqPutWaitingWorkItem((HANDLE)*v8, 0, asyncResult, v8 + 3);
  if ( v10 < 0 )
  {
    v25 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v25 = (CallStackTracing *)&qword_18009CF60;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
    }
    if ( *((_BYTE *)v25 + 8) )
    {
      v26 = (CallStackTracing *)((char *)v25 + 208);
      v27 = GetLastError();
      v28 = (CallStackContext *)TlsGetValue(*((_DWORD *)v25 + 3));
      if ( v28 )
      {
        v26 = v28;
      }
      else if ( !GetLastError() )
      {
        v29 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v29 = (CallStackTracing *)&qword_18009CF60;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
        }
        v30 = (**(__int64 (__fastcall ***)(CallStackTracing *))v29)(v29);
        if ( v30 )
          v26 = (CallStackContext *)v30;
      }
      SetLastError(v27);
      if ( *((_DWORD *)v26 + 499) != v10 )
        CallStackContext::TraceFailure(v26, "MFD3D12Sync::ScheduleFreeWait", 218, v10);
    }
    if ( !g_wppLevels )
      goto LABEL_68;
    v24 = 48;
LABEL_36:
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v24, &WPP_18b1d8a13eb8310f1056d7c08509d55f_Traceguids, this, v10);
    goto LABEL_68;
  }
  v42 = 0;
  if ( (int)CTNodePool<CTBucketHash<ID3D12Fence *,MFD3D12Sync::QueuedFreeWait *>::NODEBLOCK,CTBucketHash<ID3D12Fence *,MFD3D12Sync::QueuedFreeWait *>::NODE,8>::AcquireNode(
              &this[8].GetParameters,
              &v42) >= 0 )
  {
    v37 = v42;
    *v42 = a3;
    v37[1] = (IUnknown *)v8;
    v38 = (unsigned int)a3 % (unsigned __int64)((__int64)this[7].Invoke & 0x7FFFFFFF);
    v37[2] = (IUnknown *)*((_QWORD *)this[7].GetParameters + v38);
    *((_QWORD *)this[7].GetParameters + (unsigned int)v38) = v37;
    ++HIDWORD(this[7].Invoke);
    v10 = 0;
    goto LABEL_73;
  }
  v10 = -2147024882;
  v31 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v31 = (CallStackTracing *)&qword_18009CF60;
    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
  }
  if ( *((_BYTE *)v31 + 8) )
  {
    v32 = (CallStackTracing *)((char *)v31 + 208);
    v33 = GetLastError();
    v34 = (CallStackContext *)TlsGetValue(*((_DWORD *)v31 + 3));
    if ( v34 )
    {
      v32 = v34;
    }
    else if ( !GetLastError() )
    {
      v35 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v35 = (CallStackTracing *)&qword_18009CF60;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
      }
      v36 = (**(__int64 (__fastcall ***)(CallStackTracing *))v35)(v35);
      if ( v36 )
        v32 = (CallStackContext *)v36;
    }
    SetLastError(v33);
    if ( *((_DWORD *)v32 + 499) != -2147024882 )
      CallStackContext::TraceFailure(v32, "MFD3D12Sync::ScheduleFreeWait", 221, -2147024882);
  }
  if ( g_wppLevels )
  {
    v17 = 49;
LABEL_67:
    WPP_SF_qd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v17,
      &WPP_18b1d8a13eb8310f1056d7c08509d55f_Traceguids,
      this,
      -2147024882);
  }
LABEL_68:
  if ( *a2 )
  {
    CloseHandle(*a2);
    *a2 = 0;
  }
  if ( v8 )
    MFD3D12Sync::QueuedFreeWait::`scalar deleting destructor'((MFD3D12Sync::QueuedFreeWait *)v8, v9);
LABEL_73:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v40);
  Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&asyncResult);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18006b3c8  push    rbx
0x18006b3ca  push    rbp
0x18006b3cb  push    rsi
0x18006b3cc  push    rdi
0x18006b3cd  push    r12
0x18006b3cf  push    r13
0x18006b3d1  push    r14
0x18006b3d3  push    r15
0x18006b3d5  sub     rsp, 58h
0x18006b3d9  mov     rbx, r9
0x18006b3dc  mov     rdi, r8
0x18006b3df  mov     r13, rdx
0x18006b3e2  mov     r15, rcx
0x18006b3e5  xor     r12d, r12d
0x18006b3e8  mov     [rsp+98h+asyncResult], r12
0x18006b3ed  lea     ecx, [r12+20h]; Size
0x18006b3f2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006b3f7  mov     r14, rax
0x18006b3fa  mov     [rsp+98h+var_58], rax
0x18006b3ff  test    rax, rax
0x18006b402  jz      short loc_18006B432
0x18006b404  mov     rax, [r13+0]
0x18006b408  mov     [r14], rax
0x18006b40b  lea     rcx, [r14+8]
0x18006b40f  mov     [rcx], rdi
0x18006b412  call    ?InternalAddRef@?$ComPtr@UID3D12Resource@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<ID3D12Resource>::InternalAddRef(void)
0x18006b417  mov     [r14+10h], rbx
0x18006b41b  test    rbx, rbx
0x18006b41e  jz      short loc_18006B430
0x18006b420  mov     rax, [rbx]
0x18006b423  mov     rcx, rbx
0x18006b426  mov     rax, [rax+8]
0x18006b42a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b42f  nop
0x18006b430  jmp     short loc_18006B435
0x18006b432  mov     r14, r12
0x18006b435  mov     r8d, 0CEh; int
0x18006b43b  lea     rdx, aMfd3d12syncSch; "MFD3D12Sync::ScheduleFreeWait"
0x18006b442  lea     rcx, [rsp+98h+var_68]; this
0x18006b447  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18006b44c  nop
0x18006b44d  test    r14, r14
0x18006b450  jnz     loc_18006B51D
0x18006b456  mov     esi, 8007000Eh
0x18006b45b  mov     ebx, esi
0x18006b45d  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006b464  test    rdi, rdi
0x18006b467  jnz     short loc_18006B477
0x18006b469  lea     rdi, qword_18009CF60
0x18006b470  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x18006b477  cmp     [rdi+8], r12b
0x18006b47b  jz      loc_18006B506
0x18006b481  lea     rbp, [rdi+0D0h]
0x18006b488  call    cs:__imp_GetLastError
0x18006b48e  mov     r12d, eax
0x18006b491  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18006b494  call    cs:__imp_TlsGetValue
0x18006b49a  test    rax, rax
0x18006b49d  jz      short loc_18006B4A4
0x18006b49f  mov     rbp, rax
0x18006b4a2  jmp     short loc_18006B4DA
0x18006b4a4  call    cs:__imp_GetLastError
0x18006b4aa  test    eax, eax
0x18006b4ac  jnz     short loc_18006B4DA
0x18006b4ae  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006b4b5  test    rcx, rcx
0x18006b4b8  jnz     short loc_18006B4C8
0x18006b4ba  lea     rcx, qword_18009CF60
0x18006b4c1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006b4c8  mov     rax, [rcx]
0x18006b4cb  mov     rax, [rax]
0x18006b4ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b4d3  test    rax, rax
0x18006b4d6  cmovnz  rbp, rax
0x18006b4da  mov     ecx, r12d; dwErrCode
0x18006b4dd  call    cs:__imp_SetLastError
0x18006b4e3  xor     r12d, r12d
0x18006b4e6  cmp     [rbp+7CCh], esi
0x18006b4ec  jz      short loc_18006B506
0x18006b4ee  mov     r9d, esi; int
0x18006b4f1  mov     r8d, 0CEh; int
0x18006b4f7  lea     rdx, aMfd3d12syncSch; "MFD3D12Sync::ScheduleFreeWait"
0x18006b4fe  mov     rcx, rbp; this
0x18006b501  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006b506  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006b50d  jb      loc_18006B7DC
0x18006b513  mov     edx, 2Ch ; ','
0x18006b518  jmp     loc_18006B7BE
0x18006b51d  mov     [r13+0], r12
0x18006b521  lea     rcx, [rsp+98h+asyncResult]
0x18006b526  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x18006b52b  lea     rdx, [r15+48h]; callback
0x18006b52f  lea     r9, [rsp+98h+asyncResult]; asyncResult
0x18006b534  xor     r8d, r8d; appState
0x18006b537  mov     rcx, rdi; appObject
0x18006b53a  call    cs:__imp_RtwqCreateAsyncResult
0x18006b540  mov     ebx, eax
0x18006b542  test    eax, eax
0x18006b544  jns     loc_18006B609
0x18006b54a  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006b551  test    rdi, rdi
0x18006b554  jnz     short loc_18006B564
0x18006b556  lea     rdi, qword_18009CF60
0x18006b55d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x18006b564  cmp     [rdi+8], r12b
0x18006b568  jz      loc_18006B5EE
0x18006b56e  lea     rsi, [rdi+0D0h]
0x18006b575  call    cs:__imp_GetLastError
0x18006b57b  mov     ebp, eax
0x18006b57d  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18006b580  call    cs:__imp_TlsGetValue
0x18006b586  test    rax, rax
0x18006b589  jz      short loc_18006B590
0x18006b58b  mov     rsi, rax
0x18006b58e  jmp     short loc_18006B5C6
0x18006b590  call    cs:__imp_GetLastError
0x18006b596  test    eax, eax
0x18006b598  jnz     short loc_18006B5C6
0x18006b59a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006b5a1  test    rcx, rcx
0x18006b5a4  jnz     short loc_18006B5B4
0x18006b5a6  lea     rcx, qword_18009CF60
0x18006b5ad  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006b5b4  mov     rax, [rcx]
0x18006b5b7  mov     rax, [rax]
0x18006b5ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b5bf  test    rax, rax
0x18006b5c2  cmovnz  rsi, rax
0x18006b5c6  mov     ecx, ebp; dwErrCode
0x18006b5c8  call    cs:__imp_SetLastError
0x18006b5ce  cmp     [rsi+7CCh], ebx
0x18006b5d4  jz      short loc_18006B5EE
0x18006b5d6  mov     r9d, ebx; int
0x18006b5d9  mov     r8d, 0D9h; int
0x18006b5df  lea     rdx, aMfd3d12syncSch; "MFD3D12Sync::ScheduleFreeWait"
0x18006b5e6  mov     rcx, rsi; this
0x18006b5e9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006b5ee  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006b5f5  jb      loc_18006B7DC
0x18006b5fb  mov     edx, 2Fh ; '/'
0x18006b600  mov     [rsp+98h+var_78], ebx
0x18006b604  jmp     loc_18006B7C2
0x18006b609  lea     r9, [r14+18h]; key
0x18006b60d  mov     r8, [rsp+98h+asyncResult]; result
0x18006b612  xor     edx, edx; lPriority
0x18006b614  mov     rcx, [r14]; hEvent
0x18006b617  call    cs:__imp_RtwqPutWaitingWorkItem
0x18006b61d  mov     ebx, eax
0x18006b61f  test    eax, eax
0x18006b621  jns     loc_18006B6E2
0x18006b627  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006b62e  test    rdi, rdi
0x18006b631  jnz     short loc_18006B641
0x18006b633  lea     rdi, qword_18009CF60
0x18006b63a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x18006b641  cmp     [rdi+8], r12b
0x18006b645  jz      loc_18006B6CB
0x18006b64b  lea     rsi, [rdi+0D0h]
0x18006b652  call    cs:__imp_GetLastError
0x18006b658  mov     ebp, eax
0x18006b65a  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18006b65d  call    cs:__imp_TlsGetValue
0x18006b663  test    rax, rax
0x18006b666  jz      short loc_18006B66D
0x18006b668  mov     rsi, rax
0x18006b66b  jmp     short loc_18006B6A3
0x18006b66d  call    cs:__imp_GetLastError
0x18006b673  test    eax, eax
0x18006b675  jnz     short loc_18006B6A3
0x18006b677  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006b67e  test    rcx, rcx
0x18006b681  jnz     short loc_18006B691
0x18006b683  lea     rcx, qword_18009CF60
0x18006b68a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006b691  mov     rax, [rcx]
0x18006b694  mov     rax, [rax]
0x18006b697  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b69c  test    rax, rax
0x18006b69f  cmovnz  rsi, rax
0x18006b6a3  mov     ecx, ebp; dwErrCode
0x18006b6a5  call    cs:__imp_SetLastError
0x18006b6ab  cmp     [rsi+7CCh], ebx
0x18006b6b1  jz      short loc_18006B6CB
0x18006b6b3  mov     r9d, ebx; int
0x18006b6b6  mov     r8d, 0DAh; int
0x18006b6bc  lea     rdx, aMfd3d12syncSch; "MFD3D12Sync::ScheduleFreeWait"
0x18006b6c3  mov     rcx, rsi; this
0x18006b6c6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006b6cb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006b6d2  jb      loc_18006B7DC
0x18006b6d8  mov     edx, 30h ; '0'
0x18006b6dd  jmp     loc_18006B600
0x18006b6e2  mov     [rsp+98h+var_58], r12
0x18006b6e7  lea     rcx, [r15+0C8h]
0x18006b6ee  lea     rdx, [rsp+98h+var_58]
0x18006b6f3  call    ?AcquireNode@?$CTNodePool@UNODEBLOCK@?$CTBucketHash@PEAUID3D12Fence@@PEAVQueuedFreeWait@MFD3D12Sync@@@@VNODE@2@$07@@QEAAJPEAPEAVNODE@?$CTBucketHash@PEAUID3D12Fence@@PEAVQueuedFreeWait@MFD3D12Sync@@@@@Z; CTNodePool<CTBucketHash<ID3D12Fence *,MFD3D12Sync::QueuedFreeWait *>::NODEBLOCK,CTBucketHash<ID3D12Fence *,MFD3D12Sync::QueuedFreeWait *>::NODE,8>::AcquireNode(CTBucketHash<ID3D12Fence *,MFD3D12Sync::QueuedFreeWait *>::NODE * *)
0x18006b6f8  test    eax, eax
0x18006b6fa  jns     loc_18006B7FE
0x18006b700  mov     esi, 8007000Eh
0x18006b705  mov     ebx, esi
0x18006b707  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006b70e  test    rdi, rdi
0x18006b711  jnz     short loc_18006B721
0x18006b713  lea     rdi, qword_18009CF60
0x18006b71a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x18006b721  cmp     [rdi+8], r12b
0x18006b725  jz      loc_18006B7B0
0x18006b72b  lea     rbp, [rdi+0D0h]
0x18006b732  call    cs:__imp_GetLastError
0x18006b738  mov     r12d, eax
0x18006b73b  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18006b73e  call    cs:__imp_TlsGetValue
0x18006b744  test    rax, rax
0x18006b747  jz      short loc_18006B74E
0x18006b749  mov     rbp, rax
0x18006b74c  jmp     short loc_18006B784
0x18006b74e  call    cs:__imp_GetLastError
0x18006b754  test    eax, eax
0x18006b756  jnz     short loc_18006B784
0x18006b758  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006b75f  test    rcx, rcx
0x18006b762  jnz     short loc_18006B772
0x18006b764  lea     rcx, qword_18009CF60
0x18006b76b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006b772  mov     rax, [rcx]
0x18006b775  mov     rax, [rax]
0x18006b778  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b77d  test    rax, rax
0x18006b780  cmovnz  rbp, rax
0x18006b784  mov     ecx, r12d; dwErrCode
0x18006b787  call    cs:__imp_SetLastError
0x18006b78d  xor     r12d, r12d
0x18006b790  cmp     [rbp+7CCh], esi
0x18006b796  jz      short loc_18006B7B0
0x18006b798  mov     r9d, esi; int
0x18006b79b  mov     r8d, 0DDh; int
0x18006b7a1  lea     rdx, aMfd3d12syncSch; "MFD3D12Sync::ScheduleFreeWait"
0x18006b7a8  mov     rcx, rbp; this
0x18006b7ab  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006b7b0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006b7b7  jb      short loc_18006B7DC
0x18006b7b9  mov     edx, 31h ; '1'
0x18006b7be  mov     [rsp+98h+var_78], esi
0x18006b7c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b7c9  mov     r9, r15
0x18006b7cc  lea     r8, WPP_18b1d8a13eb8310f1056d7c08509d55f_Traceguids
0x18006b7d3  mov     rcx, [rcx+10h]
0x18006b7d7  call    WPP_SF_qd
0x18006b7dc  mov     rcx, [r13+0]; hObject
0x18006b7e0  test    rcx, rcx
0x18006b7e3  jz      short loc_18006B7EF
0x18006b7e5  call    cs:__imp_CloseHandle
0x18006b7eb  mov     [r13+0], r12
0x18006b7ef  test    r14, r14
0x18006b7f2  jz      short loc_18006B83F
0x18006b7f4  mov     rcx, r14; this
0x18006b7f7  call    ??_GQueuedFreeWait@MFD3D12Sync@@QEAAPEAXI@Z; MFD3D12Sync::QueuedFreeWait::`scalar deleting destructor'(uint)
0x18006b7fc  jmp     short loc_18006B83F
0x18006b7fe  mov     r9, [rsp+98h+var_58]
0x18006b803  mov     [r9], rdi
0x18006b806  mov     [r9+8], r14
0x18006b80a  mov     ecx, [r15+0B8h]
0x18006b811  btr     ecx, 1Fh
0x18006b815  mov     eax, edi
0x18006b817  xor     edx, edx
0x18006b819  div     ecx
0x18006b81b  mov     rax, [r15+0B0h]
0x18006b822  mov     rcx, [rax+rdx*8]
0x18006b826  mov     [r9+10h], rcx
0x18006b82a  mov     rax, [r15+0B0h]
0x18006b831  mov     [rax+rdx*8], r9
0x18006b835  inc     dword ptr [r15+0BCh]
0x18006b83c  mov     ebx, r12d
0x18006b83f  lea     rcx, [rsp+98h+var_68]; this
0x18006b844  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18006b849  nop
0x18006b84a  lea     rcx, [rsp+98h+asyncResult]
0x18006b84f  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x18006b854  mov     eax, ebx
0x18006b856  add     rsp, 58h
0x18006b85a  pop     r15
0x18006b85c  pop     r14
0x18006b85e  pop     r13
0x18006b860  pop     r12
0x18006b862  pop     rdi
0x18006b863  pop     rsi
0x18006b864  pop     rbp
0x18006b865  pop     rbx
0x18006b866  retn
```
