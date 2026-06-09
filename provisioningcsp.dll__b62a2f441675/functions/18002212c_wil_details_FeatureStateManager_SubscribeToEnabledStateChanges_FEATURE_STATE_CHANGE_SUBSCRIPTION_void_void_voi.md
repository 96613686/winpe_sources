# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18002212c`
- end: `0x180022224`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `248`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180022770`

## callees

- `0x18002212c`
- `0x180022340`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800221b8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800221b8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002219b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002219b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002215c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002215c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002220a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002220a`

## string_xrefs

- `0x180022194`: `ntdll.dll`
- `0x1800221ae`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18002212c  push    rbx
0x18002212e  push    rbp
0x18002212f  push    rsi
0x180022130  push    rdi
0x180022131  push    r14
0x180022133  push    r15
0x180022135  sub     rsp, 38h
0x180022139  mov     qword ptr [rdx], 0
0x180022140  mov     rbp, r9
0x180022143  cmp     byte ptr [rcx], 0
0x180022146  mov     r15, r8
0x180022149  mov     r14, rdx
0x18002214c  mov     rbx, rcx
0x18002214f  jz      loc_180022216
0x180022155  lea     rdi, [rcx+20h]
0x180022159  mov     rcx, rdi; SRWLock
0x18002215c  call    cs:__imp_AcquireSRWLockExclusive
0x180022163  nop     dword ptr [rax+rax+00h]
0x180022168  lea     rsi, [rbx+90h]
0x18002216f  cmp     qword ptr [rsi], 0
0x180022173  jnz     short loc_1800221F0
0x180022175  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18002217c  mov     qword ptr [rsi], 0
0x180022183  test    rax, rax
0x180022186  jnz     short loc_1800221D7
0x180022188  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18002218f  test    rax, rax
0x180022192  jnz     short loc_1800221AE
0x180022194  lea     rcx, ModuleName; "ntdll.dll"
0x18002219b  call    cs:__imp_GetModuleHandleW
0x1800221a2  nop     dword ptr [rax+rax+00h]
0x1800221a7  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800221ae  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x1800221b5  mov     rcx, rax; hModule
0x1800221b8  call    cs:__imp_GetProcAddress
0x1800221bf  nop     dword ptr [rax+rax+00h]
0x1800221c4  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x1800221cb  test    rax, rax
0x1800221ce  jnz     short loc_1800221D7
0x1800221d0  mov     eax, 0C0000139h
0x1800221d5  jmp     short loc_1800221EC
0x1800221d7  mov     r9, rsi
0x1800221da  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x1800221e1  xor     r8d, r8d
0x1800221e4  mov     rdx, rbx
0x1800221e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800221ec  test    eax, eax
0x1800221ee  jnz     short loc_180022202
0x1800221f0  lea     rcx, [rbx+48h]; this
0x1800221f4  mov     r9, rbp; void *
0x1800221f7  mov     r8, r15; void (*)(void *)
0x1800221fa  mov     rdx, r14; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1800221fd  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180022202  test    rdi, rdi
0x180022205  jz      short loc_180022216
0x180022207  mov     rcx, rdi; SRWLock
0x18002220a  call    cs:__imp_ReleaseSRWLockExclusive
0x180022211  nop     dword ptr [rax+rax+00h]
0x180022216  add     rsp, 38h
0x18002221a  pop     r15
0x18002221c  pop     r14
0x18002221e  pop     rdi
0x18002221f  pop     rsi
0x180022220  pop     rbp
0x180022221  pop     rbx
0x180022222  retn
```
