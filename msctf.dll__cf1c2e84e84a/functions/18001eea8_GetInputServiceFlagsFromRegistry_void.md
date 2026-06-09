# GetInputServiceFlagsFromRegistry(void)

- ea: `0x18001eea8`
- end: `0x18001ef82`
- name: `?GetInputServiceFlagsFromRegistry@@YAKXZ`
- size: `218`
- prototype: `unsigned int(void)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001e9f0`
- `0x18001ea24`
- `0x18001ea90`
- `0x18001f208`

## callees

- `0x18001eea8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ef17`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ef59`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ef17`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ef59`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001eed8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001eed8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ef73`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ef73`

## string_xrefs

- `0x18001ef06`: `InputServiceEnabled`
- `0x18001ef31`: `InputServiceEnabledForCCI`

## pseudocode

```c
__int64 GetInputServiceFlagsFromRegistry(void)
{
  unsigned int v0; // ebx
  int Data; // [rsp+50h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+20h] BYREF
  DWORD Type; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  v0 = 0;
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Input", 0, 0x20019u, &hKey) )
  {
    Data = 0;
    Type = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"InputServiceEnabled", 0, &Type, (LPBYTE)&Data, &cbData) )
    {
      if ( Data )
      {
        Data = 0;
        cbData = 4;
        v0 = 768;
        if ( !RegQueryValueExW(hKey, L"InputServiceEnabledForCCI", 0, &Type, (LPBYTE)&Data, &cbData) )
        {
          if ( Data )
            v0 = 1792;
        }
      }
    }
    RegCloseKey(hKey);
  }
  return v0;
}

```

## disassembly

```asm
0x18001eea8  push    rbp
0x18001eeaa  push    rbx
0x18001eeab  mov     rbp, rsp
0x18001eeae  sub     rsp, 38h
0x18001eeb2  lea     rax, [rbp+hKey]
0x18001eeb6  xor     ebx, ebx
0x18001eeb8  mov     r9d, 20019h; samDesired
0x18001eebe  mov     [rbp+hKey], rbx
0x18001eec2  xor     r8d, r8d; ulOptions
0x18001eec5  mov     [rsp+38h+phkResult], rax; phkResult
0x18001eeca  lea     rdx, aSoftwareMicros_11; "Software\\Microsoft\\Input"
0x18001eed1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001eed8  call    cs:__imp_RegOpenKeyExW
0x18001eede  test    eax, eax
0x18001eee0  jnz     loc_18001EF79
0x18001eee6  mov     rcx, [rbp+hKey]; hKey
0x18001eeea  lea     rax, [rbp+cbData]
0x18001eeee  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18001eef3  lea     r9, [rbp+Type]; lpType
0x18001eef7  lea     rax, [rbp+Data]
0x18001eefb  mov     [rbp+Data], ebx
0x18001eefe  xor     r8d, r8d; lpReserved
0x18001ef01  mov     [rsp+38h+phkResult], rax; lpData
0x18001ef06  lea     rdx, ValueName; "InputServiceEnabled"
0x18001ef0d  mov     [rbp+Type], ebx
0x18001ef10  mov     [rbp+cbData], 4
0x18001ef17  call    cs:__imp_RegQueryValueExW
0x18001ef1d  test    eax, eax
0x18001ef1f  jnz     short loc_18001EF6F
0x18001ef21  cmp     [rbp+Data], ebx
0x18001ef24  jz      short loc_18001EF6F
0x18001ef26  mov     rcx, [rbp+hKey]; hKey
0x18001ef2a  lea     r9, [rbp+Type]; lpType
0x18001ef2e  mov     [rbp+Data], eax
0x18001ef31  lea     rdx, aInputserviceen_0; "InputServiceEnabledForCCI"
0x18001ef38  lea     rax, [rbp+cbData]
0x18001ef3c  mov     [rbp+cbData], 4
0x18001ef43  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18001ef48  xor     r8d, r8d; lpReserved
0x18001ef4b  lea     rax, [rbp+Data]
0x18001ef4f  mov     ebx, 300h
0x18001ef54  mov     [rsp+38h+phkResult], rax; lpData
0x18001ef59  call    cs:__imp_RegQueryValueExW
0x18001ef5f  test    eax, eax
0x18001ef61  jnz     short loc_18001EF6F
0x18001ef63  cmp     [rbp+Data], 0
0x18001ef67  mov     eax, 700h
0x18001ef6c  cmovnz  ebx, eax
0x18001ef6f  mov     rcx, [rbp+hKey]; hKey
0x18001ef73  call    cs:__imp_RegCloseKey
0x18001ef79  mov     eax, ebx
0x18001ef7b  add     rsp, 38h
0x18001ef7f  pop     rbx
0x18001ef80  pop     rbp
0x18001ef81  retn
```
