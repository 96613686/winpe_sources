# CHtmlPreviewer::IsTargetPreviewable(IMoniker *)

- ea: `0x180067c90`
- end: `0x180067fa2`
- name: `?IsTargetPreviewable@CHtmlPreviewer@@AEAAHPEAUIMoniker@@@Z`
- size: `786`
- prototype: `__int64 __fastcall(CHtmlPreviewer *__hidden this, struct IMoniker *)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x180067bc0`

## callees

- `0x18000910c`
- `0x180067c90`
- `0x1800cc9ba`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `SHLWAPI!__imp_StrCmpNICW` at `0x180067ef2`
- `SHLWAPI!__imp_StrCmpNICW` at `0x180067f0e`
- `SHLWAPI!__imp_StrCmpNICW` at `0x180067ef2`
- `SHLWAPI!__imp_StrCmpNICW` at `0x180067f0e`
- `SHLWAPI!__imp_StrCmpICW` at `0x180067f26`
- `SHLWAPI!__imp_StrCmpICW` at `0x180067f26`
- `KERNEL32!GetVersionExA` at `0x180067d29`
- `KERNEL32!GetVersionExA` at `0x180067d29`
- `urlmon!CreateUri` at `0x180067cff`
- `urlmon!CreateUri` at `0x180067cff`
- `ole32!CoTaskMemFree` at `0x180067f7a`
- `ole32!CoTaskMemFree` at `0x180067f7a`
- `OLEAUT32!__imp_SysFreeString` at `0x180067f41`
- `OLEAUT32!__imp_SysFreeString` at `0x180067f55`
- `OLEAUT32!__imp_SysFreeString` at `0x180067f41`
- `OLEAUT32!__imp_SysFreeString` at `0x180067f55`
- `WININET!HttpQueryInfoW` at `0x180067ed6`
- `WININET!HttpQueryInfoW` at `0x180067ed6`
- `WININET!HttpSendRequestA` at `0x180067ead`
- `WININET!HttpSendRequestA` at `0x180067ead`
- `WININET!InternetOpenW` at `0x180067d6f`
- `WININET!InternetOpenW` at `0x180067d6f`
- `WININET!InternetConnectW` at `0x180067df6`
- `WININET!InternetConnectW` at `0x180067df6`
- `WININET!HttpOpenRequestW` at `0x180067e6d`
- `WININET!HttpOpenRequestW` at `0x180067e6d`
- `WININET!InternetSetOptionA` at `0x180067e97`
- `WININET!InternetSetOptionA` at `0x180067e97`
- `WININET!InternetCloseHandle` at `0x180067f36`
- `WININET!InternetCloseHandle` at `0x180067f4a`
- `WININET!InternetCloseHandle` at `0x180067f5e`
- `WININET!InternetCloseHandle` at `0x180067f36`
- `WININET!InternetCloseHandle` at `0x180067f4a`
- `WININET!InternetCloseHandle` at `0x180067f5e`

## pseudocode

