# ASN1utctime2string

- ea: `0x180007ef4`
- end: `0x180008158`
- name: `ASN1utctime2string`
- size: `612`
- prototype: `__int64 __fastcall(STRSAFE_LPSTR pszDest)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180006b00`

## callees

- `0x180007ef4`
- `0x180008160`

## pseudocode

```c
__int64 __fastcall ASN1utctime2string(STRSAFE_LPSTR pszDest, __int64 a2, __int16 *a3, _DWORD *a4)
{
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
  int v19; // eax
  int v20; // edx
  HRESULT v21; // eax
  const char *pszFormat; // rax
  int v23; // ecx
  int v24; // eax
  __int64 v25; // [rsp+30h] [rbp-40h]
  int v26; // [rsp+40h] [rbp-30h]
  int v27; // [rsp+48h] [rbp-28h]
  int v28; // [rsp+50h] [rbp-20h]
  int v29; // [rsp+58h] [rbp-18h]
  STRSAFE_LPSTR ppszDestEnd[2]; // [rsp+60h] [rbp-10h] BYREF
  size_t pcbRemaining; // [rsp+90h] [rbp+20h] BYREF

  if ( !pszDest )
    return 0;
  if ( !a3 )
    return 0;
  v6 = *((unsigned __int8 *)a3 + 1);
  v7 = *(unsigned __int8 *)a3;
  v29 = *((unsigned __int8 *)a3 + 5);
  v28 = *((unsigned __int8 *)a3 + 4);
  ppszDestEnd[0] = pszDest;
  v27 = *((unsigned __int8 *)a3 + 3);
  v26 = *((unsigned __int8 *)a3 + 2);
  pcbRemaining = 32;
  if ( StringCbPrintfExA(
         pszDest,
         0x20u,
         ppszDestEnd,
         &pcbRemaining,
         0,
         "%02d%02d%02d%02d%02d%02d",
         v7,
         v6,
         v26,
         v27,
         v28,
         v29) < 0 )
    return 0;
  if ( !*((_BYTE *)a3 + 6) )
  {
    v19 = a3[4];
    if ( a3[4] <= 0 )
    {
      if ( a3[4] >= 0 )
        goto LABEL_18;
      v23 = a3[4];
      v24 = 60 * (v19 / 60);
      if ( v23 != v24 )
      {
        LODWORD(v25) = v24 - v23 - 100 * (v23 / 60);
        v21 = StringCbPrintfExA(ppszDestEnd[0], pcbRemaining, ppszDestEnd, &pcbRemaining, 0, "-%04d", v25);
        goto LABEL_33;
      }
      v20 = ((unsigned int)(((unsigned __int64)(2004318071LL * a3[4]) >> 32) - a3[4]) >> 31)
          + ((int)(((unsigned __int64)(2004318071LL * a3[4]) >> 32) - a3[4]) >> 5);
      pszFormat = "-%02d";
    }
    else
    {
      v20 = v19 / 60;
      if ( v19 % 60 )
      {
        LODWORD(v25) = v19 % 60 + 100 * v20;
        v21 = StringCbPrintfExA(ppszDestEnd[0], pcbRemaining, ppszDestEnd, &pcbRemaining, 0, "+%04d", v25);
LABEL_33:
        v15 = v21;
        goto LABEL_17;
      }
      pszFormat = "+%02d";
    }
    LODWORD(v25) = v20;
    v21 = StringCbPrintfExA(ppszDestEnd[0], pcbRemaining, ppszDestEnd, &pcbRemaining, 0, pszFormat, v25);
    goto LABEL_33;
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
LABEL_17:
  if ( v15 >= 0 )
  {
LABEL_18:
    result = 1;
    *a4 = 32 - pcbRemaining;
    return result;
  }
  return 0;
}

```

## disassembly

