# GetCrlPreFetchUrlList(void)

- ea: `0x180017de4`
- end: `0x180017e58`
- name: `?GetCrlPreFetchUrlList@@YAPEAGXZ`
- size: `116`
- prototype: `unsigned __int16 *(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180008f80`
- `0x18001e834`

## callees

- `0x180017de4`
- `0x18001f17c`
- `0x18001f4fc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017e50`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017e50`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017e16`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017e16`

## string_xrefs

- `0x180017e06`: `Software\Microsoft\Cryptography\OID\EncodingType 0\CertDllCreateCertificateChainEngine\Config\CrlPreFetch`

## pseudocode

```c
unsigned __int16 *GetCrlPreFetchUrlList(void)
{
  __int64 SZValueFromRegistry; // rbx
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  hKey = 0;
  SZValueFromRegistry = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Cryptography\\OID\\EncodingType 0\\CertDllCreateCertificateChainEngine\\Config\\CrlPreFetch",
          0,
          0x20119u,
          &hKey) )
  {
    if ( (unsigned int)IsInProcessNameList(hKey) )
      SZValueFromRegistry = ReadSZValueFromRegistry(hKey, L"PreFetchUrlList");
    RegCloseKey(hKey);
  }
  return (unsigned __int16 *)SZValueFromRegistry;
}

```

## disassembly

```asm
0x180017de4  push    rbx
0x180017de6  sub     rsp, 30h
0x180017dea  lea     rax, [rsp+38h+hKey]
0x180017def  mov     [rsp+38h+hKey], 0
0x180017df8  mov     r9d, 20119h; samDesired
0x180017dfe  mov     [rsp+38h+phkResult], rax; phkResult
0x180017e03  xor     r8d, r8d; ulOptions
0x180017e06  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Cryptography\\OID"...
0x180017e0d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180017e14  xor     ebx, ebx
0x180017e16  call    cs:__imp_RegOpenKeyExW
0x180017e1c  test    eax, eax
0x180017e1e  jz      short loc_180017E29
0x180017e20  mov     rax, rbx
0x180017e23  add     rsp, 30h
0x180017e27  pop     rbx
0x180017e28  retn
0x180017e29  mov     rcx, [rsp+38h+hKey]
0x180017e2e  call    _IsInProcessNameList
0x180017e33  test    eax, eax
0x180017e35  jz      short loc_180017E4B
0x180017e37  mov     rcx, [rsp+38h+hKey]; hKey
0x180017e3c  lea     rdx, aPrefetchurllis; "PreFetchUrlList"
0x180017e43  call    _ReadSZValueFromRegistry
0x180017e48  mov     rbx, rax
0x180017e4b  mov     rcx, [rsp+38h+hKey]; hKey
0x180017e50  call    cs:__imp_RegCloseKey
0x180017e56  jmp     short loc_180017E20
```
