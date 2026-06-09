# EnumShowMount

- ea: `0x180003b40`
- end: `0x1800040c9`
- name: `EnumShowMount`
- size: `1417`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180005d70`

## callees

- `0x180002418`
- `0x180003b40`
- `0x18000895c`
- `0x180008d20`
- `0x180008d7c`
- `0x180008e80`
- `0x180009390`
- `0x180011b62`
- `0x180011ba0`

## import_xrefs

- `msvcrt!_snwprintf_s` at `0x180003d4b`
- `msvcrt!_snwprintf_s` at `0x180003f82`
- `msvcrt!_snwprintf_s` at `0x180003d4b`
- `msvcrt!_snwprintf_s` at `0x180003f82`
- `msvcrt!mbstowcs` at `0x180003cc6`
- `msvcrt!mbstowcs` at `0x180003f2c`
- `msvcrt!mbstowcs` at `0x180003cc6`
- `msvcrt!mbstowcs` at `0x180003f2c`

## string_xrefs

- `0x180003b76`: `EnumShowMount`

## pseudocode

```c
__int64 __fastcall EnumShowMount(__int64 a1, unsigned int *a2, _DWORD *a3, unsigned int *a4)
{
  unsigned int *v6; // r12
  _BYTE *v7; // rcx
  __int64 v8; // rdx
  unsigned int v9; // r14d
  unsigned int v10; // r13d
  __int64 v11; // rdi
  int v12; // r15d
  __int64 v13; // rcx
  __int64 v14; // rax
  int v15; // r12d
  _WORD *v16; // rcx
  const wchar_t *v17; // r9
  __int64 v18; // rax
  int v19; // eax
  unsigned int *v21; // rax
  __int64 v22; // r15
  _DWORD *v23; // r12
  __int64 v24; // r15
  __int64 v25; // rdi
  _WORD *v26; // rcx
  const wchar_t *v27; // r9
  bool v28; // cf
  int v29; // eax
  __int64 v30; // rax
  char v31; // [rsp+30h] [rbp-D0h]
  __int128 v35; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v36; // [rsp+60h] [rbp-A0h]
  char v37[16]; // [rsp+70h] [rbp-90h] BYREF
  wchar_t Buffer[264]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t Dest[264]; // [rsp+290h] [rbp+190h] BYREF

  v6 = a4;
  strcpy(v37, "EnumShowMount");
  memset_0(Dest, 0, 0x208u);
  memset_0(Buffer, 0, 0x208u);
  v35 = 0;
  v36 = 0;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      90,
      (unsigned int)&WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
      (unsigned int)v37,
      *a2);
    v7 = WPP_GLOBAL_Control;
  }
  if ( (*(_BYTE *)(a1 + 4) & 1) == 0 )
  {
    v9 = 0;
    v31 = 0;
    v10 = 0;
    goto LABEL_36;
  }
  if ( *(_DWORD *)(a1 + 24) == 1 )
  {
    if ( v7 != (_BYTE *)&WPP_GLOBAL_Control && (v7[28] & 1) != 0 )
    {
      v8 = 91;
      goto LABEL_49;
    }
    return 259;
  }
  v9 = 0;
  v31 = 0;
  v10 = 0;
  if ( v7 != (_BYTE *)&WPP_GLOBAL_Control && (v7[28] & 8) != 0 )
  {
    WPP_SF_s(*((_QWORD *)v7 + 2), 92, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, v37);
    v7 = WPP_GLOBAL_Control;
  }
  v11 = *(_QWORD *)(a1 + 96);
  if ( !v11 )
  {
    if ( *(_DWORD *)(a1 + 24) != 1 )
    {
      v11 = *(_QWORD *)(a1 + 88);
      v12 = 0;
      *(_QWORD *)(a1 + 96) = v11;
      if ( v11 )
        goto LABEL_17;
LABEL_15:
      v7 = WPP_GLOBAL_Control;
    }
LABEL_36:
    if ( v7 != (_BYTE *)&WPP_GLOBAL_Control && (v7[28] & 8) != 0 )
      WPP_SF_sd(
        *((_QWORD *)v7 + 2),
        94,
        (unsigned int)&WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
        (unsigned int)v37,
        v9);
    goto LABEL_39;
  }
  v12 = 0;
