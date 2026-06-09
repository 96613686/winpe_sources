# TlsParseParameterList

- ea: `0x1800081a8`
- end: `0x180008605`
- name: `TlsParseParameterList`
- size: `1117`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *, int *, _QWORD *, int *, _QWORD *, _DWORD *, _QWORD *, _DWORD *, _DWORD *)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180007990`
- `0x180007de4`
- `0x180012d98`
- `0x18001355c`
- `0x180020a70`

## callees

- `0x1800081a8`
- `0x18000b594`
- `0x18000b654`

## string_xrefs

- `0x18000843f`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x1800085c3`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`

## pseudocode

```c
__int64 __fastcall TlsParseParameterList(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        int *a4,
        _QWORD *a5,
        int *a6,
        _QWORD *a7,
        _DWORD *a8,
        _QWORD *a9,
        _DWORD *a10,
        _DWORD *a11)
{
  unsigned int v11; // r12d
  unsigned int v12; // eax
  __int64 v13; // r14
  __int64 v14; // rsi
  __int64 v15; // rbp
  __int64 v16; // r11
  int *v17; // rbx
  unsigned int v18; // ecx
  unsigned __int64 v19; // rax
  __int64 v20; // rcx
  unsigned int i; // ecx
  __int64 v23; // r9
  int v24; // [rsp+40h] [rbp-58h]
  int v25; // [rsp+44h] [rbp-54h]
  int v26; // [rsp+48h] [rbp-50h]
  int v27; // [rsp+4Ch] [rbp-4Ch]
  unsigned int v28; // [rsp+50h] [rbp-48h]
  __int64 v29; // [rsp+58h] [rbp-40h]
  int v30; // [rsp+A0h] [rbp+8h]
  unsigned int v31; // [rsp+A8h] [rbp+10h]
  _QWORD *v32; // [rsp+B0h] [rbp+18h]

  v32 = a3;
  v31 = a2;
  v11 = 0;
  if ( !a1 )
    goto LABEL_50;
  if ( *(_DWORD *)a1 )
    goto LABEL_50;
  v12 = *(_DWORD *)(a1 + 4);
  v28 = v12;
  if ( v12 > 0x40 )
    goto LABEL_50;
  v13 = *(_QWORD *)(a1 + 8);
  if ( !v13 )
    goto LABEL_50;
  if ( a3 )
  {
    if ( !a4 )
      goto LABEL_50;
  }
  else if ( a4 )
  {
    goto LABEL_50;
  }
  if ( a5 )
  {
    if ( !a6 )
      goto LABEL_50;
  }
  else if ( a6 )
  {
    goto LABEL_50;
  }
  if ( a7 )
  {
    if ( !a8 )
      goto LABEL_50;
  }
  else if ( a8 )
  {
    goto LABEL_50;
  }
  LODWORD(a3) = (_DWORD)a10;
  if ( a9 )
  {
    if ( a10 )
      goto LABEL_13;
LABEL_50:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        (_DWORD)a3,
        (unsigned int)"NTE_INVALID_PARAMETER",
        39,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
        50);
    return 2148073511LL;
  }
  if ( a10 )
    goto LABEL_50;
