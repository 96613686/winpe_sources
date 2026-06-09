# GetSmartCardCertificate(ushort *,_CERT_HASH *,_CRYPT_KEY_PROV_INFO *)

- ea: `0x18000627c`
- end: `0x180006644`
- name: `?GetSmartCardCertificate@@YAHPEAGPEAU_CERT_HASH@@PEAU_CRYPT_KEY_PROV_INFO@@@Z`
- size: `968`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc, struct _CERT_HASH *, struct _CRYPT_KEY_PROV_INFO *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000688c`

## callees

- `0x1800056d4`
- `0x18000627c`
- `0x18000664c`
- `0x18000b0b6`
- `0x18000b100`

## import_xrefs

- `ADVAPI32!CryptDestroyKey` at `0x1800065b5`
- `ADVAPI32!CryptDestroyKey` at `0x1800065b5`
- `ADVAPI32!CryptGetUserKey` at `0x18000632c`
- `ADVAPI32!CryptGetUserKey` at `0x18000632c`
- `ADVAPI32!CryptGetKeyParam` at `0x18000636b`
- `ADVAPI32!CryptGetKeyParam` at `0x1800063f0`
- `ADVAPI32!CryptGetKeyParam` at `0x18000636b`
- `ADVAPI32!CryptGetKeyParam` at `0x1800063f0`
- `ADVAPI32!CryptAcquireContextW` at `0x1800062e2`
- `ADVAPI32!CryptAcquireContextW` at `0x1800062e2`
- `ADVAPI32!CryptReleaseContext` at `0x1800065ca`
- `ADVAPI32!CryptReleaseContext` at `0x1800065ca`
- `KERNEL32!LocalAlloc` at `0x18000639e`
- `KERNEL32!LocalAlloc` at `0x18000653b`
- `KERNEL32!LocalAlloc` at `0x18000639e`
- `KERNEL32!LocalAlloc` at `0x18000653b`
- `KERNEL32!GetLastError` at `0x1800062fb`
- `KERNEL32!GetLastError` at `0x180006345`
- `KERNEL32!GetLastError` at `0x180006384`
- `KERNEL32!GetLastError` at `0x1800063b5`
- `KERNEL32!GetLastError` at `0x180006409`
- `KERNEL32!GetLastError` at `0x180006450`
- `KERNEL32!GetLastError` at `0x1800064a3`
- `KERNEL32!GetLastError` at `0x180006558`
- `KERNEL32!GetLastError` at `0x1800062fb`
- `KERNEL32!GetLastError` at `0x180006345`
- `KERNEL32!GetLastError` at `0x180006384`
- `KERNEL32!GetLastError` at `0x1800063b5`
- `KERNEL32!GetLastError` at `0x180006409`
- `KERNEL32!GetLastError` at `0x180006450`
- `KERNEL32!GetLastError` at `0x1800064a3`
- `KERNEL32!GetLastError` at `0x180006558`
- `KERNEL32!LocalFree` at `0x180006586`
- `KERNEL32!LocalFree` at `0x180006594`
- `KERNEL32!LocalFree` at `0x1800065a6`
- `KERNEL32!LocalFree` at `0x180006586`
- `KERNEL32!LocalFree` at `0x180006594`
- `KERNEL32!LocalFree` at `0x1800065a6`
- `CRYPT32!CertFreeCertificateContext` at `0x18000659d`
- `CRYPT32!CertFreeCertificateContext` at `0x18000659d`
- `CRYPT32!CertCreateCertificateContext` at `0x180006439`
- `CRYPT32!CertCreateCertificateContext` at `0x180006439`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180006490`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180006490`
- `rtutils!TracePrintfExA` at `0x180006316`
- `rtutils!TracePrintfExA` at `0x1800063cf`
- `rtutils!TracePrintfExA` at `0x180006422`
- `rtutils!TracePrintfExA` at `0x18000646b`
- `rtutils!TracePrintfExA` at `0x1800064be`
- `rtutils!TracePrintfExA` at `0x180006503`
- `rtutils!TracePrintfExA` at `0x180006571`
- `rtutils!TracePrintfExA` at `0x180006316`
- `rtutils!TracePrintfExA` at `0x1800063cf`
- `rtutils!TracePrintfExA` at `0x180006422`
- `rtutils!TracePrintfExA` at `0x18000646b`
- `rtutils!TracePrintfExA` at `0x1800064be`
- `rtutils!TracePrintfExA` at `0x180006503`
- `rtutils!TracePrintfExA` at `0x180006571`

## string_xrefs

- `0x18000645c`: `CertCreateCertificateContext failed and returned 0x%x`
- `0x1800064f7`: `Hash compare failed`

## pseudocode

```c
__int64 __fastcall GetSmartCardCertificate(
        STRSAFE_LPCWSTR pszSrc,
        struct _CERT_HASH *a2,
        struct _CRYPT_KEY_PROV_INFO *a3)
{
  unsigned int UserKey; // ebx
  DWORD LastError; // eax
  DWORD v8; // eax
  DWORD v9; // eax
  BYTE *v10; // rax
  BYTE *v11; // r15
  DWORD v12; // eax
  DWORD v13; // eax
  const CERT_CONTEXT *CertificateContext; // rax
  const CERT_CONTEXT *v15; // r12
  DWORD v16; // eax
  unsigned int v17; // edx
  DWORD v18; // eax
  __int64 v19; // r14
  __int64 v20; // rdx
  wchar_t *v21; // rdi
  DWORD v22; // eax
  HLOCAL v23; // rcx
  DWORD pdwDataLen; // [rsp+30h] [rbp-40h] BYREF
  HCRYPTKEY phUserKey; // [rsp+38h] [rbp-38h] BYREF
  HLOCAL hMem; // [rsp+40h] [rbp-30h] BYREF
  HCRYPTPROV phProv; // [rsp+48h] [rbp-28h] BYREF
  __int128 pvData; // [rsp+50h] [rbp-20h] BYREF
  __int64 v30; // [rsp+60h] [rbp-10h]