LABEL_17:
  while ( (unsigned int)mbstowcs(Dest, *(const char **)v11, 0x103u) - 1 > 0xFFFFFFFD )
  {
LABEL_30:
    v11 = *(_QWORD *)(v11 + 24);
    if ( !v11 )
      goto LABEL_15;
  }
  v13 = -1;
  do
    ++v13;
  while ( *(_WORD *)(*((_QWORD *)pGlobalNPCB + 5) + 2 * v13) );
  v14 = -1;
  do
    ++v14;
  while ( *(_WORD *)(*((_QWORD *)pGlobalNPCB + 6) + 2 * v14) );
  v15 = v14 + v13;
  v16 = *(_WORD **)(*(_QWORD *)(a1 + 104) + 24LL);
  if ( *v16 == 92 || (v17 = L"\\\\%s%s", v16[1] == 92) )
    v17 = L"%s%s";
  _snwprintf_s(Buffer, 0x104u, 0x103u, v17, v16, Dest);
  v18 = -1;
  do
    ++v18;
  while ( Buffer[v18] );
  v19 = v15 + v18;
  v6 = a4;
  v12 += 2 * v19 + 54;
  if ( !*a4 || v12 + v9 <= *a4 )
  {
    v9 += v12;
    ++v10;
    v31 = v9;
    if ( v10 >= *a2 )
      goto LABEL_15;
    goto LABEL_30;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, v37);
      v7 = WPP_GLOBAL_Control;
    }
    goto LABEL_36;
  }
LABEL_39:
  if ( v9 > *v6 )
  {
    *v6 = v9;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 95, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, v9);
    return 234;
  }
  if ( (*(_BYTE *)(a1 + 4) & 1) != 0 && !v10 )
  {
    *(_DWORD *)(a1 + 24) = 1;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 96;
LABEL_49:
      WPP_SF_s(*((_QWORD *)v7 + 2), v8, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, v37);
    }
    return 259;
  }
  v21 = a2;
  *a2 = v10;
  if ( (*(_BYTE *)(a1 + 4) & 1) != 0 )
  {
    v22 = *v6;
    v23 = a3;
    v24 = (__int64)a3 + v22;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, v37);
    v25 = *(_QWORD *)(a1 + 96);
    if ( v25 )
    {
      do
      {
        if ( !v10 )
          break;
        if ( (unsigned int)mbstowcs(Dest, *(const char **)v25, 0x104u) - 1 <= 0xFFFFFFFD )
        {
          v26 = *(_WORD **)(*(_QWORD *)(a1 + 104) + 24LL);
          if ( *v26 == 92 || (v27 = L"\\\\%s%s", v26[1] == 92) )
            v27 = L"%s%s";
          _snwprintf_s(Buffer, 0x104u, 0x103u, v27, v26, Dest);
          *((_QWORD *)&v35 + 1) = Buffer;
          *(_QWORD *)&v35 = 0;
          *(_QWORD *)&v36 = *((_QWORD *)pGlobalNPCB + 6);
          *((_QWORD *)&v36 + 1) = *((_QWORD *)pGlobalNPCB + 5);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_sS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              98,
              (unsigned int)&WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
              (unsigned int)v37,
              (__int64)Buffer);
          v28 = **(_BYTE **)v25 < 0x2Fu;
          if ( **(_BYTE **)v25 != 47 || (v28 = 0, *(_BYTE *)(*(_QWORD *)v25 + 1LL)) )
            v29 = v28 ? -1 : 1;
          else
            v29 = 0;
          v23[2] = v29 != 0 ? 3 : 0;
          *v23 = *(_DWORD *)a1;
          v23[1] = 1;
          v23[3] = 1;
          v30 = PackString(&v35, v23, NetResourceStrings, v24);
          v23 += 12;
          v24 = v30;
          --v10;
        }
        v25 = *(_QWORD *)(v25 + 24);
      }
      while ( v25 );
      LOBYTE(v9) = v31;
    }
    v21 = a2;
    *(_QWORD *)(a1 + 96) = v25;
    if ( !v25 )
      *(_DWORD *)(a1 + 24) = 1;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sdd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      99,
      (unsigned int)&WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
      (unsigned int)v37,
      *v21,
      v9);
  return 0;
}

