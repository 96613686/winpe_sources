# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180014188`
- end: `0x180014291`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `265`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180015a80`

## callees

- `0x180014188`
- `0x1800143bc`
- `0x180024010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1800141fc`
- `KERNEL32!GetModuleHandleW` at `0x1800141fc`
- `KERNEL32!GetProcAddress` at `0x180014219`
- `KERNEL32!GetProcAddress` at `0x180014219`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800141c0`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800141c0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001426b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001426b`

## string_xrefs

- `0x1800141f5`: `ntdll.dll`
- `0x18001420f`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x180014188  mov     [rsp+arg_0], rbx
0x18001418d  mov     [rsp+arg_8], rbp
0x180014192  mov     [rsp+arg_10], rsi
0x180014197  push    rdi
0x180014198  push    r14
0x18001419a  push    r15
0x18001419c  sub     rsp, 30h
0x1800141a0  and     qword ptr [rdx], 0
0x1800141a4  mov     rbp, r9
0x1800141a7  cmp     byte ptr [rcx], 0
0x1800141aa  mov     r15, r8
0x1800141ad  mov     r14, rdx
0x1800141b0  mov     rbx, rcx
0x1800141b3  jz      loc_180014277
0x1800141b9  lea     rdi, [rcx+20h]
0x1800141bd  mov     rcx, rdi; SRWLock
0x1800141c0  call    cs:__imp_AcquireSRWLockExclusive
0x1800141c7  nop     dword ptr [rax+rax+00h]
0x1800141cc  lea     rsi, [rbx+90h]
0x1800141d3  cmp     qword ptr [rsi], 0
0x1800141d7  jnz     short loc_180014251
0x1800141d9  and     qword ptr [rsi], 0
0x1800141dd  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x1800141e4  test    rax, rax
0x1800141e7  jnz     short loc_180014238
0x1800141e9  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800141f0  test    rax, rax
0x1800141f3  jnz     short loc_18001420F
0x1800141f5  lea     rcx, ModuleName; "ntdll.dll"
0x1800141fc  call    cs:__imp_GetModuleHandleW
0x180014203  nop     dword ptr [rax+rax+00h]
0x180014208  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001420f  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x180014216  mov     rcx, rax; hModule
0x180014219  call    cs:__imp_GetProcAddress
0x180014220  nop     dword ptr [rax+rax+00h]
0x180014225  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18001422c  test    rax, rax
0x18001422f  jnz     short loc_180014238
0x180014231  mov     eax, 0C0000139h
0x180014236  jmp     short loc_18001424D
0x180014238  mov     r9, rsi
0x18001423b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x180014242  xor     r8d, r8d
0x180014245  mov     rdx, rbx
0x180014248  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001424d  test    eax, eax
0x18001424f  jnz     short loc_180014263
0x180014251  lea     rcx, [rbx+48h]; this
0x180014255  mov     r9, rbp; void *
0x180014258  mov     r8, r15; void (*)(void *)
0x18001425b  mov     rdx, r14; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18001425e  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180014263  test    rdi, rdi
0x180014266  jz      short loc_180014277
0x180014268  mov     rcx, rdi; SRWLock
0x18001426b  call    cs:__imp_ReleaseSRWLockExclusive
0x180014272  nop     dword ptr [rax+rax+00h]
0x180014277  mov     rbx, [rsp+48h+arg_0]
0x18001427c  mov     rbp, [rsp+48h+arg_8]
0x180014281  mov     rsi, [rsp+48h+arg_10]
0x180014286  add     rsp, 30h
0x18001428a  pop     r15
0x18001428c  pop     r14
0x18001428e  pop     rdi
0x18001428f  retn
```