```c
__int64 __fastcall CHtmlPreviewer::IsTargetPreviewable(CHtmlPreviewer *this, struct IMoniker *a2)
{
  struct IMonikerVtbl *lpVtbl; // rax
  unsigned int v3; // r14d
  void *v4; // rdi
  void *v5; // rsi
  void *v6; // rax
  void *v7; // rbx
  DWORD dwFlags; // [rsp+20h] [rbp-E0h]
  int v10; // [rsp+40h] [rbp-C0h] BYREF
  IUri *ppURI; // [rsp+48h] [rbp-B8h] BYREF
  int Buffer; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwBufferLength; // [rsp+54h] [rbp-ACh] BYREF
  LPCWSTR lpszObjectName; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR lpszServerName; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR pwzURI; // [rsp+68h] [rbp-98h] BYREF
  LPCWSTR lpszAcceptTypes[2]; // [rsp+70h] [rbp-90h] BYREF
  _OSVERSIONINFOA VersionInformation; // [rsp+80h] [rbp-80h] BYREF
  WCHAR szAgent[56]; // [rsp+120h] [rbp+20h] BYREF
  WCHAR pszStr1[264]; // [rsp+190h] [rbp+90h] BYREF

  lpVtbl = a2->lpVtbl;
  pwzURI = 0;
  v3 = 1;
  if ( ((int (__fastcall *)(struct IMoniker *, _QWORD, _QWORD, LPCWSTR *))lpVtbl->GetDisplayName)(a2, 0, 0, &pwzURI) >= 0 )
  {
    ppURI = 0;
    if ( CreateUri(pwzURI, 0, 0, &ppURI) >= 0 )
    {
      memset_0(&VersionInformation.dwMajorVersion, 0, 0x90u);
      VersionInformation.dwOSVersionInfoSize = 148;
      if ( GetVersionExA(&VersionInformation) )
      {
        dwFlags = VersionInformation.dwMinorVersion;
        if ( (int)StringCchPrintfW(
                    szAgent,
                    0x32u,
                    L"Windows-Explorer (Windows NT %d.%d)",
                    VersionInformation.dwMajorVersion,
                    dwFlags) >= 0 )
        {
          v4 = InternetOpenW(szAgent, 0, 0, 0, 0);
          if ( v4 )
          {
            lpszServerName = 0;
            if ( ((int (__fastcall *)(IUri *, LPCWSTR *))ppURI->lpVtbl->GetHost)(ppURI, &lpszServerName) >= 0 )
            {
              v10 = 0;
              if ( ((int (__fastcall *)(IUri *, int *))ppURI->lpVtbl->GetPort)(ppURI, &v10) >= 0 )
              {
                v5 = InternetConnectW(v4, lpszServerName, v10, &cchOriginalDestLength, &cchOriginalDestLength, 3u, 0, 0);
                if ( v5 )
                {
                  lpszObjectName = 0;
                  if ( ((int (__fastcall *)(IUri *, LPCWSTR *))ppURI->lpVtbl->GetPathAndQuery)(ppURI, &lpszObjectName) >= 0 )
                  {
                    lpszAcceptTypes[0] = L"*/*";
                    lpszAcceptTypes[1] = 0;
                    v6 = HttpOpenRequestW(v5, L"HEAD", lpszObjectName, 0, 0, lpszAcceptTypes, 0x480000u, 0);
                    v7 = v6;
                    if ( v6 )
                    {
                      Buffer = 4;
                      InternetSetOptionA(v6, 0x55u, &Buffer, 4u);
                      if ( HttpSendRequestA(v7, 0, 0, 0, 0) )
                      {
                        dwBufferLength = 520;
                        if ( HttpQueryInfoW(v7, 1u, pszStr1, &dwBufferLength, 0) )
                        {
                          if ( StrCmpNICW(pszStr1, L"text", 4)
                            && (StrCmpNICW(pszStr1, L"image", 5) || !StrCmpICW(pszStr1, L"image/tiff")) )
                          {
                            v3 = 0;
                          }
                        }
                      }
                      InternetCloseHandle(v7);
                    }
                    SysFreeString((BSTR)lpszObjectName);
                  }
                  InternetCloseHandle(v5);
                }
              }
              SysFreeString((BSTR)lpszServerName);
            }
            InternetCloseHandle(v4);
          }
        }
      }
      ((void (__fastcall *)(IUri *))ppURI->lpVtbl->Release)(ppURI);
    }
    CoTaskMemFree((LPVOID)pwzURI);
  }
  return v3;
}

```

## disassembly