```

## disassembly

```asm
0x180003b40  push    rbp
0x180003b42  push    rbx
0x180003b43  push    rsi
0x180003b44  push    rdi
0x180003b45  push    r12
0x180003b47  push    r13
0x180003b49  push    r14
0x180003b4b  push    r15
0x180003b4d  lea     rbp, [rsp-3B8h]
0x180003b55  sub     rsp, 4B8h
0x180003b5c  mov     rax, cs:__security_cookie
0x180003b63  xor     rax, rsp
0x180003b66  mov     [rbp+3F0h+var_50], rax
0x180003b6d  mov     eax, dword ptr cs:aEnumshowmount+8; "Mount"
0x180003b73  mov     rbx, rdx
0x180003b76  movsd   xmm0, qword ptr cs:aEnumshowmount; "EnumShowMount"
0x180003b7e  mov     rsi, rcx
0x180003b81  mov     dword ptr [rsp+4F0h+var_480+8], eax
0x180003b85  lea     rcx, [rbp+3F0h+Dest]; void *
0x180003b8c  movzx   eax, word ptr cs:aEnumshowmount+0Ch; "t"
0x180003b93  mov     edi, 208h
0x180003b98  mov     [rsp+4F0h+var_4A8], r8
0x180003b9d  mov     r12, r9
0x180003ba0  mov     [rsp+4F0h+var_4B8], rdx
0x180003ba5  mov     r8d, edi; Size
0x180003ba8  xor     edx, edx; Val
0x180003baa  mov     word ptr [rsp+4F0h+var_480+0Ch], ax
0x180003baf  mov     [rsp+4F0h+var_4B0], r9
0x180003bb4  movsd   qword ptr [rsp+4F0h+var_480], xmm0
0x180003bba  call    memset_0
0x180003bbf  mov     r8d, edi; Size
0x180003bc2  lea     rcx, [rbp+3F0h+Buffer]; void *
0x180003bc6  xor     edx, edx; Val
0x180003bc8  call    memset_0
0x180003bcd  xorps   xmm0, xmm0
0x180003bd0  movups  [rsp+4F0h+var_4A0], xmm0
0x180003bd5  movups  [rsp+4F0h+var_490], xmm0
0x180003bda  mov     rcx, cs:WPP_GLOBAL_Control
0x180003be1  lea     rax, WPP_GLOBAL_Control
0x180003be8  cmp     rcx, rax
0x180003beb  jz      short loc_180003C21
0x180003bed  test    byte ptr [rcx+1Ch], 1
0x180003bf1  jz      short loc_180003C21
0x180003bf3  mov     eax, [rbx]
0x180003bf5  lea     r9, [rsp+4F0h+var_480]
0x180003bfa  mov     rcx, [rcx+10h]
0x180003bfe  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180003c05  mov     edx, 5Ah ; 'Z'
0x180003c0a  mov     dword ptr [rsp+4F0h+var_4D0], eax
0x180003c0e  call    WPP_SF_sd
0x180003c13  mov     rcx, cs:WPP_GLOBAL_Control
0x180003c1a  lea     rax, WPP_GLOBAL_Control
0x180003c21  test    byte ptr [rsi+4], 1
0x180003c25  jz      loc_180003DEC
0x180003c2b  cmp     dword ptr [rsi+18h], 1
0x180003c2f  jnz     short loc_180003C4E
0x180003c31  cmp     rcx, rax
0x180003c34  jz      loc_180003EA4
0x180003c3a  test    byte ptr [rcx+1Ch], 1
0x180003c3e  jz      loc_180003EA4
0x180003c44  mov     edx, 5Bh ; '['
0x180003c49  jmp     loc_180003E8F
0x180003c4e  xor     ebx, ebx
0x180003c50  mov     r14d, ebx
0x180003c53  mov     dword ptr [rsp+4F0h+var_4C0], ebx
0x180003c57  mov     r13d, ebx
0x180003c5a  cmp     rcx, rax
0x180003c5d  jz      short loc_180003C84
0x180003c5f  test    byte ptr [rcx+1Ch], 8
0x180003c63  jz      short loc_180003C84
0x180003c65  mov     rcx, [rcx+10h]
0x180003c69  lea     edx, [rbx+5Ch]
0x180003c6c  lea     r9, [rsp+4F0h+var_480]
0x180003c71  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180003c78  call    WPP_SF_s
0x180003c7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180003c84  mov     rdi, [rsi+60h]
0x180003c88  test    rdi, rdi
0x180003c8b  jnz     short loc_180003CB3
0x180003c8d  cmp     dword ptr [rsi+18h], 1
0x180003c91  jz      loc_180003DF8
0x180003c97  mov     rdi, [rsi+58h]
0x180003c9b  mov     r15d, ebx
0x180003c9e  mov     [rsi+60h], rdi
0x180003ca2  test    rdi, rdi
0x180003ca5  jnz     short loc_180003CB6
0x180003ca7  mov     rcx, cs:WPP_GLOBAL_Control
0x180003cae  jmp     loc_180003DF8
0x180003cb3  mov     r15d, ebx
0x180003cb6  mov     rdx, [rdi]; Source
0x180003cb9  lea     rcx, [rbp+3F0h+Dest]; Dest
0x180003cc0  mov     r8d, 103h; MaxCount
0x180003cc6  call    cs:__imp_mbstowcs
0x180003ccc  dec     eax
0x180003cce  cmp     eax, 0FFFFFFFDh
0x180003cd1  ja      loc_180003D9B
0x180003cd7  mov     rax, cs:pGlobalNPCB
0x180003cde  or      r8, 0FFFFFFFFFFFFFFFFh
0x180003ce2  mov     rcx, r8
0x180003ce5  mov     rdx, [rax+28h]
0x180003ce9  inc     rcx
0x180003cec  cmp     [rdx+rcx*2], bx
0x180003cf0  jnz     short loc_180003CE9
0x180003cf2  mov     rdx, [rax+30h]
0x180003cf6  mov     rax, r8
0x180003cf9  inc     rax
0x180003cfc  cmp     [rdx+rax*2], bx
0x180003d00  jnz     short loc_180003CF9
0x180003d02  lea     r12d, [rax+rcx]
0x180003d06  mov     rax, [rsi+68h]
0x180003d0a  mov     rcx, [rax+18h]
0x180003d0e  mov     eax, 5Ch ; '\'
0x180003d13  cmp     [rcx], ax
0x180003d16  jz      short loc_180003D25
0x180003d18  lea     r9, aSS; "\\\\%s%s"
0x180003d1f  cmp     [rcx+2], ax
0x180003d23  jnz     short loc_180003D2C
0x180003d25  lea     r9, aSS_0; "%s%s"
0x180003d2c  mov     r8d, 103h; MaxCount
0x180003d32  lea     rax, [rbp+3F0h+Dest]
0x180003d39  mov     [rsp+4F0h+var_4C8], rax
0x180003d3e  mov     [rsp+4F0h+var_4D0], rcx
0x180003d43  lea     rcx, [rbp+3F0h+Buffer]; Buffer
0x180003d47  lea     edx, [r8+1]; BufferCount
0x180003d4b  call    cs:__imp__snwprintf_s
0x180003d51  lea     rcx, [rbp+3F0h+Buffer]
0x180003d55  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003d59  inc     rax
0x180003d5c  cmp     [rcx+rax*2], bx
0x180003d60  jnz     short loc_180003D59
0x180003d62  add     eax, r12d
0x180003d65  mov     r12, [rsp+4F0h+var_4B0]
0x180003d6a  lea     r15d, [r15+rax*2]
0x180003d6e  add     r15d, 36h ; '6'
0x180003d72  cmp     [r12], ebx
0x180003d76  jz      short loc_180003D82
0x180003d78  lea     eax, [r15+r14]
0x180003d7c  cmp     eax, [r12]
0x180003d80  ja      short loc_180003DB0
0x180003d82  mov     rax, [rsp+4F0h+var_4B8]
0x180003d87  add     r14d, r15d
0x180003d8a  inc     r13d
0x180003d8d  mov     dword ptr [rsp+4F0h+var_4C0], r14d
0x180003d92  cmp     r13d, [rax]
0x180003d95  jnb     loc_180003CA7
0x180003d9b  mov     rax, [rdi+18h]
0x180003d9f  mov     rdi, rax
0x180003da2  test    rax, rax
0x180003da5  jnz     loc_180003CB6
0x180003dab  jmp     loc_180003CA7
0x180003db0  mov     rcx, cs:WPP_GLOBAL_Control
0x180003db7  lea     rdi, WPP_GLOBAL_Control
0x180003dbe  cmp     rcx, rdi
0x180003dc1  jz      short loc_180003E29
0x180003dc3  test    byte ptr [rcx+1Ch], 8
0x180003dc7  jz      short loc_180003DFF
0x180003dc9  mov     rcx, [rcx+10h]
0x180003dcd  lea     r9, [rsp+4F0h+var_480]
0x180003dd2  mov     edx, 5Dh ; ']'
0x180003dd7  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180003dde  call    WPP_SF_s
0x180003de3  mov     rcx, cs:WPP_GLOBAL_Control
0x180003dea  jmp     short loc_180003DFF
0x180003dec  xor     ebx, ebx
0x180003dee  mov     r14d, ebx
0x180003df1  mov     dword ptr [rsp+4F0h+var_4C0], ebx
0x180003df5  mov     r13d, ebx
0x180003df8  lea     rdi, WPP_GLOBAL_Control
0x180003dff  cmp     rcx, rdi
0x180003e02  jz      short loc_180003E29
0x180003e04  test    byte ptr [rcx+1Ch], 8
0x180003e08  jz      short loc_180003E29
0x180003e0a  mov     rcx, [rcx+10h]
0x180003e0e  lea     r9, [rsp+4F0h+var_480]
0x180003e13  mov     edx, 5Eh ; '^'
0x180003e18  mov     dword ptr [rsp+4F0h+var_4D0], r14d
0x180003e1d  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180003e24  call    WPP_SF_sd
0x180003e29  cmp     r14d, [r12]
0x180003e2d  jbe     short loc_180003E67
0x180003e2f  mov     [r12], r14d
0x180003e33  mov     rcx, cs:WPP_GLOBAL_Control
0x180003e3a  cmp     rcx, rdi
0x180003e3d  jz      short loc_180003E5D
0x180003e3f  test    byte ptr [rcx+1Ch], 2
0x180003e43  jz      short loc_180003E5D
0x180003e45  mov     rcx, [rcx+10h]
0x180003e49  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180003e50  mov     edx, 5Fh ; '_'
0x180003e55  mov     r9d, r14d
0x180003e58  call    WPP_SF_d
0x180003e5d  mov     eax, 0EAh
0x180003e62  jmp     loc_1800040A6
0x180003e67  test    byte ptr [rsi+4], 1
0x180003e6b  jz      short loc_180003EAE
0x180003e6d  test    r13d, r13d
0x180003e70  jnz     short loc_180003EAE
0x180003e72  mov     dword ptr [rsi+18h], 1
0x180003e79  mov     rcx, cs:WPP_GLOBAL_Control
0x180003e80  cmp     rcx, rdi
0x180003e83  jz      short loc_180003EA4
0x180003e85  test    byte ptr [rcx+1Ch], 1
0x180003e89  jz      short loc_180003EA4
0x180003e8b  lea     edx, [r13+60h]
0x180003e8f  mov     rcx, [rcx+10h]
0x180003e93  lea     r9, [rsp+4F0h+var_480]
0x180003e98  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180003e9f  call    WPP_SF_s
0x180003ea4  mov     eax, 103h
0x180003ea9  jmp     loc_1800040A6
0x180003eae  mov     rax, [rsp+4F0h+var_4B8]
0x180003eb3  mov     [rax], r13d
0x180003eb6  test    byte ptr [rsi+4], 1
0x180003eba  jz      loc_18000406D
0x180003ec0  mov     r15d, [r12]
0x180003ec4  mov     r12, [rsp+4F0h+var_4A8]
0x180003ec9  add     r15, r12
0x180003ecc  mov     rcx, cs:WPP_GLOBAL_Control
0x180003ed3  lea     rax, WPP_GLOBAL_Control
0x180003eda  cmp     rcx, rax
0x180003edd  jz      short loc_180003EFF
0x180003edf  test    byte ptr [rcx+1Ch], 8
0x180003ee3  jz      short loc_180003EFF
0x180003ee5  mov     rcx, [rcx+10h]
0x180003ee9  lea     r9, [rsp+4F0h+var_480]
0x180003eee  mov     edx, 61h ; 'a'
0x180003ef3  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180003efa  call    WPP_SF_s
0x180003eff  mov     rdi, [rsi+60h]
0x180003f03  test    rdi, rdi
0x180003f06  jz      loc_180004051
0x180003f0c  lea     r14, WPP_GLOBAL_Control
0x180003f13  test    r13d, r13d
0x180003f16  jz      loc_18000404C
0x180003f1c  mov     rdx, [rdi]; Source
0x180003f1f  lea     rcx, [rbp+3F0h+Dest]; Dest
0x180003f26  mov     r8d, 104h; MaxCount
0x180003f2c  call    cs:__imp_mbstowcs
0x180003f32  dec     eax
0x180003f34  cmp     eax, 0FFFFFFFDh
0x180003f37  ja      loc_18000403C
0x180003f3d  mov     rax, [rsi+68h]
0x180003f41  mov     rcx, [rax+18h]
0x180003f45  mov     eax, 5Ch ; '\'
0x180003f4a  cmp     [rcx], ax
0x180003f4d  jz      short loc_180003F5C
0x180003f4f  lea     r9, aSS; "\\\\%s%s"
0x180003f56  cmp     [rcx+2], ax
0x180003f5a  jnz     short loc_180003F63
0x180003f5c  lea     r9, aSS_0; "%s%s"
0x180003f63  mov     r8d, 103h; MaxCount
0x180003f69  lea     rax, [rbp+3F0h+Dest]
0x180003f70  mov     [rsp+4F0h+var_4C8], rax
0x180003f75  mov     [rsp+4F0h+var_4D0], rcx
0x180003f7a  lea     rcx, [rbp+3F0h+Buffer]; Buffer
0x180003f7e  lea     edx, [r8+1]; BufferCount
0x180003f82  call    cs:__imp__snwprintf_s
0x180003f88  mov     rcx, cs:pGlobalNPCB
0x180003f8f  lea     rax, [rbp+3F0h+Buffer]
0x180003f93  mov     qword ptr [rsp+4F0h+var_4A0+8], rax
0x180003f98  mov     qword ptr [rsp+4F0h+var_4A0], rbx
0x180003f9d  mov     rax, [rcx+30h]
0x180003fa1  mov     qword ptr [rsp+4F0h+var_490], rax
0x180003fa6  mov     rax, [rcx+28h]
0x180003faa  mov     qword ptr [rsp+4F0h+var_490+8], rax
0x180003faf  mov     rcx, cs:WPP_GLOBAL_Control
0x180003fb6  cmp     rcx, r14
0x180003fb9  jz      short loc_180003FE4
0x180003fbb  test    byte ptr [rcx+1Ch], 8
0x180003fbf  jz      short loc_180003FE4
0x180003fc1  mov     rcx, [rcx+10h]
0x180003fc5  lea     rax, [rbp+3F0h+Buffer]
0x180003fc9  mov     edx, 62h ; 'b'
0x180003fce  mov     [rsp+4F0h+var_4D0], rax
0x180003fd3  lea     r9, [rsp+4F0h+var_480]
0x180003fd8  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180003fdf  call    WPP_SF_sS
0x180003fe4  mov     rax, [rdi]
0x180003fe7  cmp     byte ptr [rax], 2Fh ; '/'
0x180003fea  jnz     short loc_180003FF5
0x180003fec  cmp     [rax+1], bl
0x180003fef  jnz     short loc_180003FF5
0x180003ff1  mov     eax, ebx
0x180003ff3  jmp     short loc_180003FFA
0x180003ff5  sbb     eax, eax
0x180003ff7  or      eax, 1
0x180003ffa  neg     eax
0x180003ffc  lea     r8, NetResourceStrings
0x180004003  mov     r9, r15
0x180004006  lea     rcx, [rsp+4F0h+var_4A0]
0x18000400b  sbb     eax, eax
0x18000400d  mov     rdx, r12
0x180004010  and     eax, 3
0x180004013  mov     [r12+8], eax
0x180004018  mov     eax, [rsi]
0x18000401a  mov     [r12], eax
0x18000401e  mov     eax, 1
0x180004023  mov     [r12+4], eax
0x180004028  mov     [r12+0Ch], eax
0x18000402d  call    PackString
  ... truncated ...
```
