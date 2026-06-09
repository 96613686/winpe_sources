# LockDownPolicyExists

- ea: `0x180006314`
- end: `0x180006423`
- name: `LockDownPolicyExists`
- size: `271`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180005af0`
- `0x180075e60`
- `0x1800cbe28`

## callees

- `0x180006314`
- `0x18004eab4`
- `0x1800ded06`
- `0x1800ded50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006398`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006398`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000641b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000641b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180006400`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180006400`

## string_xrefs

- `0x18000636c`: `SYSTEM\CurrentControlSet\Services\RasMan\Config`
- `0x18000637e`: `OSDATA\SYSTEM\CurrentControlSet\Services\RasMan\Config`

## pseudocode

```c
__int64 LockDownPolicyExists()
{
  int v0; // eax
  const WCHAR *v1; // rdx
  unsigned int v2; // ebx
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  BYTE Data[528]; // [rsp+40h] [rbp-C0h] BYREF

  cbData = 0;
  Type = 0;
  hKey = 0;
  memset_0(Data, 0, 0x105u);
  v0 = StateSepEnabled();
  v1 = L"OSDATA\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\Config";
  if ( !v0 )
    v1 = L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\Config";
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, v1, 0, 0x20019u, &hKey)
    || (cbData = 520, RegQueryValueExW(hKey, L"LockDownProfileEntryName", 0, &Type, Data, &cbData))
    || (v2 = 1, Type - 1 > 1) )
  {
    v2 = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v2;
}

```

## disassembly

```asm
0x180006314  mov     [rsp-8+arg_0], rbx
0x180006319  push    rbp
0x18000631a  lea     rbp, [rsp-160h]
0x180006322  sub     rsp, 260h
0x180006329  mov     rax, cs:__security_cookie
0x180006330  xor     rax, rsp
0x180006333  mov     [rbp+160h+var_10], rax
0x18000633a  xor     edx, edx; Val
0x18000633c  mov     [rsp+260h+cbData], 0
0x180006344  mov     r8d, 105h; Size
0x18000634a  mov     [rsp+260h+Type], 0
0x180006352  lea     rcx, [rsp+260h+Data]; void *
0x180006357  mov     [rsp+260h+hKey], 0
0x180006360  call    memset_0
0x180006365  call    StateSepEnabled
0x18000636a  test    eax, eax
0x18000636c  lea     rcx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x180006373  lea     rax, [rsp+260h+hKey]
0x180006378  mov     r9d, 20019h; samDesired
0x18000637e  lea     rdx, aOsdataSystemCu_0; "OSDATA\\SYSTEM\\CurrentControlSet\\Serv"...
0x180006385  mov     [rsp+260h+phkResult], rax; phkResult
0x18000638a  cmovz   rdx, rcx; lpSubKey
0x18000638e  xor     r8d, r8d; ulOptions
0x180006391  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180006398  call    cs:__imp_RegOpenKeyExW
0x18000639e  test    eax, eax
0x1800063a0  jz      short loc_1800063D0
0x1800063a2  xor     ebx, ebx
0x1800063a4  mov     rcx, [rsp+260h+hKey]; hKey
0x1800063a9  test    rcx, rcx
0x1800063ac  jnz     short loc_18000641B
0x1800063ae  mov     eax, ebx
0x1800063b0  mov     rcx, [rbp+160h+var_10]
0x1800063b7  xor     rcx, rsp; StackCookie
0x1800063ba  call    __security_check_cookie
0x1800063bf  mov     rbx, [rsp+260h+arg_0]
0x1800063c7  add     rsp, 260h
0x1800063ce  pop     rbp
0x1800063cf  retn
0x1800063d0  mov     rcx, [rsp+260h+hKey]; hKey
0x1800063d5  lea     rax, [rsp+260h+cbData]
0x1800063da  mov     [rsp+260h+lpcbData], rax; lpcbData
0x1800063df  lea     r9, [rsp+260h+Type]; lpType
0x1800063e4  lea     rax, [rsp+260h+Data]
0x1800063e9  mov     [rsp+260h+cbData], 208h
0x1800063f1  xor     r8d, r8d; lpReserved
0x1800063f4  mov     [rsp+260h+phkResult], rax; lpData
0x1800063f9  lea     rdx, ValueName; "LockDownProfileEntryName"
0x180006400  call    cs:__imp_RegQueryValueExW
0x180006406  test    eax, eax
0x180006408  jnz     short loc_1800063A2
0x18000640a  mov     eax, [rsp+260h+Type]
0x18000640e  mov     ebx, 1
0x180006413  dec     eax
0x180006415  cmp     eax, ebx
0x180006417  jbe     short loc_1800063A4
0x180006419  jmp     short loc_1800063A2
0x18000641b  call    cs:__imp_RegCloseKey
0x180006421  jmp     short loc_1800063AE
```
