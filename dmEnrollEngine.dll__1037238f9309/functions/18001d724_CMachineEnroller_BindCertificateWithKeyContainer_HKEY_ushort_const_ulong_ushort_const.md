# CMachineEnroller::BindCertificateWithKeyContainer(HKEY__ *,ushort const *,ulong,ushort const *)

- ea: `0x18001d724`
- end: `0x18001dc46`
- name: `?BindCertificateWithKeyContainer@CMachineEnroller@@CAJPEAUHKEY__@@PEBGK1@Z`
- size: `1314`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, char, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004f260`

## callees

- `0x1800140d0`
- `0x180014148`
- `0x18001b308`
- `0x18001d724`
- `0x1800206a8`
- `0x18002e1a0`
- `0x18002ec8c`
- `0x18004e07c`
- `0x180056764`
- `0x180056824`
- `0x18006fdd8`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18001d8db`
- `ntdll!RtlNtStatusToDosError` at `0x18001d972`
- `ntdll!RtlNtStatusToDosError` at `0x18001d8db`
- `ntdll!RtlNtStatusToDosError` at `0x18001d972`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d9fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dac2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001db20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001db55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d9fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dac2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001db20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001db55`
- `CRYPT32!CertCloseStore` at `0x18001db46`
- `CRYPT32!CertCloseStore` at `0x18001db9f`
- `CRYPT32!CertCloseStore` at `0x18001db46`
- `CRYPT32!CertCloseStore` at `0x18001db9f`
- `CRYPT32!CertFreeCertificateContext` at `0x18001db8d`
- `CRYPT32!CertFreeCertificateContext` at `0x18001db8d`
- `CRYPT32!CryptExportPublicKeyInfoEx` at `0x18001d9f2`
- `CRYPT32!CryptExportPublicKeyInfoEx` at `0x18001da6a`
- `CRYPT32!CryptExportPublicKeyInfoEx` at `0x18001d9f2`
- `CRYPT32!CryptExportPublicKeyInfoEx` at `0x18001da6a`
- `CRYPT32!CertComparePublicKeyInfo` at `0x18001da89`
- `CRYPT32!CertComparePublicKeyInfo` at `0x18001da89`
- `CRYPT32!CertSetCertificateContextProperty` at `0x18001dab8`
- `CRYPT32!CertSetCertificateContextProperty` at `0x18001dab8`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18001db16`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18001db16`
- `ncrypt!NCryptFreeObject` at `0x18001dbaf`
- `ncrypt!NCryptFreeObject` at `0x18001dbbf`
- `ncrypt!NCryptFreeObject` at `0x18001dc0e`
- `ncrypt!NCryptFreeObject` at `0x18001dbaf`
- `ncrypt!NCryptFreeObject` at `0x18001dbbf`
- `ncrypt!NCryptFreeObject` at `0x18001dc0e`
- `ncrypt!NCryptOpenKey` at `0x18001d94c`
- `ncrypt!NCryptOpenKey` at `0x18001d94c`
- `ncrypt!NCryptOpenStorageProvider` at `0x18001d8b5`
- `ncrypt!NCryptOpenStorageProvider` at `0x18001d8b5`
- `CRYPTSP!CryptReleaseContext` at `0x18001dc18`
- `CRYPTSP!CryptReleaseContext` at `0x18001dc18`

## string_xrefs

- `0x18001d9ac`: `NCryptOpenKey`
- `0x18001d915`: `NCryptOpenStorageProvider`
- `0x18001d928`: `BindCertificateWithKeyContainer:NCryptOpenStorageProvider`
- `0x18001d89d`: `BindCertificateWithKeyContainer:GetInstalledCert`
- `0x18001d9bf`: `BindCertificateWithKeyContainer:NCryptOpenKey`
- `0x18001da9b`: `BindCertificateWithKeyContainer:CertComparePublicKeyInfo`

## pseudocode

```c
__int64 __fastcall CMachineEnroller::BindCertificateWithKeyContainer(
        HKEY a1,
        const unsigned __int16 *a2,
        char a3,
        const unsigned __int16 *a4)
{
  struct _CERT_PUBLIC_KEY_INFO *pInfo; // rdi
  DWORD dwFlags; // esi
  unsigned int v8; // r8d
  const wchar_t *v9; // rbx
  unsigned int v10; // r9d
  int InstalledCert; // eax
  SECURITY_STATUS v12; // eax
  int v13; // ecx
  SECURITY_STATUS v14; // ebx
  int v15; // eax
  SECURITY_STATUS v16; // eax
  int v17; // ecx
  SECURITY_STATUS v18; // ebx
  int v19; // eax
  signed int v20; // eax
  signed int v21; // eax
  int v22; // ecx
  signed int v23; // eax
  BOOL v24; // eax
  signed int LastError; // eax
  __int64 v26; // rdx
  NCRYPT_PROV_HANDLE v27; // rcx
  unsigned int v28; // edi
  int NewKeyContainer; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbInfo; // [rsp+44h] [rbp-BCh] BYREF
  int v32; // [rsp+48h] [rbp-B8h] BYREF
  int v33; // [rsp+4Ch] [rbp-B4h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+50h] [rbp-B0h] BYREF
  HCERTSTORE hCertStore; // [rsp+58h] [rbp-A8h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+60h] [rbp-A0h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+68h] [rbp-98h] BYREF
  NCRYPT_HANDLE hObject; // [rsp+70h] [rbp-90h] BYREF
  _OWORD pvData[3]; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v40[5]; // [rsp+A8h] [rbp-58h] BYREF
  char v41; // [rsp+D0h] [rbp-30h]
  WCHAR pszProviderName[256]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR pszKeyName[256]; // [rsp+2E0h] [rbp+1E0h] BYREF

  NewKeyContainer = 0;
  hCertStore = 0;
  pCertContext = 0;
  phProvider = 0;
  phKey = 0;
  pcbInfo = 0;
  pInfo = 0;
  dwFlags = 8 * (a3 & 4 | 8);
  memset(pvData, 0, sizeof(pvData));
  hObject = 0;
  v33 = 0;
  v32 = 1;
  v40[2] = &hObject;
  v40[3] = &v32;
  v40[4] = &v33;
  v41 = 1;
  v40[0] = "CMachineEnroller::BindCertificateWithKeyContainer";
  v40[1] = &NewKeyContainer;
  memset_0(pszKeyName, 0, sizeof(pszKeyName));
  NewKeyContainer = GetNewKeyContainer(a1, pszKeyName, v8);
  if ( NewKeyContainer < 0 )
  {
    v9 = L"BindCertificateWithKeyContainer:GetNewKeyContainer";
    goto LABEL_59;
  }
  memset_0(pszProviderName, 0, sizeof(pszProviderName));
  NewKeyContainer = GetCryptoProvider(a1, 0, pszProviderName, v10);
  if ( NewKeyContainer < 0 )
  {
    v9 = L"BindCertificateWithKeyContainer:GetCryptoProvider";
    goto LABEL_59;
  }
  memset((char *)&pvData[1] + 8, 0, 24);
  *(_QWORD *)&pvData[0] = pszKeyName;
  *((_QWORD *)&pvData[0] + 1) = pszProviderName;
  LODWORD(pvData[1]) = 0;
  DWORD1(pvData[1]) = dwFlags;
  InstalledCert = GetInstalledCert(a2, &hCertStore, &pCertContext, 0, 0);
  NewKeyContainer = InstalledCert;
  if ( InstalledCert >= 0 )
  {
    v12 = NCryptOpenStorageProvider(&phProvider, pszProviderName, 0);
    v14 = v12;
    if ( v12 )
    {
      if ( v12 < 0 )
      {
        if ( v12 == -1073741559 )
        {
          v15 = -2147024579;
        }
        else
        {
          v15 = RtlNtStatusToDosError(v12);
          if ( !v15 || v15 == 317 )
          {
            v15 = v14 | 0x10000000;
          }
          else if ( v15 > 0 )
          {
            v15 = (unsigned __int16)v15 | 0x80070000;
          }
        }
      }
      else
      {
        v15 = 0;
      }
      NewKeyContainer = v15;
      if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 4) != 0 )
        McTemplateU0zzd_EventWriteTransfer(
          v13,
          (unsigned int)EnterpriseDiagnosticsBindKeyFailure,
          (unsigned int)L"NCryptOpenStorageProvider",
          (unsigned int)pszProviderName,
          v15);
      v9 = L"BindCertificateWithKeyContainer:NCryptOpenStorageProvider";
    }
    else
    {
      v16 = NCryptOpenKey(phProvider, &phKey, pszKeyName, 0, dwFlags);
      v18 = v16;
      if ( v16 )
      {
        if ( v16 < 0 )
        {
          if ( v16 == -1073741559 )
          {
            v19 = -2147024579;
          }
          else
          {
            v19 = RtlNtStatusToDosError(v16);
            if ( !v19 || v19 == 317 )
            {
              v19 = v18 | 0x10000000;
            }
            else if ( v19 > 0 )
            {
              v19 = (unsigned __int16)v19 | 0x80070000;
            }
          }
        }
        else
        {
          v19 = 0;
        }
        NewKeyContainer = v19;
        if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 4) != 0 )
          McTemplateU0zzd_EventWriteTransfer(
            v17,
            (unsigned int)EnterpriseDiagnosticsBindKeyFailure,
            (unsigned int)L"NCryptOpenKey",
            (unsigned int)pszProviderName,
            v19);
        v9 = L"BindCertificateWithKeyContainer:NCryptOpenKey";
      }
      else
      {
        if ( !CryptExportPublicKeyInfoEx(phKey, 0, 1u, 0, 0, 0, 0, &pcbInfo) )
          goto LABEL_36;
        pInfo = (struct _CERT_PUBLIC_KEY_INFO *)SafeHeapAlloc(pcbInfo);
        if ( !pInfo )
        {
          NewKeyContainer = -2147024882;
          v9 = L"BindCertificateWithKeyContainer:not enough memory for public key";
          goto LABEL_59;
        }
        if ( CryptExportPublicKeyInfoEx(phKey, 0, 1u, 0, 0, 0, pInfo, &pcbInfo) )
        {
          if ( CertComparePublicKeyInfo(0x10001u, &pCertContext->pCertInfo->SubjectPublicKeyInfo, pInfo) )
          {
            if ( CertSetCertificateContextProperty(pCertContext, 2u, 0, pvData) )
            {
              if ( CertAddCertificateContextToStore(hCertStore, pCertContext, 5u, 0) )
              {
                v24 = CertCloseStore(hCertStore, 0);
                hCertStore = 0;
                if ( v24 )
                {
                  v9 = &wszURI;
                }
                else
                {
                  LastError = GetLastError();
                  if ( LastError > 0 )
                    LastError = (unsigned __int16)LastError | 0x80070000;
                  NewKeyContainer = LastError;
                  v9 = L"BindCertificateWithKeyContainer:CertCloseStore";
                }
              }
              else
              {
                v23 = GetLastError();
                if ( v23 > 0 )
                  v23 = (unsigned __int16)v23 | 0x80070000;
                NewKeyContainer = v23;
                v9 = L"BindCertificateWithKeyContainer:CertAddCertificateContextToStore";
              }
            }
            else
            {
              v21 = GetLastError();
              if ( v21 > 0 )
                v21 = (unsigned __int16)v21 | 0x80070000;
              NewKeyContainer = v21;
              if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 4) != 0 )
                McTemplateU0zzd_EventWriteTransfer(
                  v22,
                  (unsigned int)EnterpriseDiagnosticsBindKeyFailure,
                  (unsigned int)L"CertSetCertificateContextProperty",
                  (unsigned int)pszProviderName,
                  v21);
              v9 = L"BindCertificateWithKeyContainer:CertSetCertificateContextProperty";
            }
          }
          else
          {
            NewKeyContainer = -2146893803;
            v9 = L"BindCertificateWithKeyContainer:CertComparePublicKeyInfo";
          }
        }
        else
        {
LABEL_36:
          v20 = GetLastError();
          if ( v20 > 0 )
            v20 = (unsigned __int16)v20 | 0x80070000;
          NewKeyContainer = v20;
          v9 = L"BindCertificateWithKeyContainer:CryptExportPublicKeyInfoEx";
        }
      }
    }
  }
  else
  {
    if ( InstalledCert == -2146885628 )
      NewKeyContainer = -2145910748;
    v9 = L"BindCertificateWithKeyContainer:GetInstalledCert";
  }
