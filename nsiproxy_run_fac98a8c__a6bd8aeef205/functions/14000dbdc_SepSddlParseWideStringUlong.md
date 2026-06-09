# SepSddlParseWideStringUlong

- ea: `0x14000dbdc`
- end: `0x14000dc9e`
- name: `SepSddlParseWideStringUlong`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000d768`

## callees

- `0x14000dbdc`

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
0x14000dbdc  push    rbx
0x14000dbde  push    rbp
0x14000dbdf  push    rsi
0x14000dbe0  push    rdi
0x14000dbe1  movzx   r9d, word ptr [rcx]
0x14000dbe5  xor     ebp, ebp
0x14000dbe7  mov     r11, r8
0x14000dbea  mov     [r8], ebp
0x14000dbed  mov     rbx, rdx
0x14000dbf0  mov     [rdx], rcx
0x14000dbf3  lea     esi, [rbp+30h]
0x14000dbf6  cmp     r9w, si
0x14000dbfa  jnz     short loc_14000DC18
0x14000dbfc  movzx   eax, word ptr [rcx+2]
0x14000dc00  mov     edx, 0FFDFh
0x14000dc05  sub     ax, 58h ; 'X'
0x14000dc09  test    dx, ax
0x14000dc0c  jnz     short loc_14000DC18
0x14000dc0e  add     rcx, 4
0x14000dc12  lea     r10d, [rbp+10h]
0x14000dc16  jmp     short loc_14000DC2E
0x14000dc18  mov     eax, 0Ah
0x14000dc1d  sub     r9w, si
0x14000dc21  cmp     r9w, 9
0x14000dc26  lea     r10d, [rax+6]
0x14000dc2a  cmovbe  r10d, eax
0x14000dc2e  mov     rdi, rcx
0x14000dc31  mov     r8d, ebp
0x14000dc34  movzx   edx, word ptr [rcx]
0x14000dc37  test    dx, dx
0x14000dc3a  jz      short loc_14000DC84
0x14000dc3c  movzx   eax, dx
0x14000dc3f  sub     ax, si
0x14000dc42  cmp     ax, 9
0x14000dc46  ja      short loc_14000DC4C
0x14000dc48  sub     edx, esi
0x14000dc4a  jmp     short loc_14000DC6C
0x14000dc4c  cmp     r10d, 10h
0x14000dc50  jnz     short loc_14000DC84
0x14000dc52  lea     eax, [rdx-41h]
0x14000dc55  cmp     ax, 5
0x14000dc59  ja      short loc_14000DC60
0x14000dc5b  sub     edx, 37h ; '7'
0x14000dc5e  jmp     short loc_14000DC6C
0x14000dc60  lea     eax, [rdx-61h]
0x14000dc63  cmp     ax, 5
0x14000dc67  ja      short loc_14000DC84
0x14000dc69  sub     edx, 57h ; 'W'
0x14000dc6c  mov     r9d, r10d
0x14000dc6f  imul    r9d, r8d
0x14000dc73  add     r9d, edx
0x14000dc76  cmp     r9d, r8d
0x14000dc79  jb      short loc_14000DC89
0x14000dc7b  mov     r8d, r9d
0x14000dc7e  add     rcx, 2
0x14000dc82  jmp     short loc_14000DC34
0x14000dc84  cmp     rcx, rdi
0x14000dc87  jnz     short loc_14000DC8D
0x14000dc89  xor     eax, eax
0x14000dc8b  jmp     short loc_14000DC98
0x14000dc8d  mov     [rbx], rcx
0x14000dc90  mov     eax, 1
0x14000dc95  mov     [r11], r8d
0x14000dc98  pop     rdi
0x14000dc99  pop     rsi
0x14000dc9a  pop     rbp
0x14000dc9b  pop     rbx
0x14000dc9c  retn
```
