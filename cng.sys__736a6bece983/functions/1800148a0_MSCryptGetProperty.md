# MSCryptGetProperty

- ea: `0x1800148a0`
- end: `0x180014b85`
- name: `MSCryptGetProperty`
- size: `741`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180014070`
- `0x180014450`
- `0x180080644`

## callees

- `0x18000743c`
- `0x1800148a0`
- `0x18003ad60`
- `0x18003d538`
- `0x180041f74`
- `0x1800806f0`
- `0x18009f616`
- `0x18009f628`
- `0x18009f780`

## string_xrefs

- `0x180014b5e`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x180014a7b`: `[ BCRYPT_FIPS_SERVICE_INDICATOR]`

## pseudocode

```c
__int64 __fastcall MSCryptGetProperty(__int64 a1, wchar_t *a2, _OWORD *a3, unsigned int a4, unsigned int *a5, int a6)
{
  __int64 v10; // r9
  unsigned int v11; // ebx
  __int64 v12; // rcx
  _DWORD *v13; // rbx
  unsigned int v14; // ecx
  __int64 v15; // rdx
  __int64 v16; // rax
  unsigned int v17; // eax
  int v18; // eax
  __int64 v19; // rax
  wchar_t *v20; // rcx
  int AlgProperty; // eax
  int v22; // eax

  if ( (a6 & 0xFFFFFF7F) != 0 )
  {
    v10 = 2217;
LABEL_3:
    v11 = -1073741811;
    v12 = 3221225485LL;
LABEL_54:
    DebugTraceError(v12, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c", v10);
    return v11;
  }
  v13 = (_DWORD *)validateMSCryptSymmObject();
  if ( !v13 )
  {
    v10 = 2226;
LABEL_53:
    v12 = 3221225480LL;
    v11 = -1073741816;
    goto LABEL_54;
  }
  if ( !a5 )
  {
    v10 = 2233;
    goto LABEL_3;
  }
  if ( !wcscmp_0(a2, L"AlgorithmName") )
  {
    v14 = (unsigned __int16)v13[2] - 1;
    if ( v14 >= 9 )
    {
      v10 = 2244;
      goto LABEL_53;
    }
    v15 = 14LL * v14;
    v16 = -1;
    do
      ++v16;
    while ( (&off_1800A7088)[v15][v16] );
    v17 = 2 * v16 + 2;
    *a5 = v17;
    if ( !a3 )
      return 0;
    if ( a4 < v17 )
    {
      v10 = 2259;
LABEL_17:
      v11 = -1073741789;
      v12 = 3221225507LL;
      goto LABEL_54;
    }
    memmove(a3, (&off_1800A7088)[v15], v17);
    return 0;
  }
  if ( !wcscmp_0(a2, L"BlockLength") )
  {
    *a5 = 4;
    if ( !a3 )
      return 0;
    if ( a4 < 4 )
    {
      v10 = 2280;
      goto LABEL_17;
    }
    v18 = v13[4];
LABEL_24:
    *(_DWORD *)a3 = v18;
    return 0;
  }
  if ( !wcscmp_0(a2, L"MessageBlockLength") )
  {
    *a5 = 4;
    if ( !a3 )
      return 0;
    if ( a4 < 4 )
    {
      v10 = 2302;
      goto LABEL_17;
    }
    v18 = v13[5];
    goto LABEL_24;
  }
  if ( !wcscmp_0(a2, L"ChainingMode") )
  {
    *a5 = 32;
    if ( a3 )
    {
      if ( a4 < 0x20 )
      {
        v10 = 2326;
        goto LABEL_17;
      }
      v19 = (unsigned int)v13[3];
      if ( (unsigned int)v19 >= 6 )
      {
        v10 = 2333;
        goto LABEL_53;
      }
      v20 = rgpszChainModeNameArray[v19];
      *a3 = *(_OWORD *)v20;
      a3[1] = *((_OWORD *)v20 + 1);
    }
    return 0;
  }
  if ( !wcsncmp_0(a2, L"[ BCRYPT_FIPS_SERVICE_INDICATOR]", 0x20u) )
  {
    if ( !a3 )
    {
      *a5 = 4;
      return 0;
    }
    if ( a4 < 4 )
    {
      *a5 = 0;
      v10 = 2360;
      goto LABEL_17;
    }
    AlgProperty = ApprovedServicesIndicator(a2);
    v11 = AlgProperty;
    if ( AlgProperty >= 0 )
    {
      *(_DWORD *)a3 = 0;
      *a5 = 4;
      return v11;
    }
    v10 = 2368;
LABEL_44:
    v12 = (unsigned int)AlgProperty;
    goto LABEL_54;
  }
  v22 = v13[1];
  if ( v22 == 1297306433 )
  {
    AlgProperty = MSCryptGetAlgProperty(a1, a2, a3, a4, a5, a6);
    v11 = AlgProperty;
    if ( AlgProperty >= 0 )
      return v11;
    v10 = 2389;
    goto LABEL_44;
  }
  if ( v22 != 1297306443 )
  {
    v10 = 2410;
    goto LABEL_53;
  }
  AlgProperty = MSCryptGetKeyProperty(a1, a2, a3, a4, a5);
  v11 = AlgProperty;
  if ( AlgProperty < 0 )
  {
    v10 = 2403;
    goto LABEL_44;
  }
  return v11;
}

```