  phProv = 0;
  phUserKey = 0;
  pdwDataLen = 0;
  hMem = 0;
  v30 = 0;
  pvData = 0;
  UserKey = CryptAcquireContextW(&phProv, 0, pszSrc, 1u, 0x40u);
  if ( !UserKey )
  {
    if ( g_dwTraceId != -1 )
    {
      LastError = GetLastError();
      TracePrintfExA(g_dwTraceId, 0xCu, "CryptAcquireContext failed and returned 0x%x", LastError);
    }
    goto LABEL_44;
  }
  UserKey = CryptGetUserKey(phProv, 1u, &phUserKey);
  if ( !UserKey )
  {
    if ( g_dwTraceId != -1 )
    {
      v8 = GetLastError();
      TracePrintfExA(g_dwTraceId, 0xCu, "CryptGetUserKey failed and returned 0x%x", v8);
    }
    goto LABEL_44;
  }
  UserKey = CryptGetKeyParam(phUserKey, 0x1Au, 0, &pdwDataLen, 0);
  if ( !UserKey )
  {
    if ( g_dwTraceId != -1 )
    {
      v9 = GetLastError();
      TracePrintfExA(g_dwTraceId, 0xCu, "CryptGetKeyParam(KP_CERTIFICATE) failed and returned 0x%x", v9);
    }
    goto LABEL_44;
  }
  v10 = (BYTE *)LocalAlloc(0x40u, pdwDataLen);
  v11 = v10;
  if ( v10 )
  {
    UserKey = CryptGetKeyParam(phUserKey, 0x1Au, v10, &pdwDataLen, 0);
    if ( !UserKey )
    {
      if ( g_dwTraceId != -1 )
      {
        v13 = GetLastError();
        TracePrintfExA(g_dwTraceId, UserKey + 12, "CryptGetKeyParam(KP_CERTIFICATE) failed and returned: 0x%x", v13);
      }
      goto LABEL_43;
    }
    CertificateContext = CertCreateCertificateContext(0x10001u, v11, pdwDataLen);
    v15 = CertificateContext;
    if ( !CertificateContext )
    {
      if ( g_dwTraceId != -1 )
      {
        v16 = GetLastError();
        TracePrintfExA(g_dwTraceId, 0xCu, "CertCreateCertificateContext failed and returned 0x%x", v16);
      }
      UserKey = 0;
      goto LABEL_43;
    }
    LODWORD(pvData) = 20;
    if ( !CertGetCertificateContextProperty(CertificateContext, 3u, (char *)&pvData + 4, (DWORD *)&pvData) )
    {
      if ( g_dwTraceId != -1 )
      {
        v18 = GetLastError();
        TracePrintfExA(g_dwTraceId, 0xCu, "CertGetCertificateContextProperty failed and returned 0x%x", v18);
      }
LABEL_25:
      UserKey = 0;
LABEL_42:
      CertFreeCertificateContext(v15);
LABEL_43:
      LocalFree(v11);
      goto LABEL_44;
    }
    if ( a2 && ((_DWORD)pvData != *(_DWORD *)a2 || memcmp_0((char *)&pvData + 4, (char *)a2 + 4, *(unsigned int *)a2)) )
    {
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "Hash compare failed");
      goto LABEL_25;
    }
    v19 = -1;
    UserKey = LocalCryptGetProvParamW(phProv, v17, (unsigned __int16 **)&hMem);
    v20 = -1;
    do
      ++v20;
    while ( pszSrc[v20] );
    v21 = (wchar_t *)LocalAlloc(0x40u, 2 * v20 + 2);
    if ( v21 )
    {
      do
        ++v19;
      while ( pszSrc[v19] );
      StringCchCopyW(v21, v19 + 1, pszSrc);
      if ( UserKey )
      {
        v23 = 0;
        a3->pwszContainerName = (LPWSTR)hMem;
        a3->pwszProvName = v21;
        v21 = 0;
        *(_QWORD *)&a3->dwProvType = 1;
        a3->dwKeySpec = 1;
        a3->cProvParam = 0;
        a3->rgProvParam = 0;
        goto LABEL_38;
      }
    }
    else
    {
      if ( g_dwTraceId != -1 )
      {
        v22 = GetLastError();
        TracePrintfExA(g_dwTraceId, 0xCu, "LocalAlloc failed and returned %d", v22);
      }
      UserKey = 0;
    }
    v23 = hMem;
LABEL_38:
    if ( v23 )
      LocalFree(v23);
    if ( v21 )
      LocalFree(v21);
    goto LABEL_42;
  }
  if ( g_dwTraceId != -1 )
  {
    v12 = GetLastError();
    TracePrintfExA(g_dwTraceId, 0xCu, "LocalAlloc failed and returned %d", v12);
  }
  UserKey = 0;
