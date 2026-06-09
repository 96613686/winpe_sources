# MimeOleGetExtClassId

- ea: `0x180012a00`
- end: `0x180012cc8`
- name: `MimeOleGetExtClassId`
- size: `712`
- prototype: `__int64 __fastcall(LPCSTR lpSubKey, LPCLSID pclsid)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800128a0`

## callees

- `0x180012a00`
- `0x1800cd010`

## import_xrefs

- `MSOERT2!PszToUnicode` at `0x180012c82`
- `MSOERT2!PszToUnicode` at `0x180012c82`
- `ADVAPI32!RegOpenKeyExA` at `0x180012a5e`
- `ADVAPI32!RegOpenKeyExA` at `0x180012b9b`
- `ADVAPI32!RegOpenKeyExA` at `0x180012bce`
- `ADVAPI32!RegOpenKeyExA` at `0x180012a5e`
- `ADVAPI32!RegOpenKeyExA` at `0x180012b9b`
- `ADVAPI32!RegOpenKeyExA` at `0x180012bce`
- `ADVAPI32!RegQueryValueExA` at `0x180012b03`
- `ADVAPI32!RegQueryValueExA` at `0x180012b60`
- `ADVAPI32!RegQueryValueExA` at `0x180012bf4`
- `ADVAPI32!RegQueryValueExA` at `0x180012c69`
- `ADVAPI32!RegQueryValueExA` at `0x180012b03`
- `ADVAPI32!RegQueryValueExA` at `0x180012b60`
- `ADVAPI32!RegQueryValueExA` at `0x180012bf4`
- `ADVAPI32!RegQueryValueExA` at `0x180012c69`
- `ADVAPI32!RegCloseKey` at `0x180012a77`
- `ADVAPI32!RegCloseKey` at `0x180012a87`
- `ADVAPI32!RegCloseKey` at `0x180012b73`
- `ADVAPI32!RegCloseKey` at `0x180012a77`
- `ADVAPI32!RegCloseKey` at `0x180012a87`
- `ADVAPI32!RegCloseKey` at `0x180012b73`
- `ole32!CLSIDFromString` at `0x180012c96`
- `ole32!CLSIDFromString` at `0x180012c96`

## string_xrefs

- `0x180012bc7`: `CLSID`

## pseudocode

```c
__int64 __fastcall MimeOleGetExtClassId(LPCSTR lpSubKey, LPCLSID pclsid)
{
  const CHAR *v3; // rdi
  BYTE *v4; // rsi
  const OLECHAR *v5; // rbp
  unsigned int v6; // ebx
  BYTE *lpData; // rax
  const OLECHAR *v9; // rax
  DWORD cbData; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp+20h] BYREF

  cbData = 0;
  hKey = 0;
  phkResult = 0;
  if ( !lpSubKey || !pclsid )
    return 2147942487LL;
  v3 = 0;
  v4 = 0;
  v5 = 0;
  if ( RegOpenKeyExA(HKEY_CLASSES_ROOT, lpSubKey, 0, 0x20019u, &hKey) )
  {
    v6 = -2146644475;
  }
  else
  {
    if ( !RegQueryValueExA(hKey, 0, 0, 0, 0, &cbData) )
    {
      lpData = (BYTE *)((__int64 (__fastcall *)(LPMALLOC, _QWORD))g_pMalloc->lpVtbl->Alloc)(g_pMalloc, cbData + 1);
      v3 = (const CHAR *)lpData;
      if ( lpData )
      {
        lpData[cbData] = 0;
        if ( RegQueryValueExA(hKey, 0, 0, 0, lpData, &cbData) )
        {
          v6 = -2147467259;
          goto LABEL_5;
        }
        RegCloseKey(hKey);
        hKey = 0;
        if ( RegOpenKeyExA(HKEY_CLASSES_ROOT, v3, 0, 0x20019u, &hKey) )
        {
          v6 = -2146644475;
          goto LABEL_5;
        }
        if ( RegOpenKeyExA(hKey, "CLSID", 0, 0x20019u, &phkResult) )
        {
          v6 = -2146644475;
          goto LABEL_5;
        }
        if ( RegQueryValueExA(phkResult, 0, 0, 0, 0, &cbData) )
        {
          v6 = -2147467259;
          goto LABEL_5;
        }
        v4 = (BYTE *)((__int64 (__fastcall *)(LPMALLOC, _QWORD))g_pMalloc->lpVtbl->Alloc)(g_pMalloc, ++cbData);
        if ( v4 )
        {
          if ( RegQueryValueExA(phkResult, 0, 0, 0, v4, &cbData) )
          {
            v6 = -2147467259;
            goto LABEL_5;
          }
          v9 = (const OLECHAR *)PszToUnicode(0, v4);
          v5 = v9;
          if ( v9 )
          {
            v6 = CLSIDFromString(v9, pclsid);
            goto LABEL_5;
          }
        }
      }
      v6 = -2147024882;
      goto LABEL_5;
    }
    v6 = -2146644475;
  }
LABEL_5:
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v3 )
    ((void (__fastcall *)(LPMALLOC, const CHAR *))g_pMalloc->lpVtbl->Free)(g_pMalloc, v3);
  if ( v5 )
    ((void (__fastcall *)(LPMALLOC, const OLECHAR *))g_pMalloc->lpVtbl->Free)(g_pMalloc, v5);
  if ( v4 )
    ((void (__fastcall *)(LPMALLOC, BYTE *))g_pMalloc->lpVtbl->Free)(g_pMalloc, v4);
  return v6;
}

```

