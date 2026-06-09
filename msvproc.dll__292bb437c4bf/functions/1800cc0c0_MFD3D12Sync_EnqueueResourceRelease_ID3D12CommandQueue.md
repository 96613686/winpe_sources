# MFD3D12Sync::EnqueueResourceRelease(ID3D12CommandQueue *)

- ea: `0x1800cc0c0`
- end: `0x1800cc482`
- name: `?EnqueueResourceRelease@MFD3D12Sync@@UEAAJPEAUID3D12CommandQueue@@@Z`
- size: `962`
- prototype: `__int64 __fastcall(MFD3D12Sync *__hidden this, struct ID3D12CommandQueue *)`
- caller_count: `0`
- callee_count: `12`
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
- `0x1800cc0c0`
- `0x1800cded8`
- `0x1800cf1a0`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cc0f5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cc0f5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800cc296`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800cc296`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cc45b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cc45b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cc2a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cc2a9`

## pseudocode

```c
__int64 __fastcall MFD3D12Sync::EnqueueResourceRelease(
        struct _RTL_CRITICAL_SECTION *this,
        struct ID3D12CommandQueue *a2)
{
  CallStackTracing *v4; // rcx
  signed int v5; // ebx
  struct CallStackContext *v6; // rax
  __int64 v7; // rdx
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rdi
  __int64 (__fastcall *v9)(PRTL_CRITICAL_SECTION_DEBUG, _QWORD, __int64, GUID *, __int64); // rbx
  __int64 v10; // rax
  CallStackTracing *v11; // rcx
  struct CallStackContext *v12; // rax
  CallStackTracing *v13; // rcx
  struct CallStackContext *v14; // rax
  void *v15; // rdi
  signed int LastError; // eax
  CallStackTracing *v17; // rcx
  struct CallStackContext *v18; // rax
  CallStackTracing *v19; // rcx
  struct CallStackContext *v20; // rax
  CallStackTracing *v21; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v23; // rax
  void *EventW; // [rsp+70h] [rbp+8h] BYREF
  struct ID3D12Fence *v26; // [rsp+78h] [rbp+10h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&EventW, "MFD3D12Sync::EnqueueResourceRelease", 240);
  EnterCriticalSection(this + 2);
  v26 = 0;
  if ( a2 )
  {
    DebugInfo = this[3].DebugInfo;
    v9 = *(__int64 (__fastcall **)(PRTL_CRITICAL_SECTION_DEBUG, _QWORD, __int64, GUID *, __int64))(*(_QWORD *)&DebugInfo->Type
                                                                                                 + 288LL);
    v10 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ID3D12Fence>>(&v26);
    v5 = v9(DebugInfo, 0, 1, &GUID_0a753dcf_c4d8_4b91_adf6_be5a60d95a76, v10);
    if ( v5 >= 0 )
    {
      v5 = ((__int64 (__fastcall *)(struct ID3D12CommandQueue *, struct ID3D12Fence *, PRTL_CRITICAL_SECTION_DEBUG))a2->lpVtbl->Signal)(
             a2,
             v26,
             this[4].DebugInfo);
      if ( v5 >= 0 )
      {
        EventW = CreateEventW(0, 1, 0, 0);
        v15 = EventW;
        if ( EventW )
          goto LABEL_37;
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
        if ( v5 >= 0 )
        {
LABEL_37:
          v5 = ((__int64 (__fastcall *)(struct ID3D12Fence *, PRTL_CRITICAL_SECTION_DEBUG, void *))v26->lpVtbl->SetEventOnCompletion)(
                 v26,
                 this[4].DebugInfo,
                 v15);
          if ( v5 >= 0 )
          {
            v5 = MFD3D12Sync::ScheduleFreeWait((MFD3D12Sync *)this, &EventW, v26, 0);
            if ( v5 >= 0 )
            {
              if ( g_wppLevels >= 0x20u )
              {
                v23 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)&this[3].LockCount + 64LL))(*(_QWORD *)&this[3].LockCount);
                WPP_SF_qdII(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  57,
                  HIDWORD(this[4].LockSemaphore),
                  this,
                  HIDWORD(this[4].LockSemaphore),
                  this[4].DebugInfo,
                  v23);
              }
            }
            else
            {
              v21 = CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                CallStackTracing::InitInstance();
                v21 = CallStackTracing::s_wpInstance;
              }
              if ( *((_BYTE *)v21 + 8) )
              {
                ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v21);
                if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
                  CallStackContext::TraceFailure(ThreadRelativeContext, "MFD3D12Sync::EnqueueResourceRelease", 254, v5);
              }
              if ( g_wppLevels )
              {
                v7 = 56;
                goto LABEL_9;
              }
            }
          }
          else
          {
            v19 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::InitInstance();
              v19 = CallStackTracing::s_wpInstance;
            }
            if ( *((_BYTE *)v19 + 8) )
            {
              v20 = CallStackTracing::GetThreadRelativeContext(v19);
              if ( *((_DWORD *)v20 + 499) != v5 )
                CallStackContext::TraceFailure(v20, "MFD3D12Sync::EnqueueResourceRelease", 253, v5);
            }
            if ( g_wppLevels )
            {
              v7 = 55;
              goto LABEL_9;
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
            if ( *((_DWORD *)v18 + 499) != v5 )
              CallStackContext::TraceFailure(v18, "MFD3D12Sync::EnqueueResourceRelease", 251, v5);
          }
          if ( g_wppLevels )
          {
            v7 = 54;
            goto LABEL_9;
          }
        }
      }
      else
      {
        v13 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v13 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v13 + 8) )
        {
          v14 = CallStackTracing::GetThreadRelativeContext(v13);
          if ( *((_DWORD *)v14 + 499) != v5 )
            CallStackContext::TraceFailure(v14, "MFD3D12Sync::EnqueueResourceRelease", 246, v5);
        }
        if ( g_wppLevels )
        {
          v7 = 53;
          goto LABEL_9;
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
        if ( *((_DWORD *)v12 + 499) != v5 )
          CallStackContext::TraceFailure(v12, "MFD3D12Sync::EnqueueResourceRelease", 245, v5);
      }
      if ( g_wppLevels )
      {
        v7 = 52;
        goto LABEL_9;
      }
    }
  }
  else
  {
    v4 = CallStackTracing::s_wpInstance;
    v5 = -2147024809;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v4 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v4 + 8) )
    {
      v6 = CallStackTracing::GetThreadRelativeContext(v4);
      if ( *((_DWORD *)v6 + 499) != -2147024809 )
        CallStackContext::TraceFailure(v6, "MFD3D12Sync::EnqueueResourceRelease", 244, -2147024809);
    }
    if ( g_wppLevels )
    {
      v7 = 51;
LABEL_9:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, &WPP_fb0656c5b13f3c5e1eb6232bc9370e01_Traceguids, this, v5);
    }
  }
  Microsoft::WRL::ComPtr<IMFDXGISchedulerRegistration>::InternalRelease(&v26);
  LeaveCriticalSection(this + 2);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&EventW);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800cc0c0  mov     [rsp+arg_10], rbx
