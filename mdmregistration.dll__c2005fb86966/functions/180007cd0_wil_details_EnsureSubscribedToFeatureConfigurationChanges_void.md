# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180007cd0`
- end: `0x180007da3`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `211`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `13`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180008e78`
- `0x1800149f4`
- `0x18001c944`
- `0x18001cb08`
- `0x18001cc80`
- `0x18001e98c`
- `0x180027e74`
- `0x180027fec`
- `0x1800281b0`
- `0x180028328`
- `0x18002f04c`
- `0x180036a74`
- `0x1800451d8`

## callees

- `0x180007cd0`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007cfa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007cfa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007d1e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007d7a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007d1e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007d7a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_1800708A4;
  if ( !dword_1800708A4 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_1800708A8 )
      {
        v1 = dword_1800708A4;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_1800708A8 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_1800708A8,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_1800708A8 )
      {
        v1 = 1;
        dword_1800708A4 = 1;
        goto LABEL_5;
      }
      ReleaseSRWLockExclusive(&SRWLock);
    }
    return 0;
  }
  return v1;
}

```

## disassembly

```asm
0x180007cd0  push    rbx
0x180007cd2  sub     rsp, 20h
0x180007cd6  mov     ebx, cs:dword_1800708A4
0x180007cdc  nop
0x180007cdd  test    ebx, ebx
0x180007cdf  jnz     loc_180007D88
0x180007ce5  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180007ceb  test    eax, eax
0x180007ced  jz      loc_180007D86
0x180007cf3  lea     rcx, SRWLock; SRWLock
0x180007cfa  call    cs:__imp_AcquireSRWLockExclusive
0x180007d01  nop     dword ptr [rax+rax+00h]
0x180007d06  cmp     cs:qword_1800708A8, 0
0x180007d0e  jz      short loc_180007D2C
0x180007d10  mov     ebx, cs:dword_1800708A4
0x180007d16  nop
0x180007d17  lea     rcx, SRWLock; SRWLock
0x180007d1e  call    cs:__imp_ReleaseSRWLockExclusive
0x180007d25  nop     dword ptr [rax+rax+00h]
0x180007d2a  jmp     short loc_180007D88
0x180007d2c  mov     cs:qword_1800708A8, 0
0x180007d37  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180007d3e  test    rax, rax
0x180007d41  jnz     short loc_180007D4F
0x180007d43  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180007d4a  test    rax, rax
0x180007d4d  jz      short loc_180007D69
0x180007d4f  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180007d56  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180007d5d  lea     rcx, qword_1800708A8
0x180007d64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d69  lea     rcx, SRWLock; SRWLock
0x180007d70  cmp     cs:qword_1800708A8, 0
0x180007d78  jnz     short loc_180007D91
0x180007d7a  call    cs:__imp_ReleaseSRWLockExclusive
0x180007d81  nop     dword ptr [rax+rax+00h]
0x180007d86  xor     ebx, ebx
0x180007d88  mov     eax, ebx
0x180007d8a  add     rsp, 20h
0x180007d8e  pop     rbx
0x180007d8f  retn
0x180007d91  nop
0x180007d92  mov     ebx, 1
0x180007d97  mov     cs:dword_1800708A4, ebx
0x180007d9d  jmp     loc_180007D1E
```