## disassembly

```asm
0x180012a00  mov     r11, rsp
0x180012a03  push    rbx
0x180012a04  push    r14
0x180012a06  sub     rsp, 48h
0x180012a0a  xor     r14d, r14d
0x180012a0d  mov     rbx, rdx
0x180012a10  mov     [r11+8], r14d
0x180012a14  mov     [r11+18h], r14
0x180012a18  mov     [r11+20h], r14
0x180012a1c  test    rcx, rcx
0x180012a1f  jz      loc_180012CBE
0x180012a25  test    rdx, rdx
0x180012a28  jz      loc_180012CBE
0x180012a2e  mov     [r11-18h], rbp
0x180012a32  lea     rax, [r11+18h]
0x180012a36  mov     [r11-20h], rsi
0x180012a3a  mov     rdx, rcx; lpSubKey
0x180012a3d  mov     [r11-28h], rdi
0x180012a41  mov     r9d, 20019h; samDesired
0x180012a47  xor     r8d, r8d; ulOptions
0x180012a4a  mov     [r11-38h], rax
0x180012a4e  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180012a55  mov     edi, r14d
0x180012a58  mov     esi, r14d
0x180012a5b  mov     ebp, r14d
0x180012a5e  call    cs:__imp_RegOpenKeyExA
0x180012a64  test    eax, eax
0x180012a66  jz      short loc_180012AE7
0x180012a68  mov     ebx, 800CCE05h
0x180012a6d  mov     rcx, [rsp+58h+hKey]; hKey
0x180012a72  test    rcx, rcx
0x180012a75  jz      short loc_180012A7D
0x180012a77  call    cs:__imp_RegCloseKey
0x180012a7d  mov     rcx, [rsp+58h+phkResult]; hKey
0x180012a82  test    rcx, rcx
0x180012a85  jz      short loc_180012A8D
0x180012a87  call    cs:__imp_RegCloseKey
0x180012a8d  test    rdi, rdi
0x180012a90  jz      short loc_180012AA8
0x180012a92  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x180012a99  mov     rdx, rdi
0x180012a9c  mov     rax, [rcx]
0x180012a9f  mov     rax, [rax+28h]
0x180012aa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012aa8  mov     rdi, [rsp+58h+var_28]
0x180012aad  test    rbp, rbp
0x180012ab0  jnz     loc_180012CA3
0x180012ab6  mov     rbp, [rsp+58h+var_18]
0x180012abb  test    rsi, rsi
0x180012abe  jnz     short loc_180012ACF
0x180012ac0  mov     rsi, [rsp+58h+var_20]
0x180012ac5  mov     eax, ebx
0x180012ac7  add     rsp, 48h
0x180012acb  pop     r14
0x180012acd  pop     rbx
0x180012ace  retn
0x180012acf  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x180012ad6  mov     rdx, rsi
0x180012ad9  mov     rax, [rcx]
0x180012adc  mov     rax, [rax+28h]
0x180012ae0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ae5  jmp     short loc_180012AC0
0x180012ae7  mov     rcx, [rsp+58h+hKey]; hKey
0x180012aec  lea     rax, [rsp+58h+cbData]
0x180012af1  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180012af6  xor     r9d, r9d; lpType
0x180012af9  xor     r8d, r8d; lpReserved
0x180012afc  mov     [rsp+58h+lpData], r14; lpData
0x180012b01  xor     edx, edx; lpValueName
0x180012b03  call    cs:__imp_RegQueryValueExA
0x180012b09  test    eax, eax
0x180012b0b  jz      short loc_180012B17
0x180012b0d  mov     ebx, 800CCE05h
0x180012b12  jmp     loc_180012A6D
0x180012b17  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x180012b1e  mov     edx, [rsp+58h+cbData]
0x180012b22  inc     edx
0x180012b24  mov     r8, [rcx]
0x180012b27  mov     rax, [r8+18h]
0x180012b2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b30  mov     rdi, rax
0x180012b33  test    rax, rax
0x180012b36  jz      loc_180012C25
0x180012b3c  mov     eax, [rsp+58h+cbData]
0x180012b40  xor     r9d, r9d; lpType
0x180012b43  xor     r8d, r8d; lpReserved
0x180012b46  xor     edx, edx; lpValueName
0x180012b48  mov     [rax+rdi], sil
0x180012b4c  lea     rax, [rsp+58h+cbData]
0x180012b51  mov     rcx, [rsp+58h+hKey]; hKey
0x180012b56  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180012b5b  mov     [rsp+58h+lpData], rdi; lpData
0x180012b60  call    cs:__imp_RegQueryValueExA
0x180012b66  test    eax, eax
0x180012b68  jnz     loc_180012C39
0x180012b6e  mov     rcx, [rsp+58h+hKey]; hKey
0x180012b73  call    cs:__imp_RegCloseKey
0x180012b79  lea     rax, [rsp+58h+hKey]
0x180012b7e  mov     [rsp+58h+hKey], r14
0x180012b83  mov     r9d, 20019h; samDesired
0x180012b89  mov     [rsp+58h+lpData], rax; phkResult
0x180012b8e  xor     r8d, r8d; ulOptions
0x180012b91  mov     rdx, rdi; lpSubKey
0x180012b94  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180012b9b  call    cs:__imp_RegOpenKeyExA
0x180012ba1  test    eax, eax
0x180012ba3  jz      short loc_180012BAF
0x180012ba5  mov     ebx, 800CCE05h
0x180012baa  jmp     loc_180012A6D
0x180012baf  mov     rcx, [rsp+58h+hKey]; hKey
0x180012bb4  lea     rax, [rsp+58h+phkResult]
0x180012bb9  mov     r9d, 20019h; samDesired
0x180012bbf  mov     [rsp+58h+lpData], rax; phkResult
0x180012bc4  xor     r8d, r8d; ulOptions
0x180012bc7  lea     rdx, c_szCLSID; "CLSID"
0x180012bce  call    cs:__imp_RegOpenKeyExA
0x180012bd4  test    eax, eax
0x180012bd6  jnz     short loc_180012C2F
0x180012bd8  mov     rcx, [rsp+58h+phkResult]; hKey
0x180012bdd  lea     rax, [rsp+58h+cbData]
0x180012be2  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180012be7  xor     r9d, r9d; lpType
0x180012bea  xor     r8d, r8d; lpReserved
0x180012bed  mov     [rsp+58h+lpData], r14; lpData
0x180012bf2  xor     edx, edx; lpValueName
0x180012bf4  call    cs:__imp_RegQueryValueExA
0x180012bfa  test    eax, eax
0x180012bfc  jnz     short loc_180012C43
0x180012bfe  mov     eax, [rsp+58h+cbData]
0x180012c02  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x180012c09  inc     eax
0x180012c0b  mov     [rsp+58h+cbData], eax
0x180012c0f  mov     edx, eax
0x180012c11  mov     rax, [rcx]
0x180012c14  mov     rax, [rax+18h]
0x180012c18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c1d  mov     rsi, rax
0x180012c20  test    rax, rax
0x180012c23  jnz     short loc_180012C4D
0x180012c25  mov     ebx, 8007000Eh
0x180012c2a  jmp     loc_180012A6D
0x180012c2f  mov     ebx, 800CCE05h
0x180012c34  jmp     loc_180012A6D
0x180012c39  mov     ebx, 80004005h
0x180012c3e  jmp     loc_180012A6D
0x180012c43  mov     ebx, 80004005h
0x180012c48  jmp     loc_180012A6D
0x180012c4d  mov     rcx, [rsp+58h+phkResult]; hKey
0x180012c52  lea     rax, [rsp+58h+cbData]
0x180012c57  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180012c5c  xor     r9d, r9d; lpType
0x180012c5f  xor     r8d, r8d; lpReserved
0x180012c62  mov     [rsp+58h+lpData], rsi; lpData
0x180012c67  xor     edx, edx; lpValueName
0x180012c69  call    cs:__imp_RegQueryValueExA
0x180012c6f  test    eax, eax
0x180012c71  jz      short loc_180012C7D
0x180012c73  mov     ebx, 80004005h
0x180012c78  jmp     loc_180012A6D
0x180012c7d  mov     rdx, rsi
0x180012c80  xor     ecx, ecx
0x180012c82  call    cs:__imp_PszToUnicode
0x180012c88  mov     rbp, rax
0x180012c8b  test    rax, rax
0x180012c8e  jz      short loc_180012C25
0x180012c90  mov     rdx, rbx; pclsid
0x180012c93  mov     rcx, rax; lpsz
0x180012c96  call    cs:__imp_CLSIDFromString
0x180012c9c  mov     ebx, eax
0x180012c9e  jmp     loc_180012A6D
0x180012ca3  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x180012caa  mov     rdx, rbp
0x180012cad  mov     rax, [rcx]
0x180012cb0  mov     rax, [rax+28h]
0x180012cb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012cb9  jmp     loc_180012AB6
0x180012cbe  mov     eax, 80070057h
0x180012cc3  jmp     loc_180012AC7
```
