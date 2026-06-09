# WriteRepTree

- ea: `0x18000e684`
- end: `0x18000ea2d`
- name: `WriteRepTree`
- size: `937`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180014668`

## callees

- `0x18000e684`
- `0x18000ea34`
- `0x18000eeac`
- `0x180014dc0`
- `0x18001562a`
- `0x18001b625`

## pseudocode

```c
void *__fastcall WriteRepTree(__int64 a1, _BYTE *a2, unsigned __int8 *a3, int a4)
{
  size_t v5; // r14
  int v8; // r8d
  int v9; // ecx
  int i; // edx
  __int64 v11; // rax
  unsigned __int16 v12; // dx
  __int64 v13; // rcx
  __int16 v14; // cx
  __int64 v15; // rdx
  __int16 v16; // ax
  __int64 j; // rdx
  __int64 v18; // rcx
  __int16 v19; // ax
  __int64 k; // r10
  __int64 v21; // r10
  int v22; // ebx
  int v23; // ecx
  int m; // r11d
  char v25; // r10
  char v26; // r10
  int v27; // r11d
  __int64 v28; // r8
  __int64 v29; // rdx
  int v30; // r11d
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  _BYTE v35[24]; // [rsp+20h] [rbp-E0h] BYREF
  _DWORD v36[10]; // [rsp+38h] [rbp-C8h]
  _WORD v37[17]; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v38; // [rsp+82h] [rbp-7Eh]
  __int16 v39; // [rsp+84h] [rbp-7Ch]
  __int16 v40; // [rsp+86h] [rbp-7Ah]
  _WORD v41[24]; // [rsp+C0h] [rbp-40h] BYREF

  v5 = a4;
  memset_0(v37, 0, 0x60u);
  v8 = 0;
  if ( (int)v5 <= 0 )
    goto LABEL_8;
  do
  {
    v9 = v8 + 1;
    for ( i = 0; v9 < (int)v5; ++v9 )
    {
      if ( a2[v9] != a2[v8] )
        break;
      ++i;
    }
    if ( i < 4 )
    {
      v11 = *((unsigned __int8 *)&qword_18001E6D0[2] + a3[v8] - (unsigned __int64)(unsigned __int8)a2[v8] + 1);
      ++v37[v11];
      goto LABEL_7;
    }
    if ( a2[v8] )
    {
      if ( i > 5 )
        i = 5;
      v32 = *((unsigned __int8 *)&qword_18001E6D0[2] + a3[v8] - (unsigned __int64)(unsigned __int8)a2[v8] + 1);
      ++v37[v32];
      ++v40;
      goto LABEL_38;
    }
    if ( i <= 51 )
    {
      if ( i <= 19 )
      {
        ++v38;
        goto LABEL_38;
      }
    }
    else
    {
      i = 51;
    }
    ++v39;
LABEL_38:
    v8 = i + v8 - 1;
LABEL_7:
    ++v8;
  }
  while ( v8 < (int)v5 );
LABEL_8:
  while ( 1 )
  {
    *(_DWORD *)(a1 + 9580) = 20;
    *(_QWORD *)(a1 + 2520) = v37;
    v12 = 0;
    *(_BYTE *)(a1 + 9586) = 0;
    *(_QWORD *)(a1 + 2536) = v35;
    *(_WORD *)(a1 + 9584) = 0;
    *(_WORD *)(a1 + 2546) = 0;
    do
    {
      *(_BYTE *)(v12 + *(_QWORD *)(a1 + 2536)) = 0;
      if ( v37[v12] )
      {
        v13 = *(__int16 *)(a1 + 9584);
        *(_WORD *)(a1 + 9584) = v13 + 1;
        *(_WORD *)(a1 + 2 * v13 + 2546) = v12;
      }
      ++v12;
    }
    while ( (__int16)v12 < 20 );
    v14 = *(_WORD *)(a1 + 9584);
    if ( v14 >= 2 )
      break;
    v34 = *(__int16 *)(a1 + 2546);
    if ( !v14 )
    {
      v41[v34] = 0;
      goto LABEL_17;
    }
    if ( (_WORD)v34 )
      v37[0] = 1;
    else
      v37[1] = 1;
  }
  make_tree2(a1, 20, v37, v41);
  v15 = 1;
  v36[0] = 0;
  do
  {
    v16 = *((_WORD *)v36 + v15) + *(_WORD *)(a1 + 2 * v15 + 9544);
    ++v15;
    *((_WORD *)v36 + v15) = 2 * v16;
  }
  while ( v15 != 17 );
  for ( j = 0; j != 20; ++j )
  {
    v18 = (char)v35[j];
    v19 = *((_WORD *)v36 + v18);
    v41[j] = v19;
    *((_WORD *)v36 + v18) = v19 + 1;
  }
LABEL_17:
  for ( k = 0; k != 20; k = v21 + 1 )
    output_bits(a1, 4, (unsigned int)(char)v35[k]);
  v22 = 0;
  if ( (int)v5 > 0 )
  {
    while ( 2 )
    {
      v23 = v22 + 1;
      for ( m = 0; v23 < (int)v5; ++v23 )
      {
        if ( a2[v23] != a2[v22] )
          break;
        ++m;
      }
      if ( m >= 4 )
      {
        if ( a2[v22] )
        {
          v25 = 19;
        }
        else
        {
          if ( m > 51 )
            m = 51;
          v25 = ((unsigned int)m > 0x13) + 17;
        }
      }
      else
      {
        v25 = *((_BYTE *)&qword_18001E6D0[2] + a3[v22] - (unsigned __int64)(unsigned __int8)a2[v22] + 1);
      }
      output_bits(a1, (unsigned int)(char)v35[v25], (unsigned __int16)v41[v25]);
      switch ( v26 )
      {
        case 17:
          v28 = (unsigned int)(v27 - 4);
          v29 = 4;
          goto LABEL_27;
        case 18:
          v28 = (unsigned int)(v27 - 20);
          v29 = 5;
LABEL_27:
          output_bits(a1, v29, v28);
          v22 = v30 + v22 - 1;
          break;
        case 19:
          output_bits(a1, 1, (unsigned int)(v27 - 4));
          v33 = *((char *)&qword_18001E6D0[2] + a3[v22] - (unsigned __int64)(unsigned __int8)a2[v22] + 1);
          v28 = (unsigned __int16)v41[v33];
          v29 = (unsigned int)(char)v35[v33];
          goto LABEL_27;
      }
      if ( ++v22 >= (int)v5 )
        return memcpy_0(a3, a2, v5);
      continue;
    }
  }
  return memcpy_0(a3, a2, v5);
}

