# RegistrationCertHelper::DeleteCertificate(_CERTFICATE_LOCATION,_CERT_CONTEXT const *)

- ea: `0x18005c780`
- end: `0x18005c955`
- name: `?DeleteCertificate@RegistrationCertHelper@@SAJW4_CERTFICATE_LOCATION@@PEBU_CERT_CONTEXT@@@Z`
- size: `469`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x1800543ec`
- `0x180059e74`
- `0x18005d5bc`

## callees

- `0x1800084f4`
- `0x180008530`
- `0x18000bac0`
- `0x180017fd0`
- `0x18001b2a0`
- `0x18003b434`
- `0x180043ef8`
- `0x18005c780`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c812`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c8c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c928`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c812`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c8c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c928`
- `CRYPT32!CertOpenStore` at `0x18005c804`
- `CRYPT32!CertOpenStore` at `0x18005c804`
- `CRYPT32!CertFindCertificateInStore` at `0x18005c84d`
- `CRYPT32!CertFindCertificateInStore` at `0x18005c84d`
- `CRYPT32!CertCloseStore` at `0x18005c91e`
- `CRYPT32!CertCloseStore` at `0x18005c91e`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x18005c8bc`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x18005c8bc`
- `CRYPT32!CertFreeCertificateContext` at `0x18005c90e`
- `CRYPT32!CertFreeCertificateContext` at `0x18005c90e`

## string_xrefs

- `0x18005c81e`: `CertOpenStore`
- `0x18005c8ad`: `RegistrationCertHelper::DeletePrivateKeyByCertificate`
- `0x18005c7bc`: `RegistrationCertHelper::DeleteCertificate`
- `0x18005c8d2`: `CertDeleteCertificateFromStore`

## pseudocode

```c
__int64 __fastcall RegistrationCertHelper::DeleteCertificate(int a1, const CERT_CONTEXT *a2)
{
  int v2; // edi
  const CERT_CONTEXT *v3; // rsi
  int v4; // ebp
  int CertificateThumbprintBytes; // eax
  unsigned int v6; // ebx
  HCERTSTORE v7; // rbp
  const wchar_t *v8; // r8
  DWORD LastError; // eax
  const wchar_t *v10; // r8
  const CERT_CONTEXT *CertificateInStore; // rax
  void *v12; // rbx
  const wchar_t *v13; // r8
  DWORD v14; // eax
  _OWORD pvFindPara[2]; // [rsp+30h] [rbp-28h] BYREF
  void *Block; // [rsp+70h] [rbp+18h] BYREF

  v2 = 0;
  v3 = 0;
  v4 = a1 != 0 ? 0x10000 : 0;
  pvFindPara[0] = 0;
  CertificateThumbprintBytes = CertificateUtil::GetCertificateThumbprintBytes(
                                 a2,
                                 (unsigned __int8 **)pvFindPara + 1,
                                 (unsigned int *)pvFindPara);
  v6 = CertificateThumbprintBytes;
  if ( CertificateThumbprintBytes >= 0 )
  {
    v7 = CertOpenStore((LPCSTR)0xA, 0, 0, v4 + 0x10000, L"My");
    if ( v7 || (LastError = GetLastError(), (v2 = LastError) == 0) )
    {
      CertificateInStore = CertFindCertificateInStore(v7, 0x10001u, 0, 0x10000u, pvFindPara, 0);
      v3 = CertificateInStore;
      if ( !CertificateInStore )
        goto LABEL_18;
      Block = 0;
      CertificateUtil::GetCertificateThumbprint(CertificateInStore, (unsigned __int16 **)&Block);
      v12 = Block;
      v13 = L"N/A";
      if ( Block )
        v13 = (const wchar_t *)Block;
      Logger::TraceVerbose(
        (wchar_t *)L"%s: Deleting certificate with thumbprint %s...",
        L"RegistrationCertHelper::DeleteCertificate",
        v13);
      operator delete(v12);
      CertificateThumbprintBytes = RegistrationCertHelper::DeletePrivateKeyByCertificate(v3);
      v6 = CertificateThumbprintBytes;
      if ( CertificateThumbprintBytes < 0 )
      {
        v8 = L"RegistrationCertHelper::DeletePrivateKeyByCertificate";
        goto LABEL_3;
      }
      if ( CertDeleteCertificateFromStore(v3) || (LastError = GetLastError(), (v2 = LastError) == 0) )
      {
        v3 = 0;
        goto LABEL_18;
      }
      v10 = L"CertDeleteCertificateFromStore";
    }
    else
    {
      v10 = L"CertOpenStore";
    }
    Logger::TraceError(
      L"%s: %s failed with win32 error code: 0x%08x.",
      L"RegistrationCertHelper::DeleteCertificate",
      v10,
      LastError);
    goto LABEL_18;
  }
  v7 = 0;
  v8 = L"CertificateUtil::GetCertificateThumbprintBytes";
LABEL_3:
  Logger::TraceError(
    L"%s: %s failed with error code: 0x%08x.",
    L"RegistrationCertHelper::DeleteCertificate",
    v8,
    (unsigned int)CertificateThumbprintBytes);
LABEL_18:
  operator delete(*((void **)&pvFindPara[0] + 1));
  *((_QWORD *)&pvFindPara[0] + 1) = 0;
  if ( v2 )
  {
    if ( v2 > 0 )
      v6 = (unsigned __int16)v2 | 0x80070000;
    else
      v6 = v2;
  }
  if ( v3 )
    CertFreeCertificateContext(v3);
  if ( v7 && !CertCloseStore(v7, 0) )
  {
    v14 = GetLastError();
    Logger::TraceWarning(
      (wchar_t *)L"%s: CertCloseStore failed with error code: 0x%08x. Igored.",
      L"RegistrationCertHelper::DeleteCertificate",
      v14);
  }
  return v6;
}

