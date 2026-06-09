# wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(_RTL_SRWLOCK *)

- ea: `0x180008e1c`
- end: `0x180008e69`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_SRWLOCK@@@Z`
- size: `77`
- prototype: `void __fastcall(RTL_SRWLOCK **, RTL_SRWLOCK *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000828c`
- `0x180008740`
- `0x180008afc`

## callees

- `0x180003760`
- `0x18000398c`
- `0x180008e1c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008e46`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008e46`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(
        RTL_SRWLOCK **a1,
        RTL_SRWLOCK *a2)
{
  RTL_SRWLOCK *v2; // rdi
  char v5; // [rsp+30h] [rbp+8h] BYREF

  v2 = *a1;
  if ( *a1 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v5);
    ReleaseSRWLockExclusive(v2);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v5);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x180008e1c  mov     [rsp+arg_8], rbx
0x180008e21  mov     [rsp+arg_10], rsi
0x180008e26  push    rdi
0x180008e27  sub     rsp, 20h
0x180008e2b  mov     rdi, [rcx]
0x180008e2e  mov     rsi, rdx
0x180008e31  mov     rbx, rcx
0x180008e34  test    rdi, rdi
0x180008e37  jz      short loc_180008E56
0x180008e39  lea     rcx, [rsp+28h+arg_0]; this
0x180008e3e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180008e43  mov     rcx, rdi; SRWLock
0x180008e46  call    cs:__imp_ReleaseSRWLockExclusive
0x180008e4c  lea     rcx, [rsp+28h+arg_0]; this
0x180008e51  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180008e56  mov     [rbx], rsi
0x180008e59  mov     rbx, [rsp+28h+arg_8]
0x180008e5e  mov     rsi, [rsp+28h+arg_10]
0x180008e63  add     rsp, 20h
0x180008e67  pop     rdi
0x180008e68  retn
```