0x1800cc0c5  push    rsi
0x1800cc0c6  push    rdi
0x1800cc0c7  push    r13
0x1800cc0c9  push    r14
0x1800cc0cb  push    r15
0x1800cc0cd  sub     rsp, 40h
0x1800cc0d1  mov     r14, rdx
0x1800cc0d4  lea     r13, aMfd3d12syncEnq; "MFD3D12Sync::EnqueueResourceRelease"
0x1800cc0db  mov     rsi, rcx
0x1800cc0de  mov     rdx, r13; char *
0x1800cc0e1  mov     r8d, 0F0h; int
0x1800cc0e7  lea     rcx, [rsp+68h+arg_0]; this
0x1800cc0ec  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800cc0f1  lea     rcx, [rsi+50h]; lpCriticalSection
0x1800cc0f5  call    cs:__imp_EnterCriticalSection
0x1800cc0fb  mov     [rsp+68h+arg_8], 0
0x1800cc104  test    r14, r14
0x1800cc107  jnz     short loc_1800CC182
0x1800cc109  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cc110  mov     ebx, 80070057h
0x1800cc115  test    rcx, rcx
0x1800cc118  jnz     short loc_1800CC126
0x1800cc11a  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800cc11f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800cc126  cmp     byte ptr [rcx+8], 0
0x1800cc12a  jz      short loc_1800CC14D
0x1800cc12c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800cc131  cmp     [rax+7CCh], ebx
0x1800cc137  jz      short loc_1800CC14D
0x1800cc139  mov     r9d, ebx; int
0x1800cc13c  mov     r8d, 0F4h; int
0x1800cc142  mov     rdx, r13; char *
0x1800cc145  mov     rcx, rax; this
0x1800cc148  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800cc14d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cc154  jb      loc_1800CC44D
0x1800cc15a  mov     edx, 33h ; '3'
0x1800cc15f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cc166  lea     r8, WPP_fb0656c5b13f3c5e1eb6232bc9370e01_Traceguids
0x1800cc16d  mov     r9, rsi
0x1800cc170  mov     dword ptr [rsp+68h+var_48], ebx
0x1800cc174  mov     rcx, [rcx+10h]
0x1800cc178  call    WPP_SF_qD
0x1800cc17d  jmp     loc_1800CC44D
0x1800cc182  mov     rdi, [rsi+78h]
0x1800cc186  lea     rcx, [rsp+68h+arg_8]
0x1800cc18b  mov     rax, [rdi]
0x1800cc18e  mov     rbx, [rax+120h]
0x1800cc195  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UID3D12Fence@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UID3D12Fence@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ID3D12Fence>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ID3D12Fence>>)
0x1800cc19a  xor     edx, edx
0x1800cc19c  mov     [rsp+68h+var_48], rax
0x1800cc1a1  lea     r9, _GUID_0a753dcf_c4d8_4b91_adf6_be5a60d95a76
0x1800cc1a8  mov     rcx, rdi
0x1800cc1ab  mov     rax, rbx
0x1800cc1ae  lea     r8d, [rdx+1]
0x1800cc1b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cc1b7  mov     ebx, eax
0x1800cc1b9  test    eax, eax
0x1800cc1bb  jns     short loc_1800CC213
0x1800cc1bd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cc1c4  test    rcx, rcx
0x1800cc1c7  jnz     short loc_1800CC1D5
0x1800cc1c9  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800cc1ce  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800cc1d5  cmp     byte ptr [rcx+8], 0
0x1800cc1d9  jz      short loc_1800CC1FC
0x1800cc1db  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800cc1e0  cmp     [rax+7CCh], ebx
0x1800cc1e6  jz      short loc_1800CC1FC
0x1800cc1e8  mov     r9d, ebx; int
0x1800cc1eb  mov     r8d, 0F5h; int
0x1800cc1f1  mov     rdx, r13; char *
0x1800cc1f4  mov     rcx, rax; this
0x1800cc1f7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800cc1fc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cc203  jb      loc_1800CC44D
0x1800cc209  mov     edx, 34h ; '4'
0x1800cc20e  jmp     loc_1800CC15F
0x1800cc213  mov     rax, [r14]
0x1800cc216  mov     rcx, r14
0x1800cc219  mov     r8, [rsi+0A0h]
0x1800cc220  mov     rdx, [rsp+68h+arg_8]
0x1800cc225  mov     rax, [rax+70h]
0x1800cc229  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cc22e  mov     ebx, eax
0x1800cc230  test    eax, eax
0x1800cc232  jns     short loc_1800CC28A
0x1800cc234  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cc23b  test    rcx, rcx
0x1800cc23e  jnz     short loc_1800CC24C
0x1800cc240  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800cc245  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800cc24c  cmp     byte ptr [rcx+8], 0
0x1800cc250  jz      short loc_1800CC273
0x1800cc252  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800cc257  cmp     [rax+7CCh], ebx
0x1800cc25d  jz      short loc_1800CC273
0x1800cc25f  mov     r9d, ebx; int
0x1800cc262  mov     r8d, 0F6h; int
0x1800cc268  mov     rdx, r13; char *
0x1800cc26b  mov     rcx, rax; this
0x1800cc26e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800cc273  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cc27a  jb      loc_1800CC44D
0x1800cc280  mov     edx, 35h ; '5'
0x1800cc285  jmp     loc_1800CC15F
0x1800cc28a  xor     r9d, r9d; lpName
0x1800cc28d  xor     r8d, r8d; bInitialState
0x1800cc290  xor     ecx, ecx; lpEventAttributes
0x1800cc292  lea     edx, [r9+1]; bManualReset
0x1800cc296  call    cs:__imp_CreateEventW
0x1800cc29c  mov     [rsp+68h+arg_0], rax
0x1800cc2a1  mov     rdi, rax
0x1800cc2a4  test    rax, rax
0x1800cc2a7  jnz     short loc_1800CC318
0x1800cc2a9  call    cs:__imp_GetLastError
0x1800cc2af  mov     ebx, eax
0x1800cc2b1  test    eax, eax
0x1800cc2b3  jle     short loc_1800CC2BE
0x1800cc2b5  movzx   ebx, ax
0x1800cc2b8  or      ebx, 80070000h
0x1800cc2be  test    ebx, ebx
0x1800cc2c0  jns     short loc_1800CC318
0x1800cc2c2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cc2c9  test    rcx, rcx
0x1800cc2cc  jnz     short loc_1800CC2DA
0x1800cc2ce  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800cc2d3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800cc2da  cmp     byte ptr [rcx+8], 0
0x1800cc2de  jz      short loc_1800CC301
0x1800cc2e0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800cc2e5  cmp     [rax+7CCh], ebx
0x1800cc2eb  jz      short loc_1800CC301
0x1800cc2ed  mov     r9d, ebx; int
0x1800cc2f0  mov     r8d, 0FBh; int
0x1800cc2f6  mov     rdx, r13; char *
0x1800cc2f9  mov     rcx, rax; this
0x1800cc2fc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800cc301  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cc308  jb      loc_1800CC44D
0x1800cc30e  mov     edx, 36h ; '6'
0x1800cc313  jmp     loc_1800CC15F
0x1800cc318  mov     rcx, [rsp+68h+arg_8]
0x1800cc31d  mov     r8, rdi
0x1800cc320  mov     rdx, [rsi+0A0h]
0x1800cc327  mov     rax, [rcx]
0x1800cc32a  mov     rax, [rax+48h]
0x1800cc32e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cc333  mov     ebx, eax
0x1800cc335  test    eax, eax
0x1800cc337  jns     short loc_1800CC38F
0x1800cc339  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cc340  test    rcx, rcx
0x1800cc343  jnz     short loc_1800CC351
0x1800cc345  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800cc34a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800cc351  cmp     byte ptr [rcx+8], 0
0x1800cc355  jz      short loc_1800CC378
0x1800cc357  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800cc35c  cmp     [rax+7CCh], ebx
0x1800cc362  jz      short loc_1800CC378
0x1800cc364  mov     r9d, ebx; int
0x1800cc367  mov     r8d, 0FDh; int
0x1800cc36d  mov     rdx, r13; char *
0x1800cc370  mov     rcx, rax; this
0x1800cc373  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800cc378  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cc37f  jb      loc_1800CC44D
0x1800cc385  mov     edx, 37h ; '7'
0x1800cc38a  jmp     loc_1800CC15F
0x1800cc38f  mov     r8, [rsp+68h+arg_8]; struct ID3D12Fence *
0x1800cc394  lea     rdx, [rsp+68h+arg_0]; void **
0x1800cc399  xor     r9d, r9d; struct ID3D11Fence *
0x1800cc39c  mov     rcx, rsi; this
0x1800cc39f  call    ?ScheduleFreeWait@MFD3D12Sync@@IEAAJAEAPEAXPEAUID3D12Fence@@PEAUID3D11Fence@@@Z; MFD3D12Sync::ScheduleFreeWait(void * &,ID3D12Fence *,ID3D11Fence *)
0x1800cc3a4  mov     ebx, eax
0x1800cc3a6  test    eax, eax
0x1800cc3a8  jns     short loc_1800CC3FC
0x1800cc3aa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cc3b1  test    rcx, rcx
0x1800cc3b4  jnz     short loc_1800CC3C2
0x1800cc3b6  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800cc3bb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800cc3c2  cmp     byte ptr [rcx+8], 0
0x1800cc3c6  jz      short loc_1800CC3E9
0x1800cc3c8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800cc3cd  cmp     [rax+7CCh], ebx
0x1800cc3d3  jz      short loc_1800CC3E9
0x1800cc3d5  mov     r9d, ebx; int
0x1800cc3d8  mov     r8d, 0FEh; int
0x1800cc3de  mov     rdx, r13; char *
0x1800cc3e1  mov     rcx, rax; this
0x1800cc3e4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800cc3e9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cc3f0  jb      short loc_1800CC44D
0x1800cc3f2  mov     edx, 38h ; '8'
0x1800cc3f7  jmp     loc_1800CC15F
0x1800cc3fc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 20h ; ' '; MFWppLevels g_wppLevels
0x1800cc403  jb      short loc_1800CC44D
0x1800cc405  mov     rcx, [rsi+80h]
0x1800cc40c  mov     rax, [rcx]
0x1800cc40f  mov     rax, [rax+40h]
0x1800cc413  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cc418  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cc41f  mov     edx, 39h ; '9'
0x1800cc424  mov     r8d, [rsi+0BCh]
0x1800cc42b  mov     r9, rsi
0x1800cc42e  mov     [rsp+68h+var_38], rax
0x1800cc433  mov     rax, [rsi+0A0h]
0x1800cc43a  mov     rcx, [rcx+10h]
0x1800cc43e  mov     [rsp+68h+var_40], rax
0x1800cc443  mov     dword ptr [rsp+68h+var_48], r8d
0x1800cc448  call    WPP_SF_qdII
0x1800cc44d  lea     rcx, [rsp+68h+arg_8]
0x1800cc452  call    ?InternalRelease@?$ComPtr@UIMFDXGISchedulerRegistration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFDXGISchedulerRegistration>::InternalRelease(void)
0x1800cc457  lea     rcx, [rsi+50h]; lpCriticalSection
0x1800cc45b  call    cs:__imp_LeaveCriticalSection
0x1800cc461  lea     rcx, [rsp+68h+arg_0]; this
0x1800cc466  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800cc46b  mov     eax, ebx
0x1800cc46d  mov     rbx, [rsp+68h+arg_10]
0x1800cc475  add     rsp, 40h
0x1800cc479  pop     r15
0x1800cc47b  pop     r14
0x1800cc47d  pop     r13
0x1800cc47f  pop     rdi
0x1800cc480  pop     rsi
0x1800cc481  retn
```
