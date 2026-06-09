# DhcpRegReadOptionDef

- ea: `0x18003b520`
- end: `0x18003b982`
- name: `DhcpRegReadOptionDef`
- size: `1122`
- prototype: `__int64 __fastcall(wchar_t *Str)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180011454`

## callees

- `0x1800057f0`
- `0x180005da4`
- `0x180006440`
- `0x180011efc`
- `0x1800153dc`
- `0x18003b520`
- `0x180040eb4`
- `0x180041224`
- `0x180047e3c`
- `0x18004d200`
- `0x18004d310`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18003b604`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18003b604`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18003b5f1`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18003b5f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b7c6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b7c6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003b598`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003b598`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003b679`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003b6b5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003b679`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003b6b5`

## string_xrefs

- `0x18003b66b`: `ClassId`
- `0x18003b6a6`: `ClassId`

## pseudocode

```c
__int64 __fastcall DhcpRegReadOptionDef(wchar_t *Str)
{
  __int64 v1; // r14
  unsigned int v3; // ebx
  int v4; // edx
  int v5; // ecx
  wchar_t *v6; // rax
  DWORD v7; // r12d
  LPBYTE v8; // r15
  __int64 v10; // rcx
  __int64 v11; // rcx
  int v12; // [rsp+40h] [rbp-30h] BYREF
  DWORD Type; // [rsp+44h] [rbp-2Ch] BYREF
  int v14; // [rsp+48h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-20h] BYREF
  void *v16; // [rsp+58h] [rbp-18h]
  void *Src; // [rsp+60h] [rbp-10h]
  LPBYTE v18; // [rsp+68h] [rbp-8h] BYREF
  DWORD cbData; // [rsp+C0h] [rbp+50h] BYREF
  int v20; // [rsp+C8h] [rbp+58h] BYREF

  v1 = 0;
  hKey = 0;
  Type = 0;
  cbData = 0;
  v12 = 0;
  v20 = 0;
  v14 = 0;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_S(1028, 10, WPP_5b94a9fc2174303e55b47f5e3f4ecc4f_Traceguids, Str);
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, Str, 0, 0xFu, &hKey);
  if ( v3 )
  {
    if ( (xmmword_1800616A0 & 0x10) != 0 )
    {
      v4 = 11;
      v5 = 1028;
LABEL_24:
      WPP_SF_SD(v5, v4, (unsigned int)WPP_5b94a9fc2174303e55b47f5e3f4ecc4f_Traceguids, (_DWORD)Str, v3);
      return v3;
    }
    return v3;
  }
  v18 = 0;
  v16 = 0;
  Src = 0;
  v3 = DhcpRegReadDWORDWithKey(hKey, L"OptionId", &v12);
  if ( !v3 || (v6 = wcsrchr(Str, 0x5Cu)) != 0 && (v12 = _o__wtol(v6 + 1), (unsigned int)(v12 - 1) <= 0xFFFFFFFD) )
  {
    if ( (unsigned int)DhcpRegReadDWORDWithKey(hKey, L"VendorType", &v20) )
      v20 = 0;
    v3 = DhcpRegReadDWORDWithKey(hKey, L"KeyType", &v14);
    if ( !v3 )
    {
      cbData = 0;
      v7 = 0;
      if ( !RegQueryValueExW(hKey, L"ClassId", 0, &Type, 0, &cbData) && cbData )
      {
        v18 = (LPBYTE)DhcpAlloc(cbData);
        v3 = RegQueryValueExW(hKey, L"ClassId", 0, &Type, v18, &cbData);
        if ( v3 )
        {
          v8 = v18;
LABEL_18:
          if ( v8 )
            DhcpPunycodeFree(&v18);
          goto LABEL_20;
        }
        v7 = cbData;
      }
      GetRegistryString(hKey, L"RegLocation");
      Src = 0;
      GetRegistryString(hKey, L"RegSendLocation");
      v16 = 0;
      v8 = v18;
      if ( !v7 || (v1 = DhcpAddClass(v10, v18, v7)) != 0 )
      {
        v3 = DhcpAddOptionDef(v10, v12, v20 != 0, v1, v7, 0, 0, v14);
        if ( v3 && v7 )
          DhcpDelClass(v11, v1, v7);
      }
      else
      {
        v3 = 8;
      }
      goto LABEL_18;
    }
  }
LABEL_20:
  if ( hKey )
    RegCloseKey(hKey);
  if ( (xmmword_1800616A0 & 2) != 0 )
  {
    v4 = 14;
    v5 = 1025;
    goto LABEL_24;
  }
  return v3;
}

```

