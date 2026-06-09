# wistd::__function::__func__lambda_3f78a9971162bd1363a0366959f5b7c1__void___cdecl(enum_wil::RegistryChangeKind)_::_scalar_deleting_destructor_

- ea: `0x180008430`
- end: `0x18000845b`
- name: `wistd::__function::__func__lambda_3f78a9971162bd1363a0366959f5b7c1__void___cdecl(enum_wil::RegistryChangeKind)_::_scalar_deleting_destructor_`
- size: `43`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callees

- `0x1800024d0`
- `0x180008430`

## pseudocode

```c
_QWORD *__fastcall wistd::__function::__func__lambda_3f78a9971162bd1363a0366959f5b7c1__void___cdecl_enum_wil::RegistryChangeKind__::_scalar_deleting_destructor_(
        _QWORD *a1,
        char a2)
{
  *a1 = &wistd::__function::__base<void (enum wil::RegistryChangeKind)>::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(a1, (const struct std::nothrow_t *)0x10);
  return a1;
}

```

## disassembly

```asm
0x180008430  push    rbx
0x180008432  sub     rsp, 20h
0x180008436  lea     rax, ??_7?$__base@$$A6AXW4RegistryChangeKind@wil@@@Z@__function@wistd@@6B@; const wistd::__function::__base<void (wil::RegistryChangeKind)>::`vftable'
0x18000843d  mov     rbx, rcx
0x180008440  mov     [rcx], rax
0x180008443  test    dl, 1
0x180008446  jz      short loc_180008452
0x180008448  mov     edx, 10h; struct std::nothrow_t *
0x18000844d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180008452  mov     rax, rbx
0x180008455  add     rsp, 20h
0x180008459  pop     rbx
0x18000845a  retn
```
