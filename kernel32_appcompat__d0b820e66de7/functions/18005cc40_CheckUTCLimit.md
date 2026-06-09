# CheckUTCLimit

- ea: `0x18005cc40`
- end: `0x18005ce01`
- name: `CheckUTCLimit`
- size: `449`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180043e44`

## callees

- `0x18005cc40`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005cdc6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005cdc6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005ccf3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005cd6c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005ccf3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005cd6c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005ccaa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005cd27`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005ccaa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005cd27`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005cdda`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005cdea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005cdda`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005cdea`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005cd7c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005cd7c`

## pseudocode

```c
__int64 __fastcall CheckUTCLimit(LPCWSTR lpValueName)
{
  unsigned int v2; // ebx
  unsigned __int64 v4; // [rsp+40h] [rbp-20h] BYREF
  __int64 pvData; // [rsp+48h] [rbp-18h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+50h] [rbp-10h] BYREF
  BYTE Data[8]; // [rsp+58h] [rbp-8h] BYREF
  DWORD pcbData; // [rsp+88h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+90h] [rbp+30h] BYREF
  HKEY hkey; // [rsp+98h] [rbp+38h] BYREF

  v4 = 0;
  *(_QWORD *)Data = 0;
  pvData = 0;
  SystemTimeAsFileTime = 0;
  hkey = 0;
  v2 = 1;
  hKey = 0;
  pcbData = 0;
  if ( !RegOpenKeyExW(HKEY_CURRENT_USER, L"SYSTEM\\CurrentControlSet\\Control\\WOW", 0, 0x20019u, &hkey) )
  {
    pcbData = 8;
    RegGetValueW(hkey, 0, L"UTCLimitTimeout", 0x20000048u, 0, &pvData, &pcbData);
    if ( pvData && !RegOpenKeyExW(hkey, L"UTCLimit", 0, 0x2001Bu, &hKey) )
    {
      pcbData = 8;
      RegGetValueW(hKey, 0, lpValueName, 0x20000048u, 0, &v4, &pcbData);
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      *(struct _FILETIME *)Data = SystemTimeAsFileTime;
      if ( *(_QWORD *)&SystemTimeAsFileTime <= v4 || *(_QWORD *)&SystemTimeAsFileTime - v4 <= 10000000 * pvData )
        v2 = 0;
      else
        RegSetValueExW(hKey, lpValueName, 0, 0xBu, Data, 8u);
      RegCloseKey(hKey);
    }
    RegCloseKey(hkey);
  }
  return v2;
}

