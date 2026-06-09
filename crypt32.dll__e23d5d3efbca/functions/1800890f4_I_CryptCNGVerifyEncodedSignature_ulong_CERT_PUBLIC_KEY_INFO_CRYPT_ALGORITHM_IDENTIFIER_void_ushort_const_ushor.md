# I_CryptCNGVerifyEncodedSignature(ulong,_CERT_PUBLIC_KEY_INFO *,_CRYPT_ALGORITHM_IDENTIFIER *,void *,ushort const *,ushort const *,uchar *,ulong,uchar *,ulong)

- ea: `0x1800890f4`
- end: `0x180089294`
- name: `?I_CryptCNGVerifyEncodedSignature@@YAHKPEAU_CERT_PUBLIC_KEY_INFO@@PEAU_CRYPT_ALGORITHM_IDENTIFIER@@PEAXPEBG3PEAEK4K@Z`
- size: `416`
- prototype: `__int64 __fastcall(DWORD dwEncodingType, PCERT_PUBLIC_KEY_INFO pInfo, struct _CRYPT_ALGORITHM_IDENTIFIER *, void *, WCHAR *lpString1, PCNZWCH, PUCHAR pbHash, ULONG cbHash, PUCHAR pbEncoded, ULONG cbEncoded)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18002e880`
- `0x18002fe64`

## callees

- `0x180009da0`
- `0x180026220`
- `0x1800286e0`
- `0x1800890f4`
- `0x180089450`
- `0x18008991c`
- `0x18009d820`
- `0x1800e2364`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089196`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011bb3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089196`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011bb3a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180089289`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18011bc09`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180089289`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18011bc09`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800891ec`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008924d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18011bbab`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800891ec`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008924d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18011bbab`
- `bcrypt!BCryptDestroyKey` at `0x18008927c`
- `bcrypt!BCryptDestroyKey` at `0x18008927c`

## pseudocode

```c
__int64 __fastcall I_CryptCNGVerifyEncodedSignature(
        DWORD dwEncodingType,
        PCERT_PUBLIC_KEY_INFO pInfo,
        struct _CRYPT_ALGORITHM_IDENTIFIER *a3,
        void *a4,
        WCHAR *lpString1,
        PCNZWCH a6,
        PUCHAR pbHash,
        ULONG cbHash,
        PUCHAR pbEncoded,
        ULONG cbEncoded)
{
  const CHAR *pszObjId; // r8
  BOOL OIDFunctionAddress; // eax
  ULONG v15; // r14d
  UCHAR *v16; // r15
  ULONG v17; // r12d
  UCHAR *v18; // r13
  struct _CERT_PUBLIC_KEY_INFO *v19; // rdx
  unsigned int v20; // edi
  DWORD LastError; // ebx
  WCHAR *v23; // rbx
  int v24; // eax
  unsigned int v25; // ebx
  PCCRYPT_OID_INFO OIDInfo; // rax
  PCCRYPT_OID_INFO v27; // rbx
  PCCRYPT_OID_INFO v28; // rax
  LPSTR v29; // rax
  int v30; // edx
  int v31; // ecx
  DWORD v32; // ecx
  void *ppvFuncAddr; // [rsp+60h] [rbp-18h] BYREF
  HCRYPTOIDFUNCADDR hFuncAddr; // [rsp+68h] [rbp-10h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+D0h] [rbp+58h] BYREF
  void *v38; // [rsp+D8h] [rbp+60h]

  v38 = a4;
  phKey = 0;
  pszObjId = a3->pszObjId;
  ppvFuncAddr = 0;
  hFuncAddr = 0;
  OIDFunctionAddress = CryptGetOIDFunctionAddress(
                         qword_18015CDD0,
                         dwEncodingType,
                         pszObjId,
                         0,
                         &ppvFuncAddr,
                         &hFuncAddr);
  v15 = cbEncoded;
  v16 = pbEncoded;
  v17 = cbHash;
  v18 = pbHash;
  if ( OIDFunctionAddress )
  {
    v25 = ((__int64 (__fastcall *)(_QWORD, PCERT_PUBLIC_KEY_INFO, struct _CRYPT_ALGORITHM_IDENTIFIER *, void *, WCHAR *, PCNZWCH, PUCHAR, ULONG, PUCHAR, ULONG))ppvFuncAddr)(
            dwEncodingType,
            pInfo,
            a3,
            v38,
            lpString1,
            a6,
            pbHash,
            cbHash,
            pbEncoded,
            cbEncoded);
    CryptFreeOIDFunctionAddress(hFuncAddr, 0);
    if ( v25 || GetLastError() != 50 )
      return v25;
  }
  v19 = pInfo;
  v20 = 1;
  if ( !CryptImportPublicKeyInfoEx2(1u, v19, 0x80000000, 0, &phKey) )
    goto LABEL_3;
  v23 = lpString1;
  if ( CompareStringW(0x409u, 1u, lpString1, -1, L"RSA", -1) == 2 )
  {
    v24 = CNGRSAVerifyEncodedSignature(phKey, a3->pszObjId, v18, v17, v16, v15);
    goto LABEL_11;
  }
  if ( CompareStringW(0x409u, 1u, v23, -1, L"CryptOIDInfoECCParameters", -1) == 2 )
  {
    v24 = CNGECCVerifyEncodedSignature(phKey, dwEncodingType, v17, v16, v15);
    goto LABEL_11;
  }
  OIDInfo = CryptFindOIDInfo(5u, v23, 3u);
  v27 = OIDInfo;
  if ( !OIDInfo
    || OIDInfo->dwValue != -3
    || (v28 = CryptFindOIDInfo(1u, a3->pszObjId, 0x40000004u)) == 0
    || CompareStringW(0x409u, 1u, *(PCNZWCH *)&v27[1].cbSize, -1, (PCNZWCH)v28[1].pszOID, -1) != 2 )
  {
    v32 = 50;
    goto LABEL_29;
  }
  v29 = pInfo->Algorithm.pszObjId;
  do
  {
    v30 = (unsigned __int8)v29[(unsigned __int64)(a3->pszObjId - pInfo->Algorithm.pszObjId)];
    v31 = (unsigned __int8)*v29 - v30;
    if ( v31 )
      break;
    ++v29;
  }
  while ( v30 );
  if ( v31 )
  {
    v32 = -2146893818;
LABEL_29:
    SetLastError(v32);
    goto LABEL_3;
  }
  v24 = CNGPQVerifyEncodedSignature(phKey, a6, v18, v17, v16, v15);
LABEL_11:
  if ( v24 )
  {
    LastError = 0;
    goto LABEL_4;
  }
LABEL_3:
  LastError = GetLastError();
  v20 = 0;
LABEL_4:
  if ( phKey )
    BCryptDestroyKey(phKey);
  if ( LastError )
    SetLastError(LastError);
  return v20;
}

```

