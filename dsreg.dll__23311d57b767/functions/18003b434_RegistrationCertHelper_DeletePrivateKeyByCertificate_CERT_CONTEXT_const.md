# RegistrationCertHelper::DeletePrivateKeyByCertificate(_CERT_CONTEXT const *)

- ea: `0x18003b434`
- end: `0x18003b539`
- name: `?DeletePrivateKeyByCertificate@RegistrationCertHelper@@CAJPEBU_CERT_CONTEXT@@@Z`
- size: `261`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCert)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18005c780`
- `0x18005c95c`

## callees

- `0x1800084f4`
- `0x180008530`
- `0x18000bac0`
- `0x18003b434`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b497`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b497`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x18003b48d`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x18003b48d`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18003b515`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18003b515`
- `ncrypt!NCryptDeleteKey` at `0x18003b4ca`
- `ncrypt!NCryptDeleteKey` at `0x18003b4ca`
- `ncrypt!NCryptFreeObject` at `0x18003b50b`
- `ncrypt!NCryptFreeObject` at `0x18003b50b`

## string_xrefs

- `0x18003b43d`: `RegistrationCertHelper::DeletePrivateKeyByCertificate`
- `0x18003b4ac`: `RegistrationCertHelper::DeletePrivateKeyByCertificate`
- `0x18003b4e0`: `RegistrationCertHelper::DeletePrivateKeyByCertificate`
- `0x18003b51e`: `RegistrationCertHelper::DeletePrivateKeyByCertificate`
- `0x18003b4d9`: `NCryptDeleteKey`

## pseudocode

```c
__int64 __fastcall RegistrationCertHelper::DeletePrivateKeyByCertificate(PCCERT_CONTEXT pCert)
{
  signed int LastError; // eax
  unsigned int v3; // ebx
  SECURITY_STATUS v4; // eax
  BOOL pfCallerFreeProvOrNCryptKey; // [rsp+48h] [rbp+10h] BYREF
  DWORD pdwKeySpec; // [rsp+50h] [rbp+18h] BYREF
  HCRYPTPROV_OR_NCRYPT_KEY_HANDLE phCryptProvOrNCryptKey; // [rsp+58h] [rbp+20h] BYREF

  Logger::TraceVerbose((wchar_t *)L"%s started", L"RegistrationCertHelper::DeletePrivateKeyByCertificate");
  pfCallerFreeProvOrNCryptKey = 0;
  pdwKeySpec = 2;
  phCryptProvOrNCryptKey = 0;
  if ( CryptAcquireCertificatePrivateKey(
         pCert,
         0x70040u,
         0,
         &phCryptProvOrNCryptKey,
         &pdwKeySpec,
         &pfCallerFreeProvOrNCryptKey) )
  {
    v4 = NCryptDeleteKey(phCryptProvOrNCryptKey, 0);
    v3 = v4;
    if ( v4 < 0 )
    {
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"RegistrationCertHelper::DeletePrivateKeyByCertificate",
        L"NCryptDeleteKey",
        (unsigned int)v4);
      if ( pfCallerFreeProvOrNCryptKey )
      {
        if ( phCryptProvOrNCryptKey )
        {
          if ( pdwKeySpec == -1 )
            NCryptFreeObject(phCryptProvOrNCryptKey);
          else
            CryptReleaseContext(phCryptProvOrNCryptKey, 0);
        }
      }
    }
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    Logger::TraceWarning(
      (wchar_t *)L"%s: CryptAcquireCertificatePrivateKey returned 0x%08x.",
      L"RegistrationCertHelper::DeletePrivateKeyByCertificate",
      (unsigned int)LastError);
    v3 = 0;
  }
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"RegistrationCertHelper::DeletePrivateKeyByCertificate", v3);
  return v3;
}

```

## disassembly

```asm
0x18003b434  push    rbx
0x18003b436  sub     rsp, 30h
0x18003b43a  mov     rbx, rcx
0x18003b43d  lea     rdx, aRegistrationce_0; "RegistrationCertHelper::DeletePrivateKe"...
0x18003b444  lea     rcx, aSStarted; "%s started"
0x18003b44b  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18003b450  lea     rax, [rsp+38h+arg_8]
0x18003b455  mov     [rsp+38h+arg_8], 0
0x18003b45d  mov     [rsp+38h+pfCallerFreeProvOrNCryptKey], rax; pfCallerFreeProvOrNCryptKey
0x18003b462  lea     r9, [rsp+38h+phCryptProvOrNCryptKey]; phCryptProvOrNCryptKey
0x18003b467  lea     rax, [rsp+38h+arg_10]
0x18003b46c  mov     [rsp+38h+arg_10], 2
0x18003b474  xor     r8d, r8d; pvParameters
0x18003b477  mov     [rsp+38h+pdwKeySpec], rax; pdwKeySpec
0x18003b47c  mov     edx, 70040h; dwFlags
0x18003b481  mov     [rsp+38h+phCryptProvOrNCryptKey], 0
0x18003b48a  mov     rcx, rbx; pCert
0x18003b48d  call    cs:__imp_CryptAcquireCertificatePrivateKey
0x18003b493  test    eax, eax
0x18003b495  jnz     short loc_18003B4C3
0x18003b497  call    cs:__imp_GetLastError
0x18003b49d  test    eax, eax
0x18003b49f  jle     short loc_18003B4A9
0x18003b4a1  movzx   eax, ax
0x18003b4a4  or      eax, 80070000h
0x18003b4a9  mov     r8d, eax
0x18003b4ac  lea     rdx, aRegistrationce_0; "RegistrationCertHelper::DeletePrivateKe"...
0x18003b4b3  lea     rcx, aSCryptacquirec; "%s: CryptAcquireCertificatePrivateKey r"...
0x18003b4ba  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18003b4bf  xor     ebx, ebx
0x18003b4c1  jmp     short loc_18003B51B
0x18003b4c3  mov     rcx, [rsp+38h+phCryptProvOrNCryptKey]; hKey
0x18003b4c8  xor     edx, edx; dwFlags
0x18003b4ca  call    cs:__imp_NCryptDeleteKey
0x18003b4d0  mov     ebx, eax
0x18003b4d2  test    eax, eax
0x18003b4d4  jns     short loc_18003B51B
0x18003b4d6  mov     r9d, eax
0x18003b4d9  lea     r8, aNcryptdeleteke_0; "NCryptDeleteKey"
0x18003b4e0  lea     rdx, aRegistrationce_0; "RegistrationCertHelper::DeletePrivateKe"...
0x18003b4e7  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18003b4ee  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18003b4f3  cmp     [rsp+38h+arg_8], 0
0x18003b4f8  jz      short loc_18003B51B
0x18003b4fa  mov     rcx, [rsp+38h+phCryptProvOrNCryptKey]; hProv
0x18003b4ff  test    rcx, rcx
0x18003b502  jz      short loc_18003B51B
0x18003b504  cmp     [rsp+38h+arg_10], 0FFFFFFFFh
0x18003b509  jnz     short loc_18003B513
0x18003b50b  call    cs:__imp_NCryptFreeObject
0x18003b511  jmp     short loc_18003B51B
0x18003b513  xor     edx, edx; dwFlags
0x18003b515  call    cs:__imp_CryptReleaseContext
0x18003b51b  mov     r8d, ebx
0x18003b51e  lea     rdx, aRegistrationce_0; "RegistrationCertHelper::DeletePrivateKe"...
0x18003b525  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x18003b52c  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18003b531  mov     eax, ebx
0x18003b533  add     rsp, 30h
0x18003b537  pop     rbx
0x18003b538  retn
```
