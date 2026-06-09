# SCardContainerNameToNgcKeyName

- ea: `0x18007c0f4`
- end: `0x18007c254`
- name: `SCardContainerNameToNgcKeyName`
- size: `352`
- prototype: `__int64 __fastcall(LPCWSTR pszKeyName)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18007bf64`

## callees

- `0x18007be2c`
- `0x18007be64`
- `0x18007c0f4`

## import_xrefs

- `ncrypt!NCryptOpenStorageProvider` at `0x18007c140`
- `ncrypt!NCryptOpenStorageProvider` at `0x18007c140`
- `ncrypt!NCryptGetProperty` at `0x18007c1a8`
- `ncrypt!NCryptGetProperty` at `0x18007c1f4`
- `ncrypt!NCryptGetProperty` at `0x18007c1a8`
- `ncrypt!NCryptGetProperty` at `0x18007c1f4`
- `ncrypt!NCryptOpenKey` at `0x18007c16f`
- `ncrypt!NCryptOpenKey` at `0x18007c16f`
- `ncrypt!NCryptFreeObject` at `0x18007c21c`
- `ncrypt!NCryptFreeObject` at `0x18007c231`
- `ncrypt!NCryptFreeObject` at `0x18007c21c`
- `ncrypt!NCryptFreeObject` at `0x18007c231`

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
0x18007c0f4  mov     [rsp-18h+arg_8], rbx
0x18007c0f9  push    rbp
0x18007c0fa  push    rsi
0x18007c0fb  push    rdi
0x18007c0fc  mov     rbp, rsp
0x18007c0ff  sub     rsp, 30h
0x18007c103  mov     [rbp+phProvider], 0
0x18007c10b  mov     rsi, rdx
0x18007c10e  mov     [rbp+phKey], 0
0x18007c116  mov     rdi, rcx
0x18007c119  mov     [rbp+pcbResult], 0
0x18007c120  test    rcx, rcx
0x18007c123  jz      loc_18007C241
0x18007c129  test    rdx, rdx
0x18007c12c  jz      loc_18007C241
0x18007c132  xor     r8d, r8d; dwFlags
0x18007c135  lea     rdx, aMicrosoftSmart; "Microsoft Smart Card Key Storage Provid"...
0x18007c13c  lea     rcx, [rbp+phProvider]; phProvider
0x18007c140  call    cs:__imp_NCryptOpenStorageProvider
0x18007c147  nop     dword ptr [rax+rax+00h]
0x18007c14c  mov     ebx, eax
0x18007c14e  test    eax, eax
0x18007c150  js      loc_18007C213
0x18007c156  mov     rcx, [rbp+phProvider]; hProvider
0x18007c15a  lea     rdx, [rbp+phKey]; phKey
0x18007c15e  mov     r9d, 1; dwLegacyKeySpec
0x18007c164  mov     [rsp+30h+dwFlags], 40h ; '@'; dwFlags
0x18007c16c  mov     r8, rdi; pszKeyName
0x18007c16f  call    cs:__imp_NCryptOpenKey
0x18007c176  nop     dword ptr [rax+rax+00h]
0x18007c17b  mov     ebx, eax
0x18007c17d  test    eax, eax
0x18007c17f  js      loc_18007C213
0x18007c185  mov     r9d, [rbp+pcbResult]; cbOutput
0x18007c189  lea     rax, [rbp+pcbResult]
0x18007c18d  mov     rcx, [rbp+phKey]; hObject
0x18007c191  lea     rdx, aSmartcardngcke; "SmartCardNgcKeyName"
0x18007c198  mov     [rsp+30h+var_8], 40h ; '@'; dwFlags
0x18007c1a0  xor     r8d, r8d; pbOutput
0x18007c1a3  mov     qword ptr [rsp+30h+dwFlags], rax; pcbResult
0x18007c1a8  call    cs:__imp_NCryptGetProperty
0x18007c1af  nop     dword ptr [rax+rax+00h]
0x18007c1b4  mov     ebx, eax
0x18007c1b6  test    eax, eax
0x18007c1b8  js      short loc_18007C213
0x18007c1ba  mov     ecx, [rbp+pcbResult]
0x18007c1bd  call    AllocH
0x18007c1c2  mov     rdi, rax
0x18007c1c5  test    rax, rax
0x18007c1c8  jnz     short loc_18007C1D1
0x18007c1ca  mov     ebx, 8009000Eh
0x18007c1cf  jmp     short loc_18007C213
0x18007c1d1  mov     r9d, [rbp+pcbResult]; cbOutput
0x18007c1d5  lea     rax, [rbp+pcbResult]
0x18007c1d9  mov     rcx, [rbp+phKey]; hObject
0x18007c1dd  lea     rdx, aSmartcardngcke; "SmartCardNgcKeyName"
0x18007c1e4  mov     [rsp+30h+var_8], 40h ; '@'; dwFlags
0x18007c1ec  mov     r8, rdi; pbOutput
0x18007c1ef  mov     qword ptr [rsp+30h+dwFlags], rax; pcbResult
0x18007c1f4  call    cs:__imp_NCryptGetProperty
0x18007c1fb  nop     dword ptr [rax+rax+00h]
0x18007c200  mov     ebx, eax
0x18007c202  test    eax, eax
0x18007c204  js      short loc_18007C20B
0x18007c206  mov     [rsi], rdi
0x18007c209  jmp     short loc_18007C213
0x18007c20b  mov     rcx, rdi
0x18007c20e  call    FreeH
0x18007c213  mov     rcx, [rbp+phProvider]; hObject
0x18007c217  test    rcx, rcx
0x18007c21a  jz      short loc_18007C228
0x18007c21c  call    cs:__imp_NCryptFreeObject
0x18007c223  nop     dword ptr [rax+rax+00h]
0x18007c228  mov     rcx, [rbp+phKey]; hObject
0x18007c22c  test    rcx, rcx
0x18007c22f  jz      short loc_18007C23D
0x18007c231  call    cs:__imp_NCryptFreeObject
0x18007c238  nop     dword ptr [rax+rax+00h]
0x18007c23d  mov     eax, ebx
0x18007c23f  jmp     short loc_18007C246
0x18007c241  mov     eax, 80090027h
0x18007c246  mov     rbx, [rsp+30h+arg_8]
0x18007c24b  add     rsp, 30h
0x18007c24f  pop     rdi
0x18007c250  pop     rsi
0x18007c251  pop     rbp
0x18007c252  retn
```
