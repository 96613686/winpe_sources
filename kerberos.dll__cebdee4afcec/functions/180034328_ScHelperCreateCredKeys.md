# ScHelperCreateCredKeys

- ea: `0x180034328`
- end: `0x18003498e`
- name: `ScHelperCreateCredKeys`
- size: `1638`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, DWORD dwKeySpec@<edx>, int, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800d71e8`
- `0x1800d78e0`

## callees

- `0x180007e80`
- `0x180034328`
- `0x180034f04`
- `0x18006882c`
- `0x18006bf90`
- `0x180070680`
- `0x1800d64c0`
- `0x1800f1ea0`
- `0x1800f5010`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x18003464c`
- `bcrypt!BCryptCreateHash` at `0x18003464c`
- `bcrypt!BCryptHashData` at `0x18003466e`
- `bcrypt!BCryptHashData` at `0x18003466e`
- `bcrypt!BCryptDestroyHash` at `0x18003493f`
- `bcrypt!BCryptDestroyHash` at `0x18003493f`
- `bcrypt!BCryptFinishHash` at `0x18003468d`
- `bcrypt!BCryptFinishHash` at `0x18003468d`
- `ncrypt!NCryptSignHash` at `0x1800346f6`
- `ncrypt!NCryptSignHash` at `0x1800347c6`
- `ncrypt!NCryptSignHash` at `0x1800346f6`
- `ncrypt!NCryptSignHash` at `0x1800347c6`
- `CRYPTSP!CryptCreateHash` at `0x18003445c`
- `CRYPTSP!CryptCreateHash` at `0x180034859`
- `CRYPTSP!CryptCreateHash` at `0x18003445c`
- `CRYPTSP!CryptCreateHash` at `0x180034859`
- `CRYPTSP!CryptDeriveKey` at `0x1800348bb`
- `CRYPTSP!CryptDeriveKey` at `0x1800348e1`
- `CRYPTSP!CryptDeriveKey` at `0x1800348bb`
- `CRYPTSP!CryptDeriveKey` at `0x1800348e1`
- `CRYPTSP!CryptHashData` at `0x180034477`
- `CRYPTSP!CryptHashData` at `0x180034875`
- `CRYPTSP!CryptHashData` at `0x180034895`
- `CRYPTSP!CryptHashData` at `0x180034477`
- `CRYPTSP!CryptHashData` at `0x180034875`
- `CRYPTSP!CryptHashData` at `0x180034895`
- `CRYPTSP!CryptDestroyHash` at `0x180034904`
- `CRYPTSP!CryptDestroyHash` at `0x180034913`
- `CRYPTSP!CryptDestroyHash` at `0x180034904`
- `CRYPTSP!CryptDestroyHash` at `0x180034913`
- `CRYPTSP!CryptSignHashW` at `0x18003449c`
- `CRYPTSP!CryptSignHashW` at `0x180034557`
- `CRYPTSP!CryptSignHashW` at `0x18003449c`
- `CRYPTSP!CryptSignHashW` at `0x180034557`
- `CRYPTSP!CryptReleaseContext` at `0x180034417`
- `CRYPTSP!CryptReleaseContext` at `0x180034417`
- `CRYPTSP!CryptAcquireContextW` at `0x1800343f0`
- `CRYPTSP!CryptAcquireContextW` at `0x1800343f0`

## pseudocode

