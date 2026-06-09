# Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::Enumerate(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,ushort const *,ushort const *,std::list<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x180139dd0`
- end: `0x18013a180`
- name: `?Enumerate@ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG1AEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `944`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18013959c`
- `0x18013a39c`

## callees

- `0x180019080`
- `0x180019588`
- `0x18001989c`
- `0x1800e68b0`
- `0x1800e734c`
- `0x1800e7de8`
- `0x1800e8508`
- `0x1800ed46c`
- `0x1800ef8c4`
- `0x1800efd9c`
- `0x1800f00e4`
- `0x180105294`
- `0x180134e08`
- `0x180138ba8`
- `0x180138d08`
- `0x180139364`
- `0x180139dd0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180139ef8`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180139ef8`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18013a018`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18013a018`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180139e5b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180139e5b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180139e28`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180139e28`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
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
0x180139dd0  push    rbp
0x180139dd2  push    rbx
0x180139dd3  push    rsi
0x180139dd4  push    rdi
0x180139dd5  push    r12
0x180139dd7  push    r14
0x180139dd9  push    r15
0x180139ddb  lea     rbp, [rsp-10h]
0x180139de0  sub     rsp, 110h
0x180139de7  mov     rax, cs:__security_cookie
0x180139dee  xor     rax, rsp
0x180139df1  mov     [rbp+40h+var_40], rax
0x180139df5  mov     r15, r9
0x180139df8  mov     r14, r8
0x180139dfb  mov     rdi, rdx
0x180139dfe  mov     rsi, [rbp+40h+arg_20]
0x180139e02  xor     r12d, r12d
0x180139e05  mov     [rsp+140h+hKey], r12
0x180139e0a  mov     rcx, rsi
0x180139e0d  call    ?clear@?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXXZ; std::list<std::wstring>::clear(void)
0x180139e12  mov     rbx, [rsp+140h+hKey]
0x180139e17  test    rbx, rbx
0x180139e1a  jz      short loc_180139E3D
0x180139e1c  lea     rcx, [rbp+40h+cchValueName]; this
0x180139e20  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180139e25  mov     rcx, rbx; hKey
0x180139e28  call    cs:__imp_RegCloseKey
0x180139e2f  nop     dword ptr [rax+rax+00h]
0x180139e34  lea     rcx, [rbp+40h+cchValueName]; this
0x180139e38  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180139e3d  mov     [rsp+140h+hKey], r12
0x180139e42  lea     rax, [rsp+140h+hKey]
0x180139e47  mov     [rsp+140h+phkResult], rax; int
0x180139e4c  mov     r9d, 20019h; samDesired
0x180139e52  xor     r8d, r8d; ulOptions
0x180139e55  mov     rdx, r14; lpSubKey
0x180139e58  mov     rcx, [rdi]; hKey
0x180139e5b  call    cs:__imp_RegOpenKeyExW
0x180139e62  nop     dword ptr [rax+rax+00h]
0x180139e67  mov     ebx, eax
0x180139e69  cmp     eax, 2
0x180139e6c  jz      loc_18013A152
0x180139e72  test    eax, eax
0x180139e74  jle     short loc_180139E7F
0x180139e76  movzx   ebx, ax
0x180139e79  or      ebx, 80070000h
0x180139e7f  test    ebx, ebx
0x180139e81  jns     short loc_180139EA0
0x180139e83  mov     edx, 56h ; 'V'; void *
0x180139e88  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180139e8f  mov     r9d, ebx; char *
0x180139e92  mov     rcx, [rbp+48h]; this
0x180139e96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180139e9b  jmp     loc_18013A155
0x180139ea0  mov     [rsp+140h+Type], r12d
0x180139ea5  mov     [rsp+140h+cValues], r12d
0x180139eaa  mov     [rsp+140h+cbMaxValueNameLen], r12d
0x180139eaf  mov     [rsp+140h+cbMaxValueLen], r12d
0x180139eb4  mov     [rsp+140h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180139eb9  mov     [rsp+140h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x180139ebe  lea     rax, [rsp+140h+cbMaxValueLen]
0x180139ec3  mov     [rsp+140h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180139ec8  lea     rax, [rsp+140h+cbMaxValueNameLen]
0x180139ecd  mov     [rsp+140h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180139ed2  lea     rax, [rsp+140h+cValues]
0x180139ed7  mov     [rsp+140h+lpcValues], rax; lpcValues
0x180139edc  mov     [rsp+140h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x180139ee1  mov     [rsp+140h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x180139ee6  mov     [rsp+140h+phkResult], r12; int
0x180139eeb  xor     r9d, r9d; lpReserved
0x180139eee  xor     r8d, r8d; lpcchClass
0x180139ef1  xor     edx, edx; lpClass
0x180139ef3  mov     rcx, [rsp+140h+hKey]; hKey
0x180139ef8  call    cs:__imp_RegQueryInfoKeyW
0x180139eff  nop     dword ptr [rax+rax+00h]
0x180139f04  test    eax, eax
0x180139f06  jz      short loc_180139F27
0x180139f08  mov     rcx, [rbp+48h]; this
0x180139f0c  mov     r9d, eax; char *
0x180139f0f  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180139f16  mov     edx, 69h ; 'i'; void *
0x180139f1b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180139f20  mov     ebx, eax
0x180139f22  jmp     loc_18013A155
0x180139f27  mov     ecx, [rsp+140h+cbMaxValueNameLen]
0x180139f2b  inc     ecx
0x180139f2d  mov     [rsp+140h+cbMaxValueNameLen], ecx
0x180139f31  mov     eax, 2
0x180139f36  mul     rcx
0x180139f39  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180139f40  cmovb   rax, rcx
0x180139f44  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180139f4b  mov     rcx, rax; unsigned __int64
0x180139f4e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180139f53  mov     [rbp+40h+Block], rax
0x180139f57  test    rax, rax
0x180139f5a  jnz     short loc_180139F69
0x180139f5c  mov     ebx, 8007000Eh
0x180139f61  lea     edx, [rax+6Ch]
0x180139f64  jmp     loc_180139E88
0x180139f69  lea     rax, [rbp+40h+Block]
0x180139f6d  mov     [rbp+40h+var_A0], rax
0x180139f71  mov     [rbp+40h+var_98], 1
0x180139f75  mov     eax, [rsp+140h+cbMaxValueLen]
0x180139f79  inc     eax
0x180139f7b  mov     [rsp+140h+cbMaxValueLen], eax
0x180139f7f  mov     ecx, eax; unsigned __int64
0x180139f81  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180139f88  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180139f8d  mov     rcx, rax; Block
0x180139f90  mov     [rsp+140h+var_C8], rax
0x180139f95  test    rax, rax
0x180139f98  jnz     short loc_180139FC4
0x180139f9a  mov     rcx, [rbp+48h]; this
0x180139f9e  mov     ebx, 8007000Eh
0x180139fa3  mov     r9d, ebx; char *
0x180139fa6  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180139fad  lea     edx, [rax+73h]; void *
0x180139fb0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180139fb5  nop
0x180139fb6  mov     rcx, [rbp+40h+Block]; Block
0x180139fba  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180139fbf  jmp     loc_18013A155
0x180139fc4  lea     rax, [rsp+140h+var_C8]
0x180139fc9  mov     [rbp+40h+var_90], rax
0x180139fcd  mov     [rbp+40h+var_88], 1
0x180139fd1  mov     edi, r12d
0x180139fd4  cmp     edi, [rsp+140h+cValues]
0x180139fd8  jnb     loc_18013A143
0x180139fde  mov     eax, [rsp+140h+cbMaxValueNameLen]
0x180139fe2  mov     [rbp+40h+cchValueName], eax
0x180139fe5  mov     eax, [rsp+140h+cbMaxValueLen]
0x180139fe9  mov     [rbp+40h+cbData], eax
0x180139fec  lea     rax, [rbp+40h+cbData]
0x180139ff0  mov     [rsp+140h+lpcValues], rax; lpcbData
0x180139ff5  mov     [rsp+140h+lpcbMaxClassLen], rcx; lpData
0x180139ffa  lea     rax, [rsp+140h+Type]
0x180139fff  mov     [rsp+140h+lpcbMaxSubKeyLen], rax; lpType
0x18013a004  mov     [rsp+140h+phkResult], r12; unsigned int
0x18013a009  lea     r9, [rbp+40h+cchValueName]; lpcchValueName
0x18013a00d  mov     r8, [rbp+40h+Block]; lpValueName
0x18013a011  mov     edx, edi; dwIndex
0x18013a013  mov     rcx, [rsp+140h+hKey]; hKey
0x18013a018  call    cs:__imp_RegEnumValueW
0x18013a01f  nop     dword ptr [rax+rax+00h]
0x18013a024  test    eax, eax
0x18013a026  jnz     loc_18013A11A
0x18013a02c  cmp     [rsp+140h+Type], 1
0x18013a031  jnz     loc_18013A10E
0x18013a037  mov     rdx, [rsp+140h+var_C8]
0x18013a03c  test    r15, r15
0x18013a03f  jnz     short loc_18013A064
0x18013a041  lea     rcx, [rbp+40h+var_80]
0x18013a045  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18013a04a  nop
0x18013a04b  lea     r8, [rbp+40h+var_80]
0x18013a04f  mov     rdx, [rsi]
0x18013a052  mov     rcx, rsi
0x18013a055  call    ??$_Emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAPEAU?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@1@QEAU21@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::list<std::wstring>::_Emplace<std::wstring>(std::_List_node<std::wstring,void *> * const,std::wstring &&)
0x18013a05a  nop
0x18013a05b  lea     rcx, [rbp+40h+var_80]
0x18013a05f  jmp     loc_18013A109
0x18013a064  lea     rcx, [rbp+40h+var_60]
0x18013a068  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18013a06d  nop
0x18013a06e  lea     rdx, asc_1801D2C90; "/"
0x18013a075  lea     rcx, [rbp+40h+var_80]
0x18013a079  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18013a07e  nop
0x18013a07f  mov     rdx, r15
0x18013a082  lea     rcx, [rbp+40h+var_80]
0x18013a086  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18013a08b  lea     rdx, asc_1801D2C90; "/"
0x18013a092  lea     rcx, [rbp+40h+var_80]
0x18013a096  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18013a09b  lea     rcx, [rbp+40h+var_80]
0x18013a09f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18013a0a4  mov     rbx, rax
0x18013a0a7  lea     rcx, [rbp+40h+var_60]
0x18013a0ab  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18013a0b0  mov     rcx, [rbp+40h+var_70]
0x18013a0b4  lea     rdx, [rbx+rcx*2]
0x18013a0b8  mov     rcx, [rbp+40h+var_50]
0x18013a0bc  lea     r8, [rax+rcx*2]
0x18013a0c0  mov     [rsp+140h+phkResult], rdx
0x18013a0c5  mov     r9, rbx
0x18013a0c8  mov     rdx, rax
0x18013a0cb  lea     rcx, [rbp+40h+var_A8]
0x18013a0cf  call    std__search_std___String_iterator_std___String_val_std___Simple_types_unsigned_short______std___String_iterator_std___String_val_std___Simple_types_unsigned_short_______lambda_996e1d35f9f711f32d4492c64932d28e___
0x18013a0d4  lea     rcx, [rbp+40h+var_60]
0x18013a0d8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18013a0dd  mov     rcx, [rbp+40h+var_50]
0x18013a0e1  lea     rax, [rax+rcx*2]
0x18013a0e5  cmp     [rbp+40h+var_A8], rax
0x18013a0e9  jz      short loc_18013A0FB
0x18013a0eb  lea     r8, [rbp+40h+var_60]
0x18013a0ef  mov     rdx, [rsi]
0x18013a0f2  mov     rcx, rsi
0x18013a0f5  call    ??$_Emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAPEAU?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@1@QEAU21@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::list<std::wstring>::_Emplace<std::wstring const &>(std::_List_node<std::wstring,void *> * const,std::wstring const &)
0x18013a0fa  nop
0x18013a0fb  lea     rcx, [rbp+40h+var_80]
0x18013a0ff  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013a104  nop
0x18013a105  lea     rcx, [rbp+40h+var_60]
0x18013a109  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013a10e  inc     edi
0x18013a110  mov     rcx, [rsp+140h+var_C8]
0x18013a115  jmp     loc_180139FD4
0x18013a11a  mov     rcx, [rbp+48h]; this
0x18013a11e  mov     r9d, eax; char *
0x18013a121  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18013a128  mov     edx, 87h; void *
0x18013a12d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18013a132  mov     ebx, eax
0x18013a134  mov     rcx, [rsp+140h+var_C8]; Block
0x18013a139  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18013a13e  jmp     loc_180139FB6
0x18013a143  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18013a148  nop
0x18013a149  mov     rcx, [rbp+40h+Block]; Block
0x18013a14d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18013a152  mov     ebx, r12d
0x18013a155  lea     rcx, [rsp+140h+hKey]
0x18013a15a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18013a15f  mov     eax, ebx
0x18013a161  mov     rcx, [rbp+40h+var_40]
0x18013a165  xor     rcx, rsp; StackCookie
0x18013a168  call    __security_check_cookie
0x18013a16d  add     rsp, 110h
0x18013a174  pop     r15
0x18013a176  pop     r14
0x18013a178  pop     r12
0x18013a17a  pop     rdi
0x18013a17b  pop     rsi
0x18013a17c  pop     rbx
0x18013a17d  pop     rbp
0x18013a17e  retn
```
