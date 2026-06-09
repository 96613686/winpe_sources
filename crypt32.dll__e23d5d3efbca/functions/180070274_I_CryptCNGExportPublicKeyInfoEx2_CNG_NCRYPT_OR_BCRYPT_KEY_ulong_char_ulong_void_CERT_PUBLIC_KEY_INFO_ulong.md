# I_CryptCNGExportPublicKeyInfoEx2(_CNG_NCRYPT_OR_BCRYPT_KEY *,ulong,char *,ulong,void *,_CERT_PUBLIC_KEY_INFO *,ulong *)

- ea: `0x180070274`
- end: `0x180070748`
- name: `?I_CryptCNGExportPublicKeyInfoEx2@@YAHPEAU_CNG_NCRYPT_OR_BCRYPT_KEY@@KPEADKPEAXPEAU_CERT_PUBLIC_KEY_INFO@@PEAK@Z`
- size: `1236`
- prototype: `__int64 __usercall@<rax>(struct _CNG_NCRYPT_OR_BCRYPT_KEY *@<rcx>, unsigned int@<edx>, char *pvKey@<r8>, unsigned int@<r9d>, void *, struct _CERT_PUBLIC_KEY_INFO *, unsigned int *)`
- caller_count: `4`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18006e740`
- `0x1800701b0`
- `0x180071360`
- `0x180071cb0`

## callees

- `0x180009da0`
- `0x180026220`
- `0x1800286e0`
- `0x180028d60`
- `0x180070274`
- `0x1800711f0`
- `0x1800a1488`
- `0x1800aabc8`
- `0x1800b81dc`
- `0x1800ddd0c`
- `0x1800de230`
- `0x1800e26cc`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800703e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007046c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800706fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800703e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007046c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800706fc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800706f6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180070728`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800706f6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180070728`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800704a5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800704e6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180070544`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180070572`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800705fa`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180070623`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800704a5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800704e6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180070544`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180070572`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800705fa`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180070623`

## pseudocode

```c
__int64 __fastcall I_CryptCNGExportPublicKeyInfoEx2(
        struct _CNG_NCRYPT_OR_BCRYPT_KEY *a1,
        DWORD a2,
        char *pvKey,
        unsigned int a4,
        void *a5,
        struct _CERT_PUBLIC_KEY_INFO *a6,
        unsigned int *a7)
{
  int v7; // r14d
  char *pszOID; // rbx
  DWORD v12; // ecx
  PCCRYPT_OID_INFO OIDInfoFromCNGKey; // rax
  PCCRYPT_OID_INFO v14; // rdi
  PCCRYPT_OID_INFO OIDInfo; // rax
  _WORD *v16; // rcx
  unsigned int v17; // r13d
  unsigned int v18; // ecx
  const WCHAR *v20; // r13
  int v21; // eax
  int v22; // r9d
  int v23; // r15d
  PCCRYPT_OID_INFO v24; // rax
  int v25; // eax
  const struct _CRYPT_OID_INFO *v26; // rcx
  DWORD LastError; // edi
  unsigned int v28; // ebx
  void **ppvFuncAddr; // [rsp+20h] [rbp-50h]
  unsigned int Size; // [rsp+40h] [rbp-30h] BYREF
  unsigned int Size_4; // [rsp+44h] [rbp-2Ch]
  HLOCAL hMem; // [rsp+48h] [rbp-28h] BYREF
  HLOCAL v33; // [rsp+50h] [rbp-20h] BYREF
  HCRYPTOIDFUNCADDR phFuncAddr; // [rsp+58h] [rbp-18h] BYREF
  HCRYPTOIDFUNCADDR hFuncAddr[2]; // [rsp+60h] [rbp-10h] BYREF
  char *v36; // [rsp+C0h] [rbp+50h] BYREF
  unsigned int v37; // [rsp+C8h] [rbp+58h] BYREF

  v36 = pvKey;
  hMem = 0;
  v37 = 0;
  v7 = a4 & 0x30000000;
  v33 = 0;
  Size = 0;
  pszOID = pvKey;
  if ( (a4 & 0x30000000) == 0x30000000 )
  {
    v12 = -2147024809;
LABEL_50:
    SetLastError(v12);
    goto LABEL_51;
  }
  if ( !v7 )
    v7 = 805306368;
  if ( pvKey )
  {
    OIDInfo = CryptFindOIDInfo(a4 & 0xC0000000 | 1, pvKey, 0x40000003u);
    v14 = OIDInfo;
    if ( !OIDInfo )
      goto LABEL_49;
    v16 = *(_WORD **)&OIDInfo[1].cbSize;
    if ( !v16 || !*v16 )
      goto LABEL_49;
  }
  else
  {
    OIDInfoFromCNGKey = I_CryptGetOIDInfoFromCNGKey(a1);
    v14 = OIDInfoFromCNGKey;
    if ( !OIDInfoFromCNGKey )
    {
      if ( !(unsigned int)IsGenericECCAlgorithm(a1) || (v7 & 0x10000000) == 0 )
        goto LABEL_51;
      goto LABEL_44;
    }
    pszOID = (char *)OIDInfoFromCNGKey->pszOID;
    v36 = pszOID;
  }
  phFuncAddr = 0;
  hFuncAddr[0] = 0;
  if ( !*(_DWORD *)a1 )
  {
    if ( !CryptGetOIDFunctionAddress(qword_18015CCC8, a2, pszOID, 0, hFuncAddr, &phFuncAddr) )
      goto LABEL_25;
    Size_4 = *a7;
    v17 = ((__int64 (__fastcall *)(_QWORD, _QWORD, char *, _QWORD, void *, struct _CERT_PUBLIC_KEY_INFO *, unsigned int *))hFuncAddr[0])(
            *((_QWORD *)a1 + 1),
            a2,
            pszOID,
            a4,
            a5,
            a6,
            a7);
    CryptFreeOIDFunctionAddress(phFuncAddr, 0);
    if ( !v17 && GetLastError() == 50 )
    {
      v18 = Size_4;
      goto LABEL_24;
    }
    return v17;
  }
  if ( !CryptGetOIDFunctionAddress(qword_18015CCC0, a2, pszOID, 0, &phFuncAddr, hFuncAddr) )
    goto LABEL_25;
  Size_4 = *a7;
  v17 = ((__int64 (__fastcall *)(_QWORD, _QWORD, char *, _QWORD, void *, struct _CERT_PUBLIC_KEY_INFO *, unsigned int *))phFuncAddr)(
          *((_QWORD *)a1 + 1),
          a2,
          pszOID,
          a4,
          a5,
          a6,
          a7);
  CryptFreeOIDFunctionAddress(hFuncAddr[0], 0);
  if ( v17 || GetLastError() != 50 )
    return v17;
  v18 = Size_4;
LABEL_24:
  *a7 = v18;
LABEL_25:
  v20 = *(const WCHAR **)&v14[1].cbSize;
  if ( CompareStringW(0x409u, 1u, v20, -1, L"RSA", -1) == 2 )
  {
    v21 = EncodeCNGRSAPublicKey(a1, a2, &hMem, &v37);
    goto LABEL_29;
  }
  if ( CompareStringW(0x409u, 1u, v20, -1, L"DSA", -1) != 2 )
  {
    if ( CompareStringW(0x409u, 1u, v20, -1, L"CryptOIDInfoECCParameters", -1) == 2
      || CompareStringW(0x409u, 1u, (PCNZWCH)v14[1].pszOID, -1, L"CryptOIDInfoECCParameters", -1) == 2 )
    {
      if ( CompareStringW(0x409u, 1u, v20, -1, L"ECDSA", -1) != 2
        && CompareStringW(0x409u, 1u, v20, -1, L"ECDH", -1) != 2 )
      {
        if ( (unsigned int)I_EncodeCNGECCPublicKeyAndParameters(
                             v14,
                             a1,
                             &v36,
                             a2,
                             (unsigned __int8 **)&hMem,
                             &v37,
                             (unsigned __int8 **)&v33,
                             &Size) )
          goto LABEL_47;
        goto LABEL_51;
      }
      if ( (v7 & 0x20000000) != 0 )
      {
        v26 = v14;
LABEL_45:
        v25 = I_EncodeCNGECCPublicKeyAndParameters(
                v26,
                a1,
                &v36,
                a2,
                (unsigned __int8 **)&hMem,
                &v37,
                (unsigned __int8 **)&v33,
                &Size);
LABEL_46:
        if ( v25 )
        {
LABEL_47:
          pszOID = v36;
          goto LABEL_48;
        }
LABEL_51:
        LastError = GetLastError();
        v28 = 0;
        goto LABEL_52;
      }
      if ( (v7 & 0x10000000) != 0 )
      {
LABEL_44:
        v26 = 0;
        goto LABEL_45;
      }
    }
    else if ( v14->dwValue == -3 )
    {
      v23 = a4 & 0xC000000;
      if ( !v23 || (v24 = CryptFindOIDInfo(v23 | 5u, *(void **)&v14[1].cbSize, 3u), LODWORD(v14) = (_DWORD)v24, v24) )
      {
        v25 = I_ExportCNGPQDSAPublicKey((_DWORD)v14, (_DWORD)a1, (unsigned int)&v36, v22, (__int64)&hMem, (__int64)&v37);
        goto LABEL_46;
      }
    }
LABEL_49:
    v12 = 50;
    goto LABEL_50;
  }
  v21 = I_EncodeCNGDSSPublicKeyAndParameters(a1, a2, (unsigned __int8 **)&hMem, &v37, (unsigned __int8 **)&v33, &Size);
LABEL_29:
  if ( !v21 )
    goto LABEL_51;
LABEL_48:
  LastError = 0;
  LODWORD(ppvFuncAddr) = Size;
  v28 = I_CertEncodePublicKeyInfo(pszOID, (size_t)ppvFuncAddr, (__int64)a6, (__int64)a7);
LABEL_52:
  if ( hMem )
    PkiDefaultCryptFree(hMem);
  if ( v33 )
    PkiDefaultCryptFree(v33);
  if ( LastError )
    SetLastError(LastError);
  return v28;
}

