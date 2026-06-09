# MFD3D12Sync::EnqueueResourceReady(ID3D12CommandQueue *)

- ea: `0x1800cb980`
- end: `0x1800cbd3d`
- name: `?EnqueueResourceReady@MFD3D12Sync@@UEAAJPEAUID3D12CommandQueue@@@Z`
- size: `957`
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
- `0x1800cb980`
- `0x1800cf140`
- `0x1800cf9b4`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cba53`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cba53`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cbad1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cbc5a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cbad1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cbc5a`

## string_xrefs

- `0x1800cb9ae`: `MFD3D12Sync::EnqueueResourceReady`

## pseudocode

```c
__int64 __fastcall MFD3D12Sync::EnqueueResourceReady(struct _RTL_CRITICAL_SECTION *this, struct ID3D12CommandQueue *a2)
{
  CallStackTracing *v4; // rcx
  int RecursionCount; // ebx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v7; // rdx
  CallStackTracing *v8; // rcx
  struct CallStackContext *v9; // rax
  __int64 v10; // rdx
  HRESULT (__stdcall *GetDevice)(ID3D12CommandQueue *, const IID *const, void **); // rbx
  CallStackTracing *v12; // rcx
  struct CallStackContext *v13; // rax
  CallStackTracing *v14; // rcx
  struct CallStackContext *v15; // rax
  CallStackTracing *v16; // rcx
  struct CallStackContext *v17; // rax
  __int64 v18; // r8
  CallStackTracing *v20; // rcx
  struct CallStackContext *v21; // rax
  char v22; // [rsp+68h] [rbp+38h] BYREF
  struct ID3D12Fence *v23; // [rsp+70h] [rbp+40h] BYREF
  struct ID3D12Device *v24; // [rsp+78h] [rbp+48h] BYREF

  v24 = 0;
  v23 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v22, "MFD3D12Sync::EnqueueResourceReady", 98);
  if ( !a2 )
  {
    v4 = CallStackTracing::s_wpInstance;
    RecursionCount = -2147024809;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v4 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v4 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v4);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024809 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "MFD3D12Sync::EnqueueResourceReady", 98, -2147024809);
    }
    if ( g_wppLevels )
    {
      v7 = 22;
LABEL_9:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v7,
        &WPP_fb0656c5b13f3c5e1eb6232bc9370e01_Traceguids,
        this,
        RecursionCount);
      goto LABEL_48;
    }
    goto LABEL_48;
  }
  if ( LOBYTE(this[4].LockCount) )
  {
    EnterCriticalSection(this + 2);
    RecursionCount = this[4].RecursionCount;
    if ( RecursionCount < 0 )
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
        if ( *((_DWORD *)v9 + 499) != RecursionCount )
          CallStackContext::TraceFailure(v9, "MFD3D12Sync::EnqueueResourceReady", 104, RecursionCount);
      }
      if ( !g_wppLevels )
        goto LABEL_20;
      v10 = 23;
LABEL_19:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v10,
        &WPP_fb0656c5b13f3c5e1eb6232bc9370e01_Traceguids,
        this,
        RecursionCount);
LABEL_20:
      LeaveCriticalSection(this + 2);
      goto LABEL_48;
    }
    GetDevice = a2->lpVtbl->GetDevice;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
    RecursionCount = ((__int64 (__fastcall *)(struct ID3D12CommandQueue *, GUID *, struct ID3D12Device **))GetDevice)(
                       a2,
                       &GUID_189819f1_1db6_4b57_be54_1821339b85f7,
                       &v24);
    if ( RecursionCount < 0 )
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
        if ( *((_DWORD *)v13 + 499) != RecursionCount )
          CallStackContext::TraceFailure(v13, "MFD3D12Sync::EnqueueResourceReady", 105, RecursionCount);
      }
      if ( !g_wppLevels )
        goto LABEL_20;
      v10 = 24;
      goto LABEL_19;
    }
    Microsoft::WRL::ComPtr<IMFDXGISchedulerRegistration>::InternalRelease(&v23);
    RecursionCount = SharedFenceManager::GetFence((SharedFenceManager *)&this[10].SpinCount, v24, &v23);
    if ( RecursionCount < 0 )
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
        if ( *((_DWORD *)v15 + 499) != RecursionCount )
          CallStackContext::TraceFailure(v15, "MFD3D12Sync::EnqueueResourceReady", 106, RecursionCount);
      }
      if ( !g_wppLevels )
        goto LABEL_20;
      v10 = 25;
      goto LABEL_19;
    }
    RecursionCount = ((__int64 (__fastcall *)(struct ID3D12CommandQueue *, struct ID3D12Fence *, PRTL_CRITICAL_SECTION_DEBUG))a2->lpVtbl->Signal)(
                       a2,
                       v23,
                       this[4].DebugInfo);
    if ( RecursionCount < 0 )
    {
      v16 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v16 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v16 + 8) )
      {
        v17 = CallStackTracing::GetThreadRelativeContext(v16);
        if ( *((_DWORD *)v17 + 499) != RecursionCount )
          CallStackContext::TraceFailure(v17, "MFD3D12Sync::EnqueueResourceReady", 108, RecursionCount);
      }
      if ( !g_wppLevels )
        goto LABEL_20;
      v10 = 26;
      goto LABEL_19;
    }
    this[4].RecursionCount = -1072871856;
    LeaveCriticalSection(this + 2);
