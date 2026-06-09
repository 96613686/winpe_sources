# ImportMlKemKeyPair

- ea: `0x180079acc`
- end: `0x180079c4c`
- name: `ImportMlKemKeyPair`
- size: `384`
- prototype: `__int64 __fastcall(_DWORD *, unsigned int, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18007a660`

## callees

- `0x18000743c`
- `0x180047ce0`
- `0x180079798`
- `0x180079850`
- `0x180079acc`
- `0x18008d3f8`
- `0x18008dad4`
- `0x18008dfd8`

## string_xrefs

- `0x180079b13`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\kem.c`
- `0x180079c0b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\kem.c`

## pseudocode

```c
__int64 __fastcall ImportMlKemKeyPair(_DWORD *a1, unsigned int a2, __int64 a3, __int64 a4)
{
  __int64 v7; // r9
  __int64 v8; // rbx
  __int64 v9; // rcx
  int MlKemBlobInfo; // eax
  __int64 v11; // r14
  unsigned int v12; // eax
  unsigned int v13; // ecx
  __int64 v14; // r15
  __int64 v15; // rax
  __int64 v16; // rsi
  unsigned int v17; // eax
  __int64 v19; // [rsp+30h] [rbp-58h] BYREF
  __int64 v20; // [rsp+38h] [rbp-50h]

  v19 = 0;
  v20 = 0;
  if ( a2 < 0xC )
  {
    v7 = 1599;
LABEL_3:
    LODWORD(v8) = -1073741811;
    v9 = 3221225485LL;
LABEL_4:
    DebugTraceError(v9, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\kem.c", v7);
    return (unsigned int)v8;
  }
  MlKemBlobInfo = GetMlKemBlobInfo(a3, &v19);
  LODWORD(v8) = MlKemBlobInfo;
  if ( MlKemBlobInfo < 0 )
  {
    v7 = 1606;
LABEL_7:
    v9 = (unsigned int)MlKemBlobInfo;
    goto LABEL_4;
  }
  if ( *a1 != *(_DWORD *)(v19 + 16) )
  {
    v7 = 1615;
    goto LABEL_3;
  }
  v11 = (unsigned int)a1[1];
  v12 = v11 + 12;
  if ( (unsigned int)v11 >= 0xFFFFFFF4 )
  {
    v7 = 1627;
LABEL_12:
    LODWORD(v8) = -1073741675;
    v9 = 3221225621LL;
    goto LABEL_4;
  }
  v13 = a1[2] + v12;
  if ( v13 < v12 )
  {
    v7 = 1634;
    goto LABEL_12;
  }
  if ( a2 < v13 )
  {
    v7 = 1641;
    goto LABEL_3;
  }
  MlKemBlobInfo = GetMlKemParamSetInfo(a1 + 3, (unsigned int)v11);
  LODWORD(v8) = MlKemBlobInfo;
  if ( MlKemBlobInfo < 0 )
  {
    v7 = 1651;
    goto LABEL_7;
  }
  v14 = v20;
  v15 = SymCryptMlKemkeyAllocate(*(unsigned int *)(v20 + 28));
  v16 = v15;
  if ( !v15 )
  {
    LODWORD(v8) = -1073741801;
    v7 = 1659;
    v9 = 3221225495LL;
    goto LABEL_4;
  }
  v17 = SymCryptMlKemkeySetValue((char *)a1 + v11 + 12, v15);
  if ( v17 )
  {
    v8 = (unsigned int)SymcryptErrorCodeToNtStatus(v17);
    DebugTraceError(v8, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\kem.c", 1667);
    SymCryptMlKemkeyFree(v16);
  }
  else
  {
    *(_QWORD *)(a4 + 32) = v16;
    *(_QWORD *)(a4 + 24) = v14;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180079acc  push    rbx
0x180079ace  push    rbp
0x180079acf  push    rsi
0x180079ad0  push    rdi
0x180079ad1  push    r12
0x180079ad3  push    r13
0x180079ad5  push    r14
0x180079ad7  push    r15
0x180079ad9  sub     rsp, 48h
0x180079add  mov     [rsp+88h+var_58], 0
0x180079ae6  mov     rbp, r9
0x180079ae9  mov     [rsp+88h+var_50], 0
0x180079af2  mov     esi, edx
0x180079af4  mov     rdi, rcx
0x180079af7  cmp     edx, 0Ch
0x180079afa  jnb     short loc_180079B24
0x180079afc  mov     r9d, 63Fh
0x180079b02  mov     ebx, 0C000000Dh
0x180079b07  mov     ecx, 0C000000Dh
0x180079b0c  lea     rdx, aStatus; "Status"
0x180079b13  lea     r8, aOnecoreDsSecur_38; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180079b1a  call    DebugTraceError
0x180079b1f  jmp     loc_180079C38
0x180079b24  lea     rdx, [rsp+88h+var_58]
0x180079b29  mov     rcx, r8
0x180079b2c  call    GetMlKemBlobInfo
0x180079b31  mov     ebx, eax
0x180079b33  test    eax, eax
0x180079b35  jns     short loc_180079B41
0x180079b37  mov     r9d, 646h
0x180079b3d  mov     ecx, eax
0x180079b3f  jmp     short loc_180079B0C
0x180079b41  mov     r13, [rsp+88h+var_58]
0x180079b46  mov     eax, [r13+10h]
0x180079b4a  cmp     [rdi], eax
0x180079b4c  jz      short loc_180079B56
0x180079b4e  mov     r9d, 64Fh
0x180079b54  jmp     short loc_180079B02
0x180079b56  mov     r14d, [rdi+4]
0x180079b5a  lea     eax, [r14+0Ch]
0x180079b5e  cmp     eax, 0Ch
0x180079b61  jnb     short loc_180079B75
0x180079b63  mov     r9d, 65Bh
0x180079b69  mov     ebx, 0C0000095h
0x180079b6e  mov     ecx, 0C0000095h
0x180079b73  jmp     short loc_180079B0C
0x180079b75  mov     r12d, [rdi+8]
0x180079b79  lea     ecx, [r12+rax]
0x180079b7d  cmp     ecx, eax
0x180079b7f  jnb     short loc_180079B89
0x180079b81  mov     r9d, 662h
0x180079b87  jmp     short loc_180079B69
0x180079b89  cmp     esi, ecx
0x180079b8b  jnb     short loc_180079B98
0x180079b8d  mov     r9d, 669h
0x180079b93  jmp     loc_180079B02
0x180079b98  lea     rcx, [rdi+0Ch]; Buf1
0x180079b9c  mov     edx, r14d; Size
0x180079b9f  lea     r8, [rsp+88h+var_50]
0x180079ba4  call    GetMlKemParamSetInfo
0x180079ba9  mov     ebx, eax
0x180079bab  test    eax, eax
0x180079bad  jns     short loc_180079BB7
0x180079baf  mov     r9d, 673h
0x180079bb5  jmp     short loc_180079B3D
0x180079bb7  mov     r15, [rsp+88h+var_50]
0x180079bbc  mov     ecx, [r15+1Ch]
0x180079bc0  call    SymCryptMlKemkeyAllocate
0x180079bc5  mov     rsi, rax
0x180079bc8  test    rax, rax
0x180079bcb  jnz     short loc_180079BE2
0x180079bcd  mov     ebx, 0C0000017h
0x180079bd2  mov     r9d, 67Bh
0x180079bd8  mov     ecx, 0C0000017h
0x180079bdd  jmp     loc_180079B0C
0x180079be2  mov     r9d, [rbp+0Ch]
0x180079be6  lea     rcx, [rdi+0Ch]
0x180079bea  mov     r8d, [r13+14h]
0x180079bee  add     rcx, r14; Src
0x180079bf1  mov     rdx, r12
0x180079bf4  mov     [rsp+88h+var_68], rsi; __int64
0x180079bf9  call    SymCryptMlKemkeySetValue
0x180079bfe  test    eax, eax
0x180079c00  jz      short loc_180079C30
0x180079c02  mov     ecx, eax
0x180079c04  call    SymcryptErrorCodeToNtStatus
0x180079c09  mov     ecx, eax
0x180079c0b  lea     r8, aOnecoreDsSecur_38; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180079c12  mov     r9d, 683h
0x180079c18  lea     rdx, aStatus; "Status"
0x180079c1f  mov     ebx, eax
0x180079c21  call    DebugTraceError
0x180079c26  mov     rcx, rsi
0x180079c29  call    SymCryptMlKemkeyFree
0x180079c2e  jmp     short loc_180079C38
0x180079c30  mov     [rbp+20h], rsi
0x180079c34  mov     [rbp+18h], r15
0x180079c38  mov     eax, ebx
0x180079c3a  add     rsp, 48h
0x180079c3e  pop     r15
0x180079c40  pop     r14
0x180079c42  pop     r13
0x180079c44  pop     r12
0x180079c46  pop     rdi
0x180079c47  pop     rsi
0x180079c48  pop     rbp
0x180079c49  pop     rbx
0x180079c4a  retn
```
