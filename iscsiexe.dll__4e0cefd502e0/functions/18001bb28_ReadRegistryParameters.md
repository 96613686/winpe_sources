# ReadRegistryParameters

- ea: `0x18001bb28`
- end: `0x18001bc1d`
- name: `ReadRegistryParameters`
- size: `245`
- prototype: `LSTATUS __fastcall(_DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001b834`

## callees

- `0x18001bb28`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001bc07`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001bc07`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18001bb7d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18001bb7d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18001bbb6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18001bbf0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18001bbb6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18001bbf0`

## string_xrefs

- `0x18001bb5a`: `Software\Microsoft\Windows NT\CurrentVersion\MSiSNS`

## pseudocode

```c
LSTATUS __fastcall ReadRegistryParameters(_DWORD *a1, _DWORD *a2)
{
  LSTATUS result; // eax
  DWORD Type; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+20h] BYREF
  int Data; // [rsp+68h] [rbp+28h] BYREF

  hKey = 0;
  Type = 0;
  cbData = 0;
  Data = 0;
  result = RegOpenKeyExA(HKEY_LOCAL_MACHINE, "Software\\Microsoft\\Windows NT\\CurrentVersion\\MSiSNS", 0, 1u, &hKey);
  if ( !result )
  {
    cbData = 4;
    if ( !RegQueryValueExA(hKey, "DHCPRetries", 0, &Type, (LPBYTE)&Data, &cbData) )
      *a1 = Data;
    cbData = 4;
    if ( !RegQueryValueExA(hKey, "DHCPTimeout", 0, &Type, (LPBYTE)&Data, &cbData) )
      *a2 = 1000 * Data;
    return RegCloseKey(hKey);
  }
  return result;
}

```

## disassembly

```asm
0x18001bb28  mov     [rsp-8+arg_0], rbx
0x18001bb2d  mov     [rsp-8+arg_8], rdi
0x18001bb32  push    rbp
0x18001bb33  mov     rbp, rsp
0x18001bb36  sub     rsp, 40h
0x18001bb3a  mov     rbx, rdx
0x18001bb3d  mov     [rbp+hKey], 0
0x18001bb45  mov     rdi, rcx
0x18001bb48  mov     [rbp+Type], 0
0x18001bb4f  lea     rax, [rbp+hKey]
0x18001bb53  mov     [rbp+cbData], 0
0x18001bb5a  lea     rdx, SubKey; "Software\\Microsoft\\Windows NT\\Curren"...
0x18001bb61  mov     [rsp+40h+phkResult], rax; phkResult
0x18001bb66  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001bb6d  mov     [rbp+Data], 0
0x18001bb74  mov     r9d, 1; samDesired
0x18001bb7a  xor     r8d, r8d; ulOptions
0x18001bb7d  call    cs:__imp_RegOpenKeyExA
0x18001bb83  test    eax, eax
0x18001bb85  jnz     loc_18001BC0D
0x18001bb8b  mov     rcx, [rbp+hKey]; hKey
0x18001bb8f  lea     rax, [rbp+cbData]
0x18001bb93  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18001bb98  lea     r9, [rbp+Type]; lpType
0x18001bb9c  lea     rax, [rbp+Data]
0x18001bba0  mov     [rbp+cbData], 4
0x18001bba7  xor     r8d, r8d; lpReserved
0x18001bbaa  mov     [rsp+40h+phkResult], rax; lpData
0x18001bbaf  lea     rdx, aDhcpretries; "DHCPRetries"
0x18001bbb6  call    cs:__imp_RegQueryValueExA
0x18001bbbc  test    eax, eax
0x18001bbbe  jnz     short loc_18001BBC5
0x18001bbc0  mov     eax, [rbp+Data]
0x18001bbc3  mov     [rdi], eax
0x18001bbc5  mov     rcx, [rbp+hKey]; hKey
0x18001bbc9  lea     rax, [rbp+cbData]
0x18001bbcd  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18001bbd2  lea     r9, [rbp+Type]; lpType
0x18001bbd6  lea     rax, [rbp+Data]
0x18001bbda  mov     [rbp+cbData], 4
0x18001bbe1  xor     r8d, r8d; lpReserved
0x18001bbe4  mov     [rsp+40h+phkResult], rax; lpData
0x18001bbe9  lea     rdx, aDhcptimeout; "DHCPTimeout"
0x18001bbf0  call    cs:__imp_RegQueryValueExA
0x18001bbf6  test    eax, eax
0x18001bbf8  jnz     short loc_18001BC03
0x18001bbfa  imul    eax, [rbp+Data], 3E8h
0x18001bc01  mov     [rbx], eax
0x18001bc03  mov     rcx, [rbp+hKey]; hKey
0x18001bc07  call    cs:__imp_RegCloseKey
0x18001bc0d  mov     rbx, [rsp+40h+arg_0]
0x18001bc12  mov     rdi, [rsp+40h+arg_8]
0x18001bc17  add     rsp, 40h
0x18001bc1b  pop     rbp
0x18001bc1c  retn
```