## disassembly

```asm
0x1800890f4  mov     [rsp-40h+arg_18], r9
0x1800890f9  mov     [rsp-40h+arg_8], rdx
0x1800890fe  mov     [rsp-40h+dwCertEncodingType], ecx
0x180089102  push    rbp
0x180089103  push    rbx
0x180089104  push    rsi
0x180089105  push    rdi
0x180089106  push    r12
0x180089108  push    r13
0x18008910a  push    r14
0x18008910c  push    r15
0x18008910e  mov     rbp, rsp
0x180089111  sub     rsp, 78h
0x180089115  xor     eax, eax
0x180089117  mov     rdi, rdx
0x18008911a  mov     [rbp+phKey], rax
0x18008911e  mov     rsi, r8
0x180089121  mov     r8, [r8]; pszOID
0x180089124  mov     ebx, ecx
0x180089126  mov     [rbp+var_18], rax
0x18008912a  mov     edx, ecx; dwEncodingType
0x18008912c  mov     rcx, cs:qword_18015CDD0; hFuncSet
0x180089133  xor     r9d, r9d; dwFlags
0x180089136  mov     [rbp+hFuncAddr], rax
0x18008913a  lea     rax, [rbp+hFuncAddr]
0x18008913e  mov     [rsp+78h+phFuncAddr], rax; phFuncAddr
0x180089143  lea     rax, [rbp+var_18]
0x180089147  mov     [rsp+78h+ppvFuncAddr], rax; ppvFuncAddr
0x18008914c  call    CryptGetOIDFunctionAddress
0x180089151  mov     r14d, [rbp+cbEncoded]
0x180089158  mov     r15, [rbp+pbEncoded]
0x18008915f  mov     r12d, [rbp+cbHash]
0x180089166  mov     r13, [rbp+pbHash]
0x18008916a  test    eax, eax
0x18008916c  jnz     loc_18011BAEE
0x180089172  xor     r9d, r9d; pvAuxInfo
0x180089175  lea     rax, [rbp+phKey]
0x180089179  mov     rdx, rdi; pInfo
0x18008917c  mov     [rsp+78h+ppvFuncAddr], rax; phKey
0x180089181  mov     r8d, 80000000h; dwFlags
0x180089187  lea     edi, [r9+1]
0x18008918b  mov     ecx, edi; dwCertEncodingType
0x18008918d  call    CryptImportPublicKeyInfoEx2
0x180089192  test    eax, eax
0x180089194  jnz     short loc_1800891C8
0x180089196  call    cs:__imp_GetLastError
0x18008919c  mov     ebx, eax
0x18008919e  xor     edi, edi
0x1800891a0  mov     rcx, [rbp+phKey]; hKey
0x1800891a4  test    rcx, rcx
0x1800891a7  jnz     loc_18008927C
0x1800891ad  test    ebx, ebx
0x1800891af  jnz     loc_180089287
0x1800891b5  mov     eax, edi
0x1800891b7  add     rsp, 78h
0x1800891bb  pop     r15
0x1800891bd  pop     r14
0x1800891bf  pop     r13
0x1800891c1  pop     r12
0x1800891c3  pop     rdi
0x1800891c4  pop     rsi
0x1800891c5  pop     rbx
0x1800891c6  pop     rbp
0x1800891c7  retn
0x1800891c8  mov     rbx, [rbp+lpString1]
0x1800891cc  lea     rax, aRsa; "RSA"
0x1800891d3  or      ecx, 0FFFFFFFFh
0x1800891d6  mov     r8, rbx; lpString1
0x1800891d9  mov     dword ptr [rsp+78h+phFuncAddr], ecx; cchCount2
0x1800891dd  mov     r9d, ecx; cchCount1
0x1800891e0  mov     ecx, 409h; Locale
0x1800891e5  mov     [rsp+78h+ppvFuncAddr], rax; lpString2
0x1800891ea  mov     edx, edi; dwCmpFlags
0x1800891ec  call    cs:__imp_CompareStringW
0x1800891f2  cmp     eax, 2
0x1800891f5  jnz     short loc_18008922E
0x1800891f7  mov     r9, [rbp+arg_28]
0x1800891fb  mov     r8, [rbp+arg_18]
0x1800891ff  mov     rdx, [rsi]; Str1
0x180089202  mov     rcx, [rbp+phKey]; hKey
0x180089206  mov     [rsp+78h+var_40], r14d; ULONG
0x18008920b  mov     [rsp+78h+var_48], r15; PUCHAR
0x180089210  mov     dword ptr [rsp+78h+phFuncAddr], r12d; cbHash
0x180089215  mov     [rsp+78h+ppvFuncAddr], r13; pbHash
0x18008921a  call    CNGRSAVerifyEncodedSignature
0x18008921f  test    eax, eax
0x180089221  jz      loc_180089196
0x180089227  xor     ebx, ebx
0x180089229  jmp     loc_1800891A0
0x18008922e  or      r9d, 0FFFFFFFFh; cchCount1
0x180089232  lea     rax, String2; "CryptOIDInfoECCParameters"
0x180089239  mov     dword ptr [rsp+78h+phFuncAddr], r9d; cchCount2
0x18008923e  mov     r8, rbx; lpString1
0x180089241  mov     edx, edi; dwCmpFlags
0x180089243  mov     [rsp+78h+ppvFuncAddr], rax; lpString2
0x180089248  mov     ecx, 409h; Locale
0x18008924d  call    cs:__imp_CompareStringW
0x180089253  cmp     eax, 2
0x180089256  jnz     loc_18011BB50
0x18008925c  mov     edx, [rbp+dwCertEncodingType]; dwCertEncodingType
0x18008925f  mov     r9, r13
0x180089262  mov     rcx, [rbp+phKey]; hKey
0x180089266  mov     dword ptr [rsp+78h+var_48], r14d; cbEncoded
0x18008926b  mov     [rsp+78h+phFuncAddr], r15; pbEncoded
0x180089270  mov     dword ptr [rsp+78h+ppvFuncAddr], r12d; cbHash
0x180089275  call    CNGECCVerifyEncodedSignature
0x18008927a  jmp     short loc_18008921F
0x18008927c  call    cs:__imp_BCryptDestroyKey
0x180089282  jmp     loc_1800891AD
0x180089287  mov     ecx, ebx; dwErrCode
0x180089289  call    cs:__imp_SetLastError
0x18008928f  jmp     loc_1800891B5
0x18011baee  mov     rax, [rbp+arg_28]
0x18011baf2  mov     r8, rsi
0x18011baf5  mov     r9, [rbp+arg_18]
0x18011baf9  mov     rdx, rdi
0x18011bafc  mov     [rsp+78h+var_30], r14d
0x18011bb01  mov     ecx, ebx
0x18011bb03  mov     [rsp+78h+var_38], r15
0x18011bb08  mov     [rsp+78h+var_40], r12d
0x18011bb0d  mov     [rsp+78h+var_48], r13
0x18011bb12  mov     [rsp+78h+phFuncAddr], rax
0x18011bb17  mov     rax, [rbp+lpString1]
0x18011bb1b  mov     [rsp+78h+ppvFuncAddr], rax
0x18011bb20  mov     rax, [rbp+var_18]
0x18011bb24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011bb29  mov     rcx, [rbp+hFuncAddr]; hFuncAddr
0x18011bb2d  xor     edx, edx; dwFlags
0x18011bb2f  mov     ebx, eax
0x18011bb31  call    CryptFreeOIDFunctionAddress
0x18011bb36  test    ebx, ebx
0x18011bb38  jnz     short loc_18011BB49
0x18011bb3a  call    cs:__imp_GetLastError
0x18011bb40  cmp     eax, 32h ; '2'
0x18011bb43  jz      loc_180089172
0x18011bb49  mov     eax, ebx
0x18011bb4b  jmp     loc_1800891B7
0x18011bb50  mov     r8d, 3; dwGroupId
0x18011bb56  mov     rdx, rbx; pvKey
0x18011bb59  lea     ecx, [r8+2]; dwKeyType
0x18011bb5d  call    CryptFindOIDInfo
0x18011bb62  mov     rbx, rax
0x18011bb65  test    rax, rax
0x18011bb68  jz      loc_18011BC04
0x18011bb6e  cmp     dword ptr [rax+1Ch], 0FFFFFFFDh
0x18011bb72  jnz     loc_18011BC04
0x18011bb78  mov     rdx, [rsi]; pvKey
0x18011bb7b  mov     r8d, 40000004h; dwGroupId
0x18011bb81  mov     ecx, edi; dwKeyType
0x18011bb83  call    CryptFindOIDInfo
0x18011bb88  test    rax, rax
0x18011bb8b  jz      short loc_18011BC04
0x18011bb8d  mov     rax, [rax+38h]
0x18011bb91  or      ecx, 0FFFFFFFFh
0x18011bb94  mov     r8, [rbx+30h]; lpString1
0x18011bb98  mov     r9d, ecx; cchCount1
0x18011bb9b  mov     dword ptr [rsp+78h+phFuncAddr], ecx; cchCount2
0x18011bb9f  mov     edx, edi; dwCmpFlags
0x18011bba1  mov     ecx, 409h; Locale
0x18011bba6  mov     [rsp+78h+ppvFuncAddr], rax; lpString2
0x18011bbab  call    cs:__imp_CompareStringW
0x18011bbb1  cmp     eax, 2
0x18011bbb4  jnz     short loc_18011BC04
0x18011bbb6  mov     rax, [rbp+arg_8]
0x18011bbba  mov     r8, [rsi]
0x18011bbbd  mov     rax, [rax]
0x18011bbc0  sub     r8, rax
0x18011bbc3  movzx   ecx, byte ptr [rax]
0x18011bbc6  movzx   edx, byte ptr [rax+r8]
0x18011bbcb  sub     ecx, edx
0x18011bbcd  jnz     short loc_18011BBD6
0x18011bbcf  add     rax, rdi
0x18011bbd2  test    edx, edx
0x18011bbd4  jnz     short loc_18011BBC3
0x18011bbd6  test    ecx, ecx
0x18011bbd8  jz      short loc_18011BBE1
0x18011bbda  mov     ecx, 80090006h
0x18011bbdf  jmp     short loc_18011BC09
0x18011bbe1  mov     rdx, [rbp+arg_28]; lpString1
0x18011bbe5  mov     r9d, r12d; cbHash
0x18011bbe8  mov     rcx, [rbp+phKey]; hKey
0x18011bbec  mov     r8, r13; pbHash
0x18011bbef  mov     dword ptr [rsp+78h+phFuncAddr], r14d; cbSignature
0x18011bbf4  mov     [rsp+78h+ppvFuncAddr], r15; pbSignature
0x18011bbf9  call    CNGPQVerifyEncodedSignature
0x18011bbfe  nop
0x18011bbff  jmp     loc_18008921F
0x18011bc04  mov     ecx, 32h ; '2'; dwErrCode
0x18011bc09  call    cs:__imp_SetLastError
0x18011bc0f  nop
0x18011bc10  jmp     loc_180089196
```
