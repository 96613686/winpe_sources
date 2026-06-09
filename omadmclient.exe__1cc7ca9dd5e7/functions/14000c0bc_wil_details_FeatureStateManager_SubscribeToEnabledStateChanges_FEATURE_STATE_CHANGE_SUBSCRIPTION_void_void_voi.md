# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x14000c0bc`
- end: `0x14000c1b4`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `248`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x14000ca60`

## callees

- `0x14000c0bc`
- `0x14000c2d0`
- `0x140069010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000c148`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000c148`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000c12b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000c12b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000c19a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000c19a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000c0ec`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000c0ec`

## string_xrefs

- `0x14000c124`: `ntdll.dll`
- `0x14000c13e`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x14000c0bc  push    rbx
0x14000c0be  push    rbp
0x14000c0bf  push    rsi
0x14000c0c0  push    rdi
0x14000c0c1  push    r14
0x14000c0c3  push    r15
0x14000c0c5  sub     rsp, 38h
0x14000c0c9  mov     qword ptr [rdx], 0
0x14000c0d0  mov     rbp, r9
0x14000c0d3  cmp     byte ptr [rcx], 0
0x14000c0d6  mov     r15, r8
0x14000c0d9  mov     r14, rdx
0x14000c0dc  mov     rbx, rcx
0x14000c0df  jz      loc_14000C1A6
0x14000c0e5  lea     rdi, [rcx+20h]
0x14000c0e9  mov     rcx, rdi; SRWLock
0x14000c0ec  call    cs:__imp_AcquireSRWLockExclusive
0x14000c0f3  nop     dword ptr [rax+rax+00h]
0x14000c0f8  lea     rsi, [rbx+90h]
0x14000c0ff  cmp     qword ptr [rsi], 0
0x14000c103  jnz     short loc_14000C180
0x14000c105  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x14000c10c  mov     qword ptr [rsi], 0
0x14000c113  test    rax, rax
0x14000c116  jnz     short loc_14000C167
0x14000c118  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000c11f  test    rax, rax
0x14000c122  jnz     short loc_14000C13E
0x14000c124  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x14000c12b  call    cs:__imp_GetModuleHandleW
0x14000c132  nop     dword ptr [rax+rax+00h]
0x14000c137  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000c13e  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x14000c145  mov     rcx, rax; hModule
0x14000c148  call    cs:__imp_GetProcAddress
0x14000c14f  nop     dword ptr [rax+rax+00h]
0x14000c154  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x14000c15b  test    rax, rax
0x14000c15e  jnz     short loc_14000C167
0x14000c160  mov     eax, 0C0000139h
0x14000c165  jmp     short loc_14000C17C
0x14000c167  mov     r9, rsi
0x14000c16a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x14000c171  xor     r8d, r8d
0x14000c174  mov     rdx, rbx
0x14000c177  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c17c  test    eax, eax
0x14000c17e  jnz     short loc_14000C192
0x14000c180  lea     rcx, [rbx+48h]; this
0x14000c184  mov     r9, rbp; void *
0x14000c187  mov     r8, r15; void (*)(void *)
0x14000c18a  mov     rdx, r14; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x14000c18d  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x14000c192  test    rdi, rdi
0x14000c195  jz      short loc_14000C1A6
0x14000c197  mov     rcx, rdi; SRWLock
0x14000c19a  call    cs:__imp_ReleaseSRWLockExclusive
0x14000c1a1  nop     dword ptr [rax+rax+00h]
0x14000c1a6  add     rsp, 38h
0x14000c1aa  pop     r15
0x14000c1ac  pop     r14
0x14000c1ae  pop     rdi
0x14000c1af  pop     rsi
0x14000c1b0  pop     rbp
0x14000c1b1  pop     rbx
0x14000c1b2  retn
```
