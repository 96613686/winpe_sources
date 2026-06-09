# PACreateMMAuthInfos

- ea: `0x180027b24`
- end: `0x180027e5b`
- name: `PACreateMMAuthInfos`
- size: `823`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180027e64`

## callees

- `0x180006f00`
- `0x18000e510`
- `0x18001be74`
- `0x180027984`
- `0x180027b24`
- `0x180042ef8`
- `0x18004d052`

## pseudocode

```c
__int64 __fastcall PACreateMMAuthInfos(unsigned int a1, __int64 a2, unsigned int *a3, _QWORD *a4)
{
  unsigned int *v6; // rdi
  _QWORD *v7; // rbp
  unsigned int v8; // eax
  unsigned int v9; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  LPVOID v13; // rax
  LPVOID v14; // r12
  _QWORD *v15; // rsi
  unsigned int i; // r14d
  int *v17; // rdi
  int v18; // eax
  __int64 v19; // rcx
  unsigned int v20; // eax
  size_t v21; // rbp
  void *v22; // rax
  void *v23; // rax
  const WCHAR *v24; // rcx
  __int64 v25; // r9
  _QWORD *v26; // rcx
  __int64 v27; // rdx
  size_t Size[9]; // [rsp+20h] [rbp-48h] BYREF

  v6 = a3;
  Size[0] = 0;
  v7 = a4;
  v8 = NsuSizeTMultiply(a1, 24, Size);
  v9 = v8;
  if ( v8 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_50;
    v11 = 19;
    v12 = v8;
LABEL_5:
    WPP_SF_d(v10[2], v11, WPP_3886d72ed9b13ccdc9fcf8afdec51da0_Traceguids, v12);
LABEL_50:
    *v6 = 0;
    *v7 = 0;
    return v9;
  }
  v13 = IpsecAllocMem(Size[0]);
  v14 = v13;
  if ( !v13 )
  {
    v12 = 8;
    v9 = 8;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_50;
    v11 = 20;
    goto LABEL_5;
  }
  v15 = v13;
  for ( i = 0; i < a1; ++i )
  {
    v17 = *(int **)(a2 + 8LL * i);
    v18 = *v17;
    *(_DWORD *)v15 = *v17;
    if ( v18 == 3 )
    {
      if ( v17[4] && *((_QWORD *)v17 + 3) )
      {
        v23 = IpsecAllocMem((unsigned int)v17[4]);
        v15[1] = v23;
        if ( !v23 )
        {
          v25 = 8;
          v9 = 8;
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            v27 = 21;
            goto LABEL_48;
          }
          goto LABEL_49;
        }
        *((_DWORD *)v15 + 1) = v17[4];
        memcpy_0(v23, *((const void **)v17 + 3), (unsigned int)v17[4]);
      }
      else
      {
        if ( !v17[1] || (v24 = (const WCHAR *)*((_QWORD *)v17 + 1)) == 0 )
        {
          v25 = 87;
          v9 = 87;
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            v27 = 22;
LABEL_48:
            WPP_SF_d(v26[2], v27, WPP_3886d72ed9b13ccdc9fcf8afdec51da0_Traceguids, v25);
          }
LABEL_49:
          FreeIniMMAuthInfos(i, v14);
          v7 = a4;
          v6 = a3;
          goto LABEL_50;
        }
        v20 = EncodeName(v24);
        v9 = v20;
        if ( v20 )
        {
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          {
            goto LABEL_49;
          }
          v27 = 23;
          goto LABEL_35;
        }
      }
      *((_DWORD *)v15 + 4) = v17[8];
    }
    else if ( v18 == 5 )
    {
      *((_DWORD *)v15 + 1) = 0;
      v15[1] = 0;
    }
    else
    {
      if ( !v17[1] || !*((_QWORD *)v17 + 1) )
      {
        v25 = 87;
        v9 = 87;
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v27 = 24;
          goto LABEL_48;
        }
        goto LABEL_49;
      }
      v19 = (unsigned int)v17[1];
      Size[0] = 0;
      v20 = NsuSizeTMultiply(v19, 2, Size);
      v9 = v20;
      if ( v20 )
      {
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          goto LABEL_49;
        v27 = 25;
LABEL_35:
        v25 = v20;
        goto LABEL_48;
      }
      v21 = Size[0];
      v22 = IpsecAllocMem(Size[0]);
      v15[1] = v22;
      if ( !v22 )
      {
        v25 = 8;
        v9 = 8;
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v27 = 26;
          goto LABEL_48;
        }
        goto LABEL_49;
      }
      *((_DWORD *)v15 + 1) = v21;
      memcpy_0(v22, *((const void **)v17 + 1), v21);
    }
    v15 += 3;
  }
  *a3 = a1;
  *a4 = v14;
  return v9;
}

