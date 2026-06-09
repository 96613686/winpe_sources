# Pku2uCreateDHKeyWithDomainParameters(_CERT_X942_DH_PARAMETERS *,unsigned __int64 *)

- ea: `0x18001b324`
- end: `0x18001b645`
- name: `?Pku2uCreateDHKeyWithDomainParameters@@YAJPEAU_CERT_X942_DH_PARAMETERS@@PEA_K@Z`
- size: `801`
- prototype: `__int64 __fastcall(BYTE *pbData, HCRYPTKEY *phKey)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x18001ff04`
- `0x18002ff80`

## callees

- `0x180018c80`
- `0x18001b324`
- `0x1800210f0`
- `0x180021a54`
- `0x180023cb8`
- `0x180023ce0`
- `0x180044f20`
- `0x180044f8c`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b410`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b468`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b4d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b5f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b410`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b468`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b4d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b5f7`
- `CRYPTSP!CryptSetKeyParam` at `0x18001b445`
- `CRYPTSP!CryptSetKeyParam` at `0x18001b4ad`
- `CRYPTSP!CryptSetKeyParam` at `0x18001b5cc`
- `CRYPTSP!CryptSetKeyParam` at `0x18001b445`
- `CRYPTSP!CryptSetKeyParam` at `0x18001b4ad`
- `CRYPTSP!CryptSetKeyParam` at `0x18001b5cc`
- `CRYPTSP!CryptDestroyKey` at `0x18001b3bb`
- `CRYPTSP!CryptDestroyKey` at `0x18001b3bb`
- `CRYPTSP!CryptGenKey` at `0x18001b3e2`
- `CRYPTSP!CryptGenKey` at `0x18001b3e2`

## pseudocode

```c
__int64 __fastcall Pku2uCreateDHKeyWithDomainParameters(BYTE *pbData, HCRYPTKEY *phKey)
{
  unsigned int v2; // eax
  unsigned int v5; // ebx
  unsigned int v6; // ebx
  DWORD LastError; // eax
  DWORD v9; // eax
  __int64 v10; // rdx
  BYTE *v11; // r15
  unsigned __int64 v12; // rdi
  BYTE *v13; // rbx
  __int64 v14; // rcx
  unsigned __int64 v15; // rcx
  void *v16; // rsp
  void *v17; // rsp
  BYTE *v18; // rax
  unsigned int v19; // eax
  __int64 v20; // rcx
  unsigned int v21; // edx
  __int64 v22; // [rsp+0h] [rbp-20h] BYREF
  BYTE pbDataa[16]; // [rsp+20h] [rbp+0h] BYREF

  v2 = *(_DWORD *)pbData;
  *(_OWORD *)pbDataa = 0;
  if ( v2 + 7 < v2 )
  {
    v5 = 60;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_ab3076db16bc34eed0dc663a0a4f0cac_Traceguids);
    goto LABEL_45;
  }
  v6 = (v2 + 7) & 0xFFFFFFF8;
  if ( 8 * v6 < 0x400 )
    return 65;
  if ( *phKey )
  {
    CryptDestroyKey(*phKey);
    *phKey = 0;
  }
  if ( !CryptGenKey(Pku2uGlobalCSPProvider, 0xAA02u, (v6 << 19) | 0x40, phKey) )
  {
    v5 = 60;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_ab3076db16bc34eed0dc663a0a4f0cac_Traceguids, LastError);
    }
    goto LABEL_45;
  }
  if ( CryptSetKeyParam(*phKey, 0xBu, pbData, 0) )
  {
    v11 = pbData + 16;
    if ( *((_DWORD *)pbData + 4) == v6 )
    {
      if ( !CryptSetKeyParam(*phKey, 0xCu, pbData + 16, 0) )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_18;
        v9 = GetLastError();
        v10 = 16;
        goto LABEL_17;
      }
    }
    else
    {
      v12 = v6;
      *(_DWORD *)pbDataa = v6;
      v13 = 0;
      if ( !v12
        || v12 > g_ulMaxStackAllocSize
        || v12 + g_ulAdditionalProbeSize + 8 < v12
        || !(unsigned int)VerifyStackAvailable() )
      {
        goto LABEL_51;
      }
      v14 = v12 + 23;
      if ( v12 + 23 <= v12 + 8 )
        v14 = 0xFFFFFFFFFFFFFF0LL;
      v15 = v14 & 0xFFFFFFFFFFFFFFF0uLL;
      v16 = alloca(v15);
      v17 = alloca(v15);
      v13 = pbDataa;
      if ( &v22 == (__int64 *)-32LL || (*(_DWORD *)pbDataa = 1801679955, v13 = &pbDataa[8], pbDataa == (BYTE *)-8LL) )
      {
LABEL_51:
        if ( v12 + 8 >= v12 )
        {
          v18 = (BYTE *)((__int64 (*)(void))g_pfnAllocate)();
          v13 = v18;
          if ( v18 )
          {
            *(_DWORD *)v18 = 1885431112;
            v13 = v18 + 8;
          }
        }
      }
      *(_QWORD *)&pbDataa[8] = v13;
      if ( !v13 )
        goto LABEL_18;
      v19 = *(_DWORD *)pbDataa;
      if ( *(_DWORD *)v11 < *(_DWORD *)pbDataa )
        v19 = *(_DWORD *)v11;
      memcpy_0(v13, *((const void **)pbData + 3), v19);
      v20 = *(unsigned int *)pbDataa;
      v21 = *(_DWORD *)pbDataa;
      if ( *(_DWORD *)v11 < *(_DWORD *)pbDataa )
      {
        v21 = *(_DWORD *)v11;
        v20 = *(unsigned int *)v11;
      }
      memset_0((void *)(*(_QWORD *)&pbDataa[8] + v20), 0, *(_DWORD *)pbDataa - v21);
      if ( !CryptSetKeyParam(*phKey, 0xCu, pbDataa, 0) )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_18;
        v9 = GetLastError();
        v10 = 17;
        goto LABEL_17;
      }
    }
    v5 = 0;
    goto LABEL_45;
  }
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    goto LABEL_18;
  v9 = GetLastError();
  v10 = 15;