```

## disassembly

```asm
0x180070274  mov     [rsp-38h+arg_0], rbx
0x180070279  mov     [rsp-38h+arg_10], r8
0x18007027e  push    rbp
0x18007027f  push    rsi
0x180070280  push    rdi
0x180070281  push    r12
0x180070283  push    r13
0x180070285  push    r14
0x180070287  push    r15
0x180070289  mov     rbp, rsp
0x18007028c  sub     rsp, 70h
0x180070290  mov     eax, 30000000h
0x180070295  mov     [rbp+hMem], 0
0x18007029d  mov     r14d, r9d
0x1800702a0  mov     [rbp+arg_18], 0
0x1800702a7  and     r14d, eax
0x1800702aa  mov     [rbp+var_20], 0
0x1800702b2  mov     dword ptr [rbp+Size], 0
0x1800702b9  mov     r15d, r9d
0x1800702bc  mov     rbx, r8
0x1800702bf  mov     r12d, edx
0x1800702c2  mov     rsi, rcx
0x1800702c5  cmp     r14d, eax
0x1800702c8  jnz     short loc_1800702D4
0x1800702ca  mov     ecx, 80070057h; struct _CNG_NCRYPT_OR_BCRYPT_KEY *
0x1800702cf  jmp     loc_1800706F6
0x1800702d4  test    r14d, r14d
0x1800702d7  cmovz   r14d, eax
0x1800702db  test    rbx, rbx
0x1800702de  jnz     short loc_180070317
0x1800702e0  call    ?I_CryptGetOIDInfoFromCNGKey@@YAPEBU_CRYPT_OID_INFO@@PEAU_CNG_NCRYPT_OR_BCRYPT_KEY@@@Z; I_CryptGetOIDInfoFromCNGKey(_CNG_NCRYPT_OR_BCRYPT_KEY *)
0x1800702e5  mov     rdi, rax
0x1800702e8  test    rax, rax
0x1800702eb  jnz     short loc_18007030D
0x1800702ed  mov     rcx, rsi; struct _CNG_NCRYPT_OR_BCRYPT_KEY *
0x1800702f0  call    ?IsGenericECCAlgorithm@@YAHPEAU_CNG_NCRYPT_OR_BCRYPT_KEY@@@Z; IsGenericECCAlgorithm(_CNG_NCRYPT_OR_BCRYPT_KEY *)
0x1800702f5  test    eax, eax
0x1800702f7  jz      loc_1800706FC
0x1800702fd  bt      r14d, 1Ch
0x180070302  jb      loc_180070681
0x180070308  jmp     loc_1800706FC
0x18007030d  mov     rbx, [rax+8]
0x180070311  mov     [rbp+arg_10], rbx
0x180070315  jmp     short loc_180070355
0x180070317  mov     ecx, r15d
0x18007031a  mov     r8d, 40000003h; dwGroupId
0x180070320  and     ecx, 0C0000001h
0x180070326  mov     rdx, rbx; pvKey
0x180070329  or      ecx, 1; dwKeyType
0x18007032c  call    CryptFindOIDInfo
0x180070331  mov     rdi, rax
0x180070334  test    rax, rax
0x180070337  jz      loc_1800706F1
0x18007033d  mov     rcx, [rax+30h]
0x180070341  test    rcx, rcx
0x180070344  jz      loc_1800706F1
0x18007034a  xor     eax, eax
0x18007034c  cmp     ax, [rcx]
0x18007034f  jz      loc_1800706F1
0x180070355  xor     r9d, r9d; dwFlags
0x180070358  mov     [rbp+var_18], 0
0x180070360  mov     r8, rbx; pszOID
0x180070363  mov     [rbp+hFuncAddr], 0
0x18007036b  mov     edx, r12d; dwEncodingType
0x18007036e  cmp     [rsi], r9d
0x180070371  jz      loc_180070401
0x180070377  mov     rcx, cs:qword_18015CCC0; hFuncSet
0x18007037e  lea     rax, [rbp+hFuncAddr]
0x180070382  mov     [rsp+70h+phFuncAddr], rax; phFuncAddr
0x180070387  lea     rax, [rbp+var_18]
0x18007038b  mov     [rsp+70h+ppvFuncAddr], rax; ppvFuncAddr
0x180070390  call    CryptGetOIDFunctionAddress
0x180070395  test    eax, eax
0x180070397  jz      loc_180070480
0x18007039d  mov     rax, [rbp+arg_30]
0x1800703a1  mov     r9d, r15d
0x1800703a4  mov     [rsp+70h+var_40], rax
0x1800703a9  mov     r8, rbx
0x1800703ac  mov     edx, r12d
0x1800703af  mov     ecx, [rax]
0x1800703b1  mov     rax, [rbp+arg_28]
0x1800703b5  mov     dword ptr [rbp+Size+4], ecx
0x1800703b8  mov     rcx, [rbp+arg_20]
0x1800703bc  mov     [rsp+70h+phFuncAddr], rax
0x1800703c1  mov     rax, [rbp+var_18]
0x1800703c5  mov     [rsp+70h+ppvFuncAddr], rcx
0x1800703ca  mov     rcx, [rsi+8]
0x1800703ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800703d3  mov     rcx, [rbp+hFuncAddr]; hFuncAddr
0x1800703d7  xor     edx, edx; dwFlags
0x1800703d9  mov     r13d, eax
0x1800703dc  call    CryptFreeOIDFunctionAddress
0x1800703e1  test    r13d, r13d
0x1800703e4  jnz     short loc_1800703F9
0x1800703e6  call    cs:__imp_GetLastError
0x1800703ec  cmp     eax, 32h ; '2'
0x1800703ef  jnz     short loc_1800703F9
0x1800703f1  mov     ecx, dword ptr [rbp+Size+4]
0x1800703f4  jmp     loc_18007047A
0x1800703f9  mov     eax, r13d
0x1800703fc  jmp     loc_180070730
0x180070401  mov     rcx, cs:qword_18015CCC8; hFuncSet
0x180070408  lea     rax, [rbp+var_18]
0x18007040c  mov     [rsp+70h+phFuncAddr], rax; phFuncAddr
0x180070411  lea     rax, [rbp+hFuncAddr]
0x180070415  mov     [rsp+70h+ppvFuncAddr], rax; ppvFuncAddr
0x18007041a  call    CryptGetOIDFunctionAddress
0x18007041f  test    eax, eax
0x180070421  jz      short loc_180070480
0x180070423  mov     rax, [rbp+arg_30]
0x180070427  mov     r9d, r15d
0x18007042a  mov     [rsp+70h+var_40], rax
0x18007042f  mov     r8, rbx
0x180070432  mov     edx, r12d
0x180070435  mov     ecx, [rax]
0x180070437  mov     rax, [rbp+arg_28]
0x18007043b  mov     dword ptr [rbp+Size+4], ecx
0x18007043e  mov     rcx, [rbp+arg_20]
0x180070442  mov     [rsp+70h+phFuncAddr], rax
0x180070447  mov     rax, [rbp+hFuncAddr]
0x18007044b  mov     [rsp+70h+ppvFuncAddr], rcx
0x180070450  mov     rcx, [rsi+8]
0x180070454  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070459  mov     rcx, [rbp+var_18]; hFuncAddr
0x18007045d  xor     edx, edx; dwFlags
0x18007045f  mov     r13d, eax
0x180070462  call    CryptFreeOIDFunctionAddress
0x180070467  test    r13d, r13d
0x18007046a  jnz     short loc_1800703F9
0x18007046c  call    cs:__imp_GetLastError
0x180070472  cmp     eax, 32h ; '2'
0x180070475  jnz     short loc_1800703F9
0x180070477  mov     ecx, dword ptr [rbp+Size+4]
0x18007047a  mov     rax, [rbp+arg_30]
0x18007047e  mov     [rax], ecx
0x180070480  mov     r13, [rdi+30h]
0x180070484  lea     rax, aRsa; "RSA"
0x18007048b  or      ecx, 0FFFFFFFFh
0x18007048e  mov     r8, r13; lpString1
0x180070491  mov     dword ptr [rsp+70h+phFuncAddr], ecx; cchCount2
0x180070495  mov     r9d, ecx; cchCount1
0x180070498  mov     [rsp+70h+ppvFuncAddr], rax; lpString2
0x18007049d  lea     edx, [rcx+2]; dwCmpFlags
0x1800704a0  mov     ecx, 409h; Locale
0x1800704a5  call    cs:__imp_CompareStringW
0x1800704ab  cmp     eax, 2
0x1800704ae  jnz     short loc_1800704C5
0x1800704b0  lea     r9, [rbp+arg_18]
0x1800704b4  mov     edx, r12d
0x1800704b7  lea     r8, [rbp+hMem]
0x1800704bb  mov     rcx, rsi
0x1800704be  call    EncodeCNGRSAPublicKey
0x1800704c3  jmp     short loc_180070516
0x1800704c5  or      r9d, 0FFFFFFFFh; cchCount1
0x1800704c9  lea     rax, aDsa; "DSA"
0x1800704d0  mov     dword ptr [rsp+70h+phFuncAddr], r9d; cchCount2
0x1800704d5  mov     r8, r13; lpString1
0x1800704d8  mov     ecx, 409h; Locale
0x1800704dd  mov     [rsp+70h+ppvFuncAddr], rax; lpString2
0x1800704e2  lea     edx, [r9+2]; dwCmpFlags
0x1800704e6  call    cs:__imp_CompareStringW
0x1800704ec  cmp     eax, 2
0x1800704ef  jnz     short loc_180070523
0x1800704f1  lea     rax, [rbp+Size]
0x1800704f5  mov     edx, r12d; unsigned int
0x1800704f8  mov     [rsp+70h+phFuncAddr], rax; unsigned int *
0x1800704fd  lea     r9, [rbp+arg_18]; unsigned int *
0x180070501  lea     rax, [rbp+var_20]
0x180070505  mov     rcx, rsi; struct _CNG_NCRYPT_OR_BCRYPT_KEY *
0x180070508  lea     r8, [rbp+hMem]; unsigned __int8 **
0x18007050c  mov     [rsp+70h+ppvFuncAddr], rax; unsigned __int8 **
0x180070511  call    ?I_EncodeCNGDSSPublicKeyAndParameters@@YAHPEAU_CNG_NCRYPT_OR_BCRYPT_KEY@@KPEAPEAEPEAK12@Z; I_EncodeCNGDSSPublicKeyAndParameters(_CNG_NCRYPT_OR_BCRYPT_KEY *,ulong,uchar * *,ulong *,uchar * *,ulong *)
0x180070516  test    eax, eax
0x180070518  jnz     loc_1800706BE
0x18007051e  jmp     loc_1800706FC
0x180070523  or      ebx, 0FFFFFFFFh
0x180070526  lea     rax, String2; "CryptOIDInfoECCParameters"
0x18007052d  mov     dword ptr [rsp+70h+phFuncAddr], ebx; cchCount2
0x180070531  mov     r9d, ebx; cchCount1
0x180070534  mov     r8, r13; lpString1
0x180070537  mov     [rsp+70h+ppvFuncAddr], rax; lpString2
0x18007053c  mov     ecx, 409h; Locale
0x180070541  lea     edx, [rbx+2]; dwCmpFlags
0x180070544  call    cs:__imp_CompareStringW
0x18007054a  cmp     eax, 2
0x18007054d  jz      loc_1800705D6
0x180070553  mov     r8, [rdi+38h]; lpString1
0x180070557  lea     rax, String2; "CryptOIDInfoECCParameters"
0x18007055e  mov     dword ptr [rsp+70h+phFuncAddr], ebx; cchCount2
0x180070562  lea     edx, [rbx+2]; dwCmpFlags
0x180070565  mov     r9d, ebx; cchCount1
0x180070568  mov     [rsp+70h+ppvFuncAddr], rax; lpString2
0x18007056d  mov     ecx, 409h; Locale
0x180070572  call    cs:__imp_CompareStringW
0x180070578  cmp     eax, 2
0x18007057b  jz      short loc_1800705D6
0x18007057d  cmp     dword ptr [rdi+1Ch], 0FFFFFFFDh
0x180070581  jnz     loc_1800706F1
0x180070587  and     r15d, 0C000000h
0x18007058e  jz      short loc_1800705B0
0x180070590  mov     rdx, [rdi+30h]; pvKey
0x180070594  lea     r8d, [rbx+4]; dwGroupId
0x180070598  or      r15d, 5
0x18007059c  mov     ecx, r15d; dwKeyType
0x18007059f  call    CryptFindOIDInfo
0x1800705a4  mov     rdi, rax
0x1800705a7  test    rax, rax
0x1800705aa  jz      loc_1800706F1
0x1800705b0  lea     rax, [rbp+arg_18]
0x1800705b4  mov     rdx, rsi
0x1800705b7  mov     [rsp+70h+phFuncAddr], rax
0x1800705bc  lea     r8, [rbp+arg_10]
0x1800705c0  lea     rax, [rbp+hMem]
0x1800705c4  mov     rcx, rdi
0x1800705c7  mov     [rsp+70h+ppvFuncAddr], rax
0x1800705cc  call    I_ExportCNGPQDSAPublicKey
0x1800705d1  jmp     loc_1800706B6
0x1800705d6  lea     rax, aEcdsa; "ECDSA"
0x1800705dd  mov     dword ptr [rsp+70h+phFuncAddr], ebx; cchCount2
0x1800705e1  mov     r15d, 409h
0x1800705e7  mov     [rsp+70h+ppvFuncAddr], rax; lpString2
0x1800705ec  mov     ecx, r15d; Locale
0x1800705ef  mov     r9d, ebx; cchCount1
0x1800705f2  mov     r8, r13; lpString1
0x1800705f5  mov     edx, 1; dwCmpFlags
0x1800705fa  call    cs:__imp_CompareStringW
0x180070600  cmp     eax, 2
0x180070603  jz      short loc_18007066E
0x180070605  lea     rax, aEcdh; "ECDH"
0x18007060c  mov     dword ptr [rsp+70h+phFuncAddr], ebx; cchCount2
0x180070610  mov     r9d, ebx; cchCount1
0x180070613  mov     [rsp+70h+ppvFuncAddr], rax; lpString2
0x180070618  mov     r8, r13; lpString1
0x18007061b  mov     edx, 1; dwCmpFlags
0x180070620  mov     ecx, r15d; Locale
0x180070623  call    cs:__imp_CompareStringW
0x180070629  cmp     eax, 2
0x18007062c  jz      short loc_18007066E
0x18007062e  lea     rax, [rbp+Size]
0x180070632  mov     r9d, r12d; unsigned int
0x180070635  mov     [rsp+70h+var_38], rax; unsigned int *
0x18007063a  lea     r8, [rbp+arg_10]; char **
0x18007063e  lea     rax, [rbp+var_20]
0x180070642  mov     rdx, rsi; struct _CNG_NCRYPT_OR_BCRYPT_KEY *
0x180070645  mov     [rsp+70h+var_40], rax; unsigned __int8 **
0x18007064a  mov     rcx, rdi; struct _CRYPT_OID_INFO *
0x18007064d  lea     rax, [rbp+arg_18]
0x180070651  mov     [rsp+70h+phFuncAddr], rax; unsigned int *
0x180070656  lea     rax, [rbp+hMem]
0x18007065a  mov     [rsp+70h+ppvFuncAddr], rax; unsigned __int8 **
0x18007065f  call    ?I_EncodeCNGECCPublicKeyAndParameters@@YAHPEBU_CRYPT_OID_INFO@@PEAU_CNG_NCRYPT_OR_BCRYPT_KEY@@PEAPEADKPEAPEAEPEAK34@Z; I_EncodeCNGECCPublicKeyAndParameters(_CRYPT_OID_INFO const *,_CNG_NCRYPT_OR_BCRYPT_KEY *,char * *,ulong,uchar * *,ulong *,uchar * *,ulong *)
0x180070664  test    eax, eax
0x180070666  jz      loc_1800706FC
0x18007066c  jmp     short loc_1800706BA
0x18007066e  bt      r14d, 1Dh
0x180070673  jnb     short loc_18007067A
0x180070675  mov     rcx, rdi
0x180070678  jmp     short loc_180070683
0x18007067a  bt      r14d, 1Ch
0x18007067f  jnb     short loc_1800706F1
0x180070681  xor     ecx, ecx; struct _CRYPT_OID_INFO *
0x180070683  lea     rax, [rbp+Size]
0x180070687  mov     r9d, r12d; unsigned int
0x18007068a  mov     [rsp+70h+var_38], rax; unsigned int *
0x18007068f  lea     r8, [rbp+arg_10]; char **
0x180070693  lea     rax, [rbp+var_20]
0x180070697  mov     rdx, rsi; struct _CNG_NCRYPT_OR_BCRYPT_KEY *
0x18007069a  mov     [rsp+70h+var_40], rax; unsigned __int8 **
0x18007069f  lea     rax, [rbp+arg_18]
0x1800706a3  mov     [rsp+70h+phFuncAddr], rax; unsigned int *
0x1800706a8  lea     rax, [rbp+hMem]
0x1800706ac  mov     [rsp+70h+ppvFuncAddr], rax; unsigned __int8 **
0x1800706b1  call    ?I_EncodeCNGECCPublicKeyAndParameters@@YAHPEBU_CRYPT_OID_INFO@@PEAU_CNG_NCRYPT_OR_BCRYPT_KEY@@PEAPEADKPEAPEAEPEAK34@Z; I_EncodeCNGECCPublicKeyAndParameters(_CRYPT_OID_INFO const *,_CNG_NCRYPT_OR_BCRYPT_KEY *,char * *,ulong,uchar * *,ulong *,uchar * *,ulong *)
0x1800706b6  test    eax, eax
0x1800706b8  jz      short loc_1800706FC
0x1800706ba  mov     rbx, [rbp+arg_10]
0x1800706be  mov     rax, [rbp+arg_30]
0x1800706c2  xor     edi, edi
0x1800706c4  mov     r9, [rbp+var_20]
0x1800706c8  mov     rcx, rbx; Src
0x1800706cb  mov     r8d, [rbp+arg_18]
0x1800706cf  mov     rdx, [rbp+hMem]
0x1800706d3  mov     [rsp+70h+var_40], rax; __int64
0x1800706d8  mov     rax, [rbp+arg_28]
0x1800706dc  mov     [rsp+70h+phFuncAddr], rax; __int64
0x1800706e1  mov     eax, dword ptr [rbp+Size]
0x1800706e4  mov     dword ptr [rsp+70h+ppvFuncAddr], eax; Size
0x1800706e8  call    I_CertEncodePublicKeyInfo
0x1800706ed  mov     ebx, eax
0x1800706ef  jmp     short loc_180070706
0x1800706f1  mov     ecx, 32h ; '2'; dwErrCode
0x1800706f6  call    cs:__imp_SetLastError
0x1800706fc  call    cs:__imp_GetLastError
0x180070702  mov     edi, eax
0x180070704  xor     ebx, ebx
0x180070706  mov     rcx, [rbp+hMem]; hMem
0x18007070a  test    rcx, rcx
0x18007070d  jz      short loc_180070714
0x18007070f  call    PkiDefaultCryptFree
0x180070714  mov     rcx, [rbp+var_20]; hMem
  ... truncated ...
```
