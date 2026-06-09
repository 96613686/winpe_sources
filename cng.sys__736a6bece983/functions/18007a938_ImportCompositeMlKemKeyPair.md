# ImportCompositeMlKemKeyPair

- ea: `0x18007a938`
- end: `0x18007aab8`
- name: `ImportCompositeMlKemKeyPair`
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
- `0x18007a630`
- `0x18007a6e8`
- `0x18007a938`
- `0x180090554`
- `0x180090614`
- `0x180090798`

## string_xrefs

- `0x18007a97f`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\kem.c`
- `0x18007aa77`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\kem.c`

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
    v7 = 1710;
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
    v7 = 1717;
LABEL_7:
    v9 = (unsigned int)CompositeMlKemBlobInfo;
    goto LABEL_4;
  }
  if ( *a1 != *(_DWORD *)(v19 + 16) )
  {
    v7 = 1726;
    goto LABEL_3;
  }
  v11 = (unsigned int)a1[1];
  v12 = v11 + 12;
  if ( (unsigned int)v11 >= 0xFFFFFFF4 )
  {
    v7 = 1738;
LABEL_12:
    LODWORD(v8) = -1073741675;
    v9 = 3221225621LL;
    goto LABEL_4;
  }
  v13 = (unsigned int)a1[2];
  if ( (unsigned int)v13 + v12 < v12 )
  {
    v7 = 1745;
    goto LABEL_12;
  }
  if ( a2 < (unsigned int)v13 + v12 )
  {
    v7 = 1752;
    goto LABEL_3;
  }
  CompositeMlKemBlobInfo = GetCompositeMlKemParamSetInfo(a1 + 3, (unsigned int)v11);
  LODWORD(v8) = CompositeMlKemBlobInfo;
  if ( CompositeMlKemBlobInfo < 0 )
  {
    v7 = 1762;
    goto LABEL_7;
  }
  v14 = v20;
  v15 = SymCryptCompositeMlKemkeyAllocate(*(unsigned int *)(v20 + 28));
  v16 = v15;
  if ( !v15 )
  {
    LODWORD(v8) = -1073741801;
    v7 = 1770;
    v9 = 3221225495LL;
    goto LABEL_4;
  }
  v17 = SymCryptCompositeMlKemkeySetValue((char *)a1 + v11 + 12, v13, v15);
  if ( v17 )
  {
    v8 = (unsigned int)SymcryptErrorCodeToNtStatus(v17);
    DebugTraceError(v8, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\kem.c", 1778);
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
0x18007a938  push    rbx
0x18007a93a  push    rbp
0x18007a93b  push    rsi
0x18007a93c  push    rdi
0x18007a93d  push    r12
0x18007a93f  push    r13
0x18007a941  push    r14
0x18007a943  push    r15
0x18007a945  sub     rsp, 48h
0x18007a949  mov     [rsp+88h+var_58], 0
0x18007a952  mov     rbp, r9
0x18007a955  mov     [rsp+88h+var_50], 0
0x18007a95e  mov     esi, edx
0x18007a960  mov     rdi, rcx
0x18007a963  cmp     edx, 0Ch
0x18007a966  jnb     short loc_18007A990
0x18007a968  mov     r9d, 6AEh
0x18007a96e  mov     ebx, 0C000000Dh
0x18007a973  mov     ecx, 0C000000Dh
0x18007a978  lea     rdx, aStatus; "Status"
0x18007a97f  lea     r8, aOnecoreDsSecur_38; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007a986  call    DebugTraceError
0x18007a98b  jmp     loc_18007AAA4
0x18007a990  lea     rdx, [rsp+88h+var_58]
0x18007a995  mov     rcx, r8
0x18007a998  call    GetCompositeMlKemBlobInfo
0x18007a99d  mov     ebx, eax
0x18007a99f  test    eax, eax
0x18007a9a1  jns     short loc_18007A9AD
0x18007a9a3  mov     r9d, 6B5h
0x18007a9a9  mov     ecx, eax
0x18007a9ab  jmp     short loc_18007A978
0x18007a9ad  mov     r13, [rsp+88h+var_58]
0x18007a9b2  mov     eax, [r13+10h]
0x18007a9b6  cmp     [rdi], eax
0x18007a9b8  jz      short loc_18007A9C2
0x18007a9ba  mov     r9d, 6BEh
0x18007a9c0  jmp     short loc_18007A96E
0x18007a9c2  mov     r14d, [rdi+4]
0x18007a9c6  lea     eax, [r14+0Ch]
0x18007a9ca  cmp     eax, 0Ch
0x18007a9cd  jnb     short loc_18007A9E1
0x18007a9cf  mov     r9d, 6CAh
0x18007a9d5  mov     ebx, 0C0000095h
0x18007a9da  mov     ecx, 0C0000095h
0x18007a9df  jmp     short loc_18007A978
0x18007a9e1  mov     r12d, [rdi+8]
0x18007a9e5  lea     ecx, [r12+rax]
0x18007a9e9  cmp     ecx, eax
0x18007a9eb  jnb     short loc_18007A9F5
0x18007a9ed  mov     r9d, 6D1h
0x18007a9f3  jmp     short loc_18007A9D5
0x18007a9f5  cmp     esi, ecx
0x18007a9f7  jnb     short loc_18007AA04
0x18007a9f9  mov     r9d, 6D8h
0x18007a9ff  jmp     loc_18007A96E
0x18007aa04  lea     rcx, [rdi+0Ch]; Buf1
0x18007aa08  mov     edx, r14d; Size
0x18007aa0b  lea     r8, [rsp+88h+var_50]
0x18007aa10  call    GetCompositeMlKemParamSetInfo
0x18007aa15  mov     ebx, eax
0x18007aa17  test    eax, eax
0x18007aa19  jns     short loc_18007AA23
0x18007aa1b  mov     r9d, 6E2h
0x18007aa21  jmp     short loc_18007A9A9
0x18007aa23  mov     r15, [rsp+88h+var_50]
0x18007aa28  mov     ecx, [r15+1Ch]
0x18007aa2c  call    SymCryptCompositeMlKemkeyAllocate
0x18007aa31  mov     rsi, rax
0x18007aa34  test    rax, rax
0x18007aa37  jnz     short loc_18007AA4E
0x18007aa39  mov     ebx, 0C0000017h
0x18007aa3e  mov     r9d, 6EAh
0x18007aa44  mov     ecx, 0C0000017h
0x18007aa49  jmp     loc_18007A978
0x18007aa4e  mov     r9d, [rbp+0Ch]
0x18007aa52  lea     rcx, [rdi+0Ch]
0x18007aa56  mov     r8d, [r13+14h]
0x18007aa5a  add     rcx, r14; Src
0x18007aa5d  mov     rdx, r12; Size
0x18007aa60  mov     [rsp+88h+var_68], rsi; __int64
0x18007aa65  call    SymCryptCompositeMlKemkeySetValue
0x18007aa6a  test    eax, eax
0x18007aa6c  jz      short loc_18007AA9C
0x18007aa6e  mov     ecx, eax
0x18007aa70  call    SymcryptErrorCodeToNtStatus
0x18007aa75  mov     ecx, eax
0x18007aa77  lea     r8, aOnecoreDsSecur_38; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007aa7e  mov     r9d, 6F2h
0x18007aa84  lea     rdx, aStatus; "Status"
0x18007aa8b  mov     ebx, eax
0x18007aa8d  call    DebugTraceError
0x18007aa92  mov     rcx, rsi
0x18007aa95  call    SymCryptCompositeMlKemkeyFree
0x18007aa9a  jmp     short loc_18007AAA4
0x18007aa9c  mov     [rbp+20h], rsi
0x18007aaa0  mov     [rbp+18h], r15
0x18007aaa4  mov     eax, ebx
0x18007aaa6  add     rsp, 48h
0x18007aaaa  pop     r15
0x18007aaac  pop     r14
0x18007aaae  pop     r13
0x18007aab0  pop     r12
0x18007aab2  pop     rdi
0x18007aab3  pop     rsi
0x18007aab4  pop     rbp
0x18007aab5  pop     rbx
0x18007aab6  retn
```
