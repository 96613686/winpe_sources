# NullDecompress

- ea: `0x1800177f0`
- end: `0x180017837`
- name: `NullDecompress`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800177f0`
- `0x18001b625`

## pseudocode

```c
__int64 __fastcall NullDecompress(__int64 a1, const void *a2, size_t a3, void *a4, size_t a5, size_t *a6)
{
  if ( a3 )
  {
    if ( a5 == a3 )
    {
      memcpy_0(a4, a2, a3);
      *a6 = a3;
      return 0;
    }
    else
    {
      return 605;
    }
  }
  else
  {
    *a6 = a5;
    return 122;
  }
}

```

## disassembly

```asm
0x1800177f0  push    rbx
0x1800177f2  sub     rsp, 20h
0x1800177f6  mov     rbx, r8
0x1800177f9  test    r8, r8
0x1800177fc  jnz     short loc_180017811
0x1800177fe  mov     rax, [rsp+28h+arg_28]
0x180017803  mov     rcx, [rsp+28h+arg_20]
0x180017808  mov     [rax], rcx
0x18001780b  lea     eax, [r8+7Ah]
0x18001780f  jmp     short loc_180017831
0x180017811  cmp     [rsp+28h+arg_20], rbx
0x180017816  jz      short loc_18001781F
0x180017818  mov     eax, 25Dh
0x18001781d  jmp     short loc_180017831
0x18001781f  mov     rcx, r9; void *
0x180017822  call    memcpy_0
0x180017827  mov     rax, [rsp+28h+arg_28]
0x18001782c  mov     [rax], rbx
0x18001782f  xor     eax, eax
0x180017831  add     rsp, 20h
0x180017835  pop     rbx
0x180017836  retn
```
