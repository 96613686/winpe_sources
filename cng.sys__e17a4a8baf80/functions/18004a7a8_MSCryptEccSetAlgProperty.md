# MSCryptEccSetAlgProperty

- ea: `0x18004a7a8`
- end: `0x18004a913`
- name: `MSCryptEccSetAlgProperty`
- size: `363`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18004a668`

## callees

- `0x18001155c`
- `0x1800123d0`
- `0x180047434`
- `0x18004a7a8`
- `0x18004a91c`
- `0x18004af70`
- `0x180081764`
- `0x1800a4232`

## string_xrefs

- `0x18004a847`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x18004a89e`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800a8c75`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

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
0x18004a7a8  push    rbp
0x18004a7aa  push    rbx
0x18004a7ab  push    rsi
0x18004a7ac  push    rdi
0x18004a7ad  push    r14
0x18004a7af  push    r15
0x18004a7b1  mov     rbp, rsp
0x18004a7b4  sub     rsp, 68h
0x18004a7b8  mov     r14d, r9d
0x18004a7bb  mov     [rbp+var_20], 0
0x18004a7c3  mov     r15, r8
0x18004a7c6  mov     [rbp+var_28], 0
0x18004a7cd  mov     r8d, [rbp+arg_20]
0x18004a7d1  lea     rax, [rbp+var_20]
0x18004a7d5  mov     rdi, rdx
0x18004a7d8  mov     [rsp+68h+var_48], rax
0x18004a7dd  lea     r9, [rbp+var_28]
0x18004a7e1  xor     edx, edx
0x18004a7e3  call    ValidateEccAlgorithm
0x18004a7e8  mov     ebx, eax
0x18004a7ea  test    eax, eax
0x18004a7ec  js      loc_18004A87B
0x18004a7f2  lea     rdx, aEccparameters; "ECCParameters"
0x18004a7f9  mov     rcx, rdi; Str1
0x18004a7fc  call    wcscmp_0
0x18004a801  test    eax, eax
0x18004a803  jz      loc_18004A8B0
0x18004a809  lea     rdx, aEcccurvename; "ECCCurveName"
0x18004a810  mov     rcx, rdi; Str1
0x18004a813  call    wcscmp_0
0x18004a818  test    eax, eax
0x18004a81a  jz      loc_18004A8CD
0x18004a820  mov     ebx, 0C00000BBh
0x18004a825  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a82c  lea     rax, WPP_GLOBAL_Control
0x18004a833  cmp     rcx, rax
0x18004a836  jz      short loc_18004A86B
0x18004a838  mov     eax, [rcx+2Ch]
0x18004a83b  test    al, 1
0x18004a83d  jz      short loc_18004A86B
0x18004a83f  mov     [rsp+68h+var_38], 0F59h
0x18004a847  lea     rax, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004a84e  mov     [rsp+68h+var_40], rax
0x18004a853  mov     dword ptr [rsp+68h+var_48], 0C00000BBh
0x18004a85b  mov     rcx, [rcx+18h]
0x18004a85f  lea     r9, aStatus; "Status"
0x18004a866  call    WPP_SF_sDsd
0x18004a86b  mov     eax, ebx
0x18004a86d  add     rsp, 68h
0x18004a871  pop     r15
0x18004a873  pop     r14
0x18004a875  pop     rdi
0x18004a876  pop     rsi
0x18004a877  pop     rbx
0x18004a878  pop     rbp
0x18004a879  retn
0x18004a87b  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a882  lea     rax, WPP_GLOBAL_Control
0x18004a889  cmp     rcx, rax
0x18004a88c  jz      short loc_18004A86B
0x18004a88e  mov     edx, [rcx+2Ch]
0x18004a891  test    dl, 1
0x18004a894  jz      short loc_18004A86B
0x18004a896  mov     [rsp+68h+var_38], 0F1Dh
0x18004a89e  lea     rax, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004a8a5  mov     [rsp+68h+var_40], rax
0x18004a8aa  mov     dword ptr [rsp+68h+var_48], ebx
0x18004a8ae  jmp     short loc_18004A85B
0x18004a8b0  mov     rdx, [rbp+var_20]
0x18004a8b4  lea     rcx, [rdx+10h]
0x18004a8b8  cmp     qword ptr [rcx], 0
0x18004a8bc  jz      loc_1800A8C87
0x18004a8c2  mov     r9d, 0F2Bh
0x18004a8c8  jmp     loc_1800A8C5A
0x18004a8cd  mov     rdi, [rbp+var_20]
0x18004a8d1  mov     [rbp+var_18], 0
0x18004a8d9  mov     [rbp+var_28], 0
0x18004a8e0  cmp     qword ptr [rdi+10h], 0
0x18004a8e5  jnz     loc_1800A8C54
0x18004a8eb  lea     r9, [rbp+var_28]
0x18004a8ef  mov     edx, r14d
0x18004a8f2  lea     r8, [rbp+var_18]
0x18004a8f6  mov     rcx, r15
0x18004a8f9  call    ValidateCurveName
0x18004a8fe  mov     ebx, eax
0x18004a900  test    eax, eax
0x18004a902  jns     loc_1800A8CB2
0x18004a908  mov     r9d, 0F4Bh
0x18004a90e  jmp     loc_1800A8C6C
0x1800a8c54  mov     r9d, 0F43h
0x1800a8c5a  mov     ebx, 0C00000BBh
0x1800a8c5f  mov     ecx, 0C00000BBh
0x1800a8c64  jmp     short loc_1800A8C6E
0x1800a8c66  mov     r9d, 0F32h
0x1800a8c6c  mov     ecx, eax
0x1800a8c6e  lea     rdx, aStatus; "Status"
0x1800a8c75  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a8c7c  call    DebugTraceError
0x1800a8c81  nop
0x1800a8c82  jmp     loc_18004A86B
0x1800a8c87  mov     edx, [rdx+8]
0x1800a8c8a  mov     r9d, r14d
0x1800a8c8d  mov     dword ptr [rsp+68h+var_40], 0
0x1800a8c95  mov     r8, r15
0x1800a8c98  mov     [rsp+68h+var_48], 0
0x1800a8ca1  call    AssignGenericDomainParameters
0x1800a8ca6  mov     ebx, eax
0x1800a8ca8  test    eax, eax
0x1800a8caa  jns     loc_18004A86B
0x1800a8cb0  jmp     short loc_1800A8C66
0x1800a8cb2  mov     r9d, [rbp+var_28]
0x1800a8cb6  lea     rcx, [rdi+10h]
0x1800a8cba  mov     r8, [rbp+var_18]
0x1800a8cbe  mov     edx, [rdi+8]
0x1800a8cc1  call    LoadCurve
0x1800a8cc6  mov     ebx, eax
0x1800a8cc8  test    eax, eax
0x1800a8cca  jns     loc_18004A86B
0x1800a8cd0  mov     r9d, 0F52h
0x1800a8cd6  jmp     short loc_1800A8C6C
```
