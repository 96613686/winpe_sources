# DavPromptForPin

- ea: `0x18000dd38`
- end: `0x18000e02e`
- name: `DavPromptForPin`
- size: `758`
- prototype: `__int64 __fastcall(const CERT_CONTEXT *, const WCHAR *, LPWSTR *, _DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180007ad0`

## callees

- `0x18000dd38`
- `0x180011eb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000de55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000df05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dfd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000de55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000df05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dfd2`
- `KERNEL32!LocalAlloc` at `0x18000de1c`
- `KERNEL32!LocalAlloc` at `0x18000df1f`
- `KERNEL32!LocalAlloc` at `0x18000df63`
- `KERNEL32!LocalAlloc` at `0x18000de1c`
- `KERNEL32!LocalAlloc` at `0x18000df1f`
- `KERNEL32!LocalAlloc` at `0x18000df63`
- `KERNEL32!LocalFree` at `0x18000df53`
- `KERNEL32!LocalFree` at `0x18000dfca`
- `KERNEL32!LocalFree` at `0x18000dfe3`
- `KERNEL32!LocalFree` at `0x18000df53`
- `KERNEL32!LocalFree` at `0x18000dfca`
- `KERNEL32!LocalFree` at `0x18000dfe3`
- `ADVAPI32!CredMarshalCredentialW` at `0x18000ddcb`
- `ADVAPI32!CredMarshalCredentialW` at `0x18000ddcb`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18000ddb1`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18000ddb1`
- `credui!CredUIPromptForWindowsCredentialsW` at `0x18000deb4`
- `credui!CredUIPromptForWindowsCredentialsW` at `0x18000deb4`
- `credui!CredUnPackAuthenticationBufferW` at `0x18000def7`
- `credui!CredUnPackAuthenticationBufferW` at `0x18000dfb1`
- `credui!CredUnPackAuthenticationBufferW` at `0x18000def7`
- `credui!CredUnPackAuthenticationBufferW` at `0x18000dfb1`
- `credui!CredPackAuthenticationBufferW` at `0x18000ddff`
- `credui!CredPackAuthenticationBufferW` at `0x18000de4b`
- `credui!CredPackAuthenticationBufferW` at `0x18000ddff`
- `credui!CredPackAuthenticationBufferW` at `0x18000de4b`
- `ole32!CoTaskMemFree` at `0x18000e00a`
- `ole32!CoTaskMemFree` at `0x18000e00a`

## pseudocode

