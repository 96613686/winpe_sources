# GetStartupWaitHint(void)

- ea: `0x180001958`
- end: `0x180001a04`
- name: `?GetStartupWaitHint@@YAKXZ`
- size: `172`
- prototype: `unsigned int(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180001e60`
- `0x180002760`

## callees

- `0x180001958`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800019f5`
- `ADVAPI32!RegCloseKey` at `0x1800019f5`
- `ADVAPI32!RegQueryValueExA` at `0x1800019d9`
- `ADVAPI32!RegQueryValueExA` at `0x1800019d9`
- `ADVAPI32!RegOpenKeyExA` at `0x1800019a4`
- `ADVAPI32!RegOpenKeyExA` at `0x1800019a4`

## string_xrefs

- `0x180001983`: `SYSTEM\CurrentControlSet\Services\IISADMIN`

## pseudocode

```c
__int64 GetStartupWaitHint(void)
{
  unsigned int v0; // ebx
  DWORD cbData; // [rsp+50h] [rbp+18h] BYREF
  DWORD Type; // [rsp+58h] [rbp+20h] BYREF
  unsigned int Data; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  hKey = 0;
  Type = 0;
  cbData = 0;
  Data = 0;
  v0 = 180000;
  if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, "SYSTEM\\CurrentControlSet\\Services\\IISADMIN", 0, 1u, &hKey) )
  {
    cbData = 4;
    if ( !RegQueryValueExA(hKey, "StartupWaitHintInMilliseconds", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && Data )
      v0 = Data;
    RegCloseKey(hKey);
  }
  return v0;
}

```

## disassembly

```asm
0x180001958  push    rbp
0x18000195a  push    rbx
0x18000195b  mov     rbp, rsp
0x18000195e  sub     rsp, 38h
0x180001962  lea     rax, [rbp+hKey]
0x180001966  mov     [rbp+hKey], 0
0x18000196e  mov     r9d, 1; samDesired
0x180001974  mov     [rsp+38h+phkResult], rax; phkResult
0x180001979  xor     r8d, r8d; ulOptions
0x18000197c  mov     [rbp+Type], 0
0x180001983  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\II"...
0x18000198a  mov     [rbp+cbData], 0
0x180001991  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180001998  mov     [rbp+Data], 0
0x18000199f  mov     ebx, 2BF20h
0x1800019a4  call    cs:__imp_RegOpenKeyExA
0x1800019aa  test    eax, eax
0x1800019ac  jnz     short loc_1800019FB
0x1800019ae  mov     rcx, [rbp+hKey]; hKey
0x1800019b2  lea     rax, [rbp+cbData]
0x1800019b6  mov     [rsp+38h+lpcbData], rax; lpcbData
0x1800019bb  lea     r9, [rbp+Type]; lpType
0x1800019bf  lea     rax, [rbp+Data]
0x1800019c3  mov     [rbp+cbData], 4
0x1800019ca  xor     r8d, r8d; lpReserved
0x1800019cd  mov     [rsp+38h+phkResult], rax; lpData
0x1800019d2  lea     rdx, ValueName; "StartupWaitHintInMilliseconds"
0x1800019d9  call    cs:__imp_RegQueryValueExA
0x1800019df  test    eax, eax
0x1800019e1  jnz     short loc_1800019F1
0x1800019e3  cmp     [rbp+Type], 4
0x1800019e7  jnz     short loc_1800019F1
0x1800019e9  mov     ecx, [rbp+Data]
0x1800019ec  test    ecx, ecx
0x1800019ee  cmovnz  ebx, ecx
0x1800019f1  mov     rcx, [rbp+hKey]; hKey
0x1800019f5  call    cs:__imp_RegCloseKey
0x1800019fb  mov     eax, ebx
0x1800019fd  add     rsp, 38h
0x180001a01  pop     rbx
0x180001a02  pop     rbp
0x180001a03  retn
```
