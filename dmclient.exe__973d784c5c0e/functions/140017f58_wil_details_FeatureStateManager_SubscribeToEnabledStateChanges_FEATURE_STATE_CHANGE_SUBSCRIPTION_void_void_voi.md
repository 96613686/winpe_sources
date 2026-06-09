# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x140017f58`
- end: `0x140018050`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `248`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x140018570`

## callees

- `0x140017f58`
- `0x14001816c`
- `0x14001a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140017fe4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140017fe4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140017fc7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140017fc7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140017f88`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140017f88`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140018036`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140018036`

## string_xrefs

- `0x140017fc0`: `ntdll.dll`
- `0x140017fda`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x140017f58  push    rbx
0x140017f5a  push    rbp
0x140017f5b  push    rsi
0x140017f5c  push    rdi
0x140017f5d  push    r14
0x140017f5f  push    r15
0x140017f61  sub     rsp, 38h
0x140017f65  mov     qword ptr [rdx], 0
0x140017f6c  mov     rbp, r9
0x140017f6f  cmp     byte ptr [rcx], 0
0x140017f72  mov     r15, r8
0x140017f75  mov     r14, rdx
0x140017f78  mov     rbx, rcx
0x140017f7b  jz      loc_140018042
0x140017f81  lea     rdi, [rcx+20h]
0x140017f85  mov     rcx, rdi; SRWLock
0x140017f88  call    cs:__imp_AcquireSRWLockExclusive
0x140017f8f  nop     dword ptr [rax+rax+00h]
0x140017f94  lea     rsi, [rbx+90h]
0x140017f9b  cmp     qword ptr [rsi], 0
0x140017f9f  jnz     short loc_14001801C
0x140017fa1  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x140017fa8  mov     qword ptr [rsi], 0
0x140017faf  test    rax, rax
0x140017fb2  jnz     short loc_140018003
0x140017fb4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140017fbb  test    rax, rax
0x140017fbe  jnz     short loc_140017FDA
0x140017fc0  lea     rcx, ModuleName; "ntdll.dll"
0x140017fc7  call    cs:__imp_GetModuleHandleW
0x140017fce  nop     dword ptr [rax+rax+00h]
0x140017fd3  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140017fda  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x140017fe1  mov     rcx, rax; hModule
0x140017fe4  call    cs:__imp_GetProcAddress
0x140017feb  nop     dword ptr [rax+rax+00h]
0x140017ff0  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x140017ff7  test    rax, rax
0x140017ffa  jnz     short loc_140018003
0x140017ffc  mov     eax, 0C0000139h
0x140018001  jmp     short loc_140018018
0x140018003  mov     r9, rsi
0x140018006  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x14001800d  xor     r8d, r8d
0x140018010  mov     rdx, rbx
0x140018013  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018018  test    eax, eax
0x14001801a  jnz     short loc_14001802E
0x14001801c  lea     rcx, [rbx+48h]; this
0x140018020  mov     r9, rbp; void *
0x140018023  mov     r8, r15; void (*)(void *)
0x140018026  mov     rdx, r14; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x140018029  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x14001802e  test    rdi, rdi
0x140018031  jz      short loc_140018042
0x140018033  mov     rcx, rdi; SRWLock
0x140018036  call    cs:__imp_ReleaseSRWLockExclusive
0x14001803d  nop     dword ptr [rax+rax+00h]
0x140018042  add     rsp, 38h
0x140018046  pop     r15
0x140018048  pop     r14
0x14001804a  pop     rdi
0x14001804b  pop     rsi
0x14001804c  pop     rbp
0x14001804d  pop     rbx
0x14001804e  retn
```