```c
__int64 __fastcall ScHelperCreateCredKeys(
        void *a1,
        DWORD dwKeySpec,
        __int64 a3,
        UCHAR *a4,
        int a5,
        HCRYPTKEY *a6,
        HCRYPTKEY *a7,
        HCRYPTPROV *a8)
{
  UCHAR *p_pcbResult; // r14
  NTSTATUS IsNcryptRsaKey; // ebx
  BYTE *p_hBaseData; // rdi
  HCRYPTPROV v14; // rax
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  unsigned __int64 v18; // rbx
  unsigned __int64 v19; // rcx
  __int64 v20; // rsi
  unsigned __int64 v21; // rsi
  void *v22; // rsp
  void *v23; // rsp
  BYTE *v24; // rax
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // r9
  void *HelperSha1AlgHandle; // r15
  unsigned __int64 v29; // rbx
  unsigned __int64 v30; // rcx
  __int64 v31; // rcx
  unsigned __int64 v32; // rcx
  void *v33; // rsp
  void *v34; // rsp
  UCHAR *v35; // rax
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // r9
  unsigned __int64 v39; // rbx
  unsigned __int64 v40; // rcx
  __int64 v41; // rcx
  unsigned __int64 v42; // rcx
  void *v43; // rsp
  void *v44; // rsp
  BYTE *v45; // rax
  HCRYPTPROV *v46; // rbx
  _BYTE v48[32]; // [rsp+0h] [rbp-40h] BYREF
  DWORD pcbResult; // [rsp+40h] [rbp+0h] BYREF
  HCRYPTHASH hBaseData; // [rsp+48h] [rbp+8h] BYREF
  int v51; // [rsp+50h] [rbp+10h] BYREF
  HCRYPTHASH phHash; // [rsp+58h] [rbp+18h] BYREF
  HCRYPTPROV phProv; // [rsp+60h] [rbp+20h] BYREF
  BCRYPT_HASH_HANDLE hHash; // [rsp+68h] [rbp+28h] BYREF
  const WCHAR *pPaddingInfo; // [rsp+70h] [rbp+30h] BYREF
  PUCHAR pbInput; // [rsp+78h] [rbp+38h]
  __int64 v57; // [rsp+80h] [rbp+40h]
  HCRYPTPROV *v58; // [rsp+88h] [rbp+48h]
  HCRYPTKEY *phKey; // [rsp+90h] [rbp+50h]
  HCRYPTKEY *v60; // [rsp+98h] [rbp+58h]
  UCHAR pbOutput[24]; // [rsp+A8h] [rbp+68h] BYREF

  p_pcbResult = 0;
  pbInput = a4;
  *a8 = 0;
  v57 = a3;
  v60 = a6;
  phKey = a7;
  v58 = a8;
  phHash = 0;
  pcbResult = 0;
  hBaseData = 0;
  hHash = 0;
  if ( !a1 )
    return (unsigned int)-1073741023;
  if ( a4 && a6 && a7 )
  {
    p_hBaseData = 0;
    phProv = 0;
    if ( !g_hProvHelper )
    {
      if ( !CryptAcquireContextW(&phProv, 0, L"Microsoft Strong Cryptographic Provider", 1u, 0xF0000000) )
      {
        v14 = phProv;
        goto LABEL_12;
      }
      if ( _InterlockedCompareExchange64((volatile signed __int64 *)&g_hProvHelper, phProv, 0) )
        CryptReleaseContext(phProv, 0);
    }
    v14 = g_hProvHelper;
LABEL_12:
    *a8 = v14;
    if ( !v14 )
    {
LABEL_13:
      IsNcryptRsaKey = -1073741023;
      goto LABEL_78;
    }
    if ( dwKeySpec - 1 > 0xFFFFFFFD )
    {
      pPaddingInfo = 0;
      v51 = 0;
      HelperSha1AlgHandle = I_ScHelperGetHelperSha1AlgHandle();
      if ( !HelperSha1AlgHandle )
      {
        IsNcryptRsaKey = -1073741670;
        goto LABEL_78;
      }
      v29 = g_cbHashObjectLength;
      if ( !g_cbHashObjectLength )
        goto LABEL_94;
      if ( g_cbHashObjectLength > (unsigned __int64)g_ulMaxStackAllocSize )
        goto LABEL_94;
      v30 = g_cbHashObjectLength + g_ulAdditionalProbeSize + 8;
      if ( v30 < g_cbHashObjectLength || !(unsigned int)VerifyStackAvailable(v30, v25, v26, v27) )
        goto LABEL_94;
      v31 = v29 + 23;
      if ( v29 + 23 <= v29 + 8 )
        v31 = 0xFFFFFFFFFFFFFF0LL;
      v32 = v31 & 0xFFFFFFFFFFFFFFF0uLL;
      v33 = alloca(v32);
      v34 = alloca(v32);
      p_pcbResult = (UCHAR *)&pcbResult;
      if ( v48 == (_BYTE *)-64LL || (pcbResult = 1801679955, (p_pcbResult = (UCHAR *)&hBaseData) == 0) )
      {
LABEL_94:
        if ( v29 + 8 >= v29 )
        {
          v35 = (UCHAR *)((__int64 (*)(void))g_pfnAllocate)();
          p_pcbResult = v35;
          if ( v35 )
          {
            *(_DWORD *)v35 = 1885431112;
            p_pcbResult = v35 + 8;
          }
        }
      }
      if ( p_pcbResult )
      {
        IsNcryptRsaKey = BCryptCreateHash(HelperSha1AlgHandle, &hHash, p_pcbResult, g_cbHashObjectLength, 0, 0, 0);
        if ( IsNcryptRsaKey < 0 )
          goto LABEL_78;
        IsNcryptRsaKey = BCryptHashData(hHash, pbInput, 0x20u, 0);
        if ( IsNcryptRsaKey < 0 )
          goto LABEL_78;
        IsNcryptRsaKey = BCryptFinishHash(hHash, pbOutput, 0x14u, 0);
        if ( IsNcryptRsaKey < 0 )
          goto LABEL_78;
        IsNcryptRsaKey = ScHelperIsNcryptRsaKey(1, a1, &v51);
        if ( IsNcryptRsaKey < 0 )
          goto LABEL_78;
        if ( !v51 )
        {
          IsNcryptRsaKey = -1073741637;
          goto LABEL_78;
        }
        pPaddingInfo = L"SHA1";
        IsNcryptRsaKey = NCryptSignHash((NCRYPT_KEY_HANDLE)a1, &pPaddingInfo, pbOutput, 0x14u, 0, 0, &pcbResult, 2u);
        if ( IsNcryptRsaKey < 0 )
        {
LABEL_78:
          if ( phHash )
            CryptDestroyHash(phHash);
          if ( hBaseData )
            CryptDestroyHash(hBaseData);
          if ( p_hBaseData && *((_DWORD *)p_hBaseData - 2) == 1885431112 )
            ((void (*)(void))g_pfnFree)();
          if ( hHash )
            BCryptDestroyHash(hHash);
          if ( p_pcbResult )
          {
            if ( *((_DWORD *)p_pcbResult - 2) == 1885431112 )
              ((void (*)(void))g_pfnFree)();
          }
          return (unsigned int)IsNcryptRsaKey;
        }
        v39 = pcbResult;
        if ( !pcbResult )
          goto LABEL_95;
        if ( pcbResult > (unsigned __int64)g_ulMaxStackAllocSize )
          goto LABEL_95;
        v40 = pcbResult + g_ulAdditionalProbeSize + 8;
        if ( v40 < pcbResult || !(unsigned int)VerifyStackAvailable(v40, v36, v37, v38) )
          goto LABEL_95;
        v41 = v39 + 23;
        if ( v39 + 23 <= v39 + 8 )
          v41 = 0xFFFFFFFFFFFFFF0LL;
        v42 = v41 & 0xFFFFFFFFFFFFFFF0uLL;
        v43 = alloca(v42);
        v44 = alloca(v42);
        p_hBaseData = (BYTE *)&pcbResult;
        if ( v48 == (_BYTE *)-64LL || (pcbResult = 1801679955, (p_hBaseData = (BYTE *)&hBaseData) == 0) )
        {
LABEL_95:
          if ( v39 + 8 >= v39 )
          {
            v45 = (BYTE *)((__int64 (*)(void))g_pfnAllocate)();
            p_hBaseData = v45;
            if ( v45 )
            {
              *(_DWORD *)v45 = 1885431112;
              p_hBaseData = v45 + 8;
            }
          }
        }
        if ( p_hBaseData )
        {
          IsNcryptRsaKey = NCryptSignHash(
                             (NCRYPT_KEY_HANDLE)a1,
                             &pPaddingInfo,
                             pbOutput,
                             0x14u,
                             p_hBaseData,
                             pcbResult,
                             &pcbResult,
                             2u);
          if ( IsNcryptRsaKey < 0 )
            goto LABEL_78;
          goto LABEL_65;
        }
      }
    }
    else
    {
      if ( !CryptCreateHash((HCRYPTPROV)a1, 0x8004u, 0, 0, &phHash) )
        goto LABEL_13;
      if ( !CryptHashData(phHash, a4, 0x20u, 0) )
        goto LABEL_13;
      CryptSignHashW(phHash, dwKeySpec, 0, 0, 0, &pcbResult);
      if ( !pcbResult )
        goto LABEL_13;
      v18 = pcbResult;
      if ( pcbResult > (unsigned __int64)g_ulMaxStackAllocSize )
        goto LABEL_96;
      v19 = pcbResult + g_ulAdditionalProbeSize + 8;
      if ( v19 < pcbResult || !(unsigned int)VerifyStackAvailable(v19, v15, v16, v17) )
        goto LABEL_96;
      v20 = v18 + 23;
      if ( v18 + 23 <= v18 + 8 )
        v20 = 0xFFFFFFFFFFFFFF0LL;
      v21 = v20 & 0xFFFFFFFFFFFFFFF0uLL;
      v22 = alloca(v21);
      v23 = alloca(v21);
      p_hBaseData = (BYTE *)&pcbResult;
      if ( v48 == (_BYTE *)-64LL || (pcbResult = 1801679955, (p_hBaseData = (BYTE *)&hBaseData) == 0) )
      {
LABEL_96:
        if ( v18 + 8 >= v18 )
        {
          v24 = (BYTE *)((__int64 (*)(void))g_pfnAllocate)();
          p_hBaseData = v24;
          if ( v24 )
          {
            *(_DWORD *)v24 = 1885431112;
            p_hBaseData = v24 + 8;
          }
        }
      }
      if ( p_hBaseData )
      {
        if ( !CryptSignHashW(phHash, dwKeySpec, 0, 0, p_hBaseData, &pcbResult) )
          goto LABEL_13;
LABEL_65:
        if ( a5 )
        {
          if ( dwKeySpec - 1 <= 0xFFFFFFFD )
            ReverseBytes(p_hBaseData, pcbResult);
          if ( (unsigned int)ScHelperVerifyMessage(v57, (__int64)L"SHA1", pbInput, 0x20u, p_hBaseData, pcbResult) )
            goto LABEL_13;
        }
        else if ( ((dwKeySpec + 1) & 0xFFFFFFFE) != 0 )
        {
LABEL_72:
          v46 = v58;
          if ( CryptCreateHash(*v58, 0x8004u, 0, 0, &hBaseData)
            && CryptHashData(hBaseData, p_hBaseData, pcbResult, 0)
            && CryptHashData(hBaseData, pbInput + 32, 0x20u, 0)
            && CryptDeriveKey(*v46, 0x6801u, hBaseData, 0, phKey) )
          {
            IsNcryptRsaKey = !CryptDeriveKey(*v46, 0x6602u, hBaseData, 0, v60) ? 0xC0000321 : 0;
            goto LABEL_78;
          }
          goto LABEL_13;
        }
        ReverseBytes(p_hBaseData, pcbResult);
        goto LABEL_72;
      }
    }
    IsNcryptRsaKey = -1073741801;
    goto LABEL_78;
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x180034328  push    rbp
0x18003432a  push    rbx
0x18003432b  push    rsi
0x18003432c  push    rdi
0x18003432d  push    r12
0x18003432f  push    r13
0x180034331  push    r14
0x180034333  push    r15
0x180034335  sub     rsp, 0D8h
0x18003433c  lea     rbp, [rsp+40h]
0x180034341  mov     rax, cs:__security_cookie
0x180034348  xor     rax, rbp
0x18003434b  mov     [rbp+0D0h+var_50], rax
0x180034352  mov     rbx, [rbp+0D0h+arg_38]
0x180034359  xor     r14d, r14d
0x18003435c  mov     rax, [rbp+0D0h+arg_30]
0x180034363  mov     r12, rcx
0x180034366  mov     rcx, [rbp+0D0h+arg_28]
0x18003436d  mov     rsi, r9
0x180034370  mov     [rbp+0D0h+pbInput], r9
0x180034374  mov     r13d, edx
0x180034377  mov     [rbx], r14
0x18003437a  mov     [rbp+0D0h+var_90], r8
0x18003437e  mov     [rbp+0D0h+var_78], rcx
0x180034382  mov     [rbp+0D0h+phKey], rax
0x180034386  mov     [rbp+0D0h+var_88], rbx
0x18003438a  mov     [rbp+0D0h+phHash], r14
0x18003438e  mov     [rbp+0D0h+pcbResult], r14d
0x180034392  mov     [rbp+0D0h+hBaseData], r14
0x180034396  mov     [rbp+0D0h+hHash], r14
0x18003439a  test    r12, r12
0x18003439d  jnz     short loc_1800343A9
0x18003439f  mov     ebx, 0C0000321h
0x1800343a4  jmp     loc_180034962
0x1800343a9  test    rsi, rsi
0x1800343ac  jz      loc_180034966
0x1800343b2  test    rcx, rcx
0x1800343b5  jz      loc_180034966
0x1800343bb  test    rax, rax
0x1800343be  jz      loc_180034966
0x1800343c4  mov     rax, cs:?g_hProvHelper@@3_KC; unsigned __int64 volatile g_hProvHelper
0x1800343cb  mov     rdi, r14
0x1800343ce  mov     [rbp+0D0h+phProv], r14
0x1800343d2  test    rax, rax
0x1800343d5  jnz     short loc_18003441D
0x1800343d7  lea     r9d, [rax+1]; dwProvType
0x1800343db  mov     [rsp+110h+dwFlags], 0F0000000h; dwFlags
0x1800343e3  lea     r8, szProvider; "Microsoft Strong Cryptographic Provider"
0x1800343ea  xor     edx, edx; szContainer
0x1800343ec  lea     rcx, [rbp+0D0h+phProv]; phProv
0x1800343f0  call    cs:__imp_CryptAcquireContextW
0x1800343f6  test    eax, eax
0x1800343f8  jnz     short loc_180034400
0x1800343fa  mov     rax, [rbp+0D0h+phProv]
0x1800343fe  jmp     short loc_180034424
0x180034400  mov     rcx, [rbp+0D0h+phProv]
0x180034404  xor     eax, eax
0x180034406  lock cmpxchg cs:?g_hProvHelper@@3_KC, rcx; unsigned __int64 volatile g_hProvHelper
0x18003440f  jz      short loc_18003441D
0x180034411  mov     rcx, [rbp+0D0h+phProv]; hProv
0x180034415  xor     edx, edx; dwFlags
0x180034417  call    cs:__imp_CryptReleaseContext
0x18003441d  mov     rax, cs:?g_hProvHelper@@3_KC; unsigned __int64 volatile g_hProvHelper
0x180034424  mov     [rbx], rax
0x180034427  xor     ebx, ebx
0x180034429  test    rax, rax
0x18003442c  jnz     short loc_180034438
0x18003442e  mov     ebx, 0C0000321h
0x180034433  jmp     loc_1800348FB
0x180034438  lea     eax, [r13-1]
0x18003443c  cmp     eax, 0FFFFFFFDh
0x18003443f  ja      loc_18003456A
0x180034445  lea     rax, [rbp+0D0h+phHash]
0x180034449  xor     r9d, r9d; dwFlags
0x18003444c  xor     r8d, r8d; hKey
0x18003444f  mov     qword ptr [rsp+110h+dwFlags], rax; phHash
0x180034454  mov     edx, 8004h; Algid
0x180034459  mov     rcx, r12; hProv
0x18003445c  call    cs:__imp_CryptCreateHash
0x180034462  test    eax, eax
0x180034464  jz      short loc_18003442E
0x180034466  mov     rcx, [rbp+0D0h+phHash]; hHash
0x18003446a  xor     r9d, r9d; dwFlags
0x18003446d  mov     rdx, rsi; pbData
0x180034470  lea     r15d, [r9+20h]
0x180034474  mov     r8d, r15d; dwDataLen
0x180034477  call    cs:__imp_CryptHashData
0x18003447d  test    eax, eax
0x18003447f  jz      short loc_18003442E
0x180034481  mov     rcx, [rbp+0D0h+phHash]; hHash
0x180034485  lea     rax, [rbp+0D0h+pcbResult]
0x180034489  mov     [rsp+110h+pdwSigLen], rax; pdwSigLen
0x18003448e  xor     r9d, r9d; dwFlags
0x180034491  xor     r8d, r8d; szDescription
0x180034494  mov     qword ptr [rsp+110h+dwFlags], rbx; pbSignature
0x180034499  mov     edx, r13d; dwKeySpec
0x18003449c  call    cs:__imp_CryptSignHashW
0x1800344a2  mov     eax, [rbp+0D0h+pcbResult]
0x1800344a5  test    eax, eax
0x1800344a7  jz      short loc_18003442E
0x1800344a9  cmp     rax, cs:g_ulMaxStackAllocSize
0x1800344b0  mov     ebx, eax
0x1800344b2  ja      short loc_18003450C
0x1800344b4  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800344bb  add     rcx, 8
0x1800344bf  add     rcx, rax
0x1800344c2  cmp     rcx, rax
0x1800344c5  jb      short loc_18003450C
0x1800344c7  call    VerifyStackAvailable
0x1800344cc  test    eax, eax
0x1800344ce  jz      short loc_18003450C
0x1800344d0  lea     rax, [rbx+8]
0x1800344d4  lea     rsi, [rax+0Fh]
0x1800344d8  cmp     rsi, rax
0x1800344db  ja      short loc_1800344E7
0x1800344dd  mov     rsi, 0FFFFFFFFFFFFFF0h
0x1800344e7  and     rsi, 0FFFFFFFFFFFFFFF0h
0x1800344eb  mov     rax, rsi
0x1800344ee  call    _alloca_probe
0x1800344f3  sub     rsp, rsi
0x1800344f6  lea     rdi, [rsp+110h+pcbResult]
0x1800344fb  test    rdi, rdi
0x1800344fe  jz      short loc_18003450C
0x180034500  mov     dword ptr [rdi], 6B637453h
0x180034506  add     rdi, 8
0x18003450a  jnz     short loc_180034533
0x18003450c  lea     rcx, [rbx+8]
0x180034510  cmp     rcx, rbx
0x180034513  jb      short loc_180034533
0x180034515  mov     rax, cs:g_pfnAllocate
0x18003451c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034521  mov     rdi, rax
0x180034524  test    rax, rax
0x180034527  jz      short loc_180034533
0x180034529  mov     dword ptr [rax], 70616548h
0x18003452f  add     rdi, 8
0x180034533  test    rdi, rdi
0x180034536  jz      loc_180034624
0x18003453c  mov     rcx, [rbp+0D0h+phHash]; hHash
0x180034540  lea     rax, [rbp+0D0h+pcbResult]
0x180034544  mov     [rsp+110h+pdwSigLen], rax; pdwSigLen
0x180034549  xor     r9d, r9d; dwFlags
0x18003454c  xor     r8d, r8d; szDescription
0x18003454f  mov     qword ptr [rsp+110h+dwFlags], rdi; pbSignature
0x180034554  mov     edx, r13d; dwKeySpec
0x180034557  call    cs:__imp_CryptSignHashW
0x18003455d  test    eax, eax
0x18003455f  jnz     loc_1800347D6
0x180034565  jmp     loc_18003442E
0x18003456a  mov     [rbp+0D0h+pPaddingInfo], rbx
0x18003456e  mov     [rbp+0D0h+var_C0], ebx
0x180034571  call    ?I_ScHelperGetHelperSha1AlgHandle@@YAPEAXXZ; I_ScHelperGetHelperSha1AlgHandle(void)
0x180034576  mov     r15, rax
0x180034579  test    rax, rax
0x18003457c  jnz     short loc_180034588
0x18003457e  mov     ebx, 0C000009Ah
0x180034583  jmp     loc_1800348FB
0x180034588  mov     ebx, cs:?g_cbHashObjectLength@@3KA; ulong g_cbHashObjectLength
0x18003458e  mov     rsi, 0FFFFFFFFFFFFFF0h
0x180034598  test    rbx, rbx
0x18003459b  jz      short loc_1800345F8
0x18003459d  cmp     rbx, cs:g_ulMaxStackAllocSize
0x1800345a4  ja      short loc_1800345F8
0x1800345a6  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800345ad  add     rcx, 8
0x1800345b1  add     rcx, rbx
0x1800345b4  cmp     rcx, rbx
0x1800345b7  jb      short loc_1800345F8
0x1800345b9  call    VerifyStackAvailable
0x1800345be  test    eax, eax
0x1800345c0  jz      short loc_1800345F8
0x1800345c2  lea     rax, [rbx+8]
0x1800345c6  lea     rcx, [rax+0Fh]
0x1800345ca  cmp     rcx, rax
0x1800345cd  ja      short loc_1800345D2
0x1800345cf  mov     rcx, rsi
0x1800345d2  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800345d6  mov     rax, rcx
0x1800345d9  call    _alloca_probe
0x1800345de  sub     rsp, rcx
0x1800345e1  lea     r14, [rsp+110h+pcbResult]
0x1800345e6  test    r14, r14
0x1800345e9  jz      short loc_1800345F8
0x1800345eb  mov     dword ptr [r14], 6B637453h
0x1800345f2  add     r14, 8
0x1800345f6  jnz     short loc_18003461F
0x1800345f8  lea     rcx, [rbx+8]
0x1800345fc  cmp     rcx, rbx
0x1800345ff  jb      short loc_18003461F
0x180034601  mov     rax, cs:g_pfnAllocate
0x180034608  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003460d  mov     r14, rax
0x180034610  test    rax, rax
0x180034613  jz      short loc_18003461F
0x180034615  mov     dword ptr [rax], 70616548h
0x18003461b  add     r14, 8
0x18003461f  test    r14, r14
0x180034622  jnz     short loc_18003462E
0x180034624  mov     ebx, 0C0000017h
0x180034629  jmp     loc_1800348FB
0x18003462e  mov     r9d, cs:?g_cbHashObjectLength@@3KA; cbHashObject
0x180034635  lea     rdx, [rbp+0D0h+hHash]; phHash
0x180034639  mov     [rsp+110h+var_E0], edi; dwFlags
0x18003463d  mov     r8, r14; pbHashObject
0x180034640  mov     dword ptr [rsp+110h+pdwSigLen], edi; cbSecret
0x180034644  mov     rcx, r15; hAlgorithm
0x180034647  mov     qword ptr [rsp+110h+dwFlags], rdi; pbSecret
0x18003464c  call    cs:__imp_BCryptCreateHash
0x180034652  mov     ebx, eax
0x180034654  test    eax, eax
0x180034656  js      loc_1800348FB
0x18003465c  mov     rdx, [rbp+0D0h+pbInput]; pbInput
0x180034660  xor     r9d, r9d; dwFlags
0x180034663  mov     rcx, [rbp+0D0h+hHash]; hHash
0x180034667  lea     r15d, [r9+20h]
0x18003466b  mov     r8d, r15d; cbInput
0x18003466e  call    cs:__imp_BCryptHashData
0x180034674  mov     ebx, eax
0x180034676  test    eax, eax
0x180034678  js      loc_1800348FB
0x18003467e  mov     rcx, [rbp+0D0h+hHash]; hHash
0x180034682  lea     r8d, [r15-0Ch]; cbOutput
0x180034686  xor     r9d, r9d; dwFlags
0x180034689  lea     rdx, [rbp+0D0h+pbOutput]; pbOutput
0x18003468d  call    cs:__imp_BCryptFinishHash
0x180034693  mov     ebx, eax
0x180034695  test    eax, eax
0x180034697  js      loc_1800348FB
0x18003469d  lea     r8, [rbp+0D0h+var_C0]; int *
0x1800346a1  mov     rdx, r12; void *
0x1800346a4  lea     ecx, [r15-1Fh]; int
0x1800346a8  call    ?ScHelperIsNcryptRsaKey@@YAJHPEAXPEAH@Z; ScHelperIsNcryptRsaKey(int,void *,int *)
0x1800346ad  xor     ecx, ecx
0x1800346af  mov     ebx, eax
0x1800346b1  test    eax, eax
0x1800346b3  js      loc_1800348FB
0x1800346b9  cmp     [rbp+0D0h+var_C0], ecx
0x1800346bc  jz      loc_1800348F6
0x1800346c2  mov     [rsp+110h+var_D8], 2; dwFlags
0x1800346ca  lea     rax, pszAlgId; "SHA1"
0x1800346d1  mov     [rbp+0D0h+pPaddingInfo], rax
0x1800346d5  lea     r9d, [r15-0Ch]; cbHashValue
0x1800346d9  lea     rax, [rbp+0D0h+pcbResult]
0x1800346dd  mov     qword ptr [rsp+110h+var_E0], rax; pcbResult
0x1800346e2  lea     r8, [rbp+0D0h+pbOutput]; pbHashValue
0x1800346e6  mov     dword ptr [rsp+110h+pdwSigLen], ecx; cbSignature
0x1800346ea  lea     rdx, [rbp+0D0h+pPaddingInfo]; pPaddingInfo
0x1800346ee  mov     qword ptr [rsp+110h+dwFlags], rcx; pbSignature
0x1800346f3  mov     rcx, r12; hKey
0x1800346f6  call    cs:__imp_NCryptSignHash
0x1800346fc  mov     ebx, eax
0x1800346fe  test    eax, eax
0x180034700  js      loc_1800348FB
0x180034706  mov     ebx, [rbp+0D0h+pcbResult]
0x180034709  test    rbx, rbx
0x18003470c  jz      short loc_180034768
0x18003470e  cmp     rbx, cs:g_ulMaxStackAllocSize
0x180034715  ja      short loc_180034768
0x180034717  mov     rcx, cs:g_ulAdditionalProbeSize
0x18003471e  add     rcx, 8
0x180034722  add     rcx, rbx
0x180034725  cmp     rcx, rbx
0x180034728  jb      short loc_180034768
0x18003472a  call    VerifyStackAvailable
0x18003472f  test    eax, eax
0x180034731  jz      short loc_180034768
0x180034733  lea     rax, [rbx+8]
0x180034737  lea     rcx, [rax+0Fh]
0x18003473b  cmp     rcx, rax
0x18003473e  ja      short loc_180034743
0x180034740  mov     rcx, rsi
0x180034743  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180034747  mov     rax, rcx
0x18003474a  call    _alloca_probe
0x18003474f  sub     rsp, rcx
0x180034752  lea     rdi, [rsp+110h+pcbResult]
0x180034757  test    rdi, rdi
0x18003475a  jz      short loc_180034768
0x18003475c  mov     dword ptr [rdi], 6B637453h
0x180034762  add     rdi, 8
0x180034766  jnz     short loc_18003478F
0x180034768  lea     rcx, [rbx+8]
0x18003476c  cmp     rcx, rbx
0x18003476f  jb      short loc_18003478F
0x180034771  mov     rax, cs:g_pfnAllocate
0x180034778  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003477d  mov     rdi, rax
0x180034780  test    rax, rax
0x180034783  jz      short loc_18003478F
0x180034785  mov     dword ptr [rax], 70616548h
0x18003478b  add     rdi, 8
0x18003478f  test    rdi, rdi
0x180034792  jz      loc_180034624
0x180034798  lea     rax, [rbp+0D0h+pcbResult]
0x18003479c  mov     [rsp+110h+var_D8], 2; dwFlags
0x1800347a4  mov     qword ptr [rsp+110h+var_E0], rax; pcbResult
0x1800347a9  lea     r8, [rbp+0D0h+pbOutput]; pbHashValue
0x1800347ad  mov     eax, [rbp+0D0h+pcbResult]
0x1800347b0  lea     rdx, [rbp+0D0h+pPaddingInfo]; pPaddingInfo
0x1800347b4  mov     dword ptr [rsp+110h+pdwSigLen], eax; cbSignature
  ... truncated ...
```