```c
__int64 __fastcall DavPromptForPin(const CERT_CONTEXT *a1, const WCHAR *a2, LPWSTR *a3, _DWORD *a4)
{
  HLOCAL v7; // rdi
  DWORD LastError; // ebx
  WCHAR *v9; // rax
  DWORD v10; // eax
  unsigned int v11; // eax
  _BYTE *v12; // rcx
  __int64 v13; // rax
  DWORD pcbData; // [rsp+50h] [rbp-49h] BYREF
  DWORD pcchMaxDomainName; // [rsp+54h] [rbp-45h] BYREF
  DWORD pcchMaxUserName; // [rsp+58h] [rbp-41h] BYREF
  DWORD pcchMaxPassword; // [rsp+5Ch] [rbp-3Dh] BYREF
  ULONG pulAuthPackage; // [rsp+60h] [rbp-39h] BYREF
  LPWSTR MarshaledCredential; // [rsp+68h] [rbp-31h] BYREF
  PVOID pAuthBuffer; // [rsp+70h] [rbp-29h] BYREF
  _CREDUI_INFOW pUiInfo; // [rsp+78h] [rbp-21h] BYREF
  __int128 pvData; // [rsp+A0h] [rbp+7h] BYREF
  __int64 v24; // [rsp+B0h] [rbp+17h]

  pcbData = 20;
  pAuthBuffer = 0;
  MarshaledCredential = 0;
  pulAuthPackage = 0;
  pcchMaxPassword = 0;
  pvData = 0;
  pcchMaxDomainName = 0;
  pcchMaxUserName = 0;
  v24 = 0;
  memset(&pUiInfo, 0, sizeof(pUiInfo));
  LODWORD(pvData) = 24;
  if ( CertGetCertificateContextProperty(a1, 3u, (char *)&pvData + 4, &pcbData) )
  {
    if ( CredMarshalCredentialW(CertCredential, &pvData, &MarshaledCredential) )
    {
      if ( MarshaledCredential )
      {
        pcbData = 0;
        if ( CredPackAuthenticationBufferW(0, MarshaledCredential, (LPWSTR)&pszPassword, 0, &pcbData) || pcbData )
        {
          v7 = LocalAlloc(0x40u, pcbData);
          if ( !v7 )
          {
            LastError = 8;
            goto LABEL_24;
          }
          if ( CredPackAuthenticationBufferW(0, MarshaledCredential, (LPWSTR)&pszPassword, (PBYTE)v7, &pcbData) )
          {
            pUiInfo.pszMessageText = L"Please Enter Your Pin";
            *(_QWORD *)&pUiInfo.cbSize = 40;
            pUiInfo.hwndParent = 0;
            pUiInfo.pszCaptionText = a2;
            pUiInfo.hbmBanner = 0;
            LastError = CredUIPromptForWindowsCredentialsW(
                          &pUiInfo,
                          0,
                          &pulAuthPackage,
                          v7,
                          pcbData,
                          &pAuthBuffer,
                          &pcbData,
                          0,
                          0x20u);
            if ( LastError )
              goto LABEL_22;
            if ( CredUnPackAuthenticationBufferW(
                   1u,
                   pAuthBuffer,
                   pcbData,
                   0,
                   &pulAuthPackage,
                   0,
                   &pcchMaxDomainName,
                   0,
                   &pcchMaxPassword) )
            {
              goto LABEL_21;
            }
            LastError = GetLastError();
            if ( LastError != 122 )
              goto LABEL_22;
            v9 = (WCHAR *)LocalAlloc(0x40u, 2LL * pcchMaxPassword);
            *a3 = v9;
            if ( v9 )
            {
              v10 = pcchMaxDomainName;
              if ( pcchMaxDomainName <= pulAuthPackage )
              {
                pcchMaxUserName = pulAuthPackage;
                v10 = pulAuthPackage;
              }
              else
              {
                pcchMaxUserName = pcchMaxDomainName;
              }
              v11 = 2 * v10;
              pcchMaxDomainName = v11;
              if ( MarshaledCredential )
              {
                LocalFree(MarshaledCredential);
                v11 = pcchMaxDomainName;
              }
              MarshaledCredential = (LPWSTR)LocalAlloc(0x40u, v11);
              if ( MarshaledCredential )
              {
                LastError = 0;
                if ( CredUnPackAuthenticationBufferW(
                       1u,
                       pAuthBuffer,
                       pcbData,
                       MarshaledCredential,
                       &pcchMaxUserName,
                       MarshaledCredential,
                       &pcchMaxUserName,
                       *a3,
                       &pcchMaxPassword) )
                {
LABEL_21:
                  *a4 = 2 * pcchMaxPassword;
                  goto LABEL_22;
                }
              }
            }
          }
          LastError = GetLastError();
LABEL_22:
          LocalFree(v7);
          goto LABEL_24;
        }
      }
    }
  }
  LastError = GetLastError();
LABEL_24:
  if ( MarshaledCredential )
    LocalFree(MarshaledCredential);
  v12 = pAuthBuffer;
  if ( pAuthBuffer )
  {
    v13 = pcbData;
    if ( pcbData )
    {
      do
      {
        *v12++ = 0;
        --v13;
      }
      while ( v13 );
      v12 = pAuthBuffer;
    }
    CoTaskMemFree(v12);
  }
  return LastError;
}

```

## disassembly

