# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180005c18`
- end: `0x180005cd5`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `189`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `18`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180006d28`
- `0x18000c984`
- `0x18000ca64`
- `0x18000cc34`
- `0x18000cd14`
- `0x18000ce88`
- `0x18000cffc`
- `0x18000d170`
- `0x18000d2e4`
- `0x18000d464`
- `0x1800124a8`
- `0x18001267c`
- `0x1800127f0`
- `0x1800128d0`
- `0x1800129b0`
- `0x180012a90`
- `0x180012b70`
- `0x180012c50`

## callees

- `0x180005c18`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005c42`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005c42`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005c60`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005cb6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005c60`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005cb6`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_180021C74;
  if ( !dword_180021C74 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_180021CB8 )
      {
        v1 = dword_180021C74;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_180021CB8 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_180021CB8,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_180021CB8 )
      {
        v1 = 1;
        dword_180021C74 = 1;
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
0x180005c18  push    rbx
0x180005c1a  sub     rsp, 20h
0x180005c1e  mov     ebx, cs:dword_180021C74
0x180005c24  nop
0x180005c25  test    ebx, ebx
0x180005c27  jnz     loc_180005CBE
0x180005c2d  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180005c33  test    eax, eax
0x180005c35  jz      loc_180005CBC
0x180005c3b  lea     rcx, SRWLock; SRWLock
0x180005c42  call    cs:__imp_AcquireSRWLockExclusive
0x180005c48  cmp     cs:qword_180021CB8, 0
0x180005c50  jz      short loc_180005C68
0x180005c52  mov     ebx, cs:dword_180021C74
0x180005c58  nop
0x180005c59  lea     rcx, SRWLock; SRWLock
0x180005c60  call    cs:__imp_ReleaseSRWLockExclusive
0x180005c66  jmp     short loc_180005CBE
0x180005c68  mov     cs:qword_180021CB8, 0
0x180005c73  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180005c7a  test    rax, rax
0x180005c7d  jnz     short loc_180005C8B
0x180005c7f  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180005c86  test    rax, rax
0x180005c89  jz      short loc_180005CA5
0x180005c8b  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180005c92  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180005c99  lea     rcx, qword_180021CB8
0x180005ca0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ca5  lea     rcx, SRWLock; SRWLock
0x180005cac  cmp     cs:qword_180021CB8, 0
0x180005cb4  jnz     short loc_180005CC6
0x180005cb6  call    cs:__imp_ReleaseSRWLockExclusive
0x180005cbc  xor     ebx, ebx
0x180005cbe  mov     eax, ebx
0x180005cc0  add     rsp, 20h
0x180005cc4  pop     rbx
0x180005cc5  retn
0x180005cc6  nop
0x180005cc7  mov     ebx, 1
0x180005ccc  mov     cs:dword_180021C74, ebx
0x180005cd2  jmp     short loc_180005C60
```
