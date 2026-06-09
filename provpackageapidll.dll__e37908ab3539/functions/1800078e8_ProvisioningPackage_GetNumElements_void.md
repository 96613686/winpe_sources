# ProvisioningPackage::GetNumElements(void)

- ea: `0x1800078e8`
- end: `0x180007c20`
- name: `?GetNumElements@ProvisioningPackage@@AEAAJXZ`
- size: `824`
- prototype: `__int64 __fastcall(ProvisioningPackage *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800088dc`

## callees

- `0x180001510`
- `0x180001e66`
- `0x1800020a8`
- `0x1800020ec`
- `0x180006014`
- `0x1800078e8`
- `0x18000e328`
- `0x18000fc8c`

## import_xrefs

- `WIMGAPI!WIMCloseHandle` at `0x180007a52`
- `WIMGAPI!WIMCloseHandle` at `0x180007a8e`
- `WIMGAPI!WIMCloseHandle` at `0x180007b3f`
- `WIMGAPI!WIMCloseHandle` at `0x180007b55`
- `WIMGAPI!WIMCloseHandle` at `0x180007bb2`
- `WIMGAPI!WIMCloseHandle` at `0x180007c13`
- `WIMGAPI!WIMCloseHandle` at `0x180007a52`
- `WIMGAPI!WIMCloseHandle` at `0x180007a8e`
- `WIMGAPI!WIMCloseHandle` at `0x180007b3f`
- `WIMGAPI!WIMCloseHandle` at `0x180007b55`
- `WIMGAPI!WIMCloseHandle` at `0x180007bb2`
- `WIMGAPI!WIMCloseHandle` at `0x180007c13`

## string_xrefs

- `0x180007b94`: `    Failed to allocate spElementSearchPath.get()`
- `0x180007b18`: `    Failed to assemble element search path`

## pseudocode

