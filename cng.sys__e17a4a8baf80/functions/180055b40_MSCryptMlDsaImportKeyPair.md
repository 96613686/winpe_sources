# MSCryptMlDsaImportKeyPair

- ea: `0x180055b40`
- end: `0x180055d81`
- name: `MSCryptMlDsaImportKeyPair`
- size: `577`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x18001155c`
- `0x180051dd0`
- `0x180055b40`
- `0x180082fe0`
- `0x180083038`
- `0x18008307c`
- `0x1800830f0`
- `0x18008329c`
- `0x18009659c`
- `0x180096620`
- `0x1800967fc`

## string_xrefs

- `0x180055b67`: `onecore\ds\security\cryptoapi\ncrypt\msprim\pqc-sign\mldsa.c`
- `0x180055d49`: `onecore\ds\security\cryptoapi\ncrypt\msprim\pqc-sign\mldsa.c`

## pseudocode

```c
__int64 __fastcall MSCryptMlDsaImportKeyPair(
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
  __int64 v11; // r8
  __int64 BlobInfoFromType; // rax
  __int64 v13; // r15
  unsigned int v14; // r14d
  unsigned int v15; // ecx
  unsigned int v16; // edx
  __int64 InfoFromParameterSetName; // rax
  __int64 v18; // rbp
  __int64 v19; // rsi
  __int64 MSCryptMlDsaKey; // rax
  __int64 v21; // rdi
  __int64 v22; // rcx
  __int64 v23; // r9
  unsigned int v24; // eax

  if ( !a1 )
  {
    v8 = 1139;
LABEL_3:
    LODWORD(v9) = -1073741811;
    v10 = 3221225485LL;
LABEL_4:
    DebugTraceError(v10, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\pqc-sign\\mldsa.c", v8);
    return (unsigned int)v9;
  }
  if ( a2 )
  {
    LODWORD(v9) = -1073741637;
    v8 = 1146;
    v10 = 3221225659LL;
    goto LABEL_4;
  }
  if ( !a3 )
  {
    v8 = 1153;
    goto LABEL_3;
  }
  if ( !a4 )
  {
    v8 = 1160;
    goto LABEL_3;
  }
  if ( a5 && a6 >= 0xC )
  {
    if ( (a7 & 0xFFFFFFF7) != 0 )
    {
      v8 = 1174;
      goto LABEL_3;
    }
    if ( !validateMSCryptMlDsaAlgorithm() )
    {
      LODWORD(v9) = -1073741816;
      v8 = 1185;
      v10 = 3221225480LL;
      goto LABEL_4;
    }
    BlobInfoFromType = getBlobInfoFromType(v11);
    v13 = BlobInfoFromType;
    if ( !BlobInfoFromType )
    {
      v8 = 1193;
      goto LABEL_3;
    }
    if ( *a5 != *(_DWORD *)(BlobInfoFromType + 16) )
    {
      v8 = 1202;
      goto LABEL_3;
    }
    v14 = a5[1];
    v15 = v14 + 12;
    if ( v14 >= 0xFFFFFFF4 )
    {
      v8 = 1222;
LABEL_23:
      LODWORD(v9) = -1073741675;
      v10 = 3221225621LL;
      goto LABEL_4;
    }
    v16 = v15 + a5[2];
    if ( v16 < v15 )
    {
      v8 = 1229;
      goto LABEL_23;
    }
    if ( a6 < v16 )
    {
      v8 = 1236;
      goto LABEL_3;
    }
    InfoFromParameterSetName = getInfoFromParameterSetName(a5 + 3, v14);
    v18 = InfoFromParameterSetName;
    if ( !InfoFromParameterSetName )
    {
      v8 = 1247;
      goto LABEL_3;
    }
    v19 = SymCryptMlDsakeyAllocate(*(unsigned int *)(InfoFromParameterSetName + 12));
    if ( !v19 )
    {
      LODWORD(v9) = -1073741801;
      v8 = 1255;
      v10 = 3221225495LL;
      goto LABEL_4;
    }
    MSCryptMlDsaKey = createMSCryptMlDsaKey(a7);
    v21 = MSCryptMlDsaKey;
    if ( MSCryptMlDsaKey )
    {
      v24 = SymCryptMlDsakeySetValue(
              v14 + (_DWORD)a5 + 12,
              a5[2],
              *(_DWORD *)(v13 + 20),
              *(_DWORD *)(MSCryptMlDsaKey + 36),
              v19);
      if ( !v24 )
      {
        *(_QWORD *)(v21 + 16) = v18;
        LODWORD(v9) = 0;
        *(_QWORD *)(v21 + 24) = v19;
        *(_DWORD *)(v21 + 32) = 1;
        *a4 = v21;
        return (unsigned int)v9;
      }
      v9 = (unsigned int)SymcryptErrorCodeToNtStatus(v24);
      v22 = v9;
      v23 = 1276;
    }
    else
    {
      LODWORD(v9) = -1073741801;
      v22 = 3221225495LL;
      v23 = 1263;
    }
  }
  else
  {
    v21 = 0;
    LODWORD(v9) = -1073741811;
    v19 = 0;
    v22 = 3221225485LL;
    v23 = 1167;
  }
  DebugTraceError(v22, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\pqc-sign\\mldsa.c", v23);
  if ( v19 )
    SymCryptMlDsakeyFree(v19);
  if ( v21 )
    freeMSCryptMlDsaKey((PVOID)v21);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180055b40  push    rbx
0x180055b42  push    rbp
0x180055b43  push    rsi
0x180055b44  push    rdi
0x180055b45  push    r12
0x180055b47  push    r14
0x180055b49  push    r15
0x180055b4b  sub     rsp, 30h
0x180055b4f  mov     r12, r9
0x180055b52  test    rcx, rcx
0x180055b55  jnz     short loc_180055B7F
0x180055b57  mov     r9d, 473h
0x180055b5d  mov     ebx, 0C000000Dh
0x180055b62  mov     ecx, 0C000000Dh
0x180055b67  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180055b6e  lea     rdx, aStatus_0; "status"
0x180055b75  call    DebugTraceError
0x180055b7a  jmp     loc_180055D6F
0x180055b7f  test    rdx, rdx
0x180055b82  jz      short loc_180055B96
0x180055b84  mov     ebx, 0C00000BBh
0x180055b89  mov     r9d, 47Ah
0x180055b8f  mov     ecx, 0C00000BBh
0x180055b94  jmp     short loc_180055B67
0x180055b96  test    r8, r8
0x180055b99  jnz     short loc_180055BA3
0x180055b9b  mov     r9d, 481h
0x180055ba1  jmp     short loc_180055B5D
0x180055ba3  test    r12, r12
0x180055ba6  jnz     short loc_180055BB0
0x180055ba8  mov     r9d, 488h
0x180055bae  jmp     short loc_180055B5D
0x180055bb0  mov     rbx, [rsp+68h+arg_20]
0x180055bb8  test    rbx, rbx
0x180055bbb  jz      loc_180055D2E
0x180055bc1  cmp     [rsp+68h+arg_28], 0Ch
0x180055bc9  jb      loc_180055D2E
0x180055bcf  test    [rsp+68h+arg_30], 0FFFFFFF7h
0x180055bda  jz      short loc_180055BE7
0x180055bdc  mov     r9d, 496h
0x180055be2  jmp     loc_180055B5D
0x180055be7  call    validateMSCryptMlDsaAlgorithm
0x180055bec  test    rax, rax
0x180055bef  jnz     short loc_180055C06
0x180055bf1  mov     ebx, 0C0000008h
0x180055bf6  mov     r9d, 4A1h
0x180055bfc  mov     ecx, 0C0000008h
0x180055c01  jmp     loc_180055B67
0x180055c06  mov     rcx, r8
0x180055c09  call    getBlobInfoFromType
0x180055c0e  mov     r15, rax
0x180055c11  test    rax, rax
0x180055c14  jnz     short loc_180055C21
0x180055c16  mov     r9d, 4A9h
0x180055c1c  jmp     loc_180055B5D
0x180055c21  mov     eax, [rax+10h]
0x180055c24  cmp     [rbx], eax
0x180055c26  jz      short loc_180055C33
0x180055c28  mov     r9d, 4B2h
0x180055c2e  jmp     loc_180055B5D
0x180055c33  mov     r14d, [rbx+4]
0x180055c37  lea     ecx, [r14+0Ch]
0x180055c3b  cmp     ecx, 0Ch
0x180055c3e  jnb     short loc_180055C55
0x180055c40  mov     r9d, 4C6h
0x180055c46  mov     ebx, 0C0000095h
0x180055c4b  mov     ecx, 0C0000095h
0x180055c50  jmp     loc_180055B67
0x180055c55  mov     edx, [rbx+8]
0x180055c58  add     edx, ecx
0x180055c5a  cmp     edx, ecx
0x180055c5c  jnb     short loc_180055C66
0x180055c5e  mov     r9d, 4CDh
0x180055c64  jmp     short loc_180055C46
0x180055c66  cmp     [rsp+68h+arg_28], edx
0x180055c6d  jnb     short loc_180055C7A
0x180055c6f  mov     r9d, 4D4h
0x180055c75  jmp     loc_180055B5D
0x180055c7a  lea     rcx, [rbx+0Ch]; Buf1
0x180055c7e  mov     edx, r14d; Size
0x180055c81  call    getInfoFromParameterSetName
0x180055c86  mov     rbp, rax
0x180055c89  test    rax, rax
0x180055c8c  jnz     short loc_180055C99
0x180055c8e  mov     r9d, 4DFh
0x180055c94  jmp     loc_180055B5D
0x180055c99  mov     ecx, [rax+0Ch]
0x180055c9c  call    SymCryptMlDsakeyAllocate
0x180055ca1  mov     rsi, rax
0x180055ca4  test    rax, rax
0x180055ca7  jnz     short loc_180055CBE
0x180055ca9  mov     ebx, 0C0000017h
0x180055cae  mov     r9d, 4E7h
0x180055cb4  mov     ecx, 0C0000017h
0x180055cb9  jmp     loc_180055B67
0x180055cbe  mov     ecx, [rsp+68h+arg_30]
0x180055cc5  call    createMSCryptMlDsaKey
0x180055cca  mov     rdi, rax
0x180055ccd  test    rax, rax
0x180055cd0  jnz     short loc_180055CE4
0x180055cd2  mov     ebx, 0C0000017h
0x180055cd7  mov     ecx, 0C0000017h
0x180055cdc  mov     r9d, 4EFh
0x180055ce2  jmp     short loc_180055D42
0x180055ce4  mov     edx, [rbx+8]
0x180055ce7  lea     rcx, [rbx+0Ch]
0x180055ceb  mov     r9d, [rax+24h]
0x180055cef  add     rcx, r14
0x180055cf2  mov     r8d, [r15+14h]
0x180055cf6  mov     [rsp+68h+var_48], rsi
0x180055cfb  call    SymCryptMlDsakeySetValue
0x180055d00  test    eax, eax
0x180055d02  jz      short loc_180055D17
0x180055d04  mov     ecx, eax
0x180055d06  call    SymcryptErrorCodeToNtStatus
0x180055d0b  mov     ebx, eax
0x180055d0d  mov     ecx, eax
0x180055d0f  mov     r9d, 4FCh
0x180055d15  jmp     short loc_180055D42
0x180055d17  mov     [rdi+10h], rbp
0x180055d1b  xor     ebx, ebx
0x180055d1d  mov     [rdi+18h], rsi
0x180055d21  mov     dword ptr [rdi+20h], 1
0x180055d28  mov     [r12], rdi
0x180055d2c  jmp     short loc_180055D6F
0x180055d2e  xor     edi, edi
0x180055d30  mov     ebx, 0C000000Dh
0x180055d35  xor     esi, esi
0x180055d37  mov     ecx, 0C000000Dh
0x180055d3c  mov     r9d, 48Fh
0x180055d42  lea     rdx, aStatus_0; "status"
0x180055d49  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180055d50  call    DebugTraceError
0x180055d55  test    rsi, rsi
0x180055d58  jz      short loc_180055D62
0x180055d5a  mov     rcx, rsi
0x180055d5d  call    SymCryptMlDsakeyFree
0x180055d62  test    rdi, rdi
0x180055d65  jz      short loc_180055D6F
0x180055d67  mov     rcx, rdi; P
0x180055d6a  call    freeMSCryptMlDsaKey
0x180055d6f  mov     eax, ebx
0x180055d71  add     rsp, 30h
0x180055d75  pop     r15
0x180055d77  pop     r14
0x180055d79  pop     r12
0x180055d7b  pop     rdi
0x180055d7c  pop     rsi
0x180055d7d  pop     rbp
0x180055d7e  pop     rbx
0x180055d7f  retn
```
