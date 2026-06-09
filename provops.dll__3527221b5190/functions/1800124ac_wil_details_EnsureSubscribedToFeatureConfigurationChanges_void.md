# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x1800124ac`
- end: `0x180012569`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `189`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180012918`
- `0x180012aec`
- `0x180012c6c`
- `0x1800130b0`

## callees

- `0x1800124ac`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800124d6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800124d6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800124f4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001254a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800124f4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001254a`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_18004A4A4;
  if ( !dword_18004A4A4 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_18004A490);
      if ( qword_18004A4E8 )
      {
        v1 = dword_18004A4A4;
LABEL_5:
        ReleaseSRWLockExclusive(&stru_18004A490);
        return v1;
      }
      qword_18004A4E8 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_18004A4E8,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_18004A4E8 )
      {
        v1 = 1;
        dword_18004A4A4 = 1;
        goto LABEL_5;
      }
      ReleaseSRWLockExclusive(&stru_18004A490);
    }
    return 0;
  }
  return v1;
}

```

## disassembly

```asm
0x1800124ac  push    rbx
0x1800124ae  sub     rsp, 20h
0x1800124b2  mov     ebx, cs:dword_18004A4A4
0x1800124b8  nop
0x1800124b9  test    ebx, ebx
0x1800124bb  jnz     loc_180012552
0x1800124c1  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800124c7  test    eax, eax
0x1800124c9  jz      loc_180012550
0x1800124cf  lea     rcx, stru_18004A490; SRWLock
0x1800124d6  call    cs:__imp_AcquireSRWLockExclusive
0x1800124dc  cmp     cs:qword_18004A4E8, 0
0x1800124e4  jz      short loc_1800124FC
0x1800124e6  mov     ebx, cs:dword_18004A4A4
0x1800124ec  nop
0x1800124ed  lea     rcx, stru_18004A490; SRWLock
0x1800124f4  call    cs:__imp_ReleaseSRWLockExclusive
0x1800124fa  jmp     short loc_180012552
0x1800124fc  mov     cs:qword_18004A4E8, 0
0x180012507  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18001250e  test    rax, rax
0x180012511  jnz     short loc_18001251F
0x180012513  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18001251a  test    rax, rax
0x18001251d  jz      short loc_180012539
0x18001251f  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180012526  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x18001252d  lea     rcx, qword_18004A4E8
0x180012534  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012539  lea     rcx, stru_18004A490; SRWLock
0x180012540  cmp     cs:qword_18004A4E8, 0
0x180012548  jnz     short loc_18001255A
0x18001254a  call    cs:__imp_ReleaseSRWLockExclusive
0x180012550  xor     ebx, ebx
0x180012552  mov     eax, ebx
0x180012554  add     rsp, 20h
0x180012558  pop     rbx
0x180012559  retn
0x18001255a  nop
0x18001255b  mov     ebx, 1
0x180012560  mov     cs:dword_18004A4A4, ebx
0x180012566  jmp     short loc_1800124F4
```
