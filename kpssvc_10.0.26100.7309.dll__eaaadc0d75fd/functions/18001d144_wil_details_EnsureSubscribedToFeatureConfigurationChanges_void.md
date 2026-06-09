# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x18001d144`
- end: `0x18001d21c`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `216`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001d678`
- `0x18001e3b8`

## callees

- `0x18001d144`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d196`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d1ef`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d196`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d1ef`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d170`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d170`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_18003A364;
  if ( !dword_18003A364 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_18003A368 )
      {
        v1 = dword_18003A364;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_18003A368 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_18003A368,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_18003A368 )
      {
        v1 = 1;
        dword_18003A364 = 1;
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
0x18001d144  mov     [rsp+arg_0], rbx
0x18001d149  push    rdi
0x18001d14a  sub     rsp, 20h
0x18001d14e  mov     ebx, cs:dword_18003A364
0x18001d154  nop
0x18001d155  test    ebx, ebx
0x18001d157  jnz     loc_18001D1FD
0x18001d15d  cmp     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, bl; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18001d163  jz      loc_18001D1FB
0x18001d169  lea     rcx, SRWLock; SRWLock
0x18001d170  call    cs:__imp_AcquireSRWLockExclusive
0x18001d177  nop     dword ptr [rax+rax+00h]
0x18001d17c  mov     rbx, cs:qword_18003A368
0x18001d183  test    rbx, rbx
0x18001d186  jz      short loc_18001D1A4
0x18001d188  mov     ebx, cs:dword_18003A364
0x18001d18e  lea     rcx, SRWLock; SRWLock
0x18001d195  nop
0x18001d196  call    cs:__imp_ReleaseSRWLockExclusive
0x18001d19d  nop     dword ptr [rax+rax+00h]
0x18001d1a2  jmp     short loc_18001D1FD
0x18001d1a4  and     cs:qword_18003A368, 0
0x18001d1ac  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18001d1b3  test    rax, rax
0x18001d1b6  jnz     short loc_18001D1C4
0x18001d1b8  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18001d1bf  test    rax, rax
0x18001d1c2  jz      short loc_18001D1DE
0x18001d1c4  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18001d1cb  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x18001d1d2  lea     rcx, qword_18003A368
0x18001d1d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d1de  cmp     cs:qword_18003A368, 0
0x18001d1e6  lea     rcx, SRWLock; SRWLock
0x18001d1ed  jnz     short loc_18001D20B
0x18001d1ef  call    cs:__imp_ReleaseSRWLockExclusive
0x18001d1f6  nop     dword ptr [rax+rax+00h]
0x18001d1fb  xor     ebx, ebx
0x18001d1fd  mov     eax, ebx
0x18001d1ff  mov     rbx, [rsp+28h+arg_0]
0x18001d204  add     rsp, 20h
0x18001d208  pop     rdi
0x18001d209  retn
0x18001d20b  mov     ebx, 1
0x18001d210  nop
0x18001d211  mov     cs:dword_18003A364, ebx
0x18001d217  jmp     loc_18001D196
```
