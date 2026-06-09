# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x1800058f8`
- end: `0x1800059b5`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `189`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `12`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180005e44`
- `0x180005fc4`
- `0x1800060a4`
- `0x180006184`
- `0x180007700`
- `0x180012398`
- `0x18001256c`
- `0x1800126e0`
- `0x180012854`
- `0x1800129c8`
- `0x180012aa8`
- `0x180012b88`

## callees

- `0x1800058f8`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005922`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005922`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005940`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005996`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005940`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005996`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_18001E6BC;
  if ( !dword_18001E6BC )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_18001E700 )
      {
        v1 = dword_18001E6BC;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_18001E700 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_18001E700,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_18001E700 )
      {
        v1 = 1;
        dword_18001E6BC = 1;
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
0x1800058f8  push    rbx
0x1800058fa  sub     rsp, 20h
0x1800058fe  mov     ebx, cs:dword_18001E6BC
0x180005904  nop
0x180005905  test    ebx, ebx
0x180005907  jnz     loc_18000599E
0x18000590d  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180005913  test    eax, eax
0x180005915  jz      loc_18000599C
0x18000591b  lea     rcx, SRWLock; SRWLock
0x180005922  call    cs:__imp_AcquireSRWLockExclusive
0x180005928  cmp     cs:qword_18001E700, 0
0x180005930  jz      short loc_180005948
0x180005932  mov     ebx, cs:dword_18001E6BC
0x180005938  nop
0x180005939  lea     rcx, SRWLock; SRWLock
0x180005940  call    cs:__imp_ReleaseSRWLockExclusive
0x180005946  jmp     short loc_18000599E
0x180005948  mov     cs:qword_18001E700, 0
0x180005953  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18000595a  test    rax, rax
0x18000595d  jnz     short loc_18000596B
0x18000595f  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180005966  test    rax, rax
0x180005969  jz      short loc_180005985
0x18000596b  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180005972  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180005979  lea     rcx, qword_18001E700
0x180005980  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005985  lea     rcx, SRWLock; SRWLock
0x18000598c  cmp     cs:qword_18001E700, 0
0x180005994  jnz     short loc_1800059A6
0x180005996  call    cs:__imp_ReleaseSRWLockExclusive
0x18000599c  xor     ebx, ebx
0x18000599e  mov     eax, ebx
0x1800059a0  add     rsp, 20h
0x1800059a4  pop     rbx
0x1800059a5  retn
0x1800059a6  nop
0x1800059a7  mov     ebx, 1
0x1800059ac  mov     cs:dword_18001E6BC, ebx
0x1800059b2  jmp     short loc_180005940
```
