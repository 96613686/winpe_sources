# ImportMlKemKeyPair

- ea: `0x180083c74`
- end: `0x180083df4`
- name: `ImportMlKemKeyPair`
- size: `384`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180084860`

## callees

- `0x180001230`
- `0x1800012f0`
- `0x1800013a0`
- `0x18001155c`
- `0x180051dd0`
- `0x180083940`
- `0x1800839f8`
- `0x180083c74`

## string_xrefs

- `0x180083cbb`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\kem.c`
- `0x180083db3`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\kem.c`

## pseudocode

```c
__int64 __fastcall ImportMlKemKeyPair(_DWORD *a1, unsigned int a2, __int64 a3, __int64 a4)
{
  __int64 v7; // r9
  __int64 v8; // rbx
  __int64 v9; // rcx
  int MlKemBlobInfo; // eax
  __int64 v11; // r13
  __int64 v12; // r14
  unsigned int v13; // eax
  __int64 v14; // r12
  __int64 v15; // r15
  __int64 v16; // rax
  __int64 v17; // rsi
  unsigned int v18; // eax
  __int64 v20; // [rsp+30h] [rbp-58h] BYREF
  __int64 v21; // [rsp+38h] [rbp-50h]

  v20 = 0;
  v21 = 0;
  if ( a2 < 0xC )
  {
    v7 = 1613;
LABEL_3:
    LODWORD(v8) = -1073741811;
    v9 = 3221225485LL;
LABEL_4:
    DebugTraceError(v9, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\kem.c", v7);
    return (unsigned int)v8;
  }
  MlKemBlobInfo = GetMlKemBlobInfo(a3, &v20);
  LODWORD(v8) = MlKemBlobInfo;
  if ( MlKemBlobInfo < 0 )
  {
    v7 = 1620;
LABEL_7:
    v9 = (unsigned int)MlKemBlobInfo;
    goto LABEL_4;
  }
  v11 = v20;
  if ( *a1 != *(_DWORD *)(v20 + 16) )
  {
    v7 = 1629;
    goto LABEL_3;
  }
  v12 = (unsigned int)a1[1];
  v13 = v12 + 12;
  if ( (unsigned int)v12 >= 0xFFFFFFF4 )
  {
    v7 = 1641;
LABEL_12:
    LODWORD(v8) = -1073741675;
    v9 = 3221225621LL;
    goto LABEL_4;
  }
  v14 = (unsigned int)a1[2];
  if ( (unsigned int)v14 + v13 < v13 )
  {
    v7 = 1648;
    goto LABEL_12;
  }
  if ( a2 < (unsigned int)v14 + v13 )
  {
    v7 = 1655;
    goto LABEL_3;
  }
  MlKemBlobInfo = GetMlKemParamSetInfo(a1 + 3, (unsigned int)v12);
  LODWORD(v8) = MlKemBlobInfo;
  if ( MlKemBlobInfo < 0 )
  {
    v7 = 1665;
    goto LABEL_7;
  }
  v15 = v21;
  v16 = SymCryptMlKemkeyAllocate(*(unsigned int *)(v21 + 28));
  v17 = v16;
  if ( !v16 )
  {
    LODWORD(v8) = -1073741801;
    v7 = 1673;
    v9 = 3221225495LL;
    goto LABEL_4;
  }
  v18 = SymCryptMlKemkeySetValue(
          (char *)a1 + v12 + 12,
          v14,
          *(unsigned int *)(v11 + 20),
          *(unsigned int *)(a4 + 12),
          v16);
  if ( v18 )
  {
    v8 = (unsigned int)SymcryptErrorCodeToNtStatus(v18);
    DebugTraceError(v8, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\kem.c", 1681);
    SymCryptMlKemkeyFree(v17);
  }
  else
  {
    *(_QWORD *)(a4 + 32) = v17;
    *(_QWORD *)(a4 + 24) = v15;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180083c74  push    rbx
0x180083c76  push    rbp
0x180083c77  push    rsi
0x180083c78  push    rdi
0x180083c79  push    r12
0x180083c7b  push    r13
0x180083c7d  push    r14
0x180083c7f  push    r15
0x180083c81  sub     rsp, 48h
0x180083c85  mov     [rsp+88h+var_58], 0
0x180083c8e  mov     rbp, r9
0x180083c91  mov     [rsp+88h+var_50], 0
0x180083c9a  mov     esi, edx
0x180083c9c  mov     rdi, rcx
0x180083c9f  cmp     edx, 0Ch
0x180083ca2  jnb     short loc_180083CCC
0x180083ca4  mov     r9d, 64Dh
0x180083caa  mov     ebx, 0C000000Dh
0x180083caf  mov     ecx, 0C000000Dh
0x180083cb4  lea     rdx, aStatus; "Status"
0x180083cbb  lea     r8, aOnecoreDsSecur_38; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180083cc2  call    DebugTraceError
0x180083cc7  jmp     loc_180083DE0
0x180083ccc  lea     rdx, [rsp+88h+var_58]
0x180083cd1  mov     rcx, r8
0x180083cd4  call    GetMlKemBlobInfo
0x180083cd9  mov     ebx, eax
0x180083cdb  test    eax, eax
0x180083cdd  jns     short loc_180083CE9
0x180083cdf  mov     r9d, 654h
0x180083ce5  mov     ecx, eax
0x180083ce7  jmp     short loc_180083CB4
0x180083ce9  mov     r13, [rsp+88h+var_58]
0x180083cee  mov     eax, [r13+10h]
0x180083cf2  cmp     [rdi], eax
0x180083cf4  jz      short loc_180083CFE
0x180083cf6  mov     r9d, 65Dh
0x180083cfc  jmp     short loc_180083CAA
0x180083cfe  mov     r14d, [rdi+4]
0x180083d02  lea     eax, [r14+0Ch]
0x180083d06  cmp     eax, 0Ch
0x180083d09  jnb     short loc_180083D1D
0x180083d0b  mov     r9d, 669h
0x180083d11  mov     ebx, 0C0000095h
0x180083d16  mov     ecx, 0C0000095h
0x180083d1b  jmp     short loc_180083CB4
0x180083d1d  mov     r12d, [rdi+8]
0x180083d21  lea     ecx, [r12+rax]
0x180083d25  cmp     ecx, eax
0x180083d27  jnb     short loc_180083D31
0x180083d29  mov     r9d, 670h
0x180083d2f  jmp     short loc_180083D11
0x180083d31  cmp     esi, ecx
0x180083d33  jnb     short loc_180083D40
0x180083d35  mov     r9d, 677h
0x180083d3b  jmp     loc_180083CAA
0x180083d40  lea     rcx, [rdi+0Ch]; Buf1
0x180083d44  mov     edx, r14d; Size
0x180083d47  lea     r8, [rsp+88h+var_50]
0x180083d4c  call    GetMlKemParamSetInfo
0x180083d51  mov     ebx, eax
0x180083d53  test    eax, eax
0x180083d55  jns     short loc_180083D5F
0x180083d57  mov     r9d, 681h
0x180083d5d  jmp     short loc_180083CE5
0x180083d5f  mov     r15, [rsp+88h+var_50]
0x180083d64  mov     ecx, [r15+1Ch]
0x180083d68  call    SymCryptMlKemkeyAllocate
0x180083d6d  mov     rsi, rax
0x180083d70  test    rax, rax
0x180083d73  jnz     short loc_180083D8A
0x180083d75  mov     ebx, 0C0000017h
0x180083d7a  mov     r9d, 689h
0x180083d80  mov     ecx, 0C0000017h
0x180083d85  jmp     loc_180083CB4
0x180083d8a  mov     r9d, [rbp+0Ch]
0x180083d8e  lea     rcx, [rdi+0Ch]
0x180083d92  mov     r8d, [r13+14h]
0x180083d96  add     rcx, r14
0x180083d99  mov     rdx, r12
0x180083d9c  mov     [rsp+88h+var_68], rsi
0x180083da1  call    SymCryptMlKemkeySetValue
0x180083da6  test    eax, eax
0x180083da8  jz      short loc_180083DD8
0x180083daa  mov     ecx, eax
0x180083dac  call    SymcryptErrorCodeToNtStatus
0x180083db1  mov     ecx, eax
0x180083db3  lea     r8, aOnecoreDsSecur_38; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180083dba  mov     r9d, 691h
0x180083dc0  lea     rdx, aStatus; "Status"
0x180083dc7  mov     ebx, eax
0x180083dc9  call    DebugTraceError
0x180083dce  mov     rcx, rsi
0x180083dd1  call    SymCryptMlKemkeyFree
0x180083dd6  jmp     short loc_180083DE0
0x180083dd8  mov     [rbp+20h], rsi
0x180083ddc  mov     [rbp+18h], r15
0x180083de0  mov     eax, ebx
0x180083de2  add     rsp, 48h
0x180083de6  pop     r15
0x180083de8  pop     r14
0x180083dea  pop     r13
0x180083dec  pop     r12
0x180083dee  pop     rdi
0x180083def  pop     rsi
0x180083df0  pop     rbp
0x180083df1  pop     rbx
0x180083df2  retn
```
