# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180007250`
- end: `0x180007348`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `248`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180007b20`

## callees

- `0x180007250`
- `0x180007464`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800072dc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800072dc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800072bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800072bf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000732e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000732e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007280`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007280`

## string_xrefs

- `0x1800072b8`: `ntdll.dll`
- `0x1800072d2`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x180007250  push    rbx
0x180007252  push    rbp
0x180007253  push    rsi
0x180007254  push    rdi
0x180007255  push    r14
0x180007257  push    r15
0x180007259  sub     rsp, 38h
0x18000725d  mov     qword ptr [rdx], 0
0x180007264  mov     rbp, r9
0x180007267  cmp     byte ptr [rcx], 0
0x18000726a  mov     r15, r8
0x18000726d  mov     r14, rdx
0x180007270  mov     rbx, rcx
0x180007273  jz      loc_18000733A
0x180007279  lea     rdi, [rcx+20h]
0x18000727d  mov     rcx, rdi; SRWLock
0x180007280  call    cs:__imp_AcquireSRWLockExclusive
0x180007287  nop     dword ptr [rax+rax+00h]
0x18000728c  lea     rsi, [rbx+90h]
0x180007293  cmp     qword ptr [rsi], 0
0x180007297  jnz     short loc_180007314
0x180007299  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x1800072a0  mov     qword ptr [rsi], 0
0x1800072a7  test    rax, rax
0x1800072aa  jnz     short loc_1800072FB
0x1800072ac  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800072b3  test    rax, rax
0x1800072b6  jnz     short loc_1800072D2
0x1800072b8  lea     rcx, ModuleName; "ntdll.dll"
0x1800072bf  call    cs:__imp_GetModuleHandleW
0x1800072c6  nop     dword ptr [rax+rax+00h]
0x1800072cb  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800072d2  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x1800072d9  mov     rcx, rax; hModule
0x1800072dc  call    cs:__imp_GetProcAddress
0x1800072e3  nop     dword ptr [rax+rax+00h]
0x1800072e8  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x1800072ef  test    rax, rax
0x1800072f2  jnz     short loc_1800072FB
0x1800072f4  mov     eax, 0C0000139h
0x1800072f9  jmp     short loc_180007310
0x1800072fb  mov     r9, rsi
0x1800072fe  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x180007305  xor     r8d, r8d
0x180007308  mov     rdx, rbx
0x18000730b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007310  test    eax, eax
0x180007312  jnz     short loc_180007326
0x180007314  lea     rcx, [rbx+48h]; this
0x180007318  mov     r9, rbp; void *
0x18000731b  mov     r8, r15; void (*)(void *)
0x18000731e  mov     rdx, r14; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180007321  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180007326  test    rdi, rdi
0x180007329  jz      short loc_18000733A
0x18000732b  mov     rcx, rdi; SRWLock
0x18000732e  call    cs:__imp_ReleaseSRWLockExclusive
0x180007335  nop     dword ptr [rax+rax+00h]
0x18000733a  add     rsp, 38h
0x18000733e  pop     r15
0x180007340  pop     r14
0x180007342  pop     rdi
0x180007343  pop     rsi
0x180007344  pop     rbp
0x180007345  pop     rbx
0x180007346  retn
```
