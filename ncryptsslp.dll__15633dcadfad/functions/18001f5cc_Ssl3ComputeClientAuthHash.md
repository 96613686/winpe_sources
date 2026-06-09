# Ssl3ComputeClientAuthHash

- ea: `0x18001f5cc`
- end: `0x18001fb52`
- name: `Ssl3ComputeClientAuthHash`
- size: `1414`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800133f0`

## callees

- `0x180009160`
- `0x18000b654`
- `0x1800185e0`
- `0x180018ac0`
- `0x18001f5cc`
- `0x180024ef0`
- `0x180026010`

## import_xrefs

- `bcrypt!BCryptHashData` at `0x18001f7b6`
- `bcrypt!BCryptHashData` at `0x18001f7dc`
- `bcrypt!BCryptHashData` at `0x18001f882`
- `bcrypt!BCryptHashData` at `0x18001f8aa`
- `bcrypt!BCryptHashData` at `0x18001f8d3`
- `bcrypt!BCryptHashData` at `0x18001f95c`
- `bcrypt!BCryptHashData` at `0x18001f988`
- `bcrypt!BCryptHashData` at `0x18001fa3d`
- `bcrypt!BCryptHashData` at `0x18001fa65`
- `bcrypt!BCryptHashData` at `0x18001fa8e`
- `bcrypt!BCryptHashData` at `0x18001f7b6`
- `bcrypt!BCryptHashData` at `0x18001f7dc`
- `bcrypt!BCryptHashData` at `0x18001f882`
- `bcrypt!BCryptHashData` at `0x18001f8aa`
- `bcrypt!BCryptHashData` at `0x18001f8d3`
- `bcrypt!BCryptHashData` at `0x18001f95c`
- `bcrypt!BCryptHashData` at `0x18001f988`
- `bcrypt!BCryptHashData` at `0x18001fa3d`
- `bcrypt!BCryptHashData` at `0x18001fa65`
- `bcrypt!BCryptHashData` at `0x18001fa8e`
- `bcrypt!BCryptCreateHash` at `0x18001f859`
- `bcrypt!BCryptCreateHash` at `0x18001fa17`
- `bcrypt!BCryptCreateHash` at `0x18001f859`
- `bcrypt!BCryptCreateHash` at `0x18001fa17`
- `bcrypt!BCryptDuplicateHash` at `0x18001f78a`
- `bcrypt!BCryptDuplicateHash` at `0x18001f932`
- `bcrypt!BCryptDuplicateHash` at `0x18001f78a`
- `bcrypt!BCryptDuplicateHash` at `0x18001f932`
- `bcrypt!BCryptFinishHash` at `0x18001f7ff`
- `bcrypt!BCryptFinishHash` at `0x18001f8f7`
- `bcrypt!BCryptFinishHash` at `0x18001f9ae`
- `bcrypt!BCryptFinishHash` at `0x18001fab2`
- `bcrypt!BCryptFinishHash` at `0x18001f7ff`
- `bcrypt!BCryptFinishHash` at `0x18001f8f7`
- `bcrypt!BCryptFinishHash` at `0x18001f9ae`
- `bcrypt!BCryptFinishHash` at `0x18001fab2`
- `bcrypt!BCryptDestroyHash` at `0x18001f817`
- `bcrypt!BCryptDestroyHash` at `0x18001f9c9`
- `bcrypt!BCryptDestroyHash` at `0x18001fafb`
- `bcrypt!BCryptDestroyHash` at `0x18001fb0a`
- `bcrypt!BCryptDestroyHash` at `0x18001f817`
- `bcrypt!BCryptDestroyHash` at `0x18001f9c9`
- `bcrypt!BCryptDestroyHash` at `0x18001fafb`
- `bcrypt!BCryptDestroyHash` at `0x18001fb0a`

## string_xrefs

- `0x18001fadf`: `onecore\ds\security\cryptoapi\ncrypt\schannel\ssl3key.c`

## pseudocode

```c
__int64 __fastcall Ssl3ComputeClientAuthHash(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const wchar_t *a4,
        PUCHAR a5,
        unsigned int a6,
        _DWORD *a7)
{
  unsigned int v9; // eax
  int v10; // r15d
  UCHAR *v11; // r13
  unsigned int v12; // ebx
  NTSTATUS v13; // ebx
  BCRYPT_HASH_HANDLE *p_hHash; // rdi
  unsigned __int64 v15; // rcx
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // rcx
  void *v18; // rsp
  void *v19; // rsp
  _DWORD *v20; // rax
  __int64 v21; // r9
  __int64 v22; // rcx
  UCHAR *v23; // r12
  UCHAR *v24; // rsi
  NTSTATUS v25; // eax
  __int64 v26; // r15
  UCHAR *v27; // r15
  __int64 v28; // rsi
  __int64 v30; // [rsp+0h] [rbp-40h] BYREF
  BCRYPT_HASH_HANDLE hHash; // [rsp+40h] [rbp+0h] BYREF
  BCRYPT_HASH_HANDLE phNewHash; // [rsp+48h] [rbp+8h] BYREF
  PUCHAR v33; // [rsp+50h] [rbp+10h]
  __int64 v34; // [rsp+58h] [rbp+18h]
  __int64 v35; // [rsp+60h] [rbp+20h]
  UCHAR pbOutput[16]; // [rsp+70h] [rbp+30h] BYREF
  UCHAR pbInput[24]; // [rsp+80h] [rbp+40h] BYREF

  v34 = a2;
  v35 = a1;
  hHash = 0;
  phNewHash = 0;
  if ( !wcscmp(a4, L"RSA") )
  {
    v9 = 36;
    v10 = 0;
    *a7 = 36;
    v11 = a5;
    v12 = *(_DWORD *)(a3 + 24) + *(_DWORD *)(a3 + 40);
    v33 = a5 + 16;
  }
  else
  {
    if ( wcscmp(a4, L"DSA") )
    {
      p_hHash = 0;
      v13 = -2146893783;
      v21 = 995;
      v22 = 2148073513LL;
      goto LABEL_71;
    }
    *a7 = 20;
    v10 = 1;
    v12 = *(_DWORD *)(a3 + 24);
    v9 = 20;
    v11 = 0;
    v33 = a5;
  }
  if ( !a5 )
    return 0;
  if ( a6 < v9 )
    return (unsigned int)-2146893784;
  p_hHash = 0;
  if ( !v12 )
    goto LABEL_82;
  if ( v12 > (unsigned __int64)g_ulMaxStackAllocSize )
    goto LABEL_82;
  v15 = v12 + g_ulAdditionalProbeSize + 8;
  if ( v15 < v12 || !(unsigned int)VerifyStackAvailable(v15) )
    goto LABEL_82;
  v16 = v12 + 23LL;
  if ( v16 <= (unsigned __int64)v12 + 8 )
    v16 = 0xFFFFFFFFFFFFFF0LL;
  v17 = v16 & 0xFFFFFFFFFFFFFFF0uLL;
  v18 = alloca(v17);
  v19 = alloca(v17);
  p_hHash = &hHash;
  if ( &v30 == (__int64 *)-64LL || (LODWORD(hHash) = 1801679955, (p_hHash = &phNewHash) == 0) )
  {
LABEL_82:
    if ( (unsigned __int64)v12 + 8 >= v12 )
    {
      v20 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
      p_hHash = (BCRYPT_HASH_HANDLE *)v20;
      if ( v20 )
      {
        *v20 = 1885431112;
        p_hHash = (BCRYPT_HASH_HANDLE *)(v20 + 2);
      }
    }
  }
  if ( !p_hHash )
  {
    v13 = -2146893810;
    v21 = 1016;
    v22 = 2148073486LL;
LABEL_71:
    DebugTraceError(v22, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\ssl3key.c", v21);
    goto LABEL_72;
  }
  v23 = (UCHAR *)p_hHash;
  if ( !v10 )
    v23 = (UCHAR *)(p_hHash + 2);
  v24 = 0;
  if ( !v10 )
    v24 = (UCHAR *)p_hHash;
  if ( v11 )
  {
    v25 = BCryptDuplicateHash(*(BCRYPT_HASH_HANDLE *)(a3 + 32), &phNewHash, v24, *(_DWORD *)(a3 + 40), 0);
    v13 = v25;
    if ( v25 < 0 )
    {
      v21 = 1044;
LABEL_29:
      v22 = (unsigned int)v25;
      goto LABEL_71;
    }
    v26 = v34;
    v25 = BCryptHashData(phNewHash, (PUCHAR)(v34 + 28), 0x30u, 0);
    v13 = v25;
    if ( v25 < 0 )
    {
      v21 = 1055;
      goto LABEL_29;
    }
    v25 = BCryptHashData(
            phNewHash,
            (PUCHAR)"666666666666666666666666666666666666666666666666ERROR_INVALID_PARAMETER",
            0x30u,
            0);
    v13 = v25;
    if ( v25 < 0 )
    {
      v21 = 1066;
      goto LABEL_29;
    }
    v25 = BCryptFinishHash(phNewHash, pbOutput, 0x10u, 0);
    v13 = v25;
    if ( v25 < 0 )
    {
      v21 = 1077;
      goto LABEL_29;
    }
    v13 = BCryptDestroyHash(phNewHash);
    phNewHash = 0;
    if ( v13 < 0 )
    {
      v21 = 1086;
      v22 = (unsigned int)v13;
      goto LABEL_71;
    }
    v25 = BCryptCreateHash(*(BCRYPT_ALG_HANDLE *)(v35 + 304), &phNewHash, v24, *(_DWORD *)(a3 + 40), 0, 0, 0);
    v13 = v25;
    if ( v25 < 0 )
    {
      v21 = 1103;
      goto LABEL_29;
    }
    v25 = BCryptHashData(phNewHash, (PUCHAR)(v26 + 28), 0x30u, 0);
    v13 = v25;
    if ( v25 < 0 )
    {
      v21 = 1114;
      goto LABEL_29;
    }
    v25 = BCryptHashData(phNewHash, (PUCHAR)&g_rgbPad2, 0x30u, 0);
    v13 = v25;
    if ( v25 < 0 )
    {
      v21 = 1125;
      goto LABEL_29;
    }
    v25 = BCryptHashData(phNewHash, pbOutput, 0x10u, 0);
    v13 = v25;
    if ( v25 < 0 )
    {
      v21 = 1136;
      goto LABEL_29;
    }
    v25 = BCryptFinishHash(phNewHash, v11, 0x10u, 0);
    v13 = v25;
    if ( v25 < 0 )
    {
      v21 = 1147;
      goto LABEL_29;
    }
  }
  v27 = v33;
  if ( v33 )
  {
    v25 = BCryptDuplicateHash(*(BCRYPT_HASH_HANDLE *)(a3 + 16), &hHash, v23, *(_DWORD *)(a3 + 24), 0);
    v13 = v25;
    if ( v25 < 0 )
    {
      v21 = 1167;
      goto LABEL_29;
    }
    v28 = v34;
    v25 = BCryptHashData(hHash, (PUCHAR)(v34 + 28), 0x30u, 0);
    v13 = v25;
    if ( v25 < 0 )
    {
      v21 = 1178;
      goto LABEL_29;
    }
    v25 = BCryptHashData(
            hHash,
            (PUCHAR)"666666666666666666666666666666666666666666666666ERROR_INVALID_PARAMETER",
            0x28u,
            0);
    v13 = v25;
    if ( v25 < 0 )
    {
      v21 = 1189;
      goto LABEL_29;
    }
    v25 = BCryptFinishHash(hHash, pbInput, 0x14u, 0);
    v13 = v25;
    if ( v25 < 0 )
    {
      v21 = 1200;
      goto LABEL_29;
    }
    v25 = BCryptDestroyHash(hHash);
    hHash = 0;
    v13 = v25;
    if ( v25 < 0 )
    {
      v21 = 1209;
      goto LABEL_29;
    }
    v25 = BCryptCreateHash(*(BCRYPT_ALG_HANDLE *)(v35 + 336), &hHash, v23, *(_DWORD *)(a3 + 24), 0, 0, 0);
    v13 = v25;
    if ( v25 < 0 )
    {
      v21 = 1226;
      goto LABEL_29;
    }
    v25 = BCryptHashData(hHash, (PUCHAR)(v28 + 28), 0x30u, 0);
    v13 = v25;
    if ( v25 < 0 )
    {
      v21 = 1237;
      goto LABEL_29;
    }
    v25 = BCryptHashData(hHash, (PUCHAR)&g_rgbPad2, 0x28u, 0);
    v13 = v25;
    if ( v25 < 0 )
    {
      v21 = 1248;
      goto LABEL_29;
    }
    v25 = BCryptHashData(hHash, pbInput, 0x14u, 0);
    v13 = v25;
    if ( v25 < 0 )
    {
      v21 = 1259;
      goto LABEL_29;
    }
    v25 = BCryptFinishHash(hHash, v27, 0x14u, 0);
    v13 = v25;
    if ( v25 < 0 )
    {
      v21 = 1270;
      goto LABEL_29;
    }
  }
  v13 = 0;
LABEL_72:
  if ( hHash )
    BCryptDestroyHash(hHash);
  if ( phNewHash )
    BCryptDestroyHash(phNewHash);
  if ( p_hHash && *((_DWORD *)p_hHash - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18001f5cc  push    rbp
0x18001f5ce  push    rsi
0x18001f5cf  push    rdi
0x18001f5d0  push    r12
0x18001f5d2  push    r13
0x18001f5d4  push    r14
0x18001f5d6  push    r15
0x18001f5d8  sub     rsp, 0A0h
0x18001f5df  lea     rbp, [rsp+40h]
0x18001f5e4  mov     [rbp+90h+arg_18], rbx
0x18001f5eb  mov     rax, cs:__security_cookie
0x18001f5f2  xor     rax, rbp
0x18001f5f5  mov     [rbp+90h+var_38], rax
0x18001f5f9  mov     rdi, [rbp+90h+arg_20]
0x18001f600  mov     rsi, r9
0x18001f603  mov     rbx, [rbp+90h+arg_30]
0x18001f60a  mov     r14, r8
0x18001f60d  mov     [rbp+90h+var_78], rdx
0x18001f611  lea     rdx, aRsa; "RSA"
0x18001f618  mov     [rbp+90h+var_70], rcx
0x18001f61c  mov     rcx, r9; String1
0x18001f61f  mov     [rbp+90h+hHash], 0
0x18001f627  mov     [rbp+90h+phNewHash], 0
0x18001f62f  call    wcscmp
0x18001f634  mov     r12d, 14h
0x18001f63a  test    eax, eax
0x18001f63c  jnz     short loc_18001F65D
0x18001f63e  lea     eax, [r12+10h]
0x18001f643  xor     r15d, r15d
0x18001f646  mov     [rbx], eax
0x18001f648  lea     rcx, [rdi+10h]
0x18001f64c  mov     ebx, [r14+28h]
0x18001f650  mov     r13, rdi
0x18001f653  add     ebx, [r14+18h]
0x18001f657  mov     [rbp+90h+var_80], rcx
0x18001f65b  jmp     short loc_18001F689
0x18001f65d  lea     rdx, aDsa; "DSA"
0x18001f664  mov     rcx, rsi; String1
0x18001f667  call    wcscmp
0x18001f66c  test    eax, eax
0x18001f66e  jnz     loc_18001FACD
0x18001f674  mov     [rbx], r12d
0x18001f677  lea     r15d, [rax+1]
0x18001f67b  mov     ebx, [r14+18h]
0x18001f67f  mov     eax, r12d
0x18001f682  xor     r13d, r13d
0x18001f685  mov     [rbp+90h+var_80], rdi
0x18001f689  test    rdi, rdi
0x18001f68c  jnz     short loc_18001F695
0x18001f68e  xor     ebx, ebx
0x18001f690  jmp     loc_18001FB2D
0x18001f695  cmp     [rbp+90h+arg_28], eax
0x18001f69b  jnb     short loc_18001F6A7
0x18001f69d  mov     ebx, 80090028h
0x18001f6a2  jmp     loc_18001FB2D
0x18001f6a7  xor     edi, edi
0x18001f6a9  test    ebx, ebx
0x18001f6ab  jz      short loc_18001F710
0x18001f6ad  mov     esi, ebx
0x18001f6af  cmp     rsi, cs:g_ulMaxStackAllocSize
0x18001f6b6  ja      short loc_18001F710
0x18001f6b8  mov     rcx, cs:g_ulAdditionalProbeSize
0x18001f6bf  add     rcx, 8
0x18001f6c3  add     rcx, rsi
0x18001f6c6  cmp     rcx, rsi
0x18001f6c9  jb      short loc_18001F710
0x18001f6cb  call    VerifyStackAvailable
0x18001f6d0  test    eax, eax
0x18001f6d2  jz      short loc_18001F710
0x18001f6d4  lea     rax, [rsi+8]
0x18001f6d8  lea     rcx, [rax+0Fh]
0x18001f6dc  cmp     rcx, rax
0x18001f6df  ja      short loc_18001F6EB
0x18001f6e1  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18001f6eb  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18001f6ef  mov     rax, rcx
0x18001f6f2  call    _alloca_probe
0x18001f6f7  sub     rsp, rcx
0x18001f6fa  lea     rdi, [rsp+0D0h+hHash]
0x18001f6ff  test    rdi, rdi
0x18001f702  jz      short loc_18001F710
0x18001f704  mov     dword ptr [rdi], 6B637453h
0x18001f70a  add     rdi, 8
0x18001f70e  jnz     short loc_18001F739
0x18001f710  mov     eax, ebx
0x18001f712  lea     rcx, [rax+8]
0x18001f716  cmp     rcx, rax
0x18001f719  jb      short loc_18001F739
0x18001f71b  mov     rax, cs:g_pfnAllocate
0x18001f722  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f727  mov     rdi, rax
0x18001f72a  test    rax, rax
0x18001f72d  jz      short loc_18001F739
0x18001f72f  mov     dword ptr [rax], 70616548h
0x18001f735  add     rdi, 8
0x18001f739  test    rdi, rdi
0x18001f73c  jnz     short loc_18001F753
0x18001f73e  mov     ebx, 8009000Eh
0x18001f743  mov     r9d, 3F8h
0x18001f749  mov     ecx, 8009000Eh
0x18001f74e  jmp     loc_18001FADF
0x18001f753  test    r15d, r15d
0x18001f756  lea     rax, [rdi+10h]
0x18001f75a  mov     r12, rdi
0x18001f75d  cmovz   r12, rax
0x18001f761  xor     esi, esi
0x18001f763  test    r15d, r15d
0x18001f766  cmovz   rsi, rdi
0x18001f76a  test    r13, r13
0x18001f76d  jz      loc_18001F90E
0x18001f773  mov     r9d, [r14+28h]; cbHashObject
0x18001f777  lea     rdx, [rbp+90h+phNewHash]; phNewHash
0x18001f77b  mov     rcx, [r14+20h]; hHash
0x18001f77f  mov     r8, rsi; pbHashObject
0x18001f782  mov     [rsp+0D0h+dwFlags], 0; dwFlags
0x18001f78a  call    cs:__imp_BCryptDuplicateHash
0x18001f790  mov     ebx, eax
0x18001f792  test    eax, eax
0x18001f794  jns     short loc_18001F7A3
0x18001f796  mov     r9d, 414h
0x18001f79c  mov     ecx, eax
0x18001f79e  jmp     loc_18001FADF
0x18001f7a3  mov     r15, [rbp+90h+var_78]
0x18001f7a7  xor     r9d, r9d; dwFlags
0x18001f7aa  mov     rcx, [rbp+90h+phNewHash]; hHash
0x18001f7ae  lea     r8d, [r9+30h]; cbInput
0x18001f7b2  lea     rdx, [r15+1Ch]; pbInput
0x18001f7b6  call    cs:__imp_BCryptHashData
0x18001f7bc  mov     ebx, eax
0x18001f7be  test    eax, eax
0x18001f7c0  jns     short loc_18001F7CA
0x18001f7c2  mov     r9d, 41Fh
0x18001f7c8  jmp     short loc_18001F79C
0x18001f7ca  mov     rcx, [rbp+90h+phNewHash]; hHash
0x18001f7ce  lea     rdx, g_rgbPad1; "666666666666666666666666666666666666666"...
0x18001f7d5  xor     r9d, r9d; dwFlags
0x18001f7d8  lea     r8d, [r9+30h]; cbInput
0x18001f7dc  call    cs:__imp_BCryptHashData
0x18001f7e2  mov     ebx, eax
0x18001f7e4  test    eax, eax
0x18001f7e6  jns     short loc_18001F7F0
0x18001f7e8  mov     r9d, 42Ah
0x18001f7ee  jmp     short loc_18001F79C
0x18001f7f0  mov     rcx, [rbp+90h+phNewHash]; hHash
0x18001f7f4  lea     rdx, [rbp+90h+pbOutput]; pbOutput
0x18001f7f8  xor     r9d, r9d; dwFlags
0x18001f7fb  lea     r8d, [r9+10h]; cbOutput
0x18001f7ff  call    cs:__imp_BCryptFinishHash
0x18001f805  mov     ebx, eax
0x18001f807  test    eax, eax
0x18001f809  jns     short loc_18001F813
0x18001f80b  mov     r9d, 435h
0x18001f811  jmp     short loc_18001F79C
0x18001f813  mov     rcx, [rbp+90h+phNewHash]; hHash
0x18001f817  call    cs:__imp_BCryptDestroyHash
0x18001f81d  mov     ebx, eax
0x18001f81f  xor     eax, eax
0x18001f821  mov     [rbp+90h+phNewHash], rax
0x18001f825  test    ebx, ebx
0x18001f827  jns     short loc_18001F836
0x18001f829  mov     r9d, 43Eh
0x18001f82f  mov     ecx, ebx
0x18001f831  jmp     loc_18001FADF
0x18001f836  mov     rcx, [rbp+90h+var_70]
0x18001f83a  lea     rdx, [rbp+90h+phNewHash]; phHash
0x18001f83e  mov     r9d, [r14+28h]; cbHashObject
0x18001f842  mov     r8, rsi; pbHashObject
0x18001f845  mov     [rsp+0D0h+var_A0], eax; dwFlags
0x18001f849  mov     [rsp+0D0h+cbSecret], eax; cbSecret
0x18001f84d  mov     rcx, [rcx+130h]; hAlgorithm
0x18001f854  mov     qword ptr [rsp+0D0h+dwFlags], rax; pbSecret
0x18001f859  call    cs:__imp_BCryptCreateHash
0x18001f85f  mov     ebx, eax
0x18001f861  test    eax, eax
0x18001f863  jns     short loc_18001F870
0x18001f865  mov     r9d, 44Fh
0x18001f86b  jmp     loc_18001F79C
0x18001f870  mov     rcx, [rbp+90h+phNewHash]; hHash
0x18001f874  lea     rdx, [r15+1Ch]; pbInput
0x18001f878  xor     r9d, r9d; dwFlags
0x18001f87b  lea     esi, [r9+30h]
0x18001f87f  mov     r8d, esi; cbInput
0x18001f882  call    cs:__imp_BCryptHashData
0x18001f888  mov     ebx, eax
0x18001f88a  test    eax, eax
0x18001f88c  jns     short loc_18001F899
0x18001f88e  mov     r9d, 45Ah
0x18001f894  jmp     loc_18001F79C
0x18001f899  mov     rcx, [rbp+90h+phNewHash]; hHash
0x18001f89d  lea     rdx, g_rgbPad2; pbInput
0x18001f8a4  xor     r9d, r9d; dwFlags
0x18001f8a7  mov     r8d, esi; cbInput
0x18001f8aa  call    cs:__imp_BCryptHashData
0x18001f8b0  mov     ebx, eax
0x18001f8b2  test    eax, eax
0x18001f8b4  jns     short loc_18001F8C1
0x18001f8b6  mov     r9d, 465h
0x18001f8bc  jmp     loc_18001F79C
0x18001f8c1  mov     rcx, [rbp+90h+phNewHash]; hHash
0x18001f8c5  lea     rdx, [rbp+90h+pbOutput]; pbInput
0x18001f8c9  xor     r9d, r9d; dwFlags
0x18001f8cc  lea     esi, [r9+10h]
0x18001f8d0  mov     r8d, esi; cbInput
0x18001f8d3  call    cs:__imp_BCryptHashData
0x18001f8d9  mov     ebx, eax
0x18001f8db  test    eax, eax
0x18001f8dd  jns     short loc_18001F8EA
0x18001f8df  mov     r9d, 470h
0x18001f8e5  jmp     loc_18001F79C
0x18001f8ea  mov     rcx, [rbp+90h+phNewHash]; hHash
0x18001f8ee  xor     r9d, r9d; dwFlags
0x18001f8f1  mov     r8d, esi; cbOutput
0x18001f8f4  mov     rdx, r13; pbOutput
0x18001f8f7  call    cs:__imp_BCryptFinishHash
0x18001f8fd  mov     ebx, eax
0x18001f8ff  test    eax, eax
0x18001f901  jns     short loc_18001F90E
0x18001f903  mov     r9d, 47Bh
0x18001f909  jmp     loc_18001F79C
0x18001f90e  mov     r15, [rbp+90h+var_80]
0x18001f912  test    r15, r15
0x18001f915  jz      loc_18001FAC9
0x18001f91b  mov     r9d, [r14+18h]; cbHashObject
0x18001f91f  lea     rdx, [rbp+90h+hHash]; phNewHash
0x18001f923  mov     rcx, [r14+10h]; hHash
0x18001f927  mov     r8, r12; pbHashObject
0x18001f92a  mov     [rsp+0D0h+dwFlags], 0; dwFlags
0x18001f932  call    cs:__imp_BCryptDuplicateHash
0x18001f938  mov     ebx, eax
0x18001f93a  test    eax, eax
0x18001f93c  jns     short loc_18001F949
0x18001f93e  mov     r9d, 48Fh
0x18001f944  jmp     loc_18001F79C
0x18001f949  mov     rsi, [rbp+90h+var_78]
0x18001f94d  xor     r9d, r9d; dwFlags
0x18001f950  mov     rcx, [rbp+90h+hHash]; hHash
0x18001f954  lea     r8d, [r9+30h]; cbInput
0x18001f958  lea     rdx, [rsi+1Ch]; pbInput
0x18001f95c  call    cs:__imp_BCryptHashData
0x18001f962  mov     ebx, eax
0x18001f964  test    eax, eax
0x18001f966  jns     short loc_18001F973
0x18001f968  mov     r9d, 49Ah
0x18001f96e  jmp     loc_18001F79C
0x18001f973  mov     rcx, [rbp+90h+hHash]; hHash
0x18001f977  lea     rdx, g_rgbPad1; "666666666666666666666666666666666666666"...
0x18001f97e  xor     r9d, r9d; dwFlags
0x18001f981  lea     r13d, [r9+28h]
0x18001f985  mov     r8d, r13d; cbInput
0x18001f988  call    cs:__imp_BCryptHashData
0x18001f98e  mov     ebx, eax
0x18001f990  test    eax, eax
0x18001f992  jns     short loc_18001F99F
0x18001f994  mov     r9d, 4A5h
0x18001f99a  jmp     loc_18001F79C
0x18001f99f  mov     rcx, [rbp+90h+hHash]; hHash
0x18001f9a3  lea     rdx, [rbp+90h+pbInput]; pbOutput
0x18001f9a7  xor     r9d, r9d; dwFlags
0x18001f9aa  lea     r8d, [r9+14h]; cbOutput
0x18001f9ae  call    cs:__imp_BCryptFinishHash
0x18001f9b4  mov     ebx, eax
0x18001f9b6  test    eax, eax
0x18001f9b8  jns     short loc_18001F9C5
0x18001f9ba  mov     r9d, 4B0h
0x18001f9c0  jmp     loc_18001F79C
0x18001f9c5  mov     rcx, [rbp+90h+hHash]; hHash
0x18001f9c9  call    cs:__imp_BCryptDestroyHash
0x18001f9cf  mov     [rbp+90h+hHash], 0
0x18001f9d7  mov     ebx, eax
0x18001f9d9  test    eax, eax
0x18001f9db  jns     short loc_18001F9E8
0x18001f9dd  mov     r9d, 4B9h
0x18001f9e3  jmp     loc_18001F79C
0x18001f9e8  mov     rax, [rbp+90h+var_70]
0x18001f9ec  lea     rdx, [rbp+90h+hHash]; phHash
0x18001f9f0  mov     r9d, [r14+18h]; cbHashObject
0x18001f9f4  mov     r8, r12; pbHashObject
0x18001f9f7  mov     [rsp+0D0h+var_A0], 0; dwFlags
0x18001f9ff  mov     [rsp+0D0h+cbSecret], 0; cbSecret
0x18001fa07  mov     rcx, [rax+150h]; hAlgorithm
0x18001fa0e  mov     qword ptr [rsp+0D0h+dwFlags], 0; pbSecret
0x18001fa17  call    cs:__imp_BCryptCreateHash
0x18001fa1d  mov     ebx, eax
0x18001fa1f  test    eax, eax
0x18001fa21  jns     short loc_18001FA2E
0x18001fa23  mov     r9d, 4CAh
0x18001fa29  jmp     loc_18001F79C
0x18001fa2e  mov     rcx, [rbp+90h+hHash]; hHash
0x18001fa32  lea     rdx, [rsi+1Ch]; pbInput
0x18001fa36  xor     r9d, r9d; dwFlags
0x18001fa39  lea     r8d, [r9+30h]; cbInput
0x18001fa3d  call    cs:__imp_BCryptHashData
0x18001fa43  mov     ebx, eax
0x18001fa45  test    eax, eax
0x18001fa47  jns     short loc_18001FA54
0x18001fa49  mov     r9d, 4D5h
0x18001fa4f  jmp     loc_18001F79C
0x18001fa54  mov     rcx, [rbp+90h+hHash]; hHash
0x18001fa58  lea     rdx, g_rgbPad2; pbInput
0x18001fa5f  xor     r9d, r9d; dwFlags
  ... truncated ...
```
