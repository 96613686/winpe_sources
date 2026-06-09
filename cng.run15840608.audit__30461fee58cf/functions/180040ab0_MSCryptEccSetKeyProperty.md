# MSCryptEccSetKeyProperty

- ea: `0x180040ab0`
- end: `0x180040db6`
- name: `MSCryptEccSetKeyProperty`
- size: `774`
- prototype: `__int64 __fastcall(__int64, const wchar_t *, _DWORD *, unsigned int, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180040688`

## callees

- `0x18000743c`
- `0x1800082b0`
- `0x18003d474`
- `0x180040ab0`
- `0x180040f90`
- `0x1800773b4`
- `0x1800775c4`
- `0x18009d746`

## string_xrefs

- `0x180040ac7`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180040b7d`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall MSCryptEccSetKeyProperty(__int64 a1, const wchar_t *a2, _DWORD *a3, unsigned int a4, int a5)
{
  unsigned int v9; // ebx
  __int64 i; // rdx
  char *v11; // rcx
  __int64 v12; // r9
  __int64 v13; // rcx
  int Curve; // eax
  bool v15; // zf
  __int64 v16; // rax
  __int64 v17; // rdx
  _QWORD v19[9]; // [rsp+40h] [rbp-48h] BYREF
  unsigned int v20; // [rsp+90h] [rbp+8h] BYREF

  if ( !a1 )
  {
    v9 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        (_DWORD)a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        51);
    goto LABEL_46;
  }
  if ( *(_DWORD *)(a1 + 4) != 1297304409 )
  {
    v9 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        (_DWORD)a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        60);
    goto LABEL_46;
  }
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= 4 )
    {
      v9 = -1073741811;
      DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", 628);
LABEL_46:
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          (_DWORD)a2,
          (_DWORD)a3,
          (unsigned int)"Status",
          13,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
          162);
      return v9;
    }
    v11 = byte_1800A6E78;
    if ( !a5 )
      v11 = byte_1800A6DB8;
    if ( *(_DWORD *)(a1 + 8) == *(_DWORD *)&v11[48 * i] )
      break;
  }
  if ( wcscmp_0(a2, L"ECCParameters") )
  {
    if ( !wcscmp_0(a2, L"ECCCurveName") )
    {
      v15 = *(_QWORD *)(a1 + 16) == 0;
      v19[0] = 0;
      v20 = 0;
      if ( !v15 )
      {
        v12 = 3784;
LABEL_15:
        v9 = -1073741637;
        v13 = 3221225659LL;
LABEL_16:
        DebugTraceError(v13, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", v12);
        return v9;
      }
      Curve = ValidateCurveName(a3, a4, v19, &v20);
      v9 = Curve;
      if ( Curve >= 0 )
      {
        Curve = LoadCurve(a1 + 16, *(unsigned int *)(a1 + 8), v19[0], v20);
        v9 = Curve;
        if ( Curve >= 0 )
          return v9;
        v12 = 3799;
      }
      else
      {
        v12 = 3792;
      }
    }
    else
    {
      if ( !wcscmp_0(a2, L"KeyLength") || !wcscmp_0(a2, L"KeyStrength") )
      {
        if ( a4 != 4 || !a3 || (v16 = *(_QWORD *)(a1 + 16)) == 0 )
        {
          v9 = -1073741811;
          v12 = 3812;
          v13 = 3221225485LL;
          goto LABEL_16;
        }
        v17 = *(_QWORD *)(v16 + 8);
        if ( *(_DWORD *)(v17 + 12) == *a3 || *(_DWORD *)(v17 + 24) == *a3 )
          return 0;
        v12 = 3825;
        goto LABEL_15;
      }
      if ( (unsigned int)(*(_DWORD *)(a1 + 8) - 196615) > 3 || wcscmp_0(a2, L"PrivKeyVal") )
      {
        v12 = 3846;
        goto LABEL_15;
      }
      Curve = SetEccPrivateKeyVal(a1, a3, a4);
      v9 = Curve;
      if ( Curve >= 0 )
        return v9;
      v12 = 3839;
    }
LABEL_19:
    v13 = (unsigned int)Curve;
    goto LABEL_16;
  }
  if ( *(_QWORD *)(a1 + 16) )
  {
    v12 = 3760;
    goto LABEL_15;
  }
  Curve = AssignGenericDomainParameters((int)a1 + 16, *(_DWORD *)(a1 + 8), (_DWORD)a3, a4, 0, 0);
  v9 = Curve;
  if ( Curve < 0 )
  {
    v12 = 3767;
    goto LABEL_19;
  }
  return v9;
}

```

## disassembly

