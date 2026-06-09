# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x18000bdd8`
- end: `0x18000beab`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `211`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000ca60`
- `0x18000ded4`

## callees

- `0x18000bdd8`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000be26`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000be82`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000be26`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000be82`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000be02`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000be02`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_180032914;
  if ( !dword_180032914 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_180032918 )
      {
        v1 = dword_180032914;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_180032918 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_180032918,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_180032918 )
      {
        v1 = 1;
        dword_180032914 = 1;
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
0x18000bdd8  push    rbx
0x18000bdda  sub     rsp, 20h
0x18000bdde  mov     ebx, cs:dword_180032914
0x18000bde4  nop
0x18000bde5  test    ebx, ebx
0x18000bde7  jnz     loc_18000BE90
0x18000bded  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000bdf3  test    eax, eax
0x18000bdf5  jz      loc_18000BE8E
0x18000bdfb  lea     rcx, SRWLock; SRWLock
0x18000be02  call    cs:__imp_AcquireSRWLockExclusive
0x18000be09  nop     dword ptr [rax+rax+00h]
0x18000be0e  cmp     cs:qword_180032918, 0
0x18000be16  jz      short loc_18000BE34
0x18000be18  mov     ebx, cs:dword_180032914
0x18000be1e  nop
0x18000be1f  lea     rcx, SRWLock; SRWLock
0x18000be26  call    cs:__imp_ReleaseSRWLockExclusive
0x18000be2d  nop     dword ptr [rax+rax+00h]
0x18000be32  jmp     short loc_18000BE90
0x18000be34  mov     cs:qword_180032918, 0
0x18000be3f  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18000be46  test    rax, rax
0x18000be49  jnz     short loc_18000BE57
0x18000be4b  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18000be52  test    rax, rax
0x18000be55  jz      short loc_18000BE71
0x18000be57  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000be5e  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x18000be65  lea     rcx, qword_180032918
0x18000be6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be71  lea     rcx, SRWLock; SRWLock
0x18000be78  cmp     cs:qword_180032918, 0
0x18000be80  jnz     short loc_18000BE99
0x18000be82  call    cs:__imp_ReleaseSRWLockExclusive
0x18000be89  nop     dword ptr [rax+rax+00h]
0x18000be8e  xor     ebx, ebx
0x18000be90  mov     eax, ebx
0x18000be92  add     rsp, 20h
0x18000be96  pop     rbx
0x18000be97  retn
0x18000be99  nop
0x18000be9a  mov     ebx, 1
0x18000be9f  mov     cs:dword_180032914, ebx
0x18000bea5  jmp     loc_18000BE26
```
