# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180017618`
- end: `0x1800176d5`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `189`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180017abc`
- `0x180018548`

## callees

- `0x180017618`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017642`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017642`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017660`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800176b6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017660`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800176b6`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_18005263C;
  if ( !dword_18005263C )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_180052628);
      if ( qword_180052680 )
      {
        v1 = dword_18005263C;
LABEL_5:
        ReleaseSRWLockExclusive(&stru_180052628);
        return v1;
      }
      qword_180052680 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_180052680,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_180052680 )
      {
        v1 = 1;
        dword_18005263C = 1;
        goto LABEL_5;
      }
      ReleaseSRWLockExclusive(&stru_180052628);
    }
    return 0;
  }
  return v1;
}

```

## disassembly

```asm
0x180017618  push    rbx
0x18001761a  sub     rsp, 20h
0x18001761e  mov     ebx, cs:dword_18005263C
0x180017624  nop
0x180017625  test    ebx, ebx
0x180017627  jnz     loc_1800176BE
0x18001762d  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180017633  test    eax, eax
0x180017635  jz      loc_1800176BC
0x18001763b  lea     rcx, stru_180052628; SRWLock
0x180017642  call    cs:__imp_AcquireSRWLockExclusive
0x180017648  cmp     cs:qword_180052680, 0
0x180017650  jz      short loc_180017668
0x180017652  mov     ebx, cs:dword_18005263C
0x180017658  nop
0x180017659  lea     rcx, stru_180052628; SRWLock
0x180017660  call    cs:__imp_ReleaseSRWLockExclusive
0x180017666  jmp     short loc_1800176BE
0x180017668  mov     cs:qword_180052680, 0
0x180017673  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18001767a  test    rax, rax
0x18001767d  jnz     short loc_18001768B
0x18001767f  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180017686  test    rax, rax
0x180017689  jz      short loc_1800176A5
0x18001768b  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180017692  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180017699  lea     rcx, qword_180052680
0x1800176a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800176a5  lea     rcx, stru_180052628; SRWLock
0x1800176ac  cmp     cs:qword_180052680, 0
0x1800176b4  jnz     short loc_1800176C6
0x1800176b6  call    cs:__imp_ReleaseSRWLockExclusive
0x1800176bc  xor     ebx, ebx
0x1800176be  mov     eax, ebx
0x1800176c0  add     rsp, 20h
0x1800176c4  pop     rbx
0x1800176c5  retn
0x1800176c6  nop
0x1800176c7  mov     ebx, 1
0x1800176cc  mov     cs:dword_18005263C, ebx
0x1800176d2  jmp     short loc_180017660
```
