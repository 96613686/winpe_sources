# MFD3D12Sync::OpenSharedHandleToFreeFence(void * *)

- ea: `0x1800cd3b0`
- end: `0x1800cd6ef`
- name: `?OpenSharedHandleToFreeFence@MFD3D12Sync@@UEAAJPEAPEAX@Z`
- size: `831`
- prototype: `__int64 __fastcall(MFD3D12Sync *__hidden this, void **)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x18000a954`
- `0x18000c9d0`
- `0x18000caec`
- `0x18000ec20`
- `0x18000ecf0`
- `0x18003639c`
- `0x180061e00`
- `0x1800a09f0`
- `0x1800cd3b0`
- `0x1800cded8`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cd3e1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cd3e1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800cd52d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800cd52d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cd6cc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cd6cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cd540`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cd540`

## string_xrefs

- `0x1800cd3c6`: `MFD3D12Sync::OpenSharedHandleToFreeFence`
- `0x1800cd463`: `MFD3D12Sync::OpenSharedHandleToFreeFence`
- `0x1800cd4f5`: `MFD3D12Sync::OpenSharedHandleToFreeFence`
- `0x1800cd587`: `MFD3D12Sync::OpenSharedHandleToFreeFence`
- `0x1800cd605`: `MFD3D12Sync::OpenSharedHandleToFreeFence`
- `0x1800cd67a`: `MFD3D12Sync::OpenSharedHandleToFreeFence`

## pseudocode

