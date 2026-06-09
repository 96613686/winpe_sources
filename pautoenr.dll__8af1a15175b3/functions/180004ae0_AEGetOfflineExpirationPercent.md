# AEGetOfflineExpirationPercent

- ea: `0x180004ae0`
- end: `0x180004b9f`
- name: `AEGetOfflineExpirationPercent`
- size: `191`
- prototype: `__int64 __fastcall(HKEY, char *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001d90`

## callees

- `0x180004ae0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004b58`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004b58`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004b1a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004b1a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004b88`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004b88`

## pseudocode

```c
__int64 __fastcall AEGetOfflineExpirationPercent(HKEY a1, char *a2)
{
  char v3; // bl
  __int64 result; // rax
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF
  unsigned int Data; // [rsp+58h] [rbp+10h] BYREF
  DWORD Type; // [rsp+60h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+20h] BYREF

  Data = 10;
  hKey = 0;
  v3 = 0;
  if ( !RegOpenKeyExW(a1, L"SOFTWARE\\Policies\\Microsoft\\Cryptography\\AutoEnrollment", 0, 0x20019u, &hKey) )
  {
    Type = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"OfflineExpirationPercent", 0, &Type, (LPBYTE)&Data, &cbData)
      && Type == 4
      && cbData == 4
      && Data <= 0x64 )
    {
      v3 = 1;
    }
    else
    {
      Data = 10;
    }
    RegCloseKey(hKey);
  }
  result = Data;
  *a2 = v3;
  return result;
}

```

## disassembly

```asm
0x180004ae0  mov     [rsp+arg_0], rbx
0x180004ae5  push    rdi
0x180004ae6  sub     rsp, 40h
0x180004aea  mov     rdi, rdx
0x180004aed  mov     [rsp+48h+Data], 0Ah
0x180004af5  lea     rax, [rsp+48h+hKey]
0x180004afa  mov     [rsp+48h+hKey], 0
0x180004b03  lea     rdx, SubKey; "SOFTWARE\\Policies\\Microsoft\\Cryptogr"...
0x180004b0a  mov     [rsp+48h+phkResult], rax; phkResult
0x180004b0f  mov     r9d, 20019h; samDesired
0x180004b15  xor     r8d, r8d; ulOptions
0x180004b18  xor     bl, bl
0x180004b1a  call    cs:__imp_RegOpenKeyExW
0x180004b20  test    eax, eax
0x180004b22  jnz     short loc_180004B8E
0x180004b24  mov     rcx, [rsp+48h+hKey]; hKey
0x180004b29  lea     r9, [rsp+48h+Type]; lpType
0x180004b2e  mov     [rsp+48h+Type], eax
0x180004b32  lea     rdx, aOfflineexpirat; "OfflineExpirationPercent"
0x180004b39  lea     rax, [rsp+48h+cbData]
0x180004b3e  mov     [rsp+48h+cbData], 4
0x180004b46  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180004b4b  xor     r8d, r8d; lpReserved
0x180004b4e  lea     rax, [rsp+48h+Data]
0x180004b53  mov     [rsp+48h+phkResult], rax; lpData
0x180004b58  call    cs:__imp_RegQueryValueExW
0x180004b5e  test    eax, eax
0x180004b60  jnz     short loc_180004B7B
0x180004b62  cmp     [rsp+48h+Type], 4
0x180004b67  jnz     short loc_180004B7B
0x180004b69  cmp     [rsp+48h+cbData], 4
0x180004b6e  jnz     short loc_180004B7B
0x180004b70  cmp     [rsp+48h+Data], 64h ; 'd'
0x180004b75  ja      short loc_180004B7B
0x180004b77  mov     bl, 1
0x180004b79  jmp     short loc_180004B83
0x180004b7b  mov     [rsp+48h+Data], 0Ah
0x180004b83  mov     rcx, [rsp+48h+hKey]; hKey
0x180004b88  call    cs:__imp_RegCloseKey
0x180004b8e  mov     eax, [rsp+48h+Data]
0x180004b92  mov     [rdi], bl
0x180004b94  mov     rbx, [rsp+48h+arg_0]
0x180004b99  add     rsp, 40h
0x180004b9d  pop     rdi
0x180004b9e  retn
```
