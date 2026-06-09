# wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)

- ea: `0x140014cb8`
- end: `0x140014d6f`
- name: `?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ`
- size: `183`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140014c90`

## callees

- `0x140014cb8`
- `0x14001f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140014cd7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140014cd7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140014cf3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140014d3c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140014d65`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140014cf3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140014d3c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140014d65`

## pseudocode

```c
__int64 __fastcall wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(
        RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v2; // rbx
  RTL_SRWLOCK *v3; // rsi
  unsigned int Ptr_high; // edi
  void (__fastcall *v6)(RTL_SRWLOCK *, __int64 (__fastcall *)(void *), RTL_SRWLOCK *); // rax

  if ( !LODWORD(this->Ptr) )
    return 0;
  v2 = this + 1;
  AcquireSRWLockExclusive(this + 1);
  v3 = this + 12;
  if ( this[12].Ptr )
  {
    Ptr_high = HIDWORD(this[3].Ptr);
    if ( v2 )
      ReleaseSRWLockExclusive(v2);
    return Ptr_high;
  }
  v3->Ptr = 0;
  v6 = (void (__fastcall *)(RTL_SRWLOCK *, __int64 (__fastcall *)(void *), RTL_SRWLOCK *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
  if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
    || (v6 = (void (__fastcall *)(RTL_SRWLOCK *, __int64 (__fastcall *)(void *), RTL_SRWLOCK *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
  {
    v6(this + 12, _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_, this);
  }
  if ( !v3->Ptr )
  {
    if ( v2 )
      ReleaseSRWLockExclusive(v2);
    return 0;
  }
  HIDWORD(this[3].Ptr) = 1;
  if ( v2 )
    ReleaseSRWLockExclusive(v2);
  return 1;
}

```

## disassembly

```asm
0x140014cb8  mov     [rsp+arg_0], rbx
0x140014cbd  mov     [rsp+arg_8], rsi
0x140014cc2  push    rdi
0x140014cc3  sub     rsp, 20h
0x140014cc7  mov     rdi, rcx
0x140014cca  mov     eax, [rcx]
0x140014ccc  test    eax, eax
0x140014cce  jz      short loc_140014D42
0x140014cd0  lea     rbx, [rcx+8]
0x140014cd4  mov     rcx, rbx; SRWLock
0x140014cd7  call    cs:__imp_AcquireSRWLockExclusive
0x140014cdd  lea     rsi, [rdi+60h]
0x140014ce1  cmp     qword ptr [rsi], 0
0x140014ce5  jz      short loc_140014CFD
0x140014ce7  mov     edi, [rdi+1Ch]
0x140014cea  nop
0x140014ceb  test    rbx, rbx
0x140014cee  jz      short loc_140014CF9
0x140014cf0  mov     rcx, rbx; SRWLock
0x140014cf3  call    cs:__imp_ReleaseSRWLockExclusive
0x140014cf9  mov     eax, edi
0x140014cfb  jmp     short loc_140014D44
0x140014cfd  mov     qword ptr [rsi], 0
0x140014d04  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x140014d0b  test    rax, rax
0x140014d0e  jnz     short loc_140014D1C
0x140014d10  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x140014d17  test    rax, rax
0x140014d1a  jz      short loc_140014D2E
0x140014d1c  mov     r8, rdi
0x140014d1f  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x140014d26  mov     rcx, rsi
0x140014d29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014d2e  cmp     qword ptr [rsi], 0
0x140014d32  jnz     short loc_140014D54
0x140014d34  test    rbx, rbx
0x140014d37  jz      short loc_140014D42
0x140014d39  mov     rcx, rbx; SRWLock
0x140014d3c  call    cs:__imp_ReleaseSRWLockExclusive
0x140014d42  xor     eax, eax
0x140014d44  mov     rbx, [rsp+28h+arg_0]
0x140014d49  mov     rsi, [rsp+28h+arg_8]
0x140014d4e  add     rsp, 20h
0x140014d52  pop     rdi
0x140014d53  retn
0x140014d54  nop
0x140014d55  mov     esi, 1
0x140014d5a  mov     [rdi+1Ch], esi
0x140014d5d  test    rbx, rbx
0x140014d60  jz      short loc_140014D6B
0x140014d62  mov     rcx, rbx; SRWLock
0x140014d65  call    cs:__imp_ReleaseSRWLockExclusive
0x140014d6b  mov     eax, esi
0x140014d6d  jmp     short loc_140014D44
```
