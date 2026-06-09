# SCardCertToNgc

- ea: `0x180076b44`
- end: `0x180076bed`
- name: `SCardCertToNgc`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800718ac`

## callees

- `0x180076b18`
- `0x180076b44`
- `0x180076bf4`

## import_xrefs

- `ncrypt!NCryptOpenStorageProvider` at `0x180076b8b`
- `ncrypt!NCryptOpenStorageProvider` at `0x180076b8b`
- `ncrypt!NCryptOpenKey` at `0x180076baf`
- `ncrypt!NCryptOpenKey` at `0x180076baf`
- `ncrypt!NCryptFreeObject` at `0x180076bd3`
- `ncrypt!NCryptFreeObject` at `0x180076bd3`

## pseudocode

```c
__int64 __fastcall SCardCertToNgc(const CERT_CONTEXT *a1, __int64 a2, NCRYPT_KEY_HANDLE *a3)
{
  SECURITY_STATUS v4; // ebx
  NCRYPT_PROV_HANDLE phProvider; // [rsp+58h] [rbp+20h] BYREF

  phProvider = 0;
  if ( !a1 || !a3 )
    return 2148073511LL;
  v4 = SCardCertToNgcKeyName(a1);
  if ( v4 >= 0 )
  {
    v4 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Passport Key Storage Provider", 0);
    if ( v4 >= 0 )
      v4 = NCryptOpenKey(phProvider, a3, 0, 0, 0);
  }
  if ( phProvider )
    NCryptFreeObject(phProvider);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180076b44  mov     rax, rsp
0x180076b47  mov     [rax+10h], rbx
0x180076b4b  push    rsi
0x180076b4c  sub     rsp, 30h
0x180076b50  mov     qword ptr [rax+20h], 0
0x180076b58  mov     rsi, r8
0x180076b5b  mov     qword ptr [rax+8], 0
0x180076b63  test    rcx, rcx
0x180076b66  jz      short loc_180076BDD
0x180076b68  test    r8, r8
0x180076b6b  jz      short loc_180076BDD
0x180076b6d  lea     rdx, [rax+8]
0x180076b71  call    SCardCertToNgcKeyName
0x180076b76  mov     ebx, eax
0x180076b78  test    eax, eax
0x180076b7a  js      short loc_180076BB7
0x180076b7c  xor     r8d, r8d; dwFlags
0x180076b7f  lea     rdx, pszProviderName; "Microsoft Passport Key Storage Provider"
0x180076b86  lea     rcx, [rsp+38h+phProvider]; phProvider
0x180076b8b  call    cs:__imp_NCryptOpenStorageProvider
0x180076b91  mov     ebx, eax
0x180076b93  test    eax, eax
0x180076b95  js      short loc_180076BB7
0x180076b97  mov     r8, [rsp+38h+pszKeyName]; pszKeyName
0x180076b9c  xor     r9d, r9d; dwLegacyKeySpec
0x180076b9f  mov     rcx, [rsp+38h+phProvider]; hProvider
0x180076ba4  mov     rdx, rsi; phKey
0x180076ba7  mov     [rsp+38h+dwFlags], 0; dwFlags
0x180076baf  call    cs:__imp_NCryptOpenKey
0x180076bb5  mov     ebx, eax
0x180076bb7  cmp     [rsp+38h+pszKeyName], 0
0x180076bbd  jz      short loc_180076BC9
0x180076bbf  mov     rcx, [rsp+38h+pszKeyName]
0x180076bc4  call    FreeH
0x180076bc9  mov     rcx, [rsp+38h+phProvider]; hObject
0x180076bce  test    rcx, rcx
0x180076bd1  jz      short loc_180076BD9
0x180076bd3  call    cs:__imp_NCryptFreeObject
0x180076bd9  mov     eax, ebx
0x180076bdb  jmp     short loc_180076BE2
0x180076bdd  mov     eax, 80090027h
0x180076be2  mov     rbx, [rsp+38h+arg_8]
0x180076be7  add     rsp, 30h
0x180076beb  pop     rsi
0x180076bec  retn
```
