# SCardContainerNameToNgcKeyName

- ea: `0x1800f6ed8`
- end: `0x1800f7038`
- name: `SCardContainerNameToNgcKeyName`
- size: `352`
- prototype: `__int64 __fastcall(LPCWSTR pszKeyName)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800f6d48`

## callees

- `0x1800f6c00`
- `0x1800f6c38`
- `0x1800f6ed8`

## import_xrefs

- `ncrypt!NCryptOpenStorageProvider` at `0x1800f6f24`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800f6f24`
- `ncrypt!NCryptFreeObject` at `0x1800f7000`
- `ncrypt!NCryptFreeObject` at `0x1800f7015`
- `ncrypt!NCryptFreeObject` at `0x1800f7000`
- `ncrypt!NCryptFreeObject` at `0x1800f7015`
- `ncrypt!NCryptOpenKey` at `0x1800f6f53`
- `ncrypt!NCryptOpenKey` at `0x1800f6f53`
- `ncrypt!NCryptGetProperty` at `0x1800f6f8c`
- `ncrypt!NCryptGetProperty` at `0x1800f6fd8`
- `ncrypt!NCryptGetProperty` at `0x1800f6f8c`
- `ncrypt!NCryptGetProperty` at `0x1800f6fd8`

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
0x1800f6ed8  mov     [rsp-18h+arg_8], rbx
0x1800f6edd  push    rbp
0x1800f6ede  push    rsi
0x1800f6edf  push    rdi
0x1800f6ee0  mov     rbp, rsp
0x1800f6ee3  sub     rsp, 30h
0x1800f6ee7  mov     [rbp+phProvider], 0
0x1800f6eef  mov     rsi, rdx
0x1800f6ef2  mov     [rbp+phKey], 0
0x1800f6efa  mov     rdi, rcx
0x1800f6efd  mov     [rbp+pcbResult], 0
0x1800f6f04  test    rcx, rcx
0x1800f6f07  jz      loc_1800F7025
0x1800f6f0d  test    rdx, rdx
0x1800f6f10  jz      loc_1800F7025
0x1800f6f16  xor     r8d, r8d; dwFlags
0x1800f6f19  lea     rdx, aMicrosoftSmart; "Microsoft Smart Card Key Storage Provid"...
0x1800f6f20  lea     rcx, [rbp+phProvider]; phProvider
0x1800f6f24  call    cs:__imp_NCryptOpenStorageProvider
0x1800f6f2b  nop     dword ptr [rax+rax+00h]
0x1800f6f30  mov     ebx, eax
0x1800f6f32  test    eax, eax
0x1800f6f34  js      loc_1800F6FF7
0x1800f6f3a  mov     rcx, [rbp+phProvider]; hProvider
0x1800f6f3e  lea     rdx, [rbp+phKey]; phKey
0x1800f6f42  mov     r9d, 1; dwLegacyKeySpec
0x1800f6f48  mov     [rsp+30h+dwFlags], 40h ; '@'; dwFlags
0x1800f6f50  mov     r8, rdi; pszKeyName
0x1800f6f53  call    cs:__imp_NCryptOpenKey
0x1800f6f5a  nop     dword ptr [rax+rax+00h]
0x1800f6f5f  mov     ebx, eax
0x1800f6f61  test    eax, eax
0x1800f6f63  js      loc_1800F6FF7
0x1800f6f69  mov     r9d, [rbp+pcbResult]; cbOutput
0x1800f6f6d  lea     rax, [rbp+pcbResult]
0x1800f6f71  mov     rcx, [rbp+phKey]; hObject
0x1800f6f75  lea     rdx, aSmartcardngcke; "SmartCardNgcKeyName"
0x1800f6f7c  mov     [rsp+30h+var_8], 40h ; '@'; dwFlags
0x1800f6f84  xor     r8d, r8d; pbOutput
0x1800f6f87  mov     qword ptr [rsp+30h+dwFlags], rax; pcbResult
0x1800f6f8c  call    cs:__imp_NCryptGetProperty
0x1800f6f93  nop     dword ptr [rax+rax+00h]
0x1800f6f98  mov     ebx, eax
0x1800f6f9a  test    eax, eax
0x1800f6f9c  js      short loc_1800F6FF7
0x1800f6f9e  mov     ecx, [rbp+pcbResult]
0x1800f6fa1  call    AllocH
0x1800f6fa6  mov     rdi, rax
0x1800f6fa9  test    rax, rax
0x1800f6fac  jnz     short loc_1800F6FB5
0x1800f6fae  mov     ebx, 8009000Eh
0x1800f6fb3  jmp     short loc_1800F6FF7
0x1800f6fb5  mov     r9d, [rbp+pcbResult]; cbOutput
0x1800f6fb9  lea     rax, [rbp+pcbResult]
0x1800f6fbd  mov     rcx, [rbp+phKey]; hObject
0x1800f6fc1  lea     rdx, aSmartcardngcke; "SmartCardNgcKeyName"
0x1800f6fc8  mov     [rsp+30h+var_8], 40h ; '@'; dwFlags
0x1800f6fd0  mov     r8, rdi; pbOutput
0x1800f6fd3  mov     qword ptr [rsp+30h+dwFlags], rax; pcbResult
0x1800f6fd8  call    cs:__imp_NCryptGetProperty
0x1800f6fdf  nop     dword ptr [rax+rax+00h]
0x1800f6fe4  mov     ebx, eax
0x1800f6fe6  test    eax, eax
0x1800f6fe8  js      short loc_1800F6FEF
0x1800f6fea  mov     [rsi], rdi
0x1800f6fed  jmp     short loc_1800F6FF7
0x1800f6fef  mov     rcx, rdi
0x1800f6ff2  call    FreeH
0x1800f6ff7  mov     rcx, [rbp+phProvider]; hObject
0x1800f6ffb  test    rcx, rcx
0x1800f6ffe  jz      short loc_1800F700C
0x1800f7000  call    cs:__imp_NCryptFreeObject
0x1800f7007  nop     dword ptr [rax+rax+00h]
0x1800f700c  mov     rcx, [rbp+phKey]; hObject
0x1800f7010  test    rcx, rcx
0x1800f7013  jz      short loc_1800F7021
0x1800f7015  call    cs:__imp_NCryptFreeObject
0x1800f701c  nop     dword ptr [rax+rax+00h]
0x1800f7021  mov     eax, ebx
0x1800f7023  jmp     short loc_1800F702A
0x1800f7025  mov     eax, 80090027h
0x1800f702a  mov     rbx, [rsp+30h+arg_8]
0x1800f702f  add     rsp, 30h
0x1800f7033  pop     rdi
0x1800f7034  pop     rsi
0x1800f7035  pop     rbp
0x1800f7036  retn
```
