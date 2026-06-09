# EnableAutoWPPTracingForSubComponent

- ea: `0x1800bc1dc`
- end: `0x1800bc4d7`
- name: `EnableAutoWPPTracingForSubComponent`
- size: `763`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800bc148`

## callees

- `0x1800203dc`
- `0x18007e3a8`
- `0x18008d814`
- `0x1800bc1dc`
- `0x1800bcad0`
- `0x1800bd2ac`
- `0x1800ded06`
- `0x1800ded50`

## import_xrefs

- `msvcrt!fclose` at `0x1800bc496`
- `msvcrt!fclose` at `0x1800bc496`
- `msvcrt!_wfopen_s` at `0x1800bc486`
- `msvcrt!_wfopen_s` at `0x1800bc486`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bc2a7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bc2da`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bc2a7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bc2da`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800bc310`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800bc3cc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800bc310`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800bc3cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bc31b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bc3d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bc31b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bc3d7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800bc358`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800bc399`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800bc358`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800bc399`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bc456`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bc456`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bc4a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bc4a1`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800bc461`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800bc461`

## string_xrefs

- `0x1800bc25b`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Tracing\Microsoft\RemoteAccess\`

## pseudocode

```c
LSTATUS __fastcall EnableAutoWPPTracingForSubComponent(int a1)
{
  __int64 v1; // rdi
  LSTATUS result; // eax
  __int64 v3; // rcx
  HKEY v4; // rcx
  const wchar_t *TracingDir; // rax
  wchar_t *v6; // rbx
  __int64 v7; // rcx
  BYTE Data[4]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD v9; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  BYTE v11[8]; // [rsp+40h] [rbp-C0h] BYREF
  FILE *Stream; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hObject[2]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t FileName[264]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t pszDest[2]; // [rsp+270h] [rbp+170h] BYREF
  _BYTE v16[524]; // [rsp+274h] [rbp+174h] BYREF

  v1 = a1;
  hKey = 0;
  *(_DWORD *)pszDest = 0;
  memset_0(v16, 0, 0x206u);
  *(_DWORD *)v11 = 0;
  *(_DWORD *)Data = 0;
  v9 = 4;
  StringCchPrintfW(
    pszDest,
    0x105u,
    L"%s%s",
    L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Tracing\\Microsoft\\RemoteAccess\\",
    &WPP_COMPONENT_INFO[274 * v1]);
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, pszDest, 0, 0x2011Fu, &hKey);
  if ( result == 2 )
  {
    TraceEnableDisableWPPComponent(v3, (unsigned int)v1);
    result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, pszDest, 0, 0x2011Fu, &hKey);
    if ( result )
      return result;
    *(_DWORD *)Data = 1;
    RegSetValueExW(hKey, L"AutoActive", 0, 4u, Data, 4u);
    RegCloseKey(hKey);
    return 0;
  }
  if ( result )
    return result;
  v9 = 4;
  RegQueryValueExW(hKey, L"Active", 0, 0, v11, &v9);
  v4 = hKey;
  if ( *(_DWORD *)v11 )
  {
    v9 = 4;
    if ( RegQueryValueExW(hKey, L"AutoActive", 0, 0, Data, &v9) != 2 )
      goto LABEL_10;
    v4 = hKey;
    *(_DWORD *)Data = 0;
  }
  else
  {
    *(_DWORD *)Data = 1;
  }
  RegSetValueExW(v4, L"AutoActive", 0, 4u, Data, 4u);
LABEL_10:
  RegCloseKey(hKey);
  if ( !*(_DWORD *)v11 )
  {
    hObject[0] = (HANDLE)-1LL;
    TracingDir = (const wchar_t *)GetTracingDir(hObject);
    v6 = (wchar_t *)TracingDir;
    if ( !TracingDir )
      return 3;
    StringCchCopyW(FileName, 0x105u, TracingDir);
    StringCchCatW(FileName, 0x105u, L"\\");
    StringCchCatW(FileName, 0x105u, &WPP_COMPONENT_INFO[274 * v1]);
    StringCchCatW(FileName, 0x105u, L".BIN");
    LocalFree(v6);
    if ( GetFileAttributesW(FileName) != -1 )
    {
      Stream = 0;
      _wfopen_s(&Stream, FileName, L"w");
      if ( Stream )
        fclose(Stream);
    }
    CloseHandle(hObject[0]);
    TraceEnableDisableWPPComponent(v7, (unsigned int)v1);
  }
  return 0;
}

