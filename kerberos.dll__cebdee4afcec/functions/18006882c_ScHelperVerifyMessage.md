# ScHelperVerifyMessage

- ea: `0x18006882c`
- end: `0x180068af9`
- name: `ScHelperVerifyMessage`
- size: `717`
- prototype: `__int64 __fastcall(__int64, __int64, UCHAR *, ULONG, UCHAR *, ULONG cbSignature)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x180034328`
- `0x1800d6780`

## callees

- `0x180007e80`
- `0x180034f04`
- `0x18006882c`
- `0x18006bf90`
- `0x180070680`
- `0x1800d62c4`
- `0x1800d637c`
- `0x1800f1ea0`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800688b7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800688de`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800688b7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800688de`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180068ad4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180068ad4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068a7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068a7a`
- `bcrypt!BCryptCreateHash` at `0x1800689d4`
- `bcrypt!BCryptCreateHash` at `0x1800689d4`
- `bcrypt!BCryptHashData` at `0x1800689f2`
- `bcrypt!BCryptHashData` at `0x1800689f2`
- `bcrypt!BCryptDestroyHash` at `0x180068a9c`
- `bcrypt!BCryptDestroyHash` at `0x180068a9c`
- `bcrypt!BCryptFinishHash` at `0x180068a0c`
- `bcrypt!BCryptFinishHash` at `0x180068a0c`
- `bcrypt!BCryptVerifySignature` at `0x180068a67`
- `bcrypt!BCryptVerifySignature` at `0x180068a67`
- `bcrypt!BCryptDestroyKey` at `0x180068ac8`
- `bcrypt!BCryptDestroyKey` at `0x180068ac8`
- `CRYPT32!CryptImportPublicKeyInfoEx2` at `0x180068899`
- `CRYPT32!CryptImportPublicKeyInfoEx2` at `0x180068899`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ScHelperVerifyMessage(__int64 a1, __int64 a2, UCHAR *a3, ULONG a4, UCHAR *a5, ULONG cbSignature)
{
  struct _CERT_PUBLIC_KEY_INFO *v7; // rdx
  UCHAR *p_phHash; // rdi
  NTSTATUS ErrorToNtStatus; // ebx
  void *HelperSha1AlgHandle; // rax
  ULONG v12; // ebx
  ULONG v13; // r15d
  void *v14; // r14
  unsigned __int64 v15; // rcx
  unsigned __int64 v16; // rcx
  void *v17; // rsp
  void *v18; // rsp
  UCHAR *v19; // rax
  DWORD LastError; // esi
  ULONG dwFlags; // eax
  __int64 *v22; // rdx
  __int64 v24; // [rsp+0h] [rbp-40h] BYREF
  int v25; // [rsp+40h] [rbp+0h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp+8h] BYREF
  BCRYPT_KEY_HANDLE hKey; // [rsp+50h] [rbp+10h] BYREF
  ULONG cbInput; // [rsp+58h] [rbp+18h]
  __int64 v29; // [rsp+60h] [rbp+20h] BYREF
  PUCHAR pbSignature; // [rsp+68h] [rbp+28h]
  UCHAR pbOutput[32]; // [rsp+78h] [rbp+38h] BYREF

  v7 = *(struct _CERT_PUBLIC_KEY_INFO **)(a1 + 24);
  p_phHash = 0;
  pbSignature = a5;
  cbInput = a4;
  hKey = 0;
  phHash = 0;
  v29 = 0;
  v25 = 0;
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
    v12 = g_cbHashObjectLength;
    v13 = 20;
  }
  else
  {
    HelperSha1AlgHandle = I_ScHelperGetHelperSha256AlgHandle();
    v12 = g_cbSha256HashObjectLength;
    v13 = 32;
  }
  v14 = HelperSha1AlgHandle;
  if ( !HelperSha1AlgHandle )
  {
    ErrorToNtStatus = -1073741670;
    goto LABEL_32;
  }
  if ( !v12
    || v12 > (unsigned __int64)g_ulMaxStackAllocSize
    || (unsigned __int64)v12 + g_ulAdditionalProbeSize + 8 < v12
    || !(unsigned int)VerifyStackAvailable() )
  {
    goto LABEL_45;
  }
  v15 = v12 + 23LL;
  if ( v15 <= (unsigned __int64)v12 + 8 )
    v15 = 0xFFFFFFFFFFFFFF0LL;
  v16 = v15 & 0xFFFFFFFFFFFFFFF0uLL;
  v17 = alloca(v16);
  v18 = alloca(v16);
  p_phHash = (UCHAR *)&v25;
  if ( &v24 == (__int64 *)-64LL || (v25 = 1801679955, (p_phHash = (UCHAR *)&phHash) == 0) )
  {
LABEL_45:
    if ( (unsigned __int64)v12 + 8 >= v12 )
    {
      v19 = (UCHAR *)((__int64 (*)(void))g_pfnAllocate)();
      p_phHash = v19;
      if ( v19 )
      {
        *(_DWORD *)v19 = 1885431112;
        p_phHash = v19 + 8;
      }
    }
  }
  if ( !p_phHash )
  {
    ErrorToNtStatus = -1073741801;
    goto LABEL_32;
  }
  ErrorToNtStatus = BCryptCreateHash(v14, &phHash, p_phHash, v12, 0, 0, 0);
  if ( ErrorToNtStatus < 0 )
    goto LABEL_32;
  ErrorToNtStatus = BCryptHashData(phHash, a3, cbInput, 0);
  if ( ErrorToNtStatus < 0 )
    goto LABEL_32;
  ErrorToNtStatus = BCryptFinishHash(phHash, pbOutput, v13, 0);
  if ( ErrorToNtStatus < 0 )
    goto LABEL_32;
  ErrorToNtStatus = ScHelperIsNcryptRsaKey(0, hKey, &v25);
  if ( ErrorToNtStatus < 0 )
    goto LABEL_32;
  LastError = 0;
  if ( v25 )
  {
    v29 = a2;
    dwFlags = 2;
    v22 = &v29;
  }
  else
  {
    v22 = 0;
    dwFlags = 0;
  }
  ErrorToNtStatus = BCryptVerifySignature(hKey, v22, pbOutput, v13, pbSignature, cbSignature, dwFlags);
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
0x18006882c  push    rbp
0x18006882e  push    rbx
0x18006882f  push    rsi
0x180068830  push    rdi
0x180068831  push    r12
0x180068833  push    r13
0x180068835  push    r14
0x180068837  push    r15
0x180068839  sub     rsp, 0A8h
0x180068840  lea     rbp, [rsp+40h]
0x180068845  mov     rax, cs:__security_cookie
0x18006884c  xor     rax, rbp
0x18006884f  mov     [rbp+0A0h+var_48], rax
0x180068853  mov     rax, [rbp+0A0h+arg_20]
0x18006885a  mov     r12, rdx
0x18006885d  mov     rdx, [rcx+18h]
0x180068861  xor     edi, edi
0x180068863  mov     [rbp+0A0h+pbSignature], rax
0x180068867  mov     r13, r8
0x18006886a  lea     rax, [rbp+0A0h+hKey]
0x18006886e  mov     [rbp+0A0h+cbInput], r9d
0x180068872  add     rdx, 60h ; '`'; pInfo
0x180068876  mov     [rsp+0E0h+phKey], rax; phKey
0x18006887b  xor     r9d, r9d; pvAuxInfo
0x18006887e  mov     [rbp+0A0h+hKey], 0
0x180068886  xor     r8d, r8d; dwFlags
0x180068889  mov     [rbp+0A0h+phHash], rdi
0x18006888d  mov     ecx, 10001h; dwCertEncodingType
0x180068892  mov     [rbp+0A0h+var_80], rdi
0x180068896  mov     [rbp+0A0h+var_A0], edi
0x180068899  call    cs:__imp_CryptImportPublicKeyInfoEx2
0x18006889f  test    eax, eax
0x1800688a1  jnz     short loc_1800688AD
0x1800688a3  mov     ebx, 0C0000321h
0x1800688a8  jmp     loc_180068A7A
0x1800688ad  lea     rdx, aSha256; "SHA256"
0x1800688b4  mov     rcx, r12
0x1800688b7  call    cs:__imp__o__wcsicmp
0x1800688bd  test    eax, eax
0x1800688bf  jnz     short loc_1800688D4
0x1800688c1  call    ?I_ScHelperGetHelperSha256AlgHandle@@YAPEAXXZ; I_ScHelperGetHelperSha256AlgHandle(void)
0x1800688c6  mov     ebx, cs:?g_cbSha256HashObjectLength@@3KA; ulong g_cbSha256HashObjectLength
0x1800688cc  mov     r15d, 20h ; ' '
0x1800688d2  jmp     short loc_1800688FD
0x1800688d4  lea     rdx, pszAlgId; "SHA1"
0x1800688db  mov     rcx, r12
0x1800688de  call    cs:__imp__o__wcsicmp
0x1800688e4  test    eax, eax
0x1800688e6  jnz     loc_180068A75
0x1800688ec  call    ?I_ScHelperGetHelperSha1AlgHandle@@YAPEAXXZ; I_ScHelperGetHelperSha1AlgHandle(void)
0x1800688f1  mov     ebx, cs:?g_cbHashObjectLength@@3KA; ulong g_cbHashObjectLength
0x1800688f7  mov     r15d, 14h
0x1800688fd  mov     r14, rax
0x180068900  test    rax, rax
0x180068903  jnz     short loc_18006890F
0x180068905  mov     ebx, 0C000009Ah
0x18006890a  jmp     loc_180068A7A
0x18006890f  test    ebx, ebx
0x180068911  jz      short loc_180068976
0x180068913  mov     esi, ebx
0x180068915  cmp     rsi, cs:g_ulMaxStackAllocSize
0x18006891c  ja      short loc_180068976
0x18006891e  mov     rcx, cs:g_ulAdditionalProbeSize
0x180068925  add     rcx, 8
0x180068929  add     rcx, rsi
0x18006892c  cmp     rcx, rsi
0x18006892f  jb      short loc_180068976
0x180068931  call    VerifyStackAvailable
0x180068936  test    eax, eax
0x180068938  jz      short loc_180068976
0x18006893a  lea     rax, [rsi+8]
0x18006893e  lea     rcx, [rax+0Fh]
0x180068942  cmp     rcx, rax
0x180068945  ja      short loc_180068951
0x180068947  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180068951  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180068955  mov     rax, rcx
0x180068958  call    _alloca_probe
0x18006895d  sub     rsp, rcx
0x180068960  lea     rdi, [rsp+0E0h+var_A0]
0x180068965  test    rdi, rdi
0x180068968  jz      short loc_180068976
0x18006896a  mov     dword ptr [rdi], 6B637453h
0x180068970  add     rdi, 8
0x180068974  jnz     short loc_18006899F
0x180068976  mov     eax, ebx
0x180068978  lea     rcx, [rax+8]
0x18006897c  cmp     rcx, rax
0x18006897f  jb      short loc_18006899F
0x180068981  mov     rax, cs:g_pfnAllocate
0x180068988  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006898d  mov     rdi, rax
0x180068990  test    rax, rax
0x180068993  jz      short loc_18006899F
0x180068995  mov     dword ptr [rax], 70616548h
0x18006899b  add     rdi, 8
0x18006899f  test    rdi, rdi
0x1800689a2  jnz     short loc_1800689AE
0x1800689a4  mov     ebx, 0C0000017h
0x1800689a9  jmp     loc_180068A7A
0x1800689ae  mov     [rsp+0E0h+dwFlags], 0; dwFlags
0x1800689b6  lea     rdx, [rbp+0A0h+phHash]; phHash
0x1800689ba  mov     [rsp+0E0h+cbSecret], 0; cbSecret
0x1800689c2  mov     r9d, ebx; cbHashObject
0x1800689c5  mov     r8, rdi; pbHashObject
0x1800689c8  mov     [rsp+0E0h+phKey], 0; pbSecret
0x1800689d1  mov     rcx, r14; hAlgorithm
0x1800689d4  call    cs:__imp_BCryptCreateHash
0x1800689da  mov     ebx, eax
0x1800689dc  test    eax, eax
0x1800689de  js      loc_180068A7A
0x1800689e4  mov     r8d, [rbp+0A0h+cbInput]; cbInput
0x1800689e8  xor     r9d, r9d; dwFlags
0x1800689eb  mov     rcx, [rbp+0A0h+phHash]; hHash
0x1800689ef  mov     rdx, r13; pbInput
0x1800689f2  call    cs:__imp_BCryptHashData
0x1800689f8  mov     ebx, eax
0x1800689fa  test    eax, eax
0x1800689fc  js      short loc_180068A7A
0x1800689fe  mov     rcx, [rbp+0A0h+phHash]; hHash
0x180068a02  lea     rdx, [rbp+0A0h+pbOutput]; pbOutput
0x180068a06  xor     r9d, r9d; dwFlags
0x180068a09  mov     r8d, r15d; cbOutput
0x180068a0c  call    cs:__imp_BCryptFinishHash
0x180068a12  mov     ebx, eax
0x180068a14  test    eax, eax
0x180068a16  js      short loc_180068A7A
0x180068a18  mov     rdx, [rbp+0A0h+hKey]; void *
0x180068a1c  lea     r8, [rbp+0A0h+var_A0]; int *
0x180068a20  xor     ecx, ecx; int
0x180068a22  call    ?ScHelperIsNcryptRsaKey@@YAJHPEAXPEAH@Z; ScHelperIsNcryptRsaKey(int,void *,int *)
0x180068a27  mov     ebx, eax
0x180068a29  test    eax, eax
0x180068a2b  js      short loc_180068A7A
0x180068a2d  xor     esi, esi
0x180068a2f  cmp     [rbp+0A0h+var_A0], esi
0x180068a32  jz      short loc_180068A41
0x180068a34  mov     [rbp+0A0h+var_80], r12
0x180068a38  lea     eax, [rsi+2]
0x180068a3b  lea     rdx, [rbp+0A0h+var_80]
0x180068a3f  jmp     short loc_180068A45
0x180068a41  xor     edx, edx; pPaddingInfo
0x180068a43  xor     eax, eax
0x180068a45  mov     rcx, [rbp+0A0h+hKey]; hKey
0x180068a49  lea     r8, [rbp+0A0h+pbOutput]; pbHash
0x180068a4d  mov     [rsp+0E0h+dwFlags], eax; dwFlags
0x180068a51  mov     r9d, r15d; cbHash
0x180068a54  mov     eax, [rbp+0A0h+cbSignature]
0x180068a5a  mov     [rsp+0E0h+cbSecret], eax; cbSignature
0x180068a5e  mov     rax, [rbp+0A0h+pbSignature]
0x180068a62  mov     [rsp+0E0h+phKey], rax; pbSignature
0x180068a67  call    cs:__imp_BCryptVerifySignature
0x180068a6d  mov     ebx, eax
0x180068a6f  test    eax, eax
0x180068a71  js      short loc_180068A7A
0x180068a73  jmp     short loc_180068A93
0x180068a75  mov     ebx, 0C00000BBh
0x180068a7a  call    cs:__imp_GetLastError
0x180068a80  mov     edx, 1000Fh; unsigned int
0x180068a85  mov     ecx, ebx; int
0x180068a87  mov     r8d, eax; unsigned int
0x180068a8a  mov     esi, eax
0x180068a8c  call    ?LogEventAndTranslateLastErrorToNtStatus@@YAJJKK@Z; LogEventAndTranslateLastErrorToNtStatus(long,ulong,ulong)
0x180068a91  mov     ebx, eax
0x180068a93  mov     rcx, [rbp+0A0h+phHash]; hHash
0x180068a97  test    rcx, rcx
0x180068a9a  jz      short loc_180068AA2
0x180068a9c  call    cs:__imp_BCryptDestroyHash
0x180068aa2  test    rdi, rdi
0x180068aa5  jz      short loc_180068ABF
0x180068aa7  lea     rcx, [rdi-8]
0x180068aab  cmp     dword ptr [rcx], 70616548h
0x180068ab1  jnz     short loc_180068ABF
0x180068ab3  mov     rax, cs:g_pfnFree
0x180068aba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068abf  mov     rcx, [rbp+0A0h+hKey]; hKey
0x180068ac3  test    rcx, rcx
0x180068ac6  jz      short loc_180068ACE
0x180068ac8  call    cs:__imp_BCryptDestroyKey
0x180068ace  test    esi, esi
0x180068ad0  jz      short loc_180068ADA
0x180068ad2  mov     ecx, esi; dwErrCode
0x180068ad4  call    cs:__imp_SetLastError
0x180068ada  mov     eax, ebx
0x180068adc  mov     rcx, [rbp+0A0h+var_48]
0x180068ae0  xor     rcx, rbp; StackCookie
0x180068ae3  call    __security_check_cookie
0x180068ae8  lea     rsp, [rbp+68h]
0x180068aec  pop     r15
0x180068aee  pop     r14
0x180068af0  pop     r13
0x180068af2  pop     r12
0x180068af4  pop     rdi
0x180068af5  pop     rsi
0x180068af6  pop     rbx
0x180068af7  pop     rbp
0x180068af8  retn
```
