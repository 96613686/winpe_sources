# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x18000ae90`
- end: `0x18000af5d`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `205`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000cd18`
- `0x18000ce08`
- `0x18000cef8`
- `0x18000e634`

## callees

- `0x18000ae90`
- `0x180024010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x18000aeba`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000aeba`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000aede`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000af37`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000aede`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000af37`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_180030424;
  if ( !dword_180030424 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_180030468 )
      {
        v1 = dword_180030424;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_180030468 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_180030468,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_180030468 )
      {
        v1 = 1;
        dword_180030424 = 1;
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
0x18000ae90  push    rbx
0x18000ae92  sub     rsp, 20h
0x18000ae96  mov     ebx, cs:dword_180030424
0x18000ae9c  nop
0x18000ae9d  test    ebx, ebx
0x18000ae9f  jnz     loc_18000AF45
0x18000aea5  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000aeab  test    eax, eax
0x18000aead  jz      loc_18000AF43
0x18000aeb3  lea     rcx, SRWLock; SRWLock
0x18000aeba  call    cs:__imp_AcquireSRWLockExclusive
0x18000aec1  nop     dword ptr [rax+rax+00h]
0x18000aec6  cmp     cs:qword_180030468, 0
0x18000aece  jz      short loc_18000AEEC
0x18000aed0  mov     ebx, cs:dword_180030424
0x18000aed6  nop
0x18000aed7  lea     rcx, SRWLock; SRWLock
0x18000aede  call    cs:__imp_ReleaseSRWLockExclusive
0x18000aee5  nop     dword ptr [rax+rax+00h]
0x18000aeea  jmp     short loc_18000AF45
0x18000aeec  and     cs:qword_180030468, 0
0x18000aef4  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18000aefb  test    rax, rax
0x18000aefe  jnz     short loc_18000AF0C
0x18000af00  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18000af07  test    rax, rax
0x18000af0a  jz      short loc_18000AF26
0x18000af0c  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000af13  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x18000af1a  lea     rcx, qword_180030468
0x18000af21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af26  lea     rcx, SRWLock; SRWLock
0x18000af2d  cmp     cs:qword_180030468, 0
0x18000af35  jnz     short loc_18000AF4E
0x18000af37  call    cs:__imp_ReleaseSRWLockExclusive
0x18000af3e  nop     dword ptr [rax+rax+00h]
0x18000af43  xor     ebx, ebx
0x18000af45  mov     eax, ebx
0x18000af47  add     rsp, 20h
0x18000af4b  pop     rbx
0x18000af4c  retn
0x18000af4e  nop
0x18000af4f  mov     ebx, 1
0x18000af54  mov     cs:dword_180030424, ebx
0x18000af5a  jmp     short loc_18000AEDE
```
