# _drr_UpdateLastSucceedTime

- ea: `0x1800024e4`
- end: `0x1800025d0`
- name: `_drr_UpdateLastSucceedTime`
- size: `236`
- prototype: `LSTATUS()`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180003300`

## callees

- `0x1800024e4`
- `0x18000d8d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800025a6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800025a6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180002577`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180002577`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800025b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800025b5`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000252e`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000252e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180002520`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180002520`

## pseudocode

```c
LSTATUS drr_UpdateLastSucceedTime()
{
  LSTATUS result; // eax
  DWORD dwDisposition; // [rsp+50h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-28h] BYREF
  struct _FILETIME FileTime; // [rsp+60h] [rbp-20h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+68h] [rbp-18h] BYREF

  hKey = 0;
  dwDisposition = 0;
  SystemTime = 0;
  FileTime = 0;
  GetSystemTime(&SystemTime);
  result = SystemTimeToFileTime(&SystemTime, &FileTime);
  if ( result )
  {
    result = RegCreateKeyExW(
               ::hKey,
               L"Software\\Microsoft\\Windows NT\\CurrentVersion\\DIMS",
               0,
               0,
               1u,
               0xF003Fu,
               0,
               &hKey,
               &dwDisposition);
    if ( !result )
      result = RegSetValueExW(hKey, L"LastSucceedTimestamp", 0, 0xBu, (const BYTE *)&FileTime, 8u);
  }
  if ( hKey )
    return RegCloseKey(hKey);
  return result;
}

```

## disassembly

```asm
0x1800024e4  push    rbp
0x1800024e6  mov     rbp, rsp
0x1800024e9  sub     rsp, 80h
0x1800024f0  mov     rax, cs:__security_cookie
0x1800024f7  xor     rax, rsp
0x1800024fa  mov     [rbp+var_8], rax
0x1800024fe  xorps   xmm0, xmm0
0x180002501  mov     [rbp+hKey], 0
0x180002509  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x18000250d  mov     [rbp+dwDisposition], 0
0x180002514  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x180002518  mov     qword ptr [rbp+FileTime.dwLowDateTime], 0
0x180002520  call    cs:__imp_GetSystemTime
0x180002526  lea     rdx, [rbp+FileTime]; lpFileTime
0x18000252a  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x18000252e  call    cs:__imp_SystemTimeToFileTime
0x180002534  test    eax, eax
0x180002536  jz      short loc_1800025AC
0x180002538  mov     rcx, cs:hKey; hKey
0x18000253f  lea     rax, [rbp+dwDisposition]
0x180002543  mov     [rsp+80h+lpdwDisposition], rax; lpdwDisposition
0x180002548  lea     rdx, SubKey; "Software\\Microsoft\\Windows NT\\Curren"...
0x18000254f  lea     rax, [rbp+hKey]
0x180002553  xor     r9d, r9d; lpClass
0x180002556  mov     [rsp+80h+phkResult], rax; phkResult
0x18000255b  xor     r8d, r8d; Reserved
0x18000255e  mov     [rsp+80h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180002567  mov     [rsp+80h+samDesired], 0F003Fh; samDesired
0x18000256f  mov     [rsp+80h+dwOptions], 1; dwOptions
0x180002577  call    cs:__imp_RegCreateKeyExW
0x18000257d  test    eax, eax
0x18000257f  jnz     short loc_1800025AC
0x180002581  mov     rcx, [rbp+hKey]; hKey
0x180002585  lea     rax, [rbp+FileTime]
0x180002589  mov     [rsp+80h+samDesired], 8; cbData
0x180002591  lea     rdx, ValueName; "LastSucceedTimestamp"
0x180002598  mov     r9d, 0Bh; dwType
0x18000259e  mov     qword ptr [rsp+80h+dwOptions], rax; lpData
0x1800025a3  xor     r8d, r8d; Reserved
0x1800025a6  call    cs:__imp_RegSetValueExW
0x1800025ac  mov     rcx, [rbp+hKey]; hKey
0x1800025b0  test    rcx, rcx
0x1800025b3  jz      short loc_1800025BB
0x1800025b5  call    cs:__imp_RegCloseKey
0x1800025bb  mov     rcx, [rbp+var_8]
0x1800025bf  xor     rcx, rsp; StackCookie
0x1800025c2  call    __security_check_cookie
0x1800025c7  add     rsp, 80h
0x1800025ce  pop     rbp
0x1800025cf  retn
```