```asm
0x18000dd38  push    rbp
0x18000dd3a  push    rbx
0x18000dd3b  push    rsi
0x18000dd3c  push    rdi
0x18000dd3d  push    r14
0x18000dd3f  push    r15
0x18000dd41  lea     rbp, [rsp-2Fh]
0x18000dd46  sub     rsp, 0C8h
0x18000dd4d  mov     rax, cs:__security_cookie
0x18000dd54  xor     rax, rsp
0x18000dd57  mov     [rbp+57h+var_38], rax
0x18000dd5b  xor     r15d, r15d
0x18000dd5e  mov     [rbp+57h+pcbData], 14h
0x18000dd65  xor     eax, eax
0x18000dd67  mov     [rbp+57h+pAuthBuffer], r15
0x18000dd6b  xorps   xmm0, xmm0
0x18000dd6e  mov     [rbp+57h+MarshaledCredential], r15
0x18000dd72  mov     r14, r9
0x18000dd75  mov     [rbp+57h+pulAuthPackage], r15d
0x18000dd79  mov     rsi, r8
0x18000dd7c  mov     [rbp+57h+pUiInfo.hbmBanner], rax
0x18000dd80  mov     rbx, rdx
0x18000dd83  mov     [rbp+57h+pcchMaxPassword], r15d
0x18000dd87  movups  [rbp+57h+pvData], xmm0
0x18000dd8b  lea     edx, [rax+3]; dwPropId
0x18000dd8e  mov     [rbp+57h+pcchMaxDomainName], r15d
0x18000dd92  lea     r9, [rbp+57h+pcbData]; pcbData
0x18000dd96  mov     [rbp+57h+pcchMaxUserName], r15d
0x18000dd9a  lea     r8, [rbp+57h+pvData+4]; pvData
0x18000dd9e  mov     [rbp+57h+var_40], rax
0x18000dda2  movups  xmmword ptr [rbp+57h+pUiInfo.cbSize], xmm0
0x18000dda6  mov     dword ptr [rbp+57h+pvData], 18h
0x18000ddad  movups  xmmword ptr [rbp+57h+pUiInfo.pszMessageText], xmm0
0x18000ddb1  call    cs:__imp_CertGetCertificateContextProperty
0x18000ddb7  test    eax, eax
0x18000ddb9  jz      loc_18000DFD2
0x18000ddbf  lea     r8, [rbp+57h+MarshaledCredential]; MarshaledCredential
0x18000ddc3  lea     rdx, [rbp+57h+pvData]; Credential
0x18000ddc7  lea     ecx, [r15+1]; CredType
0x18000ddcb  call    cs:__imp_CredMarshalCredentialW
0x18000ddd1  test    eax, eax
0x18000ddd3  jz      loc_18000DFD2
0x18000ddd9  mov     rdx, [rbp+57h+MarshaledCredential]; pszUserName
0x18000dddd  test    rdx, rdx
0x18000dde0  jz      loc_18000DFD2
0x18000dde6  lea     rax, [rbp+57h+pcbData]
0x18000ddea  mov     [rbp+57h+pcbData], r15d
0x18000ddee  xor     r9d, r9d; pPackedCredentials
0x18000ddf1  mov     [rsp+0F0h+pcbPackedCredentials], rax; pcbPackedCredentials
0x18000ddf6  lea     r8, pszPassword; pszPassword
0x18000ddfd  xor     ecx, ecx; dwFlags
0x18000ddff  call    cs:__imp_CredPackAuthenticationBufferW
0x18000de05  mov     ecx, [rbp+57h+pcbData]
0x18000de08  test    eax, eax
0x18000de0a  jnz     short loc_18000DE14
0x18000de0c  test    ecx, ecx
0x18000de0e  jz      loc_18000DFD2
0x18000de14  mov     rdx, rcx; uBytes
0x18000de17  mov     ecx, 40h ; '@'; uFlags
0x18000de1c  call    cs:__imp_LocalAlloc
0x18000de22  mov     rdi, rax
0x18000de25  test    rax, rax
0x18000de28  jnz     short loc_18000DE32
0x18000de2a  lea     ebx, [rax+8]
0x18000de2d  jmp     loc_18000DFDA
0x18000de32  mov     rdx, [rbp+57h+MarshaledCredential]; pszUserName
0x18000de36  lea     rax, [rbp+57h+pcbData]
0x18000de3a  mov     r9, rdi; pPackedCredentials
0x18000de3d  mov     [rsp+0F0h+pcbPackedCredentials], rax; pcbPackedCredentials
0x18000de42  lea     r8, pszPassword; pszPassword
0x18000de49  xor     ecx, ecx; dwFlags
0x18000de4b  call    cs:__imp_CredPackAuthenticationBufferW
0x18000de51  test    eax, eax
0x18000de53  jnz     short loc_18000DE62
0x18000de55  call    cs:__imp_GetLastError
0x18000de5b  mov     ebx, eax
0x18000de5d  jmp     loc_18000DFC7
0x18000de62  mov     [rsp+0F0h+dwFlags], 20h ; ' '; dwFlags
0x18000de6a  lea     rax, aPleaseEnterYou; "Please Enter Your Pin"
0x18000de71  mov     [rbp+57h+pUiInfo.pszMessageText], rax
0x18000de75  lea     r8, [rbp+57h+pulAuthPackage]; pulAuthPackage
0x18000de79  mov     [rsp+0F0h+pfSave], r15; pfSave
0x18000de7e  lea     rax, [rbp+57h+pcbData]
0x18000de82  mov     [rsp+0F0h+pulOutAuthBufferSize], rax; pulOutAuthBufferSize
0x18000de87  lea     rcx, [rbp+57h+pUiInfo]; pUiInfo
0x18000de8b  lea     rax, [rbp+57h+pAuthBuffer]
0x18000de8f  mov     qword ptr [rbp+57h+pUiInfo.cbSize], 28h ; '('
0x18000de97  mov     [rsp+0F0h+ppvOutAuthBuffer], rax; ppvOutAuthBuffer
0x18000de9c  mov     r9, rdi; pvInAuthBuffer
0x18000de9f  mov     eax, [rbp+57h+pcbData]
0x18000dea2  xor     edx, edx; dwAuthError
0x18000dea4  mov     dword ptr [rsp+0F0h+pcbPackedCredentials], eax; ulInAuthBufferSize
0x18000dea8  mov     [rbp+57h+pUiInfo.hwndParent], r15
0x18000deac  mov     [rbp+57h+pUiInfo.pszCaptionText], rbx
0x18000deb0  mov     [rbp+57h+pUiInfo.hbmBanner], r15
0x18000deb4  call    cs:__imp_CredUIPromptForWindowsCredentialsW
0x18000deba  mov     ebx, eax
0x18000debc  test    eax, eax
0x18000debe  jnz     loc_18000DFC7
0x18000dec4  mov     r8d, [rbp+57h+pcbData]; cbAuthBuffer
0x18000dec8  lea     rax, [rbp+57h+pcchMaxPassword]
0x18000decc  mov     rdx, [rbp+57h+pAuthBuffer]; pAuthBuffer
0x18000ded0  lea     ecx, [rbx+1]; dwFlags
0x18000ded3  mov     qword ptr [rsp+0F0h+dwFlags], rax; pcchMaxPassword
0x18000ded8  xor     r9d, r9d; pszUserName
0x18000dedb  mov     [rsp+0F0h+pfSave], r15; pszPassword
0x18000dee0  lea     rax, [rbp+57h+pcchMaxDomainName]
0x18000dee4  mov     [rsp+0F0h+pulOutAuthBufferSize], rax; pcchMaxDomainName
0x18000dee9  lea     rax, [rbp+57h+pulAuthPackage]
0x18000deed  mov     [rsp+0F0h+ppvOutAuthBuffer], r15; pszDomainName
0x18000def2  mov     [rsp+0F0h+pcbPackedCredentials], rax; pcchMaxUserName
0x18000def7  call    cs:__imp_CredUnPackAuthenticationBufferW
0x18000defd  test    eax, eax
0x18000deff  jnz     loc_18000DFBF
0x18000df05  call    cs:__imp_GetLastError
0x18000df0b  mov     ebx, eax
0x18000df0d  cmp     eax, 7Ah ; 'z'
0x18000df10  jnz     loc_18000DFC7
0x18000df16  mov     edx, [rbp+57h+pcchMaxPassword]
0x18000df19  lea     ecx, [rax-3Ah]; uFlags
0x18000df1c  add     rdx, rdx; uBytes
0x18000df1f  call    cs:__imp_LocalAlloc
0x18000df25  mov     [rsi], rax
0x18000df28  test    rax, rax
0x18000df2b  jz      loc_18000DE55
0x18000df31  mov     eax, [rbp+57h+pcchMaxDomainName]
0x18000df34  mov     ecx, [rbp+57h+pulAuthPackage]
0x18000df37  cmp     eax, ecx
0x18000df39  jbe     short loc_18000DF40
0x18000df3b  mov     [rbp+57h+pcchMaxUserName], eax
0x18000df3e  jmp     short loc_18000DF45
0x18000df40  mov     [rbp+57h+pcchMaxUserName], ecx
0x18000df43  mov     eax, ecx
0x18000df45  mov     rcx, [rbp+57h+MarshaledCredential]; hMem
0x18000df49  add     eax, eax
0x18000df4b  mov     [rbp+57h+pcchMaxDomainName], eax
0x18000df4e  test    rcx, rcx
0x18000df51  jz      short loc_18000DF5C
0x18000df53  call    cs:__imp_LocalFree
0x18000df59  mov     eax, [rbp+57h+pcchMaxDomainName]
0x18000df5c  mov     edx, eax; uBytes
0x18000df5e  mov     ecx, 40h ; '@'; uFlags
0x18000df63  call    cs:__imp_LocalAlloc
0x18000df69  mov     [rbp+57h+MarshaledCredential], rax
0x18000df6d  mov     r9, rax; pszUserName
0x18000df70  test    rax, rax
0x18000df73  jz      loc_18000DE55
0x18000df79  mov     r8d, [rbp+57h+pcbData]; cbAuthBuffer
0x18000df7d  lea     rax, [rbp+57h+pcchMaxPassword]
0x18000df81  mov     rdx, [rbp+57h+pAuthBuffer]; pAuthBuffer
0x18000df85  mov     ecx, 1; dwFlags
0x18000df8a  mov     qword ptr [rsp+0F0h+dwFlags], rax; pcchMaxPassword
0x18000df8f  mov     ebx, r15d
0x18000df92  mov     rax, [rsi]
0x18000df95  mov     [rsp+0F0h+pfSave], rax; pszPassword
0x18000df9a  lea     rax, [rbp+57h+pcchMaxUserName]
0x18000df9e  mov     [rsp+0F0h+pulOutAuthBufferSize], rax; pcchMaxDomainName
0x18000dfa3  lea     rax, [rbp+57h+pcchMaxUserName]
0x18000dfa7  mov     [rsp+0F0h+ppvOutAuthBuffer], r9; pszDomainName
0x18000dfac  mov     [rsp+0F0h+pcbPackedCredentials], rax; pcchMaxUserName
0x18000dfb1  call    cs:__imp_CredUnPackAuthenticationBufferW
0x18000dfb7  test    eax, eax
0x18000dfb9  jz      loc_18000DE55
0x18000dfbf  mov     eax, [rbp+57h+pcchMaxPassword]
0x18000dfc2  add     eax, eax
0x18000dfc4  mov     [r14], eax
0x18000dfc7  mov     rcx, rdi; hMem
0x18000dfca  call    cs:__imp_LocalFree
0x18000dfd0  jmp     short loc_18000DFDA
0x18000dfd2  call    cs:__imp_GetLastError
0x18000dfd8  mov     ebx, eax
0x18000dfda  mov     rcx, [rbp+57h+MarshaledCredential]; hMem
0x18000dfde  test    rcx, rcx
0x18000dfe1  jz      short loc_18000DFE9
0x18000dfe3  call    cs:__imp_LocalFree
0x18000dfe9  mov     rcx, [rbp+57h+pAuthBuffer]
0x18000dfed  test    rcx, rcx
0x18000dff0  jz      short loc_18000E010
0x18000dff2  mov     eax, [rbp+57h+pcbData]
0x18000dff5  test    rax, rax
0x18000dff8  jz      short loc_18000E00A
0x18000dffa  mov     [rcx], r15b
0x18000dffd  inc     rcx
0x18000e000  sub     rax, 1
0x18000e004  jnz     short loc_18000DFFA
0x18000e006  mov     rcx, [rbp+57h+pAuthBuffer]; pv
0x18000e00a  call    cs:__imp_CoTaskMemFree
0x18000e010  mov     eax, ebx
0x18000e012  mov     rcx, [rbp+57h+var_38]
0x18000e016  xor     rcx, rsp; StackCookie
0x18000e019  call    __security_check_cookie
0x18000e01e  add     rsp, 0C8h
0x18000e025  pop     r15
0x18000e027  pop     r14
0x18000e029  pop     rdi
0x18000e02a  pop     rsi
0x18000e02b  pop     rbx
0x18000e02c  pop     rbp
0x18000e02d  retn
```
