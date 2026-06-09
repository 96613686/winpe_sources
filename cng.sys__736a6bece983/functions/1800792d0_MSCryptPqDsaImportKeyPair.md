# MSCryptPqDsaImportKeyPair

- ea: `0x1800792d0`
- end: `0x1800795c3`
- name: `MSCryptPqDsaImportKeyPair`
- size: `755`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x18000743c`
- `0x180048770`
- `0x1800792d0`
- `0x180079d60`
- `0x180079dc4`
- `0x180079e20`
- `0x180079e8c`
- `0x18007a0e8`
- `0x18008cc54`
- `0x18008cd14`
- `0x18008ced8`
- `0x18008e070`
- `0x18008e0f4`
- `0x18008e2d0`

## string_xrefs

- `0x1800792f7`: `onecore\ds\security\cryptoapi\ncrypt\msprim\pqc-sign\pqdsa.c`
- `0x18007948b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\pqc-sign\pqdsa.c`
- `0x1800794e7`: `onecore\ds\security\cryptoapi\ncrypt\msprim\pqc-sign\pqdsa.c`
- `0x180079584`: `onecore\ds\security\cryptoapi\ncrypt\msprim\pqc-sign\pqdsa.c`

## pseudocode

```c
__int64 __fastcall MSCryptPqDsaImportKeyPair(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 *a4,
        _DWORD *a5,
        unsigned int a6,
        unsigned int a7)
{
  __int64 v8; // r9
  __int64 v9; // rbx
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // r8
  __int64 v13; // rdi
  __int64 PqDsaBlobInfoFromType; // rax
  __int64 v15; // r14
  unsigned int v16; // esi
  unsigned int v17; // ecx
  unsigned int v18; // edx
  __int64 PqDsaParameterSetInfoFromName; // rbp
  __int64 PqDsaKey; // rax
  __int64 v21; // rdi
  unsigned int v22; // r12d
  __int64 v23; // r9
  __int64 v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rsi
  unsigned int v27; // eax
  __int64 v28; // rax
  unsigned int v29; // eax
  __int64 v30; // rcx
  __int64 v31; // r9

  if ( !a1 )
  {
    v8 = 1376;
LABEL_3:
    LODWORD(v9) = -1073741811;
    v10 = 3221225485LL;
LABEL_4:
    DebugTraceError(v10, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\pqc-sign\\pqdsa.c", v8);
    return (unsigned int)v9;
  }
  if ( a2 )
  {
    LODWORD(v9) = -1073741637;
    v8 = 1383;
    v10 = 3221225659LL;
    goto LABEL_4;
  }
  if ( !a3 )
  {
    v8 = 1390;
    goto LABEL_3;
  }
  if ( !a4 )
  {
    v8 = 1397;
    goto LABEL_3;
  }
  if ( a5 && a6 >= 0xC )
  {
    if ( (a7 & 0xFFFFFFF7) != 0 )
    {
      v8 = 1411;
      goto LABEL_3;
    }
    v11 = validatePqDsaAlgorithm();
    if ( !v11 )
    {
      LODWORD(v9) = -1073741816;
      v8 = 1419;
      v10 = 3221225480LL;
      goto LABEL_4;
    }
    v13 = *(_QWORD *)(v11 + 16);
    PqDsaBlobInfoFromType = getPqDsaBlobInfoFromType(v13, v12);
    v15 = PqDsaBlobInfoFromType;
    if ( !PqDsaBlobInfoFromType )
    {
      v8 = 1427;
      goto LABEL_3;
    }
    if ( *a5 != *(_DWORD *)(PqDsaBlobInfoFromType + 16) )
    {
      v8 = 1436;
      goto LABEL_3;
    }
    v16 = a5[1];
    v17 = v16 + 12;
    if ( v16 >= 0xFFFFFFF4 )
    {
      v8 = 1449;
LABEL_23:
      LODWORD(v9) = -1073741675;
      v10 = 3221225621LL;
      goto LABEL_4;
    }
    v18 = v17 + a5[2];
    if ( v18 < v17 )
    {
      v8 = 1456;
      goto LABEL_23;
    }
    if ( a6 < v18 )
    {
      v8 = 1463;
      goto LABEL_3;
    }
    PqDsaParameterSetInfoFromName = getPqDsaParameterSetInfoFromName(v13, a5 + 3, v16);
    if ( !PqDsaParameterSetInfoFromName )
    {
      v8 = 1474;
      goto LABEL_3;
    }
    PqDsaKey = createPqDsaKey(v13, a7);
    v21 = PqDsaKey;
    if ( !PqDsaKey )
    {
      LODWORD(v9) = -1073741801;
      v8 = 1482;
      v10 = 3221225495LL;
      goto LABEL_4;
    }
    v22 = v16;
    if ( *(_DWORD *)(PqDsaKey + 8) != 196620 )
    {
      if ( *(_DWORD *)(PqDsaKey + 8) != 196621 )
      {
        LODWORD(v9) = -1073741816;
        v23 = 1543;
        v24 = 3221225480LL;
LABEL_35:
        DebugTraceError(v24, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\pqc-sign\\pqdsa.c", v23);
LABEL_50:
        freePqDsaKey((PVOID)v21);
        return (unsigned int)v9;
      }
      v25 = SymCryptCompositeMlDsakeyAllocate(*(unsigned int *)(PqDsaParameterSetInfoFromName + 24));
      v26 = v25;
      if ( !v25 )
      {
        v23 = 1519;
LABEL_38:
        LODWORD(v9) = -1073741801;
        v24 = 3221225495LL;
        goto LABEL_35;
      }
      v27 = SymCryptCompositeMlDsakeySetValue(
              v22 + (_DWORD)a5 + 12,
              a5[2],
              *(_DWORD *)(v15 + 32),
              *(_DWORD *)(v21 + 36),
              v25);
      if ( v27 )
      {
        v9 = (unsigned int)SymcryptErrorCodeToNtStatus(v27);
        DebugTraceError(v9, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\pqc-sign\\pqdsa.c", 1532);
        SymCryptCompositeMlDsakeyFree(v26);
        goto LABEL_50;
      }
      goto LABEL_45;
    }
    v28 = SymCryptMlDsakeyAllocate(*(unsigned int *)(PqDsaParameterSetInfoFromName + 24));
    v26 = v28;
    if ( !v28 )
    {
      v23 = 1493;
      goto LABEL_38;
    }
    v29 = SymCryptMlDsakeySetValue(v22 + (_DWORD)a5 + 12, a5[2], *(_DWORD *)(v15 + 32), *(_DWORD *)(v21 + 36), v28);
    if ( !v29 )
    {
LABEL_45:
      *(_QWORD *)(v21 + 40) = v26;
      LODWORD(v9) = 0;
      *(_QWORD *)(v21 + 24) = PqDsaParameterSetInfoFromName;
      *(_DWORD *)(v21 + 32) = 1;
      *a4 = v21;
      return (unsigned int)v9;
    }
    v9 = (unsigned int)SymcryptErrorCodeToNtStatus(v29);
    v30 = v9;
    v31 = 1506;
  }
  else
  {
    v21 = 0;
    LODWORD(v9) = -1073741811;
    v26 = 0;
    v30 = 3221225485LL;
    v31 = 1404;
  }
  DebugTraceError(v30, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\pqc-sign\\pqdsa.c", v31);
  if ( v26 )
    SymCryptMlDsakeyFree(v26);
  if ( v21 )
    goto LABEL_50;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800792d0  push    rbx
0x1800792d2  push    rbp
0x1800792d3  push    rsi
0x1800792d4  push    rdi
0x1800792d5  push    r12
0x1800792d7  push    r14
0x1800792d9  push    r15
0x1800792db  sub     rsp, 30h
0x1800792df  mov     r15, r9
0x1800792e2  test    rcx, rcx
0x1800792e5  jnz     short loc_18007930F
0x1800792e7  mov     r9d, 560h
0x1800792ed  mov     ebx, 0C000000Dh
0x1800792f2  mov     ecx, 0C000000Dh
0x1800792f7  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800792fe  lea     rdx, aStatus_0; "status"
0x180079305  call    DebugTraceError
0x18007930a  jmp     loc_1800795B1
0x18007930f  test    rdx, rdx
0x180079312  jz      short loc_180079326
0x180079314  mov     ebx, 0C00000BBh
0x180079319  mov     r9d, 567h
0x18007931f  mov     ecx, 0C00000BBh
0x180079324  jmp     short loc_1800792F7
0x180079326  test    r8, r8
0x180079329  jnz     short loc_180079333
0x18007932b  mov     r9d, 56Eh
0x180079331  jmp     short loc_1800792ED
0x180079333  test    r15, r15
0x180079336  jnz     short loc_180079340
0x180079338  mov     r9d, 575h
0x18007933e  jmp     short loc_1800792ED
0x180079340  mov     rbx, [rsp+68h+arg_20]
0x180079348  test    rbx, rbx
0x18007934b  jz      loc_180079570
0x180079351  cmp     [rsp+68h+arg_28], 0Ch
0x180079359  jb      loc_180079570
0x18007935f  test    [rsp+68h+arg_30], 0FFFFFFF7h
0x18007936a  jz      short loc_180079377
0x18007936c  mov     r9d, 583h
0x180079372  jmp     loc_1800792ED
0x180079377  call    validatePqDsaAlgorithm
0x18007937c  test    rax, rax
0x18007937f  jnz     short loc_180079396
0x180079381  mov     ebx, 0C0000008h
0x180079386  mov     r9d, 58Bh
0x18007938c  mov     ecx, 0C0000008h
0x180079391  jmp     loc_1800792F7
0x180079396  mov     rdi, [rax+10h]
0x18007939a  mov     rdx, r8
0x18007939d  mov     rcx, rdi
0x1800793a0  call    getPqDsaBlobInfoFromType
0x1800793a5  mov     r14, rax
0x1800793a8  test    rax, rax
0x1800793ab  jnz     short loc_1800793B8
0x1800793ad  mov     r9d, 593h
0x1800793b3  jmp     loc_1800792ED
0x1800793b8  mov     eax, [rax+10h]
0x1800793bb  cmp     [rbx], eax
0x1800793bd  jz      short loc_1800793CA
0x1800793bf  mov     r9d, 59Ch
0x1800793c5  jmp     loc_1800792ED
0x1800793ca  mov     esi, [rbx+4]
0x1800793cd  lea     ecx, [rsi+0Ch]
0x1800793d0  cmp     ecx, 0Ch
0x1800793d3  jnb     short loc_1800793EA
0x1800793d5  mov     r9d, 5A9h
0x1800793db  mov     ebx, 0C0000095h
0x1800793e0  mov     ecx, 0C0000095h
0x1800793e5  jmp     loc_1800792F7
0x1800793ea  mov     edx, [rbx+8]
0x1800793ed  add     edx, ecx
0x1800793ef  cmp     edx, ecx
0x1800793f1  jnb     short loc_1800793FB
0x1800793f3  mov     r9d, 5B0h
0x1800793f9  jmp     short loc_1800793DB
0x1800793fb  cmp     [rsp+68h+arg_28], edx
0x180079402  jnb     short loc_18007940F
0x180079404  mov     r9d, 5B7h
0x18007940a  jmp     loc_1800792ED
0x18007940f  lea     rdx, [rbx+0Ch]
0x180079413  mov     r8d, esi
0x180079416  mov     rcx, rdi
0x180079419  call    getPqDsaParameterSetInfoFromName
0x18007941e  mov     rbp, rax
0x180079421  test    rax, rax
0x180079424  jnz     short loc_180079431
0x180079426  mov     r9d, 5C2h
0x18007942c  jmp     loc_1800792ED
0x180079431  mov     edx, [rsp+68h+arg_30]
0x180079438  mov     rcx, rdi
0x18007943b  call    createPqDsaKey
0x180079440  mov     rdi, rax
0x180079443  test    rax, rax
0x180079446  jnz     short loc_18007945D
0x180079448  mov     ebx, 0C0000017h
0x18007944d  mov     r9d, 5CAh
0x180079453  mov     ecx, 0C0000017h
0x180079458  jmp     loc_1800792F7
0x18007945d  mov     ecx, [rax+8]
0x180079460  mov     r12, rsi
0x180079463  sub     ecx, 3000Ch
0x180079469  jz      loc_18007950F
0x18007946f  cmp     ecx, 1
0x180079472  jz      short loc_18007949C
0x180079474  mov     ebx, 0C0000008h
0x180079479  mov     r9d, 607h
0x18007947f  mov     ecx, 0C0000008h
0x180079484  lea     rdx, aStatus_0; "status"
0x18007948b  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180079492  call    DebugTraceError
0x180079497  jmp     loc_1800795A9
0x18007949c  mov     ecx, [rbp+18h]
0x18007949f  call    SymCryptCompositeMlDsakeyAllocate
0x1800794a4  mov     rsi, rax
0x1800794a7  test    rax, rax
0x1800794aa  jnz     short loc_1800794BE
0x1800794ac  mov     r9d, 5EFh
0x1800794b2  mov     ebx, 0C0000017h
0x1800794b7  mov     ecx, 0C0000017h
0x1800794bc  jmp     short loc_180079484
0x1800794be  mov     edx, [rbx+8]
0x1800794c1  lea     rcx, [rbx+0Ch]
0x1800794c5  mov     r9d, [rdi+24h]
0x1800794c9  add     rcx, r12
0x1800794cc  mov     r8d, [r14+20h]
0x1800794d0  mov     [rsp+68h+var_48], rsi
0x1800794d5  call    SymCryptCompositeMlDsakeySetValue
0x1800794da  test    eax, eax
0x1800794dc  jz      short loc_18007955A
0x1800794de  mov     ecx, eax
0x1800794e0  call    SymcryptErrorCodeToNtStatus
0x1800794e5  mov     ecx, eax
0x1800794e7  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800794ee  mov     r9d, 5FCh
0x1800794f4  lea     rdx, aStatus_0; "status"
0x1800794fb  mov     ebx, eax
0x1800794fd  call    DebugTraceError
0x180079502  mov     rcx, rsi
0x180079505  call    SymCryptCompositeMlDsakeyFree
0x18007950a  jmp     loc_1800795A9
0x18007950f  mov     ecx, [rbp+18h]
0x180079512  call    SymCryptMlDsakeyAllocate
0x180079517  mov     rsi, rax
0x18007951a  test    rax, rax
0x18007951d  jnz     short loc_180079527
0x18007951f  mov     r9d, 5D5h
0x180079525  jmp     short loc_1800794B2
0x180079527  mov     edx, [rbx+8]
0x18007952a  lea     rcx, [rbx+0Ch]
0x18007952e  mov     r9d, [rdi+24h]
0x180079532  add     rcx, r12
0x180079535  mov     r8d, [r14+20h]
0x180079539  mov     [rsp+68h+var_48], rax
0x18007953e  call    SymCryptMlDsakeySetValue
0x180079543  test    eax, eax
0x180079545  jz      short loc_18007955A
0x180079547  mov     ecx, eax
0x180079549  call    SymcryptErrorCodeToNtStatus
0x18007954e  mov     ebx, eax
0x180079550  mov     ecx, eax
0x180079552  mov     r9d, 5E2h
0x180079558  jmp     short loc_180079584
0x18007955a  mov     [rdi+28h], rsi
0x18007955e  xor     ebx, ebx
0x180079560  mov     [rdi+18h], rbp
0x180079564  mov     dword ptr [rdi+20h], 1
0x18007956b  mov     [r15], rdi
0x18007956e  jmp     short loc_1800795B1
0x180079570  xor     edi, edi
0x180079572  mov     ebx, 0C000000Dh
0x180079577  xor     esi, esi
0x180079579  mov     ecx, 0C000000Dh
0x18007957e  mov     r9d, 57Ch
0x180079584  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007958b  lea     rdx, aStatus_0; "status"
0x180079592  call    DebugTraceError
0x180079597  test    rsi, rsi
0x18007959a  jz      short loc_1800795A4
0x18007959c  mov     rcx, rsi
0x18007959f  call    SymCryptMlDsakeyFree
0x1800795a4  test    rdi, rdi
0x1800795a7  jz      short loc_1800795B1
0x1800795a9  mov     rcx, rdi; P
0x1800795ac  call    freePqDsaKey
0x1800795b1  mov     eax, ebx
0x1800795b3  add     rsp, 30h
0x1800795b7  pop     r15
0x1800795b9  pop     r14
0x1800795bb  pop     r12
0x1800795bd  pop     rdi
0x1800795be  pop     rsi
0x1800795bf  pop     rbp
0x1800795c0  pop     rbx
0x1800795c1  retn
```
