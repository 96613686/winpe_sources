# MSCryptMlDsaImportKeyPair

- ea: `0x18004ba40`
- end: `0x18004bc81`
- name: `MSCryptMlDsaImportKeyPair`
- size: `577`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x18000743c`
- `0x180047ce0`
- `0x18004ba40`
- `0x180078e40`
- `0x180078e98`
- `0x180078edc`
- `0x180078f50`
- `0x1800790fc`
- `0x18008c60c`
- `0x18008c690`
- `0x18008c86c`

## string_xrefs

- `0x18004ba67`: `onecore\ds\security\cryptoapi\ncrypt\msprim\pqc-sign\mldsa.c`
- `0x18004bc49`: `onecore\ds\security\cryptoapi\ncrypt\msprim\pqc-sign\mldsa.c`

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
0x18004ba40  push    rbx
0x18004ba42  push    rbp
0x18004ba43  push    rsi
0x18004ba44  push    rdi
0x18004ba45  push    r12
0x18004ba47  push    r14
0x18004ba49  push    r15
0x18004ba4b  sub     rsp, 30h
0x18004ba4f  mov     r12, r9
0x18004ba52  test    rcx, rcx
0x18004ba55  jnz     short loc_18004BA7F
0x18004ba57  mov     r9d, 473h
0x18004ba5d  mov     ebx, 0C000000Dh
0x18004ba62  mov     ecx, 0C000000Dh
0x18004ba67  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004ba6e  lea     rdx, aStatus_0; "status"
0x18004ba75  call    DebugTraceError
0x18004ba7a  jmp     loc_18004BC6F
0x18004ba7f  test    rdx, rdx
0x18004ba82  jz      short loc_18004BA96
0x18004ba84  mov     ebx, 0C00000BBh
0x18004ba89  mov     r9d, 47Ah
0x18004ba8f  mov     ecx, 0C00000BBh
0x18004ba94  jmp     short loc_18004BA67
0x18004ba96  test    r8, r8
0x18004ba99  jnz     short loc_18004BAA3
0x18004ba9b  mov     r9d, 481h
0x18004baa1  jmp     short loc_18004BA5D
0x18004baa3  test    r12, r12
0x18004baa6  jnz     short loc_18004BAB0
0x18004baa8  mov     r9d, 488h
0x18004baae  jmp     short loc_18004BA5D
0x18004bab0  mov     rbx, [rsp+68h+arg_20]
0x18004bab8  test    rbx, rbx
0x18004babb  jz      loc_18004BC2E
0x18004bac1  cmp     [rsp+68h+arg_28], 0Ch
0x18004bac9  jb      loc_18004BC2E
0x18004bacf  test    [rsp+68h+arg_30], 0FFFFFFF7h
0x18004bada  jz      short loc_18004BAE7
0x18004badc  mov     r9d, 496h
0x18004bae2  jmp     loc_18004BA5D
0x18004bae7  call    validateMSCryptMlDsaAlgorithm
0x18004baec  test    rax, rax
0x18004baef  jnz     short loc_18004BB06
0x18004baf1  mov     ebx, 0C0000008h
0x18004baf6  mov     r9d, 4A1h
0x18004bafc  mov     ecx, 0C0000008h
0x18004bb01  jmp     loc_18004BA67
0x18004bb06  mov     rcx, r8
0x18004bb09  call    getBlobInfoFromType
0x18004bb0e  mov     r15, rax
0x18004bb11  test    rax, rax
0x18004bb14  jnz     short loc_18004BB21
0x18004bb16  mov     r9d, 4A9h
0x18004bb1c  jmp     loc_18004BA5D
0x18004bb21  mov     eax, [rax+10h]
0x18004bb24  cmp     [rbx], eax
0x18004bb26  jz      short loc_18004BB33
0x18004bb28  mov     r9d, 4B2h
0x18004bb2e  jmp     loc_18004BA5D
0x18004bb33  mov     r14d, [rbx+4]
0x18004bb37  lea     ecx, [r14+0Ch]
0x18004bb3b  cmp     ecx, 0Ch
0x18004bb3e  jnb     short loc_18004BB55
0x18004bb40  mov     r9d, 4C6h
0x18004bb46  mov     ebx, 0C0000095h
0x18004bb4b  mov     ecx, 0C0000095h
0x18004bb50  jmp     loc_18004BA67
0x18004bb55  mov     edx, [rbx+8]
0x18004bb58  add     edx, ecx
0x18004bb5a  cmp     edx, ecx
0x18004bb5c  jnb     short loc_18004BB66
0x18004bb5e  mov     r9d, 4CDh
0x18004bb64  jmp     short loc_18004BB46
0x18004bb66  cmp     [rsp+68h+arg_28], edx
0x18004bb6d  jnb     short loc_18004BB7A
0x18004bb6f  mov     r9d, 4D4h
0x18004bb75  jmp     loc_18004BA5D
0x18004bb7a  lea     rcx, [rbx+0Ch]; Buf1
0x18004bb7e  mov     edx, r14d; Size
0x18004bb81  call    getInfoFromParameterSetName
0x18004bb86  mov     rbp, rax
0x18004bb89  test    rax, rax
0x18004bb8c  jnz     short loc_18004BB99
0x18004bb8e  mov     r9d, 4DFh
0x18004bb94  jmp     loc_18004BA5D
0x18004bb99  mov     ecx, [rax+0Ch]
0x18004bb9c  call    SymCryptMlDsakeyAllocate
0x18004bba1  mov     rsi, rax
0x18004bba4  test    rax, rax
0x18004bba7  jnz     short loc_18004BBBE
0x18004bba9  mov     ebx, 0C0000017h
0x18004bbae  mov     r9d, 4E7h
0x18004bbb4  mov     ecx, 0C0000017h
0x18004bbb9  jmp     loc_18004BA67
0x18004bbbe  mov     ecx, [rsp+68h+arg_30]
0x18004bbc5  call    createMSCryptMlDsaKey
0x18004bbca  mov     rdi, rax
0x18004bbcd  test    rax, rax
0x18004bbd0  jnz     short loc_18004BBE4
0x18004bbd2  mov     ebx, 0C0000017h
0x18004bbd7  mov     ecx, 0C0000017h
0x18004bbdc  mov     r9d, 4EFh
0x18004bbe2  jmp     short loc_18004BC42
0x18004bbe4  mov     edx, [rbx+8]
0x18004bbe7  lea     rcx, [rbx+0Ch]
0x18004bbeb  mov     r9d, [rax+24h]
0x18004bbef  add     rcx, r14
0x18004bbf2  mov     r8d, [r15+14h]
0x18004bbf6  mov     [rsp+68h+var_48], rsi
0x18004bbfb  call    SymCryptMlDsakeySetValue
0x18004bc00  test    eax, eax
0x18004bc02  jz      short loc_18004BC17
0x18004bc04  mov     ecx, eax
0x18004bc06  call    SymcryptErrorCodeToNtStatus
0x18004bc0b  mov     ebx, eax
0x18004bc0d  mov     ecx, eax
0x18004bc0f  mov     r9d, 4FCh
0x18004bc15  jmp     short loc_18004BC42
0x18004bc17  mov     [rdi+10h], rbp
0x18004bc1b  xor     ebx, ebx
0x18004bc1d  mov     [rdi+18h], rsi
0x18004bc21  mov     dword ptr [rdi+20h], 1
0x18004bc28  mov     [r12], rdi
0x18004bc2c  jmp     short loc_18004BC6F
0x18004bc2e  xor     edi, edi
0x18004bc30  mov     ebx, 0C000000Dh
0x18004bc35  xor     esi, esi
0x18004bc37  mov     ecx, 0C000000Dh
0x18004bc3c  mov     r9d, 48Fh
0x18004bc42  lea     rdx, aStatus_0; "status"
0x18004bc49  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004bc50  call    DebugTraceError
0x18004bc55  test    rsi, rsi
0x18004bc58  jz      short loc_18004BC62
0x18004bc5a  mov     rcx, rsi
0x18004bc5d  call    SymCryptMlDsakeyFree
0x18004bc62  test    rdi, rdi
0x18004bc65  jz      short loc_18004BC6F
0x18004bc67  mov     rcx, rdi; P
0x18004bc6a  call    freeMSCryptMlDsaKey
0x18004bc6f  mov     eax, ebx
0x18004bc71  add     rsp, 30h
0x18004bc75  pop     r15
0x18004bc77  pop     r14
0x18004bc79  pop     r12
0x18004bc7b  pop     rdi
0x18004bc7c  pop     rsi
0x18004bc7d  pop     rbp
0x18004bc7e  pop     rbx
0x18004bc7f  retn
```
