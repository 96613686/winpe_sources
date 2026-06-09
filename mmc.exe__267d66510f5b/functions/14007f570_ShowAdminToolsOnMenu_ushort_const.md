# ShowAdminToolsOnMenu(ushort const *)

- ea: `0x14007f570`
- end: `0x14007f780`
- name: `?ShowAdminToolsOnMenu@@YAXPEBG@Z`
- size: `528`
- prototype: `void __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14007c380`

## callees

- `0x14005b1b8`
- `0x14007f570`
- `0x1400e9e10`

## import_xrefs

- `USER32!SendMessageTimeoutW` at `0x14007f73f`
- `USER32!SendMessageTimeoutW` at `0x14007f73f`
- `MFC42u!__imp_??0CString@@QEAA@PEBG@Z` at `0x14007f5a3`
- `MFC42u!__imp_??0CString@@QEAA@PEBG@Z` at `0x14007f5a3`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x14007f5f9`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x14007f62c`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x14007f756`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x14007f5f9`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x14007f62c`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x14007f756`
- `MFC42u!__imp_?Left@CString@@QEBA?AV1@H@Z` at `0x14007f5d8`
- `MFC42u!__imp_?Left@CString@@QEBA?AV1@H@Z` at `0x14007f5d8`
- `MFC42u!__imp_?ReverseFind@CString@@QEBAHG@Z` at `0x14007f5b4`
- `MFC42u!__imp_?ReverseFind@CString@@QEBAHG@Z` at `0x14007f5b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14007f74a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14007f74a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14007f6a7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14007f6a7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14007f703`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14007f703`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14007f662`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14007f662`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14007f6d9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14007f6d9`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x14007f5ee`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x14007f5ee`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ShowAdminToolsOnMenu(const unsigned __int16 *a1)
{
  int v1; // eax
  __int64 v2; // r8
  LPCWSTR *v3; // rax
  __int64 v4; // rcx
  char *v5; // rcx
  char *v6; // rdx
  int v7; // eax
  int v8; // ebx
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cbData; // [rsp+4Ch] [rbp-B4h] BYREF
  _BYTE v12[8]; // [rsp+50h] [rbp-B0h] BYREF
  ULONG_PTR dwResult; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR Data[8]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Buffer[264]; // [rsp+70h] [rbp-90h] BYREF

  CString::CString((CString *)v12, a1);
  v1 = CString::ReverseFind((CString *)v12, 0x5Cu);
  if ( v1 != -1 )
  {
    v2 = (unsigned int)(v1 + 1);
    if ( v1 >= 3 )
      v2 = (unsigned int)v1;
    v3 = (LPCWSTR *)CString::Left(v12, &hKey, v2);
    GetFullPathNameW(*v3, 0x104u, Buffer, 0);
    CString::~CString(&hKey);
    v5 = *(char **)CAMCApp::GetDefaultDirectory(v4, &hKey);
    v6 = (char *)((char *)Buffer - v5);
    do
    {
      v7 = *(unsigned __int16 *)&v6[(_QWORD)v5];
      v8 = *(unsigned __int16 *)v5 - v7;
      if ( v8 )
        break;
      v5 += 2;
    }
    while ( v7 );
    CString::~CString(&hKey);
    if ( !v8 )
    {
      hKey = 0;
      if ( !RegOpenKeyExW(
              HKEY_CURRENT_USER,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Advanced",
              0,
              3u,
              &hKey) )
      {
        Type = 1;
        cbData = 8;
        if ( RegQueryValueExW(hKey, L"StartMenuAdminTools", 0, &Type, (LPBYTE)Data, &cbData)
          || Type != 1
          || CompareStringW(0x7Fu, 1u, Data, -1, L"YES", -1) != 2 )
        {
          RegSetValueExW(hKey, L"StartMenuAdminTools", 0, 1u, (const BYTE *)L"YES", 8u);
          dwResult = 0;
          SendMessageTimeoutW(HWND_BROADCAST, 0x1Au, 0, (LPARAM)L"ShellMenu", 2u, 0x64u, &dwResult);
        }
        RegCloseKey(hKey);
      }
    }
  }
  CString::~CString(v12);
}

