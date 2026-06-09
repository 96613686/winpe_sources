# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180008c18`
- end: `0x180008d21`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `265`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800095e0`

## callees

- `0x180008c18`
- `0x180008e4c`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008c8c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008c8c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008ca9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008ca9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008cfb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008cfb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008c50`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008c50`

## string_xrefs

- `0x180008c85`: `ntdll.dll`
- `0x180008c9f`: `RtlRegisterFeatureConfigurationChangeNotification`

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
    this[18].Ptr = 0;
    ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
    if ( g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification )
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
0x180008c18  mov     [rsp+arg_0], rbx
0x180008c1d  mov     [rsp+arg_8], rbp
0x180008c22  mov     [rsp+arg_10], rsi
0x180008c27  push    rdi
0x180008c28  push    r14
0x180008c2a  push    r15
0x180008c2c  sub     rsp, 30h
0x180008c30  and     qword ptr [rdx], 0
0x180008c34  mov     rbp, r9
0x180008c37  cmp     byte ptr [rcx], 0
0x180008c3a  mov     r15, r8
0x180008c3d  mov     r14, rdx
0x180008c40  mov     rbx, rcx
0x180008c43  jz      loc_180008D07
0x180008c49  lea     rdi, [rcx+20h]
0x180008c4d  mov     rcx, rdi; SRWLock
0x180008c50  call    cs:__imp_AcquireSRWLockExclusive
0x180008c57  nop     dword ptr [rax+rax+00h]
0x180008c5c  lea     rsi, [rbx+90h]
0x180008c63  cmp     qword ptr [rsi], 0
0x180008c67  jnz     short loc_180008CE1
0x180008c69  and     qword ptr [rsi], 0
0x180008c6d  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180008c74  test    rax, rax
0x180008c77  jnz     short loc_180008CC8
0x180008c79  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008c80  test    rax, rax
0x180008c83  jnz     short loc_180008C9F
0x180008c85  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x180008c8c  call    cs:__imp_GetModuleHandleW
0x180008c93  nop     dword ptr [rax+rax+00h]
0x180008c98  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008c9f  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x180008ca6  mov     rcx, rax; hModule
0x180008ca9  call    cs:__imp_GetProcAddress
0x180008cb0  nop     dword ptr [rax+rax+00h]
0x180008cb5  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x180008cbc  test    rax, rax
0x180008cbf  jnz     short loc_180008CC8
0x180008cc1  mov     eax, 0C0000139h
0x180008cc6  jmp     short loc_180008CDD
0x180008cc8  mov     r9, rsi
0x180008ccb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x180008cd2  xor     r8d, r8d
0x180008cd5  mov     rdx, rbx
0x180008cd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cdd  test    eax, eax
0x180008cdf  jnz     short loc_180008CF3
0x180008ce1  lea     rcx, [rbx+48h]; this
0x180008ce5  mov     r9, rbp; void *
0x180008ce8  mov     r8, r15; void (*)(void *)
0x180008ceb  mov     rdx, r14; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180008cee  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180008cf3  test    rdi, rdi
0x180008cf6  jz      short loc_180008D07
0x180008cf8  mov     rcx, rdi; SRWLock
0x180008cfb  call    cs:__imp_ReleaseSRWLockExclusive
0x180008d02  nop     dword ptr [rax+rax+00h]
0x180008d07  mov     rbx, [rsp+48h+arg_0]
0x180008d0c  mov     rbp, [rsp+48h+arg_8]
0x180008d11  mov     rsi, [rsp+48h+arg_10]
0x180008d16  add     rsp, 30h
0x180008d1a  pop     r15
0x180008d1c  pop     r14
0x180008d1e  pop     rdi
0x180008d1f  retn
```
