# wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::~unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>(void)

- ea: `0x180005fec`
- end: `0x18000600c`
- name: `??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(void **, const struct std::nothrow_t *)`
- caller_count: `22`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800185b8`
- `0x18001861a`
- `0x180018630`
- `0x18001866e`
- `0x180018680`
- `0x1800186da`
- `0x1800186ec`
- `0x1800186fe`
- `0x180018734`
- `0x1800187d5`
- `0x1800187e7`
- `0x1800187f9`
- `0x180018853`
- `0x180018877`
- `0x1800188ad`
- `0x1800188d1`
- `0x180018a03`
- `0x180018a15`
- `0x180018a87`
- `0x180018a9d`
- `0x180018ab3`
- `0x180018ac9`

## callees

- `0x1800020a8`
- `0x180005fec`

## pseudocode

```c
void __fastcall wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::~unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>(
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
0x180005fec  sub     rsp, 28h
0x180005ff0  mov     rax, [rcx]
0x180005ff3  mov     qword ptr [rcx], 0
0x180005ffa  test    rax, rax
0x180005ffd  jz      short loc_180006007
0x180005fff  mov     rcx, rax; void *
0x180006002  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006007  add     rsp, 28h
0x18000600b  retn
```
