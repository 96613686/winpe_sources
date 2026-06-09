# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x18000ad30`
- end: `0x18000aded`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `189`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000c384`
- `0x18000c464`
- `0x18000c544`
- `0x18000c6c4`
- `0x18000dbf4`

## callees

- `0x18000ad30`
- `0x180023010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x18000ad5a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000ad5a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000ad78`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000adce`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000ad78`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000adce`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_18002F4B4;
  if ( !dword_18002F4B4 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_18002F4F8 )
      {
        v1 = dword_18002F4B4;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_18002F4F8 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_18002F4F8,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_18002F4F8 )
      {
        v1 = 1;
        dword_18002F4B4 = 1;
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
0x18000ad30  push    rbx
0x18000ad32  sub     rsp, 20h
0x18000ad36  mov     ebx, cs:dword_18002F4B4
0x18000ad3c  nop
0x18000ad3d  test    ebx, ebx
0x18000ad3f  jnz     loc_18000ADD6
0x18000ad45  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000ad4b  test    eax, eax
0x18000ad4d  jz      loc_18000ADD4
0x18000ad53  lea     rcx, SRWLock; SRWLock
0x18000ad5a  call    cs:__imp_AcquireSRWLockExclusive
0x18000ad60  cmp     cs:qword_18002F4F8, 0
0x18000ad68  jz      short loc_18000AD80
0x18000ad6a  mov     ebx, cs:dword_18002F4B4
0x18000ad70  nop
0x18000ad71  lea     rcx, SRWLock; SRWLock
0x18000ad78  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ad7e  jmp     short loc_18000ADD6
0x18000ad80  mov     cs:qword_18002F4F8, 0
0x18000ad8b  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18000ad92  test    rax, rax
0x18000ad95  jnz     short loc_18000ADA3
0x18000ad97  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18000ad9e  test    rax, rax
0x18000ada1  jz      short loc_18000ADBD
0x18000ada3  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000adaa  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x18000adb1  lea     rcx, qword_18002F4F8
0x18000adb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adbd  lea     rcx, SRWLock; SRWLock
0x18000adc4  cmp     cs:qword_18002F4F8, 0
0x18000adcc  jnz     short loc_18000ADDE
0x18000adce  call    cs:__imp_ReleaseSRWLockExclusive
0x18000add4  xor     ebx, ebx
0x18000add6  mov     eax, ebx
0x18000add8  add     rsp, 20h
0x18000addc  pop     rbx
0x18000addd  retn
0x18000adde  nop
0x18000addf  mov     ebx, 1
0x18000ade4  mov     cs:dword_18002F4B4, ebx
0x18000adea  jmp     short loc_18000AD78
```
