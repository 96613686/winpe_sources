# GetRsaProperty

- ea: `0x18004979c`
- end: `0x18004999f`
- name: `GetRsaProperty`
- size: `515`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180049770`
- `0x180081ae0`
- `0x180088308`

## callees

- `0x18001155c`
- `0x1800123d0`
- `0x18004979c`
- `0x1800499a8`
- `0x180049c28`
- `0x180081874`
- `0x1800a4232`

## import_xrefs

- `ntoskrnl!wcscpy_s` at `0x1800a898c`
- `ntoskrnl!wcscpy_s` at `0x1800a898c`

## string_xrefs

- `0x180049899`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x1800a89b6`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`

## pseudocode

```c
__int64 __fastcall GetRsaProperty(
        __int64 a1,
        const wchar_t *a2,
        __int64 a3,
        unsigned int a4,
        unsigned int *a5,
        unsigned int a6,
        char a7)
{
  unsigned __int64 v8; // rsi
  int v11; // eax
  unsigned int v12; // ebx
  __int64 v14; // rbp
  __int64 v15; // r9
  __int64 v16; // rcx
  char v17; // r8
  unsigned int v18; // ecx
  bool v19; // zf
  const wchar_t *v20; // r8
  unsigned int v21; // eax
  __int64 v22; // rax
  int v23; // eax

  v8 = a4;
  if ( a6 )
  {
    v12 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        (_DWORD)a2,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
        78);
    return v12;
  }
  if ( !a2 )
  {
    v12 = -1073741811;
    v15 = 597;
    v16 = 3221225485LL;
LABEL_34:
    DebugTraceError(v16, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c", v15);
    return v12;
  }
  if ( !a1 || (v11 = *(_DWORD *)(a1 + 4), v11 != 1297306177) && v11 != 1297306187 )
  {
    v12 = -1073741816;
    v15 = 605;
    v16 = 3221225480LL;
    goto LABEL_34;
  }
  if ( !wcscmp_0(a2, L"AlgorithmName") )
  {
    v17 = a7;
    v18 = a7 != 0 ? 18 : 8;
    *a5 = v18;
    if ( !a3 )
      return 0;
    if ( (unsigned int)v8 >= v18 )
    {
      v19 = v17 == 0;
      v20 = L"RSA_SIGN";
      if ( v19 )
        v20 = L"RSA";
      wcscpy_s((wchar_t *)a3, v8 >> 1, v20);
      return 0;
    }
    return (unsigned int)-1073741789;
  }
  if ( validateMSCryptRsaAlgorithm(a1) )
  {
    if ( !wcscmp_0(a2, L"PaddingSchemes") )
    {
      *a5 = 4;
      if ( !a3 )
        return 0;
      if ( (unsigned int)v8 >= 4 )
      {
        *(_DWORD *)a3 = a7 != 0 ? 20 : 30;
        return 0;
      }
      return (unsigned int)-1073741789;
    }
    if ( !wcscmp_0(a2, L"KeyLengths") )
    {
      *a5 = 12;
      if ( !a3 )
        return 0;
      if ( (unsigned int)v8 >= 0xC )
      {
        *(_DWORD *)a3 = 512;
        *(_DWORD *)(a3 + 4) = 0x4000;
        *(_DWORD *)(a3 + 8) = 8;
        return 0;
      }
      return (unsigned int)-1073741789;
    }
    v15 = 707;
LABEL_33:
    v12 = -1073741637;
    v16 = 3221225659LL;
    goto LABEL_34;
  }
  v14 = validateMSCryptRsaKey(a1);
  if ( v14 )
  {
    if ( !wcscmp_0(a2, L"KeyStrength") || !wcscmp_0(a2, L"KeyLength") || !wcscmp_0(a2, L"PublicKeyLength") )
    {
      *a5 = 4;
      if ( !a3 )
        return 0;
      if ( (unsigned int)v8 < 4 )
        return (unsigned int)-1073741789;
      v21 = *(_DWORD *)(v14 + 12);
    }
    else if ( !wcscmp_0(a2, L"BlockLength") || !wcscmp_0(a2, L"SignatureLength") )
    {
      *a5 = 4;
      if ( !a3 )
        return 0;
      if ( (unsigned int)v8 < 4 )
        return (unsigned int)-1073741789;
      v22 = *(_QWORD *)(v14 + 32);
      if ( v22 )
        v23 = *(_DWORD *)(v22 + 16);
      else
        v23 = *(_DWORD *)(v14 + 12);
      v21 = (unsigned int)(v23 + 7) >> 3;
    }
    else
    {
      if ( wcscmp_0(a2, L"IsIfxTpmWeakKey") )
      {
        v15 = 781;
        goto LABEL_33;
      }
      a6 = 0;
      *a5 = 4;
      if ( !a3 )
        return 0;
      if ( (unsigned int)v8 < 4 )
        return (unsigned int)-1073741789;
      v12 = IsIfxTpmWeakKeyProperty(a1, &a6);
      if ( (v12 & 0x80000000) != 0 )
        return v12;
      v21 = a6;
    }
    *(_DWORD *)a3 = v21;
    return 0;
  }
  return 3221225480LL;
}

