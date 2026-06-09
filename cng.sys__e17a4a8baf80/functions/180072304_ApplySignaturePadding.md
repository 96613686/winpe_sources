# ApplySignaturePadding

- ea: `0x180072304`
- end: `0x180072698`
- name: `ApplySignaturePadding`
- size: `916`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180063f10`

## callees

- `0x18000dd90`
- `0x18000e090`
- `0x180010590`
- `0x18001155c`
- `0x180071b30`
- `0x180071bd8`
- `0x180071eec`
- `0x180072064`
- `0x180072304`

## string_xrefs

- `0x18007235c`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`
- `0x18007238c`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`
- `0x18007248e`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`
- `0x18007255a`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`
- `0x18007265c`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`

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
  NTSTATUS v17; // eax
  __int64 v18; // r9
  __int64 v19; // rcx
  int v20; // eax
  UCHAR pbOutput[4]; // [rsp+50h] [rbp-10h] BYREF
  UCHAR v23[4]; // [rsp+54h] [rbp-Ch] BYREF
  BCRYPT_HANDLE hObject; // [rsp+58h] [rbp-8h] BYREF
  ULONG cbOutput; // [rsp+90h] [rbp+30h] BYREF

  v6 = 0;
  v7 = 0;
  hObject = 0;
  *(_DWORD *)v23 = 0;
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
    Property = BCryptGetProperty(hObject, L"ObjectLength", v23, 4u, &cbOutput, 0);
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
    Property = ApplyPSSPaddingSalted(v6, *(unsigned int *)pbOutput, *(unsigned int *)v23);
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
    v20 = ApplyPKCS1SigningFormat(0, 0, a5, a6, 0);
    v10 = v20;
    if ( v20 < 0 )
    {
      v9 = 1434;
      v11 = (unsigned int)v20;
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
    v7 = MSCryptAlloc(cbOutput, v16);
    if ( !v7 )
    {
      v10 = -1073741801;
      v14 = 1383;
      v15 = 3221225495LL;
      goto LABEL_45;
    }
    v17 = BCryptGetProperty(v6, L"HashOIDList", (PUCHAR)v7, cbOutput, &cbOutput, 0);
    v10 = v17;
    if ( v17 < 0 )
    {
      v18 = 1395;
LABEL_21:
      v19 = (unsigned int)v17;
LABEL_22:
      DebugTraceError(v19, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\format.c", v18);
LABEL_41:
      MSCryptFree((PVOID)v7);
      goto LABEL_46;
    }
    if ( !*(_DWORD *)v7 )
    {
      v10 = -1073741595;
      v18 = 1404;
      v19 = 3221225701LL;
      goto LABEL_22;
    }
    v17 = ApplyPKCS1SigningFormat(*(void **)(*(_QWORD *)(v7 + 8) + 8LL), **(unsigned int **)(v7 + 8), a5, a6, 1);
    v10 = v17;
    if ( v17 < 0 )
    {
      v18 = 1418;
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
0x180072304  mov     [rsp-28h+arg_8], rbx
0x180072309  mov     [rsp-28h+arg_10], rsi
0x18007230e  push    rbp
0x18007230f  push    rdi
0x180072310  push    r12
0x180072312  push    r14
0x180072314  push    r15
0x180072316  mov     rbp, rsp
0x180072319  sub     rsp, 60h
0x18007231d  xor     esi, esi
0x18007231f  xor     edi, edi
0x180072321  mov     [rbp+hObject], rsi
0x180072325  mov     r15d, r9d
0x180072328  mov     dword ptr [rbp+var_C], esi
0x18007232b  mov     r12, r8
0x18007232e  mov     dword ptr [rbp+pbOutput], esi
0x180072331  mov     r14, rdx
0x180072334  mov     [rbp+cbOutput], esi
0x180072337  test    cl, 2
0x18007233a  jz      loc_180072529
0x180072340  test    rdx, rdx
0x180072343  jnz     short loc_18007236D
0x180072345  mov     r9d, 531h
0x18007234b  mov     ebx, 0C000000Dh
0x180072350  mov     ecx, 0C000000Dh
0x180072355  lea     rdx, aStatus; "Status"
0x18007235c  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180072363  call    DebugTraceError
0x180072368  jmp     loc_18007267C
0x18007236d  mov     rdx, [rdx]
0x180072370  test    rdx, rdx
0x180072373  jz      loc_1800724F5
0x180072379  lea     rcx, [rbp+hObject]
0x18007237d  call    CachedOpenAlgorithmProvider
0x180072382  test    eax, eax
0x180072384  jns     short loc_1800723AF
0x180072386  mov     r9d, 53Eh
0x18007238c  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180072393  lea     rdx, aStatus; "Status"
0x18007239a  mov     ecx, eax
0x18007239c  call    DebugTraceError
0x1800723a1  mov     ebx, 0C00000BBh
0x1800723a6  mov     rsi, [rbp+hObject]
0x1800723aa  jmp     loc_18007266F
0x1800723af  mov     [rsp+60h+dwFlags], esi; dwFlags
0x1800723b3  lea     rax, [rbp+cbOutput]
0x1800723b7  mov     rsi, [rbp+hObject]
0x1800723bb  lea     r8, [rbp+pbOutput]; pbOutput
0x1800723bf  mov     rcx, rsi; hObject
0x1800723c2  mov     [rsp+60h+pcbResult], rax; pcbResult
0x1800723c7  mov     r9d, 4; cbOutput
0x1800723cd  lea     rdx, aHashdigestleng; "HashDigestLength"
0x1800723d4  call    BCryptGetProperty
0x1800723d9  mov     ebx, eax
0x1800723db  test    eax, eax
0x1800723dd  jns     short loc_1800723EC
0x1800723df  mov     r9d, 54Bh
0x1800723e5  mov     ecx, eax
0x1800723e7  jmp     loc_18007265C
0x1800723ec  cmp     dword ptr [rbp+pbOutput], r15d
0x1800723f0  jz      short loc_1800723FD
0x1800723f2  mov     r9d, 551h
0x1800723f8  jmp     loc_180072652
0x1800723fd  lea     rax, [rbp+cbOutput]
0x180072401  mov     [rsp+60h+dwFlags], edi; dwFlags
0x180072405  xor     r9d, r9d; cbOutput
0x180072408  mov     [rsp+60h+pcbResult], rax; pcbResult
0x18007240d  xor     r8d, r8d; pbOutput
0x180072410  lea     rdx, aHashoidlist; "HashOIDList"
0x180072417  mov     rcx, rsi; hObject
0x18007241a  call    BCryptGetProperty
0x18007241f  mov     ebx, eax
0x180072421  test    eax, eax
0x180072423  jns     short loc_18007242D
0x180072425  mov     r9d, 55Dh
0x18007242b  jmp     short loc_1800723E5
0x18007242d  mov     ecx, [rbp+cbOutput]
0x180072430  call    MSCryptAlloc
0x180072435  mov     rdi, rax
0x180072438  test    rax, rax
0x18007243b  jnz     short loc_180072452
0x18007243d  mov     ebx, 0C0000017h
0x180072442  mov     r9d, 567h
0x180072448  mov     ecx, 0C0000017h
0x18007244d  jmp     loc_18007265C
0x180072452  mov     r9d, [rbp+cbOutput]; cbOutput
0x180072456  lea     rax, [rbp+cbOutput]
0x18007245a  mov     [rsp+60h+dwFlags], 0; dwFlags
0x180072462  lea     rdx, aHashoidlist; "HashOIDList"
0x180072469  mov     r8, rdi; pbOutput
0x18007246c  mov     [rsp+60h+pcbResult], rax; pcbResult
0x180072471  mov     rcx, rsi; hObject
0x180072474  call    BCryptGetProperty
0x180072479  mov     ebx, eax
0x18007247b  test    eax, eax
0x18007247d  jns     short loc_18007249F
0x18007247f  mov     r9d, 573h
0x180072485  mov     ecx, eax
0x180072487  lea     rdx, aStatus; "Status"
0x18007248e  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180072495  call    DebugTraceError
0x18007249a  jmp     loc_180072637
0x18007249f  cmp     dword ptr [rdi], 0
0x1800724a2  jnz     short loc_1800724B6
0x1800724a4  mov     ebx, 0C00000E5h
0x1800724a9  mov     r9d, 57Ch
0x1800724af  mov     ecx, 0C00000E5h
0x1800724b4  jmp     short loc_180072487
0x1800724b6  mov     rcx, [rdi+8]
0x1800724ba  mov     r9d, r15d
0x1800724bd  mov     eax, [rbp+arg_28]
0x1800724c0  mov     r8, r12
0x1800724c3  mov     [rsp+60h+var_30], 1; int
0x1800724cb  mov     [rsp+60h+dwFlags], eax; int
0x1800724cf  mov     edx, [rcx]; Size
0x1800724d1  mov     rax, [rbp+arg_20]
0x1800724d5  mov     rcx, [rcx+8]; Src
0x1800724d9  mov     [rsp+60h+pcbResult], rax; __int64
0x1800724de  call    ApplyPKCS1SigningFormat
0x1800724e3  mov     ebx, eax
0x1800724e5  test    eax, eax
0x1800724e7  jns     loc_180072630
0x1800724ed  mov     r9d, 58Ah
0x1800724f3  jmp     short loc_180072485
0x1800724f5  mov     eax, [rbp+arg_28]
0x1800724f8  xor     edx, edx; Size
0x1800724fa  mov     [rsp+60h+var_30], esi; int
0x1800724fe  xor     ecx, ecx; Src
0x180072500  mov     [rsp+60h+dwFlags], eax; int
0x180072504  mov     rax, [rbp+arg_20]
0x180072508  mov     [rsp+60h+pcbResult], rax; __int64
0x18007250d  call    ApplyPKCS1SigningFormat
0x180072512  mov     ebx, eax
0x180072514  test    eax, eax
0x180072516  jns     loc_180072630
0x18007251c  mov     r9d, 59Ah
0x180072522  mov     ecx, eax
0x180072524  jmp     loc_180072355
0x180072529  test    cl, 8
0x18007252c  jz      loc_18007264C
0x180072532  test    r14, r14
0x180072535  jz      loc_180072641
0x18007253b  mov     rdx, [rdx]
0x18007253e  test    rdx, rdx
0x180072541  jz      loc_180072641
0x180072547  lea     rcx, [rbp+hObject]
0x18007254b  call    CachedOpenAlgorithmProvider
0x180072550  test    eax, eax
0x180072552  jns     short loc_18007257C
0x180072554  mov     r9d, 5B3h
0x18007255a  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180072561  lea     rdx, aStatus; "Status"
0x180072568  mov     ecx, 0C00000BBh
0x18007256d  mov     ebx, 0C00000BBh
0x180072572  call    DebugTraceError
0x180072577  jmp     loc_1800723A6
0x18007257c  mov     [rsp+60h+dwFlags], esi; dwFlags
0x180072580  lea     rax, [rbp+cbOutput]
0x180072584  mov     rsi, [rbp+hObject]
0x180072588  lea     r8, [rbp+var_C]; pbOutput
0x18007258c  mov     rcx, rsi; hObject
0x18007258f  mov     [rsp+60h+pcbResult], rax; pcbResult
0x180072594  mov     r9d, 4; cbOutput
0x18007259a  lea     rdx, aObjectlength; "ObjectLength"
0x1800725a1  call    BCryptGetProperty
0x1800725a6  mov     ebx, eax
0x1800725a8  test    eax, eax
0x1800725aa  jns     short loc_1800725B7
0x1800725ac  mov     r9d, 5BFh
0x1800725b2  jmp     loc_1800723E5
0x1800725b7  lea     rax, [rbp+cbOutput]
0x1800725bb  mov     [rsp+60h+dwFlags], edi; dwFlags
0x1800725bf  mov     r9d, 4; cbOutput
0x1800725c5  mov     [rsp+60h+pcbResult], rax; pcbResult
0x1800725ca  lea     r8, [rbp+pbOutput]; pbOutput
0x1800725ce  mov     rcx, rsi; hObject
0x1800725d1  lea     rdx, aHashdigestleng; "HashDigestLength"
0x1800725d8  call    BCryptGetProperty
0x1800725dd  mov     ebx, eax
0x1800725df  test    eax, eax
0x1800725e1  jns     short loc_1800725EE
0x1800725e3  mov     r9d, 5CBh
0x1800725e9  jmp     loc_1800723E5
0x1800725ee  mov     eax, [rbp+arg_28]
0x1800725f1  mov     rcx, rsi
0x1800725f4  mov     r8d, dword ptr [rbp+var_C]
0x1800725f8  mov     edx, dword ptr [rbp+pbOutput]
0x1800725fb  mov     [rsp+60h+var_20], eax
0x1800725ff  mov     rax, [rbp+arg_20]
0x180072603  mov     [rsp+60h+var_28], rax
0x180072608  mov     eax, [r14+8]
0x18007260c  mov     [rsp+60h+var_30], r15d
0x180072611  mov     qword ptr [rsp+60h+dwFlags], r12
0x180072616  mov     dword ptr [rsp+60h+pcbResult], eax
0x18007261a  call    ApplyPSSPaddingSalted
0x18007261f  mov     ebx, eax
0x180072621  test    eax, eax
0x180072623  jns     short loc_180072630
0x180072625  mov     r9d, 5D9h
0x18007262b  jmp     loc_1800723E5
0x180072630  xor     ebx, ebx
0x180072632  test    rdi, rdi
0x180072635  jz      short loc_18007266F
0x180072637  mov     rcx, rdi; P
0x18007263a  call    MSCryptFree
0x18007263f  jmp     short loc_18007266F
0x180072641  mov     r9d, 5A7h
0x180072647  jmp     loc_18007234B
0x18007264c  mov     r9d, 5E0h
0x180072652  mov     ecx, 0C000000Dh
0x180072657  mov     ebx, 0C000000Dh
0x18007265c  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180072663  lea     rdx, aStatus; "Status"
0x18007266a  call    DebugTraceError
0x18007266f  test    rsi, rsi
0x180072672  jz      short loc_18007267C
0x180072674  mov     rcx, rsi; hAlgorithm
0x180072677  call    CachedCloseAlgorithmProvider
0x18007267c  lea     r11, [rsp+60h+var_s0]
0x180072681  mov     eax, ebx
0x180072683  mov     rbx, [r11+38h]
0x180072687  mov     rsi, [r11+40h]
0x18007268b  mov     rsp, r11
0x18007268e  pop     r15
0x180072690  pop     r14
0x180072692  pop     r12
0x180072694  pop     rdi
0x180072695  pop     rbp
0x180072696  retn
```