```

## disassembly

```asm
0x14007f570  mov     [rsp-8+arg_8], rbx
0x14007f575  mov     [rsp-8+arg_10], rsi
0x14007f57a  push    rbp
0x14007f57b  lea     rbp, [rsp-190h]
0x14007f583  sub     rsp, 290h
0x14007f58a  mov     rax, cs:__security_cookie
0x14007f591  xor     rax, rsp
0x14007f594  mov     [rbp+190h+var_10], rax
0x14007f59b  mov     rdx, rcx
0x14007f59e  lea     rcx, [rsp+290h+var_240]
0x14007f5a3  call    cs:__imp_??0CString@@QEAA@PEBG@Z; CString::CString(ushort const *)
0x14007f5a9  nop
0x14007f5aa  mov     edx, 5Ch ; '\'
0x14007f5af  lea     rcx, [rsp+290h+var_240]
0x14007f5b4  call    cs:__imp_?ReverseFind@CString@@QEBAHG@Z; CString::ReverseFind(ushort)
0x14007f5ba  cmp     eax, 0FFFFFFFFh
0x14007f5bd  jz      loc_14007F751
0x14007f5c3  lea     r8d, [rax+1]
0x14007f5c7  cmp     eax, 3
0x14007f5ca  cmovge  r8d, eax
0x14007f5ce  lea     rdx, [rsp+290h+hKey]
0x14007f5d3  lea     rcx, [rsp+290h+var_240]
0x14007f5d8  call    cs:__imp_?Left@CString@@QEBA?AV1@H@Z; CString::Left(int)
0x14007f5de  xor     r9d, r9d; lpFilePart
0x14007f5e1  lea     r8, [rsp+290h+Buffer]; lpBuffer
0x14007f5e6  mov     edx, 104h; nBufferLength
0x14007f5eb  mov     rcx, [rax]; lpFileName
0x14007f5ee  call    cs:__imp_GetFullPathNameW
0x14007f5f4  lea     rcx, [rsp+290h+hKey]
0x14007f5f9  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x14007f5ff  lea     rdx, [rsp+290h+hKey]
0x14007f604  call    ?GetDefaultDirectory@CAMCApp@@QEAA?AVCString@@XZ; CAMCApp::GetDefaultDirectory(void)
0x14007f609  mov     rcx, [rax]
0x14007f60c  lea     rdx, [rsp+290h+Buffer]
0x14007f611  sub     rdx, rcx
0x14007f614  movzx   ebx, word ptr [rcx]
0x14007f617  movzx   eax, word ptr [rcx+rdx]
0x14007f61b  sub     ebx, eax
0x14007f61d  jnz     short loc_14007F627
0x14007f61f  add     rcx, 2
0x14007f623  test    eax, eax
0x14007f625  jnz     short loc_14007F614
0x14007f627  lea     rcx, [rsp+290h+hKey]
0x14007f62c  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x14007f632  test    ebx, ebx
0x14007f634  jnz     loc_14007F751
0x14007f63a  mov     [rsp+290h+hKey], 0
0x14007f643  lea     rax, [rsp+290h+hKey]
0x14007f648  mov     [rsp+290h+phkResult], rax; phkResult
0x14007f64d  lea     r9d, [rbx+3]; samDesired
0x14007f651  xor     r8d, r8d; ulOptions
0x14007f654  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14007f65b  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14007f662  call    cs:__imp_RegOpenKeyExW
0x14007f668  test    eax, eax
0x14007f66a  jnz     loc_14007F751
0x14007f670  lea     ebx, [rax+1]
0x14007f673  mov     [rsp+290h+Type], ebx
0x14007f677  mov     [rsp+290h+cbData], 8
0x14007f67f  lea     rax, [rsp+290h+cbData]
0x14007f684  mov     [rsp+290h+lpcbData], rax; lpcbData
0x14007f689  lea     rax, [rsp+290h+Data]
0x14007f68e  mov     [rsp+290h+phkResult], rax; lpData
0x14007f693  lea     r9, [rsp+290h+Type]; lpType
0x14007f698  xor     r8d, r8d; lpReserved
0x14007f69b  lea     rdx, aStartmenuadmin; "StartMenuAdminTools"
0x14007f6a2  mov     rcx, [rsp+290h+hKey]; hKey
0x14007f6a7  call    cs:__imp_RegQueryValueExW
0x14007f6ad  lea     rsi, aYes; "YES"
0x14007f6b4  test    eax, eax
0x14007f6b6  jnz     short loc_14007F6E4
0x14007f6b8  cmp     [rsp+290h+Type], ebx
0x14007f6bc  jnz     short loc_14007F6E4
0x14007f6be  mov     dword ptr [rsp+290h+lpcbData], 0FFFFFFFFh; cchCount2
0x14007f6c6  mov     [rsp+290h+phkResult], rsi; lpString2
0x14007f6cb  or      r9d, 0FFFFFFFFh; cchCount1
0x14007f6cf  lea     r8, [rsp+290h+Data]; lpString1
0x14007f6d4  mov     edx, ebx; dwCmpFlags
0x14007f6d6  lea     ecx, [rbx+7Eh]; Locale
0x14007f6d9  call    cs:__imp_CompareStringW
0x14007f6df  cmp     eax, 2
0x14007f6e2  jz      short loc_14007F745
0x14007f6e4  mov     dword ptr [rsp+290h+lpcbData], 8; cbData
0x14007f6ec  mov     [rsp+290h+phkResult], rsi; lpData
0x14007f6f1  mov     r9d, ebx; dwType
0x14007f6f4  xor     r8d, r8d; Reserved
0x14007f6f7  lea     rdx, aStartmenuadmin; "StartMenuAdminTools"
0x14007f6fe  mov     rcx, [rsp+290h+hKey]; hKey
0x14007f703  call    cs:__imp_RegSetValueExW
0x14007f709  mov     [rsp+290h+dwResult], 0
0x14007f712  lea     rax, [rsp+290h+dwResult]
0x14007f717  mov     [rsp+290h+lpdwResult], rax; lpdwResult
0x14007f71c  mov     dword ptr [rsp+290h+lpcbData], 64h ; 'd'; uTimeout
0x14007f724  mov     dword ptr [rsp+290h+phkResult], 2; fuFlags
0x14007f72c  lea     r9, aShellmenu; "ShellMenu"
0x14007f733  xor     r8d, r8d; wParam
0x14007f736  lea     edx, [r8+1Ah]; Msg
0x14007f73a  mov     ecx, 0FFFFh; hWnd
0x14007f73f  call    cs:__imp_SendMessageTimeoutW
0x14007f745  mov     rcx, [rsp+290h+hKey]; hKey
0x14007f74a  call    cs:__imp_RegCloseKey
0x14007f750  nop
0x14007f751  lea     rcx, [rsp+290h+var_240]
0x14007f756  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x14007f75c  mov     rcx, [rbp+190h+var_10]
0x14007f763  xor     rcx, rsp; StackCookie
0x14007f766  call    __security_check_cookie
0x14007f76b  lea     r11, [rsp+290h+var_s0]
0x14007f773  mov     rbx, [r11+18h]
0x14007f777  mov     rsi, [r11+20h]
0x14007f77b  mov     rsp, r11
0x14007f77e  pop     rbp
0x14007f77f  retn
```
