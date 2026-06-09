# SCardContainerNameToNgcKeyName

- ea: `0x1800f1c34`
- end: `0x1800f1d6f`
- name: `SCardContainerNameToNgcKeyName`
- size: `315`
- prototype: `__int64 __fastcall(LPCWSTR pszKeyName)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800f1ac0`

## callees

- `0x1800f19b8`
- `0x1800f19e4`
- `0x1800f1c34`

## import_xrefs

- `ncrypt!NCryptOpenKey` at `0x1800f1ca9`
- `ncrypt!NCryptOpenKey` at `0x1800f1ca9`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800f1c80`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800f1c80`
- `ncrypt!NCryptFreeObject` at `0x1800f1d44`
- `ncrypt!NCryptFreeObject` at `0x1800f1d53`
- `ncrypt!NCryptFreeObject` at `0x1800f1d44`
- `ncrypt!NCryptFreeObject` at `0x1800f1d53`
- `ncrypt!NCryptGetProperty` at `0x1800f1cdc`
- `ncrypt!NCryptGetProperty` at `0x1800f1d22`
- `ncrypt!NCryptGetProperty` at `0x1800f1cdc`
- `ncrypt!NCryptGetProperty` at `0x1800f1d22`

## pseudocode

```c
__int64 __fastcall SCardContainerNameToNgcKeyName(LPCWSTR pszKeyName, BYTE **a2)
{
  SECURITY_STATUS Property; // ebx
  BYTE *v5; // rdi
  DWORD pcbResult; // [rsp+50h] [rbp+20h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+60h] [rbp+30h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+68h] [rbp+38h] BYREF

  phProvider = 0;
  phKey = 0;
  pcbResult = 0;
  if ( !pszKeyName || !a2 )
    return 2148073511LL;
  Property = NCryptOpenStorageProvider(&phProvider, L"Microsoft Smart Card Key Storage Provider", 0);
  if ( Property >= 0 )
  {
    Property = NCryptOpenKey(phProvider, &phKey, pszKeyName, 1u, 0x40u);
    if ( Property >= 0 )
    {
      Property = NCryptGetProperty(phKey, L"SmartCardNgcKeyName", 0, pcbResult, &pcbResult, 0x40u);
      if ( Property >= 0 )
      {
        v5 = (BYTE *)AllocH(pcbResult);
        if ( v5 )
        {
          Property = NCryptGetProperty(phKey, L"SmartCardNgcKeyName", v5, pcbResult, &pcbResult, 0x40u);
          if ( Property < 0 )
            FreeH(v5);
          else
            *a2 = v5;
        }
        else
        {
          Property = -2146893810;
        }
      }
    }
  }
  if ( phProvider )
    NCryptFreeObject(phProvider);
  if ( phKey )
    NCryptFreeObject(phKey);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x1800f1c34  mov     [rsp-18h+arg_8], rbx
0x1800f1c39  push    rbp
0x1800f1c3a  push    rsi
0x1800f1c3b  push    rdi
0x1800f1c3c  mov     rbp, rsp
0x1800f1c3f  sub     rsp, 30h
0x1800f1c43  mov     [rbp+phProvider], 0
0x1800f1c4b  mov     rsi, rdx
0x1800f1c4e  mov     [rbp+phKey], 0
0x1800f1c56  mov     rdi, rcx
0x1800f1c59  mov     [rbp+pcbResult], 0
0x1800f1c60  test    rcx, rcx
0x1800f1c63  jz      loc_1800F1D5D
0x1800f1c69  test    rdx, rdx
0x1800f1c6c  jz      loc_1800F1D5D
0x1800f1c72  xor     r8d, r8d; dwFlags
0x1800f1c75  lea     rdx, aMicrosoftSmart; "Microsoft Smart Card Key Storage Provid"...
0x1800f1c7c  lea     rcx, [rbp+phProvider]; phProvider
0x1800f1c80  call    cs:__imp_NCryptOpenStorageProvider
0x1800f1c86  mov     ebx, eax
0x1800f1c88  test    eax, eax
0x1800f1c8a  js      loc_1800F1D3B
0x1800f1c90  mov     rcx, [rbp+phProvider]; hProvider
0x1800f1c94  lea     rdx, [rbp+phKey]; phKey
0x1800f1c98  mov     r9d, 1; dwLegacyKeySpec
0x1800f1c9e  mov     [rsp+30h+dwFlags], 40h ; '@'; dwFlags
0x1800f1ca6  mov     r8, rdi; pszKeyName
0x1800f1ca9  call    cs:__imp_NCryptOpenKey
0x1800f1caf  mov     ebx, eax
0x1800f1cb1  test    eax, eax
0x1800f1cb3  js      loc_1800F1D3B
0x1800f1cb9  mov     r9d, [rbp+pcbResult]; cbOutput
0x1800f1cbd  lea     rax, [rbp+pcbResult]
0x1800f1cc1  mov     rcx, [rbp+phKey]; hObject
0x1800f1cc5  lea     rdx, aSmartcardngcke; "SmartCardNgcKeyName"
0x1800f1ccc  mov     [rsp+30h+var_8], 40h ; '@'; dwFlags
0x1800f1cd4  xor     r8d, r8d; pbOutput
0x1800f1cd7  mov     qword ptr [rsp+30h+dwFlags], rax; pcbResult
0x1800f1cdc  call    cs:__imp_NCryptGetProperty
0x1800f1ce2  mov     ebx, eax
0x1800f1ce4  test    eax, eax
0x1800f1ce6  js      short loc_1800F1D3B
0x1800f1ce8  mov     ecx, [rbp+pcbResult]
0x1800f1ceb  call    AllocH
0x1800f1cf0  mov     rdi, rax
0x1800f1cf3  test    rax, rax
0x1800f1cf6  jnz     short loc_1800F1CFF
0x1800f1cf8  mov     ebx, 8009000Eh
0x1800f1cfd  jmp     short loc_1800F1D3B
0x1800f1cff  mov     r9d, [rbp+pcbResult]; cbOutput
0x1800f1d03  lea     rax, [rbp+pcbResult]
0x1800f1d07  mov     rcx, [rbp+phKey]; hObject
0x1800f1d0b  lea     rdx, aSmartcardngcke; "SmartCardNgcKeyName"
0x1800f1d12  mov     [rsp+30h+var_8], 40h ; '@'; dwFlags
0x1800f1d1a  mov     r8, rdi; pbOutput
0x1800f1d1d  mov     qword ptr [rsp+30h+dwFlags], rax; pcbResult
0x1800f1d22  call    cs:__imp_NCryptGetProperty
0x1800f1d28  mov     ebx, eax
0x1800f1d2a  test    eax, eax
0x1800f1d2c  js      short loc_1800F1D33
0x1800f1d2e  mov     [rsi], rdi
0x1800f1d31  jmp     short loc_1800F1D3B
0x1800f1d33  mov     rcx, rdi
0x1800f1d36  call    FreeH
0x1800f1d3b  mov     rcx, [rbp+phProvider]; hObject
0x1800f1d3f  test    rcx, rcx
0x1800f1d42  jz      short loc_1800F1D4A
0x1800f1d44  call    cs:__imp_NCryptFreeObject
0x1800f1d4a  mov     rcx, [rbp+phKey]; hObject
0x1800f1d4e  test    rcx, rcx
0x1800f1d51  jz      short loc_1800F1D59
0x1800f1d53  call    cs:__imp_NCryptFreeObject
0x1800f1d59  mov     eax, ebx
0x1800f1d5b  jmp     short loc_1800F1D62
0x1800f1d5d  mov     eax, 80090027h
0x1800f1d62  mov     rbx, [rsp+30h+arg_8]
0x1800f1d67  add     rsp, 30h
0x1800f1d6b  pop     rdi
0x1800f1d6c  pop     rsi
0x1800f1d6d  pop     rbp
0x1800f1d6e  retn
```
