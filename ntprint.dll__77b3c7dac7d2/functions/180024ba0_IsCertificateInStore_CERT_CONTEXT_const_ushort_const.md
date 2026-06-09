# IsCertificateInStore(_CERT_CONTEXT const *,ushort const *)

- ea: `0x180024ba0`
- end: `0x180024cc4`
- name: `?IsCertificateInStore@@YAHPEBU_CERT_CONTEXT@@PEBG@Z`
- size: `292`
- prototype: `int(const struct _CERT_CONTEXT *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180024ccc`

## callees

- `0x180002300`
- `0x18000d57c`
- `0x180024ba0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024c6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024c7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024c6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024c7e`
- `CRYPT32!CertCloseStore` at `0x180024c67`
- `CRYPT32!CertCloseStore` at `0x180024c67`
- `CRYPT32!CertFindCertificateInStore` at `0x180024c31`
- `CRYPT32!CertFindCertificateInStore` at `0x180024c31`
- `CRYPT32!CertOpenStore` at `0x180024c06`
- `CRYPT32!CertOpenStore` at `0x180024c06`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180024be5`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180024be5`
- `CRYPT32!CertFreeCertificateContext` at `0x180024c44`
- `CRYPT32!CertFreeCertificateContext` at `0x180024c44`

## string_xrefs

- `0x180024c75`: `CertOpenStore for %ws failed! Error %d`

## pseudocode

```c
__int64 __fastcall IsCertificateInStore(const struct _CERT_CONTEXT *a1, const unsigned __int16 *a2)
{
  unsigned int v3; // esi
  HCERTSTORE v4; // rdi
  const CERT_CONTEXT *CertificateInStore; // rax
  DWORD LastError; // eax
  DWORD v7; // eax
  _QWORD pvFindPara[2]; // [rsp+30h] [rbp-68h] BYREF
  _BYTE v10[64]; // [rsp+40h] [rbp-58h] BYREF

  pvFindPara[0] = 64;
  v3 = 0;
  pvFindPara[1] = v10;
  if ( CertGetCertificateContextProperty(a1, 0xFu, v10, (DWORD *)pvFindPara) )
  {
    v4 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x2C000u, a2);
    if ( v4 )
    {
      CertificateInStore = CertFindCertificateInStore(v4, 0, 0, 0xE0000u, pvFindPara, 0);
      if ( CertificateInStore )
      {
        v3 = 1;
        CertFreeCertificateContext(CertificateInStore);
      }
      else
      {
        ClassInstallerTelemetry::WriteDbgTraceError("IsCertificateInStore", L"Certificate is not in the %ws store!", a2);
      }
      CertCloseStore(v4, 0);
    }
    else
    {
      LastError = GetLastError();
      ClassInstallerTelemetry::WriteDbgTraceError(
        "IsCertificateInStore",
        L"CertOpenStore for %ws failed! Error %d",
        a2,
        LastError);
    }
  }
  else
  {
    v7 = GetLastError();
    ClassInstallerTelemetry::WriteDbgTraceError(
      "IsCertificateInStore",
      L"CertGetCertificateContextProperty for %ws failed! Error %d",
      a2,
      v7);
  }
  return v3;
}

```

## disassembly

```asm
0x180024ba0  mov     r11, rsp
0x180024ba3  mov     [r11+18h], rbx
0x180024ba7  mov     [r11+20h], rsi
0x180024bab  push    rdi
0x180024bac  sub     rsp, 90h
0x180024bb3  mov     rax, cs:__security_cookie
0x180024bba  xor     rax, rsp
0x180024bbd  mov     [rsp+98h+var_18], rax
0x180024bc5  mov     rbx, rdx
0x180024bc8  mov     qword ptr [r11-68h], 40h ; '@'
0x180024bd0  lea     rax, [r11-58h]
0x180024bd4  xor     esi, esi
0x180024bd6  lea     r9, [r11-68h]; pcbData
0x180024bda  mov     [r11-60h], rax
0x180024bde  lea     r8, [r11-58h]; pvData
0x180024be2  lea     edx, [rsi+0Fh]; dwPropId
0x180024be5  call    cs:__imp_CertGetCertificateContextProperty
0x180024beb  test    eax, eax
0x180024bed  jz      loc_180024C7E
0x180024bf3  mov     r9d, 2C000h; dwFlags
0x180024bf9  mov     [rsp+98h+pvPara], rbx; pvPara
0x180024bfe  xor     r8d, r8d; hCryptProv
0x180024c01  lea     ecx, [rsi+0Ah]; lpszStoreProvider
0x180024c04  xor     edx, edx; dwEncodingType
0x180024c06  call    cs:__imp_CertOpenStore
0x180024c0c  mov     rdi, rax
0x180024c0f  test    rax, rax
0x180024c12  jz      short loc_180024C6F
0x180024c14  lea     rax, [rsp+98h+pvFindPara]
0x180024c19  mov     [rsp+98h+pPrevCertContext], rsi; pPrevCertContext
0x180024c1e  mov     r9d, 0E0000h; dwFindType
0x180024c24  mov     [rsp+98h+pvPara], rax; pvFindPara
0x180024c29  xor     r8d, r8d; dwFindFlags
0x180024c2c  xor     edx, edx; dwCertEncodingType
0x180024c2e  mov     rcx, rdi; hCertStore
0x180024c31  call    cs:__imp_CertFindCertificateInStore
0x180024c37  test    rax, rax
0x180024c3a  jz      short loc_180024C4C
0x180024c3c  mov     rcx, rax; pCertContext
0x180024c3f  mov     esi, 1
0x180024c44  call    cs:__imp_CertFreeCertificateContext
0x180024c4a  jmp     short loc_180024C62
0x180024c4c  mov     r8, rbx
0x180024c4f  lea     rdx, aCertificateIsN; "Certificate is not in the %ws store!"
0x180024c56  lea     rcx, aIscertificatei; "IsCertificateInStore"
0x180024c5d  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180024c62  xor     edx, edx; dwFlags
0x180024c64  mov     rcx, rdi; hCertStore
0x180024c67  call    cs:__imp_CertCloseStore
0x180024c6d  jmp     short loc_180024C9D
0x180024c6f  call    cs:__imp_GetLastError
0x180024c75  lea     rdx, aCertopenstoreF; "CertOpenStore for %ws failed! Error %d"
0x180024c7c  jmp     short loc_180024C8B
0x180024c7e  call    cs:__imp_GetLastError
0x180024c84  lea     rdx, aCertgetcertifi; "CertGetCertificateContextProperty for %"...
0x180024c8b  mov     r9d, eax
0x180024c8e  lea     rcx, aIscertificatei; "IsCertificateInStore"
0x180024c95  mov     r8, rbx
0x180024c98  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180024c9d  mov     eax, esi
0x180024c9f  mov     rcx, [rsp+98h+var_18]
0x180024ca7  xor     rcx, rsp; StackCookie
0x180024caa  call    __security_check_cookie
0x180024caf  lea     r11, [rsp+98h+var_8]
0x180024cb7  mov     rbx, [r11+20h]
0x180024cbb  mov     rsi, [r11+28h]
0x180024cbf  mov     rsp, r11
0x180024cc2  pop     rdi
0x180024cc3  retn
```
