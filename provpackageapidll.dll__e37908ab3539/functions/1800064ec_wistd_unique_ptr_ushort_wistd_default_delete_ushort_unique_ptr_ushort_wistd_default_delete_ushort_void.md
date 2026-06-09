# wistd::unique_ptr<ushort,wistd::default_delete<ushort>>::~unique_ptr<ushort,wistd::default_delete<ushort>>(void)

- ea: `0x1800064ec`
- end: `0x180006511`
- name: `??1?$unique_ptr@GU?$default_delete@G@wistd@@@wistd@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18001877c`

## callees

- `0x1800020a8`
- `0x1800064ec`

## pseudocode

```c
void __fastcall wistd::unique_ptr<unsigned short,wistd::default_delete<unsigned short>>::~unique_ptr<unsigned short,wistd::default_delete<unsigned short>>(
        void **a1)
{
  void *v1; // rax

  v1 = *a1;
  *a1 = 0;
  if ( v1 )
    operator delete(v1, (const struct std::nothrow_t *)2);
}

```

## disassembly

```asm
0x1800064ec  sub     rsp, 28h
0x1800064f0  mov     rax, [rcx]
0x1800064f3  mov     qword ptr [rcx], 0
0x1800064fa  test    rax, rax
0x1800064fd  jz      short loc_18000650C
0x1800064ff  mov     edx, 2; struct std::nothrow_t *
0x180006504  mov     rcx, rax; void *
0x180006507  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000650c  add     rsp, 28h
0x180006510  retn
```
