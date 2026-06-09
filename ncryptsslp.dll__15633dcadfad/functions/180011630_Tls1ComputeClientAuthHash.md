# Tls1ComputeClientAuthHash

- ea: `0x180011630`
- end: `0x180011a35`
- name: `Tls1ComputeClientAuthHash`
- size: `1029`
- prototype: `__int64 __fastcall(__int64, const wchar_t *, UCHAR *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800133f0`

## callees

- `0x180009160`
- `0x18000b594`
- `0x18000b654`
- `0x180011630`
- `0x1800185e0`
- `0x180018ac0`
- `0x180024ef0`
- `0x180026010`

## import_xrefs

- `bcrypt!BCryptDuplicateHash` at `0x1800117bb`
- `bcrypt!BCryptDuplicateHash` at `0x180011981`
- `bcrypt!BCryptDuplicateHash` at `0x1800117bb`
- `bcrypt!BCryptDuplicateHash` at `0x180011981`
- `bcrypt!BCryptFinishHash` at `0x1800119a8`
- `bcrypt!BCryptFinishHash` at `0x1800119ea`
- `bcrypt!BCryptFinishHash` at `0x1800119a8`
- `bcrypt!BCryptFinishHash` at `0x1800119ea`
- `bcrypt!BCryptDestroyHash` at `0x1800119fd`
- `bcrypt!BCryptDestroyHash` at `0x180011a08`
- `bcrypt!BCryptDestroyHash` at `0x1800119fd`
- `bcrypt!BCryptDestroyHash` at `0x180011a08`

## string_xrefs