```asm
0x180040ab0  push    rbx
0x180040ab2  push    rbp
0x180040ab3  push    rsi
0x180040ab4  push    rdi
0x180040ab5  push    r12
0x180040ab7  push    r14
0x180040ab9  sub     rsp, 58h
0x180040abd  lea     r12, WPP_GLOBAL_Control
0x180040ac4  mov     r14d, r9d
0x180040ac7  lea     rdi, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180040ace  mov     rbx, r8
0x180040ad1  mov     rbp, rdx
0x180040ad4  mov     rsi, rcx
0x180040ad7  test    rcx, rcx
0x180040ada  jz      loc_180040D33
0x180040ae0  cmp     dword ptr [rcx+4], 4D534B59h
0x180040ae7  jz      short loc_180040B18
0x180040ae9  mov     ebx, 0C000000Dh
0x180040aee  mov     esi, ebx
0x180040af0  mov     rcx, cs:WPP_GLOBAL_Control
0x180040af7  cmp     rcx, r12
0x180040afa  jz      loc_180040D72
0x180040b00  mov     eax, [rcx+2Ch]
0x180040b03  test    al, 1
0x180040b05  jz      loc_180040D72
0x180040b0b  mov     [rsp+88h+var_58], 23Ch
0x180040b13  jmp     loc_180040D55
0x180040b18  xor     edx, edx
0x180040b1a  cmp     edx, 4
0x180040b1d  jnb     loc_180040D10
0x180040b23  cmp     [rsp+88h+arg_20], 0
0x180040b2b  lea     rax, byte_1800A6DB8
0x180040b32  lea     rcx, byte_1800A6E78
0x180040b39  cmovz   rcx, rax
0x180040b3d  lea     rax, [rdx+rdx*2]
0x180040b41  add     rax, rax
0x180040b44  mov     eax, [rcx+rax*8]
0x180040b47  cmp     [rsi+8], eax
0x180040b4a  jz      short loc_180040B50
0x180040b4c  inc     edx
0x180040b4e  jmp     short loc_180040B1A
0x180040b50  lea     rdx, aEccparameters; "ECCParameters"
0x180040b57  mov     rcx, rbp; Str1
0x180040b5a  call    wcscmp_0
0x180040b5f  test    eax, eax
0x180040b61  jnz     short loc_180040BC8
0x180040b63  lea     rcx, [rsi+10h]
0x180040b67  cmp     qword ptr [rcx], 0
0x180040b6b  jz      short loc_180040B95
0x180040b6d  mov     r9d, 0EB0h
0x180040b73  mov     ebx, 0C00000BBh
0x180040b78  mov     ecx, 0C00000BBh
0x180040b7d  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180040b84  lea     rdx, aStatus; "Status"
0x180040b8b  call    DebugTraceError
0x180040b90  jmp     loc_180040DA6
0x180040b95  mov     edx, [rsi+8]
0x180040b98  mov     r9d, r14d
0x180040b9b  mov     dword ptr [rsp+88h+var_60], 0
0x180040ba3  mov     r8, rbx
0x180040ba6  mov     [rsp+88h+var_68], 0
0x180040baf  call    AssignGenericDomainParameters
0x180040bb4  mov     ebx, eax
0x180040bb6  test    eax, eax
0x180040bb8  jns     loc_180040DA6
0x180040bbe  mov     r9d, 0EB7h
0x180040bc4  mov     ecx, eax
0x180040bc6  jmp     short loc_180040B7D
0x180040bc8  lea     rdx, aEcccurvename; "ECCCurveName"
0x180040bcf  mov     rcx, rbp; Str1
0x180040bd2  call    wcscmp_0
0x180040bd7  test    eax, eax
0x180040bd9  jnz     short loc_180040C51
0x180040bdb  cmp     qword ptr [rsi+10h], 0
0x180040be0  mov     [rsp+88h+var_48], 0
0x180040be9  mov     [rsp+88h+arg_0], eax
0x180040bf0  jz      short loc_180040BFD
0x180040bf2  mov     r9d, 0EC8h
0x180040bf8  jmp     loc_180040B73
0x180040bfd  lea     r9, [rsp+88h+arg_0]
0x180040c05  mov     edx, r14d
0x180040c08  lea     r8, [rsp+88h+var_48]
0x180040c0d  mov     rcx, rbx
0x180040c10  call    ValidateCurveName
0x180040c15  mov     ebx, eax
0x180040c17  test    eax, eax
0x180040c19  jns     short loc_180040C23
0x180040c1b  mov     r9d, 0ED0h
0x180040c21  jmp     short loc_180040BC4
0x180040c23  mov     r9d, [rsp+88h+arg_0]
0x180040c2b  lea     rcx, [rsi+10h]
0x180040c2f  mov     r8, [rsp+88h+var_48]
0x180040c34  mov     edx, [rsi+8]
0x180040c37  call    LoadCurve
0x180040c3c  mov     ebx, eax
0x180040c3e  test    eax, eax
0x180040c40  jns     loc_180040DA6
0x180040c46  mov     r9d, 0ED7h
0x180040c4c  jmp     loc_180040BC4
0x180040c51  lea     rdx, aKeylength; "KeyLength"
0x180040c58  mov     rcx, rbp; Str1
0x180040c5b  call    wcscmp_0
0x180040c60  test    eax, eax
0x180040c62  jz      short loc_180040CC5
0x180040c64  lea     rdx, aKeystrength; "KeyStrength"
0x180040c6b  mov     rcx, rbp; Str1
0x180040c6e  call    wcscmp_0
0x180040c73  test    eax, eax
0x180040c75  jz      short loc_180040CC5
0x180040c77  mov     eax, [rsi+8]
0x180040c7a  sub     eax, 30007h
0x180040c7f  cmp     eax, 3
0x180040c82  ja      short loc_180040CBA
0x180040c84  lea     rdx, aPrivkeyval; "PrivKeyVal"
0x180040c8b  mov     rcx, rbp; Str1
0x180040c8e  call    wcscmp_0
0x180040c93  test    eax, eax
0x180040c95  jnz     short loc_180040CBA
0x180040c97  mov     r8d, r14d
0x180040c9a  mov     rdx, rbx
0x180040c9d  mov     rcx, rsi
0x180040ca0  call    SetEccPrivateKeyVal
0x180040ca5  mov     ebx, eax
0x180040ca7  test    eax, eax
0x180040ca9  jns     loc_180040DA6
0x180040caf  mov     r9d, 0EFFh
0x180040cb5  jmp     loc_180040BC4
0x180040cba  mov     r9d, 0F06h
0x180040cc0  jmp     loc_180040B73
0x180040cc5  cmp     r14d, 4
0x180040cc9  jnz     short loc_180040CFB
0x180040ccb  test    rbx, rbx
0x180040cce  jz      short loc_180040CFB
0x180040cd0  mov     rax, [rsi+10h]
0x180040cd4  test    rax, rax
0x180040cd7  jz      short loc_180040CFB
0x180040cd9  mov     rdx, [rax+8]
0x180040cdd  mov     ecx, [rbx]
0x180040cdf  cmp     [rdx+0Ch], ecx
0x180040ce2  jz      short loc_180040CF4
0x180040ce4  cmp     [rdx+18h], ecx
0x180040ce7  jz      short loc_180040CF4
0x180040ce9  mov     r9d, 0EF1h
0x180040cef  jmp     loc_180040B73
0x180040cf4  xor     ebx, ebx
0x180040cf6  jmp     loc_180040DA6
0x180040cfb  mov     ebx, 0C000000Dh
0x180040d00  mov     r9d, 0EE4h
0x180040d06  mov     ecx, 0C000000Dh
0x180040d0b  jmp     loc_180040B7D
0x180040d10  mov     ebx, 0C000000Dh
0x180040d15  lea     rdx, aStatus; "Status"
0x180040d1c  mov     r9d, 274h
0x180040d22  mov     r8, rdi
0x180040d25  mov     ecx, 0C000000Dh
0x180040d2a  mov     esi, ebx
0x180040d2c  call    DebugTraceError
0x180040d31  jmp     short loc_180040D72
0x180040d33  mov     ebx, 0C000000Dh
0x180040d38  mov     esi, ebx
0x180040d3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180040d41  cmp     rcx, r12
0x180040d44  jz      short loc_180040D72
0x180040d46  mov     eax, [rcx+2Ch]
0x180040d49  test    al, 1
0x180040d4b  jz      short loc_180040D72
0x180040d4d  mov     [rsp+88h+var_58], 233h
0x180040d55  mov     rcx, [rcx+18h]
0x180040d59  lea     r9, aStatus; "Status"
0x180040d60  mov     [rsp+88h+var_60], rdi
0x180040d65  mov     dword ptr [rsp+88h+var_68], 0C000000Dh
0x180040d6d  call    WPP_SF_sDsd
0x180040d72  mov     rcx, cs:WPP_GLOBAL_Control
0x180040d79  cmp     rcx, r12
0x180040d7c  jz      short loc_180040DA6
0x180040d7e  mov     eax, [rcx+2Ch]
0x180040d81  test    al, 1
0x180040d83  jz      short loc_180040DA6
0x180040d85  mov     rcx, [rcx+18h]
0x180040d89  lea     r9, aStatus; "Status"
0x180040d90  mov     [rsp+88h+var_58], 0EA2h
0x180040d98  mov     [rsp+88h+var_60], rdi
0x180040d9d  mov     dword ptr [rsp+88h+var_68], esi
0x180040da1  call    WPP_SF_sDsd
0x180040da6  mov     eax, ebx
0x180040da8  add     rsp, 58h
0x180040dac  pop     r14
0x180040dae  pop     r12
0x180040db0  pop     rdi
0x180040db1  pop     rsi
0x180040db2  pop     rbp
0x180040db3  pop     rbx
0x180040db4  retn
```