```

## disassembly

```asm
0x1800bc1dc  mov     [rsp-8+arg_8], rbx
0x1800bc1e1  mov     [rsp-8+arg_10], rsi
0x1800bc1e6  push    rbp
0x1800bc1e7  push    rdi
0x1800bc1e8  push    r15
0x1800bc1ea  lea     rbp, [rsp-390h]
0x1800bc1f2  sub     rsp, 490h
0x1800bc1f9  mov     rax, cs:__security_cookie
0x1800bc200  xor     rax, rsp
0x1800bc203  mov     [rbp+3A0h+var_20], rax
0x1800bc20a  movsxd  rdi, ecx
0x1800bc20d  xor     edx, edx; Val
0x1800bc20f  lea     rcx, [rbp+3A0h+var_22C]; void *
0x1800bc216  mov     [rsp+4A0h+hKey], 0
0x1800bc21f  mov     r8d, 206h; Size
0x1800bc225  mov     dword ptr [rbp+3A0h+pszDest], 0
0x1800bc22f  call    memset_0
0x1800bc234  lea     rax, WPP_COMPONENT_INFO; "RASMAN"
0x1800bc23b  mov     dword ptr [rsp+4A0h+var_460], 0
0x1800bc243  imul    rsi, rdi, 224h
0x1800bc24a  mov     r15d, 105h
0x1800bc250  mov     dword ptr [rsp+4A0h+Data], 0
0x1800bc258  add     rsi, rax
0x1800bc25b  lea     r9, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800bc262  mov     ebx, 4
0x1800bc267  mov     [rsp+4A0h+phkResult], rsi
0x1800bc26c  lea     r8, aSS_3; "%s%s"
0x1800bc273  mov     [rsp+4A0h+var_46C], ebx
0x1800bc277  mov     edx, r15d; cchDest
0x1800bc27a  lea     rcx, [rbp+3A0h+pszDest]; pszDest
0x1800bc281  call    StringCchPrintfW
0x1800bc286  lea     rax, [rsp+4A0h+hKey]
0x1800bc28b  mov     r9d, 2011Fh; samDesired
0x1800bc291  xor     r8d, r8d; ulOptions
0x1800bc294  mov     [rsp+4A0h+phkResult], rax; phkResult
0x1800bc299  lea     rdx, [rbp+3A0h+pszDest]; lpSubKey
0x1800bc2a0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800bc2a7  call    cs:__imp_RegOpenKeyExW
0x1800bc2ad  cmp     eax, 2
0x1800bc2b0  jnz     short loc_1800BC326
0x1800bc2b2  mov     edx, edi
0x1800bc2b4  call    TraceEnableDisableWPPComponent
0x1800bc2b9  lea     rax, [rsp+4A0h+hKey]
0x1800bc2be  mov     r9d, 2011Fh; samDesired
0x1800bc2c4  xor     r8d, r8d; ulOptions
0x1800bc2c7  mov     [rsp+4A0h+phkResult], rax; phkResult
0x1800bc2cc  lea     rdx, [rbp+3A0h+pszDest]; lpSubKey
0x1800bc2d3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800bc2da  call    cs:__imp_RegOpenKeyExW
0x1800bc2e0  test    eax, eax
0x1800bc2e2  jnz     loc_1800BC4B0
0x1800bc2e8  mov     rcx, [rsp+4A0h+hKey]; hKey
0x1800bc2ed  lea     rax, [rsp+4A0h+Data]
0x1800bc2f2  mov     [rsp+4A0h+cbData], ebx; cbData
0x1800bc2f6  lea     rdx, aAutoactive; "AutoActive"
0x1800bc2fd  mov     r9d, ebx; dwType
0x1800bc300  mov     [rsp+4A0h+phkResult], rax; lpData
0x1800bc305  xor     r8d, r8d; Reserved
0x1800bc308  mov     dword ptr [rsp+4A0h+Data], 1
0x1800bc310  call    cs:__imp_RegSetValueExW
0x1800bc316  mov     rcx, [rsp+4A0h+hKey]; hKey
0x1800bc31b  call    cs:__imp_RegCloseKey
0x1800bc321  jmp     loc_1800BC4AE
0x1800bc326  test    eax, eax
0x1800bc328  jnz     loc_1800BC4B0
0x1800bc32e  mov     rcx, [rsp+4A0h+hKey]; hKey
0x1800bc333  lea     rax, [rsp+4A0h+var_46C]
0x1800bc338  mov     qword ptr [rsp+4A0h+cbData], rax; lpcbData
0x1800bc33d  lea     rdx, aActive; "Active"
0x1800bc344  lea     rax, [rsp+4A0h+var_460]
0x1800bc349  mov     [rsp+4A0h+var_46C], ebx
0x1800bc34d  xor     r9d, r9d; lpType
0x1800bc350  mov     [rsp+4A0h+phkResult], rax; lpData
0x1800bc355  xor     r8d, r8d; lpReserved
0x1800bc358  call    cs:__imp_RegQueryValueExW
0x1800bc35e  cmp     dword ptr [rsp+4A0h+var_460], 0
0x1800bc363  lea     rdx, aAutoactive; "AutoActive"
0x1800bc36a  mov     rcx, [rsp+4A0h+hKey]; hKey
0x1800bc36f  jnz     short loc_1800BC37B
0x1800bc371  mov     dword ptr [rsp+4A0h+Data], 1
0x1800bc379  jmp     short loc_1800BC3B8
0x1800bc37b  lea     rax, [rsp+4A0h+var_46C]
0x1800bc380  mov     [rsp+4A0h+var_46C], ebx
0x1800bc384  mov     qword ptr [rsp+4A0h+cbData], rax; lpcbData
0x1800bc389  xor     r9d, r9d; lpType
0x1800bc38c  lea     rax, [rsp+4A0h+Data]
0x1800bc391  xor     r8d, r8d; lpReserved
0x1800bc394  mov     [rsp+4A0h+phkResult], rax; lpData
0x1800bc399  call    cs:__imp_RegQueryValueExW
0x1800bc39f  cmp     eax, 2
0x1800bc3a2  jnz     short loc_1800BC3D2
0x1800bc3a4  mov     rcx, [rsp+4A0h+hKey]; hKey
0x1800bc3a9  lea     rdx, aAutoactive; "AutoActive"
0x1800bc3b0  mov     dword ptr [rsp+4A0h+Data], 0
0x1800bc3b8  lea     rax, [rsp+4A0h+Data]
0x1800bc3bd  mov     [rsp+4A0h+cbData], ebx; cbData
0x1800bc3c1  mov     r9d, ebx; dwType
0x1800bc3c4  mov     [rsp+4A0h+phkResult], rax; lpData
0x1800bc3c9  xor     r8d, r8d; Reserved
0x1800bc3cc  call    cs:__imp_RegSetValueExW
0x1800bc3d2  mov     rcx, [rsp+4A0h+hKey]; hKey
0x1800bc3d7  call    cs:__imp_RegCloseKey
0x1800bc3dd  cmp     dword ptr [rsp+4A0h+var_460], 0
0x1800bc3e2  jnz     loc_1800BC4AE
0x1800bc3e8  mov     [rsp+4A0h+hObject], 0FFFFFFFFFFFFFFFFh
0x1800bc3f1  lea     rcx, [rsp+4A0h+hObject]
0x1800bc3f6  call    GetTracingDir
0x1800bc3fb  mov     rbx, rax
0x1800bc3fe  test    rax, rax
0x1800bc401  jnz     short loc_1800BC40B
0x1800bc403  lea     eax, [rbx+3]
0x1800bc406  jmp     loc_1800BC4B0
0x1800bc40b  mov     r8, rbx; pszSrc
0x1800bc40e  lea     rcx, [rsp+4A0h+FileName]; pszDest
0x1800bc413  mov     rdx, r15; cchDest
0x1800bc416  call    StringCchCopyW
0x1800bc41b  lea     r8, asc_1800E75F8; "\\"
0x1800bc422  mov     rdx, r15; cchDest
0x1800bc425  lea     rcx, [rsp+4A0h+FileName]; pszDest
0x1800bc42a  call    StringCchCatW
0x1800bc42f  mov     r8, rsi; pszSrc
0x1800bc432  lea     rcx, [rsp+4A0h+FileName]; pszDest
0x1800bc437  mov     rdx, r15; cchDest
0x1800bc43a  call    StringCchCatW
0x1800bc43f  lea     r8, aBin; ".BIN"
0x1800bc446  mov     rdx, r15; cchDest
0x1800bc449  lea     rcx, [rsp+4A0h+FileName]; pszDest
0x1800bc44e  call    StringCchCatW
0x1800bc453  mov     rcx, rbx; hMem
0x1800bc456  call    cs:__imp_LocalFree
0x1800bc45c  lea     rcx, [rsp+4A0h+FileName]; lpFileName
0x1800bc461  call    cs:__imp_GetFileAttributesW
0x1800bc467  cmp     eax, 0FFFFFFFFh
0x1800bc46a  jz      short loc_1800BC49C
0x1800bc46c  lea     r8, aW; "w"
0x1800bc473  mov     [rsp+4A0h+Stream], 0
0x1800bc47c  lea     rdx, [rsp+4A0h+FileName]; FileName
0x1800bc481  lea     rcx, [rsp+4A0h+Stream]; Stream
0x1800bc486  call    cs:__imp__wfopen_s
0x1800bc48c  mov     rcx, [rsp+4A0h+Stream]; Stream
0x1800bc491  test    rcx, rcx
0x1800bc494  jz      short loc_1800BC49C
0x1800bc496  call    cs:__imp_fclose
0x1800bc49c  mov     rcx, [rsp+4A0h+hObject]; hObject
0x1800bc4a1  call    cs:__imp_CloseHandle
0x1800bc4a7  mov     edx, edi
0x1800bc4a9  call    TraceEnableDisableWPPComponent
0x1800bc4ae  xor     eax, eax
0x1800bc4b0  mov     rcx, [rbp+3A0h+var_20]
0x1800bc4b7  xor     rcx, rsp; StackCookie
0x1800bc4ba  call    __security_check_cookie
0x1800bc4bf  lea     r11, [rsp+4A0h+var_10]
0x1800bc4c7  mov     rbx, [r11+28h]
0x1800bc4cb  mov     rsi, [r11+30h]
0x1800bc4cf  mov     rsp, r11
0x1800bc4d2  pop     r15
0x1800bc4d4  pop     rdi
0x1800bc4d5  pop     rbp
0x1800bc4d6  retn
```
