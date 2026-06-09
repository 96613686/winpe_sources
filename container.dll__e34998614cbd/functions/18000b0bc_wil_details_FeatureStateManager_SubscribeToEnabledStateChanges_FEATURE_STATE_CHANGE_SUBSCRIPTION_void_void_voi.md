# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000b0bc`
- end: `0x18000b1b4`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `248`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000ba00`

## callees

- `0x18000b0bc`
- `0x18000b2d0`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b12b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b12b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b148`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b148`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b19a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b19a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b0ec`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b0ec`

## string_xrefs

- `0x18000b124`: `ntdll.dll`
- `0x18000b13e`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18000b0bc  push    rbx
0x18000b0be  push    rbp
0x18000b0bf  push    rsi
0x18000b0c0  push    rdi
0x18000b0c1  push    r14
0x18000b0c3  push    r15
0x18000b0c5  sub     rsp, 38h
0x18000b0c9  mov     qword ptr [rdx], 0
0x18000b0d0  mov     rbp, r9
0x18000b0d3  cmp     byte ptr [rcx], 0
0x18000b0d6  mov     r15, r8
0x18000b0d9  mov     r14, rdx
0x18000b0dc  mov     rbx, rcx
0x18000b0df  jz      loc_18000B1A6
0x18000b0e5  lea     rdi, [rcx+20h]
0x18000b0e9  mov     rcx, rdi; SRWLock
0x18000b0ec  call    cs:__imp_AcquireSRWLockExclusive
0x18000b0f3  nop     dword ptr [rax+rax+00h]
0x18000b0f8  lea     rsi, [rbx+90h]
0x18000b0ff  cmp     qword ptr [rsi], 0
0x18000b103  jnz     short loc_18000B180
0x18000b105  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000b10c  mov     qword ptr [rsi], 0
0x18000b113  test    rax, rax
0x18000b116  jnz     short loc_18000B167
0x18000b118  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b11f  test    rax, rax
0x18000b122  jnz     short loc_18000B13E
0x18000b124  lea     rcx, ModuleName; "ntdll.dll"
0x18000b12b  call    cs:__imp_GetModuleHandleW
0x18000b132  nop     dword ptr [rax+rax+00h]
0x18000b137  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b13e  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000b145  mov     rcx, rax; hModule
0x18000b148  call    cs:__imp_GetProcAddress
0x18000b14f  nop     dword ptr [rax+rax+00h]
0x18000b154  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000b15b  test    rax, rax
0x18000b15e  jnz     short loc_18000B167
0x18000b160  mov     eax, 0C0000139h
0x18000b165  jmp     short loc_18000B17C
0x18000b167  mov     r9, rsi
0x18000b16a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18000b171  xor     r8d, r8d
0x18000b174  mov     rdx, rbx
0x18000b177  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b17c  test    eax, eax
0x18000b17e  jnz     short loc_18000B192
0x18000b180  lea     rcx, [rbx+48h]; this
0x18000b184  mov     r9, rbp; void *
0x18000b187  mov     r8, r15; void (*)(void *)
0x18000b18a  mov     rdx, r14; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000b18d  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18000b192  test    rdi, rdi
0x18000b195  jz      short loc_18000B1A6
0x18000b197  mov     rcx, rdi; SRWLock
0x18000b19a  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b1a1  nop     dword ptr [rax+rax+00h]
0x18000b1a6  add     rsp, 38h
0x18000b1aa  pop     r15
0x18000b1ac  pop     r14
0x18000b1ae  pop     rdi
0x18000b1af  pop     rsi
0x18000b1b0  pop     rbp
0x18000b1b1  pop     rbx
0x18000b1b2  retn
```
