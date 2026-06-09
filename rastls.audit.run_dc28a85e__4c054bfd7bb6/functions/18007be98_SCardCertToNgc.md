# SCardCertToNgc

- ea: `0x18007be98`
- end: `0x18007bf5c`
- name: `SCardCertToNgc`
- size: `196`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180076704`

## callees

- `0x18007be64`
- `0x18007be98`
- `0x18007bf64`

## import_xrefs

- `ncrypt!NCryptOpenStorageProvider` at `0x18007bee7`
- `ncrypt!NCryptOpenStorageProvider` at `0x18007bee7`
- `ncrypt!NCryptOpenKey` at `0x18007bf11`
- `ncrypt!NCryptOpenKey` at `0x18007bf11`
- `ncrypt!NCryptFreeObject` at `0x18007bf3b`
- `ncrypt!NCryptFreeObject` at `0x18007bf3b`

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
0x18007be98  mov     rax, rsp
0x18007be9b  mov     [rax+10h], rbx
0x18007be9f  push    rsi
0x18007bea0  sub     rsp, 30h
0x18007bea4  mov     qword ptr [rax+20h], 0
0x18007beac  mov     rsi, r8
0x18007beaf  mov     qword ptr [rax+8], 0
0x18007beb7  test    rcx, rcx
0x18007beba  jz      loc_18007BF4B
0x18007bec0  test    r8, r8
0x18007bec3  jz      loc_18007BF4B
0x18007bec9  lea     rdx, [rax+8]
0x18007becd  call    SCardCertToNgcKeyName
0x18007bed2  mov     ebx, eax
0x18007bed4  test    eax, eax
0x18007bed6  js      short loc_18007BF1F
0x18007bed8  xor     r8d, r8d; dwFlags
0x18007bedb  lea     rdx, pszProviderName; "Microsoft Passport Key Storage Provider"
0x18007bee2  lea     rcx, [rsp+38h+phProvider]; phProvider
0x18007bee7  call    cs:__imp_NCryptOpenStorageProvider
0x18007beee  nop     dword ptr [rax+rax+00h]
0x18007bef3  mov     ebx, eax
0x18007bef5  test    eax, eax
0x18007bef7  js      short loc_18007BF1F
0x18007bef9  mov     r8, [rsp+38h+pszKeyName]; pszKeyName
0x18007befe  xor     r9d, r9d; dwLegacyKeySpec
0x18007bf01  mov     rcx, [rsp+38h+phProvider]; hProvider
0x18007bf06  mov     rdx, rsi; phKey
0x18007bf09  mov     [rsp+38h+dwFlags], 0; dwFlags
0x18007bf11  call    cs:__imp_NCryptOpenKey
0x18007bf18  nop     dword ptr [rax+rax+00h]
0x18007bf1d  mov     ebx, eax
0x18007bf1f  cmp     [rsp+38h+pszKeyName], 0
0x18007bf25  jz      short loc_18007BF31
0x18007bf27  mov     rcx, [rsp+38h+pszKeyName]
0x18007bf2c  call    FreeH
0x18007bf31  mov     rcx, [rsp+38h+phProvider]; hObject
0x18007bf36  test    rcx, rcx
0x18007bf39  jz      short loc_18007BF47
0x18007bf3b  call    cs:__imp_NCryptFreeObject
0x18007bf42  nop     dword ptr [rax+rax+00h]
0x18007bf47  mov     eax, ebx
0x18007bf49  jmp     short loc_18007BF50
0x18007bf4b  mov     eax, 80090027h
0x18007bf50  mov     rbx, [rsp+38h+arg_8]
0x18007bf55  add     rsp, 30h
0x18007bf59  pop     rsi
0x18007bf5a  retn
```
