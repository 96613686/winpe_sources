# MFD3D12Sync::ScheduleFreeWait(void * &,ID3D12Fence *,ID3D11Fence *)

- ea: `0x1800cded8`
- end: `0x1800ce18c`
- name: `?ScheduleFreeWait@MFD3D12Sync@@IEAAJAEAPEAXPEAUID3D12Fence@@PEAUID3D11Fence@@@Z`
- size: `692`
- prototype: `int(MFD3D12Sync *__hidden this, void **, struct ID3D12Fence *, struct ID3D11Fence *)`
- caller_count: `4`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1800cc0c0`
- `0x1800cc6d0`
- `0x1800cd3b0`
- `0x1800ce600`

## callees

- `0x18000a09c`
- `0x18000a954`
- `0x18000c9d0`
- `0x18000caec`
- `0x18000ec20`
- `0x18000ecf0`
- `0x18001b3c4`
- `0x18003639c`
- `0x180053bfc`
- `0x1800cb3fc`
- `0x1800cc644`
- `0x1800cded8`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ce144`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ce144`
- `RTWorkQ!RtwqPutWaitingWorkItem` at `0x1800ce054`
- `RTWorkQ!RtwqPutWaitingWorkItem` at `0x1800ce054`
- `RTWorkQ!RtwqCreateAsyncResult` at `0x1800cdfe5`
- `RTWorkQ!RtwqCreateAsyncResult` at `0x1800cdfe5`

## pseudocode

```c
__int64 __fastcall MFD3D12Sync::ScheduleFreeWait(
        IRtwqAsyncCallback *this,
        RTWQWORKITEM_KEY *a2,
        IUnknown *a3,
        struct ID3D11Fence *a4)
{
  RTWQWORKITEM_KEY *v8; // rdi
  unsigned int v9; // edx
  CallStackTracing *v10; // rcx
  HRESULT v11; // ebx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v13; // rdx
  CallStackTracing *v14; // rcx
  struct CallStackContext *v15; // rax
  CallStackTracing *v16; // rcx
  struct CallStackContext *v17; // rax
  CallStackTracing *v18; // rcx
  struct CallStackContext *v19; // rax
  char v21[8]; // [rsp+30h] [rbp-20h] BYREF
  IRtwqAsyncResult *asyncResult; // [rsp+38h] [rbp-18h] BYREF
  MFD3D12Sync::QueuedFreeWait *v23; // [rsp+40h] [rbp-10h] BYREF
  IUnknown *v24; // [rsp+90h] [rbp+40h] BYREF

  v24 = a3;
  asyncResult = 0;
  v8 = (RTWQWORKITEM_KEY *)operator new(0x20u);
  if ( v8 )
  {
    *v8 = *a2;
    v8[1] = (RTWQWORKITEM_KEY)a3;
    Microsoft::WRL::ComPtr<IMFMediaBuffer>::InternalAddRef(v8 + 1);
    v8[2] = (RTWQWORKITEM_KEY)a4;
    if ( a4 )
      ((void (__fastcall *)(struct ID3D11Fence *))a4->lpVtbl->AddRef)(a4);
  }
  else
  {
    v8 = 0;
  }
  v23 = (MFD3D12Sync::QueuedFreeWait *)v8;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v21, "MFD3D12Sync::ScheduleFreeWait", 206);
  if ( !v8 )
  {
    v10 = CallStackTracing::s_wpInstance;
    v11 = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v10 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v10);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024882 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "MFD3D12Sync::ScheduleFreeWait", 206, -2147024882);
    }
    if ( !g_wppLevels )
      goto LABEL_38;
    v13 = 44;
    goto LABEL_37;
  }
  *a2 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&asyncResult);
  v11 = RtwqCreateAsyncResult(a3, this + 3, 0, &asyncResult);
  if ( v11 < 0 )
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
      if ( *((_DWORD *)v15 + 499) != v11 )
        CallStackContext::TraceFailure(v15, "MFD3D12Sync::ScheduleFreeWait", 217, v11);
    }
    if ( !g_wppLevels )
      goto LABEL_38;
    v13 = 47;
    goto LABEL_37;
  }
  v11 = RtwqPutWaitingWorkItem((HANDLE)*v8, 0, asyncResult, v8 + 3);
  if ( v11 < 0 )
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
      if ( *((_DWORD *)v17 + 499) != v11 )
        CallStackContext::TraceFailure(v17, "MFD3D12Sync::ScheduleFreeWait", 218, v11);
    }
    if ( !g_wppLevels )
      goto LABEL_38;
    v13 = 48;
    goto LABEL_37;
  }
  v11 = CTBucketHash<ID3D12Fence *,MFD3D12Sync::QueuedFreeWait *>::Insert(&this[7].GetParameters, &v24, &v23);
  if ( v11 >= 0 )
    goto LABEL_42;
  v18 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v18 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v18 + 8) )
  {
    v19 = CallStackTracing::GetThreadRelativeContext(v18);
    if ( *((_DWORD *)v19 + 499) != v11 )
      CallStackContext::TraceFailure(v19, "MFD3D12Sync::ScheduleFreeWait", 221, v11);
  }
  if ( g_wppLevels )
  {
    v13 = 49;
LABEL_37:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_fb0656c5b13f3c5e1eb6232bc9370e01_Traceguids, this, v11);
  }