```

## disassembly

```asm
0x18000e684  push    rbp
0x18000e686  push    rbx
0x18000e687  push    rsi
0x18000e688  push    rdi
0x18000e689  push    r12
0x18000e68b  push    r13
0x18000e68d  push    r14
0x18000e68f  push    r15
0x18000e691  lea     rbp, [rsp-8]
0x18000e696  sub     rsp, 108h
0x18000e69d  mov     rax, cs:__security_cookie
0x18000e6a4  xor     rax, rsp
0x18000e6a7  mov     [rbp+40h+var_50], rax
0x18000e6ab  mov     r15, rdx
0x18000e6ae  movsxd  r14, r9d
0x18000e6b1  xor     edx, edx; Val
0x18000e6b3  mov     r12, r8
0x18000e6b6  mov     rsi, rcx
0x18000e6b9  lea     rcx, [rsp+140h+var_E0]; void *
0x18000e6be  lea     r8d, [rdx+60h]; Size
0x18000e6c2  call    memset_0
0x18000e6c7  xor     edi, edi
0x18000e6c9  lea     r11, qword_18001E6D0
0x18000e6d0  mov     r8d, edi
0x18000e6d3  lea     r13d, [rdi+1]
0x18000e6d7  lea     r9d, [rdi+33h]
0x18000e6db  lea     r10d, [rdi+5]
0x18000e6df  test    r14d, r14d
0x18000e6e2  jle     short loc_18000E73D
0x18000e6e4  lea     ecx, [r8+1]
0x18000e6e8  mov     edx, edi
0x18000e6ea  cmp     ecx, r14d
0x18000e6ed  jge     short loc_18000E710
0x18000e6ef  movsxd  rax, r8d
0x18000e6f2  mov     r9b, [rax+r15]
0x18000e6f6  movsxd  rax, ecx
0x18000e6f9  cmp     [rax+r15], r9b
0x18000e6fd  jnz     short loc_18000E70A
0x18000e6ff  add     edx, r13d
0x18000e702  add     ecx, r13d
0x18000e705  cmp     ecx, r14d
0x18000e708  jl      short loc_18000E6F6
0x18000e70a  mov     r9d, 33h ; '3'
0x18000e710  movsxd  rax, r8d
0x18000e713  cmp     edx, 4
0x18000e716  jge     loc_18000E934
0x18000e71c  movzx   ecx, byte ptr [rax+r12]
0x18000e721  movzx   eax, byte ptr [rax+r15]
0x18000e726  sub     rcx, rax
0x18000e729  movzx   eax, byte ptr [rcx+r11+11h]
0x18000e72f  add     [rsp+rax*2+140h+var_E0], r13w
0x18000e735  add     r8d, r13d
0x18000e738  cmp     r8d, r14d
0x18000e73b  jl      short loc_18000E6E4
0x18000e73d  mov     ebx, 14h
0x18000e742  lea     rax, [rsp+140h+var_E0]
0x18000e747  mov     [rsi+256Ch], ebx
0x18000e74d  mov     [rsi+9D8h], rax
0x18000e754  mov     edx, edi
0x18000e756  lea     rax, [rsp+140h+var_120]
0x18000e75b  mov     [rsi+2572h], dil
0x18000e762  mov     [rsi+9E8h], rax
0x18000e769  mov     [rsi+2570h], di
0x18000e770  mov     [rsi+9F2h], di
0x18000e777  mov     rax, [rsi+9E8h]
0x18000e77e  movzx   ecx, dx
0x18000e781  mov     [rcx+rax], dil
0x18000e785  cmp     [rsp+rcx*2+140h+var_E0], di
0x18000e78a  jz      short loc_18000E7A7
0x18000e78c  movsx   rcx, word ptr [rsi+2570h]
0x18000e794  lea     eax, [rcx+r13]
0x18000e798  mov     [rsi+2570h], ax
0x18000e79f  mov     [rsi+rcx*2+9F2h], dx
0x18000e7a7  add     dx, r13w
0x18000e7ab  cmp     dx, bx
0x18000e7ae  jl      short loc_18000E777
0x18000e7b0  movzx   ecx, word ptr [rsi+2570h]
0x18000e7b7  cmp     cx, 2
0x18000e7bb  jl      loc_18000E9BB
0x18000e7c1  mov     edx, ebx
0x18000e7c3  lea     r9, [rbp+40h+var_80]
0x18000e7c7  lea     r8, [rsp+140h+var_E0]
0x18000e7cc  mov     rcx, rsi
0x18000e7cf  call    make_tree2
0x18000e7d4  mov     rdx, r13
0x18000e7d7  mov     [rsp+140h+var_108], edi
0x18000e7db  movzx   eax, word ptr [rsi+rdx*2+2548h]
0x18000e7e3  lea     rcx, [rdx+1]
0x18000e7e7  add     ax, word ptr [rsp+rdx*2+140h+var_108]
0x18000e7ec  mov     rdx, rcx
0x18000e7ef  add     ax, ax
0x18000e7f2  mov     word ptr [rsp+rcx*2+140h+var_108], ax
0x18000e7f7  cmp     rcx, 11h
0x18000e7fb  jnz     short loc_18000E7DB
0x18000e7fd  mov     rdx, rdi
0x18000e800  movsx   rcx, [rsp+rdx+140h+var_120]
0x18000e806  movzx   eax, word ptr [rsp+rcx*2+140h+var_108]
0x18000e80b  mov     [rbp+rdx*2+40h+var_80], ax
0x18000e810  add     ax, r13w
0x18000e814  add     rdx, r13
0x18000e817  mov     word ptr [rsp+rcx*2+140h+var_108], ax
0x18000e81c  cmp     rdx, rbx
0x18000e81f  jnz     short loc_18000E800
0x18000e821  mov     r10, rdi
0x18000e824  movsx   r8d, [rsp+r10+140h+var_120]
0x18000e82a  mov     edx, 4
0x18000e82f  mov     rcx, rsi
0x18000e832  call    output_bits
0x18000e837  add     r10, r13
0x18000e83a  cmp     r10, rbx
0x18000e83d  jnz     short loc_18000E824
0x18000e83f  mov     ebx, edi
0x18000e841  test    r14d, r14d
0x18000e844  jle     loc_18000E8DE
0x18000e84a  lea     ecx, [rbx+1]
0x18000e84d  mov     r11d, edi
0x18000e850  cmp     ecx, r14d
0x18000e853  jge     short loc_18000E870
0x18000e855  movsxd  rax, ebx
0x18000e858  mov     dl, [rax+r15]
0x18000e85c  movsxd  rax, ecx
0x18000e85f  cmp     [rax+r15], dl
0x18000e863  jnz     short loc_18000E870
0x18000e865  add     r11d, r13d
0x18000e868  add     ecx, r13d
0x18000e86b  cmp     ecx, r14d
0x18000e86e  jl      short loc_18000E85C
0x18000e870  movsxd  rdi, ebx
0x18000e873  cmp     r11d, 4
0x18000e877  jge     loc_18000E90C
0x18000e87d  movzx   eax, byte ptr [rdi+r15]
0x18000e882  movzx   ecx, byte ptr [rdi+r12]
0x18000e887  sub     rcx, rax
0x18000e88a  lea     rax, qword_18001E6D0
0x18000e891  mov     r10b, [rcx+rax+11h]
0x18000e896  movsx   rax, r10b
0x18000e89a  mov     rcx, rsi
0x18000e89d  movzx   r8d, [rbp+rax*2+40h+var_80]
0x18000e8a3  movsx   edx, [rsp+rax+140h+var_120]
0x18000e8a8  call    output_bits
0x18000e8ad  cmp     r10b, 11h
0x18000e8b1  jnz     loc_18000E96E
0x18000e8b7  lea     r8d, [r11-4]
0x18000e8bb  mov     edx, 4
0x18000e8c0  mov     rcx, rsi
0x18000e8c3  call    output_bits
0x18000e8c8  dec     ebx
0x18000e8ca  add     ebx, r11d
0x18000e8cd  add     ebx, r13d
0x18000e8d0  mov     edi, 0
0x18000e8d5  cmp     ebx, r14d
0x18000e8d8  jl      loc_18000E84A
0x18000e8de  mov     r8, r14; Size
0x18000e8e1  mov     rdx, r15; Src
0x18000e8e4  mov     rcx, r12; void *
0x18000e8e7  call    memcpy_0
0x18000e8ec  mov     rcx, [rbp+40h+var_50]
0x18000e8f0  xor     rcx, rsp; StackCookie
0x18000e8f3  call    __security_check_cookie
0x18000e8f8  add     rsp, 108h
0x18000e8ff  pop     r15
0x18000e901  pop     r14
0x18000e903  pop     r13
0x18000e905  pop     r12
0x18000e907  pop     rdi
0x18000e908  pop     rsi
0x18000e909  pop     rbx
0x18000e90a  pop     rbp
0x18000e90b  retn
0x18000e90c  cmp     byte ptr [rdi+r15], 0
0x18000e911  jnz     loc_18000EA0B
0x18000e917  mov     eax, 33h ; '3'
0x18000e91c  cmp     r11d, eax
0x18000e91f  cmovg   r11d, eax
0x18000e923  cmp     r11d, 13h
0x18000e927  setnbe  r10b
0x18000e92b  add     r10b, 11h
0x18000e92f  jmp     loc_18000E896
0x18000e934  cmp     [rax+r15], dil
0x18000e938  jz      loc_18000E9D2
0x18000e93e  movzx   ecx, byte ptr [rax+r12]
0x18000e943  cmp     edx, r10d
0x18000e946  movzx   eax, byte ptr [rax+r15]
0x18000e94b  cmovg   edx, r10d
0x18000e94f  sub     rcx, rax
0x18000e952  movzx   eax, byte ptr [rcx+r11+11h]
0x18000e958  add     [rsp+rax*2+140h+var_E0], r13w
0x18000e95e  add     [rbp+40h+var_BA], r13w
0x18000e963  dec     r8d
0x18000e966  add     r8d, edx
0x18000e969  jmp     loc_18000E735
0x18000e96e  cmp     r10b, 12h
0x18000e972  jz      loc_18000EA1F
0x18000e978  cmp     r10b, 13h
0x18000e97c  jnz     loc_18000E8CD
0x18000e982  lea     r8d, [r11-4]
0x18000e986  mov     edx, r13d
0x18000e989  mov     rcx, rsi
0x18000e98c  call    output_bits
0x18000e991  movzx   eax, byte ptr [rdi+r15]
0x18000e996  movzx   r10d, byte ptr [rdi+r12]
0x18000e99b  sub     r10, rax
0x18000e99e  lea     rax, qword_18001E6D0
0x18000e9a5  movsx   rax, byte ptr [r10+rax+11h]
0x18000e9ab  movzx   r8d, [rbp+rax*2+40h+var_80]
0x18000e9b1  movsx   edx, [rsp+rax+140h+var_120]
0x18000e9b6  jmp     loc_18000E8C0
0x18000e9bb  movsx   rax, word ptr [rsi+9F2h]
0x18000e9c3  test    cx, cx
0x18000e9c6  jnz     short loc_18000E9F0
0x18000e9c8  mov     [rbp+rax*2+40h+var_80], di
0x18000e9cd  jmp     loc_18000E821
0x18000e9d2  cmp     edx, r9d
0x18000e9d5  jle     short loc_18000E9E1
0x18000e9d7  mov     edx, r9d
0x18000e9da  add     [rbp+40h+var_BC], r13w
0x18000e9df  jmp     short loc_18000E963
0x18000e9e1  cmp     edx, 13h
0x18000e9e4  jg      short loc_18000E9DA
0x18000e9e6  add     [rbp+40h+var_BE], r13w
0x18000e9eb  jmp     loc_18000E963
0x18000e9f0  test    ax, ax
0x18000e9f3  jnz     short loc_18000EA00
0x18000e9f5  mov     [rsp+140h+var_DE], r13w
0x18000e9fb  jmp     loc_18000E742
0x18000ea00  mov     [rsp+140h+var_E0], r13w
0x18000ea06  jmp     loc_18000E742
0x18000ea0b  mov     eax, 5
0x18000ea10  mov     r10b, 13h
0x18000ea13  cmp     r11d, eax
0x18000ea16  cmovg   r11d, eax
0x18000ea1a  jmp     loc_18000E896
0x18000ea1f  lea     r8d, [r11-14h]
0x18000ea23  mov     edx, 5
0x18000ea28  jmp     loc_18000E8C0
```