LABEL_17:
  WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, WPP_ab3076db16bc34eed0dc663a0a4f0cac_Traceguids, v9);
LABEL_18:
  v5 = 60;
LABEL_45:
  if ( *(_QWORD *)&pbDataa[8] )
  {
    if ( *(_DWORD *)(*(_QWORD *)&pbDataa[8] - 8LL) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
  }
  return v5;
}

```

## disassembly

```asm
0x18001b324  push    rbp
0x18001b326  push    rbx
0x18001b327  push    rsi
0x18001b328  push    rdi
0x18001b329  push    r14
0x18001b32b  push    r15
0x18001b32d  sub     rsp, 48h
0x18001b331  lea     rbp, [rsp+20h]
0x18001b336  mov     rax, cs:__security_cookie
0x18001b33d  xor     rax, rbp
0x18001b340  mov     [rbp+50h+var_38], rax
0x18001b344  mov     eax, [rcx]
0x18001b346  xorps   xmm0, xmm0
0x18001b349  mov     rsi, rdx
0x18001b34c  mov     r14, rcx
0x18001b34f  movups  xmmword ptr [rbp+50h+pbData], xmm0
0x18001b353  lea     ebx, [rax+7]
0x18001b356  cmp     ebx, eax
0x18001b358  jnb     short loc_18001B398
0x18001b35a  mov     ebx, 3Ch ; '<'
0x18001b35f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b366  lea     rax, WPP_GLOBAL_Control
0x18001b36d  cmp     rcx, rax
0x18001b370  jz      loc_18001B609
0x18001b376  test    byte ptr [rcx+1Ch], 1
0x18001b37a  jz      loc_18001B609
0x18001b380  mov     rcx, [rcx+10h]
0x18001b384  lea     edx, [rbx-2Fh]
0x18001b387  lea     r8, WPP_ab3076db16bc34eed0dc663a0a4f0cac_Traceguids
0x18001b38e  call    WPP_SF_
0x18001b393  jmp     loc_18001B609
0x18001b398  and     ebx, 0FFFFFFF8h
0x18001b39b  lea     eax, ds:0[rbx*8]
0x18001b3a2  cmp     eax, 400h
0x18001b3a7  jnb     short loc_18001B3B3
0x18001b3a9  mov     eax, 41h ; 'A'
0x18001b3ae  jmp     loc_18001B62C
0x18001b3b3  mov     rcx, [rdx]; hKey
0x18001b3b6  test    rcx, rcx
0x18001b3b9  jz      short loc_18001B3C8
0x18001b3bb  call    cs:__imp_CryptDestroyKey
0x18001b3c1  mov     qword ptr [rsi], 0
0x18001b3c8  mov     rcx, cs:?Pku2uGlobalCSPProvider@@3_KA; hProv
0x18001b3cf  mov     r8d, ebx
0x18001b3d2  shl     r8d, 13h
0x18001b3d6  mov     r9, rsi; phKey
0x18001b3d9  or      r8d, 40h; dwFlags
0x18001b3dd  mov     edx, 0AA02h; Algid
0x18001b3e2  call    cs:__imp_CryptGenKey
0x18001b3e8  test    eax, eax
0x18001b3ea  jnz     short loc_18001B438
0x18001b3ec  lea     ebx, [rax+3Ch]
0x18001b3ef  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b3f6  lea     rax, WPP_GLOBAL_Control
0x18001b3fd  cmp     rcx, rax
0x18001b400  jz      loc_18001B609
0x18001b406  test    byte ptr [rcx+1Ch], 1
0x18001b40a  jz      loc_18001B609
0x18001b410  call    cs:__imp_GetLastError
0x18001b416  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b41d  lea     edx, [rbx-2Eh]
0x18001b420  mov     r9d, eax
0x18001b423  lea     r8, WPP_ab3076db16bc34eed0dc663a0a4f0cac_Traceguids
0x18001b42a  mov     rcx, [rcx+10h]
0x18001b42e  call    WPP_SF_d
0x18001b433  jmp     loc_18001B609
0x18001b438  mov     rcx, [rsi]; hKey
0x18001b43b  xor     r9d, r9d; dwFlags
0x18001b43e  mov     r8, r14; pbData
0x18001b441  lea     edx, [r9+0Bh]; dwParam
0x18001b445  call    cs:__imp_CryptSetKeyParam
0x18001b44b  test    eax, eax
0x18001b44d  jnz     short loc_18001B497
0x18001b44f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b456  lea     rax, WPP_GLOBAL_Control
0x18001b45d  cmp     rcx, rax
0x18001b460  jz      short loc_18001B48D
0x18001b462  test    byte ptr [rcx+1Ch], 1
0x18001b466  jz      short loc_18001B48D
0x18001b468  call    cs:__imp_GetLastError
0x18001b46e  mov     edx, 0Fh
0x18001b473  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b47a  lea     r8, WPP_ab3076db16bc34eed0dc663a0a4f0cac_Traceguids
0x18001b481  mov     r9d, eax
0x18001b484  mov     rcx, [rcx+10h]
0x18001b488  call    WPP_SF_d
0x18001b48d  mov     ebx, 3Ch ; '<'
0x18001b492  jmp     loc_18001B609
0x18001b497  lea     r15, [r14+10h]
0x18001b49b  cmp     [r15], ebx
0x18001b49e  jnz     short loc_18001B4E1
0x18001b4a0  mov     rcx, [rsi]; hKey
0x18001b4a3  xor     r9d, r9d; dwFlags
0x18001b4a6  mov     r8, r15; pbData
0x18001b4a9  lea     edx, [r9+0Ch]; dwParam
0x18001b4ad  call    cs:__imp_CryptSetKeyParam
0x18001b4b3  test    eax, eax
0x18001b4b5  jnz     loc_18001B607
0x18001b4bb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b4c2  lea     rax, WPP_GLOBAL_Control
0x18001b4c9  cmp     rcx, rax
0x18001b4cc  jz      short loc_18001B48D
0x18001b4ce  test    byte ptr [rcx+1Ch], 1
0x18001b4d2  jz      short loc_18001B48D
0x18001b4d4  call    cs:__imp_GetLastError
0x18001b4da  mov     edx, 10h
0x18001b4df  jmp     short loc_18001B473
0x18001b4e1  mov     edi, ebx
0x18001b4e3  mov     dword ptr [rbp+50h+pbData], ebx
0x18001b4e6  xor     ebx, ebx
0x18001b4e8  test    rdi, rdi
0x18001b4eb  jz      short loc_18001B54E
0x18001b4ed  cmp     rdi, cs:g_ulMaxStackAllocSize
0x18001b4f4  ja      short loc_18001B54E
0x18001b4f6  mov     rcx, cs:g_ulAdditionalProbeSize
0x18001b4fd  add     rcx, 8
0x18001b501  add     rcx, rdi
0x18001b504  cmp     rcx, rdi
0x18001b507  jb      short loc_18001B54E
0x18001b509  call    VerifyStackAvailable
0x18001b50e  test    eax, eax
0x18001b510  jz      short loc_18001B54E
0x18001b512  lea     rax, [rdi+8]
0x18001b516  lea     rcx, [rax+0Fh]
0x18001b51a  cmp     rcx, rax
0x18001b51d  ja      short loc_18001B529
0x18001b51f  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18001b529  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18001b52d  mov     rax, rcx
0x18001b530  call    _alloca_probe
0x18001b535  sub     rsp, rcx
0x18001b538  lea     rbx, [rsp+70h+pbData]
0x18001b53d  test    rbx, rbx
0x18001b540  jz      short loc_18001B54E
0x18001b542  mov     dword ptr [rbx], 6B637453h
0x18001b548  add     rbx, 8
0x18001b54c  jnz     short loc_18001B575
0x18001b54e  lea     rcx, [rdi+8]
0x18001b552  cmp     rcx, rdi
0x18001b555  jb      short loc_18001B575
0x18001b557  mov     rax, cs:g_pfnAllocate
0x18001b55e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b563  mov     rbx, rax
0x18001b566  test    rax, rax
0x18001b569  jz      short loc_18001B575
0x18001b56b  mov     dword ptr [rax], 70616548h
0x18001b571  add     rbx, 8
0x18001b575  mov     qword ptr [rbp+50h+pbData+8], rbx
0x18001b579  test    rbx, rbx
0x18001b57c  jz      loc_18001B48D
0x18001b582  mov     eax, dword ptr [rbp+50h+pbData]
0x18001b585  mov     rcx, rbx; void *
0x18001b588  cmp     [r15], eax
0x18001b58b  mov     rdx, [r14+18h]; Src
0x18001b58f  cmovb   eax, [r15]
0x18001b593  mov     r8d, eax; Size
0x18001b596  call    memcpy_0
0x18001b59b  mov     r8d, dword ptr [rbp+50h+pbData]
0x18001b59f  mov     ecx, r8d
0x18001b5a2  cmp     [r15], r8d
0x18001b5a5  mov     edx, r8d
0x18001b5a8  cmovb   edx, [r15]
0x18001b5ac  cmovb   ecx, [r15]
0x18001b5b0  sub     r8d, edx; Size
0x18001b5b3  add     rcx, qword ptr [rbp+50h+pbData+8]; void *
0x18001b5b7  xor     edx, edx; Val
0x18001b5b9  call    memset_0
0x18001b5be  mov     rcx, [rsi]; hKey
0x18001b5c1  lea     r8, [rbp+50h+pbData]; pbData
0x18001b5c5  xor     r9d, r9d; dwFlags
0x18001b5c8  lea     edx, [r9+0Ch]; dwParam
0x18001b5cc  call    cs:__imp_CryptSetKeyParam
0x18001b5d2  test    eax, eax
0x18001b5d4  jnz     short loc_18001B607
0x18001b5d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b5dd  lea     rax, WPP_GLOBAL_Control
0x18001b5e4  cmp     rcx, rax
0x18001b5e7  jz      loc_18001B48D
0x18001b5ed  test    byte ptr [rcx+1Ch], 1
0x18001b5f1  jz      loc_18001B48D
0x18001b5f7  call    cs:__imp_GetLastError
0x18001b5fd  mov     edx, 11h
0x18001b602  jmp     loc_18001B473
0x18001b607  xor     ebx, ebx
0x18001b609  mov     rax, qword ptr [rbp+50h+pbData+8]
0x18001b60d  test    rax, rax
0x18001b610  jz      short loc_18001B62A
0x18001b612  lea     rcx, [rax-8]
0x18001b616  cmp     dword ptr [rcx], 70616548h
0x18001b61c  jnz     short loc_18001B62A
0x18001b61e  mov     rax, cs:g_pfnFree
0x18001b625  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b62a  mov     eax, ebx
0x18001b62c  mov     rcx, [rbp+50h+var_38]
0x18001b630  xor     rcx, rbp; StackCookie
0x18001b633  call    __security_check_cookie
0x18001b638  lea     rsp, [rbp+28h]
0x18001b63c  pop     r15
0x18001b63e  pop     r14
0x18001b640  pop     rdi
0x18001b641  pop     rsi
0x18001b642  pop     rbx
0x18001b643  pop     rbp
0x18001b644  retn
```