LABEL_46:
    if ( g_wppLevels >= 0x10u )
      WPP_SF_qqI(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, v18, this, a2, this[4].DebugInfo);
    goto LABEL_48;
  }
  RecursionCount = ((__int64 (__fastcall *)(struct ID3D12CommandQueue *, _QWORD, PRTL_CRITICAL_SECTION_DEBUG))a2->lpVtbl->Signal)(
                     a2,
                     *(_QWORD *)&this[3].LockCount,
                     this[4].DebugInfo);
  if ( RecursionCount >= 0 )
    goto LABEL_46;
  v20 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v20 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v20 + 8) )
  {
    v21 = CallStackTracing::GetThreadRelativeContext(v20);
    if ( *((_DWORD *)v21 + 499) != RecursionCount )
      CallStackContext::TraceFailure(v21, "MFD3D12Sync::EnqueueResourceReady", 113, RecursionCount);
  }
  if ( g_wppLevels )
  {
    v7 = 27;
    goto LABEL_9;
  }
LABEL_48:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v22);
  Microsoft::WRL::ComPtr<IMFDXGISchedulerRegistration>::InternalRelease(&v23);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
  return (unsigned int)RecursionCount;
}

```

## disassembly

```asm
0x1800cb980  mov     [rsp-28h+arg_0], rbx
0x1800cb985  push    rbp
0x1800cb986  push    rsi
0x1800cb987  push    rdi
0x1800cb988  push    r12
0x1800cb98a  push    r14
0x1800cb98c  mov     rbp, rsp
0x1800cb98f  sub     rsp, 30h
0x1800cb993  mov     r14, rdx
0x1800cb996  mov     [rbp+arg_18], 0
0x1800cb99e  mov     rdi, rcx
0x1800cb9a1  mov     [rbp+arg_10], 0
0x1800cb9a9  mov     esi, 62h ; 'b'
0x1800cb9ae  lea     r12, aMfd3d12syncEnq_0; "MFD3D12Sync::EnqueueResourceReady"
0x1800cb9b5  mov     r8d, esi; int
0x1800cb9b8  lea     rcx, [rbp+arg_8]; this
0x1800cb9bc  mov     rdx, r12; char *
0x1800cb9bf  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800cb9c4  test    r14, r14
0x1800cb9c7  jnz     short loc_1800CBA3F
0x1800cb9c9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cb9d0  mov     ebx, 80070057h
0x1800cb9d5  test    rcx, rcx
0x1800cb9d8  jnz     short loc_1800CB9E6
0x1800cb9da  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800cb9df  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800cb9e6  cmp     byte ptr [rcx+8], 0
0x1800cb9ea  jz      short loc_1800CBA0A
0x1800cb9ec  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800cb9f1  cmp     [rax+7CCh], ebx
0x1800cb9f7  jz      short loc_1800CBA0A
0x1800cb9f9  mov     r9d, ebx; int
0x1800cb9fc  mov     r8d, esi; int
0x1800cb9ff  mov     rdx, r12; char *
0x1800cba02  mov     rcx, rax; this
0x1800cba05  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800cba0a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cba11  jb      loc_1800CBC92
0x1800cba17  mov     edx, 16h
0x1800cba1c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cba23  lea     r8, WPP_fb0656c5b13f3c5e1eb6232bc9370e01_Traceguids
0x1800cba2a  mov     r9, rdi
0x1800cba2d  mov     dword ptr [rsp+30h+var_10], ebx
0x1800cba31  mov     rcx, [rcx+10h]
0x1800cba35  call    WPP_SF_qD
0x1800cba3a  jmp     loc_1800CBC92
0x1800cba3f  cmp     byte ptr [rdi+0A8h], 0
0x1800cba46  jz      loc_1800CBCC0
0x1800cba4c  lea     rsi, [rdi+50h]
0x1800cba50  mov     rcx, rsi; lpCriticalSection
0x1800cba53  call    cs:__imp_EnterCriticalSection
0x1800cba59  mov     ebx, [rdi+0ACh]
0x1800cba5f  test    ebx, ebx
0x1800cba61  jns     short loc_1800CBADC
0x1800cba63  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cba6a  test    rcx, rcx
0x1800cba6d  jnz     short loc_1800CBA7B
0x1800cba6f  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800cba74  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800cba7b  cmp     byte ptr [rcx+8], 0
0x1800cba7f  jz      short loc_1800CBAA2
0x1800cba81  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800cba86  cmp     [rax+7CCh], ebx
0x1800cba8c  jz      short loc_1800CBAA2
0x1800cba8e  mov     r9d, ebx; int
0x1800cba91  mov     r8d, 68h ; 'h'; int
0x1800cba97  mov     rdx, r12; char *
0x1800cba9a  mov     rcx, rax; this
0x1800cba9d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800cbaa2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cbaa9  jb      short loc_1800CBACE
0x1800cbaab  mov     edx, 17h
0x1800cbab0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cbab7  lea     r8, WPP_fb0656c5b13f3c5e1eb6232bc9370e01_Traceguids
0x1800cbabe  mov     r9, rdi
0x1800cbac1  mov     dword ptr [rsp+30h+var_10], ebx
0x1800cbac5  mov     rcx, [rcx+10h]
0x1800cbac9  call    WPP_SF_qD
0x1800cbace  mov     rcx, rsi; lpCriticalSection
0x1800cbad1  call    cs:__imp_LeaveCriticalSection
0x1800cbad7  jmp     loc_1800CBC92
0x1800cbadc  mov     rax, [r14]
0x1800cbadf  lea     rcx, [rbp+arg_18]
0x1800cbae3  mov     rbx, [rax+38h]
0x1800cbae7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cbaec  lea     r8, [rbp+arg_18]
0x1800cbaf0  mov     rcx, r14
0x1800cbaf3  lea     rdx, _GUID_189819f1_1db6_4b57_be54_1821339b85f7
0x1800cbafa  mov     rax, rbx
0x1800cbafd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cbb02  mov     ebx, eax
0x1800cbb04  test    eax, eax
0x1800cbb06  jns     short loc_1800CBB5E
0x1800cbb08  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cbb0f  test    rcx, rcx
0x1800cbb12  jnz     short loc_1800CBB20
0x1800cbb14  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800cbb19  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800cbb20  cmp     byte ptr [rcx+8], 0
0x1800cbb24  jz      short loc_1800CBB47
0x1800cbb26  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800cbb2b  cmp     [rax+7CCh], ebx
0x1800cbb31  jz      short loc_1800CBB47
0x1800cbb33  mov     r9d, ebx; int
0x1800cbb36  mov     r8d, 69h ; 'i'; int
0x1800cbb3c  mov     rdx, r12; char *
0x1800cbb3f  mov     rcx, rax; this
0x1800cbb42  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800cbb47  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cbb4e  jb      loc_1800CBACE
0x1800cbb54  mov     edx, 18h
0x1800cbb59  jmp     loc_1800CBAB0
0x1800cbb5e  lea     rcx, [rbp+arg_10]
0x1800cbb62  call    ?InternalRelease@?$ComPtr@UIMFDXGISchedulerRegistration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFDXGISchedulerRegistration>::InternalRelease(void)
0x1800cbb67  mov     rdx, [rbp+arg_18]; struct ID3D12Device *
0x1800cbb6b  lea     rcx, [rdi+1B0h]; this
0x1800cbb72  lea     r8, [rbp+arg_10]; struct ID3D12Fence **
0x1800cbb76  call    ?GetFence@SharedFenceManager@@QEAAJPEAUID3D12Device@@PEAPEAUID3D12Fence@@@Z; SharedFenceManager::GetFence(ID3D12Device *,ID3D12Fence * *)
0x1800cbb7b  mov     ebx, eax
0x1800cbb7d  test    eax, eax
0x1800cbb7f  jns     short loc_1800CBBD7
0x1800cbb81  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cbb88  test    rcx, rcx
0x1800cbb8b  jnz     short loc_1800CBB99
0x1800cbb8d  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800cbb92  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800cbb99  cmp     byte ptr [rcx+8], 0
0x1800cbb9d  jz      short loc_1800CBBC0
0x1800cbb9f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800cbba4  cmp     [rax+7CCh], ebx
0x1800cbbaa  jz      short loc_1800CBBC0
0x1800cbbac  mov     r9d, ebx; int
0x1800cbbaf  mov     r8d, 6Ah ; 'j'; int
0x1800cbbb5  mov     rdx, r12; char *
0x1800cbbb8  mov     rcx, rax; this
0x1800cbbbb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800cbbc0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cbbc7  jb      loc_1800CBACE
0x1800cbbcd  mov     edx, 19h
0x1800cbbd2  jmp     loc_1800CBAB0
0x1800cbbd7  mov     rax, [r14]
0x1800cbbda  mov     rcx, r14
0x1800cbbdd  mov     r8, [rdi+0A0h]
0x1800cbbe4  mov     rdx, [rbp+arg_10]
0x1800cbbe8  mov     rax, [rax+70h]
0x1800cbbec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cbbf1  mov     ebx, eax
0x1800cbbf3  test    eax, eax
0x1800cbbf5  jns     short loc_1800CBC4D
0x1800cbbf7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cbbfe  test    rcx, rcx
0x1800cbc01  jnz     short loc_1800CBC0F
0x1800cbc03  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800cbc08  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800cbc0f  cmp     byte ptr [rcx+8], 0
0x1800cbc13  jz      short loc_1800CBC36
0x1800cbc15  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800cbc1a  cmp     [rax+7CCh], ebx
0x1800cbc20  jz      short loc_1800CBC36
0x1800cbc22  mov     r9d, ebx; int
0x1800cbc25  mov     r8d, 6Ch ; 'l'; int
0x1800cbc2b  mov     rdx, r12; char *
0x1800cbc2e  mov     rcx, rax; this
0x1800cbc31  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800cbc36  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cbc3d  jb      loc_1800CBACE
0x1800cbc43  mov     edx, 1Ah
0x1800cbc48  jmp     loc_1800CBAB0
0x1800cbc4d  mov     rcx, rsi; lpCriticalSection
0x1800cbc50  mov     dword ptr [rdi+0ACh], 0C00D4650h
0x1800cbc5a  call    cs:__imp_LeaveCriticalSection
0x1800cbc60  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 10h; MFWppLevels g_wppLevels
0x1800cbc67  jb      short loc_1800CBC92
0x1800cbc69  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cbc70  mov     edx, 1Ch
0x1800cbc75  mov     rax, [rdi+0A0h]
0x1800cbc7c  mov     r9, rdi
0x1800cbc7f  mov     [rsp+30h+var_8], rax
0x1800cbc84  mov     [rsp+30h+var_10], r14
0x1800cbc89  mov     rcx, [rcx+10h]
0x1800cbc8d  call    WPP_SF_qqI
0x1800cbc92  lea     rcx, [rbp+arg_8]; this
0x1800cbc96  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800cbc9b  lea     rcx, [rbp+arg_10]
0x1800cbc9f  call    ?InternalRelease@?$ComPtr@UIMFDXGISchedulerRegistration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFDXGISchedulerRegistration>::InternalRelease(void)
0x1800cbca4  lea     rcx, [rbp+arg_18]
0x1800cbca8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cbcad  mov     eax, ebx
0x1800cbcaf  mov     rbx, [rsp+30h+arg_0]
0x1800cbcb4  add     rsp, 30h
0x1800cbcb8  pop     r14
0x1800cbcba  pop     r12
0x1800cbcbc  pop     rdi
0x1800cbcbd  pop     rsi
0x1800cbcbe  pop     rbp
0x1800cbcbf  retn
0x1800cbcc0  mov     rax, [r14]
0x1800cbcc3  mov     rcx, r14
0x1800cbcc6  mov     r8, [rdi+0A0h]
0x1800cbccd  mov     rdx, [rdi+80h]
0x1800cbcd4  mov     rax, [rax+70h]
0x1800cbcd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cbcdd  mov     ebx, eax
0x1800cbcdf  test    eax, eax
0x1800cbce1  jns     loc_1800CBC60
0x1800cbce7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cbcee  test    rcx, rcx
0x1800cbcf1  jnz     short loc_1800CBCFF
0x1800cbcf3  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800cbcf8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800cbcff  cmp     byte ptr [rcx+8], 0
0x1800cbd03  jz      short loc_1800CBD26
0x1800cbd05  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800cbd0a  cmp     [rax+7CCh], ebx
0x1800cbd10  jz      short loc_1800CBD26
0x1800cbd12  mov     r9d, ebx; int
0x1800cbd15  mov     r8d, 71h ; 'q'; int
0x1800cbd1b  mov     rdx, r12; char *
0x1800cbd1e  mov     rcx, rax; this
0x1800cbd21  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800cbd26  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cbd2d  jb      loc_1800CBC92
0x1800cbd33  mov     edx, 1Bh
0x1800cbd38  jmp     loc_1800CBA1C
```
