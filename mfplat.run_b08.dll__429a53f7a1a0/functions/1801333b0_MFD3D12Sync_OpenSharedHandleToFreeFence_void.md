# MFD3D12Sync::OpenSharedHandleToFreeFence(void * *)

- ea: `0x1801333b0`
- end: `0x18013380c`
- name: `?OpenSharedHandleToFreeFence@MFD3D12Sync@@UEAAJPEAPEAX@Z`
- size: `1116`
- prototype: `__int64 __fastcall(MFD3D12Sync *__hidden this, void **)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180004870`
- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x1801333b0`
- `0x180134114`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801333e1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801333e1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801337e9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801337e9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801335a1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801335a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801335b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801335b8`

## string_xrefs

- `0x1801333c6`: `MFD3D12Sync::OpenSharedHandleToFreeFence`
- `0x1801334a1`: `MFD3D12Sync::OpenSharedHandleToFreeFence`
- `0x180133569`: `MFD3D12Sync::OpenSharedHandleToFreeFence`
- `0x180133635`: `MFD3D12Sync::OpenSharedHandleToFreeFence`
- `0x1801336e9`: `MFD3D12Sync::OpenSharedHandleToFreeFence`
- `0x180133797`: `MFD3D12Sync::OpenSharedHandleToFreeFence`

## pseudocode

