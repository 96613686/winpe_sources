# CheckExtensionsList

- ea: `0x1400289f8`
- end: `0x140028ac0`
- name: `CheckExtensionsList`
- size: `200`
- prototype: `__int64 __fastcall(unsigned __int16 *, _DWORD *, _DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140029b30`

## callees

- `0x1400289f8`

## pseudocode

```c
__int64 __fastcall CheckExtensionsList(unsigned __int16 *a1, _DWORD *a2, _DWORD *a3, _DWORD *a4)
{
  unsigned int v4; // r11d
  _WORD *v8; // r10
  _WORD *v10; // r11
  int v11; // edx
  int v12; // r8d
  int v13; // r9d
  _WORD *i; // rax
  __int64 v15; // rcx

  v4 = *a1 >> 1;
  if ( !v4 )
    goto LABEL_4;
  v8 = (_WORD *)*((_QWORD *)a1 + 1);
  if ( v4 == 1 )
  {
    if ( !*v8 )
    {
LABEL_4:
      *a2 = 0;
      *a3 = 0;
      *a4 = 0;
      return 0;
    }
    goto LABEL_10;
  }
  if ( v4 != 2 )
  {
LABEL_10:
    if ( v4 >= 3 && *v8 && !v8[v4 - 2] && !v8[v4 - 1] )
    {
      v10 = &v8[v4];
      v11 = 0;
      v12 = 0;
      v13 = 0;
      do
      {
        for ( i = v8 + 1; *i; ++i )
          ;
        v15 = i - v8;
        if ( (unsigned int)v15 > 4 )
        {
          ++v12;
          v13 += v15;
        }
        else
        {
          ++v11;
        }
        v8 = i + 1;
      }
      while ( i[1] );
      if ( i + 2 == v10 )
      {
        *a2 = v11;
        *a3 = v12;
        *a4 = v13;
        return 0;
      }
    }
    return 3221225485LL;
  }
  if ( !*v8 && !v8[1] )
    goto LABEL_4;
  return 3221225485LL;
}

```

## disassembly

```asm
0x1400289f8  push    rbx
0x1400289fa  push    rbp
0x1400289fb  push    rsi
0x1400289fc  push    rdi
0x1400289fd  movzx   r11d, word ptr [rcx]
0x140028a01  xor     ebp, ebp
0x140028a03  shr     r11d, 1
0x140028a06  mov     rbx, r9
0x140028a09  mov     rdi, r8
0x140028a0c  mov     rsi, rdx
0x140028a0f  jz      short loc_140028A21
0x140028a11  mov     r10, [rcx+8]
0x140028a15  cmp     r11d, 1
0x140028a19  jnz     short loc_140028A31
0x140028a1b  cmp     [r10], bp
0x140028a1f  jnz     short loc_140028A4B
0x140028a21  mov     [rdx], ebp
0x140028a23  mov     [r8], ebp
0x140028a26  mov     [r9], ebp
0x140028a29  xor     eax, eax
0x140028a2b  pop     rdi
0x140028a2c  pop     rsi
0x140028a2d  pop     rbp
0x140028a2e  pop     rbx
0x140028a2f  retn
0x140028a31  cmp     r11d, 2
0x140028a35  jnz     short loc_140028A4B
0x140028a37  cmp     [r10], bp
0x140028a3b  jnz     short loc_140028A44
0x140028a3d  cmp     [r10+2], bp
0x140028a42  jz      short loc_140028A21
0x140028a44  mov     eax, 0C000000Dh
0x140028a49  jmp     short loc_140028A2B
0x140028a4b  cmp     r11d, 3
0x140028a4f  jb      short loc_140028A44
0x140028a51  cmp     [r10], bp
0x140028a55  jz      short loc_140028A44
0x140028a57  lea     eax, [r11-2]
0x140028a5b  cmp     [r10+rax*2], bp
0x140028a60  jnz     short loc_140028A44
0x140028a62  lea     eax, [r11-1]
0x140028a66  cmp     [r10+rax*2], bp
0x140028a6b  jnz     short loc_140028A44
0x140028a6d  lea     r11, [r10+r11*2]
0x140028a71  mov     edx, ebp
0x140028a73  mov     r8d, ebp
0x140028a76  mov     r9d, ebp
0x140028a79  lea     rax, [r10+2]
0x140028a7d  jmp     short loc_140028A83
0x140028a7f  add     rax, 2
0x140028a83  cmp     [rax], bp
0x140028a86  jnz     short loc_140028A7F
0x140028a88  mov     rcx, rax
0x140028a8b  sub     rcx, r10
0x140028a8e  sar     rcx, 1
0x140028a91  cmp     ecx, 4
0x140028a94  ja      short loc_140028A9A
0x140028a96  inc     edx
0x140028a98  jmp     short loc_140028AA0
0x140028a9a  inc     r8d
0x140028a9d  add     r9d, ecx
0x140028aa0  lea     r10, [rax+2]
0x140028aa4  cmp     [r10], bp
0x140028aa8  jnz     short loc_140028A79
0x140028aaa  lea     rax, [r10+2]
0x140028aae  cmp     rax, r11
0x140028ab1  jnz     short loc_140028A44
0x140028ab3  mov     [rsi], edx
0x140028ab5  mov     [rdi], r8d
0x140028ab8  mov     [rbx], r9d
0x140028abb  jmp     loc_140028A29
```
