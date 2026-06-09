# MFD3D12Sync::EnqueueResourceReadyWait(ID3D12CommandQueue *)

- ea: `0x1800cbd50`
- end: `0x1800cc0b6`
- name: `?EnqueueResourceReadyWait@MFD3D12Sync@@UEAAJPEAUID3D12CommandQueue@@@Z`
- size: `870`
- prototype: `__int64 __fastcall(MFD3D12Sync *__hidden this, struct ID3D12CommandQueue *)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x18000a09c`
- `0x18000a954`
- `0x18000c9d0`
- `0x18000caec`
- `0x18000ec20`
- `0x18000ecf0`
- `0x18003639c`
- `0x180061e00`
- `0x1800cbd50`
- `0x1800cf140`
- `0x1800cf9b4`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cbe24`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cbe24`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cbec8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cbfd7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cbec8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cbfd7`

## string_xrefs

- `0x1800cbd66`: `MFD3D12Sync::EnqueueResourceReadyWait`

## pseudocode

```c
__int64 __fastcall MFD3D12Sync::EnqueueResourceReadyWait(
        struct _RTL_CRITICAL_SECTION *this,
        struct ID3D12CommandQueue *a2)
{
  CallStackTracing *v4; // rcx
  int Fence; // ebx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v7; // rdx
  HRESULT (__stdcall *GetDevice)(ID3D12CommandQueue *, const IID *const, void **); // rbx
  CallStackTracing *v9; // rcx
  struct CallStackContext *v10; // rax
  __int64 v11; // rdx
  CallStackTracing *v12; // rcx
  struct CallStackContext *v13; // rax
  CallStackTracing *v14; // rcx
  struct CallStackContext *v15; // rax
  __int64 v16; // r8
  CallStackTracing *v18; // rcx
  struct CallStackContext *v19; // rax
  struct ID3D12Fence *v20; // [rsp+68h] [rbp+38h] BYREF
  struct ID3D12Device *v21; // [rsp+70h] [rbp+40h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v20, "MFD3D12Sync::EnqueueResourceReadyWait", 126);
  if ( !a2 )
  {
    v4 = CallStackTracing::s_wpInstance;
    Fence = -2147024809;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v4 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v4 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v4);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024809 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "MFD3D12Sync::EnqueueResourceReadyWait", 126, -2147024809);
    }
    if ( g_wppLevels )
    {
      v7 = 29;
LABEL_9:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, &WPP_fb0656c5b13f3c5e1eb6232bc9370e01_Traceguids, this, Fence);
      goto LABEL_40;
    }
    goto LABEL_40;
  }
  if ( LOBYTE(this[4].LockCount) )
  {
    v21 = 0;
    v20 = 0;
    EnterCriticalSection(this + 2);
    GetDevice = a2->lpVtbl->GetDevice;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
    Fence = ((__int64 (__fastcall *)(struct ID3D12CommandQueue *, GUID *, struct ID3D12Device **))GetDevice)(
              a2,
              &GUID_189819f1_1db6_4b57_be54_1821339b85f7,
              &v21);
    if ( Fence < 0 )
    {
      v9 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v9 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v9 + 8) )
      {
        v10 = CallStackTracing::GetThreadRelativeContext(v9);
        if ( *((_DWORD *)v10 + 499) != Fence )
          CallStackContext::TraceFailure(v10, "MFD3D12Sync::EnqueueResourceReadyWait", 132, Fence);
      }
      if ( !g_wppLevels )
        goto LABEL_20;
      v11 = 30;
