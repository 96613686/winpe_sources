# GetMaxLengthSignedOfflineIssuanceLicense(void)

- ea: `0x18000ef5c`
- end: `0x18000f02c`
- name: `?GetMaxLengthSignedOfflineIssuanceLicense@@YAIXZ`
- size: `208`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016bb0`

## callees

- `0x18000ef5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f01d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f01d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ef6d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ef6d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f00a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f00a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000efb8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000efb8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000efed`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000efed`

## pseudocode

```c
__int64 GetMaxLengthSignedOfflineIssuanceLicense(void)
{
  unsigned int v0; // ebx
  DWORD cbData; // [rsp+50h] [rbp+18h] BYREF
  DWORD Type; // [rsp+58h] [rbp+20h] BYREF
  int Data; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  EnterCriticalSection(&g_csOptions);
  if ( !dword_180084B88 )
  {
    dword_180084B88 = 2031616;
    hKey = 0;
    Type = 0;
    Data = 0;
    cbData = 0;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\MSDRM", 0, 0x20019u, &hKey) )
    {
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"MaxLengthSignedOfflineIssuanceLicense", 0, &Type, (LPBYTE)&Data, &cbData)
        && Type == 4 )
      {
        dword_180084B88 = Data;
      }
      RegCloseKey(hKey);
    }
  }
  v0 = dword_180084B88;
  LeaveCriticalSection(&g_csOptions);
  return v0;
}

```

## disassembly

```asm
0x18000ef5c  push    rbp
0x18000ef5e  push    rbx
0x18000ef5f  mov     rbp, rsp
0x18000ef62  sub     rsp, 38h
0x18000ef66  lea     rcx, ?g_csOptions@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000ef6d  call    cs:__imp_EnterCriticalSection
0x18000ef73  xor     ebx, ebx
0x18000ef75  cmp     cs:dword_180084B88, ebx
0x18000ef7b  jnz     loc_18000F010
0x18000ef81  lea     rax, [rbp+hKey]
0x18000ef85  mov     cs:dword_180084B88, 1F0000h
0x18000ef8f  mov     r9d, 20019h; samDesired
0x18000ef95  mov     [rsp+38h+phkResult], rax; phkResult
0x18000ef9a  xor     r8d, r8d; ulOptions
0x18000ef9d  mov     [rbp+hKey], rbx
0x18000efa1  lea     rdx, ?g_wszSOIL_Key@@3QBGB; "SOFTWARE\\Microsoft\\MSDRM"
0x18000efa8  mov     [rbp+Type], ebx
0x18000efab  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000efb2  mov     [rbp+Data], ebx
0x18000efb5  mov     [rbp+cbData], ebx
0x18000efb8  call    cs:__imp_RegOpenKeyExW
0x18000efbe  test    eax, eax
0x18000efc0  jnz     short loc_18000F010
0x18000efc2  mov     rcx, [rbp+hKey]; hKey
0x18000efc6  lea     rax, [rbp+cbData]
0x18000efca  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18000efcf  lea     r9, [rbp+Type]; lpType
0x18000efd3  lea     rax, [rbp+Data]
0x18000efd7  mov     [rbp+cbData], 4
0x18000efde  xor     r8d, r8d; lpReserved
0x18000efe1  mov     [rsp+38h+phkResult], rax; lpData
0x18000efe6  lea     rdx, ?g_wszSOIL_ValueName@@3QBGB; "MaxLengthSignedOfflineIssuanceLicense"
0x18000efed  call    cs:__imp_RegQueryValueExW
0x18000eff3  test    eax, eax
0x18000eff5  jnz     short loc_18000F006
0x18000eff7  cmp     [rbp+Type], 4
0x18000effb  jnz     short loc_18000F006
0x18000effd  mov     eax, [rbp+Data]
0x18000f000  mov     cs:dword_180084B88, eax
0x18000f006  mov     rcx, [rbp+hKey]; hKey
0x18000f00a  call    cs:__imp_RegCloseKey
0x18000f010  mov     ebx, cs:dword_180084B88
0x18000f016  lea     rcx, ?g_csOptions@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000f01d  call    cs:__imp_LeaveCriticalSection
0x18000f023  mov     eax, ebx
0x18000f025  add     rsp, 38h
0x18000f029  pop     rbx
0x18000f02a  pop     rbp
0x18000f02b  retn
```
