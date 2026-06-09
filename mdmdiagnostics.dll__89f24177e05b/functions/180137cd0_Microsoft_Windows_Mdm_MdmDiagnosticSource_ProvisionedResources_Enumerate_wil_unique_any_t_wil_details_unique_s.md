# Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::Enumerate(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,ushort const *,ushort const *,std::list<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x180137cd0`
- end: `0x180138067`
- name: `?Enumerate@ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG1AEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `919`
- prototype: `__int64 __fastcall(__int64, HKEY *, const WCHAR *, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180137508`
- `0x18013826c`

## callees

- `0x180019000`
- `0x180019508`
- `0x18001981c`
- `0x1800e66dc`
- `0x1800e7124`
- `0x1800e7c08`
- `0x1800e82e4`
- `0x1800ece5c`
- `0x1800ef188`
- `0x1800ef5d8`
- `0x1800ef900`
- `0x180104108`
- `0x180132f54`
- `0x180136b50`
- `0x180136ca0`
- `0x1801372dc`
- `0x180137cd0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180137dec`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180137dec`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180137f06`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180137f06`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180137d55`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180137d55`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180137d28`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180137d28`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::Enumerate(
        __int64 a1,
        HKEY *a2,
        const WCHAR *a3,
        __int64 a4,
        _QWORD *a5)
{
  LSTATUS v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdx
  unsigned int v11; // eax
  unsigned __int64 v12; // rax
  void *v13; // rcx
  DWORD i; // edi
  unsigned int v15; // eax
  _BYTE *v16; // rcx
  __int64 v17; // rbx
  int v18; // eax
  __int64 v19; // rax
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  DWORD cbMaxValueNameLen; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cbMaxValueLen; // [rsp+64h] [rbp-9Ch] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  DWORD cValues; // [rsp+70h] [rbp-90h] BYREF
  DWORD Type; // [rsp+74h] [rbp-8Ch] BYREF
  void *v28; // [rsp+78h] [rbp-88h] BYREF
  void *Block; // [rsp+80h] [rbp-80h] BYREF
  DWORD cbData; // [rsp+88h] [rbp-78h] BYREF
  DWORD cchValueName; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v32[2]; // [rsp+98h] [rbp-68h] BYREF
  char v33; // [rsp+A8h] [rbp-58h]
  void **v34; // [rsp+B0h] [rbp-50h]
  char v35; // [rsp+B8h] [rbp-48h]
  _BYTE v36[16]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v37; // [rsp+D0h] [rbp-30h]
  _BYTE v38[16]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v39; // [rsp+F0h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  std::list<std::wstring>::clear(a5);
  hKey = 0;
  v8 = RegOpenKeyExW(*a2, a3, 0, 0x20019u, &hKey);
  v9 = v8;
  if ( v8 == 2 )
  {
LABEL_29:
    v9 = 0;
    goto LABEL_30;
  }
  if ( v8 > 0 )
    v9 = (unsigned __int16)v8 | 0x80070000;
  if ( (v9 & 0x80000000) != 0 )
  {
    v10 = 86;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\erm.cpp",
      (const char *)v9,
      phkResult);
    goto LABEL_30;
  }
  Type = 0;
  cValues = 0;
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  v11 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
  if ( v11 )
  {
    v9 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x69,
           (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\erm.cpp",
           (const char *)v11,
           phkResult);
    goto LABEL_30;
  }
  v12 = 2LL * ++cbMaxValueNameLen;
  if ( !is_mul_ok(cbMaxValueNameLen, 2u) )
    v12 = -1;
  Block = operator new[](v12, (const struct std::nothrow_t *)std::nothrow);
  if ( !Block )
  {
    v9 = -2147024882;
    v10 = 108;
    goto LABEL_6;
  }
  v32[1] = &Block;
  v33 = 1;
  v13 = operator new[](++cbMaxValueLen, (const struct std::nothrow_t *)std::nothrow);
  v28 = v13;
  if ( v13 )
  {
    v34 = &v28;
    v35 = 1;
    for ( i = 0; i < cValues; ++i )
    {
      cchValueName = cbMaxValueNameLen;
      cbData = cbMaxValueLen;
      v15 = RegEnumValueW(hKey, i, (LPWSTR)Block, &cchValueName, 0, &Type, (LPBYTE)v13, &cbData);
      if ( v15 )
      {
        v9 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x87,
               (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\erm.cpp",
               (const char *)v15,
               phkResulta);
        operator delete(v28);
        goto LABEL_15;
      }
      if ( Type == 1 )
      {
        if ( a4 )
        {
          std::wstring::wstring(v38, v28);
          std::wstring::wstring(v36, L"/");
          std::wstring::append(v36, a4);
          std::wstring::append(v36, L"/");
          v17 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v36);
          v18 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v38);
          std::search_std::_String_iterator_std::_String_val_std::_Simple_types_unsigned_short______std::_String_iterator_std::_String_val_std::_Simple_types_unsigned_short_______lambda_996e1d35f9f711f32d4492c64932d28e___(
            (unsigned int)v32,
            v18,
            v18 + 2 * v39,
            v17,
            v17 + 2 * v37);
          v19 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v38);
          if ( v32[0] != v19 + 2 * v39 )
            std::list<std::wstring>::_Emplace<std::wstring const &>(a5, *a5, v38);
          std::wstring::_Tidy_deallocate(v36);
          v16 = v38;
        }
        else
        {
          std::wstring::wstring(v36, v28);
          std::list<std::wstring>::_Emplace<std::wstring>(a5, *a5, v36);
          v16 = v36;
        }
        std::wstring::_Tidy_deallocate(v16);
      }
      v13 = v28;
    }
    operator delete(v13);
    operator delete(Block);
    goto LABEL_29;
  }
  v9 = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x73,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\erm.cpp",
    (const char *)0x8007000ELL,
    phkResult);
