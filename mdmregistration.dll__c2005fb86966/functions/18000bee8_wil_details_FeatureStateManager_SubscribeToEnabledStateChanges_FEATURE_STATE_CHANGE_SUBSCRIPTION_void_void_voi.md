# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000bee8`
- end: `0x18000bfe0`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `248`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000c8a0`

## callees

- `0x18000bee8`
- `0x18000c0fc`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000bf57`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000bf57`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000bf74`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000bf74`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000bf18`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000bf18`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000bfc6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000bfc6`

## string_xrefs

- `0x18000bf50`: `ntdll.dll`
- `0x18000bf6a`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(
        RTL_SRWLOCK *this,
        struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **a2,
        void (*a3)(void *),
        void *a4)
{
  RTL_SRWLOCK *v8; // rdi
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v11; // eax

  *a2 = 0;
  if ( LOBYTE(this->Ptr) )
  {
    v8 = this + 4;
    AcquireSRWLockExclusive(this + 4);
    if ( this[18].Ptr )
      goto LABEL_10;
    ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
    this[18].Ptr = 0;
    if ( ProcAddress )
      goto LABEL_8;
    ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
    if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
    {
      ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
      `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
    }
    ProcAddress = GetProcAddress(ModuleHandleW, "RtlRegisterFeatureConfigurationChangeNotification");
    g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification = (__int64)ProcAddress;
    if ( ProcAddress )
LABEL_8:
      v11 = ((__int64 (__fastcall *)(__int64 (__fastcall *)(void *), RTL_SRWLOCK *, _QWORD, RTL_SRWLOCK *))ProcAddress)(
              _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_,
              this,
              0,
              &this[18]);
    else
      v11 = -1073741511;
    if ( !v11 )
LABEL_10:
      wil::details_abi::SubscriptionList::SubscribeUnderLock((wil::details_abi::SubscriptionList *)&this[9], a2, a3, a4);
    if ( v8 )
      ReleaseSRWLockExclusive(v8);
  }
}

```

## disassembly

```asm
0x18000bee8  push    rbx
0x18000beea  push    rbp
0x18000beeb  push    rsi
0x18000beec  push    rdi
0x18000beed  push    r14
0x18000beef  push    r15
0x18000bef1  sub     rsp, 38h
0x18000bef5  mov     qword ptr [rdx], 0
0x18000befc  mov     rbp, r9
0x18000beff  cmp     byte ptr [rcx], 0
0x18000bf02  mov     r15, r8
0x18000bf05  mov     r14, rdx
0x18000bf08  mov     rbx, rcx
0x18000bf0b  jz      loc_18000BFD2
0x18000bf11  lea     rdi, [rcx+20h]
0x18000bf15  mov     rcx, rdi; SRWLock
0x18000bf18  call    cs:__imp_AcquireSRWLockExclusive
0x18000bf1f  nop     dword ptr [rax+rax+00h]
0x18000bf24  lea     rsi, [rbx+90h]
0x18000bf2b  cmp     qword ptr [rsi], 0
0x18000bf2f  jnz     short loc_18000BFAC
0x18000bf31  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000bf38  mov     qword ptr [rsi], 0
0x18000bf3f  test    rax, rax
0x18000bf42  jnz     short loc_18000BF93
0x18000bf44  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000bf4b  test    rax, rax
0x18000bf4e  jnz     short loc_18000BF6A
0x18000bf50  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18000bf57  call    cs:__imp_GetModuleHandleW
0x18000bf5e  nop     dword ptr [rax+rax+00h]
0x18000bf63  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000bf6a  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000bf71  mov     rcx, rax; hModule
0x18000bf74  call    cs:__imp_GetProcAddress
0x18000bf7b  nop     dword ptr [rax+rax+00h]
0x18000bf80  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000bf87  test    rax, rax
0x18000bf8a  jnz     short loc_18000BF93
0x18000bf8c  mov     eax, 0C0000139h
0x18000bf91  jmp     short loc_18000BFA8
0x18000bf93  mov     r9, rsi
0x18000bf96  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18000bf9d  xor     r8d, r8d
0x18000bfa0  mov     rdx, rbx
0x18000bfa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfa8  test    eax, eax
0x18000bfaa  jnz     short loc_18000BFBE
0x18000bfac  lea     rcx, [rbx+48h]; this
0x18000bfb0  mov     r9, rbp; void *
0x18000bfb3  mov     r8, r15; void (*)(void *)
0x18000bfb6  mov     rdx, r14; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000bfb9  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18000bfbe  test    rdi, rdi
0x18000bfc1  jz      short loc_18000BFD2
0x18000bfc3  mov     rcx, rdi; SRWLock
0x18000bfc6  call    cs:__imp_ReleaseSRWLockExclusive
0x18000bfcd  nop     dword ptr [rax+rax+00h]
0x18000bfd2  add     rsp, 38h
0x18000bfd6  pop     r15
0x18000bfd8  pop     r14
0x18000bfda  pop     rdi
0x18000bfdb  pop     rsi
0x18000bfdc  pop     rbp
0x18000bfdd  pop     rbx
0x18000bfde  retn
```