LABEL_59:
  SafeHeapFree(pInfo);
  if ( pCertContext )
    CertFreeCertificateContext(pCertContext);
  if ( hCertStore )
    CertCloseStore(hCertStore, 0);
  if ( phKey )
    NCryptFreeObject(phKey);
  v27 = phProvider;
  if ( phProvider )
    NCryptFreeObject(phProvider);
  v28 = NewKeyContainer;
  if ( NewKeyContainer < 0 && (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
  {
    McTemplateU0zd_EventWriteTransfer(
      v27,
      EnterpriseDiagnosticsEnrollFixupCertsFailure,
      v9,
      (unsigned int)NewKeyContainer);
    v28 = NewKeyContainer;
  }
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v40, v26);
  if ( hObject && v32 )
  {
    if ( v33 == -1 )
      NCryptFreeObject(hObject);
    else
      CryptReleaseContext(hObject, 0);
  }
  return v28;
}

```

## disassembly

```asm
0x18001d724  mov     [rsp-8+arg_10], rbx
0x18001d729  push    rbp
0x18001d72a  push    rsi
0x18001d72b  push    rdi
0x18001d72c  push    r14
0x18001d72e  push    r15
0x18001d730  lea     rbp, [rsp-3F0h]
0x18001d738  sub     rsp, 4F0h
0x18001d73f  mov     rax, cs:__security_cookie
0x18001d746  xor     rax, rsp
0x18001d749  mov     [rbp+410h+var_30], rax
0x18001d750  mov     esi, r8d
0x18001d753  mov     r14, rdx
0x18001d756  mov     rbx, rcx
0x18001d759  xor     r15d, r15d
0x18001d75c  mov     [rsp+510h+var_4D0], r15d
0x18001d761  mov     [rsp+510h+hCertStore], r15
0x18001d766  mov     [rsp+510h+pCertContext], r15
0x18001d76b  mov     [rsp+510h+phProvider], r15
0x18001d770  mov     [rsp+510h+phKey], r15
0x18001d775  mov     [rsp+510h+var_4CC], r15d
0x18001d77a  mov     edi, r15d
0x18001d77d  and     esi, 4
0x18001d780  or      esi, 8
0x18001d783  shl     esi, 3
0x18001d786  xorps   xmm0, xmm0
0x18001d789  movups  [rsp+510h+pvData], xmm0
0x18001d78e  movups  [rbp+410h+var_488], xmm0
0x18001d792  movups  [rbp+410h+var_478], xmm0
0x18001d796  mov     [rsp+510h+hObject], r15
0x18001d79b  mov     [rsp+510h+var_4C4], r15d
0x18001d7a0  mov     [rsp+510h+var_4C8], 1
0x18001d7a8  lea     rax, [rsp+510h+hObject]
0x18001d7ad  mov     [rbp+410h+var_458], rax
0x18001d7b1  lea     rax, [rsp+510h+var_4C8]
0x18001d7b6  mov     [rbp+410h+var_450], rax
0x18001d7ba  lea     rax, [rsp+510h+var_4C4]
0x18001d7bf  mov     [rbp+410h+var_448], rax
0x18001d7c3  mov     [rbp+410h+var_440], 1
0x18001d7c7  lea     rax, aCmachineenroll_11; "CMachineEnroller::BindCertificateWithKe"...
0x18001d7ce  mov     [rbp+410h+var_468], rax
0x18001d7d2  lea     rax, [rsp+510h+var_4D0]
0x18001d7d7  mov     [rbp+410h+var_460], rax
0x18001d7db  xor     edx, edx; Val
0x18001d7dd  mov     r8d, 200h; Size
0x18001d7e3  lea     rcx, [rbp+410h+pszKeyName]; void *
0x18001d7ea  call    memset_0
0x18001d7ef  lea     rdx, [rbp+410h+pszKeyName]; unsigned __int16 *
0x18001d7f6  mov     rcx, rbx; HKEY
0x18001d7f9  call    ?GetNewKeyContainer@@YAJPEAUHKEY__@@PEAGK@Z; GetNewKeyContainer(HKEY__ *,ushort *,ulong)
0x18001d7fe  mov     [rsp+510h+var_4D0], eax
0x18001d802  test    eax, eax
0x18001d804  jns     short loc_18001D812
0x18001d806  lea     rbx, aBindcertificat_6; "BindCertificateWithKeyContainer:GetNewK"...
0x18001d80d  jmp     loc_18001DB7B
0x18001d812  xor     edx, edx; Val
0x18001d814  mov     r8d, 200h; Size
0x18001d81a  lea     rcx, [rbp+410h+pszProviderName]; void *
0x18001d81e  call    memset_0
0x18001d823  lea     r8, [rbp+410h+pszProviderName]; unsigned __int16 *
0x18001d827  xor     edx, edx; bool
0x18001d829  mov     rcx, rbx; HKEY
0x18001d82c  call    ?GetCryptoProvider@@YAJPEAUHKEY__@@_NPEAGK@Z; GetCryptoProvider(HKEY__ *,bool,ushort *,ulong)
0x18001d831  mov     [rsp+510h+var_4D0], eax
0x18001d835  test    eax, eax
0x18001d837  jns     short loc_18001D845
0x18001d839  lea     rbx, aBindcertificat_7; "BindCertificateWithKeyContainer:GetCryp"...
0x18001d840  jmp     loc_18001DB7B
0x18001d845  xorps   xmm0, xmm0
0x18001d848  movdqu  [rbp+410h+var_488+8], xmm0
0x18001d84d  mov     qword ptr [rbp+410h+var_478+8], r15
0x18001d851  lea     rax, [rbp+410h+pszKeyName]
0x18001d858  mov     qword ptr [rsp+510h+pvData], rax
0x18001d85d  lea     rax, [rbp+410h+pszProviderName]
0x18001d861  mov     qword ptr [rbp+410h+pvData+8], rax
0x18001d865  mov     dword ptr [rbp+410h+var_488], r15d
0x18001d869  mov     dword ptr [rbp+410h+var_488+4], esi
0x18001d86c  mov     qword ptr [rsp+510h+dwFlags], r15; unsigned int *
0x18001d871  xor     r9d, r9d; int
0x18001d874  lea     r8, [rsp+510h+pCertContext]; struct _CERT_CONTEXT **
0x18001d879  lea     rdx, [rsp+510h+hCertStore]; void **
0x18001d87e  mov     rcx, r14; unsigned __int16 *
0x18001d881  call    ?GetInstalledCert@@YAJPEBGPEAPEAXPEAPEBU_CERT_CONTEXT@@HPEAK@Z; GetInstalledCert(ushort const *,void * *,_CERT_CONTEXT const * *,int,ulong *)
0x18001d886  mov     [rsp+510h+var_4D0], eax
0x18001d88a  test    eax, eax
0x18001d88c  jns     short loc_18001D8A9
0x18001d88e  cmp     eax, 80092004h
0x18001d893  jnz     short loc_18001D89D
0x18001d895  mov     [rsp+510h+var_4D0], 80180024h
0x18001d89d  lea     rbx, aBindcertificat_10; "BindCertificateWithKeyContainer:GetInst"...
0x18001d8a4  jmp     loc_18001DB7B
0x18001d8a9  xor     r8d, r8d; dwFlags
0x18001d8ac  lea     rdx, [rbp+410h+pszProviderName]; pszProviderName
0x18001d8b0  lea     rcx, [rsp+510h+phProvider]; phProvider
0x18001d8b5  call    cs:__imp_NCryptOpenStorageProvider
0x18001d8bb  mov     ebx, eax
0x18001d8bd  test    eax, eax
0x18001d8bf  jz      short loc_18001D934
0x18001d8c1  test    eax, eax
0x18001d8c3  js      short loc_18001D8CA
0x18001d8c5  mov     eax, r15d
0x18001d8c8  jmp     short loc_18001D900
0x18001d8ca  cmp     ebx, 0C0000109h
0x18001d8d0  jnz     short loc_18001D8D9
0x18001d8d2  mov     eax, 8007013Dh
0x18001d8d7  jmp     short loc_18001D900
0x18001d8d9  mov     ecx, ebx; Status
0x18001d8db  call    cs:__imp_RtlNtStatusToDosError
0x18001d8e1  test    eax, eax
0x18001d8e3  jz      short loc_18001D8FA
0x18001d8e5  cmp     eax, 13Dh
0x18001d8ea  jz      short loc_18001D8FA
0x18001d8ec  test    eax, eax
0x18001d8ee  jle     short loc_18001D900
0x18001d8f0  movzx   eax, ax
0x18001d8f3  or      eax, 80070000h
0x18001d8f8  jmp     short loc_18001D900
0x18001d8fa  mov     eax, ebx
0x18001d8fc  bts     eax, 1Ch
0x18001d900  mov     [rsp+510h+var_4D0], eax
0x18001d904  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 4
0x18001d90b  jz      short loc_18001D928
0x18001d90d  mov     [rsp+510h+dwFlags], eax
0x18001d911  lea     r9, [rbp+410h+pszProviderName]
0x18001d915  lea     r8, aNcryptopenstor_0; "NCryptOpenStorageProvider"
0x18001d91c  lea     rdx, EnterpriseDiagnosticsBindKeyFailure
0x18001d923  call    McTemplateU0zzd_EventWriteTransfer
0x18001d928  lea     rbx, aBindcertificat_4; "BindCertificateWithKeyContainer:NCryptO"...
0x18001d92f  jmp     loc_18001DB7B
0x18001d934  mov     [rsp+510h+dwFlags], esi; dwFlags
0x18001d938  xor     r9d, r9d; dwLegacyKeySpec
0x18001d93b  lea     r8, [rbp+410h+pszKeyName]; pszKeyName
0x18001d942  lea     rdx, [rsp+510h+phKey]; phKey
0x18001d947  mov     rcx, [rsp+510h+phProvider]; hProvider
0x18001d94c  call    cs:__imp_NCryptOpenKey
0x18001d952  mov     ebx, eax
0x18001d954  test    eax, eax
0x18001d956  jz      short loc_18001D9CB
0x18001d958  test    eax, eax
0x18001d95a  js      short loc_18001D961
0x18001d95c  mov     eax, r15d
0x18001d95f  jmp     short loc_18001D997
0x18001d961  cmp     ebx, 0C0000109h
0x18001d967  jnz     short loc_18001D970
0x18001d969  mov     eax, 8007013Dh
0x18001d96e  jmp     short loc_18001D997
0x18001d970  mov     ecx, ebx; Status
0x18001d972  call    cs:__imp_RtlNtStatusToDosError
0x18001d978  test    eax, eax
0x18001d97a  jz      short loc_18001D991
0x18001d97c  cmp     eax, 13Dh
0x18001d981  jz      short loc_18001D991
0x18001d983  test    eax, eax
0x18001d985  jle     short loc_18001D997
0x18001d987  movzx   eax, ax
0x18001d98a  or      eax, 80070000h
0x18001d98f  jmp     short loc_18001D997
0x18001d991  mov     eax, ebx
0x18001d993  bts     eax, 1Ch
0x18001d997  mov     [rsp+510h+var_4D0], eax
0x18001d99b  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 4
0x18001d9a2  jz      short loc_18001D9BF
0x18001d9a4  mov     [rsp+510h+dwFlags], eax
0x18001d9a8  lea     r9, [rbp+410h+pszProviderName]
0x18001d9ac  lea     r8, aNcryptopenkey_0; "NCryptOpenKey"
0x18001d9b3  lea     rdx, EnterpriseDiagnosticsBindKeyFailure
0x18001d9ba  call    McTemplateU0zzd_EventWriteTransfer
0x18001d9bf  lea     rbx, aBindcertificat_2; "BindCertificateWithKeyContainer:NCryptO"...
0x18001d9c6  jmp     loc_18001DB7B
0x18001d9cb  lea     rax, [rsp+510h+var_4CC]
0x18001d9d0  mov     [rsp+510h+pcbInfo], rax; pcbInfo
0x18001d9d5  mov     [rsp+510h+pInfo], r15; pInfo
0x18001d9da  mov     [rsp+510h+pvAuxInfo], r15; pvAuxInfo
0x18001d9df  mov     [rsp+510h+dwFlags], r15d; dwFlags
0x18001d9e4  xor     r9d, r9d; pszPublicKeyObjId
0x18001d9e7  xor     edx, edx; dwKeySpec
0x18001d9e9  lea     r8d, [r9+1]; dwCertEncodingType
0x18001d9ed  mov     rcx, [rsp+510h+phKey]; hCryptProvOrNCryptKey
0x18001d9f2  call    cs:__imp_CryptExportPublicKeyInfoEx
0x18001d9f8  test    eax, eax
0x18001d9fa  jnz     short loc_18001DA1E
0x18001d9fc  call    cs:__imp_GetLastError
0x18001da02  test    eax, eax
0x18001da04  jle     short loc_18001DA0E
0x18001da06  movzx   eax, ax
0x18001da09  or      eax, 80070000h
0x18001da0e  mov     [rsp+510h+var_4D0], eax
0x18001da12  lea     rbx, aBindcertificat_5; "BindCertificateWithKeyContainer:CryptEx"...
0x18001da19  jmp     loc_18001DB7B
0x18001da1e  mov     ecx, [rsp+510h+var_4CC]; unsigned __int64
0x18001da22  call    ?SafeHeapAlloc@@YAPEAX_K@Z; SafeHeapAlloc(unsigned __int64)
0x18001da27  mov     rdi, rax
0x18001da2a  test    rax, rax
0x18001da2d  jnz     short loc_18001DA43
0x18001da2f  mov     [rsp+510h+var_4D0], 8007000Eh
0x18001da37  lea     rbx, aBindcertificat_9; "BindCertificateWithKeyContainer:not eno"...
0x18001da3e  jmp     loc_18001DB7B
0x18001da43  lea     rax, [rsp+510h+var_4CC]
0x18001da48  mov     [rsp+510h+pcbInfo], rax; pcbInfo
0x18001da4d  mov     [rsp+510h+pInfo], rdi; pInfo
0x18001da52  mov     [rsp+510h+pvAuxInfo], r15; pvAuxInfo
0x18001da57  mov     [rsp+510h+dwFlags], r15d; dwFlags
0x18001da5c  xor     r9d, r9d; pszPublicKeyObjId
0x18001da5f  xor     edx, edx; dwKeySpec
0x18001da61  lea     r8d, [r9+1]; dwCertEncodingType
0x18001da65  mov     rcx, [rsp+510h+phKey]; hCryptProvOrNCryptKey
0x18001da6a  call    cs:__imp_CryptExportPublicKeyInfoEx
0x18001da70  test    eax, eax
0x18001da72  jz      short loc_18001D9FC
0x18001da74  mov     rax, [rsp+510h+pCertContext]
0x18001da79  mov     rdx, [rax+18h]
0x18001da7d  add     rdx, 60h ; '`'; pPublicKey1
0x18001da81  mov     r8, rdi; pPublicKey2
0x18001da84  mov     ecx, 10001h; dwCertEncodingType
0x18001da89  call    cs:__imp_CertComparePublicKeyInfo
0x18001da8f  test    eax, eax
0x18001da91  jnz     short loc_18001DAA7
0x18001da93  mov     [rsp+510h+var_4D0], 80090015h
0x18001da9b  lea     rbx, aBindcertificat_3; "BindCertificateWithKeyContainer:CertCom"...
0x18001daa2  jmp     loc_18001DB7B
0x18001daa7  lea     r9, [rsp+510h+pvData]; pvData
0x18001daac  xor     r8d, r8d; dwFlags
0x18001daaf  lea     edx, [r8+2]; dwPropId
0x18001dab3  mov     rcx, [rsp+510h+pCertContext]; pCertContext
0x18001dab8  call    cs:__imp_CertSetCertificateContextProperty
0x18001dabe  test    eax, eax
0x18001dac0  jnz     short loc_18001DB05
0x18001dac2  call    cs:__imp_GetLastError
0x18001dac8  test    eax, eax
0x18001daca  jle     short loc_18001DAD4
0x18001dacc  movzx   eax, ax
0x18001dacf  or      eax, 80070000h
0x18001dad4  mov     [rsp+510h+var_4D0], eax
0x18001dad8  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 4
0x18001dadf  jz      short loc_18001DAFC
0x18001dae1  mov     [rsp+510h+dwFlags], eax
0x18001dae5  lea     r9, [rbp+410h+pszProviderName]
0x18001dae9  lea     r8, aCertsetcertifi_0; "CertSetCertificateContextProperty"
0x18001daf0  lea     rdx, EnterpriseDiagnosticsBindKeyFailure
0x18001daf7  call    McTemplateU0zzd_EventWriteTransfer
0x18001dafc  lea     rbx, aBindcertificat_8; "BindCertificateWithKeyContainer:CertSet"...
0x18001db03  jmp     short loc_18001DB7B
0x18001db05  xor     r9d, r9d; ppStoreContext
0x18001db08  lea     r8d, [r9+5]; dwAddDisposition
0x18001db0c  mov     rdx, [rsp+510h+pCertContext]; pCertContext
0x18001db11  mov     rcx, [rsp+510h+hCertStore]; hCertStore
0x18001db16  call    cs:__imp_CertAddCertificateContextToStore
0x18001db1c  test    eax, eax
0x18001db1e  jnz     short loc_18001DB3F
0x18001db20  call    cs:__imp_GetLastError
0x18001db26  test    eax, eax
0x18001db28  jle     short loc_18001DB32
0x18001db2a  movzx   eax, ax
0x18001db2d  or      eax, 80070000h
0x18001db32  mov     [rsp+510h+var_4D0], eax
0x18001db36  lea     rbx, aBindcertificat_0; "BindCertificateWithKeyContainer:CertAdd"...
0x18001db3d  jmp     short loc_18001DB7B
0x18001db3f  xor     edx, edx; dwFlags
0x18001db41  mov     rcx, [rsp+510h+hCertStore]; hCertStore
0x18001db46  call    cs:__imp_CertCloseStore
0x18001db4c  mov     [rsp+510h+hCertStore], r15
0x18001db51  test    eax, eax
0x18001db53  jnz     short loc_18001DB74
0x18001db55  call    cs:__imp_GetLastError
0x18001db5b  test    eax, eax
0x18001db5d  jle     short loc_18001DB67
0x18001db5f  movzx   eax, ax
0x18001db62  or      eax, 80070000h
0x18001db67  mov     [rsp+510h+var_4D0], eax
0x18001db6b  lea     rbx, aBindcertificat; "BindCertificateWithKeyContainer:CertClo"...
0x18001db72  jmp     short loc_18001DB7B
0x18001db74  lea     rbx, wszURI
0x18001db7b  mov     rcx, rdi; void *
0x18001db7e  call    ?SafeHeapFree@@YAHPEAX@Z; SafeHeapFree(void *)
0x18001db83  mov     rcx, [rsp+510h+pCertContext]; pCertContext
0x18001db88  test    rcx, rcx
0x18001db8b  jz      short loc_18001DB93
0x18001db8d  call    cs:__imp_CertFreeCertificateContext
0x18001db93  mov     rcx, [rsp+510h+hCertStore]; hCertStore
0x18001db98  test    rcx, rcx
0x18001db9b  jz      short loc_18001DBA5
0x18001db9d  xor     edx, edx; dwFlags
0x18001db9f  call    cs:__imp_CertCloseStore
0x18001dba5  mov     rcx, [rsp+510h+phKey]; hObject
0x18001dbaa  test    rcx, rcx
0x18001dbad  jz      short loc_18001DBB5
0x18001dbaf  call    cs:__imp_NCryptFreeObject
0x18001dbb5  mov     rcx, [rsp+510h+phProvider]; hObject
0x18001dbba  test    rcx, rcx
0x18001dbbd  jz      short loc_18001DBC5
0x18001dbbf  call    cs:__imp_NCryptFreeObject
0x18001dbc5  mov     edi, [rsp+510h+var_4D0]
0x18001dbc9  test    edi, edi
0x18001dbcb  jns     short loc_18001DBEC
0x18001dbcd  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x18001dbd4  jz      short loc_18001DBEC
0x18001dbd6  mov     r9d, edi
0x18001dbd9  mov     r8, rbx
0x18001dbdc  lea     rdx, EnterpriseDiagnosticsEnrollFixupCertsFailure
0x18001dbe3  call    McTemplateU0zd_EventWriteTransfer
  ... truncated ...
```
