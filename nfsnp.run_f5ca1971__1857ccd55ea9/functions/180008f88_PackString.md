# PackString

- ea: `0x180008f88`
- end: `0x180008ffb`
- name: `PackString`
- size: `115`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x1800034ec`
- `0x180003884`
- `0x180003b6c`
- `0x180003cf0`
- `0x180006b50`
- `0x180007860`
- `0x180008150`

## callees

- `0x180008f88`
- `0x180012e26`

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
0x180008f88  push    rbx
0x180008f8a  push    rbp
0x180008f8b  push    rsi
0x180008f8c  push    rdi
0x180008f8d  push    r14
0x180008f8f  sub     rsp, 20h
0x180008f93  cmp     dword ptr [r8], 0FFFFFFFFh
0x180008f97  mov     rsi, r9
0x180008f9a  mov     rbx, r8
0x180008f9d  mov     rbp, rdx
0x180008fa0  mov     rdi, rcx
0x180008fa3  jz      short loc_180008FEC
0x180008fa5  xor     r14d, r14d
0x180008fa8  mov     rdx, [rdi]; Src
0x180008fab  test    rdx, rdx
0x180008fae  jz      short loc_180008FD9
0x180008fb0  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008fb4  inc     rax
0x180008fb7  cmp     [rdx+rax*2], r14w
0x180008fbc  jnz     short loc_180008FB4
0x180008fbe  lea     r8d, ds:2[rax*2]; Size
0x180008fc6  sub     rsi, r8
0x180008fc9  mov     rcx, rsi; void *
0x180008fcc  call    memcpy_0
0x180008fd1  mov     eax, [rbx]
0x180008fd3  mov     [rax+rbp], rsi
0x180008fd7  jmp     short loc_180008FDF
0x180008fd9  mov     eax, [rbx]
0x180008fdb  mov     [rax+rbp], r14
0x180008fdf  add     rbx, 4
0x180008fe3  add     rdi, 8
0x180008fe7  cmp     dword ptr [rbx], 0FFFFFFFFh
0x180008fea  jnz     short loc_180008FA8
0x180008fec  mov     rax, rsi
0x180008fef  add     rsp, 20h
0x180008ff3  pop     r14
0x180008ff5  pop     rdi
0x180008ff6  pop     rsi
0x180008ff7  pop     rbp
0x180008ff8  pop     rbx
0x180008ff9  retn
```
