# PackString

- ea: `0x140009e0c`
- end: `0x140009e7e`
- name: `PackString`
- size: `114`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1400088c0`
- `0x140008b50`
- `0x140009180`

## callees

- `0x140009e0c`
- `0x140018302`

## pseudocode

```c
char *__fastcall PackString(const void **a1, __int64 a2, _DWORD *a3, char *a4)
{
  _DWORD *i; // rbx
  _WORD *v8; // rdx
  __int64 v9; // rax
  size_t v10; // r8

  for ( i = a3; *i != -1; ++a1 )
  {
    v8 = *a1;
    if ( *a1 )
    {
      v9 = -1;
      do
        ++v9;
      while ( v8[v9] );
      v10 = (unsigned int)(2 * v9 + 2);
      a4 -= v10;
      memcpy_0(a4, v8, v10);
      *(_QWORD *)((unsigned int)*i + a2) = a4;
    }
    else
    {
      *(_QWORD *)((unsigned int)*i + a2) = 0;
    }
    ++i;
  }
  return a4;
}

```

## disassembly

```asm
0x140009e0c  push    rbx
0x140009e0e  push    rbp
0x140009e0f  push    rsi
0x140009e10  push    rdi
0x140009e11  push    r14
0x140009e13  sub     rsp, 20h
0x140009e17  cmp     dword ptr [r8], 0FFFFFFFFh
0x140009e1b  mov     rsi, r9
0x140009e1e  mov     rbx, r8
0x140009e21  mov     rbp, rdx
0x140009e24  mov     rdi, rcx
0x140009e27  jz      short loc_140009E70
0x140009e29  xor     r14d, r14d
0x140009e2c  mov     rdx, [rdi]; Src
0x140009e2f  test    rdx, rdx
0x140009e32  jz      short loc_140009E5D
0x140009e34  or      rax, 0FFFFFFFFFFFFFFFFh
0x140009e38  inc     rax
0x140009e3b  cmp     [rdx+rax*2], r14w
0x140009e40  jnz     short loc_140009E38
0x140009e42  lea     r8d, ds:2[rax*2]; Size
0x140009e4a  sub     rsi, r8
0x140009e4d  mov     rcx, rsi; void *
0x140009e50  call    memcpy_0
0x140009e55  mov     eax, [rbx]
0x140009e57  mov     [rax+rbp], rsi
0x140009e5b  jmp     short loc_140009E63
0x140009e5d  mov     eax, [rbx]
0x140009e5f  mov     [rax+rbp], r14
0x140009e63  add     rbx, 4
0x140009e67  add     rdi, 8
0x140009e6b  cmp     dword ptr [rbx], 0FFFFFFFFh
0x140009e6e  jnz     short loc_140009E2C
0x140009e70  mov     rax, rsi
0x140009e73  add     rsp, 20h
0x140009e77  pop     r14
0x140009e79  pop     rdi
0x140009e7a  pop     rsi
0x140009e7b  pop     rbp
0x140009e7c  pop     rbx
0x140009e7d  retn
```
