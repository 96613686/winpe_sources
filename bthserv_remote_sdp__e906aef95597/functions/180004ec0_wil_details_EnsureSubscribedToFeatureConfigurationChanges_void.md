# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180004ec0`
- end: `0x180004f8d`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `205`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `17`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180005fb4`
- `0x18000fbb0`
- `0x18000fc98`
- `0x18000fe10`
- `0x1800284ec`
- `0x1800285d4`
- `0x1800286bc`
- `0x1800287a4`
- `0x18002891c`
- `0x180028a94`
- `0x180028c0c`
- `0x180028cf4`
- `0x180028ddc`
- `0x180028ec4`
- `0x18002903c`
- `0x180029124`
- `0x18002920c`

## callees

- `0x180004ec0`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004f0e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004f67`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004f0e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004f67`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004eea`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004eea`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_1800464C4;
  if ( !dword_1800464C4 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_180046508 )
      {
        v1 = dword_1800464C4;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_180046508 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_180046508,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_180046508 )
      {
        v1 = 1;
        dword_1800464C4 = 1;
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
0x180004ec0  push    rbx
0x180004ec2  sub     rsp, 20h
0x180004ec6  mov     ebx, cs:dword_1800464C4
0x180004ecc  nop
0x180004ecd  test    ebx, ebx
0x180004ecf  jnz     loc_180004F75
0x180004ed5  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180004edb  test    eax, eax
0x180004edd  jz      loc_180004F73
0x180004ee3  lea     rcx, SRWLock; SRWLock
0x180004eea  call    cs:__imp_AcquireSRWLockExclusive
0x180004ef1  nop     dword ptr [rax+rax+00h]
0x180004ef6  cmp     cs:qword_180046508, 0
0x180004efe  jz      short loc_180004F1C
0x180004f00  mov     ebx, cs:dword_1800464C4
0x180004f06  nop
0x180004f07  lea     rcx, SRWLock; SRWLock
0x180004f0e  call    cs:__imp_ReleaseSRWLockExclusive
0x180004f15  nop     dword ptr [rax+rax+00h]
0x180004f1a  jmp     short loc_180004F75
0x180004f1c  and     cs:qword_180046508, 0
0x180004f24  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180004f2b  test    rax, rax
0x180004f2e  jnz     short loc_180004F3C
0x180004f30  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180004f37  test    rax, rax
0x180004f3a  jz      short loc_180004F56
0x180004f3c  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180004f43  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180004f4a  lea     rcx, qword_180046508
0x180004f51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f56  lea     rcx, SRWLock; SRWLock
0x180004f5d  cmp     cs:qword_180046508, 0
0x180004f65  jnz     short loc_180004F7E
0x180004f67  call    cs:__imp_ReleaseSRWLockExclusive
0x180004f6e  nop     dword ptr [rax+rax+00h]
0x180004f73  xor     ebx, ebx
0x180004f75  mov     eax, ebx
0x180004f77  add     rsp, 20h
0x180004f7b  pop     rbx
0x180004f7c  retn
0x180004f7e  nop
0x180004f7f  mov     ebx, 1
0x180004f84  mov     cs:dword_1800464C4, ebx
0x180004f8a  jmp     short loc_180004F0E
```
