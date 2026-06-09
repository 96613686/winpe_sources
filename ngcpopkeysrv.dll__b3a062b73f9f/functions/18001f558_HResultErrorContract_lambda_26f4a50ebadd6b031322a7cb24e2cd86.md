# HResultErrorContract__lambda_26f4a50ebadd6b031322a7cb24e2cd86_

- ea: `0x18001f558`
- end: `0x18001f5c0`
- name: `HResultErrorContract__lambda_26f4a50ebadd6b031322a7cb24e2cd86___`
- size: `104`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180011f94`

## callees

- `0x18001f558`

## import_xrefs

- `ncrypt!NCryptFreeObject` at `0x18001f5a2`
- `ncrypt!NCryptFreeObject` at `0x18001f5a2`
- `ncrypt!NCryptOpenStorageProvider` at `0x18001f57a`
- `ncrypt!NCryptOpenStorageProvider` at `0x18001f57a`
- `ncrypt!NCryptIsAlgSupported` at `0x18001f595`
- `ncrypt!NCryptIsAlgSupported` at `0x18001f595`

## pseudocode

```c
__int64 HResultErrorContract__lambda_26f4a50ebadd6b031322a7cb24e2cd86_()
{
  unsigned int IsAlgSupported; // ebx
  NCRYPT_PROV_HANDLE phProvider; // [rsp+50h] [rbp+8h] BYREF

  phProvider = 0;
  IsAlgSupported = NCryptOpenStorageProvider(&phProvider, L"Microsoft Platform Crypto Provider", 0);
  if ( !IsAlgSupported )
  {
    IsAlgSupported = NCryptIsAlgSupported(phProvider, L"HMAC-SHA256", 0);
    NCryptFreeObject(phProvider);
  }
  return IsAlgSupported;
}

```

## disassembly

```asm
0x18001f558  mov     [rsp+phProvider], rcx
0x18001f55d  push    rbx
0x18001f55e  sub     rsp, 40h
0x18001f562  mov     [rsp+48h+phProvider], 0
0x18001f56b  xor     r8d, r8d; dwFlags
0x18001f56e  lea     rdx, pszProviderName; "Microsoft Platform Crypto Provider"
0x18001f575  lea     rcx, [rsp+48h+phProvider]; phProvider
0x18001f57a  call    cs:__imp_NCryptOpenStorageProvider
0x18001f580  mov     ebx, eax
0x18001f582  test    eax, eax
0x18001f584  jnz     short loc_18001F5A8
0x18001f586  xor     r8d, r8d; dwFlags
0x18001f589  lea     rdx, aHmacSha256; "HMAC-SHA256"
0x18001f590  mov     rcx, [rsp+48h+phProvider]; hProvider
0x18001f595  call    cs:__imp_NCryptIsAlgSupported
0x18001f59b  mov     ebx, eax
0x18001f59d  mov     rcx, [rsp+48h+phProvider]; hObject
0x18001f5a2  call    cs:__imp_NCryptFreeObject
0x18001f5a8  mov     dword ptr [rsp+48h+phProvider], ebx
0x18001f5ac  jmp     short loc_18001F5B6
0x18001f5ae  jmp     short loc_18001F5B6
0x18001f5b0  jmp     short loc_18001F5B6
0x18001f5b2  jmp     short loc_18001F5B6
0x18001f5b4  jmp     short $+2
0x18001f5b6  mov     eax, dword ptr [rsp+48h+phProvider]
0x18001f5ba  add     rsp, 40h
0x18001f5be  pop     rbx
0x18001f5bf  retn
```
