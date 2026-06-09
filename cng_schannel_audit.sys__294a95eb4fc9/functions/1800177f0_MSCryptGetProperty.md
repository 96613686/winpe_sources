# MSCryptGetProperty

- ea: `0x1800177f0`
- end: `0x180017ad5`
- name: `MSCryptGetProperty`
- size: `741`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180016fc0`
- `0x1800173a0`
- `0x18007f654`

## callees

- `0x18000743c`
- `0x1800177f0`
- `0x18003a260`
- `0x18003ca38`
- `0x1800413e4`
- `0x18007f700`
- `0x18009d746`
- `0x18009d758`
- `0x18009da40`

## string_xrefs

- `0x180017aae`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x1800179cb`: `[ BCRYPT_FIPS_SERVICE_INDICATOR]`

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
    while ( (&off_1800A5088)[v15][v16] );
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
    memmove(a3, (&off_1800A5088)[v15], v17);
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
0x1800177f0  push    rbx
0x1800177f2  push    rbp
0x1800177f3  push    rsi
0x1800177f4  push    rdi
0x1800177f5  push    r12
0x1800177f7  push    r13
0x1800177f9  push    r14
0x1800177fb  push    r15
0x1800177fd  sub     rsp, 38h
0x180017801  mov     r12d, [rsp+78h+arg_28]
0x180017809  mov     ebp, r9d
0x18001780c  mov     rdi, r8
0x18001780f  mov     r14, rdx
0x180017812  mov     r15, rcx
0x180017815  test    r12d, 0FFFFFF7Fh
0x18001781c  jz      short loc_180017833
0x18001781e  mov     r9d, 8A9h
0x180017824  mov     ebx, 0C000000Dh
0x180017829  mov     ecx, 0C000000Dh
0x18001782e  jmp     loc_180017AAE
0x180017833  call    validateMSCryptSymmObject
0x180017838  xor     r13d, r13d
0x18001783b  mov     rbx, rax
0x18001783e  test    rax, rax
0x180017841  jnz     short loc_18001784E
0x180017843  mov     r9d, 8B2h
0x180017849  jmp     loc_180017AA4
0x18001784e  mov     rsi, [rsp+78h+arg_20]
0x180017856  test    rsi, rsi
0x180017859  jnz     short loc_180017863
0x18001785b  mov     r9d, 8B9h
0x180017861  jmp     short loc_180017824
0x180017863  lea     rdx, aAlgorithmname; "AlgorithmName"
0x18001786a  mov     rcx, r14; Str1
0x18001786d  call    wcscmp_0
0x180017872  test    eax, eax
0x180017874  jnz     short loc_1800178F5
0x180017876  mov     eax, [rbx+8]
0x180017879  movzx   ecx, ax
0x18001787c  dec     ecx
0x18001787e  cmp     ecx, 9
0x180017881  jb      short loc_18001788E
0x180017883  mov     r9d, 8C4h
0x180017889  jmp     loc_180017AA4
0x18001788e  mov     eax, ecx
0x180017890  lea     rcx, cs:180000000h
0x180017897  imul    rdx, rax, 70h ; 'p'
0x18001789b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001789f  mov     r8, [rdx+rcx+0A5088h]
0x1800178a7  inc     rax
0x1800178aa  cmp     [r8+rax*2], r13w
0x1800178af  jnz     short loc_1800178A7
0x1800178b1  lea     eax, ds:2[rax*2]
0x1800178b8  mov     [rsi], eax
0x1800178ba  test    rdi, rdi
0x1800178bd  jnz     short loc_1800178C7
0x1800178bf  mov     ebx, r13d
0x1800178c2  jmp     loc_180017AC1
0x1800178c7  cmp     ebp, eax
0x1800178c9  jnb     short loc_1800178E0
0x1800178cb  mov     r9d, 8D3h
0x1800178d1  mov     ebx, 0C0000023h
0x1800178d6  mov     ecx, 0C0000023h
0x1800178db  jmp     loc_180017AAE
0x1800178e0  mov     rdx, [rdx+rcx+0A5088h]; Src
0x1800178e8  mov     rcx, rdi; void *
0x1800178eb  mov     r8d, eax; Size
0x1800178ee  call    memmove
0x1800178f3  jmp     short loc_1800178BF
0x1800178f5  lea     rdx, aBlocklength; "BlockLength"
0x1800178fc  mov     rcx, r14; Str1
0x1800178ff  call    wcscmp_0
0x180017904  test    eax, eax
0x180017906  jnz     short loc_180017927
0x180017908  mov     dword ptr [rsi], 4
0x18001790e  test    rdi, rdi
0x180017911  jz      short loc_1800178BF
0x180017913  cmp     ebp, 4
0x180017916  jnb     short loc_180017920
0x180017918  mov     r9d, 8E8h
0x18001791e  jmp     short loc_1800178D1
0x180017920  mov     eax, [rbx+10h]
0x180017923  mov     [rdi], eax
0x180017925  jmp     short loc_1800178BF
0x180017927  lea     rdx, aMessageblockle; "MessageBlockLength"
0x18001792e  mov     rcx, r14; Str1
0x180017931  call    wcscmp_0
0x180017936  test    eax, eax
0x180017938  jnz     short loc_18001795E
0x18001793a  mov     dword ptr [rsi], 4
0x180017940  test    rdi, rdi
0x180017943  jz      loc_1800178BF
0x180017949  cmp     ebp, 4
0x18001794c  jnb     short loc_180017959
0x18001794e  mov     r9d, 8FEh
0x180017954  jmp     loc_1800178D1
0x180017959  mov     eax, [rbx+14h]
0x18001795c  jmp     short loc_180017923
0x18001795e  lea     rdx, aChainingmode; "ChainingMode"
0x180017965  mov     rcx, r14; Str1
0x180017968  call    wcscmp_0
0x18001796d  test    eax, eax
0x18001796f  jnz     short loc_1800179C5
0x180017971  mov     dword ptr [rsi], 20h ; ' '
0x180017977  test    rdi, rdi
0x18001797a  jz      loc_1800178BF
0x180017980  cmp     ebp, 20h ; ' '
0x180017983  jnb     short loc_180017990
0x180017985  mov     r9d, 916h
0x18001798b  jmp     loc_1800178D1
0x180017990  mov     eax, [rbx+0Ch]
0x180017993  cmp     eax, 6
0x180017996  jb      short loc_1800179A3
0x180017998  mov     r9d, 91Dh
0x18001799e  jmp     loc_180017AA4
0x1800179a3  lea     rcx, cs:180000000h
0x1800179aa  mov     rcx, ds:rva rgpszChainModeNameArray[rcx+rax*8]
0x1800179b2  movups  xmm0, xmmword ptr [rcx]
0x1800179b5  movups  xmmword ptr [rdi], xmm0
0x1800179b8  movups  xmm1, xmmword ptr [rcx+10h]
0x1800179bc  movups  xmmword ptr [rdi+10h], xmm1
0x1800179c0  jmp     loc_1800178BF
0x1800179c5  mov     r8d, 20h ; ' '; MaxCount
0x1800179cb  lea     rdx, aBcryptFipsServ; "[ BCRYPT_FIPS_SERVICE_INDICATOR]"
0x1800179d2  mov     rcx, r14; Str1
0x1800179d5  call    wcsncmp_0
0x1800179da  test    eax, eax
0x1800179dc  jnz     short loc_180017A40
0x1800179de  mov     [rsp+78h+arg_28], r13d
0x1800179e6  test    rdi, rdi
0x1800179e9  jnz     short loc_1800179F6
0x1800179eb  mov     dword ptr [rsi], 4
0x1800179f1  jmp     loc_1800178BF
0x1800179f6  cmp     ebp, 4
0x1800179f9  jnb     short loc_180017A09
0x1800179fb  mov     [rsi], r13d
0x1800179fe  mov     r9d, 938h
0x180017a04  jmp     loc_1800178D1
0x180017a09  lea     rdx, [rsp+78h+arg_28]
0x180017a11  mov     rcx, r14; Src
0x180017a14  call    ApprovedServicesIndicator
0x180017a19  mov     ebx, eax
0x180017a1b  test    eax, eax
0x180017a1d  jns     short loc_180017A2C
0x180017a1f  mov     r9d, 940h
0x180017a25  mov     ecx, eax
0x180017a27  jmp     loc_180017AAE
0x180017a2c  mov     eax, [rsp+78h+arg_28]
0x180017a33  mov     [rdi], eax
0x180017a35  mov     dword ptr [rsi], 4
0x180017a3b  jmp     loc_180017AC1
0x180017a40  mov     eax, [rbx+4]
0x180017a43  cmp     eax, 4D535341h
0x180017a48  jnz     short loc_180017A73
0x180017a4a  mov     [rsp+78h+var_50], r12d
0x180017a4f  mov     r9d, ebp
0x180017a52  mov     r8, rdi
0x180017a55  mov     [rsp+78h+var_58], rsi
0x180017a5a  mov     rdx, r14
0x180017a5d  mov     rcx, r15
0x180017a60  call    MSCryptGetAlgProperty
0x180017a65  mov     ebx, eax
0x180017a67  test    eax, eax
0x180017a69  jns     short loc_180017AC1
0x180017a6b  mov     r9d, 955h
0x180017a71  jmp     short loc_180017A25
0x180017a73  cmp     eax, 4D53534Bh
0x180017a78  jnz     short loc_180017A9E
0x180017a7a  mov     r9d, ebp
0x180017a7d  mov     [rsp+78h+var_58], rsi
0x180017a82  mov     r8, rdi
0x180017a85  mov     rdx, r14
0x180017a88  mov     rcx, r15
0x180017a8b  call    MSCryptGetKeyProperty
0x180017a90  mov     ebx, eax
0x180017a92  test    eax, eax
0x180017a94  jns     short loc_180017AC1
0x180017a96  mov     r9d, 963h
0x180017a9c  jmp     short loc_180017A25
0x180017a9e  mov     r9d, 96Ah
0x180017aa4  mov     ecx, 0C0000008h
0x180017aa9  mov     ebx, 0C0000008h
0x180017aae  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180017ab5  lea     rdx, aStatus; "Status"
0x180017abc  call    DebugTraceError
0x180017ac1  mov     eax, ebx
0x180017ac3  add     rsp, 38h
0x180017ac7  pop     r15
0x180017ac9  pop     r14
0x180017acb  pop     r13
0x180017acd  pop     r12
0x180017acf  pop     rdi
0x180017ad0  pop     rsi
0x180017ad1  pop     rbp
0x180017ad2  pop     rbx
0x180017ad3  retn
```
