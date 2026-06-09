# ApplySignaturePadding

- ea: `0x180068b64`
- end: `0x180068ef8`
- name: `ApplySignaturePadding`
- size: `916`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18005a630`

## callees

- `0x180003c70`
- `0x180003f70`
- `0x180006470`
- `0x18000743c`
- `0x180068390`
- `0x180068438`
- `0x18006874c`
- `0x1800688c4`
- `0x180068b64`

## string_xrefs

- `0x180068bbc`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`
- `0x180068bec`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`
- `0x180068cee`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`
- `0x180068dba`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`
- `0x180068ebc`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`

## pseudocode

```c
__int64 __fastcall ApplySignaturePadding(char a1, _QWORD *a2, __int64 a3, int a4, __int64 a5, int a6)
{
  BCRYPT_HANDLE v6; // rsi
  __int64 v7; // rdi
  __int64 v9; // r9
  unsigned int v10; // ebx
  __int64 v11; // rcx
  int v12; // eax
  NTSTATUS Property; // eax
  __int64 v14; // r9
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  NTSTATUS v19; // eax
  __int64 v20; // r9
  __int64 v21; // rcx
  int v22; // eax
  UCHAR pbOutput[4]; // [rsp+50h] [rbp-10h] BYREF
  UCHAR v25[4]; // [rsp+54h] [rbp-Ch] BYREF
  BCRYPT_HANDLE hObject; // [rsp+58h] [rbp-8h] BYREF
  ULONG cbOutput; // [rsp+90h] [rbp+30h] BYREF

  v6 = 0;
  v7 = 0;
  hObject = 0;
  *(_DWORD *)v25 = 0;
  *(_DWORD *)pbOutput = 0;
  cbOutput = 0;
  if ( (a1 & 2) == 0 )
  {
    if ( (a1 & 8) == 0 )
    {
      v14 = 1504;
      goto LABEL_44;
    }
    if ( !a2 || !*a2 )
    {
      v9 = 1447;
      goto LABEL_4;
    }
    if ( (int)CachedOpenAlgorithmProvider(&hObject) < 0 )
    {
      v10 = -1073741637;
      DebugTraceError(3221225659LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\format.c", 1459);
      goto LABEL_9;
    }
    v6 = hObject;
    Property = BCryptGetProperty(hObject, L"ObjectLength", v25, 4u, &cbOutput, 0);
    v10 = Property;
    if ( Property < 0 )
    {
      v14 = 1471;
      goto LABEL_12;
    }
    Property = BCryptGetProperty(v6, L"HashDigestLength", pbOutput, 4u, &cbOutput, 0);
    v10 = Property;
    if ( Property < 0 )
    {
      v14 = 1483;
      goto LABEL_12;
    }
    Property = ApplyPSSPaddingSalted(v6, *(unsigned int *)pbOutput, *(unsigned int *)v25);
    v10 = Property;
    if ( Property < 0 )
    {
      v14 = 1497;
      goto LABEL_12;
    }
    goto LABEL_40;
  }
  if ( !a2 )
  {
    v9 = 1329;
LABEL_4:
    v10 = -1073741811;
    v11 = 3221225485LL;
LABEL_5:
    DebugTraceError(v11, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\format.c", v9);
    return v10;
  }
  if ( !*a2 )
  {
    v22 = ApplyPKCS1SigningFormat(0, 0, a5, a6, 0);
    v10 = v22;
    if ( v22 < 0 )
    {
      v9 = 1434;
      v11 = (unsigned int)v22;
      goto LABEL_5;
    }
    goto LABEL_40;
  }
  v12 = CachedOpenAlgorithmProvider(&hObject);
  if ( v12 < 0 )
  {
    DebugTraceError((unsigned int)v12, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\format.c", 1342);
    v10 = -1073741637;
LABEL_9:
    v6 = hObject;
    goto LABEL_46;
  }
  v6 = hObject;
  Property = BCryptGetProperty(hObject, L"HashDigestLength", pbOutput, 4u, &cbOutput, 0);
  v10 = Property;
  if ( Property >= 0 )
  {
    if ( *(_DWORD *)pbOutput != a4 )
    {
      v14 = 1361;
LABEL_44:
      v15 = 3221225485LL;
      v10 = -1073741811;
      goto LABEL_45;
    }
    Property = BCryptGetProperty(v6, L"HashOIDList", 0, 0, &cbOutput, 0);
    v10 = Property;
    if ( Property < 0 )
    {
      v14 = 1373;
      goto LABEL_12;
    }
    v7 = MSCryptAlloc(cbOutput, v16, v17, v18);
    if ( !v7 )
    {
      v10 = -1073741801;
      v14 = 1383;
      v15 = 3221225495LL;
      goto LABEL_45;
    }
    v19 = BCryptGetProperty(v6, L"HashOIDList", (PUCHAR)v7, cbOutput, &cbOutput, 0);
    v10 = v19;
    if ( v19 < 0 )
    {
      v20 = 1395;
LABEL_21:
      v21 = (unsigned int)v19;
LABEL_22:
      DebugTraceError(v21, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\format.c", v20);
LABEL_41:
      MSCryptFree((PVOID)v7);
      goto LABEL_46;
    }
    if ( !*(_DWORD *)v7 )
    {
      v10 = -1073741595;
      v20 = 1404;
      v21 = 3221225701LL;
      goto LABEL_22;
    }
    v19 = ApplyPKCS1SigningFormat(*(void **)(*(_QWORD *)(v7 + 8) + 8LL), **(unsigned int **)(v7 + 8), a5, a6, 1);
    v10 = v19;
    if ( v19 < 0 )
    {
      v20 = 1418;
      goto LABEL_21;
    }
LABEL_40:
    v10 = 0;
    if ( !v7 )
      goto LABEL_46;
    goto LABEL_41;
  }
  v14 = 1355;
LABEL_12:
  v15 = (unsigned int)Property;
LABEL_45:
  DebugTraceError(v15, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\format.c", v14);
LABEL_46:
  if ( v6 )
    CachedCloseAlgorithmProvider(v6);
  return v10;
}

```