```c
__int64 __fastcall ProvisioningPackage::GetNumElements(ProvisioningPackage *this)
{
  int NextFile; // edi
  __int64 v3; // rax
  size_t v4; // rsi
  unsigned __int64 v5; // rax
  unsigned __int64 v6; // kr00_8
  WCHAR *v7; // rax
  WCHAR *v8; // rdi
  HRESULT v9; // eax
  unsigned int v10; // esi
  int v11; // eax
  const struct std::nothrow_t *v12; // rdx
  const struct std::nothrow_t *v14; // rdx
  __int64 v15; // rcx
  bool v16; // cc
  __int64 v17; // [rsp+20h] [rbp-E0h]
  __int64 v18; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v19[3]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v20[44]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszPathIn[314]; // [rsp+7Ch] [rbp-84h] BYREF
  _BYTE v22[672]; // [rsp+2F0h] [rbp+1F0h] BYREF

  memset_0(v20, 0, 0x2A0u);
  v18 = 0;
  *((_DWORD *)this + 22) = 0;
  NextFile = GetNextFile(*((_QWORD *)this + 2), &v18, (__int64)L"*", (__int64)v20);
  if ( NextFile != -2147024637 )
  {
    while ( 1 )
    {
      if ( NextFile == -2147024893 )
        goto LABEL_20;
      if ( NextFile < 0 )
        break;
      if ( (v20[0] & 0x10) != 0 )
      {
        memset_0(v22, 0, sizeof(v22));
        v19[0] = 0;
        while ( 1 )
        {
          v3 = -1;
          do
            ++v3;
          while ( pszPathIn[v3] );
          v4 = v3 + 3;
          v6 = v3 + 3;
          v5 = 2 * (v3 + 3);
          if ( !is_mul_ok(v6, 2u) )
            v5 = -1;
          v7 = (WCHAR *)operator new[](v5, (const struct std::nothrow_t *)&std::nothrow);
          v8 = v7;
          v19[1] = (__int64)v7;
          if ( !v7 )
            break;
          v9 = PathCchCombineEx(v7, v4, pszPathIn, L"*", v17);
          v10 = v9;
          if ( v9 < 0 )
          {
            LODWORD(v17) = 333;
            ProvPackageLog(
              3,
              L"%hs (%hs:%d) - 0x%08x:",
              "ProvisioningPackage::GetNumElements",
              "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
              v17,
              v9);
            ProvPackageLog(3, L"    Failed to assemble element search path");
            goto LABEL_25;
          }
          v11 = GetNextFile(*((_QWORD *)this + 2), v19, (__int64)v8, (__int64)v22);
          v10 = v11;
          if ( v11 == -2147024637 )
          {
            operator delete(v8, v12);
            if ( (unsigned __int64)(v19[0] - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
              WIMCloseHandle(v19[0]);
            goto LABEL_19;
          }
          if ( v11 < 0 )
          {
            LODWORD(v17) = 340;
            ProvPackageLog(
              3,
              L"%hs (%hs:%d) - 0x%08x:",
              "ProvisioningPackage::GetNumElements",
              "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
              v17,
              v11);
            ProvPackageLog(3, L"    Failed to get next element");
LABEL_25:
            operator delete(v8, v14);
            if ( (unsigned __int64)(v19[0] - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
              WIMCloseHandle(v19[0]);
            if ( (unsigned __int64)(v18 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
              WIMCloseHandle(v18);
            return v10;
          }
          if ( (v22[0] & 0x10) != 0 )
            ++*((_DWORD *)this + 22);
          operator delete(v8, v12);
        }
        NextFile = -2147024882;
        LODWORD(v17) = 329;
        ProvPackageLog(
          3,
          L"%hs (%hs:%d) - 0x%08x:",
          "ProvisioningPackage::GetNumElements",
          "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
          v17,
          -2147024882);
        ProvPackageLog(3, L"    Failed to allocate spElementSearchPath.get()");
        if ( (unsigned __int64)(v19[0] - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          WIMCloseHandle(v19[0]);
        v15 = v18;
        v16 = (unsigned __int64)(v18 - 1) <= 0xFFFFFFFFFFFFFFFDuLL;
        goto LABEL_34;
      }
LABEL_19:
      NextFile = GetNextFile(*((_QWORD *)this + 2), &v18, (__int64)L"*", (__int64)v20);
      if ( NextFile == -2147024637 )
        goto LABEL_20;
    }
    LODWORD(v17) = 316;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ProvisioningPackage::GetNumElements",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
      v17,
      NextFile);
    ProvPackageLog(3, L"    Failed to get next type");
    v15 = v18;
    v16 = (unsigned __int64)(v18 - 1) <= 0xFFFFFFFFFFFFFFFDuLL;
LABEL_34:
    if ( v16 )
      WIMCloseHandle(v15);
    return (unsigned int)NextFile;
  }
LABEL_20:
  if ( (unsigned __int64)(v18 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    WIMCloseHandle(v18);
  return 0;
}

```

## disassembly