```

## disassembly

```asm
0x180027b24  mov     rax, rsp
0x180027b27  mov     [rax+8], rbx
0x180027b2b  mov     [rax+20h], r9
0x180027b2f  mov     [rax+18h], r8
0x180027b33  push    rbp
0x180027b34  push    rsi
0x180027b35  push    rdi
0x180027b36  push    r12
0x180027b38  push    r13
0x180027b3a  push    r14
0x180027b3c  push    r15
0x180027b3e  sub     rsp, 30h
0x180027b42  mov     r13, rdx
0x180027b45  mov     r15d, ecx
0x180027b48  mov     rdi, r8
0x180027b4b  mov     ecx, ecx
0x180027b4d  lea     r8, [rax-48h]
0x180027b51  mov     qword ptr [rax-48h], 0
0x180027b59  mov     edx, 18h
0x180027b5e  mov     rbp, r9
0x180027b61  call    NsuSizeTMultiply
0x180027b66  mov     ebx, eax
0x180027b68  test    eax, eax
0x180027b6a  jz      short loc_180027BAA
0x180027b6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180027b73  lea     rdx, WPP_GLOBAL_Control
0x180027b7a  cmp     rcx, rdx
0x180027b7d  jz      loc_180027E1E
0x180027b83  test    byte ptr [rcx+1Ch], 10h
0x180027b87  jz      loc_180027E1E
0x180027b8d  mov     edx, 13h
0x180027b92  mov     r9d, eax
0x180027b95  mov     rcx, [rcx+10h]
0x180027b99  lea     r8, WPP_3886d72ed9b13ccdc9fcf8afdec51da0_Traceguids
0x180027ba0  call    WPP_SF_d
0x180027ba5  jmp     loc_180027E1E
0x180027baa  mov     rcx, [rsp+68h+Size]
0x180027baf  call    IpsecAllocMem
0x180027bb4  mov     r12, rax
0x180027bb7  test    rax, rax
0x180027bba  jnz     short loc_180027BE9
0x180027bbc  lea     r9d, [rax+8]
0x180027bc0  mov     ebx, r9d
0x180027bc3  mov     rcx, cs:WPP_GLOBAL_Control
0x180027bca  lea     rdx, WPP_GLOBAL_Control
0x180027bd1  cmp     rcx, rdx
0x180027bd4  jz      loc_180027E1E
0x180027bda  test    byte ptr [rcx+1Ch], 10h
0x180027bde  jz      loc_180027E1E
0x180027be4  lea     edx, [rax+14h]
0x180027be7  jmp     short loc_180027B95
0x180027be9  xor     ebp, ebp
0x180027beb  mov     rsi, r12
0x180027bee  mov     r14d, ebp
0x180027bf1  cmp     r14d, r15d
0x180027bf4  jnb     loc_180027E2E
0x180027bfa  mov     eax, r14d
0x180027bfd  mov     rdi, [r13+rax*8+0]
0x180027c02  mov     eax, [rdi]
0x180027c04  mov     [rsi], eax
0x180027c06  cmp     eax, 3
0x180027c09  jz      short loc_180027C7D
0x180027c0b  cmp     eax, 5
0x180027c0e  jz      short loc_180027C74
0x180027c10  cmp     [rdi+4], ebp
0x180027c13  jz      loc_180027D55
0x180027c19  cmp     [rdi+8], rbp
0x180027c1d  jz      loc_180027D55
0x180027c23  mov     ecx, [rdi+4]
0x180027c26  lea     r8, [rsp+68h+Size]
0x180027c2b  mov     edx, 2
0x180027c30  mov     [rsp+68h+Size], rbp
0x180027c35  call    NsuSizeTMultiply
0x180027c3a  mov     ebx, eax
0x180027c3c  test    eax, eax
0x180027c3e  jnz     loc_180027D27
0x180027c44  mov     rbp, [rsp+68h+Size]
0x180027c49  mov     rcx, rbp
0x180027c4c  call    IpsecAllocMem
0x180027c51  mov     [rsi+8], rax
0x180027c55  test    rax, rax
0x180027c58  jz      loc_180027CF4
0x180027c5e  mov     [rsi+4], ebp
0x180027c61  mov     r8, rbp; Size
0x180027c64  mov     rdx, [rdi+8]; Src
0x180027c68  mov     rcx, rax; void *
0x180027c6b  call    memcpy_0
0x180027c70  xor     ebp, ebp
0x180027c72  jmp     short loc_180027CE8
0x180027c74  mov     [rsi+4], ebp
0x180027c77  mov     [rsi+8], rbp
0x180027c7b  jmp     short loc_180027CE8
0x180027c7d  cmp     [rdi+10h], ebp
0x180027c80  jz      short loc_180027CB5
0x180027c82  cmp     [rdi+18h], rbp
0x180027c86  jz      short loc_180027CB5
0x180027c88  mov     ecx, [rdi+10h]
0x180027c8b  call    IpsecAllocMem
0x180027c90  mov     [rsi+8], rax
0x180027c94  test    rax, rax
0x180027c97  jz      loc_180027D85
0x180027c9d  mov     ecx, [rdi+10h]
0x180027ca0  mov     [rsi+4], ecx
0x180027ca3  mov     rcx, rax; void *
0x180027ca6  mov     r8d, [rdi+10h]; Size
0x180027caa  mov     rdx, [rdi+18h]; Src
0x180027cae  call    memcpy_0
0x180027cb3  jmp     short loc_180027CE2
0x180027cb5  cmp     [rdi+4], ebp
0x180027cb8  jz      loc_180027DCD
0x180027cbe  mov     rcx, [rdi+8]; pszX500
0x180027cc2  test    rcx, rcx
0x180027cc5  jz      loc_180027DCD
0x180027ccb  lea     r8, [rsi+4]
0x180027ccf  lea     rdx, [rsi+8]
0x180027cd3  call    EncodeName
0x180027cd8  mov     ebx, eax
0x180027cda  test    eax, eax
0x180027cdc  jnz     loc_180027DAD
0x180027ce2  mov     eax, [rdi+20h]
0x180027ce5  mov     [rsi+10h], eax
0x180027ce8  add     rsi, 18h
0x180027cec  inc     r14d
0x180027cef  jmp     loc_180027BF1
0x180027cf4  mov     r9d, 8
0x180027cfa  mov     ebx, r9d
0x180027cfd  mov     rcx, cs:WPP_GLOBAL_Control
0x180027d04  lea     rdx, WPP_GLOBAL_Control
0x180027d0b  cmp     rcx, rdx
0x180027d0e  jz      loc_180027E03
0x180027d14  test    byte ptr [rcx+1Ch], 10h
0x180027d18  jz      loc_180027E03
0x180027d1e  lea     edx, [r9+12h]
0x180027d22  jmp     loc_180027DF3
0x180027d27  mov     rcx, cs:WPP_GLOBAL_Control
0x180027d2e  lea     rdx, WPP_GLOBAL_Control
0x180027d35  cmp     rcx, rdx
0x180027d38  jz      loc_180027E03
0x180027d3e  test    byte ptr [rcx+1Ch], 10h
0x180027d42  jz      loc_180027E03
0x180027d48  mov     edx, 19h
0x180027d4d  mov     r9d, eax
0x180027d50  jmp     loc_180027DF3
0x180027d55  mov     r9d, 57h ; 'W'
0x180027d5b  mov     ebx, r9d
0x180027d5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180027d65  lea     rdx, WPP_GLOBAL_Control
0x180027d6c  cmp     rcx, rdx
0x180027d6f  jz      loc_180027E03
0x180027d75  test    byte ptr [rcx+1Ch], 10h
0x180027d79  jz      loc_180027E03
0x180027d7f  lea     edx, [r9-3Fh]
0x180027d83  jmp     short loc_180027DF3
0x180027d85  mov     r9d, 8
0x180027d8b  mov     ebx, r9d
0x180027d8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180027d95  lea     rdx, WPP_GLOBAL_Control
0x180027d9c  cmp     rcx, rdx
0x180027d9f  jz      short loc_180027E03
0x180027da1  test    byte ptr [rcx+1Ch], 10h
0x180027da5  jz      short loc_180027E03
0x180027da7  lea     edx, [r9+0Dh]
0x180027dab  jmp     short loc_180027DF3
0x180027dad  mov     rcx, cs:WPP_GLOBAL_Control
0x180027db4  lea     rdx, WPP_GLOBAL_Control
0x180027dbb  cmp     rcx, rdx
0x180027dbe  jz      short loc_180027E03
0x180027dc0  test    byte ptr [rcx+1Ch], 10h
0x180027dc4  jz      short loc_180027E03
0x180027dc6  mov     edx, 17h
0x180027dcb  jmp     short loc_180027D4D
0x180027dcd  mov     r9d, 57h ; 'W'
0x180027dd3  mov     ebx, r9d
0x180027dd6  mov     rcx, cs:WPP_GLOBAL_Control
0x180027ddd  lea     rdx, WPP_GLOBAL_Control
0x180027de4  cmp     rcx, rdx
0x180027de7  jz      short loc_180027E03
0x180027de9  test    byte ptr [rcx+1Ch], 10h
0x180027ded  jz      short loc_180027E03
0x180027def  lea     edx, [r9-41h]
0x180027df3  mov     rcx, [rcx+10h]
0x180027df7  lea     r8, WPP_3886d72ed9b13ccdc9fcf8afdec51da0_Traceguids
0x180027dfe  call    WPP_SF_d
0x180027e03  mov     rdx, r12
0x180027e06  mov     ecx, r14d
0x180027e09  call    FreeIniMMAuthInfos
0x180027e0e  mov     rbp, [rsp+68h+arg_18]
0x180027e16  mov     rdi, [rsp+68h+arg_10]
0x180027e1e  mov     dword ptr [rdi], 0
0x180027e24  mov     qword ptr [rbp+0], 0
0x180027e2c  jmp     short loc_180027E44
0x180027e2e  mov     rax, [rsp+68h+arg_10]
0x180027e36  mov     [rax], r15d
0x180027e39  mov     rax, [rsp+68h+arg_18]
0x180027e41  mov     [rax], r12
0x180027e44  mov     eax, ebx
0x180027e46  mov     rbx, [rsp+68h+arg_0]
0x180027e4b  add     rsp, 30h
0x180027e4f  pop     r15
0x180027e51  pop     r14
0x180027e53  pop     r13
0x180027e55  pop     r12
0x180027e57  pop     rdi
0x180027e58  pop     rsi
0x180027e59  pop     rbp
0x180027e5a  retn
```
