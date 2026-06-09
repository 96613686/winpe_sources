# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x1800054b4`
- end: `0x180005570`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `188`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180006798`
- `0x180014030`
- `0x180014110`

## callees

- `0x1800054b4`
- `0x180019010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800054fc`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180005552`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800054fc`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180005552`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800054de`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800054de`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_1800214BC;
  if ( !dword_1800214BC )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_180021500 )
      {
        v1 = dword_1800214BC;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      qword_180021500 = 0;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_180021500,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_180021500 )
      {
        v1 = 1;
        dword_1800214BC = 1;
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
0x1800054b4  push    rbx
0x1800054b6  sub     rsp, 20h
0x1800054ba  mov     ebx, cs:dword_1800214BC
0x1800054c0  nop
0x1800054c1  test    ebx, ebx
0x1800054c3  jnz     loc_18000555A
0x1800054c9  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800054cf  test    eax, eax
0x1800054d1  jz      loc_180005558
0x1800054d7  lea     rcx, SRWLock; SRWLock
0x1800054de  call    cs:__imp_AcquireSRWLockExclusive
0x1800054e4  cmp     cs:qword_180021500, 0
0x1800054ec  jz      short loc_180005504
0x1800054ee  mov     ebx, cs:dword_1800214BC
0x1800054f4  lea     rcx, SRWLock; SRWLock
0x1800054fb  nop
0x1800054fc  call    cs:__imp_ReleaseSRWLockExclusive
0x180005502  jmp     short loc_18000555A
0x180005504  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18000550b  mov     cs:qword_180021500, 0
0x180005516  test    rax, rax
0x180005519  jnz     short loc_180005527
0x18000551b  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180005522  test    rax, rax
0x180005525  jz      short loc_180005541
0x180005527  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000552e  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180005535  lea     rcx, qword_180021500
0x18000553c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005541  cmp     cs:qword_180021500, 0
0x180005549  lea     rcx, SRWLock; SRWLock
0x180005550  jnz     short loc_180005562
0x180005552  call    cs:__imp_ReleaseSRWLockExclusive
0x180005558  xor     ebx, ebx
0x18000555a  mov     eax, ebx
0x18000555c  add     rsp, 20h
0x180005560  pop     rbx
0x180005561  retn
0x180005562  mov     ebx, 1
0x180005567  nop
0x180005568  mov     cs:dword_1800214BC, ebx
0x18000556e  jmp     short loc_1800054FC
```
