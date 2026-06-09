# GetDebugLevel(void)

- ea: `0x180005f68`
- end: `0x180006011`
- name: `?GetDebugLevel@@YAKXZ`
- size: `169`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000613c`

## callees

- `0x180005f68`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180005fae`
- `ADVAPI32!RegOpenKeyExW` at `0x180005fae`
- `ADVAPI32!RegCloseKey` at `0x180006002`
- `ADVAPI32!RegCloseKey` at `0x180006002`
- `ADVAPI32!RegQueryValueExW` at `0x180005fe7`
- `ADVAPI32!RegQueryValueExW` at `0x180005fe7`

## pseudocode

```c
__int64 GetDebugLevel(void)
{
  unsigned int Data; // [rsp+40h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+18h] BYREF
  DWORD Type; // [rsp+50h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+28h] BYREF

  Data = 0;
  cbData = 0;
  Type = 0;
  hKey = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Fax\\Client", 0, 0x20019u, &hKey) )
    return 0;
  cbData = 4;
  if ( RegQueryValueExW(hKey, L"DebugLevel", 0, &Type, (LPBYTE)&Data, &cbData) || Type != 4 )
    Data = 0;
  RegCloseKey(hKey);
  return Data;
}

```

## disassembly

```asm
0x180005f68  push    rbp
0x180005f6a  mov     rbp, rsp
0x180005f6d  sub     rsp, 30h
0x180005f71  lea     rax, [rbp+hKey]
0x180005f75  mov     [rbp+Data], 0
0x180005f7c  mov     r9d, 20019h; samDesired
0x180005f82  mov     [rsp+30h+phkResult], rax; phkResult
0x180005f87  xor     r8d, r8d; ulOptions
0x180005f8a  mov     [rbp+cbData], 0
0x180005f91  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Fax\\Client"
0x180005f98  mov     [rbp+Type], 0
0x180005f9f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180005fa6  mov     [rbp+hKey], 0
0x180005fae  call    cs:__imp_RegOpenKeyExW
0x180005fb4  test    eax, eax
0x180005fb6  jz      short loc_180005FBC
0x180005fb8  xor     eax, eax
0x180005fba  jmp     short loc_18000600B
0x180005fbc  mov     rcx, [rbp+hKey]; hKey
0x180005fc0  lea     rax, [rbp+cbData]
0x180005fc4  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180005fc9  lea     r9, [rbp+Type]; lpType
0x180005fcd  lea     rax, [rbp+Data]
0x180005fd1  mov     [rbp+cbData], 4
0x180005fd8  xor     r8d, r8d; lpReserved
0x180005fdb  mov     [rsp+30h+phkResult], rax; lpData
0x180005fe0  lea     rdx, aDebuglevel; "DebugLevel"
0x180005fe7  call    cs:__imp_RegQueryValueExW
0x180005fed  test    eax, eax
0x180005fef  jnz     short loc_180005FF7
0x180005ff1  cmp     [rbp+Type], 4
0x180005ff5  jz      short loc_180005FFE
0x180005ff7  mov     [rbp+Data], 0
0x180005ffe  mov     rcx, [rbp+hKey]; hKey
0x180006002  call    cs:__imp_RegCloseKey
0x180006008  mov     eax, [rbp+Data]
0x18000600b  add     rsp, 30h
0x18000600f  pop     rbp
0x180006010  retn
```