```

## disassembly

```asm
0x18005c780  mov     r11, rsp
0x18005c783  mov     [r11+8], rbx
0x18005c787  mov     [r11+10h], rbp
0x18005c78b  push    rsi
0x18005c78c  push    rdi
0x18005c78d  push    r15
0x18005c78f  sub     rsp, 40h
0x18005c793  mov     rax, rdx
0x18005c796  lea     r8, [r11-28h]; unsigned int *
0x18005c79a  xorps   xmm0, xmm0
0x18005c79d  lea     rdx, [r11-20h]; unsigned __int8 **
0x18005c7a1  xor     edi, edi
0x18005c7a3  xor     esi, esi
0x18005c7a5  neg     ecx
0x18005c7a7  mov     rcx, rax; pCertContext
0x18005c7aa  sbb     ebp, ebp
0x18005c7ac  and     ebp, 10000h
0x18005c7b2  movups  [rsp+58h+pvFindPara], xmm0
0x18005c7b7  call    ?GetCertificateThumbprintBytes@CertificateUtil@@SAJPEBU_CERT_CONTEXT@@PEAPEAEPEAK@Z; CertificateUtil::GetCertificateThumbprintBytes(_CERT_CONTEXT const *,uchar * *,ulong *)
0x18005c7bc  lea     r15, aRegistrationce_4; "RegistrationCertHelper::DeleteCertifica"...
0x18005c7c3  mov     ebx, eax
0x18005c7c5  test    eax, eax
0x18005c7c7  jns     short loc_18005C7E9
0x18005c7c9  xor     ebp, ebp
0x18005c7cb  lea     r8, aCertificateuti_3; "CertificateUtil::GetCertificateThumbpri"...
0x18005c7d2  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18005c7d9  mov     r9d, eax
0x18005c7dc  mov     rdx, r15
0x18005c7df  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005c7e4  jmp     loc_18005C8E0
0x18005c7e9  xor     edx, edx; dwEncodingType
0x18005c7eb  lea     rax, aMy; "My"
0x18005c7f2  lea     r9d, [rbp+10000h]; dwFlags
0x18005c7f9  mov     [rsp+58h+pvPara], rax; pvPara
0x18005c7fe  xor     r8d, r8d; hCryptProv
0x18005c801  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x18005c804  call    cs:__imp_CertOpenStore
0x18005c80a  mov     rbp, rax
0x18005c80d  test    rax, rax
0x18005c810  jnz     short loc_18005C82E
0x18005c812  call    cs:__imp_GetLastError
0x18005c818  mov     edi, eax
0x18005c81a  test    eax, eax
0x18005c81c  jz      short loc_18005C82E
0x18005c81e  lea     r8, aCertopenstore_0; "CertOpenStore"
0x18005c825  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x18005c82c  jmp     short loc_18005C7D9
0x18005c82e  mov     r9d, 10000h; dwFindType
0x18005c834  mov     [rsp+58h+pPrevCertContext], rsi; pPrevCertContext
0x18005c839  lea     rax, [rsp+58h+pvFindPara]
0x18005c83e  xor     r8d, r8d; dwFindFlags
0x18005c841  mov     rcx, rbp; hCertStore
0x18005c844  mov     [rsp+58h+pvPara], rax; pvFindPara
0x18005c849  lea     edx, [r9+1]; dwCertEncodingType
0x18005c84d  call    cs:__imp_CertFindCertificateInStore
0x18005c853  mov     rsi, rax
0x18005c856  test    rax, rax
0x18005c859  jz      loc_18005C8E0
0x18005c85f  lea     rdx, [rsp+58h+Block]; unsigned __int16 **
0x18005c864  mov     [rsp+58h+Block], 0
0x18005c86d  mov     rcx, rax; pCertContext
0x18005c870  call    ?GetCertificateThumbprint@CertificateUtil@@SAJPEBU_CERT_CONTEXT@@PEAPEAG@Z; CertificateUtil::GetCertificateThumbprint(_CERT_CONTEXT const *,ushort * *)
0x18005c875  mov     rbx, [rsp+58h+Block]
0x18005c87a  lea     r8, aNA; "N/A"
0x18005c881  test    rbx, rbx
0x18005c884  lea     rcx, aSDeletingCerti_0; "%s: Deleting certificate with thumbprin"...
0x18005c88b  mov     rdx, r15
0x18005c88e  cmovnz  r8, rbx
0x18005c892  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18005c897  mov     rcx, rbx; Block
0x18005c89a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005c89f  mov     rcx, rsi; pCert
0x18005c8a2  call    ?DeletePrivateKeyByCertificate@RegistrationCertHelper@@CAJPEBU_CERT_CONTEXT@@@Z; RegistrationCertHelper::DeletePrivateKeyByCertificate(_CERT_CONTEXT const *)
0x18005c8a7  mov     ebx, eax
0x18005c8a9  test    eax, eax
0x18005c8ab  jns     short loc_18005C8B9
0x18005c8ad  lea     r8, aRegistrationce_0; "RegistrationCertHelper::DeletePrivateKe"...
0x18005c8b4  jmp     loc_18005C7D2
0x18005c8b9  mov     rcx, rsi; pCertContext
0x18005c8bc  call    cs:__imp_CertDeleteCertificateFromStore
0x18005c8c2  test    eax, eax
0x18005c8c4  jnz     short loc_18005C8DE
0x18005c8c6  call    cs:__imp_GetLastError
0x18005c8cc  mov     edi, eax
0x18005c8ce  test    eax, eax
0x18005c8d0  jz      short loc_18005C8DE
0x18005c8d2  lea     r8, aCertdeletecert_0; "CertDeleteCertificateFromStore"
0x18005c8d9  jmp     loc_18005C825
0x18005c8de  xor     esi, esi
0x18005c8e0  mov     rcx, qword ptr [rsp+58h+pvFindPara+8]; Block
0x18005c8e5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005c8ea  mov     qword ptr [rsp+58h+pvFindPara+8], 0
0x18005c8f3  test    edi, edi
0x18005c8f5  jz      short loc_18005C906
0x18005c8f7  jg      short loc_18005C8FD
0x18005c8f9  mov     ebx, edi
0x18005c8fb  jmp     short loc_18005C906
0x18005c8fd  movzx   ebx, di
0x18005c900  or      ebx, 80070000h
0x18005c906  test    rsi, rsi
0x18005c909  jz      short loc_18005C914
0x18005c90b  mov     rcx, rsi; pCertContext
0x18005c90e  call    cs:__imp_CertFreeCertificateContext
0x18005c914  test    rbp, rbp
0x18005c917  jz      short loc_18005C940
0x18005c919  xor     edx, edx; dwFlags
0x18005c91b  mov     rcx, rbp; hCertStore
0x18005c91e  call    cs:__imp_CertCloseStore
0x18005c924  test    eax, eax
0x18005c926  jnz     short loc_18005C940
0x18005c928  call    cs:__imp_GetLastError
0x18005c92e  mov     rdx, r15
0x18005c931  lea     rcx, aSCertclosestor; "%s: CertCloseStore failed with error co"...
0x18005c938  mov     r8d, eax
0x18005c93b  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18005c940  mov     rbp, [rsp+58h+arg_8]
0x18005c945  mov     eax, ebx
0x18005c947  mov     rbx, [rsp+58h+arg_0]
0x18005c94c  add     rsp, 40h
0x18005c950  pop     r15
0x18005c952  pop     rdi
0x18005c953  pop     rsi
0x18005c954  retn
```
