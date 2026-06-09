# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180013094`
- end: `0x18001318c`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `248`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180013a10`

## callees

- `0x180013094`
- `0x1800132a8`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180013103`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180013103`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013120`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013120`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013172`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013172`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800130c4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800130c4`

## string_xrefs

- `0x1800130fc`: `ntdll.dll`
- `0x180013116`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x180013094  push    rbx
0x180013096  push    rbp
0x180013097  push    rsi
0x180013098  push    rdi
0x180013099  push    r14
0x18001309b  push    r15
0x18001309d  sub     rsp, 38h
0x1800130a1  mov     qword ptr [rdx], 0
0x1800130a8  mov     rbp, r9
0x1800130ab  cmp     byte ptr [rcx], 0
0x1800130ae  mov     r15, r8
0x1800130b1  mov     r14, rdx
0x1800130b4  mov     rbx, rcx
0x1800130b7  jz      loc_18001317E
0x1800130bd  lea     rdi, [rcx+20h]
0x1800130c1  mov     rcx, rdi; SRWLock
0x1800130c4  call    cs:__imp_AcquireSRWLockExclusive
0x1800130cb  nop     dword ptr [rax+rax+00h]
0x1800130d0  lea     rsi, [rbx+90h]
0x1800130d7  cmp     qword ptr [rsi], 0
0x1800130db  jnz     short loc_180013158
0x1800130dd  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x1800130e4  mov     qword ptr [rsi], 0
0x1800130eb  test    rax, rax
0x1800130ee  jnz     short loc_18001313F
0x1800130f0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800130f7  test    rax, rax
0x1800130fa  jnz     short loc_180013116
0x1800130fc  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180013103  call    cs:__imp_GetModuleHandleW
0x18001310a  nop     dword ptr [rax+rax+00h]
0x18001310f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180013116  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18001311d  mov     rcx, rax; hModule
0x180013120  call    cs:__imp_GetProcAddress
0x180013127  nop     dword ptr [rax+rax+00h]
0x18001312c  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x180013133  test    rax, rax
0x180013136  jnz     short loc_18001313F
0x180013138  mov     eax, 0C0000139h
0x18001313d  jmp     short loc_180013154
0x18001313f  mov     r9, rsi
0x180013142  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x180013149  xor     r8d, r8d
0x18001314c  mov     rdx, rbx
0x18001314f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013154  test    eax, eax
0x180013156  jnz     short loc_18001316A
0x180013158  lea     rcx, [rbx+48h]; this
0x18001315c  mov     r9, rbp; void *
0x18001315f  mov     r8, r15; void (*)(void *)
0x180013162  mov     rdx, r14; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180013165  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18001316a  test    rdi, rdi
0x18001316d  jz      short loc_18001317E
0x18001316f  mov     rcx, rdi; SRWLock
0x180013172  call    cs:__imp_ReleaseSRWLockExclusive
0x180013179  nop     dword ptr [rax+rax+00h]
0x18001317e  add     rsp, 38h
0x180013182  pop     r15
0x180013184  pop     r14
0x180013186  pop     rdi
0x180013187  pop     rsi
0x180013188  pop     rbp
0x180013189  pop     rbx
0x18001318a  retn
```
