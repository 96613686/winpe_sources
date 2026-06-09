# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x1800084b4`
- end: `0x180008571`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `189`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `12`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180008aa0`
- `0x180008c74`
- `0x180008d54`
- `0x180008ec8`
- `0x18000903c`
- `0x1800091b0`
- `0x180009330`
- `0x180009410`
- `0x1800094f0`
- `0x1800095d0`
- `0x1800096b0`
- `0x18000ab34`

## callees

- `0x1800084b4`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800084fc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008552`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800084fc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008552`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800084de`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800084de`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_18001D394;
  if ( !dword_18001D394 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_18001D3D8 )
      {
        v1 = dword_18001D394;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_18001D3D8 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_18001D3D8,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_18001D3D8 )
      {
        v1 = 1;
        dword_18001D394 = 1;
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
0x1800084b4  push    rbx
0x1800084b6  sub     rsp, 20h
0x1800084ba  mov     ebx, cs:dword_18001D394
0x1800084c0  nop
0x1800084c1  test    ebx, ebx
0x1800084c3  jnz     loc_18000855A
0x1800084c9  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800084cf  test    eax, eax
0x1800084d1  jz      loc_180008558
0x1800084d7  lea     rcx, SRWLock; SRWLock
0x1800084de  call    cs:__imp_AcquireSRWLockExclusive
0x1800084e4  cmp     cs:qword_18001D3D8, 0
0x1800084ec  jz      short loc_180008504
0x1800084ee  mov     ebx, cs:dword_18001D394
0x1800084f4  nop
0x1800084f5  lea     rcx, SRWLock; SRWLock
0x1800084fc  call    cs:__imp_ReleaseSRWLockExclusive
0x180008502  jmp     short loc_18000855A
0x180008504  mov     cs:qword_18001D3D8, 0
0x18000850f  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180008516  test    rax, rax
0x180008519  jnz     short loc_180008527
0x18000851b  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180008522  test    rax, rax
0x180008525  jz      short loc_180008541
0x180008527  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000852e  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180008535  lea     rcx, qword_18001D3D8
0x18000853c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008541  lea     rcx, SRWLock; SRWLock
0x180008548  cmp     cs:qword_18001D3D8, 0
0x180008550  jnz     short loc_180008562
0x180008552  call    cs:__imp_ReleaseSRWLockExclusive
0x180008558  xor     ebx, ebx
0x18000855a  mov     eax, ebx
0x18000855c  add     rsp, 20h
0x180008560  pop     rbx
0x180008561  retn
0x180008562  nop
0x180008563  mov     ebx, 1
0x180008568  mov     cs:dword_18001D394, ebx
0x18000856e  jmp     short loc_1800084FC
```
