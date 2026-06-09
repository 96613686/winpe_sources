# GetPublicKeyInfo

- ea: `0x1800fa054`
- end: `0x1800fa25d`
- name: `GetPublicKeyInfo`
- size: `521`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800f94ec`

## callees

- `0x18006d700`
- `0x18006ee50`
- `0x1800701b0`
- `0x1800fa054`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fa0ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fa18d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fa1ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fa0ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fa18d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fa1ec`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800fa11a`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800fa11a`
- `ncrypt!NCryptOpenKey` at `0x1800fa143`
- `ncrypt!NCryptOpenKey` at `0x1800fa143`
- `ncrypt!NCryptFreeObject` at `0x1800fa226`
- `ncrypt!NCryptFreeObject` at `0x1800fa23c`
- `ncrypt!NCryptFreeObject` at `0x1800fa226`
- `ncrypt!NCryptFreeObject` at `0x1800fa23c`
- `CRYPTSP!CryptAcquireContextW` at `0x1800fa0bc`
- `CRYPTSP!CryptAcquireContextW` at `0x1800fa0bc`
- `CRYPTSP!CryptReleaseContext` at `0x1800fa21e`
- `CRYPTSP!CryptReleaseContext` at `0x1800fa21e`

## pseudocode

```c
__int64 __fastcall GetPublicKeyInfo(__int64 a1, char a2, struct _CERT_PUBLIC_KEY_INFO **a3)
{
  int v5; // ebx
  int v6; // esi
  HCRYPTPROV v7; // rax
  signed int LastError; // eax
  DWORD v9; // r14d
  DWORD v10; // edx
  signed int v11; // eax
  struct _CERT_PUBLIC_KEY_INFO *pInfo; // r14
  signed int v13; // eax
  NCRYPT_PROV_HANDLE phProvider[2]; // [rsp+40h] [rbp-10h] BYREF
  DWORD pcbInfo; // [rsp+80h] [rbp+30h] BYREF
  HCRYPTPROV phProv; // [rsp+98h] [rbp+48h] BYREF

  v5 = 0;
  pcbInfo = 0;
  v6 = 0;
  phProvider[0] = 0;
  phProv = 0;
  if ( *(_DWORD *)(a1 + 80) )
  {
    v7 = *(_QWORD *)a1;
    if ( !*(_QWORD *)a1 )
    {
      if ( !*(_DWORD *)(a1 + 84) )
        return (unsigned int)-2147467259;
      if ( !CryptAcquireContextW(
              &phProv,
              *(LPCWSTR *)(a1 + 16),
              *(LPCWSTR *)(a1 + 24),
              *(_DWORD *)(a1 + 32),
              *(_DWORD *)(a1 + 36) | a2 & 0x40) )
      {
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_29;
      }
      goto LABEL_13;
    }
LABEL_9:
    phProv = v7;
LABEL_14:
    v10 = *(_DWORD *)(a1 + 56);
    pcbInfo = 0;
    if ( CryptExportPublicKeyInfoEx(phProv, v10, 0x10001u, 0, 0, 0, 0, &pcbInfo) )
    {
      pInfo = (struct _CERT_PUBLIC_KEY_INFO *)PFXHelpAlloc(pcbInfo);
      if ( pInfo )
      {
        if ( CryptExportPublicKeyInfoEx(phProv, *(_DWORD *)(a1 + 56), 0x10001u, 0, 0, 0, pInfo, &pcbInfo) )
        {
          *a3 = pInfo;
        }
        else
        {
          v13 = GetLastError();
          v5 = v13;
          if ( v13 > 0 )
            v5 = (unsigned __int16)v13 | 0x80070000;
          PFXHelpFree(pInfo);
        }
      }
      else
      {
        v5 = -2147024882;
      }
    }
    else
    {
      v11 = GetLastError();
      v5 = v11;
      if ( v11 > 0 )
        v5 = (unsigned __int16)v11 | 0x80070000;
    }
    if ( v6 )
    {
      if ( *(_DWORD *)(a1 + 80) )
        CryptReleaseContext(phProv, 0);
      else
        NCryptFreeObject(phProv);
    }
    goto LABEL_29;
  }
  v7 = *(_QWORD *)(a1 + 8);
  if ( v7 )
    goto LABEL_9;
  if ( *(_DWORD *)(a1 + 84) )
  {
    v9 = a2 & 0x40;
    v5 = NCryptOpenStorageProvider(phProvider, *(LPCWSTR *)(a1 + 24), v9);
    if ( v5 >= 0 )
    {
      v5 = NCryptOpenKey(phProvider[0], &phProv, *(LPCWSTR *)(a1 + 16), *(_DWORD *)(a1 + 56), *(_DWORD *)(a1 + 36) | v9);
      if ( v5 >= 0 )
      {
LABEL_13:
        v6 = 1;
        goto LABEL_14;
      }
    }
  }
  else
  {
    v5 = -2147467259;
  }
LABEL_29:
  if ( phProvider[0] )
    NCryptFreeObject(phProvider[0]);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800fa054  mov     [rsp-28h+arg_8], rbx
0x1800fa059  mov     [rsp-28h+arg_10], rsi
0x1800fa05e  push    rbp
0x1800fa05f  push    rdi
0x1800fa060  push    r12
0x1800fa062  push    r14
0x1800fa064  push    r15
0x1800fa066  mov     rbp, rsp
0x1800fa069  sub     rsp, 50h
0x1800fa06d  xor     r12d, r12d
0x1800fa070  mov     r15, r8
0x1800fa073  mov     r14d, edx
0x1800fa076  mov     rdi, rcx
0x1800fa079  mov     ebx, r12d
0x1800fa07c  mov     [rbp+arg_0], r12d
0x1800fa080  mov     esi, r12d
0x1800fa083  mov     [rbp+phProvider], r12
0x1800fa087  mov     [rbp+phProv], r12
0x1800fa08b  cmp     [rcx+50h], r12d
0x1800fa08f  jz      short loc_1800FA0F2
0x1800fa091  mov     rax, [rcx]
0x1800fa094  test    rax, rax
0x1800fa097  jnz     short loc_1800FA0FB
0x1800fa099  cmp     [rcx+54h], r12d
0x1800fa09d  jz      short loc_1800FA0E8
0x1800fa09f  mov     r9d, [rcx+20h]; dwProvType
0x1800fa0a3  and     r14d, 40h
0x1800fa0a7  or      r14d, [rcx+24h]
0x1800fa0ab  mov     r8, [rcx+18h]; szProvider
0x1800fa0af  mov     rdx, [rcx+10h]; szContainer
0x1800fa0b3  lea     rcx, [rbp+phProv]; phProv
0x1800fa0b7  mov     [rsp+50h+dwFlags], r14d; dwFlags
0x1800fa0bc  call    cs:__imp_CryptAcquireContextW
0x1800fa0c2  test    eax, eax
0x1800fa0c4  jnz     loc_1800FA153
0x1800fa0ca  call    cs:__imp_GetLastError
0x1800fa0d0  mov     ebx, eax
0x1800fa0d2  test    eax, eax
0x1800fa0d4  jle     loc_1800FA233
0x1800fa0da  movzx   ebx, ax
0x1800fa0dd  or      ebx, 80070000h
0x1800fa0e3  jmp     loc_1800FA233
0x1800fa0e8  mov     ebx, 80004005h
0x1800fa0ed  jmp     loc_1800FA242
0x1800fa0f2  mov     rax, [rcx+8]
0x1800fa0f6  test    rax, rax
0x1800fa0f9  jz      short loc_1800FA101
0x1800fa0fb  mov     [rbp+phProv], rax
0x1800fa0ff  jmp     short loc_1800FA158
0x1800fa101  cmp     [rcx+54h], r12d
0x1800fa105  jz      loc_1800FA22E
0x1800fa10b  mov     rdx, [rcx+18h]; pszProviderName
0x1800fa10f  and     r14d, 40h
0x1800fa113  mov     r8d, r14d; dwFlags
0x1800fa116  lea     rcx, [rbp+phProvider]; phProvider
0x1800fa11a  call    cs:__imp_NCryptOpenStorageProvider
0x1800fa120  mov     ebx, eax
0x1800fa122  test    eax, eax
0x1800fa124  js      loc_1800FA233
0x1800fa12a  or      r14d, [rdi+24h]
0x1800fa12e  lea     rdx, [rbp+phProv]; phKey
0x1800fa132  mov     r9d, [rdi+38h]; dwLegacyKeySpec
0x1800fa136  mov     r8, [rdi+10h]; pszKeyName
0x1800fa13a  mov     rcx, [rbp+phProvider]; hProvider
0x1800fa13e  mov     [rsp+50h+dwFlags], r14d; dwFlags
0x1800fa143  call    cs:__imp_NCryptOpenKey
0x1800fa149  mov     ebx, eax
0x1800fa14b  test    eax, eax
0x1800fa14d  js      loc_1800FA233
0x1800fa153  mov     esi, 1
0x1800fa158  mov     edx, [rdi+38h]; dwKeySpec
0x1800fa15b  lea     rax, [rbp+arg_0]
0x1800fa15f  mov     rcx, [rbp+phProv]; hCryptProvOrNCryptKey
0x1800fa163  xor     r9d, r9d; pszPublicKeyObjId
0x1800fa166  mov     [rsp+50h+pcbInfo], rax; pcbInfo
0x1800fa16b  mov     r8d, 10001h; dwCertEncodingType
0x1800fa171  mov     [rsp+50h+pInfo], r12; pInfo
0x1800fa176  mov     [rsp+50h+pvAuxInfo], r12; pvAuxInfo
0x1800fa17b  mov     [rsp+50h+dwFlags], r12d; dwFlags
0x1800fa180  mov     [rbp+arg_0], r12d
0x1800fa184  call    CryptExportPublicKeyInfoEx
0x1800fa189  test    eax, eax
0x1800fa18b  jnz     short loc_1800FA1A4
0x1800fa18d  call    cs:__imp_GetLastError
0x1800fa193  mov     ebx, eax
0x1800fa195  test    eax, eax
0x1800fa197  jle     short loc_1800FA20E
0x1800fa199  movzx   ebx, ax
0x1800fa19c  or      ebx, 80070000h
0x1800fa1a2  jmp     short loc_1800FA20E
0x1800fa1a4  mov     ecx, [rbp+arg_0]; uBytes
0x1800fa1a7  call    PFXHelpAlloc
0x1800fa1ac  mov     r14, rax
0x1800fa1af  test    rax, rax
0x1800fa1b2  jnz     short loc_1800FA1BB
0x1800fa1b4  mov     ebx, 8007000Eh
0x1800fa1b9  jmp     short loc_1800FA20E
0x1800fa1bb  mov     edx, [rdi+38h]; dwKeySpec
0x1800fa1be  lea     rax, [rbp+arg_0]
0x1800fa1c2  mov     rcx, [rbp+phProv]; hCryptProvOrNCryptKey
0x1800fa1c6  xor     r9d, r9d; pszPublicKeyObjId
0x1800fa1c9  mov     [rsp+50h+pcbInfo], rax; pcbInfo
0x1800fa1ce  mov     r8d, 10001h; dwCertEncodingType
0x1800fa1d4  mov     [rsp+50h+pInfo], r14; pInfo
0x1800fa1d9  mov     [rsp+50h+pvAuxInfo], r12; pvAuxInfo
0x1800fa1de  mov     [rsp+50h+dwFlags], r12d; dwFlags
0x1800fa1e3  call    CryptExportPublicKeyInfoEx
0x1800fa1e8  test    eax, eax
0x1800fa1ea  jnz     short loc_1800FA20B
0x1800fa1ec  call    cs:__imp_GetLastError
0x1800fa1f2  mov     ebx, eax
0x1800fa1f4  test    eax, eax
0x1800fa1f6  jle     short loc_1800FA201
0x1800fa1f8  movzx   ebx, ax
0x1800fa1fb  or      ebx, 80070000h
0x1800fa201  mov     rcx, r14
0x1800fa204  call    PFXHelpFree
0x1800fa209  jmp     short loc_1800FA20E
0x1800fa20b  mov     [r15], r14
0x1800fa20e  test    esi, esi
0x1800fa210  jz      short loc_1800FA233
0x1800fa212  mov     rcx, [rbp+phProv]; hObject
0x1800fa216  cmp     [rdi+50h], r12d
0x1800fa21a  jz      short loc_1800FA226
0x1800fa21c  xor     edx, edx; dwFlags
0x1800fa21e  call    cs:__imp_CryptReleaseContext
0x1800fa224  jmp     short loc_1800FA233
0x1800fa226  call    cs:__imp_NCryptFreeObject
0x1800fa22c  jmp     short loc_1800FA233
0x1800fa22e  mov     ebx, 80004005h
0x1800fa233  mov     rcx, [rbp+phProvider]; hObject
0x1800fa237  test    rcx, rcx
0x1800fa23a  jz      short loc_1800FA242
0x1800fa23c  call    cs:__imp_NCryptFreeObject
0x1800fa242  lea     r11, [rsp+50h+var_s0]
0x1800fa247  mov     eax, ebx
0x1800fa249  mov     rbx, [r11+38h]
0x1800fa24d  mov     rsi, [r11+40h]
0x1800fa251  mov     rsp, r11
0x1800fa254  pop     r15
0x1800fa256  pop     r14
0x1800fa258  pop     r12
0x1800fa25a  pop     rdi
0x1800fa25b  pop     rbp
0x1800fa25c  retn
```
