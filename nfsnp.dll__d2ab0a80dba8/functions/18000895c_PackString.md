# PackString

- ea: `0x18000895c`
- end: `0x1800089ce`
- name: `PackString`
- size: `114`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x180003344`
- `0x1800036d4`
- `0x1800039bc`
- `0x180003b40`
- `0x1800066c0`
- `0x180007330`
- `0x180007bc0`

## callees

- `0x18000895c`
- `0x180011b56`

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
0x18000895c  push    rbx
0x18000895e  push    rbp
0x18000895f  push    rsi
0x180008960  push    rdi
0x180008961  push    r14
0x180008963  sub     rsp, 20h
0x180008967  cmp     dword ptr [r8], 0FFFFFFFFh
0x18000896b  mov     rsi, r9
0x18000896e  mov     rbx, r8
0x180008971  mov     rbp, rdx
0x180008974  mov     rdi, rcx
0x180008977  jz      short loc_1800089C0
0x180008979  xor     r14d, r14d
0x18000897c  mov     rdx, [rdi]; Src
0x18000897f  test    rdx, rdx
0x180008982  jz      short loc_1800089AD
0x180008984  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008988  inc     rax
0x18000898b  cmp     [rdx+rax*2], r14w
0x180008990  jnz     short loc_180008988
0x180008992  lea     r8d, ds:2[rax*2]; Size
0x18000899a  sub     rsi, r8
0x18000899d  mov     rcx, rsi; void *
0x1800089a0  call    memcpy_0
0x1800089a5  mov     eax, [rbx]
0x1800089a7  mov     [rax+rbp], rsi
0x1800089ab  jmp     short loc_1800089B3
0x1800089ad  mov     eax, [rbx]
0x1800089af  mov     [rax+rbp], r14
0x1800089b3  add     rbx, 4
0x1800089b7  add     rdi, 8
0x1800089bb  cmp     dword ptr [rbx], 0FFFFFFFFh
0x1800089be  jnz     short loc_18000897C
0x1800089c0  mov     rax, rsi
0x1800089c3  add     rsp, 20h
0x1800089c7  pop     r14
0x1800089c9  pop     rdi
0x1800089ca  pop     rsi
0x1800089cb  pop     rbp
0x1800089cc  pop     rbx
0x1800089cd  retn
```
