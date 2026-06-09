# EnumShowMount

- ea: `0x180003cf0`
- end: `0x180004292`
- name: `EnumShowMount`
- size: `1442`
- prototype: `__int64 __fastcall(__int64, unsigned int *, _DWORD *, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800061c0`

## callees

- `0x180002538`
- `0x180003cf0`
- `0x180008f88`
- `0x18000937c`
- `0x1800093e0`
- `0x1800094f4`
- `0x180009a2c`
- `0x180012e32`
- `0x180012e70`

## import_xrefs

- `msvcrt!_snwprintf_s` at `0x180003f01`
- `msvcrt!_snwprintf_s` at `0x180004144`
- `msvcrt!_snwprintf_s` at `0x180003f01`
- `msvcrt!_snwprintf_s` at `0x180004144`
- `msvcrt!mbstowcs` at `0x180003e76`
- `msvcrt!mbstowcs` at `0x1800040e8`
- `msvcrt!mbstowcs` at `0x180003e76`
- `msvcrt!mbstowcs` at `0x1800040e8`

## string_xrefs

- `0x180003d26`: `EnumShowMount`

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
0x180003cf0  push    rbp
0x180003cf2  push    rbx
0x180003cf3  push    rsi
0x180003cf4  push    rdi
0x180003cf5  push    r12
0x180003cf7  push    r13
0x180003cf9  push    r14
0x180003cfb  push    r15
0x180003cfd  lea     rbp, [rsp-3B8h]
0x180003d05  sub     rsp, 4B8h
0x180003d0c  mov     rax, cs:__security_cookie
0x180003d13  xor     rax, rsp
0x180003d16  mov     [rbp+3F0h+var_50], rax
0x180003d1d  mov     eax, dword ptr cs:aEnumshowmount+8; "Mount"
0x180003d23  mov     rbx, rdx
0x180003d26  movsd   xmm0, qword ptr cs:aEnumshowmount; "EnumShowMount"
0x180003d2e  mov     rsi, rcx
0x180003d31  mov     dword ptr [rsp+4F0h+var_480+8], eax
0x180003d35  lea     rcx, [rbp+3F0h+Dest]; void *
0x180003d3c  movzx   eax, word ptr cs:aEnumshowmount+0Ch; "t"
0x180003d43  mov     edi, 208h
0x180003d48  mov     [rsp+4F0h+var_4A8], r8
0x180003d4d  mov     r12, r9
0x180003d50  mov     [rsp+4F0h+var_4B8], rdx
0x180003d55  mov     r8d, edi; Size
0x180003d58  xor     edx, edx; Val
0x180003d5a  mov     word ptr [rsp+4F0h+var_480+0Ch], ax
0x180003d5f  mov     [rsp+4F0h+var_4B0], r9
0x180003d64  movsd   qword ptr [rsp+4F0h+var_480], xmm0
0x180003d6a  call    memset_0
0x180003d6f  mov     r8d, edi; Size
0x180003d72  lea     rcx, [rbp+3F0h+Buffer]; void *
0x180003d76  xor     edx, edx; Val
0x180003d78  call    memset_0
0x180003d7d  xorps   xmm0, xmm0
0x180003d80  movups  [rsp+4F0h+var_4A0], xmm0
0x180003d85  movups  [rsp+4F0h+var_490], xmm0
0x180003d8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180003d91  lea     rax, WPP_GLOBAL_Control
0x180003d98  cmp     rcx, rax
0x180003d9b  jz      short loc_180003DD1
0x180003d9d  test    byte ptr [rcx+1Ch], 1
0x180003da1  jz      short loc_180003DD1
0x180003da3  mov     eax, [rbx]
0x180003da5  lea     r9, [rsp+4F0h+var_480]
0x180003daa  mov     rcx, [rcx+10h]
0x180003dae  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180003db5  mov     edx, 5Ah ; 'Z'
0x180003dba  mov     dword ptr [rsp+4F0h+var_4D0], eax
0x180003dbe  call    WPP_SF_sd
0x180003dc3  mov     rcx, cs:WPP_GLOBAL_Control
0x180003dca  lea     rax, WPP_GLOBAL_Control
0x180003dd1  test    byte ptr [rsi+4], 1
0x180003dd5  jz      loc_180003FA8
0x180003ddb  cmp     dword ptr [rsi+18h], 1
0x180003ddf  jnz     short loc_180003DFE
0x180003de1  cmp     rcx, rax
0x180003de4  jz      loc_180004060
0x180003dea  test    byte ptr [rcx+1Ch], 1
0x180003dee  jz      loc_180004060
0x180003df4  mov     edx, 5Bh ; '['
0x180003df9  jmp     loc_18000404B
0x180003dfe  xor     ebx, ebx
0x180003e00  mov     r14d, ebx
0x180003e03  mov     dword ptr [rsp+4F0h+var_4C0], ebx
0x180003e07  mov     r13d, ebx
0x180003e0a  cmp     rcx, rax
0x180003e0d  jz      short loc_180003E34
0x180003e0f  test    byte ptr [rcx+1Ch], 8
0x180003e13  jz      short loc_180003E34
0x180003e15  mov     rcx, [rcx+10h]
0x180003e19  lea     edx, [rbx+5Ch]
0x180003e1c  lea     r9, [rsp+4F0h+var_480]
0x180003e21  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180003e28  call    WPP_SF_s
0x180003e2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180003e34  mov     rdi, [rsi+60h]
0x180003e38  test    rdi, rdi
0x180003e3b  jnz     short loc_180003E63
0x180003e3d  cmp     dword ptr [rsi+18h], 1
0x180003e41  jz      loc_180003FB4
0x180003e47  mov     rdi, [rsi+58h]
0x180003e4b  mov     r15d, ebx
0x180003e4e  mov     [rsi+60h], rdi
0x180003e52  test    rdi, rdi
0x180003e55  jnz     short loc_180003E66
0x180003e57  mov     rcx, cs:WPP_GLOBAL_Control
0x180003e5e  jmp     loc_180003FB4
0x180003e63  mov     r15d, ebx
0x180003e66  mov     rdx, [rdi]; Source
0x180003e69  lea     rcx, [rbp+3F0h+Dest]; Dest
0x180003e70  mov     r8d, 103h; MaxCount
0x180003e76  call    cs:__imp_mbstowcs
0x180003e7d  nop     dword ptr [rax+rax+00h]
0x180003e82  dec     eax
0x180003e84  cmp     eax, 0FFFFFFFDh
0x180003e87  ja      loc_180003F57
0x180003e8d  mov     rax, cs:pGlobalNPCB
0x180003e94  or      r8, 0FFFFFFFFFFFFFFFFh
0x180003e98  mov     rcx, r8
0x180003e9b  mov     rdx, [rax+28h]
0x180003e9f  inc     rcx
0x180003ea2  cmp     [rdx+rcx*2], bx
0x180003ea6  jnz     short loc_180003E9F
0x180003ea8  mov     rdx, [rax+30h]
0x180003eac  mov     rax, r8
0x180003eaf  inc     rax
0x180003eb2  cmp     [rdx+rax*2], bx
0x180003eb6  jnz     short loc_180003EAF
0x180003eb8  lea     r12d, [rax+rcx]
0x180003ebc  mov     rax, [rsi+68h]
0x180003ec0  mov     rcx, [rax+18h]
0x180003ec4  mov     eax, 5Ch ; '\'
0x180003ec9  cmp     [rcx], ax
0x180003ecc  jz      short loc_180003EDB
0x180003ece  lea     r9, aSS; "\\\\%s%s"
0x180003ed5  cmp     [rcx+2], ax
0x180003ed9  jnz     short loc_180003EE2
0x180003edb  lea     r9, aSS_0; "%s%s"
0x180003ee2  mov     r8d, 103h; MaxCount
0x180003ee8  lea     rax, [rbp+3F0h+Dest]
0x180003eef  mov     [rsp+4F0h+var_4C8], rax
0x180003ef4  mov     [rsp+4F0h+var_4D0], rcx
0x180003ef9  lea     rcx, [rbp+3F0h+Buffer]; Buffer
0x180003efd  lea     edx, [r8+1]; BufferCount
0x180003f01  call    cs:__imp__snwprintf_s
0x180003f08  nop     dword ptr [rax+rax+00h]
0x180003f0d  lea     rcx, [rbp+3F0h+Buffer]
0x180003f11  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003f15  inc     rax
0x180003f18  cmp     [rcx+rax*2], bx
0x180003f1c  jnz     short loc_180003F15
0x180003f1e  add     eax, r12d
0x180003f21  mov     r12, [rsp+4F0h+var_4B0]
0x180003f26  lea     r15d, [r15+rax*2]
0x180003f2a  add     r15d, 36h ; '6'
0x180003f2e  cmp     [r12], ebx
0x180003f32  jz      short loc_180003F3E
0x180003f34  lea     eax, [r15+r14]
0x180003f38  cmp     eax, [r12]
0x180003f3c  ja      short loc_180003F6C
0x180003f3e  mov     rax, [rsp+4F0h+var_4B8]
0x180003f43  add     r14d, r15d
0x180003f46  inc     r13d
0x180003f49  mov     dword ptr [rsp+4F0h+var_4C0], r14d
0x180003f4e  cmp     r13d, [rax]
0x180003f51  jnb     loc_180003E57
0x180003f57  mov     rax, [rdi+18h]
0x180003f5b  mov     rdi, rax
0x180003f5e  test    rax, rax
0x180003f61  jnz     loc_180003E66
0x180003f67  jmp     loc_180003E57
0x180003f6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180003f73  lea     rdi, WPP_GLOBAL_Control
0x180003f7a  cmp     rcx, rdi
0x180003f7d  jz      short loc_180003FE5
0x180003f7f  test    byte ptr [rcx+1Ch], 8
0x180003f83  jz      short loc_180003FBB
0x180003f85  mov     rcx, [rcx+10h]
0x180003f89  lea     r9, [rsp+4F0h+var_480]
0x180003f8e  mov     edx, 5Dh ; ']'
0x180003f93  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180003f9a  call    WPP_SF_s
0x180003f9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180003fa6  jmp     short loc_180003FBB
0x180003fa8  xor     ebx, ebx
0x180003faa  mov     r14d, ebx
0x180003fad  mov     dword ptr [rsp+4F0h+var_4C0], ebx
0x180003fb1  mov     r13d, ebx
0x180003fb4  lea     rdi, WPP_GLOBAL_Control
0x180003fbb  cmp     rcx, rdi
0x180003fbe  jz      short loc_180003FE5
0x180003fc0  test    byte ptr [rcx+1Ch], 8
0x180003fc4  jz      short loc_180003FE5
0x180003fc6  mov     rcx, [rcx+10h]
0x180003fca  lea     r9, [rsp+4F0h+var_480]
0x180003fcf  mov     edx, 5Eh ; '^'
0x180003fd4  mov     dword ptr [rsp+4F0h+var_4D0], r14d
0x180003fd9  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180003fe0  call    WPP_SF_sd
0x180003fe5  cmp     r14d, [r12]
0x180003fe9  jbe     short loc_180004023
0x180003feb  mov     [r12], r14d
0x180003fef  mov     rcx, cs:WPP_GLOBAL_Control
0x180003ff6  cmp     rcx, rdi
0x180003ff9  jz      short loc_180004019
0x180003ffb  test    byte ptr [rcx+1Ch], 2
0x180003fff  jz      short loc_180004019
0x180004001  mov     rcx, [rcx+10h]
0x180004005  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x18000400c  mov     edx, 5Fh ; '_'
0x180004011  mov     r9d, r14d
0x180004014  call    WPP_SF_d
0x180004019  mov     eax, 0EAh
0x18000401e  jmp     loc_18000426E
0x180004023  test    byte ptr [rsi+4], 1
0x180004027  jz      short loc_18000406A
0x180004029  test    r13d, r13d
0x18000402c  jnz     short loc_18000406A
0x18000402e  mov     dword ptr [rsi+18h], 1
0x180004035  mov     rcx, cs:WPP_GLOBAL_Control
0x18000403c  cmp     rcx, rdi
0x18000403f  jz      short loc_180004060
0x180004041  test    byte ptr [rcx+1Ch], 1
0x180004045  jz      short loc_180004060
0x180004047  lea     edx, [r13+60h]
0x18000404b  mov     rcx, [rcx+10h]
0x18000404f  lea     r9, [rsp+4F0h+var_480]
0x180004054  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x18000405b  call    WPP_SF_s
0x180004060  mov     eax, 103h
0x180004065  jmp     loc_18000426E
0x18000406a  mov     rax, [rsp+4F0h+var_4B8]
0x18000406f  mov     [rax], r13d
0x180004072  test    byte ptr [rsi+4], 1
0x180004076  jz      loc_180004235
0x18000407c  mov     r15d, [r12]
0x180004080  mov     r12, [rsp+4F0h+var_4A8]
0x180004085  add     r15, r12
0x180004088  mov     rcx, cs:WPP_GLOBAL_Control
0x18000408f  lea     rax, WPP_GLOBAL_Control
0x180004096  cmp     rcx, rax
0x180004099  jz      short loc_1800040BB
0x18000409b  test    byte ptr [rcx+1Ch], 8
0x18000409f  jz      short loc_1800040BB
0x1800040a1  mov     rcx, [rcx+10h]
0x1800040a5  lea     r9, [rsp+4F0h+var_480]
0x1800040aa  mov     edx, 61h ; 'a'
0x1800040af  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x1800040b6  call    WPP_SF_s
0x1800040bb  mov     rdi, [rsi+60h]
0x1800040bf  test    rdi, rdi
0x1800040c2  jz      loc_180004219
0x1800040c8  lea     r14, WPP_GLOBAL_Control
0x1800040cf  test    r13d, r13d
0x1800040d2  jz      loc_180004214
0x1800040d8  mov     rdx, [rdi]; Source
0x1800040db  lea     rcx, [rbp+3F0h+Dest]; Dest
0x1800040e2  mov     r8d, 104h; MaxCount
0x1800040e8  call    cs:__imp_mbstowcs
0x1800040ef  nop     dword ptr [rax+rax+00h]
0x1800040f4  dec     eax
0x1800040f6  cmp     eax, 0FFFFFFFDh
0x1800040f9  ja      loc_180004204
0x1800040ff  mov     rax, [rsi+68h]
0x180004103  mov     rcx, [rax+18h]
0x180004107  mov     eax, 5Ch ; '\'
0x18000410c  cmp     [rcx], ax
0x18000410f  jz      short loc_18000411E
0x180004111  lea     r9, aSS; "\\\\%s%s"
0x180004118  cmp     [rcx+2], ax
0x18000411c  jnz     short loc_180004125
0x18000411e  lea     r9, aSS_0; "%s%s"
0x180004125  mov     r8d, 103h; MaxCount
0x18000412b  lea     rax, [rbp+3F0h+Dest]
0x180004132  mov     [rsp+4F0h+var_4C8], rax
0x180004137  mov     [rsp+4F0h+var_4D0], rcx
0x18000413c  lea     rcx, [rbp+3F0h+Buffer]; Buffer
0x180004140  lea     edx, [r8+1]; BufferCount
0x180004144  call    cs:__imp__snwprintf_s
0x18000414b  nop     dword ptr [rax+rax+00h]
0x180004150  mov     rcx, cs:pGlobalNPCB
0x180004157  lea     rax, [rbp+3F0h+Buffer]
0x18000415b  mov     qword ptr [rsp+4F0h+var_4A0+8], rax
0x180004160  mov     qword ptr [rsp+4F0h+var_4A0], rbx
0x180004165  mov     rax, [rcx+30h]
0x180004169  mov     qword ptr [rsp+4F0h+var_490], rax
0x18000416e  mov     rax, [rcx+28h]
0x180004172  mov     qword ptr [rsp+4F0h+var_490+8], rax
0x180004177  mov     rcx, cs:WPP_GLOBAL_Control
0x18000417e  cmp     rcx, r14
0x180004181  jz      short loc_1800041AC
0x180004183  test    byte ptr [rcx+1Ch], 8
0x180004187  jz      short loc_1800041AC
0x180004189  mov     rcx, [rcx+10h]
0x18000418d  lea     rax, [rbp+3F0h+Buffer]
0x180004191  mov     edx, 62h ; 'b'
0x180004196  mov     [rsp+4F0h+var_4D0], rax
0x18000419b  lea     r9, [rsp+4F0h+var_480]
0x1800041a0  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x1800041a7  call    WPP_SF_sS
0x1800041ac  mov     rax, [rdi]
0x1800041af  cmp     byte ptr [rax], 2Fh ; '/'
0x1800041b2  jnz     short loc_1800041BD
0x1800041b4  cmp     [rax+1], bl
0x1800041b7  jnz     short loc_1800041BD
0x1800041b9  mov     eax, ebx
0x1800041bb  jmp     short loc_1800041C2
0x1800041bd  sbb     eax, eax
0x1800041bf  or      eax, 1
0x1800041c2  neg     eax
0x1800041c4  lea     r8, NetResourceStrings
0x1800041cb  mov     r9, r15
0x1800041ce  lea     rcx, [rsp+4F0h+var_4A0]
0x1800041d3  sbb     eax, eax
0x1800041d5  mov     rdx, r12
0x1800041d8  and     eax, 3
0x1800041db  mov     [r12+8], eax
0x1800041e0  mov     eax, [rsi]
0x1800041e2  mov     [r12], eax
  ... truncated ...
```