```c
__int64 __fastcall MFD3D12Sync::OpenSharedHandleToFreeFence(MFD3D12Sync *this, void **a2)
{
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, _QWORD, __int64, GUID *, __int64); // rbx
  __int64 v6; // rax
  signed int v7; // ebx
  CallStackTracing *v8; // rcx
  struct CallStackContext *v9; // rax
  __int64 v10; // rdx
  CallStackTracing *v11; // rcx
  struct CallStackContext *v12; // rax
  void *v13; // rdi
  signed int LastError; // eax
  CallStackTracing *v15; // rcx
  struct CallStackContext *v16; // rax
  CallStackTracing *v17; // rcx
  struct CallStackContext *v18; // rax
  CallStackTracing *v19; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  void *EventW; // [rsp+70h] [rbp+8h] BYREF
  struct ID3D12Fence *v23; // [rsp+80h] [rbp+18h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&EventW,
    "MFD3D12Sync::OpenSharedHandleToFreeFence",
    163);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  v23 = 0;
  v4 = *((_QWORD *)this + 13);
  v5 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, GUID *, __int64))(*(_QWORD *)v4 + 288LL);
  v6 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ID3D12Fence>>(&v23);
  v7 = v5(v4, 0, 1, &GUID_0a753dcf_c4d8_4b91_adf6_be5a60d95a76, v6);
  if ( v7 >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(_QWORD, struct ID3D12Fence *, _QWORD, __int64, _QWORD, void **))(**((_QWORD **)this + 13) + 248LL))(
           *((_QWORD *)this + 13),
           v23,
           0,
           0x10000000,
           0,
           a2);
    if ( v7 >= 0 )
    {
      EventW = CreateEventW(0, 1, 0, 0);
      v13 = EventW;
      if ( EventW )
        goto LABEL_28;
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      if ( v7 >= 0 )
      {
LABEL_28:
        v7 = ((__int64 (__fastcall *)(struct ID3D12Fence *, _QWORD, void *))v23->lpVtbl->SetEventOnCompletion)(
               v23,
               *((_QWORD *)this + 18),
               v13);
        if ( v7 >= 0 )
        {
          v7 = MFD3D12Sync::ScheduleFreeWait((MFD3D12Sync *)((char *)this - 16), &EventW, v23, 0);
          if ( v7 < 0 )
          {
            v19 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::InitInstance();
              v19 = CallStackTracing::s_wpInstance;
            }
            if ( *((_BYTE *)v19 + 8) )
            {
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v19);
              if ( *((_DWORD *)ThreadRelativeContext + 499) != v7 )
                CallStackContext::TraceFailure(
                  ThreadRelativeContext,
                  "MFD3D12Sync::OpenSharedHandleToFreeFence",
                  175,
                  v7);
            }
            if ( g_wppLevels )
            {
              v10 = 42;
              goto LABEL_44;
            }
          }
        }
        else
        {
          v17 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::InitInstance();
            v17 = CallStackTracing::s_wpInstance;
          }
          if ( *((_BYTE *)v17 + 8) )
          {
            v18 = CallStackTracing::GetThreadRelativeContext(v17);
            if ( *((_DWORD *)v18 + 499) != v7 )
              CallStackContext::TraceFailure(v18, "MFD3D12Sync::OpenSharedHandleToFreeFence", 174, v7);
          }
          if ( g_wppLevels )
          {
            v10 = 41;
            goto LABEL_44;
          }
        }
      }
      else
      {
        v15 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v15 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v15 + 8) )
        {
          v16 = CallStackTracing::GetThreadRelativeContext(v15);
          if ( *((_DWORD *)v16 + 499) != v7 )
            CallStackContext::TraceFailure(v16, "MFD3D12Sync::OpenSharedHandleToFreeFence", 172, v7);
        }
        if ( g_wppLevels )
        {
          v10 = 40;
          goto LABEL_44;
        }
      }
    }
    else
    {
      v11 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v11 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v11 + 8) )
      {
        v12 = CallStackTracing::GetThreadRelativeContext(v11);
        if ( *((_DWORD *)v12 + 499) != v7 )
          CallStackContext::TraceFailure(v12, "MFD3D12Sync::OpenSharedHandleToFreeFence", 168, v7);
      }
      if ( g_wppLevels )
      {
        v10 = 39;
        goto LABEL_44;
      }
    }
  }
  else
  {
    v8 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v8 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v8 + 8) )
    {
      v9 = CallStackTracing::GetThreadRelativeContext(v8);
      if ( *((_DWORD *)v9 + 499) != v7 )
        CallStackContext::TraceFailure(v9, "MFD3D12Sync::OpenSharedHandleToFreeFence", 167, v7);
    }
    if ( g_wppLevels )
    {
      v10 = 38;
LABEL_44:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v10,
        &WPP_fb0656c5b13f3c5e1eb6232bc9370e01_Traceguids,
        (char *)this - 16,
        v7);
    }
  }
  Microsoft::WRL::ComPtr<IMFDXGISchedulerRegistration>::InternalRelease(&v23);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&EventW);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800cd3b0  mov     [rsp+arg_8], rbx
0x1800cd3b5  push    rbp
0x1800cd3b6  push    rsi
0x1800cd3b7  push    rdi
0x1800cd3b8  push    r14
0x1800cd3ba  push    r15
0x1800cd3bc  sub     rsp, 40h
0x1800cd3c0  mov     r14, rdx
0x1800cd3c3  mov     rbp, rcx
0x1800cd3c6  lea     rdx, aMfd3d12syncOpe; "MFD3D12Sync::OpenSharedHandleToFreeFenc"...
0x1800cd3cd  mov     r8d, 0A3h; int
0x1800cd3d3  lea     rcx, [rsp+68h+arg_0]; this
0x1800cd3d8  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800cd3dd  lea     rcx, [rbp+40h]; lpCriticalSection
0x1800cd3e1  call    cs:__imp_EnterCriticalSection
0x1800cd3e7  mov     [rsp+68h+arg_10], 0
0x1800cd3f3  lea     rsi, [rbp-10h]
0x1800cd3f7  mov     rdi, [rsi+78h]
0x1800cd3fb  lea     rcx, [rsp+68h+arg_10]
0x1800cd403  mov     rax, [rdi]
0x1800cd406  mov     rbx, [rax+120h]
0x1800cd40d  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UID3D12Fence@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UID3D12Fence@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ID3D12Fence>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ID3D12Fence>>)
0x1800cd412  xor     edx, edx
0x1800cd414  mov     [rsp+68h+var_48], rax
0x1800cd419  lea     r9, _GUID_0a753dcf_c4d8_4b91_adf6_be5a60d95a76
0x1800cd420  mov     rcx, rdi
0x1800cd423  mov     rax, rbx
0x1800cd426  lea     r8d, [rdx+1]
0x1800cd42a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd42f  mov     ebx, eax
0x1800cd431  test    eax, eax
0x1800cd433  jns     short loc_1800CD48F
0x1800cd435  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cd43c  test    rcx, rcx
0x1800cd43f  jnz     short loc_1800CD44D
0x1800cd441  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800cd446  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800cd44d  cmp     byte ptr [rcx+8], 0
0x1800cd451  jz      short loc_1800CD478
0x1800cd453  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800cd458  cmp     [rax+7CCh], ebx
0x1800cd45e  jz      short loc_1800CD478
0x1800cd460  mov     r9d, ebx; int
0x1800cd463  lea     rdx, aMfd3d12syncOpe; "MFD3D12Sync::OpenSharedHandleToFreeFenc"...
0x1800cd46a  mov     r8d, 0A7h; int
0x1800cd470  mov     rcx, rax; this
0x1800cd473  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800cd478  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cd47f  jb      loc_1800CD6BB
0x1800cd485  mov     edx, 26h ; '&'
0x1800cd48a  jmp     loc_1800CD69D
0x1800cd48f  mov     rcx, [rsi+78h]
0x1800cd493  mov     r9d, 10000000h
0x1800cd499  mov     rdx, [rsp+68h+arg_10]
0x1800cd4a1  xor     r8d, r8d
0x1800cd4a4  mov     [rsp+68h+var_40], r14
0x1800cd4a9  mov     [rsp+68h+var_48], 0
0x1800cd4b2  mov     rax, [rcx]
0x1800cd4b5  mov     rax, [rax+0F8h]
0x1800cd4bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd4c1  mov     ebx, eax
0x1800cd4c3  test    eax, eax
0x1800cd4c5  jns     short loc_1800CD521
0x1800cd4c7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cd4ce  test    rcx, rcx
0x1800cd4d1  jnz     short loc_1800CD4DF
0x1800cd4d3  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800cd4d8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800cd4df  cmp     byte ptr [rcx+8], 0
0x1800cd4e3  jz      short loc_1800CD50A
0x1800cd4e5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800cd4ea  cmp     [rax+7CCh], ebx
0x1800cd4f0  jz      short loc_1800CD50A
0x1800cd4f2  mov     r9d, ebx; int
0x1800cd4f5  lea     rdx, aMfd3d12syncOpe; "MFD3D12Sync::OpenSharedHandleToFreeFenc"...
0x1800cd4fc  mov     r8d, 0A8h; int
0x1800cd502  mov     rcx, rax; this
0x1800cd505  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800cd50a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cd511  jb      loc_1800CD6BB
0x1800cd517  mov     edx, 27h ; '''
0x1800cd51c  jmp     loc_1800CD69D
0x1800cd521  xor     r9d, r9d; lpName
0x1800cd524  xor     r8d, r8d; bInitialState
0x1800cd527  xor     ecx, ecx; lpEventAttributes
0x1800cd529  lea     edx, [r9+1]; bManualReset
0x1800cd52d  call    cs:__imp_CreateEventW
0x1800cd533  mov     [rsp+68h+arg_0], rax
0x1800cd538  mov     rdi, rax
0x1800cd53b  test    rax, rax
0x1800cd53e  jnz     short loc_1800CD5B3
0x1800cd540  call    cs:__imp_GetLastError
0x1800cd546  mov     ebx, eax
0x1800cd548  test    eax, eax
0x1800cd54a  jle     short loc_1800CD555
0x1800cd54c  movzx   ebx, ax
0x1800cd54f  or      ebx, 80070000h
0x1800cd555  test    ebx, ebx
0x1800cd557  jns     short loc_1800CD5B3
0x1800cd559  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cd560  test    rcx, rcx
0x1800cd563  jnz     short loc_1800CD571
0x1800cd565  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800cd56a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800cd571  cmp     byte ptr [rcx+8], 0
0x1800cd575  jz      short loc_1800CD59C
0x1800cd577  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800cd57c  cmp     [rax+7CCh], ebx
0x1800cd582  jz      short loc_1800CD59C
0x1800cd584  mov     r9d, ebx; int
0x1800cd587  lea     rdx, aMfd3d12syncOpe; "MFD3D12Sync::OpenSharedHandleToFreeFenc"...
0x1800cd58e  mov     r8d, 0ACh; int
0x1800cd594  mov     rcx, rax; this
0x1800cd597  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800cd59c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cd5a3  jb      loc_1800CD6BB
0x1800cd5a9  mov     edx, 28h ; '('
0x1800cd5ae  jmp     loc_1800CD69D
0x1800cd5b3  mov     rcx, [rsp+68h+arg_10]
0x1800cd5bb  mov     r8, rdi
0x1800cd5be  mov     rdx, [rbp+90h]
0x1800cd5c5  mov     rax, [rcx]
0x1800cd5c8  mov     rax, [rax+48h]
0x1800cd5cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd5d1  mov     ebx, eax
0x1800cd5d3  test    eax, eax
0x1800cd5d5  jns     short loc_1800CD62E
0x1800cd5d7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cd5de  test    rcx, rcx
0x1800cd5e1  jnz     short loc_1800CD5EF
0x1800cd5e3  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800cd5e8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800cd5ef  cmp     byte ptr [rcx+8], 0
0x1800cd5f3  jz      short loc_1800CD61A
0x1800cd5f5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800cd5fa  cmp     [rax+7CCh], ebx
0x1800cd600  jz      short loc_1800CD61A
0x1800cd602  mov     r9d, ebx; int
0x1800cd605  lea     rdx, aMfd3d12syncOpe; "MFD3D12Sync::OpenSharedHandleToFreeFenc"...
0x1800cd60c  mov     r8d, 0AEh; int
0x1800cd612  mov     rcx, rax; this
0x1800cd615  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800cd61a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cd621  jb      loc_1800CD6BB
0x1800cd627  mov     edx, 29h ; ')'
0x1800cd62c  jmp     short loc_1800CD69D
0x1800cd62e  mov     r8, [rsp+68h+arg_10]; struct ID3D12Fence *
0x1800cd636  lea     rdx, [rsp+68h+arg_0]; void **
0x1800cd63b  xor     r9d, r9d; struct ID3D11Fence *
0x1800cd63e  mov     rcx, rsi; this
0x1800cd641  call    ?ScheduleFreeWait@MFD3D12Sync@@IEAAJAEAPEAXPEAUID3D12Fence@@PEAUID3D11Fence@@@Z; MFD3D12Sync::ScheduleFreeWait(void * &,ID3D12Fence *,ID3D11Fence *)
0x1800cd646  mov     ebx, eax
0x1800cd648  test    eax, eax
0x1800cd64a  jns     short loc_1800CD6BB
0x1800cd64c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cd653  test    rcx, rcx
0x1800cd656  jnz     short loc_1800CD664
0x1800cd658  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800cd65d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800cd664  cmp     byte ptr [rcx+8], 0
0x1800cd668  jz      short loc_1800CD68F
0x1800cd66a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800cd66f  cmp     [rax+7CCh], ebx
0x1800cd675  jz      short loc_1800CD68F
0x1800cd677  mov     r9d, ebx; int
0x1800cd67a  lea     rdx, aMfd3d12syncOpe; "MFD3D12Sync::OpenSharedHandleToFreeFenc"...
0x1800cd681  mov     r8d, 0AFh; int
0x1800cd687  mov     rcx, rax; this
0x1800cd68a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800cd68f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cd696  jb      short loc_1800CD6BB
0x1800cd698  mov     edx, 2Ah ; '*'
0x1800cd69d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cd6a4  lea     r8, WPP_fb0656c5b13f3c5e1eb6232bc9370e01_Traceguids
0x1800cd6ab  mov     r9, rsi
0x1800cd6ae  mov     dword ptr [rsp+68h+var_48], ebx
0x1800cd6b2  mov     rcx, [rcx+10h]
0x1800cd6b6  call    WPP_SF_qD
0x1800cd6bb  lea     rcx, [rsp+68h+arg_10]
0x1800cd6c3  call    ?InternalRelease@?$ComPtr@UIMFDXGISchedulerRegistration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFDXGISchedulerRegistration>::InternalRelease(void)
0x1800cd6c8  lea     rcx, [rbp+40h]; lpCriticalSection
0x1800cd6cc  call    cs:__imp_LeaveCriticalSection
0x1800cd6d2  lea     rcx, [rsp+68h+arg_0]; this
0x1800cd6d7  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800cd6dc  mov     eax, ebx
0x1800cd6de  mov     rbx, [rsp+68h+arg_8]
0x1800cd6e3  add     rsp, 40h
0x1800cd6e7  pop     r15
0x1800cd6e9  pop     r14
0x1800cd6eb  pop     rdi
0x1800cd6ec  pop     rsi
0x1800cd6ed  pop     rbp
0x1800cd6ee  retn
```
