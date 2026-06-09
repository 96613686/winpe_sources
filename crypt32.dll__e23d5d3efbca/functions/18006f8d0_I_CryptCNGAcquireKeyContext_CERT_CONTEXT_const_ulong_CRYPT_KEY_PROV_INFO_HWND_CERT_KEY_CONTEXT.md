# I_CryptCNGAcquireKeyContext(_CERT_CONTEXT const *,ulong,_CRYPT_KEY_PROV_INFO *,HWND__ *,_CERT_KEY_CONTEXT *)

- ea: `0x18006f8d0`
- end: `0x18006fbc4`
- name: `?I_CryptCNGAcquireKeyContext@@YAHPEBU_CERT_CONTEXT@@KPEAU_CRYPT_KEY_PROV_INFO@@PEAUHWND__@@PEAU_CERT_KEY_CONTEXT@@@Z`
- size: `756`
- prototype: `__int64 __fastcall(const struct _CERT_CONTEXT *, unsigned int, struct _CRYPT_KEY_PROV_INFO *, HWND, struct _CERT_KEY_CONTEXT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18006f478`

## callees

- `0x18002a7d8`
- `0x18006f8d0`
- `0x1800bec20`
- `0x180115040`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fa30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fa30`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006fa2a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006fa75`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006fa2a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006fa75`
- `ncrypt!NCryptOpenStorageProvider` at `0x18006fb2c`
- `ncrypt!NCryptOpenStorageProvider` at `0x18006fb2c`
- `ncrypt!NCryptOpenKey` at `0x18006fb83`
- `ncrypt!NCryptOpenKey` at `0x18006fb83`
- `ncrypt!NCryptFreeObject` at `0x18006fa44`
- `ncrypt!NCryptFreeObject` at `0x18006fa44`
- `ncrypt!NCryptSetProperty` at `0x18006fb5e`
- `ncrypt!NCryptSetProperty` at `0x18006fbaa`
- `ncrypt!NCryptSetProperty` at `0x18006fb5e`
- `ncrypt!NCryptSetProperty` at `0x18006fbaa`
- `SspiCli!GetUserNameExW` at `0x18006fb10`
- `SspiCli!GetUserNameExW` at `0x18006fb10`
- `CRYPTSP!CryptGetDefaultProviderW` at `0x18006f975`
- `CRYPTSP!CryptGetDefaultProviderW` at `0x18006fabb`
- `CRYPTSP!CryptGetDefaultProviderW` at `0x18006f975`
- `CRYPTSP!CryptGetDefaultProviderW` at `0x18006fabb`

## pseudocode

```c
__int64 __fastcall I_CryptCNGAcquireKeyContext(
        const struct _CERT_CONTEXT *a1,
        int a2,
        struct _CRYPT_KEY_PROV_INFO *a3,
        HWND a4,
        struct _CERT_KEY_CONTEXT *a5)
{
  WCHAR *v5; // rbx
  unsigned int v7; // r15d
  LPWSTR pwszProvName; // r14
  DWORD v9; // ecx
  DWORD v10; // eax
  int v11; // r12d
  __int64 v12; // rdx
  unsigned __int64 v13; // rdi
  unsigned __int64 v14; // rcx
  __int64 v15; // rcx
  unsigned __int64 v16; // rcx
  void *v17; // rsp
  void *v18; // rsp
  WCHAR *v19; // rax
  DWORD v20; // ecx
  DWORD LastError; // edi
  LPWSTR pwszContainerName; // rdi
  __int64 v24; // rax
  SECURITY_STATUS v25; // r14d
  DWORD dwKeySpec; // r9d
  __int64 v27; // [rsp+0h] [rbp-30h] BYREF
  DWORD *pcbProvName; // [rsp+20h] [rbp-10h]
  DWORD v29; // [rsp+30h] [rbp+0h] BYREF
  BYTE pbInput[8]; // [rsp+38h] [rbp+8h] BYREF
  NCRYPT_HANDLE hObject; // [rsp+40h] [rbp+10h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+48h] [rbp+18h] BYREF
  ULONG nSize[4]; // [rsp+50h] [rbp+20h] BYREF
  WCHAR NameBuffer[264]; // [rsp+60h] [rbp+30h] BYREF

