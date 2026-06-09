# EnableAutoWPPTracingForSubComponent

- ea: `0x1800aa728`
- end: `0x1800aaa92`
- name: `EnableAutoWPPTracingForSubComponent`
- size: `874`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180022bd0`
- `0x1800cea20`
- `0x1800d9a60`
- `0x1800e0e34`

## callees

- `0x18000eb54`
- `0x180056178`
- `0x1800aa728`
- `0x1800ab130`
- `0x1800aba58`
- `0x1800e8e96`
- `0x1800e8ef0`

## import_xrefs

- `msvcrt!_wfopen_s` at `0x1800aaa31`
- `msvcrt!_wfopen_s` at `0x1800aaa31`
- `msvcrt!fclose` at `0x1800aaa47`
- `msvcrt!fclose` at `0x1800aaa47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800aaa58`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800aaa58`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800aa7e3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800aa823`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800aa7e3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800aa823`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800aa85f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800aa930`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800aa85f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800aa930`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800aa870`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800aa941`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800aa870`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800aa941`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800aa8b3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800aa8fa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800aa8b3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800aa8fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aa9f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aa9f9`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800aaa0a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800aaa0a`

## string_xrefs

- `0x1800aa79c`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Tracing\Microsoft\RemoteAccess\`

## pseudocode

```c
LSTATUS __fastcall EnableAutoWPPTracingForSubComponent(int a1)
{
  __int64 v1; // rdi
  LSTATUS result; // eax
  HKEY v3; // rcx
  wchar_t *TracingDir; // rbx
  __int64 v5; // rcx
  wchar_t *v6; // rax
  wchar_t *v7; // rdx
  __int64 v8; // r9
  wchar_t *v9; // rcx
  BYTE Data[4]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD v11; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  BYTE v13[8]; // [rsp+40h] [rbp-C0h] BYREF
  FILE *Stream; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hObject[2]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t pszDest[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey[2]; // [rsp+270h] [rbp+170h] BYREF
  char v18[524]; // [rsp+274h] [rbp+174h] BYREF

  v1 = a1;
  hKey = 0;
  *(_DWORD *)SubKey = 0;
  memset_0(v18, 0, 0x206u);
  *(_DWORD *)v13 = 0;
  *(_DWORD *)Data = 0;
  v11 = 4;
  StringCchPrintfW(
    SubKey,
    0x105u,
    L"%s%s",
    L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Tracing\\Microsoft\\RemoteAccess\\",
    &WPP_COMPONENT_INFO[274 * v1]);
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x2011Fu, &hKey);
  if ( result == 2 )
  {
    TraceEnableDisableWPPComponent(1, (unsigned int)v1);
    result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x2011Fu, &hKey);
    if ( result )
      return result;
    *(_DWORD *)Data = 1;
    RegSetValueExW(hKey, L"AutoActive", 0, 4u, Data, 4u);
    RegCloseKey(hKey);
    return 0;
  }
  if ( result )
    return result;
  v11 = 4;
  RegQueryValueExW(hKey, L"Active", 0, 0, v13, &v11);
  v3 = hKey;
  if ( *(_DWORD *)v13 )
  {
    v11 = 4;
    if ( RegQueryValueExW(hKey, L"AutoActive", 0, 0, Data, &v11) != 2 )
      goto LABEL_10;
    v3 = hKey;
    *(_DWORD *)Data = 0;
  }
  else
  {
    *(_DWORD *)Data = 1;
  }
  RegSetValueExW(v3, L"AutoActive", 0, 4u, Data, 4u);
LABEL_10:
  RegCloseKey(hKey);
  if ( !*(_DWORD *)v13 )
  {
    hObject[0] = (HANDLE)-1LL;
    TracingDir = (wchar_t *)GetTracingDir(hObject);
    if ( !TracingDir )
      return 3;
    v5 = 2147483646;
    v6 = pszDest;
    v7 = TracingDir;
    v8 = 261;
    do
    {
      if ( !v5 )
        break;
      if ( !*v7 )
        break;
      *v6++ = *v7++;
      --v5;
      --v8;
    }
    while ( v8 );
    v9 = v6 - 1;
    if ( v8 )
      v9 = v6;
    *v9 = 0;
    StringCchCatW(pszDest, 0x105u, L"\\");
    StringCchCatW(pszDest, 0x105u, &WPP_COMPONENT_INFO[274 * v1]);
    StringCchCatW(pszDest, 0x105u, L".BIN");
    LocalFree(TracingDir);
    if ( GetFileAttributesW(pszDest) != -1 )
    {
      Stream = 0;
      _wfopen_s(&Stream, pszDest, L"w");
      if ( Stream )
        fclose(Stream);
    }
    CloseHandle(hObject[0]);
    TraceEnableDisableWPPComponent(1, (unsigned int)v1);
  }
  return 0;
}

