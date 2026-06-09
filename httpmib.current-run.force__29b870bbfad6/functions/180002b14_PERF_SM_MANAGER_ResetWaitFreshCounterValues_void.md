# PERF_SM_MANAGER::ResetWaitFreshCounterValues(void)

- ea: `0x180002b14`
- end: `0x180002c58`
- name: `?ResetWaitFreshCounterValues@PERF_SM_MANAGER@@AEAAXXZ`
- size: `324`
- prototype: `void __fastcall(PERF_SM_MANAGER *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x1800027f8`

## callees

- `0x180002b14`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002b61`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002b61`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002b9a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002bdf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002c24`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002b9a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002bdf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002c24`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002c47`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002c47`

## string_xrefs

- `0x180002b5a`: `System\CurrentControlSet\Services\W3SVC\Performance`

## pseudocode

```c
void __fastcall PERF_SM_MANAGER::ResetWaitFreshCounterValues(PERF_SM_MANAGER *this)
{
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+18h] BYREF
  DWORD Type; // [rsp+60h] [rbp+20h] BYREF
  int Data; // [rsp+68h] [rbp+28h] BYREF

  hKey = 0;
  cbData = 0;
  Type = 0;
  Data = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\W3SVC\\Performance", 0, 1u, &hKey) )
  {
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"FreshTimeForCounters", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && Data )
      *((_DWORD *)this + 18) = Data;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"CheckCountersEveryNMiliseconds", 0, &Type, (LPBYTE)&Data, &cbData)
      && Type == 4
      && Data )
    {
      *((_DWORD *)this + 20) = Data;
    }
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"NumberOfTimesToCheckCounters", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && Data )
      *((_DWORD *)this + 19) = Data;
    if ( hKey )
      RegCloseKey(hKey);
  }
}

```

## disassembly

```asm
0x180002b14  mov     [rsp-8+arg_0], rbx
0x180002b19  push    rbp
0x180002b1a  mov     rbp, rsp
0x180002b1d  sub     rsp, 40h
0x180002b21  mov     rbx, rcx
0x180002b24  mov     [rbp+hKey], 0
0x180002b2c  lea     rax, [rbp+hKey]
0x180002b30  mov     [rbp+cbData], 0
0x180002b37  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180002b3e  mov     [rsp+40h+phkResult], rax; phkResult
0x180002b43  mov     r9d, 1; samDesired
0x180002b49  mov     [rbp+Type], 0
0x180002b50  xor     r8d, r8d; ulOptions
0x180002b53  mov     [rbp+Data], 0
0x180002b5a  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\W3"...
0x180002b61  call    cs:__imp_RegOpenKeyExW
0x180002b67  test    eax, eax
0x180002b69  jnz     loc_180002C4D
0x180002b6f  mov     rcx, [rbp+hKey]; hKey
0x180002b73  lea     rax, [rbp+cbData]
0x180002b77  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180002b7c  lea     r9, [rbp+Type]; lpType
0x180002b80  lea     rax, [rbp+Data]
0x180002b84  mov     [rbp+cbData], 4
0x180002b8b  xor     r8d, r8d; lpReserved
0x180002b8e  mov     [rsp+40h+phkResult], rax; lpData
0x180002b93  lea     rdx, ValueName; "FreshTimeForCounters"
0x180002b9a  call    cs:__imp_RegQueryValueExW
0x180002ba0  test    eax, eax
0x180002ba2  jnz     short loc_180002BB4
0x180002ba4  cmp     [rbp+Type], 4
0x180002ba8  jnz     short loc_180002BB4
0x180002baa  mov     eax, [rbp+Data]
0x180002bad  test    eax, eax
0x180002baf  jz      short loc_180002BB4
0x180002bb1  mov     [rbx+48h], eax
0x180002bb4  mov     rcx, [rbp+hKey]; hKey
0x180002bb8  lea     rax, [rbp+cbData]
0x180002bbc  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180002bc1  lea     r9, [rbp+Type]; lpType
0x180002bc5  lea     rax, [rbp+Data]
0x180002bc9  mov     [rbp+cbData], 4
0x180002bd0  xor     r8d, r8d; lpReserved
0x180002bd3  mov     [rsp+40h+phkResult], rax; lpData
0x180002bd8  lea     rdx, aCheckcounterse; "CheckCountersEveryNMiliseconds"
0x180002bdf  call    cs:__imp_RegQueryValueExW
0x180002be5  test    eax, eax
0x180002be7  jnz     short loc_180002BF9
0x180002be9  cmp     [rbp+Type], 4
0x180002bed  jnz     short loc_180002BF9
0x180002bef  mov     eax, [rbp+Data]
0x180002bf2  test    eax, eax
0x180002bf4  jz      short loc_180002BF9
0x180002bf6  mov     [rbx+50h], eax
0x180002bf9  mov     rcx, [rbp+hKey]; hKey
0x180002bfd  lea     rax, [rbp+cbData]
0x180002c01  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180002c06  lea     r9, [rbp+Type]; lpType
0x180002c0a  lea     rax, [rbp+Data]
0x180002c0e  mov     [rbp+cbData], 4
0x180002c15  xor     r8d, r8d; lpReserved
0x180002c18  mov     [rsp+40h+phkResult], rax; lpData
0x180002c1d  lea     rdx, aNumberoftimest; "NumberOfTimesToCheckCounters"
0x180002c24  call    cs:__imp_RegQueryValueExW
0x180002c2a  test    eax, eax
0x180002c2c  jnz     short loc_180002C3E
0x180002c2e  cmp     [rbp+Type], 4
0x180002c32  jnz     short loc_180002C3E
0x180002c34  mov     eax, [rbp+Data]
0x180002c37  test    eax, eax
0x180002c39  jz      short loc_180002C3E
0x180002c3b  mov     [rbx+4Ch], eax
0x180002c3e  mov     rcx, [rbp+hKey]; hKey
0x180002c42  test    rcx, rcx
0x180002c45  jz      short loc_180002C4D
0x180002c47  call    cs:__imp_RegCloseKey
0x180002c4d  mov     rbx, [rsp+40h+arg_0]
0x180002c52  add     rsp, 40h
0x180002c56  pop     rbp
0x180002c57  retn
```
