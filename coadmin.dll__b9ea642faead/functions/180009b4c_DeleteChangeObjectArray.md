# _DeleteChangeObjectArray

- ea: `0x180009b4c`
- end: `0x180009bcf`
- name: `_DeleteChangeObjectArray`
- size: `131`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180001c3c`
- `0x180003590`

## callees

- `0x1800010b0`
- `0x180009b4c`

## pseudocode

```c
__int64 __fastcall DeleteChangeObjectArray(unsigned int a1, void **a2)
{
  unsigned int v3; // esi
  _QWORD *v4; // rbx
  unsigned int v5; // ebp
  __int64 v6; // r14
  void *v7; // rcx
  void *v8; // rcx

  if ( a2 )
  {
    v4 = *a2;
    v3 = 0;
    *a2 = 0;
    if ( v4 )
    {
      v5 = 0;
      if ( a1 )
      {
        v6 = 0;
        do
        {
          v7 = (void *)v4[3 * v6];
          if ( v7 )
          {
            operator delete[](v7);
            v4[3 * v6] = 0;
          }
          v8 = (void *)v4[3 * v6 + 2];
          v4[3 * v6 + 1] = 0;
          if ( v8 )
          {
            operator delete[](v8);
            v4[3 * v6 + 2] = 0;
          }
          ++v5;
          ++v6;
        }
        while ( v5 < a1 );
      }
      operator delete[](v4);
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v3;
}

```

## disassembly

```asm
0x180009b4c  push    rbx
0x180009b4e  push    rbp
0x180009b4f  push    rsi
0x180009b50  push    rdi
0x180009b51  push    r14
0x180009b53  push    r15
0x180009b55  sub     rsp, 28h
0x180009b59  mov     r15d, ecx
0x180009b5c  test    rdx, rdx
0x180009b5f  jnz     short loc_180009B68
0x180009b61  mov     esi, 80070057h
0x180009b66  jmp     short loc_180009BC0
0x180009b68  mov     rbx, [rdx]
0x180009b6b  xor     esi, esi
0x180009b6d  mov     [rdx], rsi
0x180009b70  test    rbx, rbx
0x180009b73  jz      short loc_180009BC0
0x180009b75  xor     ebp, ebp
0x180009b77  test    r15d, r15d
0x180009b7a  jz      short loc_180009BB8
0x180009b7c  xor     r14d, r14d
0x180009b7f  lea     rdi, [r14+r14*2]
0x180009b83  mov     rcx, [rbx+rdi*8]; Block
0x180009b87  test    rcx, rcx
0x180009b8a  jz      short loc_180009B95
0x180009b8c  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180009b91  mov     [rbx+rdi*8], rsi
0x180009b95  mov     rcx, [rbx+rdi*8+10h]; Block
0x180009b9a  mov     [rbx+rdi*8+8], rsi
0x180009b9f  test    rcx, rcx
0x180009ba2  jz      short loc_180009BAE
0x180009ba4  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180009ba9  mov     [rbx+rdi*8+10h], rsi
0x180009bae  inc     ebp
0x180009bb0  inc     r14
0x180009bb3  cmp     ebp, r15d
0x180009bb6  jb      short loc_180009B7F
0x180009bb8  mov     rcx, rbx; Block
0x180009bbb  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180009bc0  mov     eax, esi
0x180009bc2  add     rsp, 28h
0x180009bc6  pop     r15
0x180009bc8  pop     r14
0x180009bca  pop     rdi
0x180009bcb  pop     rsi
0x180009bcc  pop     rbp
0x180009bcd  pop     rbx
0x180009bce  retn
```
