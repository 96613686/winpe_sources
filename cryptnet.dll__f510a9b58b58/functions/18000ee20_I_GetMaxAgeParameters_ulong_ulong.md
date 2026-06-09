# I_GetMaxAgeParameters(ulong *,ulong *)

- ea: `0x18000ee20`
- end: `0x18000ef1f`
- name: `?I_GetMaxAgeParameters@@YAXPEAK0@Z`
- size: `255`
- prototype: `void __fastcall(unsigned int *, unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000ca20`
- `0x18000cfa0`

## callees

- `0x18000ee20`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000eee3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000eee3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ee65`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ee65`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000eea0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000eed5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000eea0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000eed5`

## string_xrefs

- `0x18000ee49`: `Software\Microsoft\Cryptography\OID\EncodingType 0\CertDllCreateCertificateChainEngine\Config`

## pseudocode

```c
void __fastcall I_GetMaxAgeParameters(unsigned int *a1, unsigned int *a2)
{
  DWORD cbData; // [rsp+50h] [rbp+20h] BYREF
  DWORD Type; // [rsp+58h] [rbp+28h] BYREF
  unsigned int Data; // [rsp+60h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+38h] BYREF

  *a1 = 3600;
  *a2 = 1209600;
  hKey = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Cryptography\\OID\\EncodingType 0\\CertDllCreateCertificateChainEngine\\Config",
          0,
          0x20119u,
          &hKey) )
  {
    Type = 0;
    Data = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"CryptnetPreFetchMinMaxAgeSeconds", 0, &Type, (LPBYTE)&Data, &cbData)
      && Type == 4
      && cbData == 4
      && Data )
    {
      *a1 = Data;
    }
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"CryptnetPreFetchMaxMaxAgeSeconds", 0, &Type, (LPBYTE)&Data, &cbData)
      && Type == 4
      && cbData == 4 )
    {
      if ( Data )
        *a2 = Data;
    }
    RegCloseKey(hKey);
  }
}

```

## disassembly

```asm
0x18000ee20  push    rbp
0x18000ee22  push    rbx
0x18000ee23  push    rdi
0x18000ee24  mov     rbp, rsp
0x18000ee27  sub     rsp, 30h
0x18000ee2b  mov     rdi, rdx
0x18000ee2e  mov     dword ptr [rcx], 0E10h
0x18000ee34  mov     rbx, rcx
0x18000ee37  mov     dword ptr [rdx], 127500h
0x18000ee3d  lea     rax, [rbp+hKey]
0x18000ee41  mov     [rbp+hKey], 0
0x18000ee49  lea     rdx, SubKey; "Software\\Microsoft\\Cryptography\\OID"...
0x18000ee50  mov     [rsp+30h+phkResult], rax; phkResult
0x18000ee55  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000ee5c  mov     r9d, 20119h; samDesired
0x18000ee62  xor     r8d, r8d; ulOptions
0x18000ee65  call    cs:__imp_RegOpenKeyExW
0x18000ee6b  test    eax, eax
0x18000ee6d  jnz     short loc_18000EEE9
0x18000ee6f  mov     rcx, [rbp+hKey]; hKey
0x18000ee73  lea     r9, [rbp+Type]; lpType
0x18000ee77  mov     [rbp+Type], eax
0x18000ee7a  lea     rdx, aCryptnetprefet_0; "CryptnetPreFetchMinMaxAgeSeconds"
0x18000ee81  mov     [rbp+Data], eax
0x18000ee84  xor     r8d, r8d; lpReserved
0x18000ee87  lea     rax, [rbp+cbData]
0x18000ee8b  mov     [rbp+cbData], 4
0x18000ee92  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18000ee97  lea     rax, [rbp+Data]
0x18000ee9b  mov     [rsp+30h+phkResult], rax; lpData
0x18000eea0  call    cs:__imp_RegQueryValueExW
0x18000eea6  test    eax, eax
0x18000eea8  jz      short loc_18000EEF1
0x18000eeaa  mov     rcx, [rbp+hKey]; hKey
0x18000eeae  lea     rax, [rbp+cbData]
0x18000eeb2  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18000eeb7  lea     r9, [rbp+Type]; lpType
0x18000eebb  lea     rax, [rbp+Data]
0x18000eebf  mov     [rbp+cbData], 4
0x18000eec6  xor     r8d, r8d; lpReserved
0x18000eec9  mov     [rsp+30h+phkResult], rax; lpData
0x18000eece  lea     rdx, aCryptnetprefet; "CryptnetPreFetchMaxMaxAgeSeconds"
0x18000eed5  call    cs:__imp_RegQueryValueExW
0x18000eedb  test    eax, eax
0x18000eedd  jz      short loc_18000EF08
0x18000eedf  mov     rcx, [rbp+hKey]; hKey
0x18000eee3  call    cs:__imp_RegCloseKey
0x18000eee9  add     rsp, 30h
0x18000eeed  pop     rdi
0x18000eeee  pop     rbx
0x18000eeef  pop     rbp
0x18000eef0  retn
0x18000eef1  cmp     [rbp+Type], 4
0x18000eef5  jnz     short loc_18000EEAA
0x18000eef7  cmp     [rbp+cbData], 4
0x18000eefb  jnz     short loc_18000EEAA
0x18000eefd  mov     eax, [rbp+Data]
0x18000ef00  test    eax, eax
0x18000ef02  jz      short loc_18000EEAA
0x18000ef04  mov     [rbx], eax
0x18000ef06  jmp     short loc_18000EEAA
0x18000ef08  cmp     [rbp+Type], 4
0x18000ef0c  jnz     short loc_18000EEDF
0x18000ef0e  cmp     [rbp+cbData], 4
0x18000ef12  jnz     short loc_18000EEDF
0x18000ef14  mov     eax, [rbp+Data]
0x18000ef17  test    eax, eax
0x18000ef19  jz      short loc_18000EEDF
0x18000ef1b  mov     [rdi], eax
0x18000ef1d  jmp     short loc_18000EEDF
```
