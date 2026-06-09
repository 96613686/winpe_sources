# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180018b94`
- end: `0x180018c8c`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `248`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180019a20`

## callees

- `0x180018b94`
- `0x180018db0`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180018c03`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180018c03`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180018c20`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180018c20`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018c72`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018c72`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180018bc4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180018bc4`

## string_xrefs

- `0x180018bfc`: `ntdll.dll`
- `0x180018c16`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(
        RTL_SRWLOCK *this,
        struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **a2,
        void (*a3)(void *),
        void *a4)
{
  RTL_SRWLOCK *v8; // rbx
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
0x180018b94  push    rbx
0x180018b96  push    rbp
0x180018b97  push    rsi
0x180018b98  push    rdi
0x180018b99  push    r14
0x180018b9b  push    r15
0x180018b9d  sub     rsp, 38h
0x180018ba1  mov     qword ptr [rdx], 0
0x180018ba8  mov     r15, r9
0x180018bab  cmp     byte ptr [rcx], 0
0x180018bae  mov     rbp, r8
0x180018bb1  mov     r14, rdx
0x180018bb4  mov     rdi, rcx
0x180018bb7  jz      loc_180018C7E
0x180018bbd  lea     rbx, [rcx+20h]
0x180018bc1  mov     rcx, rbx; SRWLock
0x180018bc4  call    cs:__imp_AcquireSRWLockExclusive
0x180018bcb  nop     dword ptr [rax+rax+00h]
0x180018bd0  lea     rsi, [rdi+90h]
0x180018bd7  cmp     qword ptr [rsi], 0
0x180018bdb  jnz     short loc_180018C58
0x180018bdd  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180018be4  mov     qword ptr [rsi], 0
0x180018beb  test    rax, rax
0x180018bee  jnz     short loc_180018C3F
0x180018bf0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180018bf7  test    rax, rax
0x180018bfa  jnz     short loc_180018C16
0x180018bfc  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180018c03  call    cs:__imp_GetModuleHandleW
0x180018c0a  nop     dword ptr [rax+rax+00h]
0x180018c0f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180018c16  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x180018c1d  mov     rcx, rax; hModule
0x180018c20  call    cs:__imp_GetProcAddress
0x180018c27  nop     dword ptr [rax+rax+00h]
0x180018c2c  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x180018c33  test    rax, rax
0x180018c36  jnz     short loc_180018C3F
0x180018c38  mov     eax, 0C0000139h
0x180018c3d  jmp     short loc_180018C54
0x180018c3f  mov     r9, rsi
0x180018c42  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x180018c49  xor     r8d, r8d
0x180018c4c  mov     rdx, rdi
0x180018c4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018c54  test    eax, eax
0x180018c56  jnz     short loc_180018C6A
0x180018c58  lea     rcx, [rdi+48h]; this
0x180018c5c  mov     r9, r15; void *
0x180018c5f  mov     r8, rbp; void (*)(void *)
0x180018c62  mov     rdx, r14; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180018c65  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180018c6a  test    rbx, rbx
0x180018c6d  jz      short loc_180018C7E
0x180018c6f  mov     rcx, rbx; SRWLock
0x180018c72  call    cs:__imp_ReleaseSRWLockExclusive
0x180018c79  nop     dword ptr [rax+rax+00h]
0x180018c7e  add     rsp, 38h
0x180018c82  pop     r15
0x180018c84  pop     r14
0x180018c86  pop     rdi
0x180018c87  pop     rsi
0x180018c88  pop     rbp
0x180018c89  pop     rbx
0x180018c8a  retn
```
