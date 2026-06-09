# wil::details::close_invoke_helper<1,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wil::details::registry_watcher_state *>::close_reset(wil::details::registry_watcher_state *)

- ea: `0x180008afc`
- end: `0x180008b79`
- name: `?close_reset@?$close_invoke_helper@$00P6AXPEAUregistry_watcher_state@details@wil@@@Z$1?delete_registry_watcher_state@23@YAX0@ZPEAU123@@details@wil@@SAXPEAUregistry_watcher_state@23@@Z`
- size: `125`
- prototype: `void __fastcall(wil::details::registry_watcher_state *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180008e70`

## callees

- `0x180003760`
- `0x18000398c`
- `0x180008464`
- `0x180008afc`
- `0x180008e1c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008b1d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008b1d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008b5e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008b5e`

## pseudocode

```c
void __fastcall wil::details::close_invoke_helper<1,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wil::details::registry_watcher_state *>::close_reset(
        wil::details::registry_watcher_state *this)
{
  RTL_SRWLOCK *v2; // rbx
  RTL_SRWLOCK *v3; // [rsp+30h] [rbp+8h] BYREF
  char v4; // [rsp+38h] [rbp+10h] BYREF

  wil::last_error_context::last_error_context((wil::last_error_context *)&v4);
  v2 = (RTL_SRWLOCK *)((char *)this + 152);
  AcquireSRWLockExclusive((PSRWLOCK)this + 19);
  v3 = (RTL_SRWLOCK *)((char *)this + 152);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 37, 0xFFFFFFFF) == 1 )
  {
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(
      &v3,
      0);
    if ( this )
      wil::details::registry_watcher_state::`scalar deleting destructor'(this);
    v2 = v3;
  }
  if ( v2 )
    ReleaseSRWLockExclusive(v2);
  wil::last_error_context::~last_error_context((wil::last_error_context *)&v4);
}

```

## disassembly

```asm
0x180008afc  mov     [rsp+arg_10], rbx
0x180008b01  push    rdi
0x180008b02  sub     rsp, 20h
0x180008b06  mov     rdi, rcx
0x180008b09  lea     rcx, [rsp+28h+arg_8]; this
0x180008b0e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180008b13  lea     rbx, [rdi+98h]
0x180008b1a  mov     rcx, rbx; SRWLock
0x180008b1d  call    cs:__imp_AcquireSRWLockExclusive
0x180008b23  or      eax, 0FFFFFFFFh
0x180008b26  mov     [rsp+28h+arg_0], rbx
0x180008b2b  lock xadd [rdi+94h], eax
0x180008b33  cmp     eax, 1
0x180008b36  jnz     short loc_180008B56
0x180008b38  xor     edx, edx
0x180008b3a  lea     rcx, [rsp+28h+arg_0]
0x180008b3f  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_SRWLOCK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(_RTL_SRWLOCK *)
0x180008b44  test    rdi, rdi
0x180008b47  jz      short loc_180008B51
0x180008b49  mov     rcx, rdi; this
0x180008b4c  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x180008b51  mov     rbx, [rsp+28h+arg_0]
0x180008b56  test    rbx, rbx
0x180008b59  jz      short loc_180008B64
0x180008b5b  mov     rcx, rbx; SRWLock
0x180008b5e  call    cs:__imp_ReleaseSRWLockExclusive
0x180008b64  lea     rcx, [rsp+28h+arg_8]; this
0x180008b69  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180008b6e  mov     rbx, [rsp+28h+arg_10]
0x180008b73  add     rsp, 20h
0x180008b77  pop     rdi
0x180008b78  retn
```
