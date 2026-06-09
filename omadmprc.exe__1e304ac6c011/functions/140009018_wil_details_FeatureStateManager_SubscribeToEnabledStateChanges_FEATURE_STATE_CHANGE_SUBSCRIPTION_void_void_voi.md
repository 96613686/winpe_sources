# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x140009018`
- end: `0x140009110`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `248`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1400099c0`

## callees

- `0x140009018`
- `0x14000922c`
- `0x140017010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140009087`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140009087`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400090a4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400090a4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140009048`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140009048`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400090f6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400090f6`

## string_xrefs

- `0x140009080`: `ntdll.dll`
- `0x14000909a`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x140009018  push    rbx
0x14000901a  push    rbp
0x14000901b  push    rsi
0x14000901c  push    rdi
0x14000901d  push    r14
0x14000901f  push    r15
0x140009021  sub     rsp, 38h
0x140009025  mov     qword ptr [rdx], 0
0x14000902c  mov     rbp, r9
0x14000902f  cmp     byte ptr [rcx], 0
0x140009032  mov     r15, r8
0x140009035  mov     r14, rdx
0x140009038  mov     rbx, rcx
0x14000903b  jz      loc_140009102
0x140009041  lea     rdi, [rcx+20h]
0x140009045  mov     rcx, rdi; SRWLock
0x140009048  call    cs:__imp_AcquireSRWLockExclusive
0x14000904f  nop     dword ptr [rax+rax+00h]
0x140009054  lea     rsi, [rbx+90h]
0x14000905b  cmp     qword ptr [rsi], 0
0x14000905f  jnz     short loc_1400090DC
0x140009061  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x140009068  mov     qword ptr [rsi], 0
0x14000906f  test    rax, rax
0x140009072  jnz     short loc_1400090C3
0x140009074  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000907b  test    rax, rax
0x14000907e  jnz     short loc_14000909A
0x140009080  lea     rcx, ModuleName; "ntdll.dll"
0x140009087  call    cs:__imp_GetModuleHandleW
0x14000908e  nop     dword ptr [rax+rax+00h]
0x140009093  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000909a  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x1400090a1  mov     rcx, rax; hModule
0x1400090a4  call    cs:__imp_GetProcAddress
0x1400090ab  nop     dword ptr [rax+rax+00h]
0x1400090b0  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x1400090b7  test    rax, rax
0x1400090ba  jnz     short loc_1400090C3
0x1400090bc  mov     eax, 0C0000139h
0x1400090c1  jmp     short loc_1400090D8
0x1400090c3  mov     r9, rsi
0x1400090c6  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x1400090cd  xor     r8d, r8d
0x1400090d0  mov     rdx, rbx
0x1400090d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400090d8  test    eax, eax
0x1400090da  jnz     short loc_1400090EE
0x1400090dc  lea     rcx, [rbx+48h]; this
0x1400090e0  mov     r9, rbp; void *
0x1400090e3  mov     r8, r15; void (*)(void *)
0x1400090e6  mov     rdx, r14; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1400090e9  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x1400090ee  test    rdi, rdi
0x1400090f1  jz      short loc_140009102
0x1400090f3  mov     rcx, rdi; SRWLock
0x1400090f6  call    cs:__imp_ReleaseSRWLockExclusive
0x1400090fd  nop     dword ptr [rax+rax+00h]
0x140009102  add     rsp, 38h
0x140009106  pop     r15
0x140009108  pop     r14
0x14000910a  pop     rdi
0x14000910b  pop     rsi
0x14000910c  pop     rbp
0x14000910d  pop     rbx
0x14000910e  retn
```