## disassembly

```asm
0x18003b520  mov     [rsp-38h+arg_0], rbx
0x18003b525  push    rbp
0x18003b526  push    rsi
0x18003b527  push    rdi
0x18003b528  push    r12
0x18003b52a  push    r13
0x18003b52c  push    r14
0x18003b52e  push    r15
0x18003b530  mov     rbp, rsp
0x18003b533  sub     rsp, 70h
0x18003b537  xor     r14d, r14d
0x18003b53a  mov     r13, rcx
0x18003b53d  mov     [rbp+hKey], r14
0x18003b541  mov     [rbp+Type], r14d
0x18003b545  mov     [rbp+cbData], r14d
0x18003b549  mov     [rbp+var_30], r14d
0x18003b54d  mov     [rbp+arg_18], r14d
0x18003b551  mov     dword ptr [rbp+Size], r14d
0x18003b555  mov     [rbp+var_28], r14d
0x18003b559  test    byte ptr cs:xmmword_1800616A0, 10h
0x18003b560  mov     edi, 404h
0x18003b565  jz      short loc_18003B57C
0x18003b567  lea     edx, [r14+0Ah]
0x18003b56b  mov     ecx, edi
0x18003b56d  mov     r9, r13
0x18003b570  lea     r8, WPP_5b94a9fc2174303e55b47f5e3f4ecc4f_Traceguids
0x18003b577  call    WPP_SF_S
0x18003b57c  lea     rax, [rbp+hKey]
0x18003b580  mov     r9d, 0Fh; samDesired
0x18003b586  xor     r8d, r8d; ulOptions
0x18003b589  mov     [rsp+70h+phkResult], rax; phkResult
0x18003b58e  mov     rdx, r13; lpSubKey
0x18003b591  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003b598  call    cs:__imp_RegOpenKeyExW
0x18003b59e  mov     ebx, eax
0x18003b5a0  test    eax, eax
0x18003b5a2  jz      short loc_18003B5BD
0x18003b5a4  test    byte ptr cs:xmmword_1800616A0, 10h
0x18003b5ab  jz      loc_18003B7F2
0x18003b5b1  mov     edx, 0Bh
0x18003b5b6  mov     ecx, edi
0x18003b5b8  jmp     loc_18003B7DF
0x18003b5bd  mov     rcx, [rbp+hKey]
0x18003b5c1  lea     r8, [rbp+var_30]
0x18003b5c5  lea     rdx, aOptionid; "OptionId"
0x18003b5cc  mov     [rbp+var_8], r14
0x18003b5d0  mov     rdi, r14
0x18003b5d3  mov     [rbp+var_18], r14
0x18003b5d7  mov     rsi, r14
0x18003b5da  mov     [rbp+Src], r14
0x18003b5de  call    DhcpRegReadDWORDWithKey
0x18003b5e3  mov     ebx, eax
0x18003b5e5  test    eax, eax
0x18003b5e7  jz      short loc_18003B618
0x18003b5e9  mov     edx, 5Ch ; '\'; Ch
0x18003b5ee  mov     rcx, r13; Str
0x18003b5f1  call    cs:__imp_wcsrchr
0x18003b5f7  test    rax, rax
0x18003b5fa  jz      loc_18003B7BD
0x18003b600  lea     rcx, [rax+2]
0x18003b604  call    cs:__imp__o__wtol
0x18003b60a  mov     [rbp+var_30], eax
0x18003b60d  dec     eax
0x18003b60f  cmp     eax, 0FFFFFFFDh
0x18003b612  ja      loc_18003B7BD
0x18003b618  mov     rcx, [rbp+hKey]
0x18003b61c  lea     r8, [rbp+arg_18]
0x18003b620  lea     rdx, aVendortype; "VendorType"
0x18003b627  call    DhcpRegReadDWORDWithKey
0x18003b62c  test    eax, eax
0x18003b62e  jz      short loc_18003B634
0x18003b630  mov     [rbp+arg_18], r14d
0x18003b634  mov     rcx, [rbp+hKey]
0x18003b638  lea     r8, [rbp+var_28]
0x18003b63c  lea     rdx, aKeytype; "KeyType"
0x18003b643  call    DhcpRegReadDWORDWithKey
0x18003b648  mov     ebx, eax
0x18003b64a  test    eax, eax
0x18003b64c  jnz     loc_18003B7BD
0x18003b652  mov     rcx, [rbp+hKey]; hKey
0x18003b656  lea     rax, [rbp+cbData]
0x18003b65a  mov     [rsp+70h+lpcbData], rax; lpcbData
0x18003b65f  lea     r9, [rbp+Type]; lpType
0x18003b663  xor     r8d, r8d; lpReserved
0x18003b666  mov     [rsp+70h+phkResult], r14; lpData
0x18003b66b  lea     rdx, aClassid; "ClassId"
0x18003b672  mov     [rbp+cbData], r14d
0x18003b676  mov     r12d, r14d
0x18003b679  call    cs:__imp_RegQueryValueExW
0x18003b67f  test    eax, eax
0x18003b681  jnz     short loc_18003B6C9
0x18003b683  mov     eax, [rbp+cbData]
0x18003b686  test    eax, eax
0x18003b688  jz      short loc_18003B6C9
0x18003b68a  mov     ecx, eax
0x18003b68c  call    DhcpAlloc
0x18003b691  lea     rcx, [rbp+cbData]
0x18003b695  mov     [rbp+var_8], rax
0x18003b699  mov     [rsp+70h+lpcbData], rcx; lpcbData
0x18003b69e  lea     r9, [rbp+Type]; lpType
0x18003b6a2  mov     rcx, [rbp+hKey]; hKey
0x18003b6a6  lea     rdx, aClassid; "ClassId"
0x18003b6ad  xor     r8d, r8d; lpReserved
0x18003b6b0  mov     [rsp+70h+phkResult], rax; lpData
0x18003b6b5  call    cs:__imp_RegQueryValueExW
0x18003b6bb  mov     ebx, eax
0x18003b6bd  test    eax, eax
0x18003b6bf  jnz     loc_18003B78F
0x18003b6c5  mov     r12d, [rbp+cbData]
0x18003b6c9  mov     rcx, [rbp+hKey]; hKey
0x18003b6cd  lea     r9, [rbp+Size]
0x18003b6d1  lea     r8, [rbp+Src]
0x18003b6d5  lea     rdx, aReglocation; "RegLocation"
0x18003b6dc  call    GetRegistryString
0x18003b6e1  or      r15, 0FFFFFFFFFFFFFFFFh
0x18003b6e5  test    eax, eax
0x18003b6e7  jnz     short loc_18003B71F
0x18003b6e9  mov     eax, dword ptr [rbp+Size]
0x18003b6ec  test    eax, eax
0x18003b6ee  jz      short loc_18003B71F
0x18003b6f0  mov     rsi, [rbp+Src]
0x18003b6f4  mov     rcx, r15
0x18003b6f7  inc     rcx
0x18003b6fa  cmp     [rsi+rcx*2], r14w
0x18003b6ff  jnz     short loc_18003B6F7
0x18003b701  test    rcx, rcx
0x18003b704  jnz     short loc_18003B729
0x18003b706  lea     rcx, [rbp+Src]
0x18003b70a  call    DhcpPunycodeFree
0x18003b70f  mov     rsi, r14
0x18003b712  mov     [rbp+Src], r14
0x18003b716  mov     dword ptr [rbp+Size], r14d
0x18003b71a  jmp     loc_18003B834
0x18003b71f  mov     eax, r14d
0x18003b722  mov     [rbp+Src], r14
0x18003b726  mov     dword ptr [rbp+Size], eax
0x18003b729  test    eax, eax
0x18003b72b  jz      loc_18003B834
0x18003b731  mov     r14d, eax
0x18003b734  xor     ecx, ecx
0x18003b736  mov     rax, r15
0x18003b739  inc     rax
0x18003b73c  cmp     [rsi+rax*2], cx
0x18003b740  jnz     short loc_18003B739
0x18003b742  lea     rax, ds:2[rax*2]
0x18003b74a  cmp     rax, r14
0x18003b74d  jnz     loc_18003B831
0x18003b753  lea     rcx, [r14+2]
0x18003b757  call    DhcpAlloc
0x18003b75c  mov     rbx, rax
0x18003b75f  test    byte ptr cs:xmmword_1800616A0, 10h
0x18003b766  jz      short loc_18003B781
0x18003b768  mov     edx, 0Ch
0x18003b76d  lea     r8, WPP_5b94a9fc2174303e55b47f5e3f4ecc4f_Traceguids
0x18003b774  mov     ecx, 404h
0x18003b779  mov     r9, rsi
0x18003b77c  call    WPP_SF_S
0x18003b781  test    rbx, rbx
0x18003b784  jnz     loc_18003B80C
0x18003b78a  mov     ebx, 8
0x18003b78f  mov     r15, [rbp+var_8]
0x18003b793  test    r15, r15
0x18003b796  jz      short loc_18003B7A1
0x18003b798  lea     rcx, [rbp+var_8]
0x18003b79c  call    DhcpPunycodeFree
0x18003b7a1  test    rdi, rdi
0x18003b7a4  jz      short loc_18003B7AF
0x18003b7a6  lea     rcx, [rbp+var_18]
0x18003b7aa  call    DhcpPunycodeFree
0x18003b7af  test    rsi, rsi
0x18003b7b2  jz      short loc_18003B7BD
0x18003b7b4  lea     rcx, [rbp+Src]
0x18003b7b8  call    DhcpPunycodeFree
0x18003b7bd  mov     rcx, [rbp+hKey]; hKey
0x18003b7c1  test    rcx, rcx
0x18003b7c4  jz      short loc_18003B7CC
0x18003b7c6  call    cs:__imp_RegCloseKey
0x18003b7cc  test    byte ptr cs:xmmword_1800616A0, 2
0x18003b7d3  jz      short loc_18003B7F2
0x18003b7d5  mov     edx, 0Eh
0x18003b7da  mov     ecx, 401h
0x18003b7df  mov     r9, r13
0x18003b7e2  mov     dword ptr [rsp+70h+phkResult], ebx
0x18003b7e6  lea     r8, WPP_5b94a9fc2174303e55b47f5e3f4ecc4f_Traceguids
0x18003b7ed  call    WPP_SF_SD
0x18003b7f2  mov     eax, ebx
0x18003b7f4  mov     rbx, [rsp+70h+arg_0]
0x18003b7fc  add     rsp, 70h
0x18003b800  pop     r15
0x18003b802  pop     r14
0x18003b804  pop     r13
0x18003b806  pop     r12
0x18003b808  pop     rdi
0x18003b809  pop     rsi
0x18003b80a  pop     rbp
0x18003b80b  retn
0x18003b80c  mov     r8, r14; Size
0x18003b80f  mov     rdx, rsi; Src
0x18003b812  mov     rcx, rbx; void *
0x18003b815  call    memcpy_0
0x18003b81a  xor     ecx, ecx
0x18003b81c  mov     [r14+rbx], cx
0x18003b821  lea     rcx, [rbp+Src]
0x18003b825  call    DhcpPunycodeFree
0x18003b82a  mov     rsi, rbx
0x18003b82d  mov     [rbp+Src], rbx
0x18003b831  xor     r14d, r14d
0x18003b834  mov     rcx, [rbp+hKey]; hKey
0x18003b838  lea     r9, [rbp+Size]
0x18003b83c  lea     r8, [rbp+var_18]
0x18003b840  lea     rdx, aRegsendlocatio; "RegSendLocation"
0x18003b847  call    GetRegistryString
0x18003b84c  test    eax, eax
0x18003b84e  jnz     short loc_18003B882
0x18003b850  mov     eax, dword ptr [rbp+Size]
0x18003b853  test    eax, eax
0x18003b855  jz      short loc_18003B882
0x18003b857  mov     rdi, [rbp+var_18]
0x18003b85b  mov     rcx, r15
0x18003b85e  inc     rcx
0x18003b861  cmp     [rdi+rcx*2], r14w
0x18003b866  jnz     short loc_18003B85E
0x18003b868  test    rcx, rcx
0x18003b86b  jnz     short loc_18003B88C
0x18003b86d  lea     rcx, [rbp+var_18]
0x18003b871  call    DhcpPunycodeFree
0x18003b876  mov     rdi, r14
0x18003b879  mov     [rbp+var_18], r14
0x18003b87d  jmp     loc_18003B90C
0x18003b882  mov     rdi, r14
0x18003b885  mov     [rbp+var_18], r14
0x18003b889  mov     eax, r14d
0x18003b88c  test    eax, eax
0x18003b88e  jz      short loc_18003B90C
0x18003b890  mov     r14d, eax
0x18003b893  xor     eax, eax
0x18003b895  inc     r15
0x18003b898  cmp     [rdi+r15*2], ax
0x18003b89d  jnz     short loc_18003B895
0x18003b89f  lea     rax, ds:2[r15*2]
0x18003b8a7  cmp     rax, r14
0x18003b8aa  jnz     short loc_18003B909
0x18003b8ac  lea     rcx, [r14+2]
0x18003b8b0  call    DhcpAlloc
0x18003b8b5  mov     rbx, rax
0x18003b8b8  test    byte ptr cs:xmmword_1800616A0, 10h
0x18003b8bf  jz      short loc_18003B8DA
0x18003b8c1  mov     edx, 0Dh
0x18003b8c6  lea     r8, WPP_5b94a9fc2174303e55b47f5e3f4ecc4f_Traceguids
0x18003b8cd  mov     ecx, 404h
0x18003b8d2  mov     r9, rdi
0x18003b8d5  call    WPP_SF_S
0x18003b8da  xor     r15d, r15d
0x18003b8dd  test    rbx, rbx
0x18003b8e0  jz      loc_18003B78A
0x18003b8e6  mov     r8, r14; Size
0x18003b8e9  mov     rdx, rdi; Src
0x18003b8ec  mov     rcx, rbx; void *
0x18003b8ef  call    memcpy_0
0x18003b8f4  lea     rcx, [rbp+var_18]
0x18003b8f8  mov     [r14+rbx], r15w
0x18003b8fd  call    DhcpPunycodeFree
0x18003b902  mov     rdi, rbx
0x18003b905  mov     [rbp+var_18], rbx
0x18003b909  xor     r14d, r14d
0x18003b90c  mov     r15, [rbp+var_8]
0x18003b910  test    r12d, r12d
0x18003b913  jz      short loc_18003B932
0x18003b915  mov     r8d, r12d
0x18003b918  mov     rdx, r15
0x18003b91b  call    DhcpAddClass
0x18003b920  mov     r14, rax
0x18003b923  xor     eax, eax
0x18003b925  test    r14, r14
0x18003b928  jnz     short loc_18003B934
0x18003b92a  lea     ebx, [rax+8]
0x18003b92d  jmp     loc_18003B793
0x18003b932  xor     eax, eax
0x18003b934  cmp     [rbp+arg_18], eax
0x18003b937  mov     r8d, eax
0x18003b93a  mov     eax, [rbp+var_28]
0x18003b93d  mov     r9, r14; int
0x18003b940  mov     edx, [rbp+var_30]; int
0x18003b943  setnz   r8b; int
0x18003b947  mov     [rsp+70h+var_38], eax; int
0x18003b94b  mov     [rsp+70h+psz], rsi; psz
0x18003b950  mov     [rsp+70h+lpcbData], rdi; Src
0x18003b955  mov     dword ptr [rsp+70h+phkResult], r12d; int
0x18003b95a  call    DhcpAddOptionDef
0x18003b95f  mov     ebx, eax
0x18003b961  test    eax, eax
0x18003b963  jz      loc_18003B793
0x18003b969  test    r12d, r12d
0x18003b96c  jz      loc_18003B793
0x18003b972  mov     r8d, r12d
0x18003b975  mov     rdx, r14
0x18003b978  call    DhcpDelClass
0x18003b97d  jmp     loc_18003B793
```
