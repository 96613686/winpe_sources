# RegReadContainerResolutionFlag

- ea: `0x180035a34`
- end: `0x180035af0`
- name: `RegReadContainerResolutionFlag`
- size: `188`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800495c0`
- `0x18004a470`

## callees

- `0x180035a34`
- `0x180046ec0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035ad5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035ad5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035a88`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035a88`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180035aba`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180035aba`

## pseudocode

```c
__int64 RegReadContainerResolutionFlag()
{
  unsigned int v0; // ebx
  HKEY hKey; // [rsp+30h] [rbp-28h] BYREF
  BYTE Data[4]; // [rsp+38h] [rbp-20h] BYREF
  DWORD cbData; // [rsp+3Ch] [rbp-1Ch] BYREF
  DWORD Type; // [rsp+40h] [rbp-18h] BYREF

  *(_DWORD *)Data = 0;
  cbData = 4;
  Type = 4;
  v0 = 0;
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Containers", 0, 1u, &hKey)
    && !RegQueryValueExW(hKey, L"SendDnsToHost", 0, &Type, Data, &cbData) )
  {
    LOBYTE(v0) = *(_DWORD *)Data != 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v0;
}

```

## disassembly

```asm
0x180035a34  push    rbx
0x180035a36  sub     rsp, 50h
0x180035a3a  mov     rax, cs:__security_cookie
0x180035a41  xor     rax, rsp
0x180035a44  mov     [rsp+58h+var_10], rax
0x180035a49  mov     eax, 4
0x180035a4e  mov     dword ptr [rsp+58h+Data], 0
0x180035a56  mov     [rsp+58h+cbData], eax
0x180035a5a  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180035a61  mov     [rsp+58h+Type], eax
0x180035a65  xor     ebx, ebx
0x180035a67  lea     rax, [rsp+58h+hKey]
0x180035a6c  mov     [rsp+58h+hKey], 0
0x180035a75  xor     r8d, r8d; ulOptions
0x180035a78  mov     [rsp+58h+phkResult], rax; phkResult
0x180035a7d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180035a84  lea     r9d, [rbx+1]; samDesired
0x180035a88  call    cs:__imp_RegOpenKeyExW
0x180035a8e  test    eax, eax
0x180035a90  jnz     short loc_180035ACB
0x180035a92  mov     rcx, [rsp+58h+hKey]; hKey
0x180035a97  lea     rax, [rsp+58h+cbData]
0x180035a9c  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180035aa1  lea     r9, [rsp+58h+Type]; lpType
0x180035aa6  lea     rax, [rsp+58h+Data]
0x180035aab  xor     r8d, r8d; lpReserved
0x180035aae  lea     rdx, aSenddnstohost; "SendDnsToHost"
0x180035ab5  mov     [rsp+58h+phkResult], rax; lpData
0x180035aba  call    cs:__imp_RegQueryValueExW
0x180035ac0  test    eax, eax
0x180035ac2  jnz     short loc_180035ACB
0x180035ac4  cmp     dword ptr [rsp+58h+Data], ebx
0x180035ac8  setnz   bl
0x180035acb  mov     rcx, [rsp+58h+hKey]; hKey
0x180035ad0  test    rcx, rcx
0x180035ad3  jz      short loc_180035ADB
0x180035ad5  call    cs:__imp_RegCloseKey
0x180035adb  mov     eax, ebx
0x180035add  mov     rcx, [rsp+58h+var_10]
0x180035ae2  xor     rcx, rsp; StackCookie
0x180035ae5  call    __security_check_cookie
0x180035aea  add     rsp, 50h
0x180035aee  pop     rbx
0x180035aef  retn
```
