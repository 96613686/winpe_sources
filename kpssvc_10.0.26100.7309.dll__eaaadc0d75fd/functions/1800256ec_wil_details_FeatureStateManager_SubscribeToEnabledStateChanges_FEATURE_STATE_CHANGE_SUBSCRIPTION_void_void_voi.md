# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x1800256ec`
- end: `0x1800257f5`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `265`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180026030`

## callees

- `0x1800256ec`
- `0x180025920`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800257cf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800257cf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180025724`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180025724`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002577d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002577d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180025760`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180025760`

## string_xrefs

- `0x180025759`: `ntdll.dll`
- `0x180025773`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x1800256ec  mov     [rsp+arg_0], rbx
0x1800256f1  mov     [rsp+arg_8], rbp
0x1800256f6  mov     [rsp+arg_10], rsi
0x1800256fb  push    rdi
0x1800256fc  push    r14
0x1800256fe  push    r15
0x180025700  sub     rsp, 30h
0x180025704  and     qword ptr [rdx], 0
0x180025708  mov     rbp, r9
0x18002570b  cmp     byte ptr [rcx], 0
0x18002570e  mov     r15, r8
0x180025711  mov     r14, rdx
0x180025714  mov     rbx, rcx
0x180025717  jz      loc_1800257DB
0x18002571d  lea     rdi, [rcx+20h]
0x180025721  mov     rcx, rdi; SRWLock
0x180025724  call    cs:__imp_AcquireSRWLockExclusive
0x18002572b  nop     dword ptr [rax+rax+00h]
0x180025730  lea     rsi, [rbx+90h]
0x180025737  cmp     qword ptr [rsi], 0
0x18002573b  jnz     short loc_1800257B5
0x18002573d  and     qword ptr [rsi], 0
0x180025741  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180025748  test    rax, rax
0x18002574b  jnz     short loc_18002579C
0x18002574d  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180025754  test    rax, rax
0x180025757  jnz     short loc_180025773
0x180025759  lea     rcx, ModuleName; "ntdll.dll"
0x180025760  call    cs:__imp_GetModuleHandleW
0x180025767  nop     dword ptr [rax+rax+00h]
0x18002576c  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180025773  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18002577a  mov     rcx, rax; hModule
0x18002577d  call    cs:__imp_GetProcAddress
0x180025784  nop     dword ptr [rax+rax+00h]
0x180025789  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x180025790  test    rax, rax
0x180025793  jnz     short loc_18002579C
0x180025795  mov     eax, 0C0000139h
0x18002579a  jmp     short loc_1800257B1
0x18002579c  mov     r9, rsi
0x18002579f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x1800257a6  xor     r8d, r8d
0x1800257a9  mov     rdx, rbx
0x1800257ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800257b1  test    eax, eax
0x1800257b3  jnz     short loc_1800257C7
0x1800257b5  lea     rcx, [rbx+48h]; this
0x1800257b9  mov     r9, rbp; void *
0x1800257bc  mov     r8, r15; void (*)(void *)
0x1800257bf  mov     rdx, r14; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1800257c2  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x1800257c7  test    rdi, rdi
0x1800257ca  jz      short loc_1800257DB
0x1800257cc  mov     rcx, rdi; SRWLock
0x1800257cf  call    cs:__imp_ReleaseSRWLockExclusive
0x1800257d6  nop     dword ptr [rax+rax+00h]
0x1800257db  mov     rbx, [rsp+48h+arg_0]
0x1800257e0  mov     rbp, [rsp+48h+arg_8]
0x1800257e5  mov     rsi, [rsp+48h+arg_10]
0x1800257ea  add     rsp, 30h
0x1800257ee  pop     r15
0x1800257f0  pop     r14
0x1800257f2  pop     rdi
0x1800257f3  retn
```
