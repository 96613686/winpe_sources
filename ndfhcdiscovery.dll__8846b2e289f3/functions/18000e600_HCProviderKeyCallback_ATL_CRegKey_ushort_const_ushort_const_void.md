# HCProviderKeyCallback(ATL::CRegKey &,ushort const *,ushort const *,void *)

- ea: `0x18000e600`
- end: `0x18000e7b6`
- name: `?HCProviderKeyCallback@@YAJAEAVCRegKey@ATL@@PEBG1PEAX@Z`
- size: `438`
- prototype: `int(struct ATL::CRegKey *, const unsigned __int16 *, const unsigned __int16 *, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000e600`
- `0x180011690`
- `0x180011920`
- `0x1800136b0`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18000e68d`
- `ADVAPI32!RegQueryValueExW` at `0x18000e707`
- `ADVAPI32!RegQueryValueExW` at `0x18000e68d`
- `ADVAPI32!RegQueryValueExW` at `0x18000e707`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000e643`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000e643`

## pseudocode

```c
__int64 __fastcall HCProviderKeyCallback(HKEY *a1, const unsigned __int16 *a2, const unsigned __int16 *a3, void *a4)
{
  HRESULT v8; // eax
  int v9; // ecx
  unsigned int v10; // ebx
  HKEY v11; // rcx
  const WCHAR *v12; // rsi
  LSTATUS v13; // eax
  int v14; // ecx
  int v15; // r9d
  HKEY v16; // rcx
  LSTATUS v17; // eax
  DWORD Type; // [rsp+30h] [rbp-38h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-34h] BYREF
  CLSID pclsid[2]; // [rsp+38h] [rbp-30h] BYREF

  memset(pclsid, 0, sizeof(pclsid));
  v8 = CLSIDFromString(a2, pclsid);
  v10 = v8;
  if ( v8 >= 0 )
  {
    v11 = *a1;
    v12 = L"Keywords";
    Type = 0;
    cbData = 8;
    v13 = RegQueryValueExW(v11, L"Keywords", 0, &Type, pclsid[1].Data4, &cbData);
    if ( v13 )
    {
      if ( v13 != 2 )
      {
        if ( v13 <= 0 )
        {
          v10 = v13;
          goto LABEL_6;
        }
LABEL_5:
        v10 = (unsigned __int16)v13 | 0x80070000;
LABEL_6:
        if ( (Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits & 1) == 0 )
          goto LABEL_18;
        v15 = 941;
LABEL_17:
        McTemplateU0qqzz_EventWriteTransfer(v14, (unsigned int)RegistryError, v10, v15, (__int64)a3, (__int64)v12);
        goto LABEL_18;
      }
    }
    else if ( Type != 11 )
    {
      LOWORD(v13) = 13;
      goto LABEL_5;
    }
    v16 = *a1;
    v12 = L"Level";
    Type = 0;
    cbData = 4;
    v17 = RegQueryValueExW(v16, L"Level", 0, &Type, (LPBYTE)&pclsid[1], &cbData);
    if ( v17 )
    {
      if ( v17 == 2 )
      {
LABEL_18:
        if ( (v10 & 0x80000000) == 0 )
          std::vector<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003>::push_back(a4, pclsid);
        return v10;
      }
      if ( v17 <= 0 )
      {
        v10 = v17;
        goto LABEL_15;
      }
    }
    else
    {
      if ( Type == 4 )
        goto LABEL_18;
      LOWORD(v17) = 13;
    }
    v10 = (unsigned __int16)v17 | 0x80070000;
LABEL_15:
    if ( (Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits & 1) == 0 )
      goto LABEL_18;
    v15 = 949;
    goto LABEL_17;
  }
  if ( (Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits & 1) != 0 )
    McTemplateU0qqzz_EventWriteTransfer(v9, (unsigned int)RegistryError, v8, 955, (__int64)a3, (__int64)a2);
  return v10;
}

