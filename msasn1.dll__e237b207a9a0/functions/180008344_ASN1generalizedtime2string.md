# ASN1generalizedtime2string

- ea: `0x180008344`
- end: `0x180008633`
- name: `ASN1generalizedtime2string`
- size: `751`
- prototype: `__int64 __fastcall(STRSAFE_LPSTR pszDest)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800067c0`

## callees

- `0x180008160`
- `0x180008344`

## pseudocode

```c
__int64 __fastcall ASN1generalizedtime2string(STRSAFE_LPSTR pszDest, unsigned __int16 *a2, _DWORD *a3)
{
  int v5; // r8d
  int v6; // r9d
  int v7; // r10d
  size_t v8; // rdx
  STRSAFE_LPSTR v9; // r8
  __int64 v10; // rax
  const char *v11; // rcx
  __int64 v12; // r10
  size_t v13; // r9
  STRSAFE_LPSTR v14; // rax
  signed int v15; // ecx
  __int64 v16; // rax
  size_t v17; // rdx
  __int64 result; // rax
  unsigned int v19; // r8d
  HRESULT v20; // eax
  int v21; // eax
  int v22; // edx
  HRESULT v23; // eax
  const char *pszFormat; // rax
  int v25; // ecx
  int v26; // eax
  __int64 v27; // [rsp+30h] [rbp-40h]
  int v28; // [rsp+48h] [rbp-28h]
  int v29; // [rsp+50h] [rbp-20h]
  int v30; // [rsp+58h] [rbp-18h]
  STRSAFE_LPSTR ppszDestEnd[2]; // [rsp+60h] [rbp-10h] BYREF
  size_t pcbRemaining; // [rsp+A8h] [rbp+38h] BYREF

  if ( !pszDest )
    return 0;
  if ( !a2 )
    return 0;
  v5 = *((unsigned __int8 *)a2 + 3);
  v6 = *((unsigned __int8 *)a2 + 2);
  v7 = *a2;
  v30 = *((unsigned __int8 *)a2 + 6);
  v29 = *((unsigned __int8 *)a2 + 5);
  ppszDestEnd[0] = pszDest;
  v28 = *((unsigned __int8 *)a2 + 4);
  pcbRemaining = 32;
  if ( StringCbPrintfExA(
         pszDest,
         0x20u,
         ppszDestEnd,
         &pcbRemaining,
         0,
         "%04d%02d%02d%02d%02d%02d",
         v7,
         v6,
         v5,
         v28,
         v29,
         v30) < 0 )
    return 0;
  if ( a2[4] )
  {
    v19 = a2[4];
    if ( v19 == 100 * (v19 / 0x64) )
    {
      LODWORD(v27) = a2[4] / 0x64u;
      v20 = StringCbPrintfExA(ppszDestEnd[0], pcbRemaining, ppszDestEnd, &pcbRemaining, 0, ".%01d", v27);
    }
    else if ( v19 == 10 * (v19 / 0xA) )
    {
      LODWORD(v27) = v19 / 0xA;
      v20 = StringCbPrintfExA(ppszDestEnd[0], pcbRemaining, ppszDestEnd, &pcbRemaining, 0, ".%02d", v27);
    }
    else
    {
      LODWORD(v27) = a2[4];
      v20 = StringCbPrintfExA(ppszDestEnd[0], pcbRemaining, ppszDestEnd, &pcbRemaining, 0, ".%03d", v27);
    }
    if ( v20 < 0 )
      return 0;
  }
  if ( !*((_BYTE *)a2 + 10) )
  {
    v21 = (__int16)a2[6];
    if ( (__int16)a2[6] <= 0 )
    {
      if ( (a2[6] & 0x8000u) == 0 )
        goto LABEL_19;
      v25 = (__int16)a2[6];
      v26 = 60 * (v21 / 60);
      if ( v25 != v26 )
      {
        LODWORD(v27) = v26 - v25 - 100 * (v25 / 60);
        v23 = StringCbPrintfExA(ppszDestEnd[0], pcbRemaining, ppszDestEnd, &pcbRemaining, 0, "-%04d", v27);
        goto LABEL_40;
      }
      v22 = ((unsigned int)(((unsigned __int64)(2004318071LL * (__int16)a2[6]) >> 32) - (__int16)a2[6]) >> 31)
          + ((int)(((unsigned __int64)(2004318071LL * (__int16)a2[6]) >> 32) - (__int16)a2[6]) >> 5);
      pszFormat = "-%02d";
    }
    else
    {
      v22 = v21 / 60;
      if ( v21 % 60 )
      {
        LODWORD(v27) = v21 % 60 + 100 * v22;
        v23 = StringCbPrintfExA(ppszDestEnd[0], pcbRemaining, ppszDestEnd, &pcbRemaining, 0, "+%04d", v27);
LABEL_40:
        v15 = v23;
        goto LABEL_18;
      }
      pszFormat = "+%02d";
    }
    LODWORD(v27) = v22;
    v23 = StringCbPrintfExA(ppszDestEnd[0], pcbRemaining, ppszDestEnd, &pcbRemaining, 0, pszFormat, v27);
    goto LABEL_40;
  }
  v8 = pcbRemaining;
  v9 = ppszDestEnd[0];
  if ( pcbRemaining )
  {
    if ( pcbRemaining > 0x7FFFFFFF )
    {
      v15 = -2147024809;
      *ppszDestEnd[0] = 0;
    }
    else
    {
      v10 = 2147483646;
      v11 = "Z";
      v12 = 0;
      v13 = pcbRemaining;
      do
      {
        if ( !v10 )
          break;
        if ( !*v11 )
          break;
        *v9++ = *v11++;
        --v10;
        ++v12;
        --v13;
      }
      while ( v13 );
      v14 = v9 - 1;
      v15 = v13 == 0 ? 0x8007007A : 0;
      if ( v13 )
        v14 = v9;
      *v14 = 0;
      v16 = v12 - 1;
      if ( v13 )
        v16 = v12;
      v17 = v8 - v16;
      if ( ((v15 + 0x80000000) & 0x80000000) != 0 || v15 == -2147024774 )
        pcbRemaining = v17;
    }
  }
  else
  {
    v15 = -2147024809;
  }
LABEL_18:
  if ( v15 >= 0 )
  {
LABEL_19:
    result = 1;
    *a3 = 32 - pcbRemaining;
    return result;
  }
  return 0;
}

```