```

## disassembly

```asm
0x1800aa728  push    rbp
0x1800aa72a  push    rbx
0x1800aa72b  push    rsi
0x1800aa72c  push    rdi
0x1800aa72d  push    r14
0x1800aa72f  push    r15
0x1800aa731  lea     rbp, [rsp-398h]
0x1800aa739  sub     rsp, 498h
0x1800aa740  mov     rax, cs:__security_cookie
0x1800aa747  xor     rax, rsp
0x1800aa74a  mov     [rbp+3C0h+var_40], rax
0x1800aa751  movsxd  rdi, ecx
0x1800aa754  xor     r14d, r14d
0x1800aa757  lea     rcx, [rbp+3C0h+var_24C]; void *
0x1800aa75e  mov     [rsp+4C0h+hKey], r14
0x1800aa763  xor     edx, edx; Val
0x1800aa765  mov     dword ptr [rbp+3C0h+SubKey], r14d
0x1800aa76c  mov     r8d, 206h; Size
0x1800aa772  call    memset_0
0x1800aa777  lea     rax, WPP_COMPONENT_INFO; "RASMAN"
0x1800aa77e  mov     dword ptr [rsp+4C0h+var_480], r14d
0x1800aa783  imul    rsi, rdi, 224h
0x1800aa78a  mov     r15d, 105h
0x1800aa790  mov     dword ptr [rsp+4C0h+Data], r14d
0x1800aa795  add     rsi, rax
0x1800aa798  lea     ebx, [r14+4]
0x1800aa79c  lea     r9, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800aa7a3  mov     [rsp+4C0h+phkResult], rsi
0x1800aa7a8  lea     r8, aSS_3; "%s%s"
0x1800aa7af  mov     [rsp+4C0h+var_48C], ebx
0x1800aa7b3  mov     edx, r15d; unsigned __int64
0x1800aa7b6  lea     rcx, [rbp+3C0h+SubKey]; unsigned __int16 *
0x1800aa7bd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800aa7c2  lea     rax, [rsp+4C0h+hKey]
0x1800aa7c7  mov     r9d, 2011Fh; samDesired
0x1800aa7cd  xor     r8d, r8d; ulOptions
0x1800aa7d0  mov     [rsp+4C0h+phkResult], rax; phkResult
0x1800aa7d5  lea     rdx, [rbp+3C0h+SubKey]; lpSubKey
0x1800aa7dc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800aa7e3  call    cs:__imp_RegOpenKeyExW
0x1800aa7ea  nop     dword ptr [rax+rax+00h]
0x1800aa7ef  cmp     eax, 2
0x1800aa7f2  jnz     loc_1800AA881
0x1800aa7f8  mov     edx, edi
0x1800aa7fa  lea     ecx, [rbx-3]
0x1800aa7fd  call    TraceEnableDisableWPPComponent
0x1800aa802  lea     rax, [rsp+4C0h+hKey]
0x1800aa807  mov     r9d, 2011Fh; samDesired
0x1800aa80d  xor     r8d, r8d; ulOptions
0x1800aa810  mov     [rsp+4C0h+phkResult], rax; phkResult
0x1800aa815  lea     rdx, [rbp+3C0h+SubKey]; lpSubKey
0x1800aa81c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800aa823  call    cs:__imp_RegOpenKeyExW
0x1800aa82a  nop     dword ptr [rax+rax+00h]
0x1800aa82f  test    eax, eax
0x1800aa831  jnz     loc_1800AAA72
0x1800aa837  mov     rcx, [rsp+4C0h+hKey]; hKey
0x1800aa83c  lea     rax, [rsp+4C0h+Data]
0x1800aa841  mov     [rsp+4C0h+cbData], ebx; cbData
0x1800aa845  lea     rdx, aAutoactive; "AutoActive"
0x1800aa84c  mov     r9d, ebx; dwType
0x1800aa84f  mov     [rsp+4C0h+phkResult], rax; lpData
0x1800aa854  xor     r8d, r8d; Reserved
0x1800aa857  mov     dword ptr [rsp+4C0h+Data], 1
0x1800aa85f  call    cs:__imp_RegSetValueExW
0x1800aa866  nop     dword ptr [rax+rax+00h]
0x1800aa86b  mov     rcx, [rsp+4C0h+hKey]; hKey
0x1800aa870  call    cs:__imp_RegCloseKey
0x1800aa877  nop     dword ptr [rax+rax+00h]
0x1800aa87c  jmp     loc_1800AAA70
0x1800aa881  test    eax, eax
0x1800aa883  jnz     loc_1800AAA72
0x1800aa889  mov     rcx, [rsp+4C0h+hKey]; hKey
0x1800aa88e  lea     rax, [rsp+4C0h+var_48C]
0x1800aa893  mov     qword ptr [rsp+4C0h+cbData], rax; lpcbData
0x1800aa898  lea     rdx, aActive_0; "Active"
0x1800aa89f  lea     rax, [rsp+4C0h+var_480]
0x1800aa8a4  mov     [rsp+4C0h+var_48C], ebx
0x1800aa8a8  xor     r9d, r9d; lpType
0x1800aa8ab  mov     [rsp+4C0h+phkResult], rax; lpData
0x1800aa8b0  xor     r8d, r8d; lpReserved
0x1800aa8b3  call    cs:__imp_RegQueryValueExW
0x1800aa8ba  nop     dword ptr [rax+rax+00h]
0x1800aa8bf  lea     rdx, aAutoactive; "AutoActive"
0x1800aa8c6  mov     rcx, [rsp+4C0h+hKey]; hKey
0x1800aa8cb  cmp     dword ptr [rsp+4C0h+var_480], r14d
0x1800aa8d0  jnz     short loc_1800AA8DC
0x1800aa8d2  mov     dword ptr [rsp+4C0h+Data], 1
0x1800aa8da  jmp     short loc_1800AA91C
0x1800aa8dc  lea     rax, [rsp+4C0h+var_48C]
0x1800aa8e1  mov     [rsp+4C0h+var_48C], ebx
0x1800aa8e5  mov     qword ptr [rsp+4C0h+cbData], rax; lpcbData
0x1800aa8ea  xor     r9d, r9d; lpType
0x1800aa8ed  lea     rax, [rsp+4C0h+Data]
0x1800aa8f2  xor     r8d, r8d; lpReserved
0x1800aa8f5  mov     [rsp+4C0h+phkResult], rax; lpData
0x1800aa8fa  call    cs:__imp_RegQueryValueExW
0x1800aa901  nop     dword ptr [rax+rax+00h]
0x1800aa906  cmp     eax, 2
0x1800aa909  jnz     short loc_1800AA93C
0x1800aa90b  mov     rcx, [rsp+4C0h+hKey]; hKey
0x1800aa910  lea     rdx, aAutoactive; "AutoActive"
0x1800aa917  mov     dword ptr [rsp+4C0h+Data], r14d
0x1800aa91c  lea     rax, [rsp+4C0h+Data]
0x1800aa921  mov     [rsp+4C0h+cbData], ebx; cbData
0x1800aa925  mov     r9d, ebx; dwType
0x1800aa928  mov     [rsp+4C0h+phkResult], rax; lpData
0x1800aa92d  xor     r8d, r8d; Reserved
0x1800aa930  call    cs:__imp_RegSetValueExW
0x1800aa937  nop     dword ptr [rax+rax+00h]
0x1800aa93c  mov     rcx, [rsp+4C0h+hKey]; hKey
0x1800aa941  call    cs:__imp_RegCloseKey
0x1800aa948  nop     dword ptr [rax+rax+00h]
0x1800aa94d  cmp     dword ptr [rsp+4C0h+var_480], r14d
0x1800aa952  jnz     loc_1800AAA70
0x1800aa958  mov     [rsp+4C0h+hObject], 0FFFFFFFFFFFFFFFFh
0x1800aa961  lea     rcx, [rsp+4C0h+hObject]
0x1800aa966  call    GetTracingDir
0x1800aa96b  mov     rbx, rax
0x1800aa96e  test    rax, rax
0x1800aa971  jnz     short loc_1800AA97B
0x1800aa973  lea     eax, [rbx+3]
0x1800aa976  jmp     loc_1800AAA72
0x1800aa97b  mov     ecx, 7FFFFFFEh
0x1800aa980  lea     rax, [rsp+4C0h+pszDest]
0x1800aa985  mov     rdx, rbx
0x1800aa988  mov     r9, r15
0x1800aa98b  test    rcx, rcx
0x1800aa98e  jz      short loc_1800AA9AF
0x1800aa990  movzx   r8d, word ptr [rdx]
0x1800aa994  test    r8w, r8w
0x1800aa998  jz      short loc_1800AA9AF
0x1800aa99a  mov     [rax], r8w
0x1800aa99e  add     rdx, 2
0x1800aa9a2  add     rax, 2
0x1800aa9a6  dec     rcx
0x1800aa9a9  sub     r9, 1
0x1800aa9ad  jnz     short loc_1800AA98B
0x1800aa9af  test    r9, r9
0x1800aa9b2  lea     rcx, [rax-2]
0x1800aa9b6  lea     r8, Source; "\\"
0x1800aa9bd  mov     rdx, r15; cchDest
0x1800aa9c0  cmovnz  rcx, rax
0x1800aa9c4  mov     [rcx], r14w
0x1800aa9c8  lea     rcx, [rsp+4C0h+pszDest]; pszDest
0x1800aa9cd  call    StringCchCatW
0x1800aa9d2  mov     r8, rsi; pszSrc
0x1800aa9d5  lea     rcx, [rsp+4C0h+pszDest]; pszDest
0x1800aa9da  mov     rdx, r15; cchDest
0x1800aa9dd  call    StringCchCatW
0x1800aa9e2  lea     r8, aBin; ".BIN"
0x1800aa9e9  mov     rdx, r15; cchDest
0x1800aa9ec  lea     rcx, [rsp+4C0h+pszDest]; pszDest
0x1800aa9f1  call    StringCchCatW
0x1800aa9f6  mov     rcx, rbx; hMem
0x1800aa9f9  call    cs:__imp_LocalFree
0x1800aaa00  nop     dword ptr [rax+rax+00h]
0x1800aaa05  lea     rcx, [rsp+4C0h+pszDest]; lpFileName
0x1800aaa0a  call    cs:__imp_GetFileAttributesW
0x1800aaa11  nop     dword ptr [rax+rax+00h]
0x1800aaa16  cmp     eax, 0FFFFFFFFh
0x1800aaa19  jz      short loc_1800AAA53
0x1800aaa1b  lea     r8, aW; "w"
0x1800aaa22  mov     [rsp+4C0h+Stream], r14
0x1800aaa27  lea     rdx, [rsp+4C0h+pszDest]; FileName
0x1800aaa2c  lea     rcx, [rsp+4C0h+Stream]; Stream
0x1800aaa31  call    cs:__imp__wfopen_s
0x1800aaa38  nop     dword ptr [rax+rax+00h]
0x1800aaa3d  mov     rcx, [rsp+4C0h+Stream]; Stream
0x1800aaa42  test    rcx, rcx
0x1800aaa45  jz      short loc_1800AAA53
0x1800aaa47  call    cs:__imp_fclose
0x1800aaa4e  nop     dword ptr [rax+rax+00h]
0x1800aaa53  mov     rcx, [rsp+4C0h+hObject]; hObject
0x1800aaa58  call    cs:__imp_CloseHandle
0x1800aaa5f  nop     dword ptr [rax+rax+00h]
0x1800aaa64  mov     edx, edi
0x1800aaa66  mov     ecx, 1
0x1800aaa6b  call    TraceEnableDisableWPPComponent
0x1800aaa70  xor     eax, eax
0x1800aaa72  mov     rcx, [rbp+3C0h+var_40]
0x1800aaa79  xor     rcx, rsp; StackCookie
0x1800aaa7c  call    __security_check_cookie
0x1800aaa81  add     rsp, 498h
0x1800aaa88  pop     r15
0x1800aaa8a  pop     r14
0x1800aaa8c  pop     rdi
0x1800aaa8d  pop     rsi
0x1800aaa8e  pop     rbx
0x1800aaa8f  pop     rbp
0x1800aaa90  retn
```
