# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180005a90`
- end: `0x180005b4c`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `188`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000798c`

## callees

- `0x180005a90`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005aba`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005aba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005ad8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005b2e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005ad8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005b2e`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_18001425C;
  if ( !dword_18001425C )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_1800142A0 )
      {
        v1 = dword_18001425C;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      qword_1800142A0 = 0;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_1800142A0,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_1800142A0 )
      {
        v1 = 1;
        dword_18001425C = 1;
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
0x180005a90  push    rbx
0x180005a92  sub     rsp, 20h
0x180005a96  mov     ebx, cs:dword_18001425C
0x180005a9c  nop
0x180005a9d  test    ebx, ebx
0x180005a9f  jnz     loc_180005B36
0x180005aa5  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180005aab  test    eax, eax
0x180005aad  jz      loc_180005B34
0x180005ab3  lea     rcx, SRWLock; SRWLock
0x180005aba  call    cs:__imp_AcquireSRWLockExclusive
0x180005ac0  cmp     cs:qword_1800142A0, 0
0x180005ac8  jz      short loc_180005AE0
0x180005aca  mov     ebx, cs:dword_18001425C
0x180005ad0  lea     rcx, SRWLock; SRWLock
0x180005ad7  nop
0x180005ad8  call    cs:__imp_ReleaseSRWLockExclusive
0x180005ade  jmp     short loc_180005B36
0x180005ae0  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180005ae7  mov     cs:qword_1800142A0, 0
0x180005af2  test    rax, rax
0x180005af5  jnz     short loc_180005B03
0x180005af7  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180005afe  test    rax, rax
0x180005b01  jz      short loc_180005B1D
0x180005b03  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180005b0a  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180005b11  lea     rcx, qword_1800142A0
0x180005b18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b1d  cmp     cs:qword_1800142A0, 0
0x180005b25  lea     rcx, SRWLock; SRWLock
0x180005b2c  jnz     short loc_180005B3E
0x180005b2e  call    cs:__imp_ReleaseSRWLockExclusive
0x180005b34  xor     ebx, ebx
0x180005b36  mov     eax, ebx
0x180005b38  add     rsp, 20h
0x180005b3c  pop     rbx
0x180005b3d  retn
0x180005b3e  mov     ebx, 1
0x180005b43  nop
0x180005b44  mov     cs:dword_18001425C, ebx
0x180005b4a  jmp     short loc_180005AD8
```