LABEL_13:
  v14 = 0;
  v24 = 0;
  v15 = 0;
  v25 = 0;
  v16 = 0;
  v26 = 0;
  v29 = 0;
  v27 = 0;
  v30 = 0;
  while ( 1 )
  {
    if ( v11 >= v12 )
    {
      if ( v14 )
      {
        if ( !v15 )
          goto LABEL_60;
      }
      else if ( v15 )
      {
        goto LABEL_60;
      }
      if ( !v16 || !v14 )
      {
        LODWORD(a2) = v30;
        if ( !a11 || v30 )
        {
          if ( v32 && a4 )
          {
            *v32 = v14;
            *a4 = v24;
          }
          if ( a5 && a6 )
          {
            *a5 = v15;
            *a6 = v25;
          }
          if ( a7 && a8 )
          {
            *a7 = v16;
            *a8 = v26;
          }
          if ( a9 && a10 )
          {
            *a9 = v29;
            *a10 = v27;
          }
          if ( a11 )
            *a11 = v30;
          return 0;
        }
      }
LABEL_60:
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          a2,
          (_DWORD)a10,
          (unsigned int)"NTE_INVALID_PARAMETER",
          39,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
          136);
      return 2148073511LL;
    }
    v17 = *(int **)(v13 + 16LL * v11 + 8);
    if ( !v17 || (v18 = *(_DWORD *)(v13 + 16LL * v11)) == 0 )
    {
      v23 = 828;
      goto LABEL_88;
    }
    LODWORD(a2) = *(_DWORD *)(v13 + 16LL * v11 + 4) - 20;
    if ( *(_DWORD *)(v13 + 16LL * v11 + 4) != 20 )
      break;
    if ( v16 || v18 != 32 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          0,
          (_DWORD)a10,
          (unsigned int)"NTE_INVALID_PARAMETER",
          39,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
          71);
      return 2148073511LL;
    }
    v24 = 32;
    v14 = *(_QWORD *)(v13 + 16LL * v11 + 8);
LABEL_28:
    v12 = v28;
    ++v11;
  }
  LODWORD(a2) = *(_DWORD *)(v13 + 16LL * v11 + 4) - 21;
  if ( *(_DWORD *)(v13 + 16LL * v11 + 4) == 21 )
  {
    if ( v16 || v18 != 32 )
    {
      v23 = 849;
      goto LABEL_88;
    }
    v25 = 32;
    v15 = *(_QWORD *)(v13 + 16LL * v11 + 8);
    goto LABEL_28;
  }
  LODWORD(a2) = *(_DWORD *)(v13 + 16LL * v11 + 4) - 22;
  if ( *(_DWORD *)(v13 + 16LL * v11 + 4) == 22 )
  {
    if ( v18 == 4 )
      v30 = *v17;
    goto LABEL_28;
  }
  LODWORD(a2) = *(_DWORD *)(v13 + 16LL * v11 + 4) - 23;
  if ( *(_DWORD *)(v13 + 16LL * v11 + 4) == 23 )
  {
    if ( v18 > 0x100 )
    {
      v23 = 886;
LABEL_88:
      DebugTraceError(
        2148073511LL,
        "NTE_INVALID_PARAMETER",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
        v23);
      return 2148073511LL;
    }
    v29 = *(_QWORD *)(v13 + 16LL * v11 + 8);
    v27 = *(_DWORD *)(v13 + 16LL * v11);
    goto LABEL_28;
  }
  if ( *(_DWORD *)(v13 + 16LL * v11 + 4) != 25 )
    goto LABEL_28;
  v26 = *(_DWORD *)(v13 + 16LL * v11);
  if ( !v14 && !v15 && v31 >= 0x301 )
  {
    v19 = v18 - 32;
    if ( (unsigned int)v19 <= 0x20 )
    {
      v20 = 0x100010011LL;
      if ( _bittest64(&v20, v19) )
      {
LABEL_27:
        v16 = *(_QWORD *)(v13 + 16LL * v11 + 8);
        goto LABEL_28;
      }
    }
  }
  for ( i = 7; i < g_dwHashInfoTotalCount; ++i )
  {
    a2 = g_pHashInfo[i];
    if ( a2 && *(_DWORD *)(a2 + 8) == *(_DWORD *)(v13 + 16LL * v11) )
      goto LABEL_27;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      a2,
      (_DWORD)a10,
      (unsigned int)"NTE_INVALID_PARAMETER",
      39,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
      107);
  return 2148073511LL;
}

