# wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>(void)

- ea: `0x18000828c`
- end: `0x1800082f5`
- name: `??1?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `105`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800082fc`
- `0x1800084f4`
- `0x18000965d`

## callees

- `0x18000828c`
- `0x180008464`
- `0x180008e1c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800082a8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800082a8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800082e4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800082e4`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>(
        __int64 *a1)
{
  __int64 v1; // rdi
  RTL_SRWLOCK *v2; // rbx
  unsigned int v3; // edx
  RTL_SRWLOCK *v4; // [rsp+30h] [rbp+8h] BYREF

  v1 = *a1;
  if ( *a1 )
  {
    v2 = (RTL_SRWLOCK *)(v1 + 152);
    AcquireSRWLockExclusive((PSRWLOCK)(v1 + 152));
    v4 = (RTL_SRWLOCK *)(v1 + 152);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v1 + 148), 0xFFFFFFFF) == 1 )
    {
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(
        &v4,
        0);
      wil::details::registry_watcher_state::`scalar deleting destructor'((wil::details::registry_watcher_state *)v1, v3);
      v2 = v4;
    }
    if ( v2 )
      ReleaseSRWLockExclusive(v2);
  }
}

```

## disassembly

```asm
0x18000828c  mov     [rsp+arg_8], rbx
0x180008291  push    rdi
0x180008292  sub     rsp, 20h
0x180008296  mov     rdi, [rcx]
0x180008299  test    rdi, rdi
0x18000829c  jz      short loc_1800082EA
0x18000829e  lea     rbx, [rdi+98h]
0x1800082a5  mov     rcx, rbx; SRWLock
0x1800082a8  call    cs:__imp_AcquireSRWLockExclusive
0x1800082ae  or      eax, 0FFFFFFFFh
0x1800082b1  mov     [rsp+28h+arg_0], rbx
0x1800082b6  lock xadd [rdi+94h], eax
0x1800082be  cmp     eax, 1
0x1800082c1  jnz     short loc_1800082DC
0x1800082c3  xor     edx, edx
0x1800082c5  lea     rcx, [rsp+28h+arg_0]
0x1800082ca  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_SRWLOCK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(_RTL_SRWLOCK *)
0x1800082cf  mov     rcx, rdi; this
0x1800082d2  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x1800082d7  mov     rbx, [rsp+28h+arg_0]
0x1800082dc  test    rbx, rbx
0x1800082df  jz      short loc_1800082EA
0x1800082e1  mov     rcx, rbx; SRWLock
0x1800082e4  call    cs:__imp_ReleaseSRWLockExclusive
0x1800082ea  mov     rbx, [rsp+28h+arg_8]
0x1800082ef  add     rsp, 20h
0x1800082f3  pop     rdi
0x1800082f4  retn
```