## disassembly

```asm
0x180008344  mov     [rsp-18h+arg_8], rbx
0x180008349  mov     [rsp-18h+arg_10], rsi
0x18000834e  push    rbp
0x18000834f  push    rdi
0x180008350  push    r14
0x180008352  mov     rbp, rsp
0x180008355  sub     rsp, 70h
0x180008359  xor     r14d, r14d
0x18000835c  mov     rsi, r8
0x18000835f  mov     rbx, rdx
0x180008362  mov     r11, rcx
0x180008365  test    rcx, rcx
0x180008368  jz      loc_1800084DA
0x18000836e  test    rdx, rdx
0x180008371  jz      loc_1800084DA
0x180008377  movzx   eax, byte ptr [rdx+6]
0x18000837b  lea     edi, [r14+20h]
0x18000837f  movzx   edx, byte ptr [rdx+5]
0x180008383  movzx   r8d, byte ptr [rbx+3]
0x180008388  movzx   r9d, byte ptr [rbx+2]
0x18000838d  movzx   r10d, word ptr [rbx]
0x180008391  mov     [rsp+70h+var_18], eax
0x180008395  lea     rax, a04d02d02d02d02; "%04d%02d%02d%02d%02d%02d"
0x18000839c  mov     [rsp+70h+var_20], edx
0x1800083a0  mov     edx, edi; cbDest
0x1800083a2  mov     [rbp+ppszDestEnd], rcx
0x1800083a6  movzx   ecx, byte ptr [rbx+4]
0x1800083aa  mov     [rsp+70h+var_28], ecx
0x1800083ae  mov     rcx, r11; pszDest
0x1800083b1  mov     [rsp+70h+var_30], r8d
0x1800083b6  lea     r8, [rbp+ppszDestEnd]; ppszDestEnd
0x1800083ba  mov     [rsp+70h+var_38], r9d
0x1800083bf  lea     r9, [rbp+pcbRemaining]; pcbRemaining
0x1800083c3  mov     dword ptr [rsp+70h+var_40], r10d
0x1800083c8  mov     [rsp+70h+pszFormat], rax; pszFormat
0x1800083cd  mov     qword ptr [rsp+70h+dwFlags], r14; dwFlags
0x1800083d2  mov     [rbp+pcbRemaining], rdi
0x1800083d6  call    StringCbPrintfExA
0x1800083db  test    eax, eax
0x1800083dd  js      loc_1800084DA
0x1800083e3  cmp     [rbx+8], r14w
0x1800083e8  jnz     loc_1800084DE
0x1800083ee  cmp     [rbx+0Ah], r14b
0x1800083f2  jz      loc_180008550
0x1800083f8  mov     rdx, [rbp+pcbRemaining]
0x1800083fc  mov     r8, [rbp+ppszDestEnd]
0x180008400  test    rdx, rdx
0x180008403  jz      loc_18000853A
0x180008409  cmp     rdx, 7FFFFFFFh
0x180008410  ja      loc_180008533
0x180008416  mov     eax, 7FFFFFFEh
0x18000841b  lea     rcx, aZ; "Z"
0x180008422  mov     r10, r14
0x180008425  mov     r9, rdx
0x180008428  test    rax, rax
0x18000842b  jz      short loc_18000844A
0x18000842d  mov     r11b, [rcx]
0x180008430  test    r11b, r11b
0x180008433  jz      short loc_18000844A
0x180008435  mov     [r8], r11b
0x180008438  inc     rcx
0x18000843b  inc     r8
0x18000843e  dec     rax
0x180008441  inc     r10
0x180008444  sub     r9, 1
0x180008448  jnz     short loc_180008428
0x18000844a  mov     rax, r9
0x18000844d  mov     r11d, 8007007Ah
0x180008453  neg     rax
0x180008456  lea     rax, [r8-1]
0x18000845a  sbb     ecx, ecx
0x18000845c  not     ecx
0x18000845e  and     ecx, r11d
0x180008461  test    r9, r9
0x180008464  cmovnz  rax, r8
0x180008468  mov     r8d, 80000000h
0x18000846e  mov     [rax], r14b
0x180008471  lea     rax, [r10-1]
0x180008475  cmovnz  rax, r10
0x180008479  sub     rdx, rax
0x18000847c  lea     eax, [rcx+r8]
0x180008480  test    r8d, eax
0x180008483  jz      short loc_1800084AC
0x180008485  mov     [rbp+pcbRemaining], rdx
0x180008489  test    ecx, ecx
0x18000848b  js      short loc_1800084DA
0x18000848d  sub     edi, dword ptr [rbp+pcbRemaining]
0x180008490  mov     eax, 1
0x180008495  mov     [rsi], edi
0x180008497  lea     r11, [rsp+70h+var_s0]
0x18000849c  mov     rbx, [r11+28h]
0x1800084a0  mov     rsi, [r11+30h]
0x1800084a4  mov     rsp, r11
0x1800084a7  pop     r14
0x1800084a9  pop     rdi
0x1800084aa  pop     rbp
0x1800084ab  retn
0x1800084ac  cmp     ecx, r11d
0x1800084af  jz      short loc_180008485
0x1800084b1  jmp     short loc_180008489
0x1800084b3  mov     rdx, [rbp+pcbRemaining]; cbDest
0x1800084b7  lea     r9, [rbp+pcbRemaining]; pcbRemaining
0x1800084bb  mov     rcx, [rbp+ppszDestEnd]; pszDest
0x1800084bf  lea     r8, [rbp+ppszDestEnd]; ppszDestEnd
0x1800084c3  mov     [rsp+70h+pszFormat], rax; pszFormat
0x1800084c8  mov     qword ptr [rsp+70h+dwFlags], r14; dwFlags
0x1800084cd  call    StringCbPrintfExA
0x1800084d2  test    eax, eax
0x1800084d4  jns     loc_1800083EE
0x1800084da  xor     eax, eax
0x1800084dc  jmp     short loc_180008497
0x1800084de  movzx   r8d, word ptr [rbx+8]
0x1800084e3  mov     eax, 51EB851Fh
0x1800084e8  mul     r8d
0x1800084eb  shr     edx, 5
0x1800084ee  imul    eax, edx, 64h ; 'd'
0x1800084f1  cmp     r8d, eax
0x1800084f4  jnz     short loc_180008503
0x1800084f6  mov     dword ptr [rsp+70h+var_40], edx
0x1800084fa  lea     rax, a01d; ".%01d"
0x180008501  jmp     short loc_1800084B3
0x180008503  mov     eax, 0CCCCCCCDh
0x180008508  mul     r8d
0x18000850b  shr     edx, 3
0x18000850e  lea     ecx, [rdx+rdx*4]
0x180008511  add     ecx, ecx
0x180008513  cmp     r8d, ecx
0x180008516  jnz     short loc_180008525
0x180008518  mov     dword ptr [rsp+70h+var_40], edx
0x18000851c  lea     rax, a02d; ".%02d"
0x180008523  jmp     short loc_1800084B3
0x180008525  mov     dword ptr [rsp+70h+var_40], r8d
0x18000852a  lea     rax, a03d; ".%03d"
0x180008531  jmp     short loc_1800084B3
0x180008533  mov     ecx, 80070057h
0x180008538  jmp     short loc_180008548
0x18000853a  mov     ecx, 80070057h
0x18000853f  test    rdx, rdx
0x180008542  jz      loc_180008489
0x180008548  mov     [r8], r14b
0x18000854b  jmp     loc_180008489
0x180008550  movsx   eax, word ptr [rbx+0Ch]
0x180008554  test    ax, ax
0x180008557  jle     short loc_18000859B
0x180008559  mov     ecx, eax
0x18000855b  lea     r9, [rbp+pcbRemaining]
0x18000855f  mov     eax, 88888889h
0x180008564  lea     r8, [rbp+ppszDestEnd]
0x180008568  imul    ecx
0x18000856a  add     edx, ecx
0x18000856c  sar     edx, 5
0x18000856f  mov     eax, edx
0x180008571  shr     eax, 1Fh
0x180008574  add     edx, eax
0x180008576  imul    eax, edx, 3Ch ; '<'
0x180008579  sub     ecx, eax
0x18000857b  jz      short loc_180008592
0x18000857d  imul    eax, edx, 64h ; 'd'
0x180008580  add     eax, ecx
0x180008582  mov     dword ptr [rsp+70h+var_40], eax
0x180008586  lea     rax, a04d; "+%04d"
0x18000858d  jmp     loc_180008615
0x180008592  lea     rax, a02d_0; "+%02d"
0x180008599  jmp     short loc_180008611
0x18000859b  jns     loc_18000848D
0x1800085a1  mov     ecx, eax
0x1800085a3  lea     r9, [rbp+pcbRemaining]; pcbRemaining
0x1800085a7  mov     eax, 88888889h
0x1800085ac  mov     r8d, ecx
0x1800085af  imul    ecx
0x1800085b1  add     edx, ecx
0x1800085b3  sar     edx, 5
0x1800085b6  mov     eax, edx
0x1800085b8  shr     eax, 1Fh
0x1800085bb  add     edx, eax
0x1800085bd  imul    eax, edx, 3Ch ; '<'
0x1800085c0  sub     r8d, eax
0x1800085c3  jz      short loc_1800085F3
0x1800085c5  mov     eax, 88888889h
0x1800085ca  neg     r8d
0x1800085cd  imul    ecx
0x1800085cf  add     edx, ecx
0x1800085d1  sar     edx, 5
0x1800085d4  mov     eax, edx
0x1800085d6  shr     eax, 1Fh
0x1800085d9  add     edx, eax
0x1800085db  imul    eax, edx, 64h ; 'd'
0x1800085de  sub     r8d, eax
0x1800085e1  lea     rax, a04d_0; "-%04d"
0x1800085e8  mov     dword ptr [rsp+70h+var_40], r8d
0x1800085ed  lea     r8, [rbp+ppszDestEnd]
0x1800085f1  jmp     short loc_180008615
0x1800085f3  mov     eax, 77777777h
0x1800085f8  lea     r8, [rbp+ppszDestEnd]; ppszDestEnd
0x1800085fc  imul    ecx
0x1800085fe  sub     edx, ecx
0x180008600  sar     edx, 5
0x180008603  mov     eax, edx
0x180008605  shr     eax, 1Fh
0x180008608  add     edx, eax
0x18000860a  lea     rax, a02d_1; "-%02d"
0x180008611  mov     dword ptr [rsp+70h+var_40], edx
0x180008615  mov     rdx, [rbp+pcbRemaining]; cbDest
0x180008619  mov     rcx, [rbp+ppszDestEnd]; pszDest
0x18000861d  mov     [rsp+70h+pszFormat], rax; pszFormat
0x180008622  mov     qword ptr [rsp+70h+dwFlags], r14; dwFlags
0x180008627  call    StringCbPrintfExA
0x18000862c  mov     ecx, eax
0x18000862e  jmp     loc_180008489
```