```

## disassembly

```asm
0x18004979c  push    rbx
0x18004979e  push    rbp
0x18004979f  push    rsi
0x1800497a0  push    rdi
0x1800497a1  push    r14
0x1800497a3  sub     rsp, 40h
0x1800497a7  cmp     [rsp+68h+arg_28], 0
0x1800497af  mov     rdi, r8
0x1800497b2  mov     esi, r9d
0x1800497b5  mov     rbx, rdx
0x1800497b8  mov     r14, rcx
0x1800497bb  jnz     loc_180049876
0x1800497c1  test    rdx, rdx
0x1800497c4  jz      loc_1800498C3
0x1800497ca  test    rcx, rcx
0x1800497cd  jz      loc_1800498E3
0x1800497d3  mov     eax, [rcx+4]
0x1800497d6  cmp     eax, 4D535241h
0x1800497db  jnz     loc_1800498D8
0x1800497e1  lea     rdx, aAlgorithmname; "AlgorithmName"
0x1800497e8  mov     rcx, rbx; Str1
0x1800497eb  call    wcscmp_0
0x1800497f0  test    eax, eax
0x1800497f2  jz      loc_1800498F8
0x1800497f8  mov     rcx, r14
0x1800497fb  call    validateMSCryptRsaAlgorithm
0x180049800  test    rax, rax
0x180049803  jz      short loc_18004985B
0x180049805  lea     rdx, aPaddingschemes; "PaddingSchemes"
0x18004980c  mov     rcx, rbx; Str1
0x18004980f  call    wcscmp_0
0x180049814  test    eax, eax
0x180049816  jnz     loc_180049953
0x18004981c  mov     rax, [rsp+68h+arg_20]
0x180049824  mov     dword ptr [rax], 4
0x18004982a  test    rdi, rdi
0x18004982d  jz      short loc_18004984B
0x18004982f  cmp     esi, 4
0x180049832  jb      loc_180049949
0x180049838  mov     al, [rsp+68h+arg_30]
0x18004983f  neg     al
0x180049841  sbb     ecx, ecx
0x180049843  and     ecx, 0FFFFFFF6h
0x180049846  add     ecx, 1Eh
0x180049849  mov     [rdi], ecx
0x18004984b  xor     ebx, ebx
0x18004984d  mov     eax, ebx
0x18004984f  add     rsp, 40h
0x180049853  pop     r14
0x180049855  pop     rdi
0x180049856  pop     rsi
0x180049857  pop     rbp
0x180049858  pop     rbx
0x180049859  retn
0x18004985b  mov     rcx, r14
0x18004985e  call    validateMSCryptRsaKey
0x180049863  mov     rbp, rax
0x180049866  test    rax, rax
0x180049869  jnz     loc_1800A89CF
0x18004986f  mov     eax, 0C0000008h
0x180049874  jmp     short loc_18004984F
0x180049876  mov     ebx, 0C000000Dh
0x18004987b  mov     rcx, cs:WPP_GLOBAL_Control
0x180049882  lea     rax, WPP_GLOBAL_Control
0x180049889  cmp     rcx, rax
0x18004988c  jz      short loc_18004984D
0x18004988e  mov     eax, [rcx+2Ch]
0x180049891  test    al, 1
0x180049893  jz      short loc_18004984D
0x180049895  mov     rcx, [rcx+18h]
0x180049899  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800498a0  mov     [rsp+68h+var_38], 24Eh
0x1800498a8  lea     r9, aStatus; "Status"
0x1800498af  mov     [rsp+68h+var_40], r8
0x1800498b4  mov     [rsp+68h+var_48], 0C000000Dh
0x1800498bc  call    WPP_SF_sDsd
0x1800498c1  jmp     short loc_18004984D
0x1800498c3  mov     ebx, 0C000000Dh
0x1800498c8  mov     r9d, 255h
0x1800498ce  mov     ecx, 0C000000Dh
0x1800498d3  jmp     loc_1800A89B6
0x1800498d8  cmp     eax, 4D53524Bh
0x1800498dd  jz      loc_1800497E1
0x1800498e3  mov     ebx, 0C0000008h
0x1800498e8  mov     r9d, 25Dh
0x1800498ee  mov     ecx, 0C0000008h
0x1800498f3  jmp     loc_1800A89B6
0x1800498f8  mov     r8b, [rsp+68h+arg_30]
0x180049900  mov     al, r8b
0x180049903  neg     al
0x180049905  mov     rax, [rsp+68h+arg_20]
0x18004990d  sbb     ecx, ecx
0x18004990f  and     ecx, 0Ah
0x180049912  add     ecx, 8
0x180049915  mov     [rax], ecx
0x180049917  test    rdi, rdi
0x18004991a  jz      loc_18004984B
0x180049920  cmp     esi, ecx
0x180049922  jb      short loc_180049949
0x180049924  mov     rdx, rsi
0x180049927  mov     rcx, rdi; Dst
0x18004992a  shr     rdx, 1; SizeInWords
0x18004992d  test    r8b, r8b
0x180049930  lea     r8, aRsaSign; "RSA_SIGN"
0x180049937  jnz     loc_1800A898C
0x18004993d  lea     r8, aRsa; "RSA"
0x180049944  jmp     loc_1800A898C
0x180049949  mov     ebx, 0C0000023h
0x18004994e  jmp     loc_18004984D
0x180049953  lea     rdx, aKeylengths; "KeyLengths"
0x18004995a  mov     rcx, rbx; Str1
0x18004995d  call    wcscmp_0
0x180049962  test    eax, eax
0x180049964  jnz     loc_1800A899E
0x18004996a  mov     rax, [rsp+68h+arg_20]
0x180049972  mov     dword ptr [rax], 0Ch
0x180049978  test    rdi, rdi
0x18004997b  jz      loc_18004984B
0x180049981  cmp     esi, 0Ch
0x180049984  jb      short loc_180049949
0x180049986  mov     dword ptr [rdi], 200h
0x18004998c  mov     dword ptr [rdi+4], 4000h
0x180049993  mov     dword ptr [rdi+8], 8
0x18004999a  jmp     loc_18004984B
0x1800a898c  call    cs:__imp_wcscpy_s
0x1800a8993  nop     dword ptr [rax+rax+00h]
0x1800a8998  nop
0x1800a8999  jmp     loc_18004984B
0x1800a899e  mov     r9d, 2C3h
0x1800a89a4  jmp     short loc_1800A89AC
0x1800a89a6  mov     r9d, 30Dh
0x1800a89ac  mov     ebx, 0C00000BBh
0x1800a89b1  mov     ecx, 0C00000BBh
0x1800a89b6  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a89bd  lea     rdx, aStatus; "Status"
0x1800a89c4  call    DebugTraceError
0x1800a89c9  nop
0x1800a89ca  jmp     loc_18004984D
0x1800a89cf  lea     rdx, aKeystrength; "KeyStrength"
0x1800a89d6  mov     rcx, rbx; Str1
0x1800a89d9  call    wcscmp_0
0x1800a89de  test    eax, eax
0x1800a89e0  jz      loc_1800A8AD4
0x1800a89e6  lea     rdx, aKeylength; "KeyLength"
0x1800a89ed  mov     rcx, rbx; Str1
0x1800a89f0  call    wcscmp_0
0x1800a89f5  test    eax, eax
0x1800a89f7  jz      loc_1800A8AD4
0x1800a89fd  lea     rdx, aPublickeylengt; "PublicKeyLength"
0x1800a8a04  mov     rcx, rbx; Str1
0x1800a8a07  call    wcscmp_0
0x1800a8a0c  test    eax, eax
0x1800a8a0e  jz      loc_1800A8AD4
0x1800a8a14  lea     rdx, aBlocklength; "BlockLength"
0x1800a8a1b  mov     rcx, rbx; Str1
0x1800a8a1e  call    wcscmp_0
0x1800a8a23  test    eax, eax
0x1800a8a25  jz      short loc_1800A8A9B
0x1800a8a27  lea     rdx, aSignaturelengt; "SignatureLength"
0x1800a8a2e  mov     rcx, rbx; Str1
0x1800a8a31  call    wcscmp_0
0x1800a8a36  test    eax, eax
0x1800a8a38  jz      short loc_1800A8A9B
0x1800a8a3a  lea     rdx, aIsifxtpmweakke; "IsIfxTpmWeakKey"
0x1800a8a41  mov     rcx, rbx; Str1
0x1800a8a44  call    wcscmp_0
0x1800a8a49  test    eax, eax
0x1800a8a4b  jnz     loc_1800A89A6
0x1800a8a51  mov     [rsp+68h+arg_28], eax
0x1800a8a58  mov     rax, [rsp+68h+arg_20]
0x1800a8a60  mov     dword ptr [rax], 4
0x1800a8a66  test    rdi, rdi
0x1800a8a69  jz      loc_18004984B
0x1800a8a6f  cmp     esi, 4
0x1800a8a72  jb      loc_180049949
0x1800a8a78  lea     rdx, [rsp+68h+arg_28]
0x1800a8a80  mov     rcx, r14
0x1800a8a83  call    IsIfxTpmWeakKeyProperty
0x1800a8a88  mov     ebx, eax
0x1800a8a8a  test    eax, eax
0x1800a8a8c  js      loc_18004984D
0x1800a8a92  mov     eax, [rsp+68h+arg_28]
0x1800a8a99  jmp     short loc_1800A8AF7
0x1800a8a9b  mov     rax, [rsp+68h+arg_20]
0x1800a8aa3  mov     dword ptr [rax], 4
0x1800a8aa9  test    rdi, rdi
0x1800a8aac  jz      loc_18004984B
0x1800a8ab2  cmp     esi, 4
0x1800a8ab5  jb      loc_180049949
0x1800a8abb  mov     rax, [rbp+20h]
0x1800a8abf  test    rax, rax
0x1800a8ac2  jz      short loc_1800A8AC9
0x1800a8ac4  mov     eax, [rax+10h]
0x1800a8ac7  jmp     short loc_1800A8ACC
0x1800a8ac9  mov     eax, [rbp+0Ch]
0x1800a8acc  add     eax, 7
0x1800a8acf  shr     eax, 3
0x1800a8ad2  jmp     short loc_1800A8AF7
0x1800a8ad4  mov     rax, [rsp+68h+arg_20]
0x1800a8adc  mov     dword ptr [rax], 4
0x1800a8ae2  test    rdi, rdi
0x1800a8ae5  jz      loc_18004984B
0x1800a8aeb  cmp     esi, 4
0x1800a8aee  jb      loc_180049949
0x1800a8af4  mov     eax, [rbp+0Ch]
0x1800a8af7  mov     [rdi], eax
0x1800a8af9  jmp     loc_18004984B
```