- `0x180011769`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x1800117ec`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180011874`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180011927`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x1800119c2`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`

## pseudocode

```c
__int64 __fastcall Tls1ComputeClientAuthHash(
        __int64 a1,
        const wchar_t *a2,
        UCHAR *a3,
        unsigned int a4,
        unsigned int *a5)
{
  unsigned int v5; // edi
  int v7; // edx
  unsigned int v10; // r9d
  UCHAR *v12; // r13
  UCHAR *v13; // r12
  UCHAR *p_hHash; // rbx
  unsigned __int64 v15; // rcx
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // rcx
  void *v18; // rsp
  void *v19; // rsp
  UCHAR *v20; // rax
  NTSTATUS v21; // edi
  __int64 v22; // rsi
  int v23; // edx
  UCHAR *v25; // rsi
  NTSTATUS v26; // eax
  __int64 v27; // r9
  BCRYPT_HASH_HANDLE hHash; // [rsp+40h] [rbp+0h] BYREF
  BCRYPT_HASH_HANDLE phNewHash[2]; // [rsp+48h] [rbp+8h] BYREF

  v5 = *(_DWORD *)(a1 + 24);
  v7 = 0;
  v10 = *(_DWORD *)(a1 + 28);
  hHash = 0;
  v12 = 0;
  phNewHash[0] = 0;
  if ( !*(_QWORD *)(a1 + 32) )
    goto LABEL_2;
  p_hHash = 0;
  if ( v10 != 20 )
  {
    v21 = -2146893785;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return (unsigned int)v21;
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      0,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
      (unsigned int)"Status",
      39,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
      56);
    goto LABEL_26;
  }
  if ( wcscmp(a2, L"RSA") )
  {
    if ( !wcscmp(a2, L"DSA")
      || !wcscmp(a2, L"ECDSA")
      || !wcscmp(a2, L"ECDSA_P256")
      || !wcscmp(a2, L"ECDSA_P384")
      || !wcscmp(a2, L"ECDSA_P521") )
    {
      v10 = 20;
      v7 = 0;
LABEL_2:
      v13 = a3;
      *a5 = v10;
      goto LABEL_3;
    }
    v21 = -2146893783;
    DebugTraceError(2148073513LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c", 3409);
LABEL_26:
    if ( hHash )
      BCryptDestroyHash(hHash);
    if ( phNewHash[0] )
      BCryptDestroyHash(phNewHash[0]);
    if ( p_hHash )
    {
      if ( *((_DWORD *)p_hHash - 2) == 1885431112 )
        ((void (__fastcall *)(UCHAR *))g_pfnFree)(p_hHash - 8);
    }
    return (unsigned int)v21;
  }
  v13 = a3 + 16;
  v10 = 36;
  v12 = a3;
  *a5 = 36;
  v5 += *(_DWORD *)(a1 + 40);
  v7 = 0;
LABEL_3:
  if ( !a3 )
    return 0;
  if ( a4 >= v10 )
  {
    p_hHash = 0;
    if ( !v5 )
      goto LABEL_59;
    if ( v5 > (unsigned __int64)g_ulMaxStackAllocSize )
      goto LABEL_59;
    v15 = v5 + g_ulAdditionalProbeSize + 8;
    if ( v15 < v5 || !(unsigned int)VerifyStackAvailable(v15) )
      goto LABEL_59;
    v16 = v5 + 23LL;
    if ( v16 <= (unsigned __int64)v5 + 8 )
      v16 = 0xFFFFFFFFFFFFFF0LL;
    v17 = v16 & 0xFFFFFFFFFFFFFFF0uLL;
    v18 = alloca(v17);
    v19 = alloca(v17);
    p_hHash = (UCHAR *)&hHash;
    if ( !&hHash || (LODWORD(hHash) = 1801679955, (p_hHash = (UCHAR *)phNewHash) == 0) )
    {
LABEL_59:
      if ( (unsigned __int64)v5 + 8 >= v5 )
      {
        v20 = (UCHAR *)((__int64 (*)(void))g_pfnAllocate)();
        p_hHash = v20;
        if ( v20 )
        {
          *(_DWORD *)v20 = 1885431112;
          p_hHash = v20 + 8;
        }
      }
    }
    if ( !p_hHash )
    {
      v21 = -2146893810;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v7,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
          (unsigned int)"Status",
          14,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
          103);
      goto LABEL_26;
    }
    if ( v12 )
    {
      v22 = *(unsigned int *)(a1 + 40);
      v21 = BCryptDuplicateHash(*(BCRYPT_HASH_HANDLE *)(a1 + 32), phNewHash, p_hHash, *(_DWORD *)(a1 + 40), 0);
      if ( v21 < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v23,
            (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
            (unsigned int)"Status",
            v21,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
            127);
        goto LABEL_26;
      }
      v25 = &p_hHash[v22];
      v26 = BCryptFinishHash(phNewHash[0], v12, 0x10u, 0);
      v21 = v26;
      if ( v26 < 0 )
      {
        v27 = 3466;
LABEL_52:
        DebugTraceError(
          (unsigned int)v26,
          "Status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
          v27);
        goto LABEL_26;
      }
    }
    else
    {
      v25 = p_hHash;
    }
    v26 = BCryptDuplicateHash(*(BCRYPT_HASH_HANDLE *)(a1 + 16), &hHash, v25, *(_DWORD *)(a1 + 24), 0);
    v21 = v26;
    if ( v26 >= 0 )
    {
      v26 = BCryptFinishHash(hHash, v13, *(_DWORD *)(a1 + 28), 0);
      v21 = v26;
      if ( v26 >= 0 )
      {
        v21 = 0;
        goto LABEL_26;
      }
      v27 = 3491;
    }
    else
    {
      v27 = 3480;
    }
    goto LABEL_52;
  }
  return 2148073512LL;
}

