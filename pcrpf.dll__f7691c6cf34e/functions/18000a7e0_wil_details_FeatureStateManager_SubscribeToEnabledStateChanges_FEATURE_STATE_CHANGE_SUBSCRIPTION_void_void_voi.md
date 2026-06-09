# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000a7e0`
- end: `0x18000a8d8`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `248`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000b190`

## callees

- `0x18000a7e0`
- `0x18000a9f4`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a86c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a86c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a84f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a84f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a810`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a810`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a8be`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a8be`

## string_xrefs

- `0x18000a848`: `ntdll.dll`
- `0x18000a862`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18000a7e0  push    rbx
0x18000a7e2  push    rbp
0x18000a7e3  push    rsi
0x18000a7e4  push    rdi
0x18000a7e5  push    r14
0x18000a7e7  push    r15
0x18000a7e9  sub     rsp, 38h
0x18000a7ed  mov     qword ptr [rdx], 0
0x18000a7f4  mov     rbp, r9
0x18000a7f7  cmp     byte ptr [rcx], 0
0x18000a7fa  mov     r15, r8
0x18000a7fd  mov     r14, rdx
0x18000a800  mov     rbx, rcx
0x18000a803  jz      loc_18000A8CA
0x18000a809  lea     rdi, [rcx+20h]
0x18000a80d  mov     rcx, rdi; SRWLock
0x18000a810  call    cs:__imp_AcquireSRWLockExclusive
0x18000a817  nop     dword ptr [rax+rax+00h]
0x18000a81c  lea     rsi, [rbx+90h]
0x18000a823  cmp     qword ptr [rsi], 0
0x18000a827  jnz     short loc_18000A8A4
0x18000a829  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000a830  mov     qword ptr [rsi], 0
0x18000a837  test    rax, rax
0x18000a83a  jnz     short loc_18000A88B
0x18000a83c  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a843  test    rax, rax
0x18000a846  jnz     short loc_18000A862
0x18000a848  lea     rcx, ModuleName; "ntdll.dll"
0x18000a84f  call    cs:__imp_GetModuleHandleW
0x18000a856  nop     dword ptr [rax+rax+00h]
0x18000a85b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a862  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000a869  mov     rcx, rax; hModule
0x18000a86c  call    cs:__imp_GetProcAddress
0x18000a873  nop     dword ptr [rax+rax+00h]
0x18000a878  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000a87f  test    rax, rax
0x18000a882  jnz     short loc_18000A88B
0x18000a884  mov     eax, 0C0000139h
0x18000a889  jmp     short loc_18000A8A0
0x18000a88b  mov     r9, rsi
0x18000a88e  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18000a895  xor     r8d, r8d
0x18000a898  mov     rdx, rbx
0x18000a89b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8a0  test    eax, eax
0x18000a8a2  jnz     short loc_18000A8B6
0x18000a8a4  lea     rcx, [rbx+48h]; this
0x18000a8a8  mov     r9, rbp; void *
0x18000a8ab  mov     r8, r15; void (*)(void *)
0x18000a8ae  mov     rdx, r14; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000a8b1  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18000a8b6  test    rdi, rdi
0x18000a8b9  jz      short loc_18000A8CA
0x18000a8bb  mov     rcx, rdi; SRWLock
0x18000a8be  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a8c5  nop     dword ptr [rax+rax+00h]
0x18000a8ca  add     rsp, 38h
0x18000a8ce  pop     r15
0x18000a8d0  pop     r14
0x18000a8d2  pop     rdi
0x18000a8d3  pop     rsi
0x18000a8d4  pop     rbp
0x18000a8d5  pop     rbx
0x18000a8d6  retn
```
