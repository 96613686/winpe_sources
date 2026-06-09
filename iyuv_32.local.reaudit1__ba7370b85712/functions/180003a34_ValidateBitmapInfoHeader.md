# ValidateBitmapInfoHeader

- ea: `0x180003a34`
- end: `0x180003b8b`
- name: `ValidateBitmapInfoHeader`
- size: `343`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800038d4`

## callees

- `0x180003a34`

## pseudocode

```c
_BOOL8 __fastcall ValidateBitmapInfoHeader(unsigned int *a1)
{
  __int64 v1; // rsi
  int v3; // eax
  unsigned __int16 v4; // r9
  unsigned int v5; // r10d
  unsigned int v6; // ecx
  int v7; // r11d
  unsigned int v8; // ecx
  unsigned int v9; // ecx
  unsigned int v10; // r10d
  unsigned int v11; // edx
  unsigned int v12; // r10d
  __int64 v13; // rcx

  v1 = *a1;
  if ( (unsigned int)(v1 - 40) > 0xFD8 )
    return 0;
  if ( !a1[1] )
    return 0;
  v3 = a1[2];
  if ( !v3 )
    return 0;
  v4 = *((_WORD *)a1 + 7);
  v5 = 32;
  if ( v4 )
    v5 = v4;
  if ( v4 > 0xC8u )
    return 0;
  v6 = a1[1];
  v7 = -v3;
  if ( v3 > 0 )
    v7 = v3;
  v8 = v5 * v6;
  if ( v8 / v5 != a1[1] )
    return 0;
  v9 = ((v8 >> 3) + 3) & 0xFFFFFFFC;
  v10 = v7 * v9;
  if ( v9 )
  {
    if ( v10 / v9 != v7 )
      return 0;
  }
  if ( v10 > 0x40000000 )
    return 0;
  if ( a1[5] > 0x40000000 )
    return 0;
  v11 = a1[8];
  if ( v11 > 0x100 )
    return 0;
  if ( !v11 && (unsigned __int16)(v4 - 1) <= 7u )
    v11 = 1 << v4;
  v12 = a1[4];
  if ( v12 == 3 && ((v4 - 16) & 0xFFEF) != 0 )
    return 0;
  v13 = 12;
  if ( v12 != 3 )
    v13 = 0;
  return v1 + v13 + 4 * (unsigned __int64)v11 <= 0x90C
      && (v12 && v12 != 3 || !a1[5] || v7 * (((a1[1] * v4 + 31) >> 3) & 0x1FFFFFFC) <= a1[5]);
}

```

## disassembly

```asm
0x180003a34  push    rbp
0x180003a36  push    rsi
0x180003a37  push    r14
0x180003a39  mov     esi, [rcx]
0x180003a3b  mov     r8, rcx
0x180003a3e  lea     eax, [rsi-28h]
0x180003a41  cmp     eax, 0FD8h
0x180003a46  ja      loc_180003B84
0x180003a4c  xor     ebp, ebp
0x180003a4e  cmp     [rcx+4], ebp
0x180003a51  jz      loc_180003B84
0x180003a57  mov     eax, [rcx+8]
0x180003a5a  test    eax, eax
0x180003a5c  jz      loc_180003B84
0x180003a62  movzx   r9d, word ptr [rcx+0Eh]
0x180003a67  lea     r10d, [rbp+20h]
0x180003a6b  test    r9w, r9w
0x180003a6f  jz      short loc_180003A75
0x180003a71  movzx   r10d, r9w
0x180003a75  mov     ecx, 0C8h
0x180003a7a  cmp     r9w, cx
0x180003a7e  ja      loc_180003B84
0x180003a84  mov     ecx, [r8+4]
0x180003a88  mov     r11d, eax
0x180003a8b  neg     r11d
0x180003a8e  cmovs   r11d, eax
0x180003a92  imul    ecx, r10d
0x180003a96  test    r10d, r10d
0x180003a99  jz      short loc_180003AAC
0x180003a9b  xor     edx, edx
0x180003a9d  mov     eax, ecx
0x180003a9f  div     r10d
0x180003aa2  cmp     eax, [r8+4]
0x180003aa6  jnz     loc_180003B84
0x180003aac  shr     ecx, 3
0x180003aaf  add     ecx, 3
0x180003ab2  and     ecx, 0FFFFFFFCh
0x180003ab5  mov     r10d, ecx
0x180003ab8  imul    r10d, r11d
0x180003abc  test    ecx, ecx
0x180003abe  jz      short loc_180003AD0
0x180003ac0  xor     edx, edx
0x180003ac2  mov     eax, r10d
0x180003ac5  div     ecx
0x180003ac7  cmp     eax, r11d
0x180003aca  jnz     loc_180003B84
0x180003ad0  mov     eax, 40000000h
0x180003ad5  cmp     r10d, eax
0x180003ad8  ja      loc_180003B84
0x180003ade  cmp     [r8+14h], eax
0x180003ae2  ja      loc_180003B84
0x180003ae8  mov     edx, [r8+20h]
0x180003aec  cmp     edx, 100h
0x180003af2  ja      loc_180003B84
0x180003af8  mov     r14d, 1
0x180003afe  test    edx, edx
0x180003b00  jnz     short loc_180003B18
0x180003b02  movzx   eax, r9w
0x180003b06  sub     ax, r14w
0x180003b0a  cmp     ax, 7
0x180003b0e  ja      short loc_180003B18
0x180003b10  mov     ecx, r9d
0x180003b13  mov     edx, r14d
0x180003b16  shl     edx, cl
0x180003b18  mov     r10d, [r8+10h]
0x180003b1c  cmp     r10d, 3
0x180003b20  jnz     short loc_180003B30
0x180003b22  lea     eax, [r9-10h]
0x180003b26  mov     ecx, 0FFEFh
0x180003b2b  test    cx, ax
0x180003b2e  jnz     short loc_180003B84
0x180003b30  cmp     r10d, 3
0x180003b34  mov     eax, edx
0x180003b36  mov     ecx, 0Ch
0x180003b3b  cmovnz  rcx, rbp
0x180003b3f  lea     rcx, [rcx+rax*4]
0x180003b43  add     rcx, rsi
0x180003b46  cmp     rcx, 90Ch
0x180003b4d  ja      short loc_180003B84
0x180003b4f  test    r10d, r10d
0x180003b52  jz      short loc_180003B5A
0x180003b54  cmp     r10d, 3
0x180003b58  jnz     short loc_180003B7F
0x180003b5a  cmp     [r8+14h], ebp
0x180003b5e  jz      short loc_180003B7F
0x180003b60  movzx   ecx, r9w
0x180003b64  imul    ecx, [r8+4]
0x180003b69  add     ecx, 1Fh
0x180003b6c  shr     ecx, 3
0x180003b6f  and     ecx, 1FFFFFFCh
0x180003b75  imul    ecx, r11d
0x180003b79  cmp     ecx, [r8+14h]
0x180003b7d  ja      short loc_180003B84
0x180003b7f  mov     eax, r14d
0x180003b82  jmp     short loc_180003B86
0x180003b84  xor     eax, eax
0x180003b86  pop     r14
0x180003b88  pop     rsi
0x180003b89  pop     rbp
0x180003b8a  retn
```