```asm
0x1800078e8  push    rbp
0x1800078ea  push    rbx
0x1800078eb  push    rsi
0x1800078ec  push    rdi
0x1800078ed  push    r14
0x1800078ef  push    r15
0x1800078f1  lea     rbp, [rsp-4A8h]
0x1800078f9  sub     rsp, 5A8h
0x180007900  mov     rax, cs:__security_cookie
0x180007907  xor     rax, rsp
0x18000790a  mov     [rbp+4D0h+var_40], rax
0x180007911  mov     rbx, rcx
0x180007914  xor     edx, edx; Val
0x180007916  mov     r8d, 2A0h; Size
0x18000791c  lea     rcx, [rsp+5D0h+var_580]; void *
0x180007921  call    memset_0
0x180007926  xor     r14d, r14d
0x180007929  mov     [rsp+5D0h+var_5A0], r14
0x18000792e  mov     [rbx+58h], r14d
0x180007932  lea     r9, [rsp+5D0h+var_580]
0x180007937  lea     r8, pszMore; "*"
0x18000793e  lea     rdx, [rsp+5D0h+var_5A0]
0x180007943  mov     rcx, [rbx+10h]
0x180007947  call    ?GetNextFile@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?WIMCloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEBGPEAU_WIM_FILE_FIND_DATA@@@Z; GetNextFile(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&WIMCloseHandle(void *)>>> &,ushort const *,_WIM_FILE_FIND_DATA *)
0x18000794c  mov     edi, eax
0x18000794e  cmp     eax, 80070103h
0x180007953  jz      loc_180007A7F
0x180007959  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000795d  cmp     edi, 80070003h
0x180007963  jz      loc_180007A7F
0x180007969  test    edi, edi
0x18000796b  js      loc_180007BC8
0x180007971  test    [rsp+5D0h+var_580], 10h
0x180007976  jz      loc_180007A58
0x18000797c  xor     edx, edx; Val
0x18000797e  mov     r8d, 2A0h; Size
0x180007984  lea     rcx, [rbp+4D0h+var_2E0]; void *
0x18000798b  call    memset_0
0x180007990  mov     [rsp+5D0h+var_598], r14
0x180007995  lea     rcx, [rsp+5D0h+pszPathIn]
0x18000799a  mov     rax, r15
0x18000799d  inc     rax
0x1800079a0  cmp     [rcx+rax*2], r14w
0x1800079a5  jnz     short loc_18000799D
0x1800079a7  lea     rsi, [rax+3]
0x1800079ab  mov     eax, 2
0x1800079b0  mul     rsi
0x1800079b3  cmovb   rax, r15
0x1800079b7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800079be  mov     rcx, rax; unsigned __int64
0x1800079c1  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800079c6  mov     rdi, rax
0x1800079c9  mov     [rsp+5D0h+var_590], rax
0x1800079ce  test    rax, rax
0x1800079d1  jz      loc_180007B62
0x1800079d7  lea     r9, pszMore; "*"
0x1800079de  lea     r8, [rsp+5D0h+pszPathIn]; pszPathIn
0x1800079e3  mov     rdx, rsi; cchPathOut
0x1800079e6  mov     rcx, rax; pszPathOut
0x1800079e9  call    PathCchCombineEx
0x1800079ee  mov     esi, eax
0x1800079f0  test    eax, eax
0x1800079f2  js      loc_180007AEB
0x1800079f8  lea     r9, [rbp+4D0h+var_2E0]
0x1800079ff  mov     r8, rdi
0x180007a02  lea     rdx, [rsp+5D0h+var_598]
0x180007a07  mov     rcx, [rbx+10h]
0x180007a0b  call    ?GetNextFile@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?WIMCloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEBGPEAU_WIM_FILE_FIND_DATA@@@Z; GetNextFile(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&WIMCloseHandle(void *)>>> &,ushort const *,_WIM_FILE_FIND_DATA *)
0x180007a10  mov     esi, eax
0x180007a12  cmp     eax, 80070103h
0x180007a17  jz      short loc_180007A3A
0x180007a19  test    eax, eax
0x180007a1b  js      loc_180007AB5
0x180007a21  test    [rbp+4D0h+var_2E0], 10h
0x180007a28  jz      short loc_180007A2D
0x180007a2a  inc     dword ptr [rbx+58h]
0x180007a2d  mov     rcx, rdi; void *
0x180007a30  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007a35  jmp     loc_180007995
0x180007a3a  mov     rcx, rdi; void *
0x180007a3d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007a42  nop
0x180007a43  mov     rcx, [rsp+5D0h+var_598]
0x180007a48  lea     rax, [rcx-1]
0x180007a4c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180007a50  ja      short loc_180007A58
0x180007a52  call    cs:__imp_WIMCloseHandle
0x180007a58  lea     r9, [rsp+5D0h+var_580]
0x180007a5d  lea     r8, pszMore; "*"
0x180007a64  lea     rdx, [rsp+5D0h+var_5A0]
0x180007a69  mov     rcx, [rbx+10h]
0x180007a6d  call    ?GetNextFile@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?WIMCloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEBGPEAU_WIM_FILE_FIND_DATA@@@Z; GetNextFile(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&WIMCloseHandle(void *)>>> &,ushort const *,_WIM_FILE_FIND_DATA *)
0x180007a72  mov     edi, eax
0x180007a74  cmp     eax, 80070103h
0x180007a79  jnz     loc_18000795D
0x180007a7f  mov     rcx, [rsp+5D0h+var_5A0]
0x180007a84  lea     rax, [rcx-1]
0x180007a88  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180007a8c  ja      short loc_180007A94
0x180007a8e  call    cs:__imp_WIMCloseHandle
0x180007a94  xor     eax, eax
0x180007a96  mov     rcx, [rbp+4D0h+var_40]
0x180007a9d  xor     rcx, rsp; StackCookie
0x180007aa0  call    __security_check_cookie
0x180007aa5  add     rsp, 5A8h
0x180007aac  pop     r15
0x180007aae  pop     r14
0x180007ab0  pop     rdi
0x180007ab1  pop     rsi
0x180007ab2  pop     rbx
0x180007ab3  pop     rbp
0x180007ab4  retn
0x180007ab5  mov     [rsp+5D0h+var_5A8], esi
0x180007ab9  mov     dword ptr [rsp+5D0h+var_5B0], 154h
0x180007ac1  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x180007ac8  lea     r8, aProvisioningpa_13; "ProvisioningPackage::GetNumElements"
0x180007acf  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180007ad6  mov     ebx, 3
0x180007adb  mov     ecx, ebx
0x180007add  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180007ae2  lea     rdx, aFailedToGetNex; "    Failed to get next element"
0x180007ae9  jmp     short loc_180007B1F
0x180007aeb  mov     [rsp+5D0h+var_5A8], esi
0x180007aef  mov     dword ptr [rsp+5D0h+var_5B0], 14Dh
0x180007af7  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x180007afe  lea     r8, aProvisioningpa_13; "ProvisioningPackage::GetNumElements"
0x180007b05  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180007b0c  mov     ebx, 3
0x180007b11  mov     ecx, ebx
0x180007b13  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180007b18  lea     rdx, aFailedToAssemb_5; "    Failed to assemble element search p"...
0x180007b1f  mov     ecx, ebx
0x180007b21  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180007b26  nop
0x180007b27  mov     rcx, rdi; void *
0x180007b2a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007b2f  nop
0x180007b30  mov     rcx, [rsp+5D0h+var_598]
0x180007b35  lea     rax, [rcx-1]
0x180007b39  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180007b3d  ja      short loc_180007B46
0x180007b3f  call    cs:__imp_WIMCloseHandle
0x180007b45  nop
0x180007b46  mov     rcx, [rsp+5D0h+var_5A0]
0x180007b4b  lea     rax, [rcx-1]
0x180007b4f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180007b53  ja      short loc_180007B5B
0x180007b55  call    cs:__imp_WIMCloseHandle
0x180007b5b  mov     eax, esi
0x180007b5d  jmp     loc_180007A96
0x180007b62  mov     edi, 8007000Eh
0x180007b67  mov     [rsp+5D0h+var_5A8], edi
0x180007b6b  mov     dword ptr [rsp+5D0h+var_5B0], 149h
0x180007b73  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x180007b7a  lea     r8, aProvisioningpa_13; "ProvisioningPackage::GetNumElements"
0x180007b81  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180007b88  mov     ebx, 3
0x180007b8d  mov     ecx, ebx
0x180007b8f  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180007b94  lea     rdx, aFailedToAlloca_42; "    Failed to allocate spElementSearchP"...
0x180007b9b  mov     ecx, ebx
0x180007b9d  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180007ba2  nop
0x180007ba3  mov     rcx, [rsp+5D0h+var_598]
0x180007ba8  lea     rax, [rcx-1]
0x180007bac  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180007bb0  ja      short loc_180007BB9
0x180007bb2  call    cs:__imp_WIMCloseHandle
0x180007bb8  nop
0x180007bb9  mov     rcx, [rsp+5D0h+var_5A0]
0x180007bbe  lea     rdx, [rcx-1]
0x180007bc2  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180007bc6  jmp     short loc_180007C11
0x180007bc8  mov     [rsp+5D0h+var_5A8], edi
0x180007bcc  mov     dword ptr [rsp+5D0h+var_5B0], 13Ch
0x180007bd4  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x180007bdb  lea     r8, aProvisioningpa_13; "ProvisioningPackage::GetNumElements"
0x180007be2  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180007be9  mov     ebx, 3
0x180007bee  mov     ecx, ebx
0x180007bf0  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180007bf5  lea     rdx, aFailedToGetNex_1; "    Failed to get next type"
0x180007bfc  mov     ecx, ebx
0x180007bfe  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180007c03  nop
0x180007c04  mov     rcx, [rsp+5D0h+var_5A0]
0x180007c09  lea     rax, [rcx-1]
0x180007c0d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180007c11  ja      short loc_180007C19
0x180007c13  call    cs:__imp_WIMCloseHandle
0x180007c19  mov     eax, edi
0x180007c1b  jmp     loc_180007A96
```