```

## disassembly

```asm
0x1800081a8  mov     [rsp+arg_18], rbx
0x1800081ad  mov     [rsp+arg_10], r8
0x1800081b2  mov     [rsp+arg_8], edx
0x1800081b6  push    rbp
0x1800081b7  push    rsi
0x1800081b8  push    rdi
0x1800081b9  push    r12
0x1800081bb  push    r13
0x1800081bd  push    r14
0x1800081bf  push    r15
0x1800081c1  sub     rsp, 60h
0x1800081c5  xor     r12d, r12d
0x1800081c8  mov     rdi, r9
0x1800081cb  mov     rbx, r8
0x1800081ce  test    rcx, rcx
0x1800081d1  jz      loc_18000841A
0x1800081d7  cmp     [rcx], r12d
0x1800081da  jnz     loc_18000841A
0x1800081e0  mov     eax, [rcx+4]
0x1800081e3  mov     [rsp+98h+var_48], eax
0x1800081e7  cmp     eax, 40h ; '@'
0x1800081ea  ja      loc_18000841A
0x1800081f0  mov     r14, [rcx+8]
0x1800081f4  test    r14, r14
0x1800081f7  jz      loc_18000841A
0x1800081fd  test    rbx, rbx
0x180008200  jz      loc_180008544
0x180008206  test    r9, r9
0x180008209  jz      loc_18000841A
0x18000820f  mov     r9, [rsp+98h+arg_28]
0x180008217  cmp     [rsp+98h+arg_20], r12
0x18000821f  jz      loc_180008552
0x180008225  test    r9, r9
0x180008228  jz      loc_18000841A
0x18000822e  mov     r13, [rsp+98h+arg_30]
0x180008236  mov     r10, [rsp+98h+arg_38]
0x18000823e  test    r13, r13
0x180008241  jz      loc_180008560
0x180008247  test    r10, r10
0x18000824a  jz      loc_18000841A
0x180008250  mov     r15, [rsp+98h+arg_40]
0x180008258  mov     r8, [rsp+98h+arg_48]
0x180008260  test    r15, r15
0x180008263  jnz     loc_18000856E
0x180008269  test    r8, r8
0x18000826c  jnz     loc_18000841A
0x180008272  mov     rsi, r12
0x180008275  mov     [rsp+98h+var_58], r12d
0x18000827a  mov     rbp, r12
0x18000827d  mov     [rsp+98h+var_54], r12d
0x180008282  mov     r11, r12
0x180008285  mov     [rsp+98h+var_50], r12d
0x18000828a  mov     [rsp+98h+var_40], r12
0x18000828f  mov     [rsp+98h+var_4C], r12d
0x180008294  mov     [rsp+98h+arg_0], r12d
0x18000829c  cmp     r12d, eax
0x18000829f  jnb     loc_18000834C
0x1800082a5  mov     edx, r12d
0x1800082a8  add     rdx, rdx
0x1800082ab  mov     rbx, [r14+rdx*8+8]
0x1800082b0  test    rbx, rbx
0x1800082b3  jz      loc_1800085BD
0x1800082b9  mov     ecx, [r14+rdx*8]
0x1800082bd  test    ecx, ecx
0x1800082bf  jz      loc_1800085BD
0x1800082c5  mov     edx, [r14+rdx*8+4]
0x1800082ca  sub     edx, 14h
0x1800082cd  jz      loc_1800083FC
0x1800082d3  sub     edx, 1
0x1800082d6  jz      loc_180008469
0x1800082dc  sub     edx, 1
0x1800082df  jz      loc_180008487
0x1800082e5  sub     edx, 1
0x1800082e8  jz      loc_18000859F
0x1800082ee  cmp     edx, 2
0x1800082f1  jnz     short loc_180008340
0x1800082f3  mov     [rsp+98h+var_50], ecx
0x1800082f7  mov     r11d, ecx
0x1800082fa  test    rsi, rsi
0x1800082fd  jnz     loc_1800084D7
0x180008303  test    rbp, rbp
0x180008306  jnz     loc_1800084D7
0x18000830c  cmp     [rsp+98h+arg_8], 301h
0x180008317  jb      loc_1800084D7
0x18000831d  lea     eax, [rcx-20h]
0x180008320  cmp     eax, 20h ; ' '
0x180008323  ja      loc_1800084D7
0x180008329  mov     rcx, 100010011h
0x180008333  bt      rcx, rax
0x180008337  jnb     loc_1800084D7
0x18000833d  mov     r11, rbx
0x180008340  mov     eax, [rsp+98h+var_48]
0x180008344  inc     r12d
0x180008347  jmp     loc_18000829C
0x18000834c  test    rsi, rsi
0x18000834f  jnz     loc_18000849E
0x180008355  test    rbp, rbp
0x180008358  jnz     loc_1800084A7
0x18000835e  test    r11, r11
0x180008361  jz      short loc_18000836C
0x180008363  test    rsi, rsi
0x180008366  jnz     loc_1800084A7
0x18000836c  mov     rax, [rsp+98h+arg_50]
0x180008374  mov     edx, [rsp+98h+arg_0]
0x18000837b  test    rax, rax
0x18000837e  jnz     loc_1800084CD
0x180008384  mov     rbx, [rsp+98h+arg_10]
0x18000838c  test    rbx, rbx
0x18000838f  jz      short loc_18000839F
0x180008391  test    rdi, rdi
0x180008394  jz      short loc_18000839F
0x180008396  mov     ecx, [rsp+98h+var_58]
0x18000839a  mov     [rbx], rsi
0x18000839d  mov     [rdi], ecx
0x18000839f  mov     rcx, [rsp+98h+arg_20]
0x1800083a7  test    rcx, rcx
0x1800083aa  jz      short loc_1800083BB
0x1800083ac  test    r9, r9
0x1800083af  jz      short loc_1800083BB
0x1800083b1  mov     [rcx], rbp
0x1800083b4  mov     ecx, [rsp+98h+var_54]
0x1800083b8  mov     [r9], ecx
0x1800083bb  test    r13, r13
0x1800083be  jz      short loc_1800083D0
0x1800083c0  test    r10, r10
0x1800083c3  jz      short loc_1800083D0
0x1800083c5  mov     ecx, [rsp+98h+var_50]
0x1800083c9  mov     [r13+0], r11
0x1800083cd  mov     [r10], ecx
0x1800083d0  test    r15, r15
0x1800083d3  jnz     loc_1800085E8
0x1800083d9  test    rax, rax
0x1800083dc  jnz     short loc_1800083F8
0x1800083de  xor     eax, eax
0x1800083e0  mov     rbx, [rsp+98h+arg_18]
0x1800083e8  add     rsp, 60h
0x1800083ec  pop     r15
0x1800083ee  pop     r14
0x1800083f0  pop     r13
0x1800083f2  pop     r12
0x1800083f4  pop     rdi
0x1800083f5  pop     rsi
0x1800083f6  pop     rbp
0x1800083f7  retn
0x1800083f8  mov     [rax], edx
0x1800083fa  jmp     short loc_1800083DE
0x1800083fc  test    r11, r11
0x1800083ff  jnz     loc_180008516
0x180008405  cmp     ecx, 20h ; ' '
0x180008408  jnz     loc_180008516
0x18000840e  mov     [rsp+98h+var_58], ecx
0x180008412  mov     rsi, rbx
0x180008415  jmp     loc_180008340
0x18000841a  mov     rcx, cs:WPP_GLOBAL_Control
0x180008421  lea     rax, WPP_GLOBAL_Control
0x180008428  cmp     rcx, rax
0x18000842b  jz      short loc_18000845F
0x18000842d  test    byte ptr [rcx+1Ch], 1
0x180008431  jz      short loc_18000845F
0x180008433  mov     [rsp+98h+var_68], 332h
0x18000843b  mov     rcx, [rcx+10h]
0x18000843f  lea     rax, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180008446  mov     [rsp+98h+var_70], rax
0x18000844b  lea     r9, aNteInvalidPara; "NTE_INVALID_PARAMETER"
0x180008452  mov     [rsp+98h+var_78], 80090027h
0x18000845a  call    WPP_SF_sDsd
0x18000845f  mov     eax, 80090027h
0x180008464  jmp     loc_1800083E0
0x180008469  test    r11, r11
0x18000846c  jnz     loc_1800085E0
0x180008472  cmp     ecx, 20h ; ' '
0x180008475  jnz     loc_1800085E0
0x18000847b  mov     [rsp+98h+var_54], ecx
0x18000847f  mov     rbp, rbx
0x180008482  jmp     loc_180008340
0x180008487  cmp     ecx, 4
0x18000848a  jnz     loc_180008340
0x180008490  mov     eax, [rbx]
0x180008492  mov     [rsp+98h+arg_0], eax
0x180008499  jmp     loc_180008340
0x18000849e  test    rbp, rbp
0x1800084a1  jnz     loc_18000835E
0x1800084a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800084ae  lea     rax, WPP_GLOBAL_Control
0x1800084b5  cmp     rcx, rax
0x1800084b8  jz      short loc_18000845F
0x1800084ba  test    byte ptr [rcx+1Ch], 1
0x1800084be  jz      short loc_18000845F
0x1800084c0  mov     [rsp+98h+var_68], 388h
0x1800084c8  jmp     loc_18000843B
0x1800084cd  test    edx, edx
0x1800084cf  jnz     loc_180008384
0x1800084d5  jmp     short loc_1800084A7
0x1800084d7  mov     ecx, 7
0x1800084dc  cmp     ecx, cs:g_dwHashInfoTotalCount
0x1800084e2  jb      loc_18000857C
0x1800084e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800084ef  lea     rax, WPP_GLOBAL_Control
0x1800084f6  cmp     rcx, rax
0x1800084f9  jz      loc_18000845F
0x1800084ff  test    byte ptr [rcx+1Ch], 1
0x180008503  jz      loc_18000845F
0x180008509  mov     [rsp+98h+var_68], 36Bh
0x180008511  jmp     loc_18000843B
0x180008516  mov     rcx, cs:WPP_GLOBAL_Control
0x18000851d  lea     rax, WPP_GLOBAL_Control
0x180008524  cmp     rcx, rax
0x180008527  jz      loc_18000845F
0x18000852d  test    byte ptr [rcx+1Ch], 1
0x180008531  jz      loc_18000845F
0x180008537  mov     [rsp+98h+var_68], 347h
0x18000853f  jmp     loc_18000843B
0x180008544  test    rdi, rdi
0x180008547  jz      loc_18000820F
0x18000854d  jmp     loc_18000841A
0x180008552  test    r9, r9
0x180008555  jnz     loc_18000841A
0x18000855b  jmp     loc_18000822E
0x180008560  test    r10, r10
0x180008563  jnz     loc_18000841A
0x180008569  jmp     loc_180008250
0x18000856e  test    r8, r8
0x180008571  jz      loc_18000841A
0x180008577  jmp     loc_180008272
0x18000857c  mov     eax, ecx
0x18000857e  lea     rdx, g_pHashInfo
0x180008585  mov     rdx, [rdx+rax*8]
0x180008589  test    rdx, rdx
0x18000858c  jz      short loc_180008598
0x18000858e  cmp     [rdx+8], r11d
0x180008592  jz      loc_18000833D
0x180008598  inc     ecx
0x18000859a  jmp     loc_1800084DC
0x18000859f  cmp     ecx, 100h
0x1800085a5  ja      short loc_1800085B5
0x1800085a7  mov     [rsp+98h+var_40], rbx
0x1800085ac  mov     [rsp+98h+var_4C], ecx
0x1800085b0  jmp     loc_180008340
0x1800085b5  mov     r9d, 376h
0x1800085bb  jmp     short loc_1800085C3
0x1800085bd  mov     r9d, 33Ch
0x1800085c3  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800085ca  mov     ecx, 80090027h
0x1800085cf  lea     rdx, aNteInvalidPara; "NTE_INVALID_PARAMETER"
0x1800085d6  call    DebugTraceError
0x1800085db  jmp     loc_18000845F
0x1800085e0  mov     r9d, 351h
0x1800085e6  jmp     short loc_1800085C3
0x1800085e8  test    r8, r8
0x1800085eb  jz      loc_1800083D9
0x1800085f1  mov     rcx, [rsp+98h+var_40]
0x1800085f6  mov     [r15], rcx
0x1800085f9  mov     ecx, [rsp+98h+var_4C]
0x1800085fd  mov     [r8], ecx
0x180008600  jmp     loc_1800083D9
```