LABEL_19:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_fb0656c5b13f3c5e1eb6232bc9370e01_Traceguids, this, Fence);
LABEL_20:
      LeaveCriticalSection(this + 2);
      Microsoft::WRL::ComPtr<IMFDXGISchedulerRegistration>::InternalRelease(&v20);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
      goto LABEL_40;
    }
    Microsoft::WRL::ComPtr<IMFDXGISchedulerRegistration>::InternalRelease(&v20);
    Fence = SharedFenceManager::GetFence((SharedFenceManager *)&this[10].SpinCount, v21, &v20);
    if ( Fence < 0 )
    {
      v12 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v12 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v12 + 8) )
      {
        v13 = CallStackTracing::GetThreadRelativeContext(v12);
        if ( *((_DWORD *)v13 + 499) != Fence )
          CallStackContext::TraceFailure(v13, "MFD3D12Sync::EnqueueResourceReadyWait", 133, Fence);
      }
      if ( !g_wppLevels )
        goto LABEL_20;
      v11 = 31;
      goto LABEL_19;
    }
    Fence = ((__int64 (__fastcall *)(struct ID3D12CommandQueue *, struct ID3D12Fence *, PRTL_CRITICAL_SECTION_DEBUG))a2->lpVtbl->Wait)(
              a2,
              v20,
              this[4].DebugInfo);
    if ( Fence < 0 )
    {
      v14 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v14 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v14 + 8) )
      {
        v15 = CallStackTracing::GetThreadRelativeContext(v14);
        if ( *((_DWORD *)v15 + 499) != Fence )
          CallStackContext::TraceFailure(v15, "MFD3D12Sync::EnqueueResourceReadyWait", 134, Fence);
      }
      if ( !g_wppLevels )
        goto LABEL_20;
      v11 = 32;
      goto LABEL_19;
    }
    LeaveCriticalSection(this + 2);
    Microsoft::WRL::ComPtr<IMFDXGISchedulerRegistration>::InternalRelease(&v20);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
LABEL_38:
    if ( g_wppLevels >= 0x10u )
      WPP_SF_qqI(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, v16, this, a2, this[4].DebugInfo);
    goto LABEL_40;
  }
  Fence = ((__int64 (__fastcall *)(struct ID3D12CommandQueue *, _QWORD, PRTL_CRITICAL_SECTION_DEBUG))a2->lpVtbl->Wait)(
            a2,
            *(_QWORD *)&this[3].LockCount,
            this[4].DebugInfo);
  if ( Fence >= 0 )
    goto LABEL_38;
  v18 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v18 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v18 + 8) )
  {
    v19 = CallStackTracing::GetThreadRelativeContext(v18);
    if ( *((_DWORD *)v19 + 499) != Fence )
      CallStackContext::TraceFailure(v19, "MFD3D12Sync::EnqueueResourceReadyWait", 139, Fence);
  }
  if ( g_wppLevels )
  {
    v7 = 34;
    goto LABEL_9;
  }
LABEL_40:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v20);
  return (unsigned int)Fence;
}

