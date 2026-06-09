# ImportMlKemKeyPair

- ea: `0x18007aac0`
- end: `0x18007ac40`
- name: `ImportMlKemKeyPair`
- size: `384`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18007b650`

## callees

- `0x18000743c`
- `0x180048770`
- `0x18007a78c`
- `0x18007a844`
- `0x18007aac0`
- `0x18008ee5c`
- `0x18008f538`
- `0x18008fa3c`

## string_xrefs

- `0x18007ab07`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\kem.c`
- `0x18007abff`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\kem.c`

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
0x18007aac0  push    rbx
0x18007aac2  push    rbp
0x18007aac3  push    rsi
0x18007aac4  push    rdi
0x18007aac5  push    r12
0x18007aac7  push    r13
0x18007aac9  push    r14
0x18007aacb  push    r15
0x18007aacd  sub     rsp, 48h
0x18007aad1  mov     [rsp+88h+var_58], 0
0x18007aada  mov     rbp, r9
0x18007aadd  mov     [rsp+88h+var_50], 0
0x18007aae6  mov     esi, edx
0x18007aae8  mov     rdi, rcx
0x18007aaeb  cmp     edx, 0Ch
0x18007aaee  jnb     short loc_18007AB18
0x18007aaf0  mov     r9d, 63Fh
0x18007aaf6  mov     ebx, 0C000000Dh
0x18007aafb  mov     ecx, 0C000000Dh
0x18007ab00  lea     rdx, aStatus; "Status"
0x18007ab07  lea     r8, aOnecoreDsSecur_38; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007ab0e  call    DebugTraceError
0x18007ab13  jmp     loc_18007AC2C
0x18007ab18  lea     rdx, [rsp+88h+var_58]
0x18007ab1d  mov     rcx, r8
0x18007ab20  call    GetMlKemBlobInfo
0x18007ab25  mov     ebx, eax
0x18007ab27  test    eax, eax
0x18007ab29  jns     short loc_18007AB35
0x18007ab2b  mov     r9d, 646h
0x18007ab31  mov     ecx, eax
0x18007ab33  jmp     short loc_18007AB00
0x18007ab35  mov     r13, [rsp+88h+var_58]
0x18007ab3a  mov     eax, [r13+10h]
0x18007ab3e  cmp     [rdi], eax
0x18007ab40  jz      short loc_18007AB4A
0x18007ab42  mov     r9d, 64Fh
0x18007ab48  jmp     short loc_18007AAF6
0x18007ab4a  mov     r14d, [rdi+4]
0x18007ab4e  lea     eax, [r14+0Ch]
0x18007ab52  cmp     eax, 0Ch
0x18007ab55  jnb     short loc_18007AB69
0x18007ab57  mov     r9d, 65Bh
0x18007ab5d  mov     ebx, 0C0000095h
0x18007ab62  mov     ecx, 0C0000095h
0x18007ab67  jmp     short loc_18007AB00
0x18007ab69  mov     r12d, [rdi+8]
0x18007ab6d  lea     ecx, [r12+rax]
0x18007ab71  cmp     ecx, eax
0x18007ab73  jnb     short loc_18007AB7D
0x18007ab75  mov     r9d, 662h
0x18007ab7b  jmp     short loc_18007AB5D
0x18007ab7d  cmp     esi, ecx
0x18007ab7f  jnb     short loc_18007AB8C
0x18007ab81  mov     r9d, 669h
0x18007ab87  jmp     loc_18007AAF6
0x18007ab8c  lea     rcx, [rdi+0Ch]; Buf1
0x18007ab90  mov     edx, r14d; Size
0x18007ab93  lea     r8, [rsp+88h+var_50]
0x18007ab98  call    GetMlKemParamSetInfo
0x18007ab9d  mov     ebx, eax
0x18007ab9f  test    eax, eax
0x18007aba1  jns     short loc_18007ABAB
0x18007aba3  mov     r9d, 673h
0x18007aba9  jmp     short loc_18007AB31
0x18007abab  mov     r15, [rsp+88h+var_50]
0x18007abb0  mov     ecx, [r15+1Ch]
0x18007abb4  call    SymCryptMlKemkeyAllocate
0x18007abb9  mov     rsi, rax
0x18007abbc  test    rax, rax
0x18007abbf  jnz     short loc_18007ABD6
0x18007abc1  mov     ebx, 0C0000017h
0x18007abc6  mov     r9d, 67Bh
0x18007abcc  mov     ecx, 0C0000017h
0x18007abd1  jmp     loc_18007AB00
0x18007abd6  mov     r9d, [rbp+0Ch]
0x18007abda  lea     rcx, [rdi+0Ch]
0x18007abde  mov     r8d, [r13+14h]
0x18007abe2  add     rcx, r14; Src
0x18007abe5  mov     rdx, r12
0x18007abe8  mov     [rsp+88h+var_68], rsi; __int64
0x18007abed  call    SymCryptMlKemkeySetValue
0x18007abf2  test    eax, eax
0x18007abf4  jz      short loc_18007AC24
0x18007abf6  mov     ecx, eax
0x18007abf8  call    SymcryptErrorCodeToNtStatus
0x18007abfd  mov     ecx, eax
0x18007abff  lea     r8, aOnecoreDsSecur_38; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007ac06  mov     r9d, 683h
0x18007ac0c  lea     rdx, aStatus; "Status"
0x18007ac13  mov     ebx, eax
0x18007ac15  call    DebugTraceError
0x18007ac1a  mov     rcx, rsi
0x18007ac1d  call    SymCryptMlKemkeyFree
0x18007ac22  jmp     short loc_18007AC2C
0x18007ac24  mov     [rbp+20h], rsi
0x18007ac28  mov     [rbp+18h], r15
0x18007ac2c  mov     eax, ebx
0x18007ac2e  add     rsp, 48h
0x18007ac32  pop     r15
0x18007ac34  pop     r14
0x18007ac36  pop     r13
0x18007ac38  pop     r12
0x18007ac3a  pop     rdi
0x18007ac3b  pop     rsi
0x18007ac3c  pop     rbp
0x18007ac3d  pop     rbx
0x18007ac3e  retn
```
