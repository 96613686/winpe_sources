# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180004638`
- end: `0x1800046f5`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `189`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180005750`

## callees

- `0x180004638`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004662`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004662`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004680`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800046d6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004680`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800046d6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_18002A3CC;
  if ( !dword_18002A3CC )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_18002A410 )
      {
        v1 = dword_18002A3CC;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_18002A410 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_18002A410,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_18002A410 )
      {
        v1 = 1;
        dword_18002A3CC = 1;
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
0x180004638  push    rbx
0x18000463a  sub     rsp, 20h
0x18000463e  mov     ebx, cs:dword_18002A3CC
0x180004644  nop
0x180004645  test    ebx, ebx
0x180004647  jnz     loc_1800046DE
0x18000464d  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180004653  test    eax, eax
0x180004655  jz      loc_1800046DC
0x18000465b  lea     rcx, SRWLock; SRWLock
0x180004662  call    cs:__imp_AcquireSRWLockExclusive
0x180004668  cmp     cs:qword_18002A410, 0
0x180004670  jz      short loc_180004688
0x180004672  mov     ebx, cs:dword_18002A3CC
0x180004678  nop
0x180004679  lea     rcx, SRWLock; SRWLock
0x180004680  call    cs:__imp_ReleaseSRWLockExclusive
0x180004686  jmp     short loc_1800046DE
0x180004688  mov     cs:qword_18002A410, 0
0x180004693  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18000469a  test    rax, rax
0x18000469d  jnz     short loc_1800046AB
0x18000469f  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x1800046a6  test    rax, rax
0x1800046a9  jz      short loc_1800046C5
0x1800046ab  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800046b2  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x1800046b9  lea     rcx, qword_18002A410
0x1800046c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046c5  lea     rcx, SRWLock; SRWLock
0x1800046cc  cmp     cs:qword_18002A410, 0
0x1800046d4  jnz     short loc_1800046E6
0x1800046d6  call    cs:__imp_ReleaseSRWLockExclusive
0x1800046dc  xor     ebx, ebx
0x1800046de  mov     eax, ebx
0x1800046e0  add     rsp, 20h
0x1800046e4  pop     rbx
0x1800046e5  retn
0x1800046e6  nop
0x1800046e7  mov     ebx, 1
0x1800046ec  mov     cs:dword_18002A3CC, ebx
0x1800046f2  jmp     short loc_180004680
```
