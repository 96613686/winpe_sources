# SCardContainerNameToNgcKeyName

- ea: `0x18007edb4`
- end: `0x18007eeef`
- name: `SCardContainerNameToNgcKeyName`
- size: `315`
- prototype: `__int64 __fastcall(LPCWSTR pszKeyName)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18007ec40`

## callees

- `0x18007eb38`
- `0x18007eb64`
- `0x18007edb4`

## import_xrefs

- `ncrypt!NCryptFreeObject` at `0x18007eec4`
- `ncrypt!NCryptFreeObject` at `0x18007eed3`
- `ncrypt!NCryptFreeObject` at `0x18007eec4`
- `ncrypt!NCryptFreeObject` at `0x18007eed3`
- `ncrypt!NCryptOpenKey` at `0x18007ee29`
- `ncrypt!NCryptOpenKey` at `0x18007ee29`
- `ncrypt!NCryptGetProperty` at `0x18007ee5c`
- `ncrypt!NCryptGetProperty` at `0x18007eea2`
- `ncrypt!NCryptGetProperty` at `0x18007ee5c`
- `ncrypt!NCryptGetProperty` at `0x18007eea2`
- `ncrypt!NCryptOpenStorageProvider` at `0x18007ee00`
- `ncrypt!NCryptOpenStorageProvider` at `0x18007ee00`

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
0x18007edb4  mov     [rsp-18h+arg_8], rbx
0x18007edb9  push    rbp
0x18007edba  push    rsi
0x18007edbb  push    rdi
0x18007edbc  mov     rbp, rsp
0x18007edbf  sub     rsp, 30h
0x18007edc3  mov     [rbp+phProvider], 0
0x18007edcb  mov     rsi, rdx
0x18007edce  mov     [rbp+phKey], 0
0x18007edd6  mov     rdi, rcx
0x18007edd9  mov     [rbp+pcbResult], 0
0x18007ede0  test    rcx, rcx
0x18007ede3  jz      loc_18007EEDD
0x18007ede9  test    rdx, rdx
0x18007edec  jz      loc_18007EEDD
0x18007edf2  xor     r8d, r8d; dwFlags
0x18007edf5  lea     rdx, aMicrosoftSmart; "Microsoft Smart Card Key Storage Provid"...
0x18007edfc  lea     rcx, [rbp+phProvider]; phProvider
0x18007ee00  call    cs:__imp_NCryptOpenStorageProvider
0x18007ee06  mov     ebx, eax
0x18007ee08  test    eax, eax
0x18007ee0a  js      loc_18007EEBB
0x18007ee10  mov     rcx, [rbp+phProvider]; hProvider
0x18007ee14  lea     rdx, [rbp+phKey]; phKey
0x18007ee18  mov     r9d, 1; dwLegacyKeySpec
0x18007ee1e  mov     [rsp+30h+dwFlags], 40h ; '@'; dwFlags
0x18007ee26  mov     r8, rdi; pszKeyName
0x18007ee29  call    cs:__imp_NCryptOpenKey
0x18007ee2f  mov     ebx, eax
0x18007ee31  test    eax, eax
0x18007ee33  js      loc_18007EEBB
0x18007ee39  mov     r9d, [rbp+pcbResult]; cbOutput
0x18007ee3d  lea     rax, [rbp+pcbResult]
0x18007ee41  mov     rcx, [rbp+phKey]; hObject
0x18007ee45  lea     rdx, aSmartcardngcke; "SmartCardNgcKeyName"
0x18007ee4c  mov     [rsp+30h+var_8], 40h ; '@'; dwFlags
0x18007ee54  xor     r8d, r8d; pbOutput
0x18007ee57  mov     qword ptr [rsp+30h+dwFlags], rax; pcbResult
0x18007ee5c  call    cs:__imp_NCryptGetProperty
0x18007ee62  mov     ebx, eax
0x18007ee64  test    eax, eax
0x18007ee66  js      short loc_18007EEBB
0x18007ee68  mov     ecx, [rbp+pcbResult]
0x18007ee6b  call    AllocH
0x18007ee70  mov     rdi, rax
0x18007ee73  test    rax, rax
0x18007ee76  jnz     short loc_18007EE7F
0x18007ee78  mov     ebx, 8009000Eh
0x18007ee7d  jmp     short loc_18007EEBB
0x18007ee7f  mov     r9d, [rbp+pcbResult]; cbOutput
0x18007ee83  lea     rax, [rbp+pcbResult]
0x18007ee87  mov     rcx, [rbp+phKey]; hObject
0x18007ee8b  lea     rdx, aSmartcardngcke; "SmartCardNgcKeyName"
0x18007ee92  mov     [rsp+30h+var_8], 40h ; '@'; dwFlags
0x18007ee9a  mov     r8, rdi; pbOutput
0x18007ee9d  mov     qword ptr [rsp+30h+dwFlags], rax; pcbResult
0x18007eea2  call    cs:__imp_NCryptGetProperty
0x18007eea8  mov     ebx, eax
0x18007eeaa  test    eax, eax
0x18007eeac  js      short loc_18007EEB3
0x18007eeae  mov     [rsi], rdi
0x18007eeb1  jmp     short loc_18007EEBB
0x18007eeb3  mov     rcx, rdi
0x18007eeb6  call    FreeH
0x18007eebb  mov     rcx, [rbp+phProvider]; hObject
0x18007eebf  test    rcx, rcx
0x18007eec2  jz      short loc_18007EECA
0x18007eec4  call    cs:__imp_NCryptFreeObject
0x18007eeca  mov     rcx, [rbp+phKey]; hObject
0x18007eece  test    rcx, rcx
0x18007eed1  jz      short loc_18007EED9
0x18007eed3  call    cs:__imp_NCryptFreeObject
0x18007eed9  mov     eax, ebx
0x18007eedb  jmp     short loc_18007EEE2
0x18007eedd  mov     eax, 80090027h
0x18007eee2  mov     rbx, [rsp+30h+arg_8]
0x18007eee7  add     rsp, 30h
0x18007eeeb  pop     rdi
0x18007eeec  pop     rsi
0x18007eeed  pop     rbp
0x18007eeee  retn
```