```

## disassembly

```asm
0x180011630  push    rbp
0x180011632  push    rbx
0x180011633  push    rsi
0x180011634  push    rdi
0x180011635  push    r12
0x180011637  push    r13
0x180011639  push    r14
0x18001163b  push    r15
0x18001163d  sub     rsp, 68h
0x180011641  lea     rbp, [rsp+40h]
0x180011646  mov     rax, cs:__security_cookie
0x18001164d  xor     rax, rbp
0x180011650  mov     [rbp+60h+var_48], rax
0x180011654  mov     edi, [rcx+18h]
0x180011657  mov     r12, rdx
0x18001165a  xor     edx, edx
0x18001165c  mov     r15d, r9d
0x18001165f  mov     rsi, r8
0x180011662  mov     r9d, [rcx+1Ch]
0x180011666  mov     r14, rcx
0x180011669  mov     [rbp+60h+hHash], rdx
0x18001166d  mov     r13d, edx
0x180011670  mov     [rbp+60h+phNewHash], rdx
0x180011674  cmp     [rcx+20h], rdx
0x180011678  jnz     loc_18001172E
0x18001167e  mov     rax, [rbp+60h+arg_20]
0x180011685  mov     r12, rsi
0x180011688  mov     [rax], r9d
0x18001168b  test    rsi, rsi
0x18001168e  jz      loc_180011956
0x180011694  cmp     r15d, r9d
0x180011697  jb      loc_18001195D
0x18001169d  mov     rbx, rdx
0x1800116a0  test    edi, edi
0x1800116a2  jz      short loc_1800116FF
0x1800116a4  mov     esi, edi
0x1800116a6  cmp     rsi, cs:g_ulMaxStackAllocSize
0x1800116ad  ja      short loc_1800116FF
0x1800116af  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800116b6  add     rcx, 8
0x1800116ba  add     rcx, rsi
0x1800116bd  cmp     rcx, rsi
0x1800116c0  jb      short loc_1800116FF
0x1800116c2  call    VerifyStackAvailable
0x1800116c7  test    eax, eax
0x1800116c9  jz      short loc_1800116FF
0x1800116cb  lea     rax, [rsi+8]
0x1800116cf  lea     rcx, [rax+0Fh]
0x1800116d3  cmp     rcx, rax
0x1800116d6  ja      short loc_1800116E2
0x1800116d8  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800116e2  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800116e6  mov     rax, rcx
0x1800116e9  call    _alloca_probe
0x1800116ee  sub     rsp, rcx
0x1800116f1  lea     rbx, [rsp+0A0h+hHash]
0x1800116f6  test    rbx, rbx
0x1800116f9  jnz     loc_18001177F
0x1800116ff  mov     eax, edi
0x180011701  lea     rcx, [rax+8]
0x180011705  cmp     rcx, rax
0x180011708  jb      loc_18001178F
0x18001170e  mov     rax, cs:g_pfnAllocate
0x180011715  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001171a  mov     rbx, rax
0x18001171d  test    rax, rax
0x180011720  jz      short loc_18001178F
0x180011722  mov     dword ptr [rax], 70616548h
0x180011728  add     rbx, 8
0x18001172c  jmp     short loc_18001178F
0x18001172e  mov     rbx, rdx
0x180011731  cmp     r9d, 14h
0x180011735  jz      loc_18001188D
0x18001173b  mov     edi, 80090027h
0x180011740  mov     rcx, cs:WPP_GLOBAL_Control
0x180011747  lea     rax, WPP_GLOBAL_Control
0x18001174e  cmp     rcx, rax
0x180011751  jz      loc_18001182F
0x180011757  test    byte ptr [rcx+1Ch], 1
0x18001175b  jz      loc_18001182F
0x180011761  mov     [rsp+0A0h+var_70], 0D38h
0x180011769  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011770  mov     [rsp+0A0h+var_78], r8
0x180011775  mov     [rsp+0A0h+dwFlags], 80090027h
0x18001177d  jmp     short loc_1800117FC
0x18001177f  mov     dword ptr [rbx], 6B637453h
0x180011785  add     rbx, 8
0x180011789  jz      loc_1800116FF
0x18001178f  test    rbx, rbx
0x180011792  jz      loc_18001184E
0x180011798  test    r13, r13
0x18001179b  jz      loc_180011967
0x1800117a1  mov     esi, [r14+28h]
0x1800117a5  lea     rdx, [rbp+60h+phNewHash]; phNewHash
0x1800117a9  mov     rcx, [r14+20h]; hHash
0x1800117ad  mov     r9d, esi; cbHashObject
0x1800117b0  mov     r8, rbx; pbHashObject
0x1800117b3  mov     [rsp+0A0h+dwFlags], 0; dwFlags
0x1800117bb  call    cs:__imp_BCryptDuplicateHash
0x1800117c1  mov     edi, eax
0x1800117c3  test    eax, eax
0x1800117c5  jns     loc_180011995
0x1800117cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800117d2  lea     rax, WPP_GLOBAL_Control
0x1800117d9  cmp     rcx, rax
0x1800117dc  jz      short loc_18001180C
0x1800117de  test    byte ptr [rcx+1Ch], 1
0x1800117e2  jz      short loc_18001180C
0x1800117e4  mov     [rsp+0A0h+var_70], 0D7Fh
0x1800117ec  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800117f3  mov     [rsp+0A0h+var_78], r8
0x1800117f8  mov     [rsp+0A0h+dwFlags], edi
0x1800117fc  mov     rcx, [rcx+10h]
0x180011800  lea     r9, aStatus; "Status"
0x180011807  call    WPP_SF_sDsd
0x18001180c  mov     rcx, [rbp+60h+hHash]; hHash
0x180011810  test    rcx, rcx
0x180011813  jnz     loc_1800119FD
0x180011819  mov     rcx, [rbp+60h+phNewHash]; hHash
0x18001181d  test    rcx, rcx
0x180011820  jnz     loc_180011A08
0x180011826  test    rbx, rbx
0x180011829  jnz     loc_180011A13
0x18001182f  mov     eax, edi
0x180011831  mov     rcx, [rbp+60h+var_48]
0x180011835  xor     rcx, rbp; StackCookie
0x180011838  call    __security_check_cookie
0x18001183d  lea     rsp, [rbp+28h]
0x180011841  pop     r15
0x180011843  pop     r14
0x180011845  pop     r13
0x180011847  pop     r12
0x180011849  pop     rdi
0x18001184a  pop     rsi
0x18001184b  pop     rbx
0x18001184c  pop     rbp
0x18001184d  retn
0x18001184e  mov     edi, 8009000Eh
0x180011853  mov     rcx, cs:WPP_GLOBAL_Control
0x18001185a  lea     rax, WPP_GLOBAL_Control
0x180011861  cmp     rcx, rax
0x180011864  jz      short loc_18001180C
0x180011866  test    byte ptr [rcx+1Ch], 1
0x18001186a  jz      short loc_18001180C
0x18001186c  mov     [rsp+0A0h+var_70], 0D67h
0x180011874  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001187b  mov     [rsp+0A0h+var_78], r8
0x180011880  mov     [rsp+0A0h+dwFlags], 8009000Eh
0x180011888  jmp     loc_1800117FC
0x18001188d  lea     rdx, aRsa; "RSA"
0x180011894  mov     rcx, r12; String1
0x180011897  call    wcscmp
0x18001189c  test    eax, eax
0x18001189e  jnz     short loc_1800118C2
0x1800118a0  mov     rax, [rbp+60h+arg_20]
0x1800118a7  lea     r12, [rsi+10h]
0x1800118ab  mov     r9d, 24h ; '$'
0x1800118b1  mov     r13, rsi
0x1800118b4  mov     [rax], r9d
0x1800118b7  add     edi, [r14+28h]
0x1800118bb  xor     edx, edx
0x1800118bd  jmp     loc_18001168B
0x1800118c2  lea     rdx, aDsa; "DSA"
0x1800118c9  mov     rcx, r12; String1
0x1800118cc  call    wcscmp
0x1800118d1  test    eax, eax
0x1800118d3  jz      short loc_180011949
0x1800118d5  lea     rdx, aEcdsa; "ECDSA"
0x1800118dc  mov     rcx, r12; String1
0x1800118df  call    wcscmp
0x1800118e4  test    eax, eax
0x1800118e6  jz      short loc_180011949
0x1800118e8  lea     rdx, aEcdsaP256; "ECDSA_P256"
0x1800118ef  mov     rcx, r12; String1
0x1800118f2  call    wcscmp
0x1800118f7  test    eax, eax
0x1800118f9  jz      short loc_180011949
0x1800118fb  lea     rdx, aEcdsaP384; "ECDSA_P384"
0x180011902  mov     rcx, r12; String1
0x180011905  call    wcscmp
0x18001190a  test    eax, eax
0x18001190c  jz      short loc_180011949
0x18001190e  lea     rdx, aEcdsaP521; "ECDSA_P521"
0x180011915  mov     rcx, r12; String1
0x180011918  call    wcscmp
0x18001191d  test    eax, eax
0x18001191f  jz      short loc_180011949
0x180011921  mov     r9d, 0D51h
0x180011927  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001192e  lea     rdx, aStatus; "Status"
0x180011935  mov     ecx, 80090029h
0x18001193a  mov     edi, 80090029h
0x18001193f  call    DebugTraceError
0x180011944  jmp     loc_18001180C
0x180011949  mov     r9d, 14h
0x18001194f  xor     edx, edx
0x180011951  jmp     loc_18001167E
0x180011956  mov     eax, edx
0x180011958  jmp     loc_180011831
0x18001195d  mov     eax, 80090028h
0x180011962  jmp     loc_180011831
0x180011967  mov     rsi, rbx
0x18001196a  mov     r9d, [r14+18h]; cbHashObject
0x18001196e  lea     rdx, [rbp+60h+hHash]; phNewHash
0x180011972  mov     rcx, [r14+10h]; hHash
0x180011976  mov     r8, rsi; pbHashObject
0x180011979  mov     [rsp+0A0h+dwFlags], 0; dwFlags
0x180011981  call    cs:__imp_BCryptDuplicateHash
0x180011987  mov     edi, eax
0x180011989  test    eax, eax
0x18001198b  jns     short loc_1800119DC
0x18001198d  mov     r9d, 0D98h
0x180011993  jmp     short loc_1800119C2
0x180011995  mov     rcx, [rbp+60h+phNewHash]; hHash
0x180011999  xor     r9d, r9d; dwFlags
0x18001199c  mov     r8d, 10h; cbOutput
0x1800119a2  mov     rdx, r13; pbOutput
0x1800119a5  add     rsi, rbx
0x1800119a8  call    cs:__imp_BCryptFinishHash
0x1800119ae  mov     edi, eax
0x1800119b0  test    eax, eax
0x1800119b2  jns     short loc_18001196A
0x1800119b4  mov     r9d, 0D8Ah
0x1800119ba  jmp     short loc_1800119C2
0x1800119bc  mov     r9d, 0DA3h
0x1800119c2  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800119c9  mov     ecx, eax
0x1800119cb  lea     rdx, aStatus; "Status"
0x1800119d2  call    DebugTraceError
0x1800119d7  jmp     loc_18001180C
0x1800119dc  mov     r8d, [r14+1Ch]; cbOutput
0x1800119e0  xor     r9d, r9d; dwFlags
0x1800119e3  mov     rcx, [rbp+60h+hHash]; hHash
0x1800119e7  mov     rdx, r12; pbOutput
0x1800119ea  call    cs:__imp_BCryptFinishHash
0x1800119f0  mov     edi, eax
0x1800119f2  test    eax, eax
0x1800119f4  js      short loc_1800119BC
0x1800119f6  xor     edi, edi
0x1800119f8  jmp     loc_18001180C
0x1800119fd  call    cs:__imp_BCryptDestroyHash
0x180011a03  jmp     loc_180011819
0x180011a08  call    cs:__imp_BCryptDestroyHash
0x180011a0e  jmp     loc_180011826
0x180011a13  cmp     dword ptr [rbx-8], 70616548h
0x180011a1a  lea     rcx, [rbx-8]
0x180011a1e  jnz     loc_18001182F
0x180011a24  mov     rax, cs:g_pfnFree
0x180011a2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a30  jmp     loc_18001182F
```
