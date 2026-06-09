# SepSddlParseWideStringUlong

- ea: `0x140009b4c`
- end: `0x140009c0e`
- name: `SepSddlParseWideStringUlong`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400096d8`

## callees

- `0x140009b4c`

## pseudocode

```c
__int64 __fastcall SepSddlParseWideStringUlong(unsigned __int16 *a1, unsigned __int16 **a2, unsigned int *a3)
{
  unsigned __int16 v3; // r9
  int v6; // r10d
  unsigned __int16 *v7; // rdi
  unsigned int v8; // r8d
  int v9; // edx
  int v10; // edx
  __int64 result; // rax

  v3 = *a1;
  *a3 = 0;
  *a2 = a1;
  if ( v3 != 48 || ((a1[1] - 88) & 0xFFDF) != 0 )
  {
    v6 = 16;
    if ( (unsigned __int16)(v3 - 48) <= 9u )
      v6 = 10;
  }
  else
  {
    a1 += 2;
    v6 = 16;
  }
  v7 = a1;
  v8 = 0;
  while ( 1 )
  {
    v9 = *a1;
    if ( !(_WORD)v9 )
      break;
    if ( (unsigned __int16)(v9 - 48) > 9u )
    {
      if ( v6 != 16 )
        break;
      if ( (unsigned __int16)(v9 - 65) > 5u )
      {
        if ( (unsigned __int16)(v9 - 97) > 5u )
          break;
        v10 = v9 - 87;
      }
      else
      {
        v10 = v9 - 55;
      }
    }
    else
    {
      v10 = v9 - 48;
    }
    if ( v10 + v8 * v6 < v8 )
      return 0;
    v8 = v10 + v8 * v6;
    ++a1;
  }
  if ( a1 == v7 )
    return 0;
  *a2 = a1;
  result = 1;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x140009b4c  push    rbx
0x140009b4e  push    rbp
0x140009b4f  push    rsi
0x140009b50  push    rdi
0x140009b51  movzx   r9d, word ptr [rcx]
0x140009b55  xor     ebp, ebp
0x140009b57  mov     r11, r8
0x140009b5a  mov     [r8], ebp
0x140009b5d  mov     rbx, rdx
0x140009b60  mov     [rdx], rcx
0x140009b63  lea     esi, [rbp+30h]
0x140009b66  cmp     r9w, si
0x140009b6a  jnz     short loc_140009B88
0x140009b6c  movzx   eax, word ptr [rcx+2]
0x140009b70  mov     edx, 0FFDFh
0x140009b75  sub     ax, 58h ; 'X'
0x140009b79  test    dx, ax
0x140009b7c  jnz     short loc_140009B88
0x140009b7e  add     rcx, 4
0x140009b82  lea     r10d, [rbp+10h]
0x140009b86  jmp     short loc_140009B9E
0x140009b88  mov     eax, 0Ah
0x140009b8d  sub     r9w, si
0x140009b91  cmp     r9w, 9
0x140009b96  lea     r10d, [rax+6]
0x140009b9a  cmovbe  r10d, eax
0x140009b9e  mov     rdi, rcx
0x140009ba1  mov     r8d, ebp
0x140009ba4  movzx   edx, word ptr [rcx]
0x140009ba7  test    dx, dx
0x140009baa  jz      short loc_140009BF4
0x140009bac  movzx   eax, dx
0x140009baf  sub     ax, si
0x140009bb2  cmp     ax, 9
0x140009bb6  ja      short loc_140009BBC
0x140009bb8  sub     edx, esi
0x140009bba  jmp     short loc_140009BDC
0x140009bbc  cmp     r10d, 10h
0x140009bc0  jnz     short loc_140009BF4
0x140009bc2  lea     eax, [rdx-41h]
0x140009bc5  cmp     ax, 5
0x140009bc9  ja      short loc_140009BD0
0x140009bcb  sub     edx, 37h ; '7'
0x140009bce  jmp     short loc_140009BDC
0x140009bd0  lea     eax, [rdx-61h]
0x140009bd3  cmp     ax, 5
0x140009bd7  ja      short loc_140009BF4
0x140009bd9  sub     edx, 57h ; 'W'
0x140009bdc  mov     r9d, r10d
0x140009bdf  imul    r9d, r8d
0x140009be3  add     r9d, edx
0x140009be6  cmp     r9d, r8d
0x140009be9  jb      short loc_140009BF9
0x140009beb  mov     r8d, r9d
0x140009bee  add     rcx, 2
0x140009bf2  jmp     short loc_140009BA4
0x140009bf4  cmp     rcx, rdi
0x140009bf7  jnz     short loc_140009BFD
0x140009bf9  xor     eax, eax
0x140009bfb  jmp     short loc_140009C08
0x140009bfd  mov     [rbx], rcx
0x140009c00  mov     eax, 1
0x140009c05  mov     [r11], r8d
0x140009c08  pop     rdi
0x140009c09  pop     rsi
0x140009c0a  pop     rbp
0x140009c0b  pop     rbx
0x140009c0c  retn
```
