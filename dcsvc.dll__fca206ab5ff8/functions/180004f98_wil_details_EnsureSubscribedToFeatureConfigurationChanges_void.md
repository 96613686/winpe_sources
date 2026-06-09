# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180004f98`
- end: `0x180005055`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `189`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180006210`
- `0x18000b9d0`

## callees

- `0x180004f98`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004fe0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005036`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004fe0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005036`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004fc2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004fc2`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_18001B584;
  if ( !dword_18001B584 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_18001B5C8 )
      {
        v1 = dword_18001B584;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_18001B5C8 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_18001B5C8,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_18001B5C8 )
      {
        v1 = 1;
        dword_18001B584 = 1;
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
0x180004f98  push    rbx
0x180004f9a  sub     rsp, 20h
0x180004f9e  mov     ebx, cs:dword_18001B584
0x180004fa4  nop
0x180004fa5  test    ebx, ebx
0x180004fa7  jnz     loc_18000503E
0x180004fad  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180004fb3  test    eax, eax
0x180004fb5  jz      loc_18000503C
0x180004fbb  lea     rcx, SRWLock; SRWLock
0x180004fc2  call    cs:__imp_AcquireSRWLockExclusive
0x180004fc8  cmp     cs:qword_18001B5C8, 0
0x180004fd0  jz      short loc_180004FE8
0x180004fd2  mov     ebx, cs:dword_18001B584
0x180004fd8  nop
0x180004fd9  lea     rcx, SRWLock; SRWLock
0x180004fe0  call    cs:__imp_ReleaseSRWLockExclusive
0x180004fe6  jmp     short loc_18000503E
0x180004fe8  mov     cs:qword_18001B5C8, 0
0x180004ff3  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180004ffa  test    rax, rax
0x180004ffd  jnz     short loc_18000500B
0x180004fff  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180005006  test    rax, rax
0x180005009  jz      short loc_180005025
0x18000500b  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180005012  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180005019  lea     rcx, qword_18001B5C8
0x180005020  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005025  lea     rcx, SRWLock; SRWLock
0x18000502c  cmp     cs:qword_18001B5C8, 0
0x180005034  jnz     short loc_180005046
0x180005036  call    cs:__imp_ReleaseSRWLockExclusive
0x18000503c  xor     ebx, ebx
0x18000503e  mov     eax, ebx
0x180005040  add     rsp, 20h
0x180005044  pop     rbx
0x180005045  retn
0x180005046  nop
0x180005047  mov     ebx, 1
0x18000504c  mov     cs:dword_18001B584, ebx
0x180005052  jmp     short loc_180004FE0
```