## disassembly

```asm
0x180068b64  mov     [rsp-28h+arg_8], rbx
0x180068b69  mov     [rsp-28h+arg_10], rsi
0x180068b6e  push    rbp
0x180068b6f  push    rdi
0x180068b70  push    r12
0x180068b72  push    r14
0x180068b74  push    r15
0x180068b76  mov     rbp, rsp
0x180068b79  sub     rsp, 60h
0x180068b7d  xor     esi, esi
0x180068b7f  xor     edi, edi
0x180068b81  mov     [rbp+hObject], rsi
0x180068b85  mov     r15d, r9d
0x180068b88  mov     dword ptr [rbp+var_C], esi
0x180068b8b  mov     r12, r8
0x180068b8e  mov     dword ptr [rbp+pbOutput], esi
0x180068b91  mov     r14, rdx
0x180068b94  mov     [rbp+cbOutput], esi
0x180068b97  test    cl, 2
0x180068b9a  jz      loc_180068D89
0x180068ba0  test    rdx, rdx
0x180068ba3  jnz     short loc_180068BCD
0x180068ba5  mov     r9d, 531h
0x180068bab  mov     ebx, 0C000000Dh
0x180068bb0  mov     ecx, 0C000000Dh
0x180068bb5  lea     rdx, aStatus; "Status"
0x180068bbc  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180068bc3  call    DebugTraceError
0x180068bc8  jmp     loc_180068EDC
0x180068bcd  mov     rdx, [rdx]
0x180068bd0  test    rdx, rdx
0x180068bd3  jz      loc_180068D55
0x180068bd9  lea     rcx, [rbp+hObject]
0x180068bdd  call    CachedOpenAlgorithmProvider
0x180068be2  test    eax, eax
0x180068be4  jns     short loc_180068C0F
0x180068be6  mov     r9d, 53Eh
0x180068bec  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180068bf3  lea     rdx, aStatus; "Status"
0x180068bfa  mov     ecx, eax
0x180068bfc  call    DebugTraceError
0x180068c01  mov     ebx, 0C00000BBh
0x180068c06  mov     rsi, [rbp+hObject]
0x180068c0a  jmp     loc_180068ECF
0x180068c0f  mov     [rsp+60h+dwFlags], esi; dwFlags
0x180068c13  lea     rax, [rbp+cbOutput]
0x180068c17  mov     rsi, [rbp+hObject]
0x180068c1b  lea     r8, [rbp+pbOutput]; pbOutput
0x180068c1f  mov     rcx, rsi; hObject
0x180068c22  mov     [rsp+60h+pcbResult], rax; pcbResult
0x180068c27  mov     r9d, 4; cbOutput
0x180068c2d  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180068c34  call    BCryptGetProperty
0x180068c39  mov     ebx, eax
0x180068c3b  test    eax, eax
0x180068c3d  jns     short loc_180068C4C
0x180068c3f  mov     r9d, 54Bh
0x180068c45  mov     ecx, eax
0x180068c47  jmp     loc_180068EBC
0x180068c4c  cmp     dword ptr [rbp+pbOutput], r15d
0x180068c50  jz      short loc_180068C5D
0x180068c52  mov     r9d, 551h
0x180068c58  jmp     loc_180068EB2
0x180068c5d  lea     rax, [rbp+cbOutput]
0x180068c61  mov     [rsp+60h+dwFlags], edi; dwFlags
0x180068c65  xor     r9d, r9d; cbOutput
0x180068c68  mov     [rsp+60h+pcbResult], rax; pcbResult
0x180068c6d  xor     r8d, r8d; pbOutput
0x180068c70  lea     rdx, aHashoidlist; "HashOIDList"
0x180068c77  mov     rcx, rsi; hObject
0x180068c7a  call    BCryptGetProperty
0x180068c7f  mov     ebx, eax
0x180068c81  test    eax, eax
0x180068c83  jns     short loc_180068C8D
0x180068c85  mov     r9d, 55Dh
0x180068c8b  jmp     short loc_180068C45
0x180068c8d  mov     ecx, [rbp+cbOutput]
0x180068c90  call    MSCryptAlloc
0x180068c95  mov     rdi, rax
0x180068c98  test    rax, rax
0x180068c9b  jnz     short loc_180068CB2
0x180068c9d  mov     ebx, 0C0000017h
0x180068ca2  mov     r9d, 567h
0x180068ca8  mov     ecx, 0C0000017h
0x180068cad  jmp     loc_180068EBC
0x180068cb2  mov     r9d, [rbp+cbOutput]; cbOutput
0x180068cb6  lea     rax, [rbp+cbOutput]
0x180068cba  mov     [rsp+60h+dwFlags], 0; dwFlags
0x180068cc2  lea     rdx, aHashoidlist; "HashOIDList"
0x180068cc9  mov     r8, rdi; pbOutput
0x180068ccc  mov     [rsp+60h+pcbResult], rax; pcbResult
0x180068cd1  mov     rcx, rsi; hObject
0x180068cd4  call    BCryptGetProperty
0x180068cd9  mov     ebx, eax
0x180068cdb  test    eax, eax
0x180068cdd  jns     short loc_180068CFF
0x180068cdf  mov     r9d, 573h
0x180068ce5  mov     ecx, eax
0x180068ce7  lea     rdx, aStatus; "Status"
0x180068cee  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180068cf5  call    DebugTraceError
0x180068cfa  jmp     loc_180068E97
0x180068cff  cmp     dword ptr [rdi], 0
0x180068d02  jnz     short loc_180068D16
0x180068d04  mov     ebx, 0C00000E5h
0x180068d09  mov     r9d, 57Ch
0x180068d0f  mov     ecx, 0C00000E5h
0x180068d14  jmp     short loc_180068CE7
0x180068d16  mov     rcx, [rdi+8]
0x180068d1a  mov     r9d, r15d
0x180068d1d  mov     eax, [rbp+arg_28]
0x180068d20  mov     r8, r12
0x180068d23  mov     [rsp+60h+var_30], 1; int
0x180068d2b  mov     [rsp+60h+dwFlags], eax; int
0x180068d2f  mov     edx, [rcx]; Size
0x180068d31  mov     rax, [rbp+arg_20]
0x180068d35  mov     rcx, [rcx+8]; Src
0x180068d39  mov     [rsp+60h+pcbResult], rax; __int64
0x180068d3e  call    ApplyPKCS1SigningFormat
0x180068d43  mov     ebx, eax
0x180068d45  test    eax, eax
0x180068d47  jns     loc_180068E90
0x180068d4d  mov     r9d, 58Ah
0x180068d53  jmp     short loc_180068CE5
0x180068d55  mov     eax, [rbp+arg_28]
0x180068d58  xor     edx, edx; Size
0x180068d5a  mov     [rsp+60h+var_30], esi; int
0x180068d5e  xor     ecx, ecx; Src
0x180068d60  mov     [rsp+60h+dwFlags], eax; int
0x180068d64  mov     rax, [rbp+arg_20]
0x180068d68  mov     [rsp+60h+pcbResult], rax; __int64
0x180068d6d  call    ApplyPKCS1SigningFormat
0x180068d72  mov     ebx, eax
0x180068d74  test    eax, eax
0x180068d76  jns     loc_180068E90
0x180068d7c  mov     r9d, 59Ah
0x180068d82  mov     ecx, eax
0x180068d84  jmp     loc_180068BB5
0x180068d89  test    cl, 8
0x180068d8c  jz      loc_180068EAC
0x180068d92  test    r14, r14
0x180068d95  jz      loc_180068EA1
0x180068d9b  mov     rdx, [rdx]
0x180068d9e  test    rdx, rdx
0x180068da1  jz      loc_180068EA1
0x180068da7  lea     rcx, [rbp+hObject]
0x180068dab  call    CachedOpenAlgorithmProvider
0x180068db0  test    eax, eax
0x180068db2  jns     short loc_180068DDC
0x180068db4  mov     r9d, 5B3h
0x180068dba  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180068dc1  lea     rdx, aStatus; "Status"
0x180068dc8  mov     ecx, 0C00000BBh
0x180068dcd  mov     ebx, 0C00000BBh
0x180068dd2  call    DebugTraceError
0x180068dd7  jmp     loc_180068C06
0x180068ddc  mov     [rsp+60h+dwFlags], esi; dwFlags
0x180068de0  lea     rax, [rbp+cbOutput]
0x180068de4  mov     rsi, [rbp+hObject]
0x180068de8  lea     r8, [rbp+var_C]; pbOutput
0x180068dec  mov     rcx, rsi; hObject
0x180068def  mov     [rsp+60h+pcbResult], rax; pcbResult
0x180068df4  mov     r9d, 4; cbOutput
0x180068dfa  lea     rdx, aObjectlength; "ObjectLength"
0x180068e01  call    BCryptGetProperty
0x180068e06  mov     ebx, eax
0x180068e08  test    eax, eax
0x180068e0a  jns     short loc_180068E17
0x180068e0c  mov     r9d, 5BFh
0x180068e12  jmp     loc_180068C45
0x180068e17  lea     rax, [rbp+cbOutput]
0x180068e1b  mov     [rsp+60h+dwFlags], edi; dwFlags
0x180068e1f  mov     r9d, 4; cbOutput
0x180068e25  mov     [rsp+60h+pcbResult], rax; pcbResult
0x180068e2a  lea     r8, [rbp+pbOutput]; pbOutput
0x180068e2e  mov     rcx, rsi; hObject
0x180068e31  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180068e38  call    BCryptGetProperty
0x180068e3d  mov     ebx, eax
0x180068e3f  test    eax, eax
0x180068e41  jns     short loc_180068E4E
0x180068e43  mov     r9d, 5CBh
0x180068e49  jmp     loc_180068C45
0x180068e4e  mov     eax, [rbp+arg_28]
0x180068e51  mov     rcx, rsi
0x180068e54  mov     r8d, dword ptr [rbp+var_C]
0x180068e58  mov     edx, dword ptr [rbp+pbOutput]
0x180068e5b  mov     [rsp+60h+var_20], eax
0x180068e5f  mov     rax, [rbp+arg_20]
0x180068e63  mov     [rsp+60h+var_28], rax
0x180068e68  mov     eax, [r14+8]
0x180068e6c  mov     [rsp+60h+var_30], r15d
0x180068e71  mov     qword ptr [rsp+60h+dwFlags], r12
0x180068e76  mov     dword ptr [rsp+60h+pcbResult], eax
0x180068e7a  call    ApplyPSSPaddingSalted
0x180068e7f  mov     ebx, eax
0x180068e81  test    eax, eax
0x180068e83  jns     short loc_180068E90
0x180068e85  mov     r9d, 5D9h
0x180068e8b  jmp     loc_180068C45
0x180068e90  xor     ebx, ebx
0x180068e92  test    rdi, rdi
0x180068e95  jz      short loc_180068ECF
0x180068e97  mov     rcx, rdi; P
0x180068e9a  call    MSCryptFree
0x180068e9f  jmp     short loc_180068ECF
0x180068ea1  mov     r9d, 5A7h
0x180068ea7  jmp     loc_180068BAB
0x180068eac  mov     r9d, 5E0h
0x180068eb2  mov     ecx, 0C000000Dh
0x180068eb7  mov     ebx, 0C000000Dh
0x180068ebc  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180068ec3  lea     rdx, aStatus; "Status"
0x180068eca  call    DebugTraceError
0x180068ecf  test    rsi, rsi
0x180068ed2  jz      short loc_180068EDC
0x180068ed4  mov     rcx, rsi; hAlgorithm
0x180068ed7  call    CachedCloseAlgorithmProvider
0x180068edc  lea     r11, [rsp+60h+var_s0]
0x180068ee1  mov     eax, ebx
0x180068ee3  mov     rbx, [r11+38h]
0x180068ee7  mov     rsi, [r11+40h]
0x180068eeb  mov     rsp, r11
0x180068eee  pop     r15
0x180068ef0  pop     r14
0x180068ef2  pop     r12
0x180068ef4  pop     rdi
0x180068ef5  pop     rbp
0x180068ef6  retn
```
