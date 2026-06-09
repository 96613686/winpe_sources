# ImportCompositeMlKemKeyPair

- ea: `0x180083aec`
- end: `0x180083c6c`
- name: `ImportCompositeMlKemKeyPair`
- size: `384`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180084860`

## callees

- `0x18001155c`
- `0x180051dd0`
- `0x1800837e4`
- `0x18008389c`
- `0x180083aec`
- `0x1800970e0`
- `0x1800971a0`
- `0x180097334`

## string_xrefs

- `0x180083b33`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\kem.c`
- `0x180083c2b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\kem.c`

## pseudocode

```c
__int64 __fastcall ImportCompositeMlKemKeyPair(_DWORD *a1, unsigned int a2, __int64 a3, __int64 a4)
{
  __int64 v7; // r9
  __int64 v8; // rbx
  __int64 v9; // rcx
  int CompositeMlKemBlobInfo; // eax
  __int64 v11; // r14
  unsigned int v12; // eax
  size_t v13; // r12
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
    v7 = 1724;
LABEL_3:
    LODWORD(v8) = -1073741811;
    v9 = 3221225485LL;
LABEL_4:
    DebugTraceError(v9, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\kem.c", v7);
    return (unsigned int)v8;
  }
  CompositeMlKemBlobInfo = GetCompositeMlKemBlobInfo(a3, &v19);
  LODWORD(v8) = CompositeMlKemBlobInfo;
  if ( CompositeMlKemBlobInfo < 0 )
  {
    v7 = 1731;
LABEL_7:
    v9 = (unsigned int)CompositeMlKemBlobInfo;
    goto LABEL_4;
  }
  if ( *a1 != *(_DWORD *)(v19 + 16) )
  {
    v7 = 1740;
    goto LABEL_3;
  }
  v11 = (unsigned int)a1[1];
  v12 = v11 + 12;
  if ( (unsigned int)v11 >= 0xFFFFFFF4 )
  {
    v7 = 1752;
LABEL_12:
    LODWORD(v8) = -1073741675;
    v9 = 3221225621LL;
    goto LABEL_4;
  }
  v13 = (unsigned int)a1[2];
  if ( (unsigned int)v13 + v12 < v12 )
  {
    v7 = 1759;
    goto LABEL_12;
  }
  if ( a2 < (unsigned int)v13 + v12 )
  {
    v7 = 1766;
    goto LABEL_3;
  }
  CompositeMlKemBlobInfo = GetCompositeMlKemParamSetInfo(a1 + 3, (unsigned int)v11);
  LODWORD(v8) = CompositeMlKemBlobInfo;
  if ( CompositeMlKemBlobInfo < 0 )
  {
    v7 = 1776;
    goto LABEL_7;
  }
  v14 = v20;
  v15 = SymCryptCompositeMlKemkeyAllocate(*(unsigned int *)(v20 + 28));
  v16 = v15;
  if ( !v15 )
  {
    LODWORD(v8) = -1073741801;
    v7 = 1784;
    v9 = 3221225495LL;
    goto LABEL_4;
  }
  v17 = SymCryptCompositeMlKemkeySetValue((char *)a1 + v11 + 12, v13, v15);
  if ( v17 )
  {
    v8 = (unsigned int)SymcryptErrorCodeToNtStatus(v17);
    DebugTraceError(v8, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\kem.c", 1792);
    SymCryptCompositeMlKemkeyFree(v16);
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
0x180083aec  push    rbx
0x180083aee  push    rbp
0x180083aef  push    rsi
0x180083af0  push    rdi
0x180083af1  push    r12
0x180083af3  push    r13
0x180083af5  push    r14
0x180083af7  push    r15
0x180083af9  sub     rsp, 48h
0x180083afd  mov     [rsp+88h+var_58], 0
0x180083b06  mov     rbp, r9
0x180083b09  mov     [rsp+88h+var_50], 0
0x180083b12  mov     esi, edx
0x180083b14  mov     rdi, rcx
0x180083b17  cmp     edx, 0Ch
0x180083b1a  jnb     short loc_180083B44
0x180083b1c  mov     r9d, 6BCh
0x180083b22  mov     ebx, 0C000000Dh
0x180083b27  mov     ecx, 0C000000Dh
0x180083b2c  lea     rdx, aStatus; "Status"
0x180083b33  lea     r8, aOnecoreDsSecur_38; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180083b3a  call    DebugTraceError
0x180083b3f  jmp     loc_180083C58
0x180083b44  lea     rdx, [rsp+88h+var_58]
0x180083b49  mov     rcx, r8
0x180083b4c  call    GetCompositeMlKemBlobInfo
0x180083b51  mov     ebx, eax
0x180083b53  test    eax, eax
0x180083b55  jns     short loc_180083B61
0x180083b57  mov     r9d, 6C3h
0x180083b5d  mov     ecx, eax
0x180083b5f  jmp     short loc_180083B2C
0x180083b61  mov     r13, [rsp+88h+var_58]
0x180083b66  mov     eax, [r13+10h]
0x180083b6a  cmp     [rdi], eax
0x180083b6c  jz      short loc_180083B76
0x180083b6e  mov     r9d, 6CCh
0x180083b74  jmp     short loc_180083B22
0x180083b76  mov     r14d, [rdi+4]
0x180083b7a  lea     eax, [r14+0Ch]
0x180083b7e  cmp     eax, 0Ch
0x180083b81  jnb     short loc_180083B95
0x180083b83  mov     r9d, 6D8h
0x180083b89  mov     ebx, 0C0000095h
0x180083b8e  mov     ecx, 0C0000095h
0x180083b93  jmp     short loc_180083B2C
0x180083b95  mov     r12d, [rdi+8]
0x180083b99  lea     ecx, [r12+rax]
0x180083b9d  cmp     ecx, eax
0x180083b9f  jnb     short loc_180083BA9
0x180083ba1  mov     r9d, 6DFh
0x180083ba7  jmp     short loc_180083B89
0x180083ba9  cmp     esi, ecx
0x180083bab  jnb     short loc_180083BB8
0x180083bad  mov     r9d, 6E6h
0x180083bb3  jmp     loc_180083B22
0x180083bb8  lea     rcx, [rdi+0Ch]; Buf1
0x180083bbc  mov     edx, r14d; Size
0x180083bbf  lea     r8, [rsp+88h+var_50]
0x180083bc4  call    GetCompositeMlKemParamSetInfo
0x180083bc9  mov     ebx, eax
0x180083bcb  test    eax, eax
0x180083bcd  jns     short loc_180083BD7
0x180083bcf  mov     r9d, 6F0h
0x180083bd5  jmp     short loc_180083B5D
0x180083bd7  mov     r15, [rsp+88h+var_50]
0x180083bdc  mov     ecx, [r15+1Ch]
0x180083be0  call    SymCryptCompositeMlKemkeyAllocate
0x180083be5  mov     rsi, rax
0x180083be8  test    rax, rax
0x180083beb  jnz     short loc_180083C02
0x180083bed  mov     ebx, 0C0000017h
0x180083bf2  mov     r9d, 6F8h
0x180083bf8  mov     ecx, 0C0000017h
0x180083bfd  jmp     loc_180083B2C
0x180083c02  mov     r9d, [rbp+0Ch]
0x180083c06  lea     rcx, [rdi+0Ch]
0x180083c0a  mov     r8d, [r13+14h]
0x180083c0e  add     rcx, r14; Src
0x180083c11  mov     rdx, r12; Size
0x180083c14  mov     [rsp+88h+var_68], rsi; __int64
0x180083c19  call    SymCryptCompositeMlKemkeySetValue
0x180083c1e  test    eax, eax
0x180083c20  jz      short loc_180083C50
0x180083c22  mov     ecx, eax
0x180083c24  call    SymcryptErrorCodeToNtStatus
0x180083c29  mov     ecx, eax
0x180083c2b  lea     r8, aOnecoreDsSecur_38; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180083c32  mov     r9d, 700h
0x180083c38  lea     rdx, aStatus; "Status"
0x180083c3f  mov     ebx, eax
0x180083c41  call    DebugTraceError
0x180083c46  mov     rcx, rsi
0x180083c49  call    SymCryptCompositeMlKemkeyFree
0x180083c4e  jmp     short loc_180083C58
0x180083c50  mov     [rbp+20h], rsi
0x180083c54  mov     [rbp+18h], r15
0x180083c58  mov     eax, ebx
0x180083c5a  add     rsp, 48h
0x180083c5e  pop     r15
0x180083c60  pop     r14
0x180083c62  pop     r13
0x180083c64  pop     r12
0x180083c66  pop     rdi
0x180083c67  pop     rsi
0x180083c68  pop     rbp
0x180083c69  pop     rbx
0x180083c6a  retn
```
