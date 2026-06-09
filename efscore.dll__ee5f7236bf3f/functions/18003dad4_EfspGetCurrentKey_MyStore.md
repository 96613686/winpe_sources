# EfspGetCurrentKey_MyStore

- ea: `0x18003dad4`
- end: `0x18003df73`
- name: `EfspGetCurrentKey_MyStore`
- size: `1183`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x1800392a0`

## callees

- `0x180010bf0`
- `0x18001efb8`
- `0x180025cd0`
- `0x180035280`
- `0x180035f50`
- `0x180036d20`
- `0x180037000`
- `0x1800380f8`
- `0x180038138`
- `0x180038d14`
- `0x180038e38`
- `0x18003dad4`
- `0x180063600`
- `0x180063698`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dbf8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dd89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003de66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dbf8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dd89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003de66`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003df2b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003df2b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003db73`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003db73`
- `CRYPT32!CertOpenStore` at `0x18003dbe5`
- `CRYPT32!CertOpenStore` at `0x18003dbe5`
- `CRYPT32!CertFindCertificateInStore` at `0x18003dc82`
- `CRYPT32!CertFindCertificateInStore` at `0x18003dc82`
- `CRYPT32!CertCloseStore` at `0x18003df49`
- `CRYPT32!CertCloseStore` at `0x18003df49`
- `CRYPT32!CertFreeCertificateContext` at `0x18003df39`
- `CRYPT32!CertFreeCertificateContext` at `0x18003df39`
- `EFSUTIL!EfsUtilCheckCurrentKeyCapabilities` at `0x18003dcfc`
- `EFSUTIL!EfsUtilCheckCurrentKeyCapabilities` at `0x18003dcfc`
- `EFSUTIL!EfsUtilSetCurrentKey` at `0x18003dec0`
- `EFSUTIL!EfsUtilSetCurrentKey` at `0x18003dec0`

## pseudocode

