# MSCryptEccSetAlgProperty

- ea: `0x180041358`
- end: `0x1800414c3`
- name: `MSCryptEccSetAlgProperty`
- size: `363`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180041218`

## callees

- `0x18000743c`
- `0x1800082b0`
- `0x18003e004`
- `0x180041358`
- `0x1800414cc`
- `0x180041b20`
- `0x180077fd4`
- `0x18009f616`

## string_xrefs

- `0x1800413f7`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x18004144e`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800a3d07`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall MSCryptEccSetAlgProperty(int a1, const wchar_t *a2, __int64 a3, unsigned int a4, int a5)
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
  v8 = ValidateEccAlgorithm(a1, 0, a5, (unsigned int)&v18, (__int64)&v19);
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
0x180041358  push    rbp
0x18004135a  push    rbx
0x18004135b  push    rsi
0x18004135c  push    rdi
0x18004135d  push    r14
0x18004135f  push    r15
0x180041361  mov     rbp, rsp
0x180041364  sub     rsp, 68h
0x180041368  mov     r14d, r9d
0x18004136b  mov     [rbp+var_20], 0
0x180041373  mov     r15, r8
0x180041376  mov     [rbp+var_28], 0
0x18004137d  mov     r8d, [rbp+arg_20]
0x180041381  lea     rax, [rbp+var_20]
0x180041385  mov     rdi, rdx
0x180041388  mov     [rsp+68h+var_48], rax
0x18004138d  lea     r9, [rbp+var_28]
0x180041391  xor     edx, edx
0x180041393  call    ValidateEccAlgorithm
0x180041398  mov     ebx, eax
0x18004139a  test    eax, eax
0x18004139c  js      loc_18004142B
0x1800413a2  lea     rdx, aEccparameters; "ECCParameters"
0x1800413a9  mov     rcx, rdi; Str1
0x1800413ac  call    wcscmp_0
0x1800413b1  test    eax, eax
0x1800413b3  jz      loc_180041460
0x1800413b9  lea     rdx, aEcccurvename; "ECCCurveName"
0x1800413c0  mov     rcx, rdi; Str1
0x1800413c3  call    wcscmp_0
0x1800413c8  test    eax, eax
0x1800413ca  jz      loc_18004147D
0x1800413d0  mov     ebx, 0C00000BBh
0x1800413d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800413dc  lea     rax, WPP_GLOBAL_Control
0x1800413e3  cmp     rcx, rax
0x1800413e6  jz      short loc_18004141B
0x1800413e8  mov     eax, [rcx+2Ch]
0x1800413eb  test    al, 1
0x1800413ed  jz      short loc_18004141B
0x1800413ef  mov     [rsp+68h+var_38], 0F59h
0x1800413f7  lea     rax, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800413fe  mov     [rsp+68h+var_40], rax
0x180041403  mov     dword ptr [rsp+68h+var_48], 0C00000BBh
0x18004140b  mov     rcx, [rcx+18h]
0x18004140f  lea     r9, aStatus; "Status"
0x180041416  call    WPP_SF_sDsd
0x18004141b  mov     eax, ebx
0x18004141d  add     rsp, 68h
0x180041421  pop     r15
0x180041423  pop     r14
0x180041425  pop     rdi
0x180041426  pop     rsi
0x180041427  pop     rbx
0x180041428  pop     rbp
0x180041429  retn
0x18004142b  mov     rcx, cs:WPP_GLOBAL_Control
0x180041432  lea     rax, WPP_GLOBAL_Control
0x180041439  cmp     rcx, rax
0x18004143c  jz      short loc_18004141B
0x18004143e  mov     edx, [rcx+2Ch]
0x180041441  test    dl, 1
0x180041444  jz      short loc_18004141B
0x180041446  mov     [rsp+68h+var_38], 0F1Dh
0x18004144e  lea     rax, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180041455  mov     [rsp+68h+var_40], rax
0x18004145a  mov     dword ptr [rsp+68h+var_48], ebx
0x18004145e  jmp     short loc_18004140B
0x180041460  mov     rdx, [rbp+var_20]
0x180041464  lea     rcx, [rdx+10h]
0x180041468  cmp     qword ptr [rcx], 0
0x18004146c  jz      loc_1800A3D19
0x180041472  mov     r9d, 0F2Bh
0x180041478  jmp     loc_1800A3CEC
0x18004147d  mov     rdi, [rbp+var_20]
0x180041481  mov     [rbp+var_18], 0
0x180041489  mov     [rbp+var_28], 0
0x180041490  cmp     qword ptr [rdi+10h], 0
0x180041495  jnz     loc_1800A3CE6
0x18004149b  lea     r9, [rbp+var_28]
0x18004149f  mov     edx, r14d
0x1800414a2  lea     r8, [rbp+var_18]
0x1800414a6  mov     rcx, r15
0x1800414a9  call    ValidateCurveName
0x1800414ae  mov     ebx, eax
0x1800414b0  test    eax, eax
0x1800414b2  jns     loc_1800A3D44
0x1800414b8  mov     r9d, 0F4Bh
0x1800414be  jmp     loc_1800A3CFE
0x1800a3ce6  mov     r9d, 0F43h
0x1800a3cec  mov     ebx, 0C00000BBh
0x1800a3cf1  mov     ecx, 0C00000BBh
0x1800a3cf6  jmp     short loc_1800A3D00
0x1800a3cf8  mov     r9d, 0F32h
0x1800a3cfe  mov     ecx, eax
0x1800a3d00  lea     rdx, aStatus; "Status"
0x1800a3d07  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a3d0e  call    DebugTraceError
0x1800a3d13  nop
0x1800a3d14  jmp     loc_18004141B
0x1800a3d19  mov     edx, [rdx+8]
0x1800a3d1c  mov     r9d, r14d
0x1800a3d1f  mov     dword ptr [rsp+68h+var_40], 0
0x1800a3d27  mov     r8, r15
0x1800a3d2a  mov     [rsp+68h+var_48], 0
0x1800a3d33  call    AssignGenericDomainParameters
0x1800a3d38  mov     ebx, eax
0x1800a3d3a  test    eax, eax
0x1800a3d3c  jns     loc_18004141B
0x1800a3d42  jmp     short loc_1800A3CF8
0x1800a3d44  mov     r9d, [rbp+var_28]
0x1800a3d48  lea     rcx, [rdi+10h]
0x1800a3d4c  mov     r8, [rbp+var_18]
0x1800a3d50  mov     edx, [rdi+8]
0x1800a3d53  call    LoadCurve
0x1800a3d58  mov     ebx, eax
0x1800a3d5a  test    eax, eax
0x1800a3d5c  jns     loc_18004141B
0x1800a3d62  mov     r9d, 0F52h
0x1800a3d68  jmp     short loc_1800A3CFE
```
