# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x18000426c`
- end: `0x180004328`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `188`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `13`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000e6a8`
- `0x18000e874`
- `0x18000e9e8`
- `0x18000eb5c`
- `0x18000ecd0`
- `0x18000ee44`
- `0x18000efb8`
- `0x18000f098`
- `0x18000f178`
- `0x18000f258`
- `0x18000f338`
- `0x18000f418`
- `0x18000fafc`

## callees

- `0x18000426c`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004296`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004296`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800042b4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000430a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800042b4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000430a`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_18001E2F4;
  if ( !dword_18001E2F4 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_18001E338 )
      {
        v1 = dword_18001E2F4;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      qword_18001E338 = 0;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_18001E338,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_18001E338 )
      {
        v1 = 1;
        dword_18001E2F4 = 1;
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
0x18000426c  push    rbx
0x18000426e  sub     rsp, 20h
0x180004272  mov     ebx, cs:dword_18001E2F4
0x180004278  nop
0x180004279  test    ebx, ebx
0x18000427b  jnz     loc_180004312
0x180004281  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180004287  test    eax, eax
0x180004289  jz      loc_180004310
0x18000428f  lea     rcx, SRWLock; SRWLock
0x180004296  call    cs:__imp_AcquireSRWLockExclusive
0x18000429c  cmp     cs:qword_18001E338, 0
0x1800042a4  jz      short loc_1800042BC
0x1800042a6  mov     ebx, cs:dword_18001E2F4
0x1800042ac  lea     rcx, SRWLock; SRWLock
0x1800042b3  nop
0x1800042b4  call    cs:__imp_ReleaseSRWLockExclusive
0x1800042ba  jmp     short loc_180004312
0x1800042bc  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x1800042c3  mov     cs:qword_18001E338, 0
0x1800042ce  test    rax, rax
0x1800042d1  jnz     short loc_1800042DF
0x1800042d3  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x1800042da  test    rax, rax
0x1800042dd  jz      short loc_1800042F9
0x1800042df  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800042e6  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x1800042ed  lea     rcx, qword_18001E338
0x1800042f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042f9  cmp     cs:qword_18001E338, 0
0x180004301  lea     rcx, SRWLock; SRWLock
0x180004308  jnz     short loc_18000431A
0x18000430a  call    cs:__imp_ReleaseSRWLockExclusive
0x180004310  xor     ebx, ebx
0x180004312  mov     eax, ebx
0x180004314  add     rsp, 20h
0x180004318  pop     rbx
0x180004319  retn
0x18000431a  mov     ebx, 1
0x18000431f  nop
0x180004320  mov     cs:dword_18001E2F4, ebx
0x180004326  jmp     short loc_1800042B4
```