```c
__int64 __fastcall MFD3D12Sync::OpenSharedHandleToFreeFence(MFD3D12Sync *this, void **a2)
{
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, _QWORD, __int64, GUID *, struct ID3D12Fence **); // rbx
  signed int v6; // ebx
  CallStackTracing *v7; // rcx
  struct CallStackContext *v8; // rax
  __int64 v9; // rdx
  CallStackTracing *v10; // rcx
  struct CallStackContext *v11; // rax
  void *v12; // rdi
  signed int LastError; // eax
  CallStackTracing *v14; // rcx
  struct CallStackContext *v15; // rax
  CallStackTracing *v16; // rcx
  struct CallStackContext *v17; // rax
  CallStackTracing *v18; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  HANDLE EventW; // [rsp+70h] [rbp+8h] BYREF
  struct ID3D12Fence *v22; // [rsp+80h] [rbp+18h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&EventW,
    "MFD3D12Sync::OpenSharedHandleToFreeFence",
    163);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  v22 = 0;
  v4 = *((_QWORD *)this + 13);
  v5 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, GUID *, struct ID3D12Fence **))(*(_QWORD *)v4 + 288LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
  v6 = v5(v4, 0, 1, &GUID_0a753dcf_c4d8_4b91_adf6_be5a60d95a76, &v22);
  if ( v6 >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(_QWORD, struct ID3D12Fence *, _QWORD, __int64, _QWORD, void **))(**((_QWORD **)this + 13) + 248LL))(
           *((_QWORD *)this + 13),
           v22,
           0,
           0x10000000,
           0,
           a2);
    if ( v6 >= 0 )
    {
      EventW = CreateEventW(0, 1, 0, 0);
      v12 = EventW;
      if ( EventW )
        goto LABEL_34;
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( v6 >= 0 )
      {
LABEL_34:
        v6 = ((__int64 (__fastcall *)(struct ID3D12Fence *, _QWORD, void *))v22->lpVtbl->SetEventOnCompletion)(
               v22,
               *((_QWORD *)this + 18),
               v12);
        if ( v6 >= 0 )
        {
          v6 = MFD3D12Sync::ScheduleFreeWait((MFD3D12Sync *)((char *)this - 16), &EventW, v22, 0);
          if ( v6 < 0 )
          {
            v18 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::s_wpInstance = &stru_1801FC290;
              if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
              {
                v18 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v18 = &stru_1801F8A30;
                CallStackTracing::s_wpInstance = &stru_1801F8A30;
              }
            }
            if ( v18->m_fEnabled )
            {
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v18);
              if ( ThreadRelativeContext->m_result != v6 )
                CallStackContext::TraceFailure(
                  ThreadRelativeContext,
                  "MFD3D12Sync::OpenSharedHandleToFreeFence",
                  175,
                  v6);
            }
            if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
            {
              v9 = 42;
              goto LABEL_54;
            }
          }
        }
        else
        {
          v16 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v16 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v16 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v16->m_fEnabled )
          {
            v17 = CallStackTracing::GetThreadRelativeContext(v16);
            if ( v17->m_result != v6 )
              CallStackContext::TraceFailure(v17, "MFD3D12Sync::OpenSharedHandleToFreeFence", 174, v6);
          }
          if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
          {
            v9 = 41;
            goto LABEL_54;
          }
        }
      }
      else
      {
        v14 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v14 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v14 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        if ( v14->m_fEnabled )
        {
          v15 = CallStackTracing::GetThreadRelativeContext(v14);
          if ( v15->m_result != v6 )
            CallStackContext::TraceFailure(v15, "MFD3D12Sync::OpenSharedHandleToFreeFence", 172, v6);
        }
        if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
        {
          v9 = 40;
          goto LABEL_54;
        }
      }
    }
    else
    {
      v10 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v10 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v10 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v10->m_fEnabled )
      {
        v11 = CallStackTracing::GetThreadRelativeContext(v10);
        if ( v11->m_result != v6 )
          CallStackContext::TraceFailure(v11, "MFD3D12Sync::OpenSharedHandleToFreeFence", 168, v6);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v9 = 39;
        goto LABEL_54;
      }
    }
  }
  else
  {
    v7 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v7 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v7->m_fEnabled )
    {
      v8 = CallStackTracing::GetThreadRelativeContext(v7);
      if ( v8->m_result != v6 )
        CallStackContext::TraceFailure(v8, "MFD3D12Sync::OpenSharedHandleToFreeFence", 167, v6);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v9 = 38;
LABEL_54:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v9,
        &WPP_fb0656c5b13f3c5e1eb6232bc9370e01_Traceguids,
        (char *)this - 16,
        v6);
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&EventW);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1801333b0  mov     [rsp+arg_8], rbx
0x1801333b5  push    rbp
0x1801333b6  push    rsi
0x1801333b7  push    rdi
0x1801333b8  push    r14
0x1801333ba  push    r15
0x1801333bc  sub     rsp, 40h
0x1801333c0  mov     r14, rdx
0x1801333c3  mov     rbp, rcx
0x1801333c6  lea     rdx, aMfd3d12syncOpe; "MFD3D12Sync::OpenSharedHandleToFreeFenc"...
0x1801333cd  mov     r8d, 0A3h; int
0x1801333d3  lea     rcx, [rsp+68h+arg_0]; this
0x1801333d8  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1801333dd  lea     rcx, [rbp+40h]; lpCriticalSection
0x1801333e1  call    cs:__imp_EnterCriticalSection
0x1801333e7  mov     [rsp+68h+arg_10], 0
0x1801333f3  lea     rsi, [rbp-10h]
0x1801333f7  mov     rdi, [rsi+78h]
0x1801333fb  lea     rcx, [rsp+68h+arg_10]
0x180133403  mov     rax, [rdi]
0x180133406  mov     rbx, [rax+120h]
0x18013340d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180133412  xor     edx, edx
0x180133414  lea     rax, [rsp+68h+arg_10]
0x18013341c  mov     [rsp+68h+var_48], rax
0x180133421  lea     r9, _GUID_0a753dcf_c4d8_4b91_adf6_be5a60d95a76
0x180133428  mov     rcx, rdi
0x18013342b  mov     rax, rbx
0x18013342e  lea     r8d, [rdx+1]
0x180133432  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180133437  mov     ebx, eax
0x180133439  test    eax, eax
0x18013343b  jns     loc_1801334CD
0x180133441  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180133448  test    rcx, rcx
0x18013344b  jnz     short loc_18013348B
0x18013344d  mov     rax, cs:stru_1801FC290.__vftable
0x180133454  lea     rcx, stru_1801FC290
0x18013345b  mov     edx, 7F0h
0x180133460  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180133467  mov     rax, [rax+8]
0x18013346b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180133470  test    eax, eax
0x180133472  jnz     short loc_180133484
0x180133474  lea     rcx, stru_1801F8A30
0x18013347b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180133482  jmp     short loc_18013348B
0x180133484  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18013348b  cmp     byte ptr [rcx+8], 0
0x18013348f  jz      short loc_1801334B6
0x180133491  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180133496  cmp     [rax+7CCh], ebx
0x18013349c  jz      short loc_1801334B6
0x18013349e  mov     r9d, ebx; int
0x1801334a1  lea     rdx, aMfd3d12syncOpe; "MFD3D12Sync::OpenSharedHandleToFreeFenc"...
0x1801334a8  mov     r8d, 0A7h; int
0x1801334ae  mov     rcx, rax; this
0x1801334b1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801334b6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801334bd  jb      loc_1801337D8
0x1801334c3  mov     edx, 26h ; '&'
0x1801334c8  jmp     loc_1801337BA
0x1801334cd  mov     rcx, [rsi+78h]
0x1801334d1  mov     r9d, 10000000h
0x1801334d7  mov     rdx, [rsp+68h+arg_10]
0x1801334df  xor     r8d, r8d
0x1801334e2  mov     [rsp+68h+var_40], r14
0x1801334e7  mov     [rsp+68h+var_48], 0
0x1801334f0  mov     rax, [rcx]
0x1801334f3  mov     rax, [rax+0F8h]
0x1801334fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801334ff  mov     ebx, eax
0x180133501  test    eax, eax
0x180133503  jns     loc_180133595
0x180133509  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180133510  test    rcx, rcx
0x180133513  jnz     short loc_180133553
0x180133515  mov     rax, cs:stru_1801FC290.__vftable
0x18013351c  lea     rcx, stru_1801FC290
0x180133523  mov     edx, 7F0h
0x180133528  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18013352f  mov     rax, [rax+8]
0x180133533  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180133538  test    eax, eax
0x18013353a  jnz     short loc_18013354C
0x18013353c  lea     rcx, stru_1801F8A30
0x180133543  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18013354a  jmp     short loc_180133553
0x18013354c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180133553  cmp     byte ptr [rcx+8], 0
0x180133557  jz      short loc_18013357E
0x180133559  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18013355e  cmp     [rax+7CCh], ebx
0x180133564  jz      short loc_18013357E
0x180133566  mov     r9d, ebx; int
0x180133569  lea     rdx, aMfd3d12syncOpe; "MFD3D12Sync::OpenSharedHandleToFreeFenc"...
0x180133570  mov     r8d, 0A8h; int
0x180133576  mov     rcx, rax; this
0x180133579  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18013357e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180133585  jb      loc_1801337D8
0x18013358b  mov     edx, 27h ; '''
0x180133590  jmp     loc_1801337BA
0x180133595  xor     r9d, r9d; lpName
0x180133598  xor     r8d, r8d; bInitialState
0x18013359b  xor     ecx, ecx; lpEventAttributes
0x18013359d  lea     edx, [r9+1]; bManualReset
0x1801335a1  call    cs:__imp_CreateEventW
0x1801335a7  mov     [rsp+68h+arg_0], rax
0x1801335ac  mov     rdi, rax
0x1801335af  test    rax, rax
0x1801335b2  jnz     loc_180133661
0x1801335b8  call    cs:__imp_GetLastError
0x1801335be  mov     ebx, eax
0x1801335c0  test    eax, eax
0x1801335c2  jle     short loc_1801335CD
0x1801335c4  movzx   ebx, ax
0x1801335c7  or      ebx, 80070000h
0x1801335cd  test    ebx, ebx
0x1801335cf  jns     loc_180133661
0x1801335d5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801335dc  test    rcx, rcx
0x1801335df  jnz     short loc_18013361F
0x1801335e1  mov     rax, cs:stru_1801FC290.__vftable
0x1801335e8  lea     rcx, stru_1801FC290
0x1801335ef  mov     edx, 7F0h
0x1801335f4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801335fb  mov     rax, [rax+8]
0x1801335ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180133604  test    eax, eax
0x180133606  jnz     short loc_180133618
0x180133608  lea     rcx, stru_1801F8A30
0x18013360f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180133616  jmp     short loc_18013361F
0x180133618  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18013361f  cmp     byte ptr [rcx+8], 0
0x180133623  jz      short loc_18013364A
0x180133625  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18013362a  cmp     [rax+7CCh], ebx
0x180133630  jz      short loc_18013364A
0x180133632  mov     r9d, ebx; int
0x180133635  lea     rdx, aMfd3d12syncOpe; "MFD3D12Sync::OpenSharedHandleToFreeFenc"...
0x18013363c  mov     r8d, 0ACh; int
0x180133642  mov     rcx, rax; this
0x180133645  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18013364a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180133651  jb      loc_1801337D8
0x180133657  mov     edx, 28h ; '('
0x18013365c  jmp     loc_1801337BA
0x180133661  mov     rcx, [rsp+68h+arg_10]
0x180133669  mov     r8, rdi
0x18013366c  mov     rdx, [rbp+90h]
0x180133673  mov     rax, [rcx]
0x180133676  mov     rax, [rax+48h]
0x18013367a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013367f  mov     ebx, eax
0x180133681  test    eax, eax
0x180133683  jns     loc_180133715
0x180133689  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180133690  test    rcx, rcx
0x180133693  jnz     short loc_1801336D3
0x180133695  mov     rax, cs:stru_1801FC290.__vftable
0x18013369c  lea     rcx, stru_1801FC290
0x1801336a3  mov     edx, 7F0h
0x1801336a8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801336af  mov     rax, [rax+8]
0x1801336b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801336b8  test    eax, eax
0x1801336ba  jnz     short loc_1801336CC
0x1801336bc  lea     rcx, stru_1801F8A30
0x1801336c3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801336ca  jmp     short loc_1801336D3
0x1801336cc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1801336d3  cmp     byte ptr [rcx+8], 0
0x1801336d7  jz      short loc_1801336FE
0x1801336d9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801336de  cmp     [rax+7CCh], ebx
0x1801336e4  jz      short loc_1801336FE
0x1801336e6  mov     r9d, ebx; int
0x1801336e9  lea     rdx, aMfd3d12syncOpe; "MFD3D12Sync::OpenSharedHandleToFreeFenc"...
0x1801336f0  mov     r8d, 0AEh; int
0x1801336f6  mov     rcx, rax; this
0x1801336f9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801336fe  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180133705  jb      loc_1801337D8
0x18013370b  mov     edx, 29h ; ')'
0x180133710  jmp     loc_1801337BA
0x180133715  mov     r8, [rsp+68h+arg_10]; struct ID3D12Fence *
0x18013371d  lea     rdx, [rsp+68h+arg_0]; void **
0x180133722  xor     r9d, r9d; struct ID3D11Fence *
0x180133725  mov     rcx, rsi; this
0x180133728  call    ?ScheduleFreeWait@MFD3D12Sync@@IEAAJAEAPEAXPEAUID3D12Fence@@PEAUID3D11Fence@@@Z; MFD3D12Sync::ScheduleFreeWait(void * &,ID3D12Fence *,ID3D11Fence *)
0x18013372d  mov     ebx, eax
0x18013372f  test    eax, eax
0x180133731  jns     loc_1801337D8
0x180133737  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013373e  test    rcx, rcx
0x180133741  jnz     short loc_180133781
0x180133743  mov     rax, cs:stru_1801FC290.__vftable
0x18013374a  lea     rcx, stru_1801FC290
0x180133751  mov     edx, 7F0h
0x180133756  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18013375d  mov     rax, [rax+8]
0x180133761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180133766  test    eax, eax
0x180133768  jnz     short loc_18013377A
0x18013376a  lea     rcx, stru_1801F8A30
0x180133771  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180133778  jmp     short loc_180133781
0x18013377a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180133781  cmp     byte ptr [rcx+8], 0
0x180133785  jz      short loc_1801337AC
0x180133787  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18013378c  cmp     [rax+7CCh], ebx
0x180133792  jz      short loc_1801337AC
0x180133794  mov     r9d, ebx; int
0x180133797  lea     rdx, aMfd3d12syncOpe; "MFD3D12Sync::OpenSharedHandleToFreeFenc"...
0x18013379e  mov     r8d, 0AFh; int
0x1801337a4  mov     rcx, rax; this
0x1801337a7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801337ac  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801337b3  jb      short loc_1801337D8
0x1801337b5  mov     edx, 2Ah ; '*'
0x1801337ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1801337c1  lea     r8, WPP_fb0656c5b13f3c5e1eb6232bc9370e01_Traceguids
0x1801337c8  mov     r9, rsi
0x1801337cb  mov     dword ptr [rsp+68h+var_48], ebx
0x1801337cf  mov     rcx, [rcx+10h]
0x1801337d3  call    WPP_SF_qD
0x1801337d8  lea     rcx, [rsp+68h+arg_10]
0x1801337e0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801337e5  lea     rcx, [rbp+40h]; lpCriticalSection
0x1801337e9  call    cs:__imp_LeaveCriticalSection
0x1801337ef  lea     rcx, [rsp+68h+arg_0]; this
0x1801337f4  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1801337f9  mov     eax, ebx
0x1801337fb  mov     rbx, [rsp+68h+arg_8]
0x180133800  add     rsp, 40h
0x180133804  pop     r15
0x180133806  pop     r14
0x180133808  pop     rdi
0x180133809  pop     rsi
0x18013380a  pop     rbp
0x18013380b  retn
```