## disassembly

```asm
0x1800148a0  push    rbx
0x1800148a2  push    rbp
0x1800148a3  push    rsi
0x1800148a4  push    rdi
0x1800148a5  push    r12
0x1800148a7  push    r13
0x1800148a9  push    r14
0x1800148ab  push    r15
0x1800148ad  sub     rsp, 38h
0x1800148b1  mov     r12d, [rsp+78h+arg_28]
0x1800148b9  mov     ebp, r9d
0x1800148bc  mov     rdi, r8
0x1800148bf  mov     r14, rdx
0x1800148c2  mov     r15, rcx
0x1800148c5  test    r12d, 0FFFFFF7Fh
0x1800148cc  jz      short loc_1800148E3
0x1800148ce  mov     r9d, 8A9h
0x1800148d4  mov     ebx, 0C000000Dh
0x1800148d9  mov     ecx, 0C000000Dh
0x1800148de  jmp     loc_180014B5E
0x1800148e3  call    validateMSCryptSymmObject
0x1800148e8  xor     r13d, r13d
0x1800148eb  mov     rbx, rax
0x1800148ee  test    rax, rax
0x1800148f1  jnz     short loc_1800148FE
0x1800148f3  mov     r9d, 8B2h
0x1800148f9  jmp     loc_180014B54
0x1800148fe  mov     rsi, [rsp+78h+arg_20]
0x180014906  test    rsi, rsi
0x180014909  jnz     short loc_180014913
0x18001490b  mov     r9d, 8B9h
0x180014911  jmp     short loc_1800148D4
0x180014913  lea     rdx, aAlgorithmname; "AlgorithmName"
0x18001491a  mov     rcx, r14; Str1
0x18001491d  call    wcscmp_0
0x180014922  test    eax, eax
0x180014924  jnz     short loc_1800149A5
0x180014926  mov     eax, [rbx+8]
0x180014929  movzx   ecx, ax
0x18001492c  dec     ecx
0x18001492e  cmp     ecx, 9
0x180014931  jb      short loc_18001493E
0x180014933  mov     r9d, 8C4h
0x180014939  jmp     loc_180014B54
0x18001493e  mov     eax, ecx
0x180014940  lea     rcx, cs:180000000h
0x180014947  imul    rdx, rax, 70h ; 'p'
0x18001494b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001494f  mov     r8, [rdx+rcx+0A7088h]
0x180014957  inc     rax
0x18001495a  cmp     [r8+rax*2], r13w
0x18001495f  jnz     short loc_180014957
0x180014961  lea     eax, ds:2[rax*2]
0x180014968  mov     [rsi], eax
0x18001496a  test    rdi, rdi
0x18001496d  jnz     short loc_180014977
0x18001496f  mov     ebx, r13d
0x180014972  jmp     loc_180014B71
0x180014977  cmp     ebp, eax
0x180014979  jnb     short loc_180014990
0x18001497b  mov     r9d, 8D3h
0x180014981  mov     ebx, 0C0000023h
0x180014986  mov     ecx, 0C0000023h
0x18001498b  jmp     loc_180014B5E
0x180014990  mov     rdx, [rdx+rcx+0A7088h]; Src
0x180014998  mov     rcx, rdi; void *
0x18001499b  mov     r8d, eax; Size
0x18001499e  call    memmove
0x1800149a3  jmp     short loc_18001496F
0x1800149a5  lea     rdx, aBlocklength; "BlockLength"
0x1800149ac  mov     rcx, r14; Str1
0x1800149af  call    wcscmp_0
0x1800149b4  test    eax, eax
0x1800149b6  jnz     short loc_1800149D7
0x1800149b8  mov     dword ptr [rsi], 4
0x1800149be  test    rdi, rdi
0x1800149c1  jz      short loc_18001496F
0x1800149c3  cmp     ebp, 4
0x1800149c6  jnb     short loc_1800149D0
0x1800149c8  mov     r9d, 8E8h
0x1800149ce  jmp     short loc_180014981
0x1800149d0  mov     eax, [rbx+10h]
0x1800149d3  mov     [rdi], eax
0x1800149d5  jmp     short loc_18001496F
0x1800149d7  lea     rdx, aMessageblockle; "MessageBlockLength"
0x1800149de  mov     rcx, r14; Str1
0x1800149e1  call    wcscmp_0
0x1800149e6  test    eax, eax
0x1800149e8  jnz     short loc_180014A0E
0x1800149ea  mov     dword ptr [rsi], 4
0x1800149f0  test    rdi, rdi
0x1800149f3  jz      loc_18001496F
0x1800149f9  cmp     ebp, 4
0x1800149fc  jnb     short loc_180014A09
0x1800149fe  mov     r9d, 8FEh
0x180014a04  jmp     loc_180014981
0x180014a09  mov     eax, [rbx+14h]
0x180014a0c  jmp     short loc_1800149D3
0x180014a0e  lea     rdx, aChainingmode; "ChainingMode"
0x180014a15  mov     rcx, r14; Str1
0x180014a18  call    wcscmp_0
0x180014a1d  test    eax, eax
0x180014a1f  jnz     short loc_180014A75
0x180014a21  mov     dword ptr [rsi], 20h ; ' '
0x180014a27  test    rdi, rdi
0x180014a2a  jz      loc_18001496F
0x180014a30  cmp     ebp, 20h ; ' '
0x180014a33  jnb     short loc_180014A40
0x180014a35  mov     r9d, 916h
0x180014a3b  jmp     loc_180014981
0x180014a40  mov     eax, [rbx+0Ch]
0x180014a43  cmp     eax, 6
0x180014a46  jb      short loc_180014A53
0x180014a48  mov     r9d, 91Dh
0x180014a4e  jmp     loc_180014B54
0x180014a53  lea     rcx, cs:180000000h
0x180014a5a  mov     rcx, ds:rva rgpszChainModeNameArray[rcx+rax*8]
0x180014a62  movups  xmm0, xmmword ptr [rcx]
0x180014a65  movups  xmmword ptr [rdi], xmm0
0x180014a68  movups  xmm1, xmmword ptr [rcx+10h]
0x180014a6c  movups  xmmword ptr [rdi+10h], xmm1
0x180014a70  jmp     loc_18001496F
0x180014a75  mov     r8d, 20h ; ' '; MaxCount
0x180014a7b  lea     rdx, aBcryptFipsServ; "[ BCRYPT_FIPS_SERVICE_INDICATOR]"
0x180014a82  mov     rcx, r14; Str1
0x180014a85  call    wcsncmp_0
0x180014a8a  test    eax, eax
0x180014a8c  jnz     short loc_180014AF0
0x180014a8e  mov     [rsp+78h+arg_28], r13d
0x180014a96  test    rdi, rdi
0x180014a99  jnz     short loc_180014AA6
0x180014a9b  mov     dword ptr [rsi], 4
0x180014aa1  jmp     loc_18001496F
0x180014aa6  cmp     ebp, 4
0x180014aa9  jnb     short loc_180014AB9
0x180014aab  mov     [rsi], r13d
0x180014aae  mov     r9d, 938h
0x180014ab4  jmp     loc_180014981
0x180014ab9  lea     rdx, [rsp+78h+arg_28]
0x180014ac1  mov     rcx, r14; Src
0x180014ac4  call    ApprovedServicesIndicator
0x180014ac9  mov     ebx, eax
0x180014acb  test    eax, eax
0x180014acd  jns     short loc_180014ADC
0x180014acf  mov     r9d, 940h
0x180014ad5  mov     ecx, eax
0x180014ad7  jmp     loc_180014B5E
0x180014adc  mov     eax, [rsp+78h+arg_28]
0x180014ae3  mov     [rdi], eax
0x180014ae5  mov     dword ptr [rsi], 4
0x180014aeb  jmp     loc_180014B71
0x180014af0  mov     eax, [rbx+4]
0x180014af3  cmp     eax, 4D535341h
0x180014af8  jnz     short loc_180014B23
0x180014afa  mov     [rsp+78h+var_50], r12d
0x180014aff  mov     r9d, ebp
0x180014b02  mov     r8, rdi
0x180014b05  mov     [rsp+78h+var_58], rsi
0x180014b0a  mov     rdx, r14
0x180014b0d  mov     rcx, r15
0x180014b10  call    MSCryptGetAlgProperty
0x180014b15  mov     ebx, eax
0x180014b17  test    eax, eax
0x180014b19  jns     short loc_180014B71
0x180014b1b  mov     r9d, 955h
0x180014b21  jmp     short loc_180014AD5
0x180014b23  cmp     eax, 4D53534Bh
0x180014b28  jnz     short loc_180014B4E
0x180014b2a  mov     r9d, ebp
0x180014b2d  mov     [rsp+78h+var_58], rsi
0x180014b32  mov     r8, rdi
0x180014b35  mov     rdx, r14
0x180014b38  mov     rcx, r15
0x180014b3b  call    MSCryptGetKeyProperty
0x180014b40  mov     ebx, eax
0x180014b42  test    eax, eax
0x180014b44  jns     short loc_180014B71
0x180014b46  mov     r9d, 963h
0x180014b4c  jmp     short loc_180014AD5
0x180014b4e  mov     r9d, 96Ah
0x180014b54  mov     ecx, 0C0000008h
0x180014b59  mov     ebx, 0C0000008h
0x180014b5e  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180014b65  lea     rdx, aStatus; "Status"
0x180014b6c  call    DebugTraceError
0x180014b71  mov     eax, ebx
0x180014b73  add     rsp, 38h
0x180014b77  pop     r15
0x180014b79  pop     r14
0x180014b7b  pop     r13
0x180014b7d  pop     r12
0x180014b7f  pop     rdi
0x180014b80  pop     rsi
0x180014b81  pop     rbp
0x180014b82  pop     rbx
0x180014b83  retn
```
