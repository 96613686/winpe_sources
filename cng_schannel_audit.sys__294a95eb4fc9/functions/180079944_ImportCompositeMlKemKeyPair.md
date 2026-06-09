# ImportCompositeMlKemKeyPair

- ea: `0x180079944`
- end: `0x180079ac4`
- name: `ImportCompositeMlKemKeyPair`
- size: `384`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18007a660`

## callees

- `0x18000743c`
- `0x180047ce0`
- `0x18007963c`
- `0x1800796f4`
- `0x180079944`
- `0x18008eaf0`
- `0x18008ebb0`
- `0x18008ed34`

## string_xrefs

- `0x18007998b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\kem.c`
- `0x180079a83`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\kem.c`

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
0x180079944  push    rbx
0x180079946  push    rbp
0x180079947  push    rsi
0x180079948  push    rdi
0x180079949  push    r12
0x18007994b  push    r13
0x18007994d  push    r14
0x18007994f  push    r15
0x180079951  sub     rsp, 48h
0x180079955  mov     [rsp+88h+var_58], 0
0x18007995e  mov     rbp, r9
0x180079961  mov     [rsp+88h+var_50], 0
0x18007996a  mov     esi, edx
0x18007996c  mov     rdi, rcx
0x18007996f  cmp     edx, 0Ch
0x180079972  jnb     short loc_18007999C
0x180079974  mov     r9d, 6AEh
0x18007997a  mov     ebx, 0C000000Dh
0x18007997f  mov     ecx, 0C000000Dh
0x180079984  lea     rdx, aStatus; "Status"
0x18007998b  lea     r8, aOnecoreDsSecur_38; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180079992  call    DebugTraceError
0x180079997  jmp     loc_180079AB0
0x18007999c  lea     rdx, [rsp+88h+var_58]
0x1800799a1  mov     rcx, r8
0x1800799a4  call    GetCompositeMlKemBlobInfo
0x1800799a9  mov     ebx, eax
0x1800799ab  test    eax, eax
0x1800799ad  jns     short loc_1800799B9
0x1800799af  mov     r9d, 6B5h
0x1800799b5  mov     ecx, eax
0x1800799b7  jmp     short loc_180079984
0x1800799b9  mov     r13, [rsp+88h+var_58]
0x1800799be  mov     eax, [r13+10h]
0x1800799c2  cmp     [rdi], eax
0x1800799c4  jz      short loc_1800799CE
0x1800799c6  mov     r9d, 6BEh
0x1800799cc  jmp     short loc_18007997A
0x1800799ce  mov     r14d, [rdi+4]
0x1800799d2  lea     eax, [r14+0Ch]
0x1800799d6  cmp     eax, 0Ch
0x1800799d9  jnb     short loc_1800799ED
0x1800799db  mov     r9d, 6CAh
0x1800799e1  mov     ebx, 0C0000095h
0x1800799e6  mov     ecx, 0C0000095h
0x1800799eb  jmp     short loc_180079984
0x1800799ed  mov     r12d, [rdi+8]
0x1800799f1  lea     ecx, [r12+rax]
0x1800799f5  cmp     ecx, eax
0x1800799f7  jnb     short loc_180079A01
0x1800799f9  mov     r9d, 6D1h
0x1800799ff  jmp     short loc_1800799E1
0x180079a01  cmp     esi, ecx
0x180079a03  jnb     short loc_180079A10
0x180079a05  mov     r9d, 6D8h
0x180079a0b  jmp     loc_18007997A
0x180079a10  lea     rcx, [rdi+0Ch]; Buf1
0x180079a14  mov     edx, r14d; Size
0x180079a17  lea     r8, [rsp+88h+var_50]
0x180079a1c  call    GetCompositeMlKemParamSetInfo
0x180079a21  mov     ebx, eax
0x180079a23  test    eax, eax
0x180079a25  jns     short loc_180079A2F
0x180079a27  mov     r9d, 6E2h
0x180079a2d  jmp     short loc_1800799B5
0x180079a2f  mov     r15, [rsp+88h+var_50]
0x180079a34  mov     ecx, [r15+1Ch]
0x180079a38  call    SymCryptCompositeMlKemkeyAllocate
0x180079a3d  mov     rsi, rax
0x180079a40  test    rax, rax
0x180079a43  jnz     short loc_180079A5A
0x180079a45  mov     ebx, 0C0000017h
0x180079a4a  mov     r9d, 6EAh
0x180079a50  mov     ecx, 0C0000017h
0x180079a55  jmp     loc_180079984
0x180079a5a  mov     r9d, [rbp+0Ch]
0x180079a5e  lea     rcx, [rdi+0Ch]
0x180079a62  mov     r8d, [r13+14h]
0x180079a66  add     rcx, r14; Src
0x180079a69  mov     rdx, r12; Size
0x180079a6c  mov     [rsp+88h+var_68], rsi; __int64
0x180079a71  call    SymCryptCompositeMlKemkeySetValue
0x180079a76  test    eax, eax
0x180079a78  jz      short loc_180079AA8
0x180079a7a  mov     ecx, eax
0x180079a7c  call    SymcryptErrorCodeToNtStatus
0x180079a81  mov     ecx, eax
0x180079a83  lea     r8, aOnecoreDsSecur_38; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180079a8a  mov     r9d, 6F2h
0x180079a90  lea     rdx, aStatus; "Status"
0x180079a97  mov     ebx, eax
0x180079a99  call    DebugTraceError
0x180079a9e  mov     rcx, rsi
0x180079aa1  call    SymCryptCompositeMlKemkeyFree
0x180079aa6  jmp     short loc_180079AB0
0x180079aa8  mov     [rbp+20h], rsi
0x180079aac  mov     [rbp+18h], r15
0x180079ab0  mov     eax, ebx
0x180079ab2  add     rsp, 48h
0x180079ab6  pop     r15
0x180079ab8  pop     r14
0x180079aba  pop     r13
0x180079abc  pop     r12
0x180079abe  pop     rdi
0x180079abf  pop     rsi
0x180079ac0  pop     rbp
0x180079ac1  pop     rbx
0x180079ac2  retn
```