LABEL_44:
  if ( phUserKey )
  {
    CryptDestroyKey(phUserKey);
    phUserKey = 0;
  }
  if ( phProv )
    CryptReleaseContext(phProv, 0);
  return UserKey;
}

```

## disassembly

```asm
0x18000627c  mov     [rsp-38h+arg_8], rbx
0x180006281  push    rbp
0x180006282  push    rsi
0x180006283  push    rdi
0x180006284  push    r12
0x180006286  push    r13
0x180006288  push    r14
0x18000628a  push    r15
0x18000628c  mov     rbp, rsp
0x18000628f  sub     rsp, 70h
0x180006293  mov     rax, cs:__security_cookie
0x18000629a  xor     rax, rsp
0x18000629d  mov     [rbp+var_8], rax
0x1800062a1  xor     r14d, r14d
0x1800062a4  mov     [rsp+70h+dwFlags], 40h ; '@'; dwFlags
0x1800062ac  mov     rsi, r8
0x1800062af  mov     [rbp+phProv], r14
0x1800062b3  mov     rdi, rdx
0x1800062b6  mov     [rbp+phUserKey], r14
0x1800062ba  mov     r13, rcx
0x1800062bd  mov     [rbp+pdwDataLen], r14d
0x1800062c1  xorps   xmm0, xmm0
0x1800062c4  mov     [rbp+hMem], r14
0x1800062c8  xor     eax, eax
0x1800062ca  lea     r15d, [r14+1]
0x1800062ce  mov     r8, rcx; szProvider
0x1800062d1  mov     [rbp+var_10], rax
0x1800062d5  mov     r9d, r15d; dwProvType
0x1800062d8  lea     rcx, [rbp+phProv]; phProv
0x1800062dc  xor     edx, edx; szContainer
0x1800062de  movups  [rbp+pvData], xmm0
0x1800062e2  call    cs:__imp_CryptAcquireContextW
0x1800062e8  mov     ebx, eax
0x1800062ea  test    eax, eax
0x1800062ec  jnz     short loc_180006321
0x1800062ee  cmp     cs:g_dwTraceId, 0FFFFFFFFh
0x1800062f5  jz      loc_1800065AC
0x1800062fb  call    cs:__imp_GetLastError
0x180006301  lea     r8, aCryptacquireco; "CryptAcquireContext failed and returned"...
0x180006308  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000630e  mov     r9d, eax
0x180006311  mov     edx, 0Ch; dwFlags
0x180006316  call    cs:__imp_TracePrintfExA
0x18000631c  jmp     loc_1800065AC
0x180006321  mov     rcx, [rbp+phProv]; hProv
0x180006325  lea     r8, [rbp+phUserKey]; phUserKey
0x180006329  mov     edx, r15d; dwKeySpec
0x18000632c  call    cs:__imp_CryptGetUserKey
0x180006332  mov     ebx, eax
0x180006334  test    eax, eax
0x180006336  jnz     short loc_180006354
0x180006338  cmp     cs:g_dwTraceId, 0FFFFFFFFh
0x18000633f  jz      loc_1800065AC
0x180006345  call    cs:__imp_GetLastError
0x18000634b  lea     r8, aCryptgetuserke; "CryptGetUserKey failed and returned 0x%"...
0x180006352  jmp     short loc_180006308
0x180006354  mov     rcx, [rbp+phUserKey]; hKey
0x180006358  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x18000635c  xor     r8d, r8d; pbData
0x18000635f  mov     [rsp+70h+dwFlags], r14d; dwFlags
0x180006364  lea     r12d, [r8+1Ah]
0x180006368  mov     edx, r12d; dwParam
0x18000636b  call    cs:__imp_CryptGetKeyParam
0x180006371  mov     ebx, eax
0x180006373  test    eax, eax
0x180006375  jnz     short loc_180006396
0x180006377  cmp     cs:g_dwTraceId, 0FFFFFFFFh
0x18000637e  jz      loc_1800065AC
0x180006384  call    cs:__imp_GetLastError
0x18000638a  lea     r8, aCryptgetkeypar; "CryptGetKeyParam(KP_CERTIFICATE) failed"...
0x180006391  jmp     loc_180006308
0x180006396  mov     edx, [rbp+pdwDataLen]; uBytes
0x180006399  mov     ecx, 40h ; '@'; uFlags
0x18000639e  call    cs:__imp_LocalAlloc
0x1800063a4  mov     r15, rax
0x1800063a7  test    rax, rax
0x1800063aa  jnz     short loc_1800063DD
0x1800063ac  cmp     cs:g_dwTraceId, 0FFFFFFFFh
0x1800063b3  jz      short loc_1800063D5
0x1800063b5  call    cs:__imp_GetLastError
0x1800063bb  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800063c1  lea     r8, aLocalallocFail; "LocalAlloc failed and returned %d"
0x1800063c8  mov     r9d, eax
0x1800063cb  lea     edx, [r15+0Ch]; dwFlags
0x1800063cf  call    cs:__imp_TracePrintfExA
0x1800063d5  mov     ebx, r14d
0x1800063d8  jmp     loc_1800065AC
0x1800063dd  mov     rcx, [rbp+phUserKey]; hKey
0x1800063e1  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x1800063e5  mov     r8, r15; pbData
0x1800063e8  mov     [rsp+70h+dwFlags], r14d; dwFlags
0x1800063ed  mov     edx, r12d; dwParam
0x1800063f0  call    cs:__imp_CryptGetKeyParam
0x1800063f6  mov     ebx, eax
0x1800063f8  test    eax, eax
0x1800063fa  jnz     short loc_18000642D
0x1800063fc  cmp     cs:g_dwTraceId, 0FFFFFFFFh
0x180006403  jz      loc_1800065A3
0x180006409  call    cs:__imp_GetLastError
0x18000640f  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180006415  lea     r8, aCryptgetkeypar_0; "CryptGetKeyParam(KP_CERTIFICATE) failed"...
0x18000641c  mov     r9d, eax
0x18000641f  lea     edx, [rbx+0Ch]; dwFlags
0x180006422  call    cs:__imp_TracePrintfExA
0x180006428  jmp     loc_1800065A3
0x18000642d  mov     r8d, [rbp+pdwDataLen]; cbCertEncoded
0x180006431  mov     rdx, r15; pbCertEncoded
0x180006434  mov     ecx, 10001h; dwCertEncodingType
0x180006439  call    cs:__imp_CertCreateCertificateContext
0x18000643f  mov     r12, rax
0x180006442  test    rax, rax
0x180006445  jnz     short loc_180006479
0x180006447  cmp     cs:g_dwTraceId, 0FFFFFFFFh
0x18000644e  jz      short loc_180006471
0x180006450  call    cs:__imp_GetLastError
0x180006456  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000645c  lea     r8, aCertcreatecert_0; "CertCreateCertificateContext failed and"...
0x180006463  mov     r9d, eax
0x180006466  lea     edx, [r12+0Ch]; dwFlags
0x18000646b  call    cs:__imp_TracePrintfExA
0x180006471  mov     ebx, r14d
0x180006474  jmp     loc_1800065A3
0x180006479  lea     r9, [rbp+pvData]; pcbData
0x18000647d  mov     dword ptr [rbp+pvData], 14h
0x180006484  lea     r8, [rbp+pvData+4]; pvData
0x180006488  mov     edx, 3; dwPropId
0x18000648d  mov     rcx, r12; pCertContext
0x180006490  call    cs:__imp_CertGetCertificateContextProperty
0x180006496  test    eax, eax
0x180006498  jnz     short loc_1800064CC
0x18000649a  cmp     cs:g_dwTraceId, 0FFFFFFFFh
0x1800064a1  jz      short loc_1800064C4
0x1800064a3  call    cs:__imp_GetLastError
0x1800064a9  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800064af  lea     r8, aCertgetcertifi_0; "CertGetCertificateContextProperty faile"...
0x1800064b6  mov     r9d, eax
0x1800064b9  mov     edx, 0Ch; dwFlags
0x1800064be  call    cs:__imp_TracePrintfExA
0x1800064c4  mov     ebx, r14d
0x1800064c7  jmp     loc_18000659A
0x1800064cc  test    rdi, rdi
0x1800064cf  jz      short loc_18000650B
0x1800064d1  mov     eax, [rdi]
0x1800064d3  cmp     dword ptr [rbp+pvData], eax
0x1800064d6  jnz     short loc_1800064EC
0x1800064d8  mov     r8d, eax; Size
0x1800064db  lea     rdx, [rdi+4]; Buf2
0x1800064df  lea     rcx, [rbp+pvData+4]; Buf1
0x1800064e3  call    memcmp_0
0x1800064e8  test    eax, eax
0x1800064ea  jz      short loc_18000650B
0x1800064ec  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800064f2  cmp     ecx, 0FFFFFFFFh
0x1800064f5  jz      short loc_1800064C4
0x1800064f7  lea     r8, aHashCompareFai; "Hash compare failed"
0x1800064fe  mov     edx, 0Ch; dwFlags
0x180006503  call    cs:__imp_TracePrintfExA
0x180006509  jmp     short loc_1800064C4
0x18000650b  mov     rcx, [rbp+phProv]; hProv
0x18000650f  lea     r8, [rbp+hMem]; unsigned __int16 **
0x180006513  call    ?LocalCryptGetProvParamW@@YAH_KKPEAPEAG@Z; LocalCryptGetProvParamW(unsigned __int64,ulong,ushort * *)
0x180006518  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000651c  mov     ebx, eax
0x18000651e  mov     rdx, r14
0x180006521  xor     eax, eax
0x180006523  inc     rdx
0x180006526  cmp     [r13+rdx*2+0], ax
0x18000652c  jnz     short loc_180006523
0x18000652e  lea     rdx, ds:2[rdx*2]; uBytes
0x180006536  mov     ecx, 40h ; '@'; uFlags
0x18000653b  call    cs:__imp_LocalAlloc
0x180006541  mov     rdi, rax
0x180006544  xor     eax, eax
0x180006546  test    rdi, rdi
0x180006549  jnz     loc_1800065F6
0x18000654f  cmp     cs:g_dwTraceId, 0FFFFFFFFh
0x180006556  jz      short loc_180006577
0x180006558  call    cs:__imp_GetLastError
0x18000655e  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180006564  lea     r8, aLocalallocFail; "LocalAlloc failed and returned %d"
0x18000656b  mov     r9d, eax
0x18000656e  lea     edx, [rdi+0Ch]; dwFlags
0x180006571  call    cs:__imp_TracePrintfExA
0x180006577  xor     r14d, r14d
0x18000657a  mov     ebx, r14d
0x18000657d  mov     rcx, [rbp+hMem]; hMem
0x180006581  test    rcx, rcx
0x180006584  jz      short loc_18000658C
0x180006586  call    cs:__imp_LocalFree
0x18000658c  test    rdi, rdi
0x18000658f  jz      short loc_18000659A
0x180006591  mov     rcx, rdi; hMem
0x180006594  call    cs:__imp_LocalFree
0x18000659a  mov     rcx, r12; pCertContext
0x18000659d  call    cs:__imp_CertFreeCertificateContext
0x1800065a3  mov     rcx, r15; hMem
0x1800065a6  call    cs:__imp_LocalFree
0x1800065ac  mov     rcx, [rbp+phUserKey]; hKey
0x1800065b0  test    rcx, rcx
0x1800065b3  jz      short loc_1800065BF
0x1800065b5  call    cs:__imp_CryptDestroyKey
0x1800065bb  mov     [rbp+phUserKey], r14
0x1800065bf  mov     rcx, [rbp+phProv]; hProv
0x1800065c3  test    rcx, rcx
0x1800065c6  jz      short loc_1800065D0
0x1800065c8  xor     edx, edx; dwFlags
0x1800065ca  call    cs:__imp_CryptReleaseContext
0x1800065d0  mov     eax, ebx
0x1800065d2  mov     rcx, [rbp+var_8]
0x1800065d6  xor     rcx, rsp; StackCookie
0x1800065d9  call    __security_check_cookie
0x1800065de  mov     rbx, [rsp+70h+arg_8]
0x1800065e6  add     rsp, 70h
0x1800065ea  pop     r15
0x1800065ec  pop     r14
0x1800065ee  pop     r13
0x1800065f0  pop     r12
0x1800065f2  pop     rdi
0x1800065f3  pop     rsi
0x1800065f4  pop     rbp
0x1800065f5  retn
0x1800065f6  inc     r14
0x1800065f9  cmp     [r13+r14*2+0], ax
0x1800065ff  jnz     short loc_1800065F6
0x180006601  lea     rdx, [r14+1]; cchDest
0x180006605  mov     r8, r13; pszSrc
0x180006608  mov     rcx, rdi; pszDest
0x18000660b  call    StringCchCopyW
0x180006610  xor     r14d, r14d
0x180006613  test    ebx, ebx
0x180006615  jz      loc_18000657D
0x18000661b  mov     rax, [rbp+hMem]
0x18000661f  mov     ecx, r14d
0x180006622  mov     [rsi], rax
0x180006625  lea     eax, [r14+1]
0x180006629  mov     [rsi+8], rdi
0x18000662d  mov     edi, r14d
0x180006630  mov     [rsi+10h], rax
0x180006634  mov     [rsi+28h], eax
0x180006637  mov     [rsi+18h], r14d
0x18000663b  mov     [rsi+20h], r14
0x18000663f  jmp     loc_180006581
```