```

## disassembly

```asm
0x18005cc40  push    rbp
0x18005cc42  push    rbx
0x18005cc43  push    rdi
0x18005cc44  mov     rbp, rsp
0x18005cc47  sub     rsp, 60h
0x18005cc4b  mov     rdi, rcx
0x18005cc4e  mov     [rbp+var_20], 0
0x18005cc56  lea     rax, [rbp+hkey]
0x18005cc5a  mov     qword ptr [rbp+Data], 0
0x18005cc62  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18005cc69  mov     [rsp+60h+phkResult], rax; phkResult
0x18005cc6e  mov     r9d, 20019h; samDesired
0x18005cc74  mov     [rbp+var_18], 0
0x18005cc7c  xor     r8d, r8d; ulOptions
0x18005cc7f  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x18005cc87  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Control\\WOW"
0x18005cc8e  mov     [rbp+hkey], 0
0x18005cc96  mov     ebx, 1
0x18005cc9b  mov     [rbp+hKey], 0
0x18005cca3  mov     [rbp+arg_8], 0
0x18005ccaa  call    cs:__imp_RegOpenKeyExW
0x18005ccb1  nop     dword ptr [rax+rax+00h]
0x18005ccb6  test    eax, eax
0x18005ccb8  jnz     loc_18005CDF6
0x18005ccbe  mov     rcx, [rbp+hkey]; hkey
0x18005ccc2  lea     rax, [rbp+arg_8]
0x18005ccc6  mov     [rsp+60h+pcbData], rax; pcbData
0x18005cccb  lea     r8, aUtclimittimeou; "UTCLimitTimeout"
0x18005ccd2  lea     rax, [rbp+var_18]
0x18005ccd6  mov     [rbp+arg_8], 8
0x18005ccdd  mov     [rsp+60h+pvData], rax; pvData
0x18005cce2  mov     r9d, 20000048h; dwFlags
0x18005cce8  xor     edx, edx; lpSubKey
0x18005ccea  mov     [rsp+60h+phkResult], 0; pdwType
0x18005ccf3  call    cs:__imp_RegGetValueW
0x18005ccfa  nop     dword ptr [rax+rax+00h]
0x18005ccff  cmp     [rbp+var_18], 0
0x18005cd04  jz      loc_18005CDE6
0x18005cd0a  mov     rcx, [rbp+hkey]; hKey
0x18005cd0e  lea     rax, [rbp+hKey]
0x18005cd12  mov     r9d, 2001Bh; samDesired
0x18005cd18  mov     [rsp+60h+phkResult], rax; phkResult
0x18005cd1d  xor     r8d, r8d; ulOptions
0x18005cd20  lea     rdx, aUtclimit; "UTCLimit"
0x18005cd27  call    cs:__imp_RegOpenKeyExW
0x18005cd2e  nop     dword ptr [rax+rax+00h]
0x18005cd33  test    eax, eax
0x18005cd35  jnz     loc_18005CDE6
0x18005cd3b  mov     rcx, [rbp+hKey]; hkey
0x18005cd3f  lea     rax, [rbp+arg_8]
0x18005cd43  mov     [rsp+60h+pcbData], rax; pcbData
0x18005cd48  mov     r9d, 20000048h; dwFlags
0x18005cd4e  lea     rax, [rbp+var_20]
0x18005cd52  mov     [rbp+arg_8], 8
0x18005cd59  mov     [rsp+60h+pvData], rax; pvData
0x18005cd5e  mov     r8, rdi; lpValue
0x18005cd61  xor     edx, edx; lpSubKey
0x18005cd63  mov     [rsp+60h+phkResult], 0; pdwType
0x18005cd6c  call    cs:__imp_RegGetValueW
0x18005cd73  nop     dword ptr [rax+rax+00h]
0x18005cd78  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18005cd7c  call    cs:__imp_GetSystemTimeAsFileTime
0x18005cd83  nop     dword ptr [rax+rax+00h]
0x18005cd88  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18005cd8c  mov     qword ptr [rbp+Data], rax
0x18005cd90  cmp     rax, [rbp+var_20]
0x18005cd94  jbe     short loc_18005CDD4
0x18005cd96  imul    rcx, [rbp+var_18], 989680h
0x18005cd9e  sub     rax, [rbp+var_20]
0x18005cda2  cmp     rax, rcx
0x18005cda5  jbe     short loc_18005CDD4
0x18005cda7  mov     rcx, [rbp+hKey]; hKey
0x18005cdab  lea     rax, [rbp+Data]
0x18005cdaf  mov     dword ptr [rsp+60h+pvData], 8; cbData
0x18005cdb7  lea     r9d, [rbx+0Ah]; dwType
0x18005cdbb  xor     r8d, r8d; Reserved
0x18005cdbe  mov     [rsp+60h+phkResult], rax; lpData
0x18005cdc3  mov     rdx, rdi; lpValueName
0x18005cdc6  call    cs:__imp_RegSetValueExW
0x18005cdcd  nop     dword ptr [rax+rax+00h]
0x18005cdd2  jmp     short loc_18005CDD6
0x18005cdd4  xor     ebx, ebx
0x18005cdd6  mov     rcx, [rbp+hKey]; hKey
0x18005cdda  call    cs:__imp_RegCloseKey
0x18005cde1  nop     dword ptr [rax+rax+00h]
0x18005cde6  mov     rcx, [rbp+hkey]; hKey
0x18005cdea  call    cs:__imp_RegCloseKey
0x18005cdf1  nop     dword ptr [rax+rax+00h]
0x18005cdf6  mov     eax, ebx
0x18005cdf8  add     rsp, 60h
0x18005cdfc  pop     rdi
0x18005cdfd  pop     rbx
0x18005cdfe  pop     rbp
0x18005cdff  retn
```
