# SCardContainerNameToNgcKeyName

- ea: `0x180076d68`
- end: `0x180076ea3`
- name: `SCardContainerNameToNgcKeyName`
- size: `315`
- prototype: `__int64 __fastcall(LPCWSTR pszKeyName)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180076bf4`

## callees

- `0x180076aec`
- `0x180076b18`
- `0x180076d68`

## import_xrefs

- `ncrypt!NCryptOpenStorageProvider` at `0x180076db4`
- `ncrypt!NCryptOpenStorageProvider` at `0x180076db4`
- `ncrypt!NCryptGetProperty` at `0x180076e10`
- `ncrypt!NCryptGetProperty` at `0x180076e56`
- `ncrypt!NCryptGetProperty` at `0x180076e10`
- `ncrypt!NCryptGetProperty` at `0x180076e56`
- `ncrypt!NCryptOpenKey` at `0x180076ddd`
- `ncrypt!NCryptOpenKey` at `0x180076ddd`
- `ncrypt!NCryptFreeObject` at `0x180076e78`
- `ncrypt!NCryptFreeObject` at `0x180076e87`
- `ncrypt!NCryptFreeObject` at `0x180076e78`
- `ncrypt!NCryptFreeObject` at `0x180076e87`

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
0x180076d68  mov     [rsp-18h+arg_8], rbx
0x180076d6d  push    rbp
0x180076d6e  push    rsi
0x180076d6f  push    rdi
0x180076d70  mov     rbp, rsp
0x180076d73  sub     rsp, 30h
0x180076d77  mov     [rbp+phProvider], 0
0x180076d7f  mov     rsi, rdx
0x180076d82  mov     [rbp+phKey], 0
0x180076d8a  mov     rdi, rcx
0x180076d8d  mov     [rbp+pcbResult], 0
0x180076d94  test    rcx, rcx
0x180076d97  jz      loc_180076E91
0x180076d9d  test    rdx, rdx
0x180076da0  jz      loc_180076E91
0x180076da6  xor     r8d, r8d; dwFlags
0x180076da9  lea     rdx, aMicrosoftSmart; "Microsoft Smart Card Key Storage Provid"...
0x180076db0  lea     rcx, [rbp+phProvider]; phProvider
0x180076db4  call    cs:__imp_NCryptOpenStorageProvider
0x180076dba  mov     ebx, eax
0x180076dbc  test    eax, eax
0x180076dbe  js      loc_180076E6F
0x180076dc4  mov     rcx, [rbp+phProvider]; hProvider
0x180076dc8  lea     rdx, [rbp+phKey]; phKey
0x180076dcc  mov     r9d, 1; dwLegacyKeySpec
0x180076dd2  mov     [rsp+30h+dwFlags], 40h ; '@'; dwFlags
0x180076dda  mov     r8, rdi; pszKeyName
0x180076ddd  call    cs:__imp_NCryptOpenKey
0x180076de3  mov     ebx, eax
0x180076de5  test    eax, eax
0x180076de7  js      loc_180076E6F
0x180076ded  mov     r9d, [rbp+pcbResult]; cbOutput
0x180076df1  lea     rax, [rbp+pcbResult]
0x180076df5  mov     rcx, [rbp+phKey]; hObject
0x180076df9  lea     rdx, aSmartcardngcke; "SmartCardNgcKeyName"
0x180076e00  mov     [rsp+30h+var_8], 40h ; '@'; dwFlags
0x180076e08  xor     r8d, r8d; pbOutput
0x180076e0b  mov     qword ptr [rsp+30h+dwFlags], rax; pcbResult
0x180076e10  call    cs:__imp_NCryptGetProperty
0x180076e16  mov     ebx, eax
0x180076e18  test    eax, eax
0x180076e1a  js      short loc_180076E6F
0x180076e1c  mov     ecx, [rbp+pcbResult]
0x180076e1f  call    AllocH
0x180076e24  mov     rdi, rax
0x180076e27  test    rax, rax
0x180076e2a  jnz     short loc_180076E33
0x180076e2c  mov     ebx, 8009000Eh
0x180076e31  jmp     short loc_180076E6F
0x180076e33  mov     r9d, [rbp+pcbResult]; cbOutput
0x180076e37  lea     rax, [rbp+pcbResult]
0x180076e3b  mov     rcx, [rbp+phKey]; hObject
0x180076e3f  lea     rdx, aSmartcardngcke; "SmartCardNgcKeyName"
0x180076e46  mov     [rsp+30h+var_8], 40h ; '@'; dwFlags
0x180076e4e  mov     r8, rdi; pbOutput
0x180076e51  mov     qword ptr [rsp+30h+dwFlags], rax; pcbResult
0x180076e56  call    cs:__imp_NCryptGetProperty
0x180076e5c  mov     ebx, eax
0x180076e5e  test    eax, eax
0x180076e60  js      short loc_180076E67
0x180076e62  mov     [rsi], rdi
0x180076e65  jmp     short loc_180076E6F
0x180076e67  mov     rcx, rdi
0x180076e6a  call    FreeH
0x180076e6f  mov     rcx, [rbp+phProvider]; hObject
0x180076e73  test    rcx, rcx
0x180076e76  jz      short loc_180076E7E
0x180076e78  call    cs:__imp_NCryptFreeObject
0x180076e7e  mov     rcx, [rbp+phKey]; hObject
0x180076e82  test    rcx, rcx
0x180076e85  jz      short loc_180076E8D
0x180076e87  call    cs:__imp_NCryptFreeObject
0x180076e8d  mov     eax, ebx
0x180076e8f  jmp     short loc_180076E96
0x180076e91  mov     eax, 80090027h
0x180076e96  mov     rbx, [rsp+30h+arg_8]
0x180076e9b  add     rsp, 30h
0x180076e9f  pop     rdi
0x180076ea0  pop     rsi
0x180076ea1  pop     rbp
0x180076ea2  retn
```
