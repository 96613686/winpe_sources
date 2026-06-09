# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x14001e900`
- end: `0x14001e9f8`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `248`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x14001ef10`

## callees

- `0x14001e900`
- `0x14001eb14`
- `0x140034010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001e98c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001e98c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14001e96f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14001e96f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001e9de`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001e9de`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001e930`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001e930`

## string_xrefs

- `0x14001e968`: `ntdll.dll`
- `0x14001e982`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x14001e900  push    rbx
0x14001e902  push    rbp
0x14001e903  push    rsi
0x14001e904  push    rdi
0x14001e905  push    r14
0x14001e907  push    r15
0x14001e909  sub     rsp, 38h
0x14001e90d  mov     qword ptr [rdx], 0
0x14001e914  mov     rbp, r9
0x14001e917  cmp     byte ptr [rcx], 0
0x14001e91a  mov     r15, r8
0x14001e91d  mov     r14, rdx
0x14001e920  mov     rbx, rcx
0x14001e923  jz      loc_14001E9EA
0x14001e929  lea     rdi, [rcx+20h]
0x14001e92d  mov     rcx, rdi; SRWLock
0x14001e930  call    cs:__imp_AcquireSRWLockExclusive
0x14001e937  nop     dword ptr [rax+rax+00h]
0x14001e93c  lea     rsi, [rbx+90h]
0x14001e943  cmp     qword ptr [rsi], 0
0x14001e947  jnz     short loc_14001E9C4
0x14001e949  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x14001e950  mov     qword ptr [rsi], 0
0x14001e957  test    rax, rax
0x14001e95a  jnz     short loc_14001E9AB
0x14001e95c  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14001e963  test    rax, rax
0x14001e966  jnz     short loc_14001E982
0x14001e968  lea     rcx, ModuleName; "ntdll.dll"
0x14001e96f  call    cs:__imp_GetModuleHandleW
0x14001e976  nop     dword ptr [rax+rax+00h]
0x14001e97b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14001e982  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x14001e989  mov     rcx, rax; hModule
0x14001e98c  call    cs:__imp_GetProcAddress
0x14001e993  nop     dword ptr [rax+rax+00h]
0x14001e998  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x14001e99f  test    rax, rax
0x14001e9a2  jnz     short loc_14001E9AB
0x14001e9a4  mov     eax, 0C0000139h
0x14001e9a9  jmp     short loc_14001E9C0
0x14001e9ab  mov     r9, rsi
0x14001e9ae  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x14001e9b5  xor     r8d, r8d
0x14001e9b8  mov     rdx, rbx
0x14001e9bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001e9c0  test    eax, eax
0x14001e9c2  jnz     short loc_14001E9D6
0x14001e9c4  lea     rcx, [rbx+48h]; this
0x14001e9c8  mov     r9, rbp; void *
0x14001e9cb  mov     r8, r15; void (*)(void *)
0x14001e9ce  mov     rdx, r14; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x14001e9d1  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x14001e9d6  test    rdi, rdi
0x14001e9d9  jz      short loc_14001E9EA
0x14001e9db  mov     rcx, rdi; SRWLock
0x14001e9de  call    cs:__imp_ReleaseSRWLockExclusive
0x14001e9e5  nop     dword ptr [rax+rax+00h]
0x14001e9ea  add     rsp, 38h
0x14001e9ee  pop     r15
0x14001e9f0  pop     r14
0x14001e9f2  pop     rdi
0x14001e9f3  pop     rsi
0x14001e9f4  pop     rbp
0x14001e9f5  pop     rbx
0x14001e9f6  retn
```
