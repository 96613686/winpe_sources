# IsEnableRemote(void)

- ea: `0x140002e14`
- end: `0x140002eb3`
- name: `?IsEnableRemote@@YAHXZ`
- size: `159`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140002ec0`
- `0x140003110`
- `0x1400031d0`
- `0x1400032a0`

## callees

- `0x140002e14`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140002e82`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140002e82`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140002ea4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140002ea4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140002e4d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140002e4d`

## pseudocode

```c
__int64 IsEnableRemote(void)
{
  unsigned int v0; // ebx
  DWORD cbData; // [rsp+50h] [rbp+18h] BYREF
  DWORD Type; // [rsp+58h] [rbp+20h] BYREF
  int Data; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  v0 = 0;
  hKey = 0;
  Data = 0;
  Type = 0;
  cbData = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\INetStp", 0, 0x20019u, &hKey) )
  {
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"EnableRestart", 0, &Type, (LPBYTE)&Data, &cbData) || Type != 4 )
      v0 = 1;
    else
      LOBYTE(v0) = Data == 1;
    RegCloseKey(hKey);
  }
  return v0;
}

```

## disassembly

```asm
0x140002e14  push    rbp
0x140002e16  push    rbx
0x140002e17  mov     rbp, rsp
0x140002e1a  sub     rsp, 38h
0x140002e1e  xor     ebx, ebx
0x140002e20  lea     rax, [rbp+hKey]
0x140002e24  mov     r9d, 20019h; samDesired
0x140002e2a  mov     [rbp+hKey], rbx
0x140002e2e  xor     r8d, r8d; ulOptions
0x140002e31  mov     [rbp+Data], ebx
0x140002e34  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\INetStp"
0x140002e3b  mov     [rbp+Type], ebx
0x140002e3e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140002e45  mov     [rbp+cbData], ebx
0x140002e48  mov     [rsp+38h+phkResult], rax; phkResult
0x140002e4d  call    cs:__imp_RegOpenKeyExW
0x140002e53  test    eax, eax
0x140002e55  jnz     short loc_140002EAA
0x140002e57  mov     rcx, [rbp+hKey]; hKey
0x140002e5b  lea     rax, [rbp+cbData]
0x140002e5f  mov     [rsp+38h+lpcbData], rax; lpcbData
0x140002e64  lea     r9, [rbp+Type]; lpType
0x140002e68  lea     rax, [rbp+Data]
0x140002e6c  mov     [rbp+cbData], 4
0x140002e73  xor     r8d, r8d; lpReserved
0x140002e76  mov     [rsp+38h+phkResult], rax; lpData
0x140002e7b  lea     rdx, aEnablerestart; "EnableRestart"
0x140002e82  call    cs:__imp_RegQueryValueExW
0x140002e88  test    eax, eax
0x140002e8a  jnz     short loc_140002E9B
0x140002e8c  cmp     [rbp+Type], 4
0x140002e90  jnz     short loc_140002E9B
0x140002e92  cmp     [rbp+Data], 1
0x140002e96  setz    bl
0x140002e99  jmp     short loc_140002EA0
0x140002e9b  mov     ebx, 1
0x140002ea0  mov     rcx, [rbp+hKey]; hKey
0x140002ea4  call    cs:__imp_RegCloseKey
0x140002eaa  mov     eax, ebx
0x140002eac  add     rsp, 38h
0x140002eb0  pop     rbx
0x140002eb1  pop     rbp
0x140002eb2  retn
```
