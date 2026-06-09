# wistd::__function::__base<void (wil::RegistryChangeKind)>::`scalar deleting destructor'(uint)

- ea: `0x1800083f0`
- end: `0x18000841b`
- name: `??_G?$__base@$$A6AXW4RegistryChangeKind@wil@@@Z@__function@wistd@@UEAAPEAXI@Z`
- size: `43`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callees

- `0x1800024d0`
- `0x1800083f0`

## pseudocode

```c
_QWORD *__fastcall wistd::__function::__base<void (enum wil::RegistryChangeKind)>::`scalar deleting destructor'(
        _QWORD *a1,
        char a2)
{
  *a1 = &wistd::__function::__base<void (enum wil::RegistryChangeKind)>::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(a1, (const struct std::nothrow_t *)8);
  return a1;
}

```

## disassembly

```asm
0x1800083f0  push    rbx
0x1800083f2  sub     rsp, 20h
0x1800083f6  lea     rax, ??_7?$__base@$$A6AXW4RegistryChangeKind@wil@@@Z@__function@wistd@@6B@; const wistd::__function::__base<void (wil::RegistryChangeKind)>::`vftable'
0x1800083fd  mov     rbx, rcx
0x180008400  mov     [rcx], rax
0x180008403  test    dl, 1
0x180008406  jz      short loc_180008412
0x180008408  mov     edx, 8; struct std::nothrow_t *
0x18000840d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180008412  mov     rax, rbx
0x180008415  add     rsp, 20h
0x180008419  pop     rbx
0x18000841a  retn
```