```asm
0x180067c90  push    rbp
0x180067c92  push    rbx
0x180067c93  push    rsi
0x180067c94  push    rdi
0x180067c95  push    r14
0x180067c97  push    r15
0x180067c99  lea     rbp, [rsp-2B8h]
0x180067ca1  sub     rsp, 3B8h
0x180067ca8  mov     rax, cs:__security_cookie
0x180067caf  xor     rax, rsp
0x180067cb2  mov     [rbp+2E0h+var_40], rax
0x180067cb9  mov     rax, [rdx]
0x180067cbc  lea     r9, [rsp+3E0h+pwzURI]
0x180067cc1  mov     rcx, rdx
0x180067cc4  xor     r15d, r15d
0x180067cc7  xor     r8d, r8d
0x180067cca  mov     [rsp+3E0h+pwzURI], r15
0x180067ccf  xor     edx, edx
0x180067cd1  mov     r14d, 1
0x180067cd7  mov     rax, [rax+0A0h]
0x180067cde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067ce3  test    eax, eax
0x180067ce5  js      loc_180067F80
0x180067ceb  mov     rcx, [rsp+3E0h+pwzURI]; pwzURI
0x180067cf0  lea     r9, [rsp+3E0h+ppURI]; ppURI
0x180067cf5  xor     r8d, r8d; dwReserved
0x180067cf8  mov     [rsp+3E0h+ppURI], r15
0x180067cfd  xor     edx, edx; dwFlags
0x180067cff  call    cs:__imp_CreateUri
0x180067d05  test    eax, eax
0x180067d07  js      loc_180067F75
0x180067d0d  xor     edx, edx; Val
0x180067d0f  lea     rcx, [rbp+2E0h+VersionInformation.dwMajorVersion]; void *
0x180067d13  mov     r8d, 90h; Size
0x180067d19  call    memset_0
0x180067d1e  lea     rcx, [rbp+2E0h+VersionInformation]; lpVersionInformation
0x180067d22  mov     [rbp+2E0h+VersionInformation.dwOSVersionInfoSize], 94h
0x180067d29  call    cs:__imp_GetVersionExA
0x180067d2f  test    eax, eax
0x180067d31  jz      loc_180067F64
0x180067d37  mov     eax, [rbp+2E0h+VersionInformation.dwMinorVersion]
0x180067d3a  lea     r8, aWindowsExplore; "Windows-Explorer (Windows NT %d.%d)"
0x180067d41  mov     r9d, [rbp+2E0h+VersionInformation.dwMajorVersion]
0x180067d45  lea     edx, [r14+31h]; unsigned __int64
0x180067d49  lea     rcx, [rbp+2E0h+szAgent]; unsigned __int16 *
0x180067d4d  mov     [rsp+3E0h+dwFlags], eax
0x180067d51  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180067d56  test    eax, eax
0x180067d58  js      loc_180067F64
0x180067d5e  xor     r9d, r9d; lpszProxyBypass
0x180067d61  mov     [rsp+3E0h+dwFlags], r15d; dwFlags
0x180067d66  xor     r8d, r8d; lpszProxy
0x180067d69  lea     rcx, [rbp+2E0h+szAgent]; lpszAgent
0x180067d6d  xor     edx, edx; dwAccessType
0x180067d6f  call    cs:__imp_InternetOpenW
0x180067d75  mov     rdi, rax
0x180067d78  test    rax, rax
0x180067d7b  jz      loc_180067F64
0x180067d81  mov     rcx, [rsp+3E0h+ppURI]
0x180067d86  lea     rdx, [rsp+3E0h+lpszServerName]
0x180067d8b  mov     [rsp+3E0h+lpszServerName], r15
0x180067d90  mov     rax, [rcx]
0x180067d93  mov     rax, [rax+68h]
0x180067d97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067d9c  test    eax, eax
0x180067d9e  js      loc_180067F5B
0x180067da4  mov     rcx, [rsp+3E0h+ppURI]
0x180067da9  lea     rdx, [rsp+3E0h+var_3A0]
0x180067dae  mov     [rsp+3E0h+var_3A0], r15d
0x180067db3  mov     rax, [rcx]
0x180067db6  mov     rax, [rax+0B8h]
0x180067dbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067dc2  test    eax, eax
0x180067dc4  js      loc_180067F50
0x180067dca  movzx   r8d, word ptr [rsp+3E0h+var_3A0]; nServerPort
0x180067dd0  lea     r9, cchOriginalDestLength; lpszUserName
0x180067dd7  mov     rdx, [rsp+3E0h+lpszServerName]; lpszServerName
0x180067ddc  mov     rcx, rdi; hInternet
0x180067ddf  mov     [rsp+3E0h+dwContext], r15; dwContext
0x180067de4  mov     [rsp+3E0h+var_3B0], r15d; dwFlags
0x180067de9  mov     [rsp+3E0h+dwService], 3; dwService
0x180067df1  mov     qword ptr [rsp+3E0h+dwFlags], r9; lpszPassword
0x180067df6  call    cs:__imp_InternetConnectW
0x180067dfc  mov     rsi, rax
0x180067dff  test    rax, rax
0x180067e02  jz      loc_180067F50
0x180067e08  mov     rcx, [rsp+3E0h+ppURI]
0x180067e0d  lea     rdx, [rsp+3E0h+lpszObjectName]
0x180067e12  mov     [rsp+3E0h+lpszObjectName], r15
0x180067e17  mov     rax, [rcx]
0x180067e1a  mov     rax, [rax+80h]
0x180067e21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067e26  test    eax, eax
0x180067e28  js      loc_180067F47
0x180067e2e  mov     r8, [rsp+3E0h+lpszObjectName]; lpszObjectName
0x180067e33  lea     rax, asc_1800DCD28; "*/*"
0x180067e3a  mov     [rsp+3E0h+dwContext], r15; dwContext
0x180067e3f  lea     rdx, szVerb; "HEAD"
0x180067e46  mov     [rsp+3E0h+lpszAcceptTypes], rax
0x180067e4b  xor     r9d, r9d; lpszVersion
0x180067e4e  lea     rax, [rsp+3E0h+lpszAcceptTypes]
0x180067e53  mov     [rsp+3E0h+var_3B0], 480000h; dwFlags
0x180067e5b  mov     qword ptr [rsp+3E0h+dwService], rax; lplpszAcceptTypes
0x180067e60  mov     rcx, rsi; hConnect
0x180067e63  mov     qword ptr [rsp+3E0h+dwFlags], r15; lpszReferrer
0x180067e68  mov     [rsp+3E0h+var_368], r15
0x180067e6d  call    cs:__imp_HttpOpenRequestW
0x180067e73  mov     rbx, rax
0x180067e76  test    rax, rax
0x180067e79  jz      loc_180067F3C
0x180067e7f  lea     r9d, [r14+3]; dwBufferLength
0x180067e83  mov     [rsp+3E0h+Buffer], 4
0x180067e8b  lea     r8, [rsp+3E0h+Buffer]; lpBuffer
0x180067e90  mov     rcx, rax; hInternet
0x180067e93  lea     edx, [r14+54h]; dwOption
0x180067e97  call    cs:__imp_InternetSetOptionA
0x180067e9d  xor     r9d, r9d; lpOptional
0x180067ea0  mov     [rsp+3E0h+dwFlags], r15d; dwOptionalLength
0x180067ea5  xor     r8d, r8d; dwHeadersLength
0x180067ea8  xor     edx, edx; lpszHeaders
0x180067eaa  mov     rcx, rbx; hRequest
0x180067ead  call    cs:__imp_HttpSendRequestA
0x180067eb3  test    eax, eax
0x180067eb5  jz      short loc_180067F33
0x180067eb7  lea     r9, [rsp+3E0h+dwBufferLength]; lpdwBufferLength
0x180067ebc  mov     [rsp+3E0h+dwBufferLength], 208h
0x180067ec4  lea     r8, [rbp+2E0h+pszStr1]; lpBuffer
0x180067ecb  mov     qword ptr [rsp+3E0h+dwFlags], r15; lpdwIndex
0x180067ed0  mov     edx, r14d; dwInfoLevel
0x180067ed3  mov     rcx, rbx; hRequest
0x180067ed6  call    cs:__imp_HttpQueryInfoW
0x180067edc  test    eax, eax
0x180067ede  jz      short loc_180067F33
0x180067ee0  lea     r8d, [r14+3]; nChar
0x180067ee4  lea     rdx, aText_0; "text"
0x180067eeb  lea     rcx, [rbp+2E0h+pszStr1]; pszStr1
0x180067ef2  call    cs:__imp_StrCmpNICW
0x180067ef8  test    eax, eax
0x180067efa  jz      short loc_180067F33
0x180067efc  lea     r8d, [r14+4]; nChar
0x180067f00  lea     rdx, aImage_0; "image"
0x180067f07  lea     rcx, [rbp+2E0h+pszStr1]; pszStr1
0x180067f0e  call    cs:__imp_StrCmpNICW
0x180067f14  test    eax, eax
0x180067f16  jnz     short loc_180067F30
0x180067f18  lea     rdx, aImageTiff; "image/tiff"
0x180067f1f  lea     rcx, [rbp+2E0h+pszStr1]; pszStr1
0x180067f26  call    cs:__imp_StrCmpICW
0x180067f2c  test    eax, eax
0x180067f2e  jnz     short loc_180067F33
0x180067f30  mov     r14d, r15d
0x180067f33  mov     rcx, rbx; hInternet
0x180067f36  call    cs:__imp_InternetCloseHandle
0x180067f3c  mov     rcx, [rsp+3E0h+lpszObjectName]; bstrString
0x180067f41  call    cs:__imp_SysFreeString
0x180067f47  mov     rcx, rsi; hInternet
0x180067f4a  call    cs:__imp_InternetCloseHandle
0x180067f50  mov     rcx, [rsp+3E0h+lpszServerName]; bstrString
0x180067f55  call    cs:__imp_SysFreeString
0x180067f5b  mov     rcx, rdi; hInternet
0x180067f5e  call    cs:__imp_InternetCloseHandle
0x180067f64  mov     rcx, [rsp+3E0h+ppURI]
0x180067f69  mov     rdx, [rcx]
0x180067f6c  mov     rax, [rdx+10h]
0x180067f70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067f75  mov     rcx, [rsp+3E0h+pwzURI]; pv
0x180067f7a  call    cs:__imp_CoTaskMemFree
0x180067f80  mov     eax, r14d
0x180067f83  mov     rcx, [rbp+2E0h+var_40]
0x180067f8a  xor     rcx, rsp; StackCookie
0x180067f8d  call    __security_check_cookie
0x180067f92  add     rsp, 3B8h
0x180067f99  pop     r15
0x180067f9b  pop     r14
0x180067f9d  pop     rdi
0x180067f9e  pop     rsi
0x180067f9f  pop     rbx
0x180067fa0  pop     rbp
0x180067fa1  retn
```