```c
__int64 __fastcall EfspGetCurrentKey_MyStore(__int64 a1, __int64 *a2)
{
  void *CertHashFromCertContext; // r12
  const WCHAR *v3; // rdx
  PCCERT_CONTEXT CertificateInStore; // r15
  struct _EFS_ECC_SECONDARY_KEY *v5; // rsi
  DWORD LastError; // eax
  DWORD v7; // ebx
  HCERTSTORE v8; // r13
  char v9; // si
  int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rcx
  DWORD IsSmartcardCert; // eax
  __int64 v14; // rcx
  int v15; // r8d
  __int64 v16; // r9
  DWORD v17; // eax
  bool v18; // zf
  unsigned int SecondaryKeyInfo; // eax
  DWORD v20; // eax
  __int64 v21; // rdx
  unsigned int v22; // r8d
  char dwOptions; // [rsp+20h] [rbp-59h]
  DWORD pcbData; // [rsp+50h] [rbp-29h] BYREF
  DWORD dwDisposition; // [rsp+54h] [rbp-25h] BYREF
  __int64 v27; // [rsp+58h] [rbp-21h] BYREF
  struct _EFS_ECC_SECONDARY_KEY *v28; // [rsp+60h] [rbp-19h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-11h] BYREF
  const char *v30; // [rsp+70h] [rbp-9h] BYREF
  _QWORD pvFindPara[11]; // [rsp+78h] [rbp-1h] BYREF
  unsigned int v34; // [rsp+F0h] [rbp+77h] BYREF
  int v35; // [rsp+F8h] [rbp+7Fh] BYREF

  CertHashFromCertContext = 0;
  pvFindPara[0] = 1;
  hKey = 0;
  dwDisposition = 0;
  v30 = "1.3.6.1.4.1.311.10.3.4";
  v34 = 0;
  *a2 = 0;
  pvFindPara[1] = &v30;
  v3 = *(const WCHAR **)(a1 + 32);
  CertificateInStore = 0;
  pcbData = 0;
  v5 = 0;
  v27 = 0;
  v28 = 0;
  LastError = RegCreateKeyExW(HKEY_USERS, v3, 0, (LPWSTR)L"REG_SZ", 0, 1u, 0, &hKey, &dwDisposition);
  v7 = LastError;
  if ( LastError )
  {
    v8 = 0;
    v9 = -106;
LABEL_3:
    v10 = fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, LastError, 12, v9);
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v10, 12, v9);
    goto LABEL_49;
  }
  v8 = CertOpenStore((LPCSTR)0xD, 0, 0, 0x10000u, L"My");
  if ( !v8 )
  {
    v7 = 6006;
    LastError = GetLastError();
    v9 = -84;
    goto LABEL_3;
  }
  fnEfsLogTrace0(v11, EFS_KEY_OPERATION_BEGIN_SEARCH_MY_STORE, 12, 1199);
  while ( 1 )
  {
    if ( CertHashFromCertContext )
    {
      EfsFreeHeap(CertHashFromCertContext);
      CertHashFromCertContext = 0;
    }
    if ( v5 )
    {
      EfsEccReleaseSecondaryKeyInfo(v5);
      v5 = 0;
      v28 = 0;
    }
    if ( v27 )
    {
      EfsReleaseUserKeyInfo();
      v27 = 0;
    }
    v7 = 6006;
    CertificateInStore = CertFindCertificateInStore(v8, 1u, 0, 0xA0000u, pvFindPara, CertificateInStore);
    if ( !CertificateInStore )
      break;
    fnEfsLogTrace0(v12, EFS_KEY_OPERATION_FOUND_MATCH_MY_STORE, 12, 1238);
    v35 = 0;
    IsSmartcardCert = EfspIsSmartcardCert(CertificateInStore, &v35);
    if ( IsSmartcardCert )
    {
      dwOptions = -33;
      goto LABEL_16;
    }
    if ( v35 )
    {
      v16 = 1253;
      goto LABEL_19;
    }
    v17 = EfsUtilCheckCurrentKeyCapabilities(CertificateInStore, 393215, &v34);
    v7 = v17;
    if ( v17 )
    {
      fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v17, 12, 239);
      v18 = v7 == -2146892987;
LABEL_22:
      if ( v18 )
        break;
    }
    else if ( (unsigned int)EfspIsValidCurrentKey_Capabilities(v34) )
    {
      if ( (v34 & 0x80u) != 0 )
      {
        CertHashFromCertContext = (void *)GetCertHashFromCertContext(CertificateInStore, &pcbData);
        if ( !CertHashFromCertContext )
        {
          v7 = GetLastError();
          fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v7, 12, 22);
          v18 = v7 == 0;
          goto LABEL_22;
        }
        if ( (v34 & 0x1000) == 0 )
          goto LABEL_35;
        SecondaryKeyInfo = EfspEccGetSecondaryKeyInfo(HKEY_USERS, *(LPCWSTR *)(a1 + 32), CertificateInStore, 1, &v28);
        if ( !SecondaryKeyInfo )
        {
          v5 = v28;
LABEL_35:
          IsSmartcardCert = EfsObtainKeyInfo(CertificateInStore, (__int64)&v27);
          if ( IsSmartcardCert )
          {
            dwOptions = 56;
          }
          else
          {
            if ( !(unsigned int)EfsTryAddKeyInfoToCache(a1, &CertificateInStore->pCertInfo->NotAfter, &v27) )
            {
              v20 = GetLastError();
              fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v20, 12, 65);
            }
            if ( v5 && (IsSmartcardCert = EfspEccSaveSecondaryKeyInfo(HKEY_USERS, *(LPCWSTR *)(a1 + 32), v5)) != 0 )
            {
              dwOptions = 79;
            }
            else
            {
              IsSmartcardCert = EfsUtilSetCurrentKey(CertHashFromCertContext, pcbData, v34, *(_QWORD *)(a1 + 32));
              v7 = IsSmartcardCert;
              if ( !IsSmartcardCert )
              {
                v21 = v27;
                v22 = v34;
                v27 = 0;
                *a2 = v21;
                EfsPromoteToCurrentKey(a1, v21, v22, (_DWORD)CertificateInStore, (__int64)L"AddressBook");
                break;
              }
              dwOptions = 89;
            }
          }
LABEL_16:
          v15 = IsSmartcardCert;
          goto LABEL_28;
        }
        fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, SecondaryKeyInfo, 12, 40);
        v5 = v28;
      }
      else
      {
        dwOptions = 8;
        v15 = -2146762495;
LABEL_28:
        fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v15, 12, dwOptions);
      }
    }
    else
    {
      v16 = 1282;
LABEL_19:
      fnEfsLogTrace0(v14, EFS_KEY_OPERATION_NOT_VALID_FOR_EFS, 12, v16);
    }
  }
  if ( v5 )
    EfsEccReleaseSecondaryKeyInfo(v5);
  if ( CertHashFromCertContext )
    EfsFreeHeap(CertHashFromCertContext);
LABEL_49:
  if ( hKey )
    RegCloseKey(hKey);
  if ( CertificateInStore )
    CertFreeCertificateContext(CertificateInStore);
  if ( v8 )
    CertCloseStore(v8, 0);
  if ( v27 )
    EfsReleaseUserKeyInfo();
  return v7;
}

```

