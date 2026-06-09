# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x140008274`
- end: `0x14000836c`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `248`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x140008be0`

## callees

- `0x140008274`
- `0x140008488`
- `0x14004d010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1400082e3`
- `KERNEL32!GetModuleHandleW` at `0x1400082e3`
- `KERNEL32!GetProcAddress` at `0x140008300`
- `KERNEL32!GetProcAddress` at `0x140008300`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1400082a4`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1400082a4`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140008352`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140008352`

## string_xrefs

- `0x1400082dc`: `ntdll.dll`
- `0x1400082f6`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x140008274  push    rbx
0x140008276  push    rbp
0x140008277  push    rsi
0x140008278  push    rdi
0x140008279  push    r14
0x14000827b  push    r15
0x14000827d  sub     rsp, 38h
0x140008281  mov     qword ptr [rdx], 0
0x140008288  mov     rbp, r9
0x14000828b  cmp     byte ptr [rcx], 0
0x14000828e  mov     r15, r8
0x140008291  mov     r14, rdx
0x140008294  mov     rbx, rcx
0x140008297  jz      loc_14000835E
0x14000829d  lea     rdi, [rcx+20h]
0x1400082a1  mov     rcx, rdi; SRWLock
0x1400082a4  call    cs:__imp_AcquireSRWLockExclusive
0x1400082ab  nop     dword ptr [rax+rax+00h]
0x1400082b0  lea     rsi, [rbx+90h]
0x1400082b7  cmp     qword ptr [rsi], 0
0x1400082bb  jnz     short loc_140008338
0x1400082bd  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x1400082c4  mov     qword ptr [rsi], 0
0x1400082cb  test    rax, rax
0x1400082ce  jnz     short loc_14000831F
0x1400082d0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400082d7  test    rax, rax
0x1400082da  jnz     short loc_1400082F6
0x1400082dc  lea     rcx, ModuleName; "ntdll.dll"
0x1400082e3  call    cs:__imp_GetModuleHandleW
0x1400082ea  nop     dword ptr [rax+rax+00h]
0x1400082ef  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400082f6  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x1400082fd  mov     rcx, rax; hModule
0x140008300  call    cs:__imp_GetProcAddress
0x140008307  nop     dword ptr [rax+rax+00h]
0x14000830c  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x140008313  test    rax, rax
0x140008316  jnz     short loc_14000831F
0x140008318  mov     eax, 0C0000139h
0x14000831d  jmp     short loc_140008334
0x14000831f  mov     r9, rsi
0x140008322  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x140008329  xor     r8d, r8d
0x14000832c  mov     rdx, rbx
0x14000832f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008334  test    eax, eax
0x140008336  jnz     short loc_14000834A
0x140008338  lea     rcx, [rbx+48h]; this
0x14000833c  mov     r9, rbp; void *
0x14000833f  mov     r8, r15; void (*)(void *)
0x140008342  mov     rdx, r14; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x140008345  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x14000834a  test    rdi, rdi
0x14000834d  jz      short loc_14000835E
0x14000834f  mov     rcx, rdi; SRWLock
0x140008352  call    cs:__imp_ReleaseSRWLockExclusive
0x140008359  nop     dword ptr [rax+rax+00h]
0x14000835e  add     rsp, 38h
0x140008362  pop     r15
0x140008364  pop     r14
0x140008366  pop     rdi
0x140008367  pop     rsi
0x140008368  pop     rbp
0x140008369  pop     rbx
0x14000836a  retn
```