```

## disassembly

```asm
0x18000e600  push    rbp
0x18000e602  push    rbx
0x18000e603  push    rsi
0x18000e604  push    rdi
0x18000e605  push    r14
0x18000e607  push    r15
0x18000e609  mov     rbp, rsp
0x18000e60c  sub     rsp, 68h
0x18000e610  mov     rax, cs:__security_cookie
0x18000e617  xor     rax, rsp
0x18000e61a  mov     [rbp+var_10], rax
0x18000e61e  mov     rsi, rdx
0x18000e621  mov     [rbp+pclsid.Data1], 0
0x18000e628  xorps   xmm0, xmm0
0x18000e62b  lea     rdx, [rbp+pclsid]; pclsid
0x18000e62f  mov     r14, rcx
0x18000e632  mov     r15, r9
0x18000e635  movups  xmmword ptr [rbp+pclsid.Data2], xmm0
0x18000e639  mov     rcx, rsi; lpsz
0x18000e63c  mov     rdi, r8
0x18000e63f  movups  xmmword ptr [rbp+var_20], xmm0
0x18000e643  call    cs:__imp_CLSIDFromString
0x18000e64a  nop     dword ptr [rax+rax+00h]
0x18000e64f  mov     ebx, eax
0x18000e651  test    eax, eax
0x18000e653  js      loc_18000E772
0x18000e659  mov     rcx, [r14]; hKey
0x18000e65c  lea     rax, [rbp+cbData]
0x18000e660  mov     [rsp+68h+lpcbData], rax; lpcbData
0x18000e665  lea     rsi, aKeywords; "Keywords"
0x18000e66c  lea     rax, [rbp+Data]
0x18000e670  mov     [rbp+Type], 0
0x18000e677  lea     r9, [rbp+Type]; lpType
0x18000e67b  mov     [rsp+68h+lpData], rax; lpData
0x18000e680  xor     r8d, r8d; lpReserved
0x18000e683  mov     [rbp+cbData], 8
0x18000e68a  mov     rdx, rsi; lpValueName
0x18000e68d  call    cs:__imp_RegQueryValueExW
0x18000e694  nop     dword ptr [rax+rax+00h]
0x18000e699  test    eax, eax
0x18000e69b  jnz     short loc_18000E6C6
0x18000e69d  cmp     [rbp+Type], 0Bh
0x18000e6a1  jz      short loc_18000E6D3
0x18000e6a3  mov     eax, 0Dh
0x18000e6a8  movzx   ebx, ax
0x18000e6ab  or      ebx, 80070000h
0x18000e6b1  test    cs:Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits, 1
0x18000e6b8  jz      loc_18000E753
0x18000e6be  mov     r9d, 3ADh
0x18000e6c4  jmp     short loc_18000E73A
0x18000e6c6  cmp     eax, 2
0x18000e6c9  jz      short loc_18000E6D3
0x18000e6cb  test    eax, eax
0x18000e6cd  jg      short loc_18000E6A8
0x18000e6cf  mov     ebx, eax
0x18000e6d1  jmp     short loc_18000E6B1
0x18000e6d3  mov     rcx, [r14]; hKey
0x18000e6d6  lea     rax, [rbp+cbData]
0x18000e6da  mov     [rsp+68h+lpcbData], rax; lpcbData
0x18000e6df  lea     rsi, aLevel; "Level"
0x18000e6e6  lea     rax, [rbp+var_20]
0x18000e6ea  mov     [rbp+Type], 0
0x18000e6f1  lea     r9, [rbp+Type]; lpType
0x18000e6f5  mov     [rsp+68h+lpData], rax; lpData
0x18000e6fa  xor     r8d, r8d; lpReserved
0x18000e6fd  mov     [rbp+cbData], 4
0x18000e704  mov     rdx, rsi; lpValueName
0x18000e707  call    cs:__imp_RegQueryValueExW
0x18000e70e  nop     dword ptr [rax+rax+00h]
0x18000e713  test    eax, eax
0x18000e715  jnz     short loc_18000E765
0x18000e717  cmp     [rbp+Type], 4
0x18000e71b  jz      short loc_18000E753
0x18000e71d  mov     eax, 0Dh
0x18000e722  movzx   ebx, ax
0x18000e725  or      ebx, 80070000h
0x18000e72b  test    cs:Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits, 1
0x18000e732  jz      short loc_18000E753
0x18000e734  mov     r9d, 3B5h
0x18000e73a  mov     [rsp+68h+lpcbData], rsi
0x18000e73f  lea     rdx, RegistryError
0x18000e746  mov     r8d, ebx
0x18000e749  mov     [rsp+68h+lpData], rdi
0x18000e74e  call    McTemplateU0qqzz_EventWriteTransfer
0x18000e753  test    ebx, ebx
0x18000e755  js      short loc_18000E79A
0x18000e757  lea     rdx, [rbp+pclsid]
0x18000e75b  mov     rcx, r15
0x18000e75e  call    ?push_back@?$vector@U__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003@@V?$allocator@U__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003@@@std@@@std@@QEAAXAEBU__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003@@@Z; std::vector<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003>::push_back(__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003 const &)
0x18000e763  jmp     short loc_18000E79A
0x18000e765  cmp     eax, 2
0x18000e768  jz      short loc_18000E753
0x18000e76a  test    eax, eax
0x18000e76c  jg      short loc_18000E722
0x18000e76e  mov     ebx, eax
0x18000e770  jmp     short loc_18000E72B
0x18000e772  test    cs:Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits, 1
0x18000e779  jz      short loc_18000E79A
0x18000e77b  mov     [rsp+68h+lpcbData], rsi
0x18000e780  lea     rdx, RegistryError
0x18000e787  mov     r9d, 3BBh
0x18000e78d  mov     [rsp+68h+lpData], rdi
0x18000e792  mov     r8d, eax
0x18000e795  call    McTemplateU0qqzz_EventWriteTransfer
0x18000e79a  mov     eax, ebx
0x18000e79c  mov     rcx, [rbp+var_10]
0x18000e7a0  xor     rcx, rsp; StackCookie
0x18000e7a3  call    __security_check_cookie
0x18000e7a8  add     rsp, 68h
0x18000e7ac  pop     r15
0x18000e7ae  pop     r14
0x18000e7b0  pop     rdi
0x18000e7b1  pop     rsi
0x18000e7b2  pop     rbx
0x18000e7b3  pop     rbp
0x18000e7b4  retn
```
