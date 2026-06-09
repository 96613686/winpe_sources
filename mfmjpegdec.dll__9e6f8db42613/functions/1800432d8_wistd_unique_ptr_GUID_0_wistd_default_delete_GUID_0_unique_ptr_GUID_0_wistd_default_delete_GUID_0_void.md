# wistd::unique_ptr<_GUID [0],wistd::default_delete<_GUID [0]>>::~unique_ptr<_GUID [0],wistd::default_delete<_GUID [0]>>(void)

- ea: `0x1800432d8`
- end: `0x1800432f8`
- name: `??1?$unique_ptr@$$BY0A@U_GUID@@U?$default_delete@$$BY0A@U_GUID@@@wistd@@@wistd@@QEAA@XZ`
- size: `32`
- prototype: ``
- caller_count: `12`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18003f120`
- `0x18003f15c`
- `0x18003f930`
- `0x180048ac4`
- `0x180049e90`
- `0x18004a1b8`
- `0x1800513a0`
- `0x180051900`
- `0x180054e08`
- `0x18006f410`
- `0x18006f46a`
- `0x18006f47c`

## callees

- `0x1800245f0`
- `0x1800432d8`

## pseudocode

```c
void __fastcall wistd::unique_ptr<_GUID [0],wistd::default_delete<_GUID [0]>>::~unique_ptr<_GUID [0],wistd::default_delete<_GUID [0]>>(
        void **a1,
        const struct std::nothrow_t *a2)
{
  void *v2; // rax

  v2 = *a1;
  *a1 = 0;
  if ( v2 )
    operator delete(v2, a2);
}

```

## disassembly

```asm
0x1800432d8  sub     rsp, 28h
0x1800432dc  mov     rax, [rcx]
0x1800432df  mov     qword ptr [rcx], 0
0x1800432e6  test    rax, rax
0x1800432e9  jz      short loc_1800432F3
0x1800432eb  mov     rcx, rax; void *
0x1800432ee  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800432f3  add     rsp, 28h
0x1800432f7  retn
```
