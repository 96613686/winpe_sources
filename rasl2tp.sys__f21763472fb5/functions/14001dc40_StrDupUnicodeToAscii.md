# StrDupUnicodeToAscii

- ea: `0x14001dc40`
- end: `0x14001dcad`
- name: `StrDupUnicodeToAscii`
- size: `109`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1400024e0`
- `0x14001d940`
- `0x14001e3c0`

## callees

- `0x140001b70`
- `0x14001dc40`

## pseudocode

```c
unsigned int *__fastcall StrDupUnicodeToAscii(__int64 a1, unsigned int a2)
{
  unsigned __int64 v2; // rbx
  unsigned int *v4; // r8
  unsigned int v5; // esi
  unsigned int i; // eax
  __int64 v7; // rdx

  v2 = a2;
  v4 = 0;
  if ( a2 >= 2 && (a2 & 1) == 0 )
  {
    if ( *(_WORD *)a1 )
    {
      if ( !*(_BYTE *)(a1 + 1) )
      {
        v5 = a2 >> 1;
        v4 = ALLOC_NONPAGED((a2 >> 1) + 1, 0x6954324Cu);
        if ( v4 )
        {
          for ( i = 0; i < v5; *((_BYTE *)v4 + v7) = *(_BYTE *)(a1 + 2 * v7) )
            v7 = i++;
          *((_BYTE *)v4 + (v2 >> 1)) = 0;
        }
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x14001dc40  push    rbx
0x14001dc42  push    rbp
0x14001dc43  push    rsi
0x14001dc44  push    rdi
0x14001dc45  sub     rsp, 28h
0x14001dc49  xor     ebp, ebp
0x14001dc4b  mov     ebx, edx
0x14001dc4d  mov     rdi, rcx
0x14001dc50  mov     r8d, ebp
0x14001dc53  cmp     edx, 2
0x14001dc56  jb      short loc_14001DCA0
0x14001dc58  test    bl, 1
0x14001dc5b  jnz     short loc_14001DCA0
0x14001dc5d  cmp     [rcx], bp
0x14001dc60  jz      short loc_14001DCA0
0x14001dc62  cmp     [rcx+1], bpl
0x14001dc66  jnz     short loc_14001DCA0
0x14001dc68  mov     esi, ebx
0x14001dc6a  mov     edx, 6954324Ch
0x14001dc6f  shr     esi, 1
0x14001dc71  lea     ecx, [rsi+1]
0x14001dc74  call    ALLOC_NONPAGED
0x14001dc79  mov     r8, rax
0x14001dc7c  test    rax, rax
0x14001dc7f  jz      short loc_14001DCA0
0x14001dc81  mov     eax, ebp
0x14001dc83  test    esi, esi
0x14001dc85  jz      short loc_14001DC96
0x14001dc87  mov     edx, eax
0x14001dc89  inc     eax
0x14001dc8b  mov     cl, [rdi+rdx*2]
0x14001dc8e  mov     [rdx+r8], cl
0x14001dc92  cmp     eax, esi
0x14001dc94  jb      short loc_14001DC87
0x14001dc96  mov     rax, rbx
0x14001dc99  shr     rax, 1
0x14001dc9c  mov     [rax+r8], bpl
0x14001dca0  mov     rax, r8
0x14001dca3  add     rsp, 28h
0x14001dca7  pop     rdi
0x14001dca8  pop     rsi
0x14001dca9  pop     rbp
0x14001dcaa  pop     rbx
0x14001dcab  retn
```