```

## disassembly

```asm
0x1800cbd50  mov     [rsp-28h+arg_0], rbx
0x1800cbd55  push    rbp
0x1800cbd56  push    rsi
0x1800cbd57  push    rdi
0x1800cbd58  push    r12
0x1800cbd5a  push    r14
0x1800cbd5c  mov     rbp, rsp
0x1800cbd5f  sub     rsp, 30h
0x1800cbd63  mov     rsi, rdx
0x1800cbd66  lea     r12, aMfd3d12syncEnq_1; "MFD3D12Sync::EnqueueResourceReadyWait"
0x1800cbd6d  mov     rdi, rcx
0x1800cbd70  mov     r14d, 7Eh ; '~'
0x1800cbd76  mov     r8d, r14d; int
0x1800cbd79  lea     rcx, [rbp+arg_8]; this
0x1800cbd7d  mov     rdx, r12; char *
0x1800cbd80  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800cbd85  test    rsi, rsi
0x1800cbd88  jnz     short loc_1800CBE00
0x1800cbd8a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cbd91  mov     ebx, 80070057h
0x1800cbd96  test    rcx, rcx
0x1800cbd99  jnz     short loc_1800CBDA7
0x1800cbd9b  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800cbda0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800cbda7  cmp     byte ptr [rcx+8], 0
0x1800cbdab  jz      short loc_1800CBDCB
0x1800cbdad  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800cbdb2  cmp     [rax+7CCh], ebx
0x1800cbdb8  jz      short loc_1800CBDCB
0x1800cbdba  mov     r9d, ebx; int
0x1800cbdbd  mov     r8d, r14d; int
0x1800cbdc0  mov     rdx, r12; char *
0x1800cbdc3  mov     rcx, rax; this
0x1800cbdc6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800cbdcb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cbdd2  jb      loc_1800CC021
0x1800cbdd8  mov     edx, 1Dh
0x1800cbddd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cbde4  lea     r8, WPP_fb0656c5b13f3c5e1eb6232bc9370e01_Traceguids
0x1800cbdeb  mov     r9, rdi
0x1800cbdee  mov     dword ptr [rsp+30h+var_10], ebx
0x1800cbdf2  mov     rcx, [rcx+10h]
0x1800cbdf6  call    WPP_SF_qD
0x1800cbdfb  jmp     loc_1800CC021
0x1800cbe00  cmp     byte ptr [rdi+0A8h], 0
0x1800cbe07  jz      loc_1800CC03D
0x1800cbe0d  lea     r14, [rdi+50h]
0x1800cbe11  mov     [rbp+arg_10], 0
0x1800cbe19  mov     rcx, r14; lpCriticalSection
0x1800cbe1c  mov     [rbp+arg_8], 0
0x1800cbe24  call    cs:__imp_EnterCriticalSection
0x1800cbe2a  mov     rax, [rsi]
0x1800cbe2d  lea     rcx, [rbp+arg_10]
0x1800cbe31  mov     rbx, [rax+38h]
0x1800cbe35  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cbe3a  lea     r8, [rbp+arg_10]
0x1800cbe3e  mov     rcx, rsi
0x1800cbe41  lea     rdx, _GUID_189819f1_1db6_4b57_be54_1821339b85f7
0x1800cbe48  mov     rax, rbx
0x1800cbe4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cbe50  mov     ebx, eax
0x1800cbe52  test    eax, eax
0x1800cbe54  jns     loc_1800CBEE5
0x1800cbe5a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cbe61  test    rcx, rcx
0x1800cbe64  jnz     short loc_1800CBE72
0x1800cbe66  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800cbe6b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800cbe72  cmp     byte ptr [rcx+8], 0
0x1800cbe76  jz      short loc_1800CBE99
0x1800cbe78  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800cbe7d  cmp     [rax+7CCh], ebx
0x1800cbe83  jz      short loc_1800CBE99
0x1800cbe85  mov     r9d, ebx; int
0x1800cbe88  mov     r8d, 84h; int
0x1800cbe8e  mov     rdx, r12; char *
0x1800cbe91  mov     rcx, rax; this
0x1800cbe94  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800cbe99  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cbea0  jb      short loc_1800CBEC5
0x1800cbea2  mov     edx, 1Eh
0x1800cbea7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cbeae  lea     r8, WPP_fb0656c5b13f3c5e1eb6232bc9370e01_Traceguids
0x1800cbeb5  mov     r9, rdi
0x1800cbeb8  mov     dword ptr [rsp+30h+var_10], ebx
0x1800cbebc  mov     rcx, [rcx+10h]
0x1800cbec0  call    WPP_SF_qD
0x1800cbec5  mov     rcx, r14; lpCriticalSection
0x1800cbec8  call    cs:__imp_LeaveCriticalSection
0x1800cbece  lea     rcx, [rbp+arg_8]
0x1800cbed2  call    ?InternalRelease@?$ComPtr@UIMFDXGISchedulerRegistration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFDXGISchedulerRegistration>::InternalRelease(void)
0x1800cbed7  lea     rcx, [rbp+arg_10]
0x1800cbedb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cbee0  jmp     loc_1800CC021
0x1800cbee5  lea     rcx, [rbp+arg_8]
0x1800cbee9  call    ?InternalRelease@?$ComPtr@UIMFDXGISchedulerRegistration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFDXGISchedulerRegistration>::InternalRelease(void)
0x1800cbeee  mov     rdx, [rbp+arg_10]; struct ID3D12Device *
0x1800cbef2  lea     rcx, [rdi+1B0h]; this
0x1800cbef9  lea     r8, [rbp+arg_8]; struct ID3D12Fence **
0x1800cbefd  call    ?GetFence@SharedFenceManager@@QEAAJPEAUID3D12Device@@PEAPEAUID3D12Fence@@@Z; SharedFenceManager::GetFence(ID3D12Device *,ID3D12Fence * *)
0x1800cbf02  mov     ebx, eax
0x1800cbf04  test    eax, eax
0x1800cbf06  jns     short loc_1800CBF5E
0x1800cbf08  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cbf0f  test    rcx, rcx
0x1800cbf12  jnz     short loc_1800CBF20
0x1800cbf14  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800cbf19  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800cbf20  cmp     byte ptr [rcx+8], 0
0x1800cbf24  jz      short loc_1800CBF47
0x1800cbf26  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800cbf2b  cmp     [rax+7CCh], ebx
0x1800cbf31  jz      short loc_1800CBF47
0x1800cbf33  mov     r9d, ebx; int
0x1800cbf36  mov     r8d, 85h; int
0x1800cbf3c  mov     rdx, r12; char *
0x1800cbf3f  mov     rcx, rax; this
0x1800cbf42  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800cbf47  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cbf4e  jb      loc_1800CBEC5
0x1800cbf54  mov     edx, 1Fh
0x1800cbf59  jmp     loc_1800CBEA7
0x1800cbf5e  mov     rax, [rsi]
0x1800cbf61  mov     rcx, rsi
0x1800cbf64  mov     r8, [rdi+0A0h]
0x1800cbf6b  mov     rdx, [rbp+arg_8]
0x1800cbf6f  mov     rax, [rax+78h]
0x1800cbf73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cbf78  mov     ebx, eax
0x1800cbf7a  test    eax, eax
0x1800cbf7c  jns     short loc_1800CBFD4
0x1800cbf7e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cbf85  test    rcx, rcx
0x1800cbf88  jnz     short loc_1800CBF96
0x1800cbf8a  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800cbf8f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800cbf96  cmp     byte ptr [rcx+8], 0
0x1800cbf9a  jz      short loc_1800CBFBD
0x1800cbf9c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800cbfa1  cmp     [rax+7CCh], ebx
0x1800cbfa7  jz      short loc_1800CBFBD
0x1800cbfa9  mov     r9d, ebx; int
0x1800cbfac  mov     r8d, 86h; int
0x1800cbfb2  mov     rdx, r12; char *
0x1800cbfb5  mov     rcx, rax; this
0x1800cbfb8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800cbfbd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cbfc4  jb      loc_1800CBEC5
0x1800cbfca  mov     edx, 20h ; ' '
0x1800cbfcf  jmp     loc_1800CBEA7
0x1800cbfd4  mov     rcx, r14; lpCriticalSection
0x1800cbfd7  call    cs:__imp_LeaveCriticalSection
0x1800cbfdd  lea     rcx, [rbp+arg_8]
0x1800cbfe1  call    ?InternalRelease@?$ComPtr@UIMFDXGISchedulerRegistration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFDXGISchedulerRegistration>::InternalRelease(void)
0x1800cbfe6  lea     rcx, [rbp+arg_10]
0x1800cbfea  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cbfef  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 10h; MFWppLevels g_wppLevels
0x1800cbff6  jb      short loc_1800CC021
0x1800cbff8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cbfff  mov     edx, 23h ; '#'
0x1800cc004  mov     rax, [rdi+0A0h]
0x1800cc00b  mov     r9, rdi
0x1800cc00e  mov     [rsp+30h+var_8], rax
0x1800cc013  mov     [rsp+30h+var_10], rsi
0x1800cc018  mov     rcx, [rcx+10h]
0x1800cc01c  call    WPP_SF_qqI
0x1800cc021  lea     rcx, [rbp+arg_8]; this
0x1800cc025  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800cc02a  mov     eax, ebx
0x1800cc02c  mov     rbx, [rsp+30h+arg_0]
0x1800cc031  add     rsp, 30h
0x1800cc035  pop     r14
0x1800cc037  pop     r12
0x1800cc039  pop     rdi
0x1800cc03a  pop     rsi
0x1800cc03b  pop     rbp
0x1800cc03c  retn
0x1800cc03d  mov     rax, [rsi]
0x1800cc040  mov     rcx, rsi
0x1800cc043  mov     r8, [rdi+0A0h]
0x1800cc04a  mov     rdx, [rdi+80h]
0x1800cc051  mov     rax, [rax+78h]
0x1800cc055  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cc05a  mov     ebx, eax
0x1800cc05c  test    eax, eax
0x1800cc05e  jns     short loc_1800CBFEF
0x1800cc060  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cc067  test    rcx, rcx
0x1800cc06a  jnz     short loc_1800CC078
0x1800cc06c  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800cc071  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800cc078  cmp     byte ptr [rcx+8], 0
0x1800cc07c  jz      short loc_1800CC09F
0x1800cc07e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800cc083  cmp     [rax+7CCh], ebx
0x1800cc089  jz      short loc_1800CC09F
0x1800cc08b  mov     r9d, ebx; int
0x1800cc08e  mov     r8d, 8Bh; int
0x1800cc094  mov     rdx, r12; char *
0x1800cc097  mov     rcx, rax; this
0x1800cc09a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800cc09f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cc0a6  jb      loc_1800CC021
0x1800cc0ac  mov     edx, 22h ; '"'
0x1800cc0b1  jmp     loc_1800CBDDD
```