LABEL_38:
  if ( *a2 )
  {
    CloseHandle((HANDLE)*a2);
    *a2 = 0;
  }
  if ( v23 )
    MFD3D12Sync::QueuedFreeWait::`scalar deleting destructor'(v23, v9);
LABEL_42:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v21);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&asyncResult);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800cded8  mov     [rsp-28h+arg_0], rbx
0x1800cdedd  mov     [rsp-28h+arg_8], rsi
0x1800cdee2  mov     [rsp-28h+arg_10], r8
0x1800cdee7  push    rbp
0x1800cdee8  push    rdi
0x1800cdee9  push    r13
0x1800cdeeb  push    r14
0x1800cdeed  push    r15
0x1800cdeef  mov     rbp, rsp
0x1800cdef2  sub     rsp, 50h
0x1800cdef6  mov     r14, rcx
0x1800cdef9  mov     [rbp+asyncResult], 0
0x1800cdf01  mov     ecx, 20h ; ' '; Size
0x1800cdf06  mov     rbx, r9
0x1800cdf09  mov     rsi, r8
0x1800cdf0c  mov     r15, rdx
0x1800cdf0f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800cdf14  mov     rdi, rax
0x1800cdf17  test    rax, rax
0x1800cdf1a  jz      short loc_1800CDF48
0x1800cdf1c  mov     rax, [r15]
0x1800cdf1f  lea     rcx, [rdi+8]
0x1800cdf23  mov     [rdi], rax
0x1800cdf26  mov     [rcx], rsi
0x1800cdf29  call    ?InternalAddRef@?$ComPtr@UIMFMediaBuffer@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IMFMediaBuffer>::InternalAddRef(void)
0x1800cdf2e  mov     [rdi+10h], rbx
0x1800cdf32  test    rbx, rbx
0x1800cdf35  jz      short loc_1800CDF4A
0x1800cdf37  mov     rax, [rbx]
0x1800cdf3a  mov     rcx, rbx
0x1800cdf3d  mov     rax, [rax+8]
0x1800cdf41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cdf46  jmp     short loc_1800CDF4A
0x1800cdf48  xor     edi, edi
0x1800cdf4a  lea     r13, aMfd3d12syncSch; "MFD3D12Sync::ScheduleFreeWait"
0x1800cdf51  mov     [rbp+var_10], rdi
0x1800cdf55  mov     rdx, r13; char *
0x1800cdf58  lea     rcx, [rbp+var_20]; this
0x1800cdf5c  mov     r8d, 0CEh; int
0x1800cdf62  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800cdf67  test    rdi, rdi
0x1800cdf6a  jnz     short loc_1800CDFC7
0x1800cdf6c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cdf73  mov     ebx, 8007000Eh
0x1800cdf78  test    rcx, rcx
0x1800cdf7b  jnz     short loc_1800CDF89
0x1800cdf7d  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800cdf82  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800cdf89  cmp     byte ptr [rcx+8], 0
0x1800cdf8d  jz      short loc_1800CDFB0
0x1800cdf8f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800cdf94  cmp     [rax+7CCh], ebx
0x1800cdf9a  jz      short loc_1800CDFB0
0x1800cdf9c  mov     r9d, ebx; int
0x1800cdf9f  mov     r8d, 0CEh; int
0x1800cdfa5  mov     rdx, r13; char *
0x1800cdfa8  mov     rcx, rax; this
0x1800cdfab  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800cdfb0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cdfb7  jb      loc_1800CE13C
0x1800cdfbd  mov     edx, 2Ch ; ','
0x1800cdfc2  jmp     loc_1800CE11E
0x1800cdfc7  lea     rcx, [rbp+asyncResult]
0x1800cdfcb  mov     qword ptr [r15], 0
0x1800cdfd2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cdfd7  lea     rdx, [r14+48h]; callback
0x1800cdfdb  xor     r8d, r8d; appState
0x1800cdfde  lea     r9, [rbp+asyncResult]; asyncResult
0x1800cdfe2  mov     rcx, rsi; appObject
0x1800cdfe5  call    cs:__imp_RtwqCreateAsyncResult
0x1800cdfeb  mov     ebx, eax
0x1800cdfed  test    eax, eax
0x1800cdfef  jns     short loc_1800CE047
0x1800cdff1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cdff8  test    rcx, rcx
0x1800cdffb  jnz     short loc_1800CE009
0x1800cdffd  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800ce002  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800ce009  cmp     byte ptr [rcx+8], 0
0x1800ce00d  jz      short loc_1800CE030
0x1800ce00f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ce014  cmp     [rax+7CCh], ebx
0x1800ce01a  jz      short loc_1800CE030
0x1800ce01c  mov     r9d, ebx; int
0x1800ce01f  mov     r8d, 0D9h; int
0x1800ce025  mov     rdx, r13; char *
0x1800ce028  mov     rcx, rax; this
0x1800ce02b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ce030  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ce037  jb      loc_1800CE13C
0x1800ce03d  mov     edx, 2Fh ; '/'
0x1800ce042  jmp     loc_1800CE11E
0x1800ce047  mov     r8, [rbp+asyncResult]; result
0x1800ce04b  lea     r9, [rdi+18h]; key
0x1800ce04f  mov     rcx, [rdi]; hEvent
0x1800ce052  xor     edx, edx; lPriority
0x1800ce054  call    cs:__imp_RtwqPutWaitingWorkItem
0x1800ce05a  mov     ebx, eax
0x1800ce05c  test    eax, eax
0x1800ce05e  jns     short loc_1800CE0B3
0x1800ce060  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ce067  test    rcx, rcx
0x1800ce06a  jnz     short loc_1800CE078
0x1800ce06c  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800ce071  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800ce078  cmp     byte ptr [rcx+8], 0
0x1800ce07c  jz      short loc_1800CE09F
0x1800ce07e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ce083  cmp     [rax+7CCh], ebx
0x1800ce089  jz      short loc_1800CE09F
0x1800ce08b  mov     r9d, ebx; int
0x1800ce08e  mov     r8d, 0DAh; int
0x1800ce094  mov     rdx, r13; char *
0x1800ce097  mov     rcx, rax; this
0x1800ce09a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ce09f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ce0a6  jb      loc_1800CE13C
0x1800ce0ac  mov     edx, 30h ; '0'
0x1800ce0b1  jmp     short loc_1800CE11E
0x1800ce0b3  lea     rcx, [r14+0B0h]
0x1800ce0ba  lea     r8, [rbp+var_10]
0x1800ce0be  lea     rdx, [rbp+arg_10]
0x1800ce0c2  call    ?Insert@?$CTBucketHash@PEAUID3D12Fence@@PEAVQueuedFreeWait@MFD3D12Sync@@@@QEAAJAEBQEAUID3D12Fence@@AEBQEAVQueuedFreeWait@MFD3D12Sync@@@Z; CTBucketHash<ID3D12Fence *,MFD3D12Sync::QueuedFreeWait *>::Insert(ID3D12Fence * const &,MFD3D12Sync::QueuedFreeWait * const &)
0x1800ce0c7  mov     ebx, eax
0x1800ce0c9  test    eax, eax
0x1800ce0cb  jns     loc_1800CE15F
0x1800ce0d1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ce0d8  test    rcx, rcx
0x1800ce0db  jnz     short loc_1800CE0E9
0x1800ce0dd  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800ce0e2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800ce0e9  cmp     byte ptr [rcx+8], 0
0x1800ce0ed  jz      short loc_1800CE110
0x1800ce0ef  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ce0f4  cmp     [rax+7CCh], ebx
0x1800ce0fa  jz      short loc_1800CE110
0x1800ce0fc  mov     r9d, ebx; int
0x1800ce0ff  mov     r8d, 0DDh; int
0x1800ce105  mov     rdx, r13; char *
0x1800ce108  mov     rcx, rax; this
0x1800ce10b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ce110  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ce117  jb      short loc_1800CE13C
0x1800ce119  mov     edx, 31h ; '1'
0x1800ce11e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ce125  lea     r8, WPP_fb0656c5b13f3c5e1eb6232bc9370e01_Traceguids
0x1800ce12c  mov     r9, r14
0x1800ce12f  mov     [rsp+50h+var_30], ebx
0x1800ce133  mov     rcx, [rcx+10h]
0x1800ce137  call    WPP_SF_qD
0x1800ce13c  mov     rcx, [r15]; hObject
0x1800ce13f  test    rcx, rcx
0x1800ce142  jz      short loc_1800CE151
0x1800ce144  call    cs:__imp_CloseHandle
0x1800ce14a  mov     qword ptr [r15], 0
0x1800ce151  mov     rcx, [rbp+var_10]; this
0x1800ce155  test    rcx, rcx
0x1800ce158  jz      short loc_1800CE15F
0x1800ce15a  call    ??_GQueuedFreeWait@MFD3D12Sync@@QEAAPEAXI@Z; MFD3D12Sync::QueuedFreeWait::`scalar deleting destructor'(uint)
0x1800ce15f  lea     rcx, [rbp+var_20]; this
0x1800ce163  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800ce168  lea     rcx, [rbp+asyncResult]
0x1800ce16c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800ce171  lea     r11, [rsp+50h+var_s0]
0x1800ce176  mov     eax, ebx
0x1800ce178  mov     rbx, [r11+30h]
0x1800ce17c  mov     rsi, [r11+38h]
0x1800ce180  mov     rsp, r11
0x1800ce183  pop     r15
0x1800ce185  pop     r14
0x1800ce187  pop     r13
0x1800ce189  pop     rdi
0x1800ce18a  pop     rbp
0x1800ce18b  retn
```
