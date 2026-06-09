# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x140004d88`
- end: `0x140004e5b`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `211`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400052e0`
- `0x140005fe0`
- `0x14000f964`
- `0x14000fadc`

## callees

- `0x140004d88`
- `0x140017010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140004db2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140004db2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140004dd6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140004e32`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140004dd6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140004e32`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_140023A04;
  if ( !dword_140023A04 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_1400239F0);
      if ( qword_140023A08 )
      {
        v1 = dword_140023A04;
LABEL_5:
        ReleaseSRWLockExclusive(&stru_1400239F0);
        return v1;
      }
      qword_140023A08 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_140023A08,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_140023A08 )
      {
        v1 = 1;
        dword_140023A04 = 1;
        goto LABEL_5;
      }
      ReleaseSRWLockExclusive(&stru_1400239F0);
    }
    return 0;
  }
  return v1;
}

```

## disassembly

```asm
0x140004d88  push    rbx
0x140004d8a  sub     rsp, 20h
0x140004d8e  mov     ebx, cs:dword_140023A04
0x140004d94  nop
0x140004d95  test    ebx, ebx
0x140004d97  jnz     loc_140004E40
0x140004d9d  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x140004da3  test    eax, eax
0x140004da5  jz      loc_140004E3E
0x140004dab  lea     rcx, stru_1400239F0; SRWLock
0x140004db2  call    cs:__imp_AcquireSRWLockExclusive
0x140004db9  nop     dword ptr [rax+rax+00h]
0x140004dbe  cmp     cs:qword_140023A08, 0
0x140004dc6  jz      short loc_140004DE4
0x140004dc8  mov     ebx, cs:dword_140023A04
0x140004dce  nop
0x140004dcf  lea     rcx, stru_1400239F0; SRWLock
0x140004dd6  call    cs:__imp_ReleaseSRWLockExclusive
0x140004ddd  nop     dword ptr [rax+rax+00h]
0x140004de2  jmp     short loc_140004E40
0x140004de4  mov     cs:qword_140023A08, 0
0x140004def  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x140004df6  test    rax, rax
0x140004df9  jnz     short loc_140004E07
0x140004dfb  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x140004e02  test    rax, rax
0x140004e05  jz      short loc_140004E21
0x140004e07  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x140004e0e  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x140004e15  lea     rcx, qword_140023A08
0x140004e1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004e21  lea     rcx, stru_1400239F0; SRWLock
0x140004e28  cmp     cs:qword_140023A08, 0
0x140004e30  jnz     short loc_140004E49
0x140004e32  call    cs:__imp_ReleaseSRWLockExclusive
0x140004e39  nop     dword ptr [rax+rax+00h]
0x140004e3e  xor     ebx, ebx
0x140004e40  mov     eax, ebx
0x140004e42  add     rsp, 20h
0x140004e46  pop     rbx
0x140004e47  retn
0x140004e49  nop
0x140004e4a  mov     ebx, 1
0x140004e4f  mov     cs:dword_140023A04, ebx
0x140004e55  jmp     loc_140004DD6
```
