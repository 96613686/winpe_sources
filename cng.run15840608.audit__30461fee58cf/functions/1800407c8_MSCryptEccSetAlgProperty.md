# MSCryptEccSetAlgProperty

- ea: `0x1800407c8`
- end: `0x180040933`
- name: `MSCryptEccSetAlgProperty`
- size: `363`
- prototype: `__int64 __fastcall(_DWORD *, const wchar_t *, __int64, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180040688`

## callees

- `0x18000743c`
- `0x1800082b0`
- `0x18003d474`
- `0x1800407c8`
- `0x18004093c`
- `0x180040f90`
- `0x1800775c4`
- `0x18009d746`

## string_xrefs

- `0x180040867`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800408be`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800a1ed7`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall MSCryptEccSetAlgProperty(
        _DWORD *a1,
        const wchar_t *a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5)
{
  unsigned int v8; // ebx
  int v9; // r8d
  int v10; // edx
  int v11; // r8d
  int v13; // edx
  __int64 v14; // r9
  __int64 v15; // rdi
  int Curve; // eax
  __int64 v17; // rcx
  unsigned int v18; // [rsp+40h] [rbp-28h] BYREF
  __int64 v19; // [rsp+48h] [rbp-20h] BYREF
  _QWORD v20[3]; // [rsp+50h] [rbp-18h] BYREF

  v19 = 0;
  v18 = 0;
  v8 = ValidateEccAlgorithm(a1, 0, a5, &v18, &v19);
  if ( (v8 & 0x80000000) == 0 )
  {
    if ( !wcscmp_0(a2, L"ECCParameters") )
    {
      if ( !*(_QWORD *)(v19 + 16) )
      {
        Curve = AssignGenericDomainParameters((int)v19 + 16, *(_DWORD *)(v19 + 8), a3, a4, 0, 0);
        v8 = Curve;
        if ( Curve >= 0 )
          return v8;
        v14 = 3890;
        goto LABEL_18;
      }
      v14 = 3883;
    }
    else
    {
      if ( wcscmp_0(a2, L"ECCCurveName") )
      {
        v8 = -1073741637;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            v10,
            v11,
            (unsigned int)"Status",
            187,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
            89);
        return v8;
      }
      v15 = v19;
      v20[0] = 0;
      v18 = 0;
      if ( !*(_QWORD *)(v19 + 16) )
      {
        Curve = ValidateCurveName(a3, a4, v20, &v18);
        v8 = Curve;
        if ( Curve >= 0 )
        {
          Curve = LoadCurve(v15 + 16, *(unsigned int *)(v15 + 8), v20[0], v18);
          v8 = Curve;
          if ( Curve >= 0 )
            return v8;
          v14 = 3922;
        }
        else
        {
          v14 = 3915;
        }
LABEL_18:
        v17 = (unsigned int)Curve;
        goto LABEL_19;
      }
      v14 = 3907;
    }
    v8 = -1073741637;
    v17 = 3221225659LL;
LABEL_19:
    DebugTraceError(v17, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", v14);
    return v8;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    v13 = *((_DWORD *)WPP_GLOBAL_Control + 11);
    if ( (v13 & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v13,
        v9,
        (unsigned int)"Status",
        v8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        29);
  }
  return v8;
}

```

## disassembly

```asm
0x1800407c8  push    rbp
0x1800407ca  push    rbx
0x1800407cb  push    rsi
0x1800407cc  push    rdi
0x1800407cd  push    r14
0x1800407cf  push    r15
0x1800407d1  mov     rbp, rsp
0x1800407d4  sub     rsp, 68h
0x1800407d8  mov     r14d, r9d
0x1800407db  mov     [rbp+var_20], 0
0x1800407e3  mov     r15, r8
0x1800407e6  mov     [rbp+var_28], 0
0x1800407ed  mov     r8d, [rbp+arg_20]
0x1800407f1  lea     rax, [rbp+var_20]
0x1800407f5  mov     rdi, rdx
0x1800407f8  mov     [rsp+68h+var_48], rax
0x1800407fd  lea     r9, [rbp+var_28]
0x180040801  xor     edx, edx
0x180040803  call    ValidateEccAlgorithm
0x180040808  mov     ebx, eax
0x18004080a  test    eax, eax
0x18004080c  js      loc_18004089B
0x180040812  lea     rdx, aEccparameters; "ECCParameters"
0x180040819  mov     rcx, rdi; Str1
0x18004081c  call    wcscmp_0
0x180040821  test    eax, eax
0x180040823  jz      loc_1800408D0
0x180040829  lea     rdx, aEcccurvename; "ECCCurveName"
0x180040830  mov     rcx, rdi; Str1
0x180040833  call    wcscmp_0
0x180040838  test    eax, eax
0x18004083a  jz      loc_1800408ED
0x180040840  mov     ebx, 0C00000BBh
0x180040845  mov     rcx, cs:WPP_GLOBAL_Control
0x18004084c  lea     rax, WPP_GLOBAL_Control
0x180040853  cmp     rcx, rax
0x180040856  jz      short loc_18004088B
0x180040858  mov     eax, [rcx+2Ch]
0x18004085b  test    al, 1
0x18004085d  jz      short loc_18004088B
0x18004085f  mov     [rsp+68h+var_38], 0F59h
0x180040867  lea     rax, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004086e  mov     [rsp+68h+var_40], rax
0x180040873  mov     dword ptr [rsp+68h+var_48], 0C00000BBh
0x18004087b  mov     rcx, [rcx+18h]
0x18004087f  lea     r9, aStatus; "Status"
0x180040886  call    WPP_SF_sDsd
0x18004088b  mov     eax, ebx
0x18004088d  add     rsp, 68h
0x180040891  pop     r15
0x180040893  pop     r14
0x180040895  pop     rdi
0x180040896  pop     rsi
0x180040897  pop     rbx
0x180040898  pop     rbp
0x180040899  retn
0x18004089b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800408a2  lea     rax, WPP_GLOBAL_Control
0x1800408a9  cmp     rcx, rax
0x1800408ac  jz      short loc_18004088B
0x1800408ae  mov     edx, [rcx+2Ch]
0x1800408b1  test    dl, 1
0x1800408b4  jz      short loc_18004088B
0x1800408b6  mov     [rsp+68h+var_38], 0F1Dh
0x1800408be  lea     rax, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800408c5  mov     [rsp+68h+var_40], rax
0x1800408ca  mov     dword ptr [rsp+68h+var_48], ebx
0x1800408ce  jmp     short loc_18004087B
0x1800408d0  mov     rdx, [rbp+var_20]
0x1800408d4  lea     rcx, [rdx+10h]
0x1800408d8  cmp     qword ptr [rcx], 0
0x1800408dc  jz      loc_1800A1EE9
0x1800408e2  mov     r9d, 0F2Bh
0x1800408e8  jmp     loc_1800A1EBC
0x1800408ed  mov     rdi, [rbp+var_20]
0x1800408f1  mov     [rbp+var_18], 0
0x1800408f9  mov     [rbp+var_28], 0
0x180040900  cmp     qword ptr [rdi+10h], 0
0x180040905  jnz     loc_1800A1EB6
0x18004090b  lea     r9, [rbp+var_28]
0x18004090f  mov     edx, r14d
0x180040912  lea     r8, [rbp+var_18]
0x180040916  mov     rcx, r15
0x180040919  call    ValidateCurveName
0x18004091e  mov     ebx, eax
0x180040920  test    eax, eax
0x180040922  jns     loc_1800A1F14
0x180040928  mov     r9d, 0F4Bh
0x18004092e  jmp     loc_1800A1ECE
0x1800a1eb6  mov     r9d, 0F43h
0x1800a1ebc  mov     ebx, 0C00000BBh
0x1800a1ec1  mov     ecx, 0C00000BBh
0x1800a1ec6  jmp     short loc_1800A1ED0
0x1800a1ec8  mov     r9d, 0F32h
0x1800a1ece  mov     ecx, eax
0x1800a1ed0  lea     rdx, aStatus; "Status"
0x1800a1ed7  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a1ede  call    DebugTraceError
0x1800a1ee3  nop
0x1800a1ee4  jmp     loc_18004088B
0x1800a1ee9  mov     edx, [rdx+8]
0x1800a1eec  mov     r9d, r14d
0x1800a1eef  mov     dword ptr [rsp+68h+var_40], 0
0x1800a1ef7  mov     r8, r15
0x1800a1efa  mov     [rsp+68h+var_48], 0
0x1800a1f03  call    AssignGenericDomainParameters
0x1800a1f08  mov     ebx, eax
0x1800a1f0a  test    eax, eax
0x1800a1f0c  jns     loc_18004088B
0x1800a1f12  jmp     short loc_1800A1EC8
0x1800a1f14  mov     r9d, [rbp+var_28]
0x1800a1f18  lea     rcx, [rdi+10h]
0x1800a1f1c  mov     r8, [rbp+var_18]
0x1800a1f20  mov     edx, [rdi+8]
0x1800a1f23  call    LoadCurve
0x1800a1f28  mov     ebx, eax
0x1800a1f2a  test    eax, eax
0x1800a1f2c  jns     loc_18004088B
0x1800a1f32  mov     r9d, 0F52h
0x1800a1f38  jmp     short loc_1800A1ECE
```
