# ScHelperVerifyMessage

- ea: `0x18007e624`
- end: `0x18007e8f1`
- name: `ScHelperVerifyMessage`
- size: `717`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x18007c9e8`
- `0x18007d49c`

## callees

- `0x18000a810`
- `0x18003f9c0`
- `0x180042410`
- `0x18007c7cc`
- `0x18007c884`
- `0x18007d1a8`
- `0x18007e624`
- `0x18007f990`
- `0x180081010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007e6af`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007e6d6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007e6af`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007e6d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e872`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e872`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007e8cc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007e8cc`
- `bcrypt!BCryptDestroyHash` at `0x18007e894`
- `bcrypt!BCryptDestroyHash` at `0x18007e894`
- `bcrypt!BCryptFinishHash` at `0x18007e804`
- `bcrypt!BCryptFinishHash` at `0x18007e804`
- `bcrypt!BCryptCreateHash` at `0x18007e7cc`
- `bcrypt!BCryptCreateHash` at `0x18007e7cc`
- `bcrypt!BCryptDestroyKey` at `0x18007e8c0`
- `bcrypt!BCryptDestroyKey` at `0x18007e8c0`
- `bcrypt!BCryptVerifySignature` at `0x18007e85f`
- `bcrypt!BCryptVerifySignature` at `0x18007e85f`
- `bcrypt!BCryptHashData` at `0x18007e7ea`
- `bcrypt!BCryptHashData` at `0x18007e7ea`
- `CRYPT32!CryptImportPublicKeyInfoEx2` at `0x18007e691`
- `CRYPT32!CryptImportPublicKeyInfoEx2` at `0x18007e691`

## pseudocode

```c
__int64 __fastcall ScHelperVerifyMessage(__int64 a1, __int64 a2, UCHAR *a3, ULONG a4, UCHAR *a5, ULONG cbSignature)
{
  struct _CERT_PUBLIC_KEY_INFO *v7; // rdx
  UCHAR *p_phHash; // rdi
  NTSTATUS ErrorToNtStatus; // ebx
  void *HelperSha1AlgHandle; // rax
  __int64 v12; // rdx
  ULONG v13; // ebx
  ULONG v14; // r15d
  void *v15; // r14
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // rcx
  unsigned __int64 v18; // rcx
  void *v19; // rsp
  void *v20; // rsp
  UCHAR *v21; // rax
  DWORD LastError; // esi
  ULONG dwFlags; // eax
  __int64 *v24; // rdx
  __int64 v26; // [rsp+0h] [rbp-40h] BYREF
  int v27; // [rsp+40h] [rbp+0h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp+8h] BYREF
  BCRYPT_KEY_HANDLE hKey; // [rsp+50h] [rbp+10h] BYREF
  ULONG cbInput; // [rsp+58h] [rbp+18h]
  __int64 v31; // [rsp+60h] [rbp+20h] BYREF
  PUCHAR pbSignature; // [rsp+68h] [rbp+28h]
  UCHAR pbOutput[32]; // [rsp+78h] [rbp+38h] BYREF

  v7 = *(struct _CERT_PUBLIC_KEY_INFO **)(a1 + 24);
  p_phHash = 0;
  pbSignature = a5;
  cbInput = a4;
  hKey = 0;
  phHash = 0;
  v31 = 0;
  v27 = 0;
  if ( !CryptImportPublicKeyInfoEx2(0x10001u, v7 + 2, 0, 0, &hKey) )
  {
    ErrorToNtStatus = -1073741023;
LABEL_32:
    LastError = GetLastError();
    ErrorToNtStatus = LogEventAndTranslateLastErrorToNtStatus(ErrorToNtStatus, 0x1000Fu, LastError);
    goto LABEL_33;
  }
  if ( (unsigned int)_o__wcsicmp(a2, L"SHA256") )
  {
    if ( (unsigned int)_o__wcsicmp(a2, L"SHA1") )
    {
      ErrorToNtStatus = -1073741637;
      goto LABEL_32;
    }
    HelperSha1AlgHandle = I_ScHelperGetHelperSha1AlgHandle();
    v13 = g_cbHashObjectLength;
    v14 = 20;
  }
  else
  {
    HelperSha1AlgHandle = I_ScHelperGetHelperSha256AlgHandle();
    v13 = g_cbSha256HashObjectLength;
    v14 = 32;
  }
  v15 = HelperSha1AlgHandle;
  if ( !HelperSha1AlgHandle )
  {
    ErrorToNtStatus = -1073741670;
    goto LABEL_32;
  }
  if ( !v13 )
    goto LABEL_45;
  if ( v13 > (unsigned __int64)g_ulMaxStackAllocSize )
    goto LABEL_45;
  v16 = v13 + g_ulAdditionalProbeSize + 8;
  if ( v16 < v13 || !(unsigned int)VerifyStackAvailable(v16, v12) )
    goto LABEL_45;
  v17 = v13 + 23LL;
  if ( v17 <= (unsigned __int64)v13 + 8 )
    v17 = 0xFFFFFFFFFFFFFF0LL;
  v18 = v17 & 0xFFFFFFFFFFFFFFF0uLL;
  v19 = alloca(v18);
  v20 = alloca(v18);
  p_phHash = (UCHAR *)&v27;
  if ( &v26 == (__int64 *)-64LL || (v27 = 1801679955, (p_phHash = (UCHAR *)&phHash) == 0) )
  {
LABEL_45:
    if ( (unsigned __int64)v13 + 8 >= v13 )
    {
      v21 = (UCHAR *)((__int64 (*)(void))g_pfnAllocate)();
      p_phHash = v21;
      if ( v21 )
      {
        *(_DWORD *)v21 = 1885431112;
        p_phHash = v21 + 8;
      }
    }
  }
  if ( !p_phHash )
  {
    ErrorToNtStatus = -1073741801;
    goto LABEL_32;
  }
  ErrorToNtStatus = BCryptCreateHash(v15, &phHash, p_phHash, v13, 0, 0, 0);
  if ( ErrorToNtStatus < 0 )
    goto LABEL_32;
  ErrorToNtStatus = BCryptHashData(phHash, a3, cbInput, 0);
  if ( ErrorToNtStatus < 0 )
    goto LABEL_32;
  ErrorToNtStatus = BCryptFinishHash(phHash, pbOutput, v14, 0);
  if ( ErrorToNtStatus < 0 )
    goto LABEL_32;
  ErrorToNtStatus = ScHelperIsNcryptRsaKey(0, hKey, &v27);
  if ( ErrorToNtStatus < 0 )
    goto LABEL_32;
  LastError = 0;
  if ( v27 )
  {
    v31 = a2;
    dwFlags = 2;
    v24 = &v31;
  }
  else
  {
    v24 = 0;
    dwFlags = 0;
  }
  ErrorToNtStatus = BCryptVerifySignature(hKey, v24, pbOutput, v14, pbSignature, cbSignature, dwFlags);
  if ( ErrorToNtStatus < 0 )
    goto LABEL_32;
LABEL_33:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( p_phHash && *((_DWORD *)p_phHash - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( hKey )
    BCryptDestroyKey(hKey);
  if ( LastError )
    SetLastError(LastError);
  return (unsigned int)ErrorToNtStatus;
}

```

## disassembly

```asm
0x18007e624  push    rbp
0x18007e626  push    rbx
0x18007e627  push    rsi
0x18007e628  push    rdi
0x18007e629  push    r12
0x18007e62b  push    r13
0x18007e62d  push    r14
0x18007e62f  push    r15
0x18007e631  sub     rsp, 0A8h
0x18007e638  lea     rbp, [rsp+40h]
0x18007e63d  mov     rax, cs:__security_cookie
0x18007e644  xor     rax, rbp
0x18007e647  mov     [rbp+0A0h+var_48], rax
0x18007e64b  mov     rax, [rbp+0A0h+arg_20]
0x18007e652  mov     r12, rdx
0x18007e655  mov     rdx, [rcx+18h]
0x18007e659  xor     edi, edi
0x18007e65b  mov     [rbp+0A0h+pbSignature], rax
0x18007e65f  mov     r13, r8
0x18007e662  lea     rax, [rbp+0A0h+hKey]
0x18007e666  mov     [rbp+0A0h+cbInput], r9d
0x18007e66a  add     rdx, 60h ; '`'; pInfo
0x18007e66e  mov     [rsp+0E0h+phKey], rax; phKey
0x18007e673  xor     r9d, r9d; pvAuxInfo
0x18007e676  mov     [rbp+0A0h+hKey], 0
0x18007e67e  xor     r8d, r8d; dwFlags
0x18007e681  mov     [rbp+0A0h+phHash], rdi
0x18007e685  mov     ecx, 10001h; dwCertEncodingType
0x18007e68a  mov     [rbp+0A0h+var_80], rdi
0x18007e68e  mov     [rbp+0A0h+var_A0], edi
0x18007e691  call    cs:__imp_CryptImportPublicKeyInfoEx2
0x18007e697  test    eax, eax
0x18007e699  jnz     short loc_18007E6A5
0x18007e69b  mov     ebx, 0C0000321h
0x18007e6a0  jmp     loc_18007E872
0x18007e6a5  lea     rdx, pszAlgId; "SHA256"
0x18007e6ac  mov     rcx, r12
0x18007e6af  call    cs:__imp__o__wcsicmp
0x18007e6b5  test    eax, eax
0x18007e6b7  jnz     short loc_18007E6CC
0x18007e6b9  call    ?I_ScHelperGetHelperSha256AlgHandle@@YAPEAXXZ; I_ScHelperGetHelperSha256AlgHandle(void)
0x18007e6be  mov     ebx, cs:?g_cbSha256HashObjectLength@@3KA; ulong g_cbSha256HashObjectLength
0x18007e6c4  mov     r15d, 20h ; ' '
0x18007e6ca  jmp     short loc_18007E6F5
0x18007e6cc  lea     rdx, aSha1; "SHA1"
0x18007e6d3  mov     rcx, r12
0x18007e6d6  call    cs:__imp__o__wcsicmp
0x18007e6dc  test    eax, eax
0x18007e6de  jnz     loc_18007E86D
0x18007e6e4  call    ?I_ScHelperGetHelperSha1AlgHandle@@YAPEAXXZ; I_ScHelperGetHelperSha1AlgHandle(void)
0x18007e6e9  mov     ebx, cs:?g_cbHashObjectLength@@3KA; ulong g_cbHashObjectLength
0x18007e6ef  mov     r15d, 14h
0x18007e6f5  mov     r14, rax
0x18007e6f8  test    rax, rax
0x18007e6fb  jnz     short loc_18007E707
0x18007e6fd  mov     ebx, 0C000009Ah
0x18007e702  jmp     loc_18007E872
0x18007e707  test    ebx, ebx
0x18007e709  jz      short loc_18007E76E
0x18007e70b  mov     esi, ebx
0x18007e70d  cmp     rsi, cs:g_ulMaxStackAllocSize
0x18007e714  ja      short loc_18007E76E
0x18007e716  mov     rcx, cs:g_ulAdditionalProbeSize
0x18007e71d  add     rcx, 8
0x18007e721  add     rcx, rsi
0x18007e724  cmp     rcx, rsi
0x18007e727  jb      short loc_18007E76E
0x18007e729  call    VerifyStackAvailable
0x18007e72e  test    eax, eax
0x18007e730  jz      short loc_18007E76E
0x18007e732  lea     rax, [rsi+8]
0x18007e736  lea     rcx, [rax+0Fh]
0x18007e73a  cmp     rcx, rax
0x18007e73d  ja      short loc_18007E749
0x18007e73f  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18007e749  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18007e74d  mov     rax, rcx
0x18007e750  call    _alloca_probe
0x18007e755  sub     rsp, rcx
0x18007e758  lea     rdi, [rsp+0E0h+var_A0]
0x18007e75d  test    rdi, rdi
0x18007e760  jz      short loc_18007E76E
0x18007e762  mov     dword ptr [rdi], 6B637453h
0x18007e768  add     rdi, 8
0x18007e76c  jnz     short loc_18007E797
0x18007e76e  mov     eax, ebx
0x18007e770  lea     rcx, [rax+8]
0x18007e774  cmp     rcx, rax
0x18007e777  jb      short loc_18007E797
0x18007e779  mov     rax, cs:g_pfnAllocate
0x18007e780  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e785  mov     rdi, rax
0x18007e788  test    rax, rax
0x18007e78b  jz      short loc_18007E797
0x18007e78d  mov     dword ptr [rax], 70616548h
0x18007e793  add     rdi, 8
0x18007e797  test    rdi, rdi
0x18007e79a  jnz     short loc_18007E7A6
0x18007e79c  mov     ebx, 0C0000017h
0x18007e7a1  jmp     loc_18007E872
0x18007e7a6  mov     [rsp+0E0h+dwFlags], 0; dwFlags
0x18007e7ae  lea     rdx, [rbp+0A0h+phHash]; phHash
0x18007e7b2  mov     [rsp+0E0h+cbSecret], 0; cbSecret
0x18007e7ba  mov     r9d, ebx; cbHashObject
0x18007e7bd  mov     r8, rdi; pbHashObject
0x18007e7c0  mov     [rsp+0E0h+phKey], 0; pbSecret
0x18007e7c9  mov     rcx, r14; hAlgorithm
0x18007e7cc  call    cs:__imp_BCryptCreateHash
0x18007e7d2  mov     ebx, eax
0x18007e7d4  test    eax, eax
0x18007e7d6  js      loc_18007E872
0x18007e7dc  mov     r8d, [rbp+0A0h+cbInput]; cbInput
0x18007e7e0  xor     r9d, r9d; dwFlags
0x18007e7e3  mov     rcx, [rbp+0A0h+phHash]; hHash
0x18007e7e7  mov     rdx, r13; pbInput
0x18007e7ea  call    cs:__imp_BCryptHashData
0x18007e7f0  mov     ebx, eax
0x18007e7f2  test    eax, eax
0x18007e7f4  js      short loc_18007E872
0x18007e7f6  mov     rcx, [rbp+0A0h+phHash]; hHash
0x18007e7fa  lea     rdx, [rbp+0A0h+pbOutput]; pbOutput
0x18007e7fe  xor     r9d, r9d; dwFlags
0x18007e801  mov     r8d, r15d; cbOutput
0x18007e804  call    cs:__imp_BCryptFinishHash
0x18007e80a  mov     ebx, eax
0x18007e80c  test    eax, eax
0x18007e80e  js      short loc_18007E872
0x18007e810  mov     rdx, [rbp+0A0h+hKey]; void *
0x18007e814  lea     r8, [rbp+0A0h+var_A0]; int *
0x18007e818  xor     ecx, ecx; int
0x18007e81a  call    ?ScHelperIsNcryptRsaKey@@YAJHPEAXPEAH@Z; ScHelperIsNcryptRsaKey(int,void *,int *)
0x18007e81f  mov     ebx, eax
0x18007e821  test    eax, eax
0x18007e823  js      short loc_18007E872
0x18007e825  xor     esi, esi
0x18007e827  cmp     [rbp+0A0h+var_A0], esi
0x18007e82a  jz      short loc_18007E839
0x18007e82c  mov     [rbp+0A0h+var_80], r12
0x18007e830  lea     eax, [rsi+2]
0x18007e833  lea     rdx, [rbp+0A0h+var_80]
0x18007e837  jmp     short loc_18007E83D
0x18007e839  xor     edx, edx; pPaddingInfo
0x18007e83b  xor     eax, eax
0x18007e83d  mov     rcx, [rbp+0A0h+hKey]; hKey
0x18007e841  lea     r8, [rbp+0A0h+pbOutput]; pbHash
0x18007e845  mov     [rsp+0E0h+dwFlags], eax; dwFlags
0x18007e849  mov     r9d, r15d; cbHash
0x18007e84c  mov     eax, [rbp+0A0h+cbSignature]
0x18007e852  mov     [rsp+0E0h+cbSecret], eax; cbSignature
0x18007e856  mov     rax, [rbp+0A0h+pbSignature]
0x18007e85a  mov     [rsp+0E0h+phKey], rax; pbSignature
0x18007e85f  call    cs:__imp_BCryptVerifySignature
0x18007e865  mov     ebx, eax
0x18007e867  test    eax, eax
0x18007e869  jns     short loc_18007E88B
0x18007e86b  jmp     short loc_18007E872
0x18007e86d  mov     ebx, 0C00000BBh
0x18007e872  call    cs:__imp_GetLastError
0x18007e878  mov     edx, 1000Fh; unsigned int
0x18007e87d  mov     ecx, ebx; int
0x18007e87f  mov     r8d, eax; unsigned int
0x18007e882  mov     esi, eax
0x18007e884  call    ?LogEventAndTranslateLastErrorToNtStatus@@YAJJKK@Z; LogEventAndTranslateLastErrorToNtStatus(long,ulong,ulong)
0x18007e889  mov     ebx, eax
0x18007e88b  mov     rcx, [rbp+0A0h+phHash]; hHash
0x18007e88f  test    rcx, rcx
0x18007e892  jz      short loc_18007E89A
0x18007e894  call    cs:__imp_BCryptDestroyHash
0x18007e89a  test    rdi, rdi
0x18007e89d  jz      short loc_18007E8B7
0x18007e89f  lea     rcx, [rdi-8]
0x18007e8a3  cmp     dword ptr [rcx], 70616548h
0x18007e8a9  jnz     short loc_18007E8B7
0x18007e8ab  mov     rax, cs:g_pfnFree
0x18007e8b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e8b7  mov     rcx, [rbp+0A0h+hKey]; hKey
0x18007e8bb  test    rcx, rcx
0x18007e8be  jz      short loc_18007E8C6
0x18007e8c0  call    cs:__imp_BCryptDestroyKey
0x18007e8c6  test    esi, esi
0x18007e8c8  jz      short loc_18007E8D2
0x18007e8ca  mov     ecx, esi; dwErrCode
0x18007e8cc  call    cs:__imp_SetLastError
0x18007e8d2  mov     eax, ebx
0x18007e8d4  mov     rcx, [rbp+0A0h+var_48]
0x18007e8d8  xor     rcx, rbp; StackCookie
0x18007e8db  call    __security_check_cookie
0x18007e8e0  lea     rsp, [rbp+68h]
0x18007e8e4  pop     r15
0x18007e8e6  pop     r14
0x18007e8e8  pop     r13
0x18007e8ea  pop     r12
0x18007e8ec  pop     rdi
0x18007e8ed  pop     rsi
0x18007e8ee  pop     rbx
0x18007e8ef  pop     rbp
0x18007e8f0  retn
```