  v5 = 0;
  *(_QWORD *)pbInput = a4;
  hObject = 0;
  phKey = 0;
  a5->dwKeySpec = -1;
  v7 = 1;
  pwszProvName = a3->pwszProvName;
  v9 = a3->dwFlags & 0x20;
  v10 = a2 | a3->dwFlags;
  v29 = 0;
  v11 = v9 | 0x40;
  if ( (v10 & 0x40) == 0 )
    v11 = v9;
  if ( !pwszProvName || !*pwszProvName )
  {
    if ( !CryptGetDefaultProviderW(a3->dwProvType, 0, 1u, 0, &v29) || v29 < 2 )
      goto LABEL_20;
    v13 = v29 + 2LL;
    if ( v13 > g_ulMaxStackAllocSize )
      goto LABEL_54;
    v14 = v13 + g_ulAdditionalProbeSize + 8;
    if ( v14 < v13 || !(unsigned int)VerifyStackAvailable(v14, v12) )
      goto LABEL_54;
    v15 = v13 + 23;
    if ( v13 + 23 <= v13 + 8 )
      v15 = 0xFFFFFFFFFFFFFF0LL;
    v16 = v15 & 0xFFFFFFFFFFFFFFF0uLL;
    v17 = alloca(v16);
    v18 = alloca(v16);
    v5 = (WCHAR *)&v29;
    if ( &v27 == (__int64 *)-48LL || (v29 = 1801679955, (v5 = (WCHAR *)pbInput) == 0) )
    {
LABEL_54:
      if ( v13 + 8 >= v13 )
      {
        v19 = (WCHAR *)((__int64 (*)(void))g_pfnAllocate)();
        v5 = v19;
        if ( v19 )
        {
          *(_DWORD *)v19 = 1885431112;
          v5 = v19 + 4;
        }
      }
    }
    if ( !v5 )
    {
      v20 = -2147024882;
LABEL_19:
      SetLastError(v20);
LABEL_20:
      LastError = GetLastError();
      v7 = 0;
      goto LABEL_21;
    }
    if ( !CryptGetDefaultProviderW(a3->dwProvType, 0, 1u, v5, &v29) )
      goto LABEL_20;
    pwszProvName = v5;
  }
  pwszContainerName = a3->pwszContainerName;
  if ( !a3->pwszContainerName || !*pwszContainerName )
  {
    if ( (a3->dwFlags & 0x20) == 0 || a3->dwProvType == 3 || a3->dwProvType == 13 || a3->dwProvType == 18 )
    {
      nSize[0] = 257;
      if ( !GetUserNameExW(NameSamCompatible, NameBuffer, nSize) )
        goto LABEL_20;
      pwszContainerName = NameBuffer;
    }
    else
    {
      pwszContainerName = L"DefaultKeys";
    }
  }
  LODWORD(v24) = NCryptOpenStorageProvider(&hObject, pwszProvName, 0);
  if ( (_DWORD)v24 )
    goto LABEL_41;
  v25 = 0;
  if ( *(_QWORD *)pbInput )
    v25 = NCryptSetProperty(hObject, L"HWND Handle", pbInput, 8u, 0);
  dwKeySpec = 0;
  LODWORD(pcbProvName) = v11;
  if ( a3->dwKeySpec != -1 )
    dwKeySpec = a3->dwKeySpec;
  LODWORD(v24) = NCryptOpenKey(hObject, &phKey, pwszContainerName, dwKeySpec, (DWORD)pcbProvName);
  if ( (_DWORD)v24 )
    goto LABEL_41;
  if ( *(_QWORD *)pbInput != v24 )
    LODWORD(v24) = NCryptSetProperty(phKey, L"HWND Handle", pbInput, 8u, 0);
  if ( v25 && (_DWORD)v24 )
  {
LABEL_41:
    v20 = v24;
    goto LABEL_19;
  }
  LastError = 0;
LABEL_21:
  if ( hObject )
    NCryptFreeObject(hObject);
  if ( v5 && *((_DWORD *)v5 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  a5->hCryptProv = phKey;
  if ( LastError )
    SetLastError(LastError);
  return v7;
}

```

## disassembly

```asm
0x18006f8d0  push    rbp
0x18006f8d2  push    rsi
0x18006f8d3  push    rdi
0x18006f8d4  push    r12
0x18006f8d6  push    r13
0x18006f8d8  push    r14
0x18006f8da  push    r15
0x18006f8dc  sub     rsp, 280h
0x18006f8e3  lea     rbp, [rsp+30h]
0x18006f8e8  mov     [rbp+280h+arg_0], rbx
0x18006f8ef  mov     rax, cs:__security_cookie
0x18006f8f6  xor     rax, rbp
0x18006f8f9  mov     [rbp+280h+var_40], rax
0x18006f900  mov     r13, [rbp+280h+arg_20]
0x18006f907  xor     ebx, ebx
0x18006f909  mov     rsi, r8
0x18006f90c  mov     qword ptr [rbp+280h+pbInput], r9
0x18006f910  mov     [rbp+280h+hObject], 0
0x18006f918  mov     [rbp+280h+phKey], 0
0x18006f920  mov     dword ptr [r13+10h], 0FFFFFFFFh
0x18006f928  lea     r15d, [rbx+1]
0x18006f92c  mov     eax, [r8+14h]
0x18006f930  mov     ecx, eax
0x18006f932  mov     r14, [r8+8]
0x18006f936  and     ecx, 20h
0x18006f939  or      eax, edx
0x18006f93b  mov     [rbp+280h+var_280], ebx
0x18006f93e  test    al, 40h
0x18006f940  mov     r12d, ecx
0x18006f943  setz    al
0x18006f946  or      r12d, 40h
0x18006f94a  test    al, al
0x18006f94c  cmovnz  r12d, ecx
0x18006f950  test    r14, r14
0x18006f953  jz      short loc_18006F961
0x18006f955  xor     eax, eax
0x18006f957  cmp     ax, [r14]
0x18006f95b  jnz     loc_18006FACC
0x18006f961  mov     ecx, [rsi+10h]; dwProvType
0x18006f964  lea     rax, [rbp+280h+var_280]
0x18006f968  xor     r9d, r9d; pszProvName
0x18006f96b  mov     [rsp+2B0h+pcbProvName], rax; pcbProvName
0x18006f970  mov     r8d, r15d; dwFlags
0x18006f973  xor     edx, edx; pdwReserved
0x18006f975  call    cs:__imp_CryptGetDefaultProviderW
0x18006f97b  test    eax, eax
0x18006f97d  jz      loc_18006FA30
0x18006f983  cmp     [rbp+280h+var_280], 2
0x18006f987  jb      loc_18006FA30
0x18006f98d  mov     edi, [rbp+280h+var_280]
0x18006f990  add     rdi, 2
0x18006f994  cmp     rdi, cs:g_ulMaxStackAllocSize
0x18006f99b  ja      short loc_18006F9F5
0x18006f99d  mov     rcx, cs:g_ulAdditionalProbeSize
0x18006f9a4  add     rcx, 8
0x18006f9a8  add     rcx, rdi
0x18006f9ab  cmp     rcx, rdi
0x18006f9ae  jb      short loc_18006F9F5
0x18006f9b0  call    VerifyStackAvailable
0x18006f9b5  test    eax, eax
0x18006f9b7  jz      short loc_18006F9F5
0x18006f9b9  lea     rax, [rdi+8]
0x18006f9bd  lea     rcx, [rax+0Fh]
0x18006f9c1  cmp     rcx, rax
0x18006f9c4  ja      short loc_18006F9D0
0x18006f9c6  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18006f9d0  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18006f9d4  mov     rax, rcx
0x18006f9d7  call    _alloca_probe
0x18006f9dc  sub     rsp, rcx
0x18006f9df  lea     rbx, [rsp+2B0h+var_280]
0x18006f9e4  test    rbx, rbx
0x18006f9e7  jz      short loc_18006F9F5
0x18006f9e9  mov     dword ptr [rbx], 6B637453h
0x18006f9ef  add     rbx, 8
0x18006f9f3  jnz     short loc_18006FA1C
0x18006f9f5  lea     rcx, [rdi+8]
0x18006f9f9  cmp     rcx, rdi
0x18006f9fc  jb      short loc_18006FA1C
0x18006f9fe  mov     rax, cs:g_pfnAllocate
0x18006fa05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fa0a  mov     rbx, rax
0x18006fa0d  test    rax, rax
0x18006fa10  jz      short loc_18006FA1C
0x18006fa12  mov     dword ptr [rax], 70616548h
0x18006fa18  add     rbx, 8
0x18006fa1c  test    rbx, rbx
0x18006fa1f  jnz     loc_18006FAA7
0x18006fa25  mov     ecx, 8007000Eh; dwErrCode
0x18006fa2a  call    cs:__imp_SetLastError
0x18006fa30  call    cs:__imp_GetLastError
0x18006fa36  mov     edi, eax
0x18006fa38  xor     r15d, r15d
0x18006fa3b  mov     rcx, [rbp+280h+hObject]; hObject
0x18006fa3f  test    rcx, rcx
0x18006fa42  jz      short loc_18006FA4A
0x18006fa44  call    cs:__imp_NCryptFreeObject
0x18006fa4a  test    rbx, rbx
0x18006fa4d  jz      short loc_18006FA67
0x18006fa4f  lea     rcx, [rbx-8]
0x18006fa53  cmp     dword ptr [rcx], 70616548h
0x18006fa59  jnz     short loc_18006FA67
0x18006fa5b  mov     rax, cs:g_pfnFree
0x18006fa62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fa67  mov     rcx, [rbp+280h+phKey]
0x18006fa6b  mov     [r13+8], rcx
0x18006fa6f  test    edi, edi
0x18006fa71  jz      short loc_18006FA7B
0x18006fa73  mov     ecx, edi; dwErrCode
0x18006fa75  call    cs:__imp_SetLastError
0x18006fa7b  mov     eax, r15d
0x18006fa7e  mov     rcx, [rbp+280h+var_40]
0x18006fa85  xor     rcx, rbp; StackCookie
0x18006fa88  call    __security_check_cookie
0x18006fa8d  mov     rbx, [rbp+280h+arg_0]
0x18006fa94  lea     rsp, [rbp+250h]
0x18006fa9b  pop     r15
0x18006fa9d  pop     r14
0x18006fa9f  pop     r13
0x18006faa1  pop     r12
0x18006faa3  pop     rdi
0x18006faa4  pop     rsi
0x18006faa5  pop     rbp
0x18006faa6  retn
0x18006faa7  mov     ecx, [rsi+10h]; dwProvType
0x18006faaa  lea     rax, [rbp+280h+var_280]
0x18006faae  mov     r9, rbx; pszProvName
0x18006fab1  mov     [rsp+2B0h+pcbProvName], rax; pcbProvName
0x18006fab6  mov     r8d, r15d; dwFlags
0x18006fab9  xor     edx, edx; pdwReserved
0x18006fabb  call    cs:__imp_CryptGetDefaultProviderW
0x18006fac1  test    eax, eax
0x18006fac3  jz      loc_18006FA30
0x18006fac9  mov     r14, rbx
0x18006facc  mov     rdi, [rsi]
0x18006facf  test    rdi, rdi
0x18006fad2  jz      short loc_18006FADB
0x18006fad4  xor     eax, eax
0x18006fad6  cmp     ax, [rdi]
0x18006fad9  jnz     short loc_18006FB22
0x18006fadb  test    byte ptr [rsi+14h], 20h
0x18006fadf  jz      short loc_18006FAFC
0x18006fae1  cmp     dword ptr [rsi+10h], 3
0x18006fae5  jz      short loc_18006FAFC
0x18006fae7  cmp     dword ptr [rsi+10h], 0Dh
0x18006faeb  jz      short loc_18006FAFC
0x18006faed  cmp     dword ptr [rsi+10h], 12h
0x18006faf1  jz      short loc_18006FAFC
0x18006faf3  lea     rdi, aDefaultkeys; "DefaultKeys"
0x18006fafa  jmp     short loc_18006FB22
0x18006fafc  lea     r8, [rbp+280h+nSize]; nSize
0x18006fb00  mov     [rbp+280h+nSize], 101h
0x18006fb07  lea     rdx, [rbp+280h+NameBuffer]; lpNameBuffer
0x18006fb0b  mov     ecx, 2; NameFormat
0x18006fb10  call    cs:__imp_GetUserNameExW
0x18006fb16  test    al, al
0x18006fb18  jz      loc_18006FA30
0x18006fb1e  lea     rdi, [rbp+280h+NameBuffer]
0x18006fb22  xor     r8d, r8d; dwFlags
0x18006fb25  lea     rcx, [rbp+280h+hObject]; phProvider
0x18006fb29  mov     rdx, r14; pszProviderName
0x18006fb2c  call    cs:__imp_NCryptOpenStorageProvider
0x18006fb32  test    eax, eax
0x18006fb34  jz      short loc_18006FB3D
0x18006fb36  mov     ecx, eax
0x18006fb38  jmp     loc_18006FA2A
0x18006fb3d  xor     r14d, r14d
0x18006fb40  cmp     qword ptr [rbp+280h+pbInput], r14
0x18006fb44  jz      short loc_18006FB67
0x18006fb46  mov     rcx, [rbp+280h+hObject]; hObject
0x18006fb4a  lea     r9d, [r14+8]; cbInput
0x18006fb4e  lea     r8, [rbp+280h+pbInput]; pbInput
0x18006fb52  mov     dword ptr [rsp+2B0h+pcbProvName], r14d; dwFlags
0x18006fb57  lea     rdx, aHwndHandle; "HWND Handle"
0x18006fb5e  call    cs:__imp_NCryptSetProperty
0x18006fb64  mov     r14d, eax
0x18006fb67  mov     rcx, [rbp+280h+hObject]; hProvider
0x18006fb6b  lea     rdx, [rbp+280h+phKey]; phKey
0x18006fb6f  xor     r9d, r9d
0x18006fb72  mov     dword ptr [rsp+2B0h+pcbProvName], r12d; dwFlags
0x18006fb77  cmp     dword ptr [rsi+28h], 0FFFFFFFFh
0x18006fb7b  mov     r8, rdi; pszKeyName
0x18006fb7e  cmovnz  r9d, [rsi+28h]; dwLegacyKeySpec
0x18006fb83  call    cs:__imp_NCryptOpenKey
0x18006fb89  test    eax, eax
0x18006fb8b  jnz     short loc_18006FB36
0x18006fb8d  cmp     qword ptr [rbp+280h+pbInput], rax
0x18006fb91  jz      short loc_18006FBB0
0x18006fb93  mov     rcx, [rbp+280h+phKey]; hObject
0x18006fb97  lea     r9d, [rax+8]; cbInput
0x18006fb9b  lea     r8, [rbp+280h+pbInput]; pbInput
0x18006fb9f  mov     dword ptr [rsp+2B0h+pcbProvName], eax; dwFlags
0x18006fba3  lea     rdx, aHwndHandle; "HWND Handle"
0x18006fbaa  call    cs:__imp_NCryptSetProperty
0x18006fbb0  test    r14d, r14d
0x18006fbb3  jz      short loc_18006FBBD
0x18006fbb5  test    eax, eax
0x18006fbb7  jnz     loc_18006FB36
0x18006fbbd  xor     edi, edi
0x18006fbbf  jmp     loc_18006FA3B
```
