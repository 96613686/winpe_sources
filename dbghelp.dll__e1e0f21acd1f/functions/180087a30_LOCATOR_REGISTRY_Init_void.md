# LOCATOR::REGISTRY::Init(void)

- ea: `0x180087a30`
- end: `0x180087c3b`
- name: `?Init@REGISTRY@LOCATOR@@AEAAXXZ`
- size: `523`
- prototype: `void __fastcall(LOCATOR::REGISTRY *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180085360`
- `0x180086180`

## callees

- `0x180026980`
- `0x1800269f8`
- `0x180087a30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180087a40`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180087a40`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180087c2f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180087c2f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180087b9f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180087bd7`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180087b9f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180087bd7`
- `api-ms-win-core-localregistry-l1-1-0!RegQueryValueExW` at `0x180087ab3`
- `api-ms-win-core-localregistry-l1-1-0!RegQueryValueExW` at `0x180087b4b`
- `api-ms-win-core-localregistry-l1-1-0!RegQueryValueExW` at `0x180087ab3`
- `api-ms-win-core-localregistry-l1-1-0!RegQueryValueExW` at `0x180087b4b`
- `api-ms-win-core-localregistry-l1-1-0!RegOpenKeyExW` at `0x180087a74`
- `api-ms-win-core-localregistry-l1-1-0!RegOpenKeyExW` at `0x180087a74`
- `api-ms-win-core-localregistry-l1-1-0!RegCloseKey` at `0x180087ac5`
- `api-ms-win-core-localregistry-l1-1-0!RegCloseKey` at `0x180087b1a`
- `api-ms-win-core-localregistry-l1-1-0!RegCloseKey` at `0x180087b5b`
- `api-ms-win-core-localregistry-l1-1-0!RegCloseKey` at `0x180087ac5`
- `api-ms-win-core-localregistry-l1-1-0!RegCloseKey` at `0x180087b1a`
- `api-ms-win-core-localregistry-l1-1-0!RegCloseKey` at `0x180087b5b`

## string_xrefs

- `0x180087a94`: `SymbolSearchPath`
- `0x180087b44`: `SymbolSearchPath`

## pseudocode

```c
void __fastcall LOCATOR::REGISTRY::Init(LOCATOR::REGISTRY *this)
{
  HKEY v2; // rcx
  __int64 v3; // rbp
  unsigned __int64 v4; // rax
  BYTE *v5; // rax
  const WCHAR *v6; // rsi
  LSTATUS v7; // ebx
  char *v8; // rdi
  PSGSI1::EnumPubsByAddr *v9; // rcx
  DWORD v10; // eax
  unsigned __int64 v11; // rbp
  unsigned __int64 v12; // rax
  WCHAR *v13; // rax
  WCHAR *v14; // rbx
  char *v15; // rdi
  PSGSI1::EnumPubsByAddr *v16; // rcx
  char v17; // [rsp+30h] [rbp-38h] BYREF
  char v18; // [rsp+38h] [rbp-30h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+8h] BYREF
  DWORD Type; // [rsp+78h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+18h] BYREF

  EnterCriticalSection(&LOCATOR::REGISTRY::m_cs);
  if ( *((_BYTE *)this + 8) )
    goto LABEL_26;
  v2 = *(HKEY *)this;
  *((_BYTE *)this + 8) = 1;
  if ( RegOpenKeyExW(v2, L"Software\\Microsoft\\VisualStudio\\MSPDB", 0, 1u, &hKey) )
    goto LABEL_26;
  cbData = 0;
  if ( RegQueryValueExW(hKey, L"SymbolSearchPath", 0, 0, 0, &cbData) )
    goto LABEL_4;
  v3 = cbData >> 1;
  v4 = 2LL * (unsigned int)(v3 + 1);
  if ( !is_mul_ok((unsigned int)(v3 + 1), 2u) )
    v4 = -1;
  v5 = (BYTE *)operator new[](v4, (const struct std::nothrow_t *)&std::nothrow);
  v6 = (const WCHAR *)v5;
  if ( !v5 )
  {
LABEL_4:
    RegCloseKey(hKey);
    goto LABEL_26;
  }
  v7 = RegQueryValueExW(hKey, L"SymbolSearchPath", 0, &Type, v5, &cbData);
  RegCloseKey(hKey);
  if ( v7 )
    goto LABEL_24;
  v6[v3] = 0;
  if ( Type != 1 )
  {
    if ( Type != 2 )
      goto LABEL_24;
    v10 = ExpandEnvironmentStringsW(v6, 0, 0);
    v11 = v10;
    if ( !v10 )
      goto LABEL_24;
    v12 = 2LL * v10;
    if ( !is_mul_ok(v11, 2u) )
      v12 = -1;
    v13 = (WCHAR *)operator new[](v12, (const struct std::nothrow_t *)&std::nothrow);
    v14 = v13;
    if ( !v13 )
      goto LABEL_24;
    if ( !ExpandEnvironmentStringsW(v6, v13, v11) || (v15 = (char *)this + 16, v15 == &v18) )
    {
      v16 = (PSGSI1::EnumPubsByAddr *)v14;
    }
    else
    {
      v16 = *(PSGSI1::EnumPubsByAddr **)v15;
      *(_QWORD *)v15 = v14;
      if ( !v16 )
        goto LABEL_24;
    }
    PSGSI1::EnumPubsByAddr::release(v16);
    goto LABEL_24;
  }
  v8 = (char *)this + 16;
  if ( v8 == &v17 )
  {
LABEL_24:
    v9 = (PSGSI1::EnumPubsByAddr *)v6;
LABEL_25:
    PSGSI1::EnumPubsByAddr::release(v9);
    goto LABEL_26;
  }
  v9 = *(PSGSI1::EnumPubsByAddr **)v8;
  *(_QWORD *)v8 = v6;
  if ( v9 )
    goto LABEL_25;
LABEL_26:
  LeaveCriticalSection(&LOCATOR::REGISTRY::m_cs);
}