LABEL_15:
  operator delete(Block);
LABEL_30:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v9;
}

```

## disassembly

```asm
0x180137cd0  push    rbp
0x180137cd2  push    rbx
0x180137cd3  push    rsi
0x180137cd4  push    rdi
0x180137cd5  push    r12
0x180137cd7  push    r14
0x180137cd9  push    r15
0x180137cdb  lea     rbp, [rsp-10h]
0x180137ce0  sub     rsp, 110h
0x180137ce7  mov     rax, cs:__security_cookie
0x180137cee  xor     rax, rsp
0x180137cf1  mov     [rbp+40h+var_40], rax
0x180137cf5  mov     r15, r9
0x180137cf8  mov     r14, r8
0x180137cfb  mov     rdi, rdx
0x180137cfe  mov     rsi, [rbp+40h+arg_20]
0x180137d02  xor     r12d, r12d
0x180137d05  mov     [rsp+140h+hKey], r12
0x180137d0a  mov     rcx, rsi
0x180137d0d  call    ?clear@?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXXZ; std::list<std::wstring>::clear(void)
0x180137d12  mov     rbx, [rsp+140h+hKey]
0x180137d17  test    rbx, rbx
0x180137d1a  jz      short loc_180137D37
0x180137d1c  lea     rcx, [rbp+40h+cchValueName]; this
0x180137d20  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180137d25  mov     rcx, rbx; hKey
0x180137d28  call    cs:__imp_RegCloseKey
0x180137d2e  lea     rcx, [rbp+40h+cchValueName]; this
0x180137d32  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180137d37  mov     [rsp+140h+hKey], r12
0x180137d3c  lea     rax, [rsp+140h+hKey]
0x180137d41  mov     [rsp+140h+phkResult], rax; int
0x180137d46  mov     r9d, 20019h; samDesired
0x180137d4c  xor     r8d, r8d; ulOptions
0x180137d4f  mov     rdx, r14; lpSubKey
0x180137d52  mov     rcx, [rdi]; hKey
0x180137d55  call    cs:__imp_RegOpenKeyExW
0x180137d5b  mov     ebx, eax
0x180137d5d  cmp     eax, 2
0x180137d60  jz      loc_18013803A
0x180137d66  test    eax, eax
0x180137d68  jle     short loc_180137D73
0x180137d6a  movzx   ebx, ax
0x180137d6d  or      ebx, 80070000h
0x180137d73  test    ebx, ebx
0x180137d75  jns     short loc_180137D94
0x180137d77  mov     edx, 56h ; 'V'; void *
0x180137d7c  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180137d83  mov     r9d, ebx; char *
0x180137d86  mov     rcx, [rbp+48h]; this
0x180137d8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180137d8f  jmp     loc_18013803D
0x180137d94  mov     [rsp+140h+Type], r12d
0x180137d99  mov     [rsp+140h+cValues], r12d
0x180137d9e  mov     [rsp+140h+cbMaxValueNameLen], r12d
0x180137da3  mov     [rsp+140h+cbMaxValueLen], r12d
0x180137da8  mov     [rsp+140h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180137dad  mov     [rsp+140h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x180137db2  lea     rax, [rsp+140h+cbMaxValueLen]
0x180137db7  mov     [rsp+140h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180137dbc  lea     rax, [rsp+140h+cbMaxValueNameLen]
0x180137dc1  mov     [rsp+140h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180137dc6  lea     rax, [rsp+140h+cValues]
0x180137dcb  mov     [rsp+140h+lpcValues], rax; lpcValues
0x180137dd0  mov     [rsp+140h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x180137dd5  mov     [rsp+140h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x180137dda  mov     [rsp+140h+phkResult], r12; int
0x180137ddf  xor     r9d, r9d; lpReserved
0x180137de2  xor     r8d, r8d; lpcchClass
0x180137de5  xor     edx, edx; lpClass
0x180137de7  mov     rcx, [rsp+140h+hKey]; hKey
0x180137dec  call    cs:__imp_RegQueryInfoKeyW
0x180137df2  test    eax, eax
0x180137df4  jz      short loc_180137E15
0x180137df6  mov     rcx, [rbp+48h]; this
0x180137dfa  mov     r9d, eax; char *
0x180137dfd  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180137e04  mov     edx, 69h ; 'i'; void *
0x180137e09  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180137e0e  mov     ebx, eax
0x180137e10  jmp     loc_18013803D
0x180137e15  mov     ecx, [rsp+140h+cbMaxValueNameLen]
0x180137e19  inc     ecx
0x180137e1b  mov     [rsp+140h+cbMaxValueNameLen], ecx
0x180137e1f  mov     eax, 2
0x180137e24  mul     rcx
0x180137e27  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180137e2e  cmovb   rax, rcx
0x180137e32  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180137e39  mov     rcx, rax; unsigned __int64
0x180137e3c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180137e41  mov     [rbp+40h+Block], rax
0x180137e45  test    rax, rax
0x180137e48  jnz     short loc_180137E57
0x180137e4a  mov     ebx, 8007000Eh
0x180137e4f  lea     edx, [rax+6Ch]
0x180137e52  jmp     loc_180137D7C
0x180137e57  lea     rax, [rbp+40h+Block]
0x180137e5b  mov     [rbp+40h+var_A0], rax
0x180137e5f  mov     [rbp+40h+var_98], 1
0x180137e63  mov     eax, [rsp+140h+cbMaxValueLen]
0x180137e67  inc     eax
0x180137e69  mov     [rsp+140h+cbMaxValueLen], eax
0x180137e6d  mov     ecx, eax; unsigned __int64
0x180137e6f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180137e76  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180137e7b  mov     rcx, rax; Block
0x180137e7e  mov     [rsp+140h+var_C8], rax
0x180137e83  test    rax, rax
0x180137e86  jnz     short loc_180137EB2
0x180137e88  mov     rcx, [rbp+48h]; this
0x180137e8c  mov     ebx, 8007000Eh
0x180137e91  mov     r9d, ebx; char *
0x180137e94  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180137e9b  lea     edx, [rax+73h]; void *
0x180137e9e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180137ea3  nop
0x180137ea4  mov     rcx, [rbp+40h+Block]; Block
0x180137ea8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180137ead  jmp     loc_18013803D
0x180137eb2  lea     rax, [rsp+140h+var_C8]
0x180137eb7  mov     [rbp+40h+var_90], rax
0x180137ebb  mov     [rbp+40h+var_88], 1
0x180137ebf  mov     edi, r12d
0x180137ec2  cmp     edi, [rsp+140h+cValues]
0x180137ec6  jnb     loc_18013802B
0x180137ecc  mov     eax, [rsp+140h+cbMaxValueNameLen]
0x180137ed0  mov     [rbp+40h+cchValueName], eax
0x180137ed3  mov     eax, [rsp+140h+cbMaxValueLen]
0x180137ed7  mov     [rbp+40h+cbData], eax
0x180137eda  lea     rax, [rbp+40h+cbData]
0x180137ede  mov     [rsp+140h+lpcValues], rax; lpcbData
0x180137ee3  mov     [rsp+140h+lpcbMaxClassLen], rcx; lpData
0x180137ee8  lea     rax, [rsp+140h+Type]
0x180137eed  mov     [rsp+140h+lpcbMaxSubKeyLen], rax; lpType
0x180137ef2  mov     [rsp+140h+phkResult], r12; unsigned int
0x180137ef7  lea     r9, [rbp+40h+cchValueName]; lpcchValueName
0x180137efb  mov     r8, [rbp+40h+Block]; lpValueName
0x180137eff  mov     edx, edi; dwIndex
0x180137f01  mov     rcx, [rsp+140h+hKey]; hKey
0x180137f06  call    cs:__imp_RegEnumValueW
0x180137f0c  test    eax, eax
0x180137f0e  jnz     loc_180138002
0x180137f14  cmp     [rsp+140h+Type], 1
0x180137f19  jnz     loc_180137FF6
0x180137f1f  mov     rdx, [rsp+140h+var_C8]
0x180137f24  test    r15, r15
0x180137f27  jnz     short loc_180137F4C
0x180137f29  lea     rcx, [rbp+40h+var_80]
0x180137f2d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180137f32  nop
0x180137f33  lea     r8, [rbp+40h+var_80]
0x180137f37  mov     rdx, [rsi]
0x180137f3a  mov     rcx, rsi
0x180137f3d  call    ??$_Emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAPEAU?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@1@QEAU21@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::list<std::wstring>::_Emplace<std::wstring>(std::_List_node<std::wstring,void *> * const,std::wstring &&)
0x180137f42  nop
0x180137f43  lea     rcx, [rbp+40h+var_80]
0x180137f47  jmp     loc_180137FF1
0x180137f4c  lea     rcx, [rbp+40h+var_60]
0x180137f50  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180137f55  nop
0x180137f56  lea     rdx, asc_1801D0CA8; "/"
0x180137f5d  lea     rcx, [rbp+40h+var_80]
0x180137f61  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180137f66  nop
0x180137f67  mov     rdx, r15
0x180137f6a  lea     rcx, [rbp+40h+var_80]
0x180137f6e  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180137f73  lea     rdx, asc_1801D0CA8; "/"
0x180137f7a  lea     rcx, [rbp+40h+var_80]
0x180137f7e  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180137f83  lea     rcx, [rbp+40h+var_80]
0x180137f87  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180137f8c  mov     rbx, rax
0x180137f8f  lea     rcx, [rbp+40h+var_60]
0x180137f93  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180137f98  mov     rcx, [rbp+40h+var_70]
0x180137f9c  lea     rdx, [rbx+rcx*2]
0x180137fa0  mov     rcx, [rbp+40h+var_50]
0x180137fa4  lea     r8, [rax+rcx*2]
0x180137fa8  mov     [rsp+140h+phkResult], rdx
0x180137fad  mov     r9, rbx
0x180137fb0  mov     rdx, rax
0x180137fb3  lea     rcx, [rbp+40h+var_A8]
0x180137fb7  call    std__search_std___String_iterator_std___String_val_std___Simple_types_unsigned_short______std___String_iterator_std___String_val_std___Simple_types_unsigned_short_______lambda_996e1d35f9f711f32d4492c64932d28e___
0x180137fbc  lea     rcx, [rbp+40h+var_60]
0x180137fc0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180137fc5  mov     rcx, [rbp+40h+var_50]
0x180137fc9  lea     rax, [rax+rcx*2]
0x180137fcd  cmp     [rbp+40h+var_A8], rax
0x180137fd1  jz      short loc_180137FE3
0x180137fd3  lea     r8, [rbp+40h+var_60]
0x180137fd7  mov     rdx, [rsi]
0x180137fda  mov     rcx, rsi
0x180137fdd  call    ??$_Emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAPEAU?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@1@QEAU21@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::list<std::wstring>::_Emplace<std::wstring const &>(std::_List_node<std::wstring,void *> * const,std::wstring const &)
0x180137fe2  nop
0x180137fe3  lea     rcx, [rbp+40h+var_80]
0x180137fe7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180137fec  nop
0x180137fed  lea     rcx, [rbp+40h+var_60]
0x180137ff1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180137ff6  inc     edi
0x180137ff8  mov     rcx, [rsp+140h+var_C8]
0x180137ffd  jmp     loc_180137EC2
0x180138002  mov     rcx, [rbp+48h]; this
0x180138006  mov     r9d, eax; char *
0x180138009  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180138010  mov     edx, 87h; void *
0x180138015  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18013801a  mov     ebx, eax
0x18013801c  mov     rcx, [rsp+140h+var_C8]; Block
0x180138021  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180138026  jmp     loc_180137EA4
0x18013802b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180138030  nop
0x180138031  mov     rcx, [rbp+40h+Block]; Block
0x180138035  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18013803a  mov     ebx, r12d
0x18013803d  lea     rcx, [rsp+140h+hKey]
0x180138042  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180138047  mov     eax, ebx
0x180138049  mov     rcx, [rbp+40h+var_40]
0x18013804d  xor     rcx, rsp; StackCookie
0x180138050  call    __security_check_cookie
0x180138055  add     rsp, 110h
0x18013805c  pop     r15
0x18013805e  pop     r14
0x180138060  pop     r12
0x180138062  pop     rdi
0x180138063  pop     rsi
0x180138064  pop     rbx
0x180138065  pop     rbp
0x180138066  retn
```
