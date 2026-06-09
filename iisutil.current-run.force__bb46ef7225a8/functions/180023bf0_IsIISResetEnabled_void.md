# IsIISResetEnabled(void)

- ea: `0x180023bf0`
- end: `0x180023c8f`
- name: `?IsIISResetEnabled@@YAHXZ`
- size: `159`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023498`

## callees

- `0x180023bf0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023c29`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023c29`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023c80`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023c80`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180023c5e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180023c5e`

## pseudocode

```c
__int64 IsIISResetEnabled(void)
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
0x180023bf0  push    rbp
0x180023bf2  push    rbx
0x180023bf3  mov     rbp, rsp
0x180023bf6  sub     rsp, 38h
0x180023bfa  xor     ebx, ebx
0x180023bfc  lea     rax, [rbp+hKey]
0x180023c00  mov     r9d, 20019h; samDesired
0x180023c06  mov     [rbp+hKey], rbx
0x180023c0a  xor     r8d, r8d; ulOptions
0x180023c0d  mov     [rbp+Data], ebx
0x180023c10  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\INetStp"
0x180023c17  mov     [rbp+Type], ebx
0x180023c1a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180023c21  mov     [rbp+cbData], ebx
0x180023c24  mov     [rsp+38h+phkResult], rax; phkResult
0x180023c29  call    cs:__imp_RegOpenKeyExW
0x180023c2f  test    eax, eax
0x180023c31  jnz     short loc_180023C86
0x180023c33  mov     rcx, [rbp+hKey]; hKey
0x180023c37  lea     rax, [rbp+cbData]
0x180023c3b  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180023c40  lea     r9, [rbp+Type]; lpType
0x180023c44  lea     rax, [rbp+Data]
0x180023c48  mov     [rbp+cbData], 4
0x180023c4f  xor     r8d, r8d; lpReserved
0x180023c52  mov     [rsp+38h+phkResult], rax; lpData
0x180023c57  lea     rdx, aEnablerestart; "EnableRestart"
0x180023c5e  call    cs:__imp_RegQueryValueExW
0x180023c64  test    eax, eax
0x180023c66  jnz     short loc_180023C77
0x180023c68  cmp     [rbp+Type], 4
0x180023c6c  jnz     short loc_180023C77
0x180023c6e  cmp     [rbp+Data], 1
0x180023c72  setz    bl
0x180023c75  jmp     short loc_180023C7C
0x180023c77  mov     ebx, 1
0x180023c7c  mov     rcx, [rbp+hKey]; hKey
0x180023c80  call    cs:__imp_RegCloseKey
0x180023c86  mov     eax, ebx
0x180023c88  add     rsp, 38h
0x180023c8c  pop     rbx
0x180023c8d  pop     rbp
0x180023c8e  retn
```
