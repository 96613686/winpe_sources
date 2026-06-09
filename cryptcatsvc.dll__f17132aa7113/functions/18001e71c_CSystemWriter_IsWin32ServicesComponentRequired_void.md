# CSystemWriter::IsWin32ServicesComponentRequired(void)

- ea: `0x18001e71c`
- end: `0x18001e813`
- name: `?IsWin32ServicesComponentRequired@CSystemWriter@@AEAAHXZ`
- size: `247`
- prototype: `__int64 __fastcall(CSystemWriter *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001e890`

## callees

- `0x18000be40`
- `0x18000c7e8`
- `0x18001e71c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18001e776`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18001e776`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e7a6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e7a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e7ee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e7ee`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e7d6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e7d6`

## string_xrefs

- `0x18001e793`: `System\CurrentControlSet\Control\SystemWriter`
- `0x18001e7bf`: `ReportWin32ServicesNonSystemState`

## pseudocode

```c
_BOOL8 __fastcall CSystemWriter::IsWin32ServicesComponentRequired(CSystemWriter *this)
{
  BOOL v1; // ebx
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cbData; // [rsp+3Ch] [rbp-C4h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+40h] [rbp-C0h] BYREF
  char v7; // [rsp+15Ah] [rbp+5Ah]

  hKey = 0;
  *(_DWORD *)Data = 0;
  cbData = 4;
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  VersionInformation.dwOSVersionInfoSize = 284;
  v1 = 0;
  if ( GetVersionExW(&VersionInformation) )
    LOBYTE(v1) = v7 != 1;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\SystemWriter", 0, 1u, &hKey) )
  {
    if ( !RegQueryValueExW(hKey, L"ReportWin32ServicesNonSystemState", 0, 0, Data, &cbData) )
      v1 = *(_DWORD *)Data != 0;
    RegCloseKey(hKey);
  }
  return v1;
}

```

## disassembly

```asm
0x18001e71c  mov     [rsp-8+arg_0], rbx
0x18001e721  push    rbp
0x18001e722  lea     rbp, [rsp-70h]
0x18001e727  sub     rsp, 170h
0x18001e72e  mov     rax, cs:__security_cookie
0x18001e735  xor     rax, rsp
0x18001e738  mov     [rbp+70h+var_10], rax
0x18001e73c  xor     edx, edx; Val
0x18001e73e  mov     [rsp+170h+hKey], 0
0x18001e747  mov     r8d, 118h; Size
0x18001e74d  mov     dword ptr [rsp+170h+Data], 0
0x18001e755  lea     rcx, [rsp+170h+VersionInformation.dwMajorVersion]; void *
0x18001e75a  mov     [rsp+170h+cbData], 4
0x18001e762  call    memset_0
0x18001e767  lea     rcx, [rsp+170h+VersionInformation]; lpVersionInformation
0x18001e76c  mov     [rsp+170h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x18001e774  xor     ebx, ebx
0x18001e776  call    cs:__imp_GetVersionExW
0x18001e77c  lea     r9d, [rbx+1]; samDesired
0x18001e780  test    eax, eax
0x18001e782  jz      short loc_18001E78B
0x18001e784  cmp     [rbp+70h+var_16], r9b
0x18001e788  setnz   bl
0x18001e78b  lea     rax, [rsp+170h+hKey]
0x18001e790  xor     r8d, r8d; ulOptions
0x18001e793  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Sys"...
0x18001e79a  mov     [rsp+170h+phkResult], rax; phkResult
0x18001e79f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001e7a6  call    cs:__imp_RegOpenKeyExW
0x18001e7ac  test    eax, eax
0x18001e7ae  jnz     short loc_18001E7F4
0x18001e7b0  mov     rcx, [rsp+170h+hKey]; hKey
0x18001e7b5  lea     rax, [rsp+170h+cbData]
0x18001e7ba  mov     [rsp+170h+lpcbData], rax; lpcbData
0x18001e7bf  lea     rdx, aReportwin32ser; "ReportWin32ServicesNonSystemState"
0x18001e7c6  lea     rax, [rsp+170h+Data]
0x18001e7cb  xor     r9d, r9d; lpType
0x18001e7ce  xor     r8d, r8d; lpReserved
0x18001e7d1  mov     [rsp+170h+phkResult], rax; lpData
0x18001e7d6  call    cs:__imp_RegQueryValueExW
0x18001e7dc  test    eax, eax
0x18001e7de  jnz     short loc_18001E7E9
0x18001e7e0  xor     ebx, ebx
0x18001e7e2  cmp     dword ptr [rsp+170h+Data], ebx
0x18001e7e6  setnz   bl
0x18001e7e9  mov     rcx, [rsp+170h+hKey]; hKey
0x18001e7ee  call    cs:__imp_RegCloseKey
0x18001e7f4  mov     eax, ebx
0x18001e7f6  mov     rcx, [rbp+70h+var_10]
0x18001e7fa  xor     rcx, rsp; StackCookie
0x18001e7fd  call    __security_check_cookie
0x18001e802  mov     rbx, [rsp+170h+arg_0]
0x18001e80a  add     rsp, 170h
0x18001e811  pop     rbp
0x18001e812  retn
```
