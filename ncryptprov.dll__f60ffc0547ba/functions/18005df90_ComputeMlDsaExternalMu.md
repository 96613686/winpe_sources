# ComputeMlDsaExternalMu

- ea: `0x18005df90`
- end: `0x18005e3bc`
- name: `ComputeMlDsaExternalMu`
- size: `1068`
- prototype: `__int64 __usercall@<rax>(BCRYPT_KEY_HANDLE hKey@<rcx>, PUCHAR pbOutput)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180003210`

## callees

- `0x1800086d0`
- `0x18000af80`
- `0x18005df90`
- `0x180062280`
- `0x180062310`
- `0x180063010`

## import_xrefs

- `bcrypt!BCryptHash` at `0x18005e1a6`
- `bcrypt!BCryptHash` at `0x18005e1a6`
- `bcrypt!BCryptExportKey` at `0x18005e003`
- `bcrypt!BCryptExportKey` at `0x18005e0eb`
- `bcrypt!BCryptExportKey` at `0x18005e003`
- `bcrypt!BCryptExportKey` at `0x18005e0eb`
- `bcrypt!BCryptCreateHash` at `0x18005e1eb`
- `bcrypt!BCryptCreateHash` at `0x18005e1eb`
- `bcrypt!BCryptHashData` at `0x18005e23b`
- `bcrypt!BCryptHashData` at `0x18005e267`
- `bcrypt!BCryptHashData` at `0x18005e293`
- `bcrypt!BCryptHashData` at `0x18005e2cf`
- `bcrypt!BCryptHashData` at `0x18005e2f7`
- `bcrypt!BCryptHashData` at `0x18005e23b`
- `bcrypt!BCryptHashData` at `0x18005e267`
- `bcrypt!BCryptHashData` at `0x18005e293`
- `bcrypt!BCryptHashData` at `0x18005e2cf`
- `bcrypt!BCryptHashData` at `0x18005e2f7`
- `bcrypt!BCryptDestroyHash` at `0x18005e358`
- `bcrypt!BCryptDestroyHash` at `0x18005e358`
- `bcrypt!BCryptFinishHash` at `0x18005e322`
- `bcrypt!BCryptFinishHash` at `0x18005e322`

## string_xrefs

- `0x18005e33c`: `onecore\ds\security\cryptoapi\ncrypt\storage\sign.c`

## pseudocode

