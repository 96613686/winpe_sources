# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x140007ca8`
- end: `0x140007d7b`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `211`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `18`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140009040`
- `0x14000e44c`
- `0x1400152d4`
- `0x1400167c4`
- `0x140016944`
- `0x140016abc`
- `0x14002c024`
- `0x1400333a8`
- `0x14003ac50`
- `0x14003adc8`
- `0x1400473f4`
- `0x14004c098`
- `0x14004cfa4`
- `0x1400529c8`
- `0x14005cc0c`
- `0x14005cdd0`
- `0x14005cf94`
- `0x140065568`

## callees

- `0x140007ca8`
- `0x140069010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140007cf6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140007d52`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140007cf6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140007d52`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140007cd2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140007cd2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_140084B74;
  if ( !dword_140084B74 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_140084B78 )
      {
        v1 = dword_140084B74;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_140084B78 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_140084B78,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_140084B78 )
      {
        v1 = 1;
        dword_140084B74 = 1;
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
0x140007ca8  push    rbx
0x140007caa  sub     rsp, 20h
0x140007cae  mov     ebx, cs:dword_140084B74
0x140007cb4  nop
0x140007cb5  test    ebx, ebx
0x140007cb7  jnz     loc_140007D60
0x140007cbd  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x140007cc3  test    eax, eax
0x140007cc5  jz      loc_140007D5E
0x140007ccb  lea     rcx, SRWLock; SRWLock
0x140007cd2  call    cs:__imp_AcquireSRWLockExclusive
0x140007cd9  nop     dword ptr [rax+rax+00h]
0x140007cde  cmp     cs:qword_140084B78, 0
0x140007ce6  jz      short loc_140007D04
0x140007ce8  mov     ebx, cs:dword_140084B74
0x140007cee  nop
0x140007cef  lea     rcx, SRWLock; SRWLock
0x140007cf6  call    cs:__imp_ReleaseSRWLockExclusive
0x140007cfd  nop     dword ptr [rax+rax+00h]
0x140007d02  jmp     short loc_140007D60
0x140007d04  mov     cs:qword_140084B78, 0
0x140007d0f  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x140007d16  test    rax, rax
0x140007d19  jnz     short loc_140007D27
0x140007d1b  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x140007d22  test    rax, rax
0x140007d25  jz      short loc_140007D41
0x140007d27  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x140007d2e  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x140007d35  lea     rcx, qword_140084B78
0x140007d3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007d41  lea     rcx, SRWLock; SRWLock
0x140007d48  cmp     cs:qword_140084B78, 0
0x140007d50  jnz     short loc_140007D69
0x140007d52  call    cs:__imp_ReleaseSRWLockExclusive
0x140007d59  nop     dword ptr [rax+rax+00h]
0x140007d5e  xor     ebx, ebx
0x140007d60  mov     eax, ebx
0x140007d62  add     rsp, 20h
0x140007d66  pop     rbx
0x140007d67  retn
0x140007d69  nop
0x140007d6a  mov     ebx, 1
0x140007d6f  mov     cs:dword_140084B74, ebx
0x140007d75  jmp     loc_140007CF6
```