## disassembly

```asm
0x18003dad4  mov     [rsp-8+arg_8], rdx
0x18003dad9  mov     [rsp-8+arg_0], rcx
0x18003dade  push    rbp
0x18003dadf  push    rbx
0x18003dae0  push    rsi
0x18003dae1  push    rdi
0x18003dae2  push    r12
0x18003dae4  push    r13
0x18003dae6  push    r14
0x18003dae8  push    r15
0x18003daea  lea     rbp, [rsp-1Fh]
0x18003daef  sub     rsp, 98h
0x18003daf6  xor     r12d, r12d
0x18003daf9  mov     [rbp+57h+pvFindPara], 1
0x18003db01  mov     rax, rdx
0x18003db04  mov     [rbp+57h+hKey], r12
0x18003db08  lea     rdx, a1361413111034; "1.3.6.1.4.1.311.10.3.4"
0x18003db0f  mov     [rbp+57h+dwDisposition], r12d
0x18003db13  mov     [rbp+57h+var_60], rdx
0x18003db17  lea     r9, Class; "REG_SZ"
0x18003db1e  lea     r8d, [r12+1]
0x18003db23  mov     [rbp+57h+arg_10], r12d
0x18003db27  mov     [rax], r12
0x18003db2a  lea     rdx, [rbp+57h+var_60]
0x18003db2e  lea     rax, [rbp+57h+dwDisposition]
0x18003db32  mov     [rbp+57h+var_50], rdx
0x18003db36  mov     rdx, [rcx+20h]; lpSubKey
0x18003db3a  mov     r15d, r12d
0x18003db3d  mov     [rsp+0D0h+lpdwDisposition], rax; lpdwDisposition
0x18003db42  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18003db49  lea     rax, [rbp+57h+hKey]
0x18003db4d  mov     [rbp+57h+pcbData], r12d
0x18003db51  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18003db56  mov     esi, r12d
0x18003db59  mov     [rsp+0D0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18003db5e  mov     [rsp+0D0h+samDesired], r8d; samDesired
0x18003db63  xor     r8d, r8d; Reserved
0x18003db66  mov     [rbp+57h+var_78], r12
0x18003db6a  mov     [rbp+57h+var_70], r12
0x18003db6e  mov     [rsp+0D0h+dwOptions], r12d; dwOptions
0x18003db73  call    cs:__imp_RegCreateKeyExW
0x18003db79  mov     ebx, eax
0x18003db7b  test    eax, eax
0x18003db7d  jz      short loc_18003DBCB
0x18003db7f  mov     r13d, r12d
0x18003db82  mov     esi, 496h
0x18003db87  mov     rcx, cs:g_hPublisher
0x18003db8e  lea     rdx, EFS_API_ERROR
0x18003db95  mov     edi, 0Ch
0x18003db9a  mov     [rsp+0D0h+dwOptions], esi
0x18003db9e  mov     r9d, edi
0x18003dba1  mov     r8d, eax
0x18003dba4  call    fnEfsLogTrace1
0x18003dba9  mov     rcx, cs:g_hPublisher
0x18003dbb0  lea     rdx, EFS_TRACE_ERROR
0x18003dbb7  mov     r9d, edi
0x18003dbba  mov     [rsp+0D0h+dwOptions], esi
0x18003dbbe  mov     r8d, eax
0x18003dbc1  call    fnEfsLogTrace1
0x18003dbc6  jmp     loc_18003DF22
0x18003dbcb  xor     edx, edx; dwEncodingType
0x18003dbcd  lea     rax, aMy; "My"
0x18003dbd4  mov     r9d, 10000h; dwFlags
0x18003dbda  mov     qword ptr [rsp+0D0h+dwOptions], rax; pvPara
0x18003dbdf  xor     r8d, r8d; hCryptProv
0x18003dbe2  lea     ecx, [rdx+0Dh]; lpszStoreProvider
0x18003dbe5  call    cs:__imp_CertOpenStore
0x18003dbeb  mov     r13, rax
0x18003dbee  test    rax, rax
0x18003dbf1  jnz     short loc_18003DC05
0x18003dbf3  mov     ebx, 1776h
0x18003dbf8  call    cs:__imp_GetLastError
0x18003dbfe  mov     esi, 4ACh
0x18003dc03  jmp     short loc_18003DB87
0x18003dc05  mov     edi, 0Ch
0x18003dc0a  lea     rdx, EFS_KEY_OPERATION_BEGIN_SEARCH_MY_STORE
0x18003dc11  mov     r8d, edi
0x18003dc14  mov     r9d, 4AFh
0x18003dc1a  call    fnEfsLogTrace0
0x18003dc1f  lea     r14, EFS_API_ERROR
0x18003dc26  test    r12, r12
0x18003dc29  jz      short loc_18003DC36
0x18003dc2b  mov     rcx, r12; lpMem
0x18003dc2e  call    EfsFreeHeap
0x18003dc33  xor     r12d, r12d
0x18003dc36  test    rsi, rsi
0x18003dc39  jz      short loc_18003DC49
0x18003dc3b  mov     rcx, rsi; lpMem
0x18003dc3e  call    EfsEccReleaseSecondaryKeyInfo
0x18003dc43  xor     esi, esi
0x18003dc45  mov     [rbp+57h+var_70], rsi
0x18003dc49  mov     rcx, [rbp+57h+var_78]
0x18003dc4d  test    rcx, rcx
0x18003dc50  jz      short loc_18003DC5F
0x18003dc52  call    EfsReleaseUserKeyInfo
0x18003dc57  mov     [rbp+57h+var_78], 0
0x18003dc5f  xor     r8d, r8d; dwFindFlags
0x18003dc62  mov     qword ptr [rsp+0D0h+samDesired], r15; pPrevCertContext
0x18003dc67  lea     rax, [rbp+57h+pvFindPara]
0x18003dc6b  mov     r9d, 0A0000h; dwFindType
0x18003dc71  mov     rcx, r13; hCertStore
0x18003dc74  mov     qword ptr [rsp+0D0h+dwOptions], rax; pvFindPara
0x18003dc79  mov     ebx, 1776h
0x18003dc7e  lea     edx, [r8+1]; dwCertEncodingType
0x18003dc82  call    cs:__imp_CertFindCertificateInStore
0x18003dc88  mov     r15, rax
0x18003dc8b  test    rax, rax
0x18003dc8e  jz      loc_18003DF08
0x18003dc94  mov     r9d, 4D6h
0x18003dc9a  lea     rdx, EFS_KEY_OPERATION_FOUND_MATCH_MY_STORE
0x18003dca1  mov     r8d, edi
0x18003dca4  call    fnEfsLogTrace0
0x18003dca9  lea     rdx, [rbp+57h+arg_18]
0x18003dcad  mov     [rbp+57h+arg_18], 0
0x18003dcb4  mov     rcx, r15
0x18003dcb7  call    EfspIsSmartcardCert
0x18003dcbc  test    eax, eax
0x18003dcbe  jz      short loc_18003DCD0
0x18003dcc0  mov     [rsp+0D0h+dwOptions], 4DFh
0x18003dcc8  mov     r8d, eax
0x18003dccb  jmp     loc_18003DD5E
0x18003dcd0  cmp     [rbp+57h+arg_18], 0
0x18003dcd4  jz      short loc_18003DCF0
0x18003dcd6  mov     r9d, 4E5h
0x18003dcdc  mov     r8d, edi
0x18003dcdf  lea     rdx, EFS_KEY_OPERATION_NOT_VALID_FOR_EFS
0x18003dce6  call    fnEfsLogTrace0
0x18003dceb  jmp     loc_18003DC26
0x18003dcf0  lea     r8, [rbp+57h+arg_10]
0x18003dcf4  mov     edx, 5FFFFh
0x18003dcf9  mov     rcx, r15
0x18003dcfc  call    cs:__imp_EfsUtilCheckCurrentKeyCapabilities
0x18003dd02  mov     ebx, eax
0x18003dd04  test    eax, eax
0x18003dd06  jz      short loc_18003DD36
0x18003dd08  mov     rcx, cs:g_hPublisher
0x18003dd0f  mov     r9d, edi
0x18003dd12  mov     r8d, eax
0x18003dd15  mov     [rsp+0D0h+dwOptions], 4EFh
0x18003dd1d  mov     rdx, r14
0x18003dd20  call    fnEfsLogTrace1
0x18003dd25  cmp     ebx, 80090345h
0x18003dd2b  jnz     loc_18003DC26
0x18003dd31  jmp     loc_18003DF08
0x18003dd36  mov     ecx, [rbp+57h+arg_10]
0x18003dd39  call    EfspIsValidCurrentKey_Capabilities
0x18003dd3e  test    eax, eax
0x18003dd40  jnz     short loc_18003DD4A
0x18003dd42  mov     r9d, 502h
0x18003dd48  jmp     short loc_18003DCDC
0x18003dd4a  test    byte ptr [rbp+57h+arg_10], 80h
0x18003dd4e  jnz     short loc_18003DD75
0x18003dd50  mov     [rsp+0D0h+dwOptions], 508h
0x18003dd58  mov     r8d, 800B0101h
0x18003dd5e  mov     rcx, cs:g_hPublisher
0x18003dd65  mov     r9d, edi
0x18003dd68  mov     rdx, r14
0x18003dd6b  call    fnEfsLogTrace1
0x18003dd70  jmp     loc_18003DC26
0x18003dd75  lea     rdx, [rbp+57h+pcbData]; pcbData
0x18003dd79  mov     rcx, r15; pCertContext
0x18003dd7c  call    GetCertHashFromCertContext
0x18003dd81  mov     r12, rax
0x18003dd84  test    rax, rax
0x18003dd87  jnz     short loc_18003DDB5
0x18003dd89  call    cs:__imp_GetLastError
0x18003dd8f  mov     rcx, cs:g_hPublisher
0x18003dd96  mov     r9d, edi
0x18003dd99  mov     r8d, eax
0x18003dd9c  mov     [rsp+0D0h+dwOptions], 516h
0x18003dda4  mov     rdx, r14
0x18003dda7  mov     ebx, eax
0x18003dda9  call    fnEfsLogTrace1
0x18003ddae  test    ebx, ebx
0x18003ddb0  jmp     loc_18003DD2B
0x18003ddb5  test    [rbp+57h+arg_10], 1000h
0x18003ddbc  mov     rbx, [rbp+57h+arg_0]
0x18003ddc0  jz      short loc_18003DE19
0x18003ddc2  mov     rdx, [rbx+20h]; lpSubKey
0x18003ddc6  lea     rax, [rbp+57h+var_70]
0x18003ddca  mov     r9d, 1; int
0x18003ddd0  mov     qword ptr [rsp+0D0h+dwOptions], rax; struct _EFS_ECC_SECONDARY_KEY **
0x18003ddd5  mov     r8, r15; struct _CERT_CONTEXT *
0x18003ddd8  mov     rcx, 0FFFFFFFF80000003h; hkey
0x18003dddf  call    ?EfspEccGetSecondaryKeyInfo@@YAKPEAUHKEY__@@PEBGPEBU_CERT_CONTEXT@@HPEAPEAU_EFS_ECC_SECONDARY_KEY@@@Z; EfspEccGetSecondaryKeyInfo(HKEY__ *,ushort const *,_CERT_CONTEXT const *,int,_EFS_ECC_SECONDARY_KEY * *)
0x18003dde4  test    eax, eax
0x18003dde6  jz      short loc_18003DE0E
0x18003dde8  mov     rcx, cs:g_hPublisher
0x18003ddef  mov     r9d, edi
0x18003ddf2  mov     r8d, eax
0x18003ddf5  mov     [rsp+0D0h+dwOptions], 528h
0x18003ddfd  mov     rdx, r14
0x18003de00  call    fnEfsLogTrace1
0x18003de05  mov     rsi, [rbp+57h+var_70]
0x18003de09  jmp     loc_18003DC26
0x18003de0e  mov     rsi, [rbp+57h+var_70]
0x18003de12  mov     edx, 30h ; '0'
0x18003de17  jmp     short loc_18003DE1E
0x18003de19  mov     edx, 1
0x18003de1e  xor     r9d, r9d
0x18003de21  lea     rax, [rbp+57h+var_78]
0x18003de25  cmp     dword ptr [rbx+58h], 2
0x18003de29  mov     r8, rsi
0x18003de2c  mov     rcx, r15; pCertContext
0x18003de2f  mov     qword ptr [rsp+0D0h+dwOptions], rax; __int64
0x18003de34  setnz   r9b
0x18003de38  call    EfsObtainKeyInfo
0x18003de3d  test    eax, eax
0x18003de3f  jz      short loc_18003DE4E
0x18003de41  mov     [rsp+0D0h+dwOptions], 538h
0x18003de49  jmp     loc_18003DCC8
0x18003de4e  mov     rdx, [r15+18h]
0x18003de52  lea     r8, [rbp+57h+var_78]
0x18003de56  add     rdx, 48h ; 'H'
0x18003de5a  mov     rcx, rbx
0x18003de5d  call    EfsTryAddKeyInfoToCache
0x18003de62  test    eax, eax
0x18003de64  jnz     short loc_18003DE89
0x18003de66  call    cs:__imp_GetLastError
0x18003de6c  mov     rcx, cs:g_hPublisher
0x18003de73  mov     r9d, edi
0x18003de76  mov     r8d, eax
0x18003de79  mov     [rsp+0D0h+dwOptions], 541h
0x18003de81  mov     rdx, r14
0x18003de84  call    fnEfsLogTrace1
0x18003de89  test    rsi, rsi
0x18003de8c  jz      short loc_18003DEB2
0x18003de8e  mov     rdx, [rbx+20h]; lpSubKey
0x18003de92  mov     r8, rsi; struct _EFS_ECC_SECONDARY_KEY *
0x18003de95  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18003de9c  call    ?EfspEccSaveSecondaryKeyInfo@@YAKPEAUHKEY__@@PEBGPEAU_EFS_ECC_SECONDARY_KEY@@@Z; EfspEccSaveSecondaryKeyInfo(HKEY__ *,ushort const *,_EFS_ECC_SECONDARY_KEY *)
0x18003dea1  test    eax, eax
0x18003dea3  jz      short loc_18003DEB2
0x18003dea5  mov     [rsp+0D0h+dwOptions], 54Fh
0x18003dead  jmp     loc_18003DCC8
0x18003deb2  mov     r9, [rbx+20h]
0x18003deb6  mov     rcx, r12
0x18003deb9  mov     r8d, [rbp+57h+arg_10]
0x18003debd  mov     edx, [rbp+57h+pcbData]
0x18003dec0  call    cs:__imp_EfsUtilSetCurrentKey
0x18003dec6  mov     ebx, eax
0x18003dec8  test    eax, eax
0x18003deca  jz      short loc_18003DED9
0x18003decc  mov     [rsp+0D0h+dwOptions], 559h
0x18003ded4  jmp     loc_18003DCC8
0x18003ded9  mov     rdx, [rbp+57h+var_78]
0x18003dedd  mov     r9, r15
0x18003dee0  mov     rax, [rbp+57h+arg_8]
0x18003dee4  mov     r8d, [rbp+57h+arg_10]
0x18003dee8  mov     rcx, [rbp+57h+arg_0]
0x18003deec  mov     [rbp+57h+var_78], 0
0x18003def4  mov     [rax], rdx
0x18003def7  lea     rax, aAddressbook; "AddressBook"
0x18003defe  mov     qword ptr [rsp+0D0h+dwOptions], rax
0x18003df03  call    EfsPromoteToCurrentKey
0x18003df08  test    rsi, rsi
0x18003df0b  jz      short loc_18003DF15
0x18003df0d  mov     rcx, rsi; lpMem
0x18003df10  call    EfsEccReleaseSecondaryKeyInfo
0x18003df15  test    r12, r12
0x18003df18  jz      short loc_18003DF22
0x18003df1a  mov     rcx, r12; lpMem
0x18003df1d  call    EfsFreeHeap
0x18003df22  mov     rcx, [rbp+57h+hKey]; hKey
0x18003df26  test    rcx, rcx
0x18003df29  jz      short loc_18003DF31
0x18003df2b  call    cs:__imp_RegCloseKey
0x18003df31  test    r15, r15
0x18003df34  jz      short loc_18003DF3F
0x18003df36  mov     rcx, r15; pCertContext
0x18003df39  call    cs:__imp_CertFreeCertificateContext
0x18003df3f  test    r13, r13
0x18003df42  jz      short loc_18003DF4F
0x18003df44  xor     edx, edx; dwFlags
0x18003df46  mov     rcx, r13; hCertStore
0x18003df49  call    cs:__imp_CertCloseStore
0x18003df4f  mov     rcx, [rbp+57h+var_78]
0x18003df53  test    rcx, rcx
0x18003df56  jz      short loc_18003DF5D
0x18003df58  call    EfsReleaseUserKeyInfo
0x18003df5d  mov     eax, ebx
0x18003df5f  add     rsp, 98h
0x18003df66  pop     r15
0x18003df68  pop     r14
0x18003df6a  pop     r13
0x18003df6c  pop     r12
0x18003df6e  pop     rdi
0x18003df6f  pop     rsi
0x18003df70  pop     rbx
0x18003df71  pop     rbp
0x18003df72  retn
```