```asm
0x180007ef4  mov     [rsp-18h+arg_8], rbx
0x180007ef9  mov     [rsp-18h+arg_10], rsi
0x180007efe  push    rbp
0x180007eff  push    rdi
0x180007f00  push    r14
0x180007f02  mov     rbp, rsp
0x180007f05  sub     rsp, 70h
0x180007f09  xor     r14d, r14d
0x180007f0c  mov     rsi, r9
0x180007f0f  mov     rbx, r8
0x180007f12  mov     r11, rcx
0x180007f15  test    rcx, rcx
0x180007f18  jz      loc_18000805B
0x180007f1e  test    rbx, rbx
0x180007f21  jz      loc_18000805B
0x180007f27  movzx   eax, byte ptr [r8+5]
0x180007f2c  lea     edi, [r14+20h]
0x180007f30  movzx   edx, byte ptr [r8+4]
0x180007f35  movzx   r9d, byte ptr [rbx+1]
0x180007f3a  movzx   r10d, byte ptr [rbx]
0x180007f3e  mov     [rsp+70h+var_18], eax
0x180007f42  lea     rax, pszFormat; "%02d%02d%02d%02d%02d%02d"
0x180007f49  mov     [rsp+70h+var_20], edx
0x180007f4d  mov     edx, edi; cbDest
0x180007f4f  mov     [rbp+ppszDestEnd], rcx
0x180007f53  movzx   ecx, byte ptr [r8+3]
0x180007f58  movzx   r8d, byte ptr [r8+2]
0x180007f5d  mov     [rsp+70h+var_28], ecx
0x180007f61  mov     rcx, r11; pszDest
0x180007f64  mov     [rsp+70h+var_30], r8d
0x180007f69  lea     r8, [rbp+ppszDestEnd]; ppszDestEnd
0x180007f6d  mov     [rsp+70h+var_38], r9d
0x180007f72  lea     r9, [rbp+pcbRemaining]; pcbRemaining
0x180007f76  mov     dword ptr [rsp+70h+var_40], r10d
0x180007f7b  mov     [rsp+70h+pszFormat], rax; pszFormat
0x180007f80  mov     qword ptr [rsp+70h+dwFlags], r14; dwFlags
0x180007f85  mov     [rbp+pcbRemaining], rdi
0x180007f89  call    StringCbPrintfExA
0x180007f8e  test    eax, eax
0x180007f90  js      loc_18000805B
0x180007f96  cmp     [rbx+6], r14b
0x180007f9a  jz      loc_180008075
0x180007fa0  mov     rdx, [rbp+pcbRemaining]
0x180007fa4  mov     r8, [rbp+ppszDestEnd]
0x180007fa8  test    rdx, rdx
0x180007fab  jz      loc_180008066
0x180007fb1  cmp     rdx, 7FFFFFFFh
0x180007fb8  ja      loc_18000805F
0x180007fbe  mov     eax, 7FFFFFFEh
0x180007fc3  lea     rcx, aZ; "Z"
0x180007fca  mov     r10d, r14d
0x180007fcd  mov     r9, rdx
0x180007fd0  test    rax, rax
0x180007fd3  jz      short loc_180007FF2
0x180007fd5  mov     r11b, [rcx]
0x180007fd8  test    r11b, r11b
0x180007fdb  jz      short loc_180007FF2
0x180007fdd  mov     [r8], r11b
0x180007fe0  inc     rcx
0x180007fe3  inc     r8
0x180007fe6  dec     rax
0x180007fe9  inc     r10
0x180007fec  sub     r9, 1
0x180007ff0  jnz     short loc_180007FD0
0x180007ff2  mov     rax, r9
0x180007ff5  mov     r11d, 8007007Ah
0x180007ffb  neg     rax
0x180007ffe  lea     rax, [r8-1]
0x180008002  sbb     ecx, ecx
0x180008004  not     ecx
0x180008006  and     ecx, r11d
0x180008009  test    r9, r9
0x18000800c  cmovnz  rax, r8
0x180008010  mov     r8d, 80000000h
0x180008016  mov     [rax], r14b
0x180008019  lea     rax, [r10-1]
0x18000801d  cmovnz  rax, r10
0x180008021  sub     rdx, rax
0x180008024  lea     eax, [rcx+r8]
0x180008028  test    r8d, eax
0x18000802b  jz      short loc_180008054
0x18000802d  mov     [rbp+pcbRemaining], rdx
0x180008031  test    ecx, ecx
0x180008033  js      short loc_18000805B
0x180008035  sub     edi, dword ptr [rbp+pcbRemaining]
0x180008038  mov     eax, 1
0x18000803d  mov     [rsi], edi
0x18000803f  lea     r11, [rsp+70h+var_s0]
0x180008044  mov     rbx, [r11+28h]
0x180008048  mov     rsi, [r11+30h]
0x18000804c  mov     rsp, r11
0x18000804f  pop     r14
0x180008051  pop     rdi
0x180008052  pop     rbp
0x180008053  retn
0x180008054  cmp     ecx, r11d
0x180008057  jz      short loc_18000802D
0x180008059  jmp     short loc_180008031
0x18000805b  xor     eax, eax
0x18000805d  jmp     short loc_18000803F
0x18000805f  mov     ecx, 80070057h
0x180008064  jmp     short loc_180008070
0x180008066  mov     ecx, 80070057h
0x18000806b  test    rdx, rdx
0x18000806e  jz      short loc_180008031
0x180008070  mov     [r8], r14b
0x180008073  jmp     short loc_180008031
0x180008075  movsx   eax, word ptr [rbx+8]
0x180008079  test    ax, ax
0x18000807c  jle     short loc_1800080C0
0x18000807e  mov     ecx, eax
0x180008080  lea     r9, [rbp+pcbRemaining]
0x180008084  mov     eax, 88888889h
0x180008089  lea     r8, [rbp+ppszDestEnd]
0x18000808d  imul    ecx
0x18000808f  add     edx, ecx
0x180008091  sar     edx, 5
0x180008094  mov     eax, edx
0x180008096  shr     eax, 1Fh
0x180008099  add     edx, eax
0x18000809b  imul    eax, edx, 3Ch ; '<'
0x18000809e  sub     ecx, eax
0x1800080a0  jz      short loc_1800080B7
0x1800080a2  imul    eax, edx, 64h ; 'd'
0x1800080a5  add     eax, ecx
0x1800080a7  mov     dword ptr [rsp+70h+var_40], eax
0x1800080ab  lea     rax, a04d; "+%04d"
0x1800080b2  jmp     loc_18000813A
0x1800080b7  lea     rax, a02d_0; "+%02d"
0x1800080be  jmp     short loc_180008136
0x1800080c0  jns     loc_180008035
0x1800080c6  mov     ecx, eax
0x1800080c8  lea     r9, [rbp+pcbRemaining]; pcbRemaining
0x1800080cc  mov     eax, 88888889h
0x1800080d1  mov     r8d, ecx
0x1800080d4  imul    ecx
0x1800080d6  add     edx, ecx
0x1800080d8  sar     edx, 5
0x1800080db  mov     eax, edx
0x1800080dd  shr     eax, 1Fh
0x1800080e0  add     edx, eax
0x1800080e2  imul    eax, edx, 3Ch ; '<'
0x1800080e5  sub     r8d, eax
0x1800080e8  jz      short loc_180008118
0x1800080ea  mov     eax, 88888889h
0x1800080ef  neg     r8d
0x1800080f2  imul    ecx
0x1800080f4  add     edx, ecx
0x1800080f6  sar     edx, 5
0x1800080f9  mov     eax, edx
0x1800080fb  shr     eax, 1Fh
0x1800080fe  add     edx, eax
0x180008100  imul    eax, edx, 64h ; 'd'
0x180008103  sub     r8d, eax
0x180008106  lea     rax, a04d_0; "-%04d"
0x18000810d  mov     dword ptr [rsp+70h+var_40], r8d
0x180008112  lea     r8, [rbp+ppszDestEnd]
0x180008116  jmp     short loc_18000813A
0x180008118  mov     eax, 77777777h
0x18000811d  lea     r8, [rbp+ppszDestEnd]; ppszDestEnd
0x180008121  imul    ecx
0x180008123  sub     edx, ecx
0x180008125  sar     edx, 5
0x180008128  mov     eax, edx
0x18000812a  shr     eax, 1Fh
0x18000812d  add     edx, eax
0x18000812f  lea     rax, a02d_1; "-%02d"
0x180008136  mov     dword ptr [rsp+70h+var_40], edx
0x18000813a  mov     rdx, [rbp+pcbRemaining]; cbDest
0x18000813e  mov     rcx, [rbp+ppszDestEnd]; pszDest
0x180008142  mov     [rsp+70h+pszFormat], rax; pszFormat
0x180008147  mov     qword ptr [rsp+70h+dwFlags], r14; dwFlags
0x18000814c  call    StringCbPrintfExA
0x180008151  mov     ecx, eax
0x180008153  jmp     loc_180008031
```
