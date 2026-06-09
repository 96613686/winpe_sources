# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x1800239b0`
- end: `0x180023a69`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `185`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180023f10`
- `0x180024120`
- `0x180025030`
- `0x18002cef0`
- `0x18002d0d0`
- `0x18002d2e0`
- `0x18002d4e0`

## callees

- `0x1800239b0`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800239da`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800239da`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800239f8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180023a57`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800239f8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180023a57`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  __int64 result; // rax
  unsigned int v2; // ebx
  void (__fastcall *v3)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  result = (unsigned int)dword_18003C42C;
  if ( !dword_18003C42C )
  {
    if ( !wil::details::g_enabledStateManager )
      return 0;
    AcquireSRWLockExclusive(&SRWLock);
    if ( qword_18003C470 )
    {
      v2 = dword_18003C42C;
    }
    else
    {
      v2 = 0;
      qword_18003C470 = 0;
      v3 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v3 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v3(
          &qword_18003C470,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
        if ( qword_18003C470 )
        {
          v2 = 1;
          dword_18003C42C = 1;
          ReleaseSRWLockExclusive(&SRWLock);
          return v2;
        }
      }
    }
    ReleaseSRWLockExclusive(&SRWLock);
    return v2;
  }
  return result;
}

```

## disassembly

```asm
0x1800239b0  push    rbx
0x1800239b2  sub     rsp, 20h
0x1800239b6  mov     eax, cs:dword_18003C42C
0x1800239bc  nop
0x1800239bd  test    eax, eax
0x1800239bf  jnz     loc_180023A63
0x1800239c5  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800239cb  test    eax, eax
0x1800239cd  jz      loc_180023A5F
0x1800239d3  lea     rcx, SRWLock; SRWLock
0x1800239da  call    cs:__imp_AcquireSRWLockExclusive
0x1800239e0  cmp     cs:qword_18003C470, 0
0x1800239e8  jz      short loc_180023A00
0x1800239ea  mov     ebx, cs:dword_18003C42C
0x1800239f0  nop
0x1800239f1  lea     rcx, SRWLock; SRWLock
0x1800239f8  call    cs:__imp_ReleaseSRWLockExclusive
0x1800239fe  jmp     short loc_180023A61
0x180023a00  xor     ebx, ebx
0x180023a02  mov     cs:qword_18003C470, rbx
0x180023a09  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180023a10  test    rax, rax
0x180023a13  jnz     short loc_180023A21
0x180023a15  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180023a1c  test    rax, rax
0x180023a1f  jz      short loc_1800239F1
0x180023a21  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180023a28  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180023a2f  lea     rcx, qword_18003C470
0x180023a36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023a3b  cmp     cs:qword_18003C470, rbx
0x180023a42  jz      short loc_1800239F1
0x180023a44  nop
0x180023a45  mov     ebx, 1
0x180023a4a  mov     cs:dword_18003C42C, ebx
0x180023a50  lea     rcx, SRWLock; SRWLock
0x180023a57  call    cs:__imp_ReleaseSRWLockExclusive
0x180023a5d  jmp     short loc_180023A61
0x180023a5f  xor     ebx, ebx
0x180023a61  mov     eax, ebx
0x180023a63  add     rsp, 20h
0x180023a67  pop     rbx
0x180023a68  retn
```
