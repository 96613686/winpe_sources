# SCardCertToNgc

- ea: `0x18007eb90`
- end: `0x18007ec39`
- name: `SCardCertToNgc`
- size: `169`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180029650`

## callees

- `0x18007eb64`
- `0x18007eb90`
- `0x18007ec40`

## import_xrefs

- `ncrypt!NCryptFreeObject` at `0x18007ec1f`
- `ncrypt!NCryptFreeObject` at `0x18007ec1f`
- `ncrypt!NCryptOpenKey` at `0x18007ebfb`
- `ncrypt!NCryptOpenKey` at `0x18007ebfb`
- `ncrypt!NCryptOpenStorageProvider` at `0x18007ebd7`
- `ncrypt!NCryptOpenStorageProvider` at `0x18007ebd7`

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
      v4 = NCryptOpenKey(phProvider, a3, 0, 0, 0x40u);
  }
  if ( phProvider )
    NCryptFreeObject(phProvider);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18007eb90  mov     rax, rsp
0x18007eb93  mov     [rax+10h], rbx
0x18007eb97  push    rsi
0x18007eb98  sub     rsp, 30h
0x18007eb9c  mov     qword ptr [rax+20h], 0
0x18007eba4  mov     rsi, r8
0x18007eba7  mov     qword ptr [rax+8], 0
0x18007ebaf  test    rcx, rcx
0x18007ebb2  jz      short loc_18007EC29
0x18007ebb4  test    r8, r8
0x18007ebb7  jz      short loc_18007EC29
0x18007ebb9  lea     rdx, [rax+8]
0x18007ebbd  call    SCardCertToNgcKeyName
0x18007ebc2  mov     ebx, eax
0x18007ebc4  test    eax, eax
0x18007ebc6  js      short loc_18007EC03
0x18007ebc8  xor     r8d, r8d; dwFlags
0x18007ebcb  lea     rdx, pszProviderName; "Microsoft Passport Key Storage Provider"
0x18007ebd2  lea     rcx, [rsp+38h+phProvider]; phProvider
0x18007ebd7  call    cs:__imp_NCryptOpenStorageProvider
0x18007ebdd  mov     ebx, eax
0x18007ebdf  test    eax, eax
0x18007ebe1  js      short loc_18007EC03
0x18007ebe3  mov     r8, [rsp+38h+pszKeyName]; pszKeyName
0x18007ebe8  xor     r9d, r9d; dwLegacyKeySpec
0x18007ebeb  mov     rcx, [rsp+38h+phProvider]; hProvider
0x18007ebf0  mov     rdx, rsi; phKey
0x18007ebf3  mov     [rsp+38h+dwFlags], 40h ; '@'; dwFlags
0x18007ebfb  call    cs:__imp_NCryptOpenKey
0x18007ec01  mov     ebx, eax
0x18007ec03  cmp     [rsp+38h+pszKeyName], 0
0x18007ec09  jz      short loc_18007EC15
0x18007ec0b  mov     rcx, [rsp+38h+pszKeyName]
0x18007ec10  call    FreeH
0x18007ec15  mov     rcx, [rsp+38h+phProvider]; hObject
0x18007ec1a  test    rcx, rcx
0x18007ec1d  jz      short loc_18007EC25
0x18007ec1f  call    cs:__imp_NCryptFreeObject
0x18007ec25  mov     eax, ebx
0x18007ec27  jmp     short loc_18007EC2E
0x18007ec29  mov     eax, 80090027h
0x18007ec2e  mov     rbx, [rsp+38h+arg_8]
0x18007ec33  add     rsp, 30h
0x18007ec37  pop     rsi
0x18007ec38  retn
```