```

## disassembly

```asm
0x180087a30  push    rdi
0x180087a32  sub     rsp, 60h
0x180087a36  mov     rdi, rcx
0x180087a39  lea     rcx, ?m_cs@REGISTRY@LOCATOR@@0VCriticalSectionNoLog@@A; lpCriticalSection
0x180087a40  call    cs:__imp_EnterCriticalSection
0x180087a46  cmp     byte ptr [rdi+8], 0
0x180087a4a  jnz     loc_180087C28
0x180087a50  mov     rcx, [rdi]; hKey
0x180087a53  lea     rax, [rsp+68h+hKey]
0x180087a5b  mov     r9d, 1; samDesired
0x180087a61  mov     [rsp+68h+phkResult], rax; phkResult
0x180087a66  xor     r8d, r8d; ulOptions
0x180087a69  mov     byte ptr [rdi+8], 1
0x180087a6d  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\VisualStudio\\MSPD"...
0x180087a74  call    cs:__imp_RegOpenKeyExW
0x180087a7a  test    eax, eax
0x180087a7c  jnz     loc_180087C28
0x180087a82  mov     rcx, [rsp+68h+hKey]; hKey
0x180087a8a  lea     rax, [rsp+68h+cbData]
0x180087a8f  mov     [rsp+68h+lpcbData], rax; lpcbData
0x180087a94  lea     rdx, aSymbolsearchpa; "SymbolSearchPath"
0x180087a9b  mov     [rsp+68h+var_20], r14
0x180087aa0  xor     r9d, r9d; lpType
0x180087aa3  xor     r14d, r14d
0x180087aa6  xor     r8d, r8d; lpReserved
0x180087aa9  mov     [rsp+68h+cbData], r14d
0x180087aae  mov     [rsp+68h+phkResult], r14; lpData
0x180087ab3  call    cs:__imp_RegQueryValueExW
0x180087ab9  test    eax, eax
0x180087abb  jz      short loc_180087AD0
0x180087abd  mov     rcx, [rsp+68h+hKey]; hKey
0x180087ac5  call    cs:__imp_RegCloseKey
0x180087acb  jmp     loc_180087C23
0x180087ad0  mov     [rsp+68h+var_10], rbp
0x180087ad5  mov     eax, 2
0x180087ada  mov     ebp, [rsp+68h+cbData]
0x180087ade  shr     ebp, 1
0x180087ae0  mov     [rsp+68h+var_18], rsi
0x180087ae5  mov     [rsp+68h+var_28], r15
0x180087aea  mov     r15, 0FFFFFFFFFFFFFFFFh
0x180087af1  lea     ecx, [rbp+1]
0x180087af4  mul     rcx
0x180087af7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180087afe  cmovb   rax, r15
0x180087b02  mov     rcx, rax; unsigned __int64
0x180087b05  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180087b0a  mov     rcx, [rsp+68h+hKey]; hKey
0x180087b12  mov     rsi, rax
0x180087b15  test    rax, rax
0x180087b18  jnz     short loc_180087B25
0x180087b1a  call    cs:__imp_RegCloseKey
0x180087b20  jmp     loc_180087C14
0x180087b25  lea     rax, [rsp+68h+cbData]
0x180087b2a  mov     [rsp+68h+arg_18], rbx
0x180087b32  mov     [rsp+68h+lpcbData], rax; lpcbData
0x180087b37  lea     r9, [rsp+68h+Type]; lpType
0x180087b3c  xor     r8d, r8d; lpReserved
0x180087b3f  mov     [rsp+68h+phkResult], rsi; lpData
0x180087b44  lea     rdx, aSymbolsearchpa; "SymbolSearchPath"
0x180087b4b  call    cs:__imp_RegQueryValueExW
0x180087b51  mov     rcx, [rsp+68h+hKey]; hKey
0x180087b59  mov     ebx, eax
0x180087b5b  call    cs:__imp_RegCloseKey
0x180087b61  test    ebx, ebx
0x180087b63  jnz     loc_180087C04
0x180087b69  mov     [rsi+rbp*2], r14w
0x180087b6e  mov     eax, [rsp+68h+Type]
0x180087b72  cmp     eax, 1
0x180087b75  jnz     short loc_180087B92
0x180087b77  add     rdi, 10h
0x180087b7b  lea     rax, [rsp+68h+var_38]
0x180087b80  cmp     rdi, rax
0x180087b83  jz      short loc_180087C04
0x180087b85  mov     rcx, [rdi]
0x180087b88  mov     [rdi], rsi
0x180087b8b  test    rcx, rcx
0x180087b8e  jz      short loc_180087C0C
0x180087b90  jmp     short loc_180087C07
0x180087b92  cmp     eax, 2
0x180087b95  jnz     short loc_180087C04
0x180087b97  xor     r8d, r8d; nSize
0x180087b9a  xor     edx, edx; lpDst
0x180087b9c  mov     rcx, rsi; lpSrc
0x180087b9f  call    cs:__imp_ExpandEnvironmentStringsW
0x180087ba5  mov     ebp, eax
0x180087ba7  test    eax, eax
0x180087ba9  jz      short loc_180087C04
0x180087bab  mov     eax, 2
0x180087bb0  mul     rbp
0x180087bb3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180087bba  cmovb   rax, r15
0x180087bbe  mov     rcx, rax; unsigned __int64
0x180087bc1  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180087bc6  mov     rbx, rax
0x180087bc9  test    rax, rax
0x180087bcc  jz      short loc_180087C04
0x180087bce  mov     r8d, ebp; nSize
0x180087bd1  mov     rdx, rax; lpDst
0x180087bd4  mov     rcx, rsi; lpSrc
0x180087bd7  call    cs:__imp_ExpandEnvironmentStringsW
0x180087bdd  test    eax, eax
0x180087bdf  jz      short loc_180087BFC
0x180087be1  add     rdi, 10h
0x180087be5  lea     rax, [rsp+68h+var_30]
0x180087bea  cmp     rdi, rax
0x180087bed  jz      short loc_180087BFC
0x180087bef  mov     rcx, [rdi]
0x180087bf2  mov     [rdi], rbx
0x180087bf5  test    rcx, rcx
0x180087bf8  jz      short loc_180087C04
0x180087bfa  jmp     short loc_180087BFF
0x180087bfc  mov     rcx, rbx; this
0x180087bff  call    ?release@EnumPubsByAddr@PSGSI1@@UEAAXXZ; PSGSI1::EnumPubsByAddr::release(void)
0x180087c04  mov     rcx, rsi; this
0x180087c07  call    ?release@EnumPubsByAddr@PSGSI1@@UEAAXXZ; PSGSI1::EnumPubsByAddr::release(void)
0x180087c0c  mov     rbx, [rsp+68h+arg_18]
0x180087c14  mov     rsi, [rsp+68h+var_18]
0x180087c19  mov     rbp, [rsp+68h+var_10]
0x180087c1e  mov     r15, [rsp+68h+var_28]
0x180087c23  mov     r14, [rsp+68h+var_20]
0x180087c28  lea     rcx, ?m_cs@REGISTRY@LOCATOR@@0VCriticalSectionNoLog@@A; lpCriticalSection
0x180087c2f  call    cs:__imp_LeaveCriticalSection
0x180087c35  add     rsp, 60h
0x180087c39  pop     rdi
0x180087c3a  retn
```