```c
__int64 __fastcall ComputeMlDsaExternalMu(BCRYPT_KEY_HANDLE hKey, __int64 a2, UCHAR *a3, ULONG a4, PUCHAR pbOutput)
{
  UCHAR *p_phHash; // rdi
  unsigned int v9; // ebx
  UCHAR *v10; // rsi
  NTSTATUS v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r9
  unsigned __int64 v14; // rbx
  unsigned __int64 v15; // rcx
  __int64 v16; // rcx
  unsigned __int64 v17; // rcx
  void *v18; // rsp
  void *v19; // rsp
  UCHAR *v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rdx
  UCHAR *v23; // rax
  __int64 v25; // [rsp-20h] [rbp-90h] BYREF
  int v26; // [rsp+20h] [rbp-50h]
  __int64 v27; // [rsp+28h] [rbp-48h] BYREF
  int v28; // [rsp+30h] [rbp-40h] BYREF
  int v29; // [rsp+70h] [rbp+0h] BYREF
  ULONG pcbResult; // [rsp+74h] [rbp+4h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+78h] [rbp+8h] BYREF
  PUCHAR v32; // [rsp+80h] [rbp+10h]

  p_phHash = 0;
  v32 = a3;
  phHash = 0;
  pcbResult = 0;
  LOWORD(v29) = 0;
  if ( !pbOutput )
    return (unsigned int)-2146893785;
  v10 = 0;
  v11 = BCryptExportKey(hKey, 0, L"PQDSAPUBLICBLOB", 0, 0, &pcbResult, 0);
  v9 = v11;
  if ( v11 < 0 )
  {
    v13 = 72;
LABEL_54:
    v21 = (unsigned int)v11;
    goto LABEL_55;
  }
  v14 = pcbResult;
  if ( !pcbResult )
    goto LABEL_67;
  if ( pcbResult > (unsigned __int64)g_ulMaxStackAllocSize )
    goto LABEL_67;
  v15 = pcbResult + g_ulAdditionalProbeSize + 8;
  if ( v15 < pcbResult || !(unsigned int)VerifyStackAvailable(v15, v12) )
    goto LABEL_67;
  v16 = v14 + 23;
  if ( v14 + 23 <= v14 + 8 )
    v16 = 0xFFFFFFFFFFFFFF0LL;
  v17 = v16 & 0xFFFFFFFFFFFFFFF0uLL;
  v18 = alloca(v17);
  v19 = alloca(v17);
  p_phHash = (UCHAR *)&v29;
  if ( &v28 == (int *)-64LL || (v29 = 1801679955, (p_phHash = (UCHAR *)&phHash) == 0) )
  {
LABEL_67:
    if ( v14 + 8 >= v14 )
    {
      v20 = (UCHAR *)((__int64 (*)(void))g_pfnAllocate)();
      p_phHash = v20;
      if ( v20 )
      {
        *(_DWORD *)v20 = 1885431112;
        p_phHash = v20 + 8;
      }
    }
  }
  if ( !p_phHash )
  {
    v13 = 80;
LABEL_18:
    v9 = -2146893810;
    v21 = 2148073486LL;
LABEL_55:
    DebugTraceError(v21, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\sign.c", v13);
    goto LABEL_56;
  }
  v11 = BCryptExportKey(hKey, 0, L"PQDSAPUBLICBLOB", p_phHash, pcbResult, &pcbResult, 0);
  v9 = v11;
  if ( v11 < 0 )
  {
    v13 = 87;
    goto LABEL_54;
  }
  if ( (unsigned __int64)g_ulMaxStackAllocSize < 0x40
    || (unsigned __int64)(g_ulAdditionalProbeSize + 72) < 0x40
    || !(unsigned int)VerifyStackAvailable(g_ulAdditionalProbeSize + 72, v22)
    || &v25 == (__int64 *)-64LL
    || (v26 = 1801679955, (v10 = (UCHAR *)&v27) == 0) )
  {
    v23 = (UCHAR *)((__int64 (__fastcall *)(__int64))g_pfnAllocate)(72);
    v10 = v23;
    if ( v23 )
    {
      *(_DWORD *)v23 = 1885431112;
      v10 = v23 + 8;
    }
  }
  if ( !v10 )
  {
    v13 = 96;
    goto LABEL_18;
  }
  v11 = BCryptHash(1121, 0, 0, &p_phHash[*((unsigned int *)p_phHash + 1) + 12], *((_DWORD *)p_phHash + 2), v10, 64);
  v9 = v11;
  if ( v11 < 0 )
  {
    v13 = 106;
    goto LABEL_54;
  }
  v11 = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x461, &phHash, 0, 0, 0, 0, 0);
  v9 = v11;
  if ( v11 < 0 )
  {
    v13 = 113;
    goto LABEL_54;
  }
  if ( a2 && *(_QWORD *)a2 )
  {
    if ( *(_DWORD *)(a2 + 8) > 0xFFu )
    {
      v9 = -2146893785;
      goto LABEL_56;
    }
    LOBYTE(v29) = *(_BYTE *)(a2 + 8);
  }
  v11 = BCryptHashData(phHash, v10, 0x40u, 0);
  v9 = v11;
  if ( v11 < 0 )
  {
    v13 = 132;
    goto LABEL_54;
  }
  v11 = BCryptHashData(phHash, (PUCHAR)&v29 + 1, 1u, 0);
  v9 = v11;
  if ( v11 < 0 )
  {
    v13 = 139;
    goto LABEL_54;
  }
  v11 = BCryptHashData(phHash, (PUCHAR)&v29, 1u, 0);
  v9 = v11;
  if ( v11 < 0 )
  {
    v13 = 146;
    goto LABEL_54;
  }
  if ( a2 )
  {
    if ( *(_QWORD *)a2 )
    {
      if ( (_BYTE)v29 )
      {
        v11 = BCryptHashData(phHash, *(PUCHAR *)a2, (unsigned __int8)v29, 0);
        v9 = v11;
        if ( v11 < 0 )
        {
          v13 = 155;
          goto LABEL_54;
        }
      }
    }
  }
  v11 = BCryptHashData(phHash, v32, a4, 0);
  v9 = v11;
  if ( v11 < 0 )
  {
    v13 = 163;
    goto LABEL_54;
  }
  v11 = BCryptFinishHash(phHash, pbOutput, 0x40u, 0);
  v9 = v11;
  if ( v11 < 0 )
  {
    v13 = 171;
    goto LABEL_54;
  }
LABEL_56:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( p_phHash && *((_DWORD *)p_phHash - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( v10 && *((_DWORD *)v10 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  return v9;
}

```

