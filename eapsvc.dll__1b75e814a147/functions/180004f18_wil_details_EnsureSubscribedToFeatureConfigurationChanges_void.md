# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180004f18`
- end: `0x180004fd5`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `189`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000612c`
- `0x18000af50`
- `0x18000b124`
- `0x18000b2a4`

## callees

- `0x180004f18`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004f42`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004f42`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004f60`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004fb6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004f60`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004fb6`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_180020774;
  if ( !dword_180020774 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_1800207B8 )
      {
        v1 = dword_180020774;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_1800207B8 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_1800207B8,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_1800207B8 )
      {
        v1 = 1;
        dword_180020774 = 1;
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
0x180004f18  push    rbx
0x180004f1a  sub     rsp, 20h
0x180004f1e  mov     ebx, cs:dword_180020774
0x180004f24  nop
0x180004f25  test    ebx, ebx
0x180004f27  jnz     loc_180004FBE
0x180004f2d  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180004f33  test    eax, eax
0x180004f35  jz      loc_180004FBC
0x180004f3b  lea     rcx, SRWLock; SRWLock
0x180004f42  call    cs:__imp_AcquireSRWLockExclusive
0x180004f48  cmp     cs:qword_1800207B8, 0
0x180004f50  jz      short loc_180004F68
0x180004f52  mov     ebx, cs:dword_180020774
0x180004f58  nop
0x180004f59  lea     rcx, SRWLock; SRWLock
0x180004f60  call    cs:__imp_ReleaseSRWLockExclusive
0x180004f66  jmp     short loc_180004FBE
0x180004f68  mov     cs:qword_1800207B8, 0
0x180004f73  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180004f7a  test    rax, rax
0x180004f7d  jnz     short loc_180004F8B
0x180004f7f  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180004f86  test    rax, rax
0x180004f89  jz      short loc_180004FA5
0x180004f8b  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180004f92  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180004f99  lea     rcx, qword_1800207B8
0x180004fa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fa5  lea     rcx, SRWLock; SRWLock
0x180004fac  cmp     cs:qword_1800207B8, 0
0x180004fb4  jnz     short loc_180004FC6
0x180004fb6  call    cs:__imp_ReleaseSRWLockExclusive
0x180004fbc  xor     ebx, ebx
0x180004fbe  mov     eax, ebx
0x180004fc0  add     rsp, 20h
0x180004fc4  pop     rbx
0x180004fc5  retn
0x180004fc6  nop
0x180004fc7  mov     ebx, 1
0x180004fcc  mov     cs:dword_180020774, ebx
0x180004fd2  jmp     short loc_180004F60
```
