# CheckUTCLimit

- ea: `0x1800577a4`
- end: `0x180057934`
- name: `CheckUTCLimit`
- size: `400`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800402f0`

## callees

- `0x1800577a4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005790c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005790c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180057851`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800578be`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180057851`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800578be`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005780e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005787f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005780e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005787f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005791a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057924`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005791a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057924`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800578c8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800578c8`

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
0x1800577a4  push    rbp
0x1800577a6  push    rbx
0x1800577a7  push    rdi
0x1800577a8  mov     rbp, rsp
0x1800577ab  sub     rsp, 60h
0x1800577af  mov     rdi, rcx
0x1800577b2  mov     [rbp+var_20], 0
0x1800577ba  lea     rax, [rbp+hkey]
0x1800577be  mov     qword ptr [rbp+Data], 0
0x1800577c6  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800577cd  mov     [rsp+60h+phkResult], rax; phkResult
0x1800577d2  mov     r9d, 20019h; samDesired
0x1800577d8  mov     [rbp+var_18], 0
0x1800577e0  xor     r8d, r8d; ulOptions
0x1800577e3  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800577eb  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Control\\WOW"
0x1800577f2  mov     [rbp+hkey], 0
0x1800577fa  mov     ebx, 1
0x1800577ff  mov     [rbp+hKey], 0
0x180057807  mov     [rbp+arg_8], 0
0x18005780e  call    cs:__imp_RegOpenKeyExW
0x180057814  test    eax, eax
0x180057816  jnz     loc_18005792A
0x18005781c  mov     rcx, [rbp+hkey]; hkey
0x180057820  lea     rax, [rbp+arg_8]
0x180057824  mov     [rsp+60h+pcbData], rax; pcbData
0x180057829  lea     r8, aUtclimittimeou; "UTCLimitTimeout"
0x180057830  lea     rax, [rbp+var_18]
0x180057834  mov     [rbp+arg_8], 8
0x18005783b  mov     [rsp+60h+pvData], rax; pvData
0x180057840  mov     r9d, 20000048h; dwFlags
0x180057846  xor     edx, edx; lpSubKey
0x180057848  mov     [rsp+60h+phkResult], 0; pdwType
0x180057851  call    cs:__imp_RegGetValueW
0x180057857  cmp     [rbp+var_18], 0
0x18005785c  jz      loc_180057920
0x180057862  mov     rcx, [rbp+hkey]; hKey
0x180057866  lea     rax, [rbp+hKey]
0x18005786a  mov     r9d, 2001Bh; samDesired
0x180057870  mov     [rsp+60h+phkResult], rax; phkResult
0x180057875  xor     r8d, r8d; ulOptions
0x180057878  lea     rdx, aUtclimit; "UTCLimit"
0x18005787f  call    cs:__imp_RegOpenKeyExW
0x180057885  test    eax, eax
0x180057887  jnz     loc_180057920
0x18005788d  mov     rcx, [rbp+hKey]; hkey
0x180057891  lea     rax, [rbp+arg_8]
0x180057895  mov     [rsp+60h+pcbData], rax; pcbData
0x18005789a  mov     r9d, 20000048h; dwFlags
0x1800578a0  lea     rax, [rbp+var_20]
0x1800578a4  mov     [rbp+arg_8], 8
0x1800578ab  mov     [rsp+60h+pvData], rax; pvData
0x1800578b0  mov     r8, rdi; lpValue
0x1800578b3  xor     edx, edx; lpSubKey
0x1800578b5  mov     [rsp+60h+phkResult], 0; pdwType
0x1800578be  call    cs:__imp_RegGetValueW
0x1800578c4  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800578c8  call    cs:__imp_GetSystemTimeAsFileTime
0x1800578ce  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800578d2  mov     qword ptr [rbp+Data], rax
0x1800578d6  cmp     rax, [rbp+var_20]
0x1800578da  jbe     short loc_180057914
0x1800578dc  imul    rcx, [rbp+var_18], 989680h
0x1800578e4  sub     rax, [rbp+var_20]
0x1800578e8  cmp     rax, rcx
0x1800578eb  jbe     short loc_180057914
0x1800578ed  mov     rcx, [rbp+hKey]; hKey
0x1800578f1  lea     rax, [rbp+Data]
0x1800578f5  mov     dword ptr [rsp+60h+pvData], 8; cbData
0x1800578fd  lea     r9d, [rbx+0Ah]; dwType
0x180057901  xor     r8d, r8d; Reserved
0x180057904  mov     [rsp+60h+phkResult], rax; lpData
0x180057909  mov     rdx, rdi; lpValueName
0x18005790c  call    cs:__imp_RegSetValueExW
0x180057912  jmp     short loc_180057916
0x180057914  xor     ebx, ebx
0x180057916  mov     rcx, [rbp+hKey]; hKey
0x18005791a  call    cs:__imp_RegCloseKey
0x180057920  mov     rcx, [rbp+hkey]; hKey
0x180057924  call    cs:__imp_RegCloseKey
0x18005792a  mov     eax, ebx
0x18005792c  add     rsp, 60h
0x180057930  pop     rdi
0x180057931  pop     rbx
0x180057932  pop     rbp
0x180057933  retn
```
