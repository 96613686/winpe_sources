# GetLocalDTCProfileInt(char const *,ulong)

- ea: `0x18000debc`
- end: `0x18000df6b`
- name: `?GetLocalDTCProfileInt@@YAKPEBDK@Z`
- size: `175`
- prototype: `__int64 __fastcall(LPCSTR lpValueName)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001010`
- `0x18000db30`
- `0x18000db58`
- `0x18000dd90`
- `0x18000e090`

## callees

- `0x18000debc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18000df37`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18000df37`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000df57`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000df57`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18000df0d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18000df0d`

## pseudocode

```c
__int64 __fastcall GetLocalDTCProfileInt(LPCSTR lpValueName)
{
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  unsigned int Data; // [rsp+58h] [rbp+18h] BYREF
  DWORD Type; // [rsp+60h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+28h] BYREF

  hKey = 0;
  Type = 0;
  Data = 0;
  cbData = 4;
  if ( RegOpenKeyExA(HKEY_LOCAL_MACHINE, "Software\\Microsoft\\MSDTC", 0, 0x20119u, &hKey)
    || RegQueryValueExA(hKey, lpValueName, 0, &Type, (LPBYTE)&Data, &cbData)
    || Type != 4 )
  {
    Data = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return Data;
}

```

## disassembly

```asm
0x18000debc  mov     [rsp-8+arg_0], rbx
0x18000dec1  mov     [rsp-8+Data], edx
0x18000dec5  push    rbp
0x18000dec6  mov     rbp, rsp
0x18000dec9  sub     rsp, 40h
0x18000decd  mov     rbx, rcx
0x18000ded0  mov     [rbp+hKey], 0
0x18000ded8  lea     rax, [rbp+hKey]
0x18000dedc  mov     [rbp+Type], 0
0x18000dee3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000deea  mov     [rsp+40h+phkResult], rax; phkResult
0x18000deef  mov     r9d, 20119h; samDesired
0x18000def5  mov     [rbp+Data], 0
0x18000defc  xor     r8d, r8d; ulOptions
0x18000deff  mov     [rbp+cbData], 4
0x18000df06  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\MSDTC"
0x18000df0d  call    cs:__imp_RegOpenKeyExA
0x18000df13  test    eax, eax
0x18000df15  jnz     short loc_18000DF47
0x18000df17  mov     rcx, [rbp+hKey]; hKey
0x18000df1b  lea     rax, [rbp+cbData]
0x18000df1f  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18000df24  lea     r9, [rbp+Type]; lpType
0x18000df28  lea     rax, [rbp+Data]
0x18000df2c  xor     r8d, r8d; lpReserved
0x18000df2f  mov     rdx, rbx; lpValueName
0x18000df32  mov     [rsp+40h+phkResult], rax; lpData
0x18000df37  call    cs:__imp_RegQueryValueExA
0x18000df3d  test    eax, eax
0x18000df3f  jnz     short loc_18000DF47
0x18000df41  cmp     [rbp+Type], 4
0x18000df45  jz      short loc_18000DF4E
0x18000df47  mov     [rbp+Data], 0
0x18000df4e  mov     rcx, [rbp+hKey]; hKey
0x18000df52  test    rcx, rcx
0x18000df55  jz      short loc_18000DF5D
0x18000df57  call    cs:__imp_RegCloseKey
0x18000df5d  mov     eax, [rbp+Data]
0x18000df60  mov     rbx, [rsp+40h+arg_0]
0x18000df65  add     rsp, 40h
0x18000df69  pop     rbp
0x18000df6a  retn
```
