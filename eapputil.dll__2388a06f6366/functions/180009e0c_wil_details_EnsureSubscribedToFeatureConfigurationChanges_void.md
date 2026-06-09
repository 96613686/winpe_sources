# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180009e0c`
- end: `0x180009ec9`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `189`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000a374`
- `0x18001b5fc`
- `0x18001b7d0`
- `0x18001b950`
- `0x18001bb0c`
- `0x18001bbec`

## callees

- `0x180009e0c`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009e54`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009eaa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009e54`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009eaa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009e36`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009e36`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_180043AB4;
  if ( !dword_180043AB4 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_180043AF8 )
      {
        v1 = dword_180043AB4;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_180043AF8 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_180043AF8,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_180043AF8 )
      {
        v1 = 1;
        dword_180043AB4 = 1;
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
0x180009e0c  push    rbx
0x180009e0e  sub     rsp, 20h
0x180009e12  mov     ebx, cs:dword_180043AB4
0x180009e18  nop
0x180009e19  test    ebx, ebx
0x180009e1b  jnz     loc_180009EB2
0x180009e21  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180009e27  test    eax, eax
0x180009e29  jz      loc_180009EB0
0x180009e2f  lea     rcx, SRWLock; SRWLock
0x180009e36  call    cs:__imp_AcquireSRWLockExclusive
0x180009e3c  cmp     cs:qword_180043AF8, 0
0x180009e44  jz      short loc_180009E5C
0x180009e46  mov     ebx, cs:dword_180043AB4
0x180009e4c  nop
0x180009e4d  lea     rcx, SRWLock; SRWLock
0x180009e54  call    cs:__imp_ReleaseSRWLockExclusive
0x180009e5a  jmp     short loc_180009EB2
0x180009e5c  mov     cs:qword_180043AF8, 0
0x180009e67  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180009e6e  test    rax, rax
0x180009e71  jnz     short loc_180009E7F
0x180009e73  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180009e7a  test    rax, rax
0x180009e7d  jz      short loc_180009E99
0x180009e7f  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180009e86  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180009e8d  lea     rcx, qword_180043AF8
0x180009e94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e99  lea     rcx, SRWLock; SRWLock
0x180009ea0  cmp     cs:qword_180043AF8, 0
0x180009ea8  jnz     short loc_180009EBA
0x180009eaa  call    cs:__imp_ReleaseSRWLockExclusive
0x180009eb0  xor     ebx, ebx
0x180009eb2  mov     eax, ebx
0x180009eb4  add     rsp, 20h
0x180009eb8  pop     rbx
0x180009eb9  retn
0x180009eba  nop
0x180009ebb  mov     ebx, 1
0x180009ec0  mov     cs:dword_180043AB4, ebx
0x180009ec6  jmp     short loc_180009E54
```