## disassembly

```asm
0x18005df90  push    rbp
0x18005df92  push    rbx
0x18005df93  push    rsi
0x18005df94  push    rdi
0x18005df95  push    r13
0x18005df97  push    r14
0x18005df99  push    r15
0x18005df9b  sub     rsp, 70h
0x18005df9f  lea     rbp, [rsp+40h]
0x18005dfa4  mov     rax, cs:__security_cookie
0x18005dfab  xor     rax, rbp
0x18005dfae  mov     [rbp+60h+var_40], rax
0x18005dfb2  xor     edi, edi
0x18005dfb4  mov     [rbp+60h+var_50], r8
0x18005dfb8  mov     r13d, r9d
0x18005dfbb  mov     r14, rdx
0x18005dfbe  mov     r15, rcx
0x18005dfc1  mov     [rbp+60h+phHash], rdi
0x18005dfc5  mov     [rbp+60h+var_5C], edi
0x18005dfc8  mov     [rbp+60h+pbInput], dil
0x18005dfcc  mov     [rbp+60h+var_60], dil
0x18005dfd0  cmp     [rbp+60h+pbOutput], rdi
0x18005dfd7  jnz     short loc_18005DFE3
0x18005dfd9  mov     ebx, 80090027h
0x18005dfde  jmp     loc_18005E39E
0x18005dfe3  lea     rax, [rbp+60h+var_5C]
0x18005dfe7  mov     [rsp+0A0h+dwFlags], edi; dwFlags
0x18005dfeb  mov     [rsp+0A0h+pcbResult], rax; pcbResult
0x18005dff0  lea     r8, aPqdsapublicblo; "PQDSAPUBLICBLOB"
0x18005dff7  xor     r9d, r9d; pbOutput
0x18005dffa  mov     [rsp+0A0h+cbOutput], edi; cbOutput
0x18005dffe  xor     edx, edx; hExportKey
0x18005e000  mov     rsi, rdi
0x18005e003  call    cs:__imp_BCryptExportKey
0x18005e00a  nop     dword ptr [rax+rax+00h]
0x18005e00f  mov     ebx, eax
0x18005e011  test    eax, eax
0x18005e013  jns     short loc_18005E020
0x18005e015  mov     r9d, 48h ; 'H'
0x18005e01b  jmp     loc_18005E33A
0x18005e020  mov     ebx, [rbp+60h+var_5C]
0x18005e023  test    rbx, rbx
0x18005e026  jz      short loc_18005E089
0x18005e028  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18005e02f  ja      short loc_18005E089
0x18005e031  mov     rcx, cs:g_ulAdditionalProbeSize
0x18005e038  add     rcx, 8
0x18005e03c  add     rcx, rbx
0x18005e03f  cmp     rcx, rbx
0x18005e042  jb      short loc_18005E089
0x18005e044  call    VerifyStackAvailable
0x18005e049  test    eax, eax
0x18005e04b  jz      short loc_18005E089
0x18005e04d  lea     rax, [rbx+8]
0x18005e051  lea     rcx, [rax+0Fh]
0x18005e055  cmp     rcx, rax
0x18005e058  ja      short loc_18005E064
0x18005e05a  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18005e064  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18005e068  mov     rax, rcx
0x18005e06b  call    _alloca_probe
0x18005e070  sub     rsp, rcx
0x18005e073  lea     rdi, [rsp+0A0h+var_60]
0x18005e078  test    rdi, rdi
0x18005e07b  jz      short loc_18005E089
0x18005e07d  mov     dword ptr [rdi], 6B637453h
0x18005e083  add     rdi, 8
0x18005e087  jnz     short loc_18005E0B0
0x18005e089  lea     rcx, [rbx+8]
0x18005e08d  cmp     rcx, rbx
0x18005e090  jb      short loc_18005E0B0
0x18005e092  mov     rax, cs:g_pfnAllocate
0x18005e099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e09e  mov     rdi, rax
0x18005e0a1  test    rax, rax
0x18005e0a4  jz      short loc_18005E0B0
0x18005e0a6  mov     dword ptr [rax], 70616548h
0x18005e0ac  add     rdi, 8
0x18005e0b0  test    rdi, rdi
0x18005e0b3  jnz     short loc_18005E0C8
0x18005e0b5  lea     r9d, [rdi+50h]
0x18005e0b9  mov     ebx, 8009000Eh
0x18005e0be  mov     ecx, 8009000Eh
0x18005e0c3  jmp     loc_18005E33C
0x18005e0c8  lea     rax, [rbp+60h+var_5C]
0x18005e0cc  mov     [rsp+0A0h+dwFlags], esi; dwFlags
0x18005e0d0  mov     [rsp+0A0h+pcbResult], rax; pcbResult
0x18005e0d5  lea     r8, aPqdsapublicblo; "PQDSAPUBLICBLOB"
0x18005e0dc  mov     eax, [rbp+60h+var_5C]
0x18005e0df  mov     r9, rdi; pbOutput
0x18005e0e2  xor     edx, edx; hExportKey
0x18005e0e4  mov     [rsp+0A0h+cbOutput], eax; cbOutput
0x18005e0e8  mov     rcx, r15; hKey
0x18005e0eb  call    cs:__imp_BCryptExportKey
0x18005e0f2  nop     dword ptr [rax+rax+00h]
0x18005e0f7  mov     ebx, eax
0x18005e0f9  test    eax, eax
0x18005e0fb  jns     short loc_18005E108
0x18005e0fd  mov     r9d, 57h ; 'W'
0x18005e103  jmp     loc_18005E33A
0x18005e108  mov     r15d, 40h ; '@'
0x18005e10e  cmp     cs:g_ulMaxStackAllocSize, r15
0x18005e115  jb      short loc_18005E14F
0x18005e117  mov     rcx, cs:g_ulAdditionalProbeSize
0x18005e11e  add     rcx, 48h ; 'H'
0x18005e122  cmp     rcx, r15
0x18005e125  jb      short loc_18005E14F
0x18005e127  call    VerifyStackAvailable
0x18005e12c  test    eax, eax
0x18005e12e  jz      short loc_18005E14F
0x18005e130  mov     eax, [rsp+0A0h+var_A0]
0x18005e133  sub     rsp, 50h
0x18005e137  lea     rsi, [rsp+0F0h+var_B0]
0x18005e13c  mov     eax, [rsi]
0x18005e13e  test    rsi, rsi
0x18005e141  jz      short loc_18005E14F
0x18005e143  mov     dword ptr [rsi], 6B637453h
0x18005e149  add     rsi, 8
0x18005e14d  jnz     short loc_18005E172
0x18005e14f  mov     rax, cs:g_pfnAllocate
0x18005e156  mov     ecx, 48h ; 'H'
0x18005e15b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e160  mov     rsi, rax
0x18005e163  test    rax, rax
0x18005e166  jz      short loc_18005E172
0x18005e168  mov     dword ptr [rax], 70616548h
0x18005e16e  add     rsi, 8
0x18005e172  test    rsi, rsi
0x18005e175  jnz     short loc_18005E180
0x18005e177  lea     r9d, [rsi+60h]
0x18005e17b  jmp     loc_18005E0B9
0x18005e180  mov     r9d, [rdi+4]
0x18005e184  xor     r8d, r8d
0x18005e187  mov     eax, [rdi+8]
0x18005e18a  add     r9, 0Ch
0x18005e18e  mov     [rsp+0F0h+var_C0], r15d
0x18005e193  add     r9, rdi
0x18005e196  mov     qword ptr [rsp+0F0h+cbSecret], rsi
0x18005e19b  xor     edx, edx
0x18005e19d  mov     ecx, 461h
0x18005e1a2  mov     dword ptr [rsp+0F0h+pbSecret], eax
0x18005e1a6  call    cs:__imp_BCryptHash
0x18005e1ad  nop     dword ptr [rax+rax+00h]
0x18005e1b2  mov     ebx, eax
0x18005e1b4  test    eax, eax
0x18005e1b6  jns     short loc_18005E1C3
0x18005e1b8  mov     r9d, 6Ah ; 'j'
0x18005e1be  jmp     loc_18005E33A
0x18005e1c3  mov     [rsp+0F0h+var_C0], 0; dwFlags
0x18005e1cb  lea     rdx, [rbp+60h+phHash]; phHash
0x18005e1cf  mov     [rsp+0F0h+cbSecret], 0; cbSecret
0x18005e1d7  xor     r9d, r9d; cbHashObject
0x18005e1da  xor     r8d, r8d; pbHashObject
0x18005e1dd  mov     [rsp+0F0h+pbSecret], 0; pbSecret
0x18005e1e6  mov     ecx, 461h; hAlgorithm
0x18005e1eb  call    cs:__imp_BCryptCreateHash
0x18005e1f2  nop     dword ptr [rax+rax+00h]
0x18005e1f7  mov     ebx, eax
0x18005e1f9  test    eax, eax
0x18005e1fb  jns     short loc_18005E208
0x18005e1fd  mov     r9d, 71h ; 'q'
0x18005e203  jmp     loc_18005E33A
0x18005e208  test    r14, r14
0x18005e20b  jz      short loc_18005E22E
0x18005e20d  cmp     qword ptr [r14], 0
0x18005e211  jz      short loc_18005E22E
0x18005e213  cmp     dword ptr [r14+8], 0FFh
0x18005e21b  jbe     short loc_18005E227
0x18005e21d  mov     ebx, 80090027h
0x18005e222  jmp     loc_18005E34F
0x18005e227  mov     al, [r14+8]
0x18005e22b  mov     [rbp+60h+var_60], al
0x18005e22e  mov     rcx, [rbp+60h+phHash]; hHash
0x18005e232  xor     r9d, r9d; dwFlags
0x18005e235  mov     r8d, r15d; cbInput
0x18005e238  mov     rdx, rsi; pbInput
0x18005e23b  call    cs:__imp_BCryptHashData
0x18005e242  nop     dword ptr [rax+rax+00h]
0x18005e247  mov     ebx, eax
0x18005e249  test    eax, eax
0x18005e24b  jns     short loc_18005E258
0x18005e24d  mov     r9d, 84h
0x18005e253  jmp     loc_18005E33A
0x18005e258  mov     rcx, [rbp+60h+phHash]; hHash
0x18005e25c  lea     rdx, [rbp+60h+pbInput]; pbInput
0x18005e260  xor     r9d, r9d; dwFlags
0x18005e263  lea     r8d, [r9+1]; cbInput
0x18005e267  call    cs:__imp_BCryptHashData
0x18005e26e  nop     dword ptr [rax+rax+00h]
0x18005e273  mov     ebx, eax
0x18005e275  test    eax, eax
0x18005e277  jns     short loc_18005E284
0x18005e279  mov     r9d, 8Bh
0x18005e27f  jmp     loc_18005E33A
0x18005e284  mov     rcx, [rbp+60h+phHash]; hHash
0x18005e288  lea     rdx, [rbp+60h+var_60]; pbInput
0x18005e28c  xor     r9d, r9d; dwFlags
0x18005e28f  lea     r8d, [r9+1]; cbInput
0x18005e293  call    cs:__imp_BCryptHashData
0x18005e29a  nop     dword ptr [rax+rax+00h]
0x18005e29f  mov     ebx, eax
0x18005e2a1  test    eax, eax
0x18005e2a3  jns     short loc_18005E2B0
0x18005e2a5  mov     r9d, 92h
0x18005e2ab  jmp     loc_18005E33A
0x18005e2b0  test    r14, r14
0x18005e2b3  jz      short loc_18005E2E9
0x18005e2b5  mov     rdx, [r14]; pbInput
0x18005e2b8  test    rdx, rdx
0x18005e2bb  jz      short loc_18005E2E9
0x18005e2bd  movzx   eax, [rbp+60h+var_60]
0x18005e2c1  test    al, al
0x18005e2c3  jz      short loc_18005E2E9
0x18005e2c5  mov     rcx, [rbp+60h+phHash]; hHash
0x18005e2c9  mov     r8d, eax; cbInput
0x18005e2cc  xor     r9d, r9d; dwFlags
0x18005e2cf  call    cs:__imp_BCryptHashData
0x18005e2d6  nop     dword ptr [rax+rax+00h]
0x18005e2db  mov     ebx, eax
0x18005e2dd  test    eax, eax
0x18005e2df  jns     short loc_18005E2E9
0x18005e2e1  mov     r9d, 9Bh
0x18005e2e7  jmp     short loc_18005E33A
0x18005e2e9  mov     rdx, [rbp+60h+var_50]; pbInput
0x18005e2ed  xor     r9d, r9d; dwFlags
0x18005e2f0  mov     rcx, [rbp+60h+phHash]; hHash
0x18005e2f4  mov     r8d, r13d; cbInput
0x18005e2f7  call    cs:__imp_BCryptHashData
0x18005e2fe  nop     dword ptr [rax+rax+00h]
0x18005e303  mov     ebx, eax
0x18005e305  test    eax, eax
0x18005e307  jns     short loc_18005E311
0x18005e309  mov     r9d, 0A3h
0x18005e30f  jmp     short loc_18005E33A
0x18005e311  mov     rdx, [rbp+60h+pbOutput]; pbOutput
0x18005e318  xor     r9d, r9d; dwFlags
0x18005e31b  mov     rcx, [rbp+60h+phHash]; hHash
0x18005e31f  mov     r8d, r15d; cbOutput
0x18005e322  call    cs:__imp_BCryptFinishHash
0x18005e329  nop     dword ptr [rax+rax+00h]
0x18005e32e  mov     ebx, eax
0x18005e330  test    eax, eax
0x18005e332  jns     short loc_18005E34F
0x18005e334  mov     r9d, 0ABh
0x18005e33a  mov     ecx, eax
0x18005e33c  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005e343  lea     rdx, aStatus; "Status"
0x18005e34a  call    DebugTraceError
0x18005e34f  mov     rcx, [rbp+60h+phHash]; hHash
0x18005e353  test    rcx, rcx
0x18005e356  jz      short loc_18005E364
0x18005e358  call    cs:__imp_BCryptDestroyHash
0x18005e35f  nop     dword ptr [rax+rax+00h]
0x18005e364  test    rdi, rdi
0x18005e367  jz      short loc_18005E381
0x18005e369  lea     rcx, [rdi-8]
0x18005e36d  cmp     dword ptr [rcx], 70616548h
0x18005e373  jnz     short loc_18005E381
0x18005e375  mov     rax, cs:g_pfnFree
0x18005e37c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e381  test    rsi, rsi
0x18005e384  jz      short loc_18005E39E
0x18005e386  lea     rcx, [rsi-8]
0x18005e38a  cmp     dword ptr [rcx], 70616548h
0x18005e390  jnz     short loc_18005E39E
0x18005e392  mov     rax, cs:g_pfnFree
0x18005e399  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e39e  mov     eax, ebx
0x18005e3a0  mov     rcx, [rbp+60h+var_40]
0x18005e3a4  xor     rcx, rbp; StackCookie
0x18005e3a7  call    __security_check_cookie
0x18005e3ac  lea     rsp, [rbp+30h]
0x18005e3b0  pop     r15
0x18005e3b2  pop     r14
0x18005e3b4  pop     r13
0x18005e3b6  pop     rdi
0x18005e3b7  pop     rsi
0x18005e3b8  pop     rbx
0x18005e3b9  pop     rbp
0x18005e3ba  retn
```
