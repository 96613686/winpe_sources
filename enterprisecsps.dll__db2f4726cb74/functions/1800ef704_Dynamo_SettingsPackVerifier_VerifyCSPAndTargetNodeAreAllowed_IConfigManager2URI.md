# Dynamo::SettingsPackVerifier::VerifyCSPAndTargetNodeAreAllowed(IConfigManager2URI *)

- ea: `0x1800ef704`
- end: `0x1800efa14`
- name: `?VerifyCSPAndTargetNodeAreAllowed@SettingsPackVerifier@Dynamo@@AEAAJPEAUIConfigManager2URI@@@Z`
- size: `784`
- prototype: `__int64 __fastcall(Dynamo::SettingsPackVerifier *__hidden this, struct IConfigManager2URI *)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800efa1c`

## callees

- `0x180008de0`
- `0x18000caf4`
- `0x18000d4d4`
- `0x18000f0c8`
- `0x180019fd8`
- `0x18002031c`
- `0x18002047c`
- `0x180025a9c`
- `0x180025ac0`
- `0x18002d994`
- `0x18002dc94`
- `0x18002dcc8`
- `0x18008b4d4`
- `0x18008bcb4`
- `0x1800eafa4`
- `0x1800ee968`
- `0x1800ef07c`
- `0x1800ef704`
- `0x180107010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800ef8ff`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800ef8ff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ef86a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ef86a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ef9af`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ef9af`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Dynamo::SettingsPackVerifier::VerifyCSPAndTargetNodeAreAllowed(
        Dynamo::SettingsPackVerifier *this,
        struct IConfigManager2URI *a2)
{
  int SegmentIndexForCSPName; // eax
  signed int v4; // ebx
  __int64 v5; // rdx
  unsigned int v6; // esi
  __int64 (__fastcall *v7)(struct IConfigManager2URI *, _QWORD, _QWORD, __int64 *); // rbx
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, _QWORD, __int64, __int64 *); // rbx
  const WCHAR *v10; // rax
  LSTATUS v11; // eax
  __int64 v12; // rdx
  WCHAR *v13; // r8
  DWORD v14; // edi
  LSTATUS v15; // eax
  int v16; // eax
  int v17; // ecx
  int v18; // r8d
  LPWSTR v19; // rcx
  bool v20; // zf
  PHKEY phkResult; // [rsp+20h] [rbp-69h]
  int phkResulta; // [rsp+20h] [rbp-69h]
  LPWSTR lpValueName; // [rsp+40h] [rbp-49h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-41h] BYREF
  __int64 v26; // [rsp+50h] [rbp-39h] BYREF
  __int64 v27; // [rsp+58h] [rbp-31h] BYREF
  unsigned int v28; // [rsp+60h] [rbp-29h] BYREF
  DWORD cchValueName; // [rsp+64h] [rbp-25h] BYREF
  __int64 v30; // [rsp+68h] [rbp-21h] BYREF
  __int64 v31; // [rsp+70h] [rbp-19h] BYREF
  _BYTE v32[40]; // [rsp+78h] [rbp-11h] BYREF
  _BYTE v33[32]; // [rsp+A0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v31 = 0;
  v28 = 0;
  v30 = 0;
  v27 = 0;
  v26 = 0;
  SegmentIndexForCSPName = Dynamo::SettingsPackVerifier::GetSegmentIndexForCSPName(this, a2, &v28);
  v4 = SegmentIndexForCSPName;
  if ( SegmentIndexForCSPName >= 0 )
  {
    v6 = v28;
    SegmentIndexForCSPName = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, _QWORD, __int64 *))(*(_QWORD *)a2 + 88LL))(
                               a2,
                               v28,
                               &v31);
    v4 = SegmentIndexForCSPName;
    if ( SegmentIndexForCSPName < 0 )
    {
      v5 = 244;
      goto LABEL_5;
    }
    v7 = *(__int64 (__fastcall **)(struct IConfigManager2URI *, _QWORD, _QWORD, __int64 *))(*(_QWORD *)a2 + 80LL);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v27);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v30);
    phkResult = (PHKEY)&v27;
    SegmentIndexForCSPName = v7(a2, v6 + 1, 0, &v30);
    v4 = SegmentIndexForCSPName;
    if ( SegmentIndexForCSPName < 0 )
    {
      v5 = 245;
      goto LABEL_5;
    }
    v8 = v27;
    v9 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64 *))(*(_QWORD *)v27 + 120LL);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v26,
      0);
    SegmentIndexForCSPName = v9(v8, 0, 47, &v26);
    v4 = SegmentIndexForCSPName;
    if ( SegmentIndexForCSPName < 0 )
    {
      v5 = 246;
      goto LABEL_5;
    }
    hKey = 0;
    std::wstring::wstring(v33, L"Software\\Microsoft\\Windows\\DynamicManagement\\");
    std::wstring::append(v33, v31);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v10 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v33);
    v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v10, 0, 0x20019u, &hKey);
    v4 = v11;
    if ( v11 == 2 )
    {
      v4 = -2147024809;
      v12 = 254;
      goto LABEL_17;
    }
    if ( v11 )
    {
      if ( v11 > 0 )
        v4 = (unsigned __int16)v11 | 0x80070000;
      if ( v4 >= 0 )
        goto LABEL_32;
      v12 = 261;
LABEL_17:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\syncmlpackprocessor.cpp",
        (const char *)(unsigned int)v4,
        phkResulta);
LABEL_32:
      std::wstring::~wstring(v33);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      goto LABEL_33;
    }
    cchValueName = 1024;
    wil::make_unique_hlocal<unsigned short [0]>(&lpValueName, 1024);
    v13 = lpValueName;
    if ( lpValueName )
    {
      v14 = 0;
      while ( 1 )
      {
        v15 = RegEnumValueW(hKey, v14, v13, &cchValueName, 0, 0, 0, 0);
        v4 = v15;
        if ( v15 )
          break;
        cchValueName = 1024;
        ++v14;
        std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::basic_regex<unsigned short,std::regex_traits<unsigned short>>(
          v32,
          lpValueName);
        v16 = std::_WChar_traits<unsigned short>::length(v26);
        if ( (unsigned __int8)std::_Regex_match1<unsigned short const *,std::allocator<std::sub_match<unsigned short const *>>,unsigned short,std::regex_traits<unsigned short>,unsigned short const *>(
                                v17,
                                v17 + 2 * v16,
                                v18,
                                (unsigned int)v32,
                                16) )
        {
          v4 = 0;
          std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::~basic_regex<unsigned short,std::regex_traits<unsigned short>>(v32);
          goto LABEL_25;
        }
        std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::~basic_regex<unsigned short,std::regex_traits<unsigned short>>(v32);
        v13 = lpValueName;
      }
      if ( v15 != 259 )
      {
LABEL_25:
        if ( v14 )
        {
          if ( v4 > 0 )
            v4 = (unsigned __int16)v4 | 0x80070000;
          goto LABEL_30;
        }
      }
      v4 = -2147024809;
      goto LABEL_30;
    }
    v4 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10D,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\syncmlpackprocessor.cpp",
      (const char *)0x8007000ELL,
      phkResulta);
LABEL_30:
    v19 = lpValueName;
    v20 = lpValueName == 0;
    lpValueName = 0;
    if ( !v20 )
      LocalFree(v19);
    goto LABEL_32;
  }
  v5 = 242;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\syncmlpackprocessor.cpp",
    (const char *)(unsigned int)SegmentIndexForCSPName,
    (int)phkResult);
LABEL_33:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v26);
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v27);
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v30);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800ef704  mov     [rsp-8+arg_0], rbx
0x1800ef709  mov     [rsp-8+arg_10], rsi
0x1800ef70e  push    rbp
0x1800ef70f  push    rdi
0x1800ef710  push    r14
0x1800ef712  lea     rbp, [rsp-47h]
0x1800ef717  sub     rsp, 0D0h
0x1800ef71e  mov     rax, cs:__security_cookie
0x1800ef725  xor     rax, rsp
0x1800ef728  mov     [rbp+57h+var_20], rax
0x1800ef72c  mov     rdi, rdx
0x1800ef72f  xor     r14d, r14d
0x1800ef732  mov     [rbp+57h+var_70], r14
0x1800ef736  mov     [rbp+57h+var_80], r14d
0x1800ef73a  mov     [rbp+57h+var_78], r14
0x1800ef73e  mov     [rbp+57h+var_88], r14
0x1800ef742  mov     [rbp+57h+var_90], r14
0x1800ef746  lea     r8, [rbp+57h+var_80]; unsigned int *
0x1800ef74a  call    ?GetSegmentIndexForCSPName@SettingsPackVerifier@Dynamo@@AEAAJPEAUIConfigManager2URI@@AEAK@Z; Dynamo::SettingsPackVerifier::GetSegmentIndexForCSPName(IConfigManager2URI *,ulong &)
0x1800ef74f  mov     ebx, eax
0x1800ef751  test    eax, eax
0x1800ef753  jns     short loc_1800EF75C
0x1800ef755  mov     edx, 0F2h
0x1800ef75a  jmp     short loc_1800EF77F
0x1800ef75c  mov     rax, [rdi]
0x1800ef75f  lea     r8, [rbp+57h+var_70]
0x1800ef763  mov     esi, [rbp+57h+var_80]
0x1800ef766  mov     edx, esi
0x1800ef768  mov     rcx, rdi
0x1800ef76b  mov     rax, [rax+58h]
0x1800ef76f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef774  mov     ebx, eax
0x1800ef776  test    eax, eax
0x1800ef778  jns     short loc_1800EF797
0x1800ef77a  mov     edx, 0F4h; void *
0x1800ef77f  lea     r8, aOnecoreuapAdmi_97; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800ef786  mov     r9d, eax; char *
0x1800ef789  mov     rcx, [rbp+5Fh]; this
0x1800ef78d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ef792  jmp     loc_1800EF9D0
0x1800ef797  mov     rax, [rdi]
0x1800ef79a  mov     rbx, [rax+50h]
0x1800ef79e  lea     rcx, [rbp+57h+var_88]
0x1800ef7a2  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800ef7a7  lea     rcx, [rbp+57h+var_78]
0x1800ef7ab  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800ef7b0  lea     edx, [rsi+1]
0x1800ef7b3  lea     rax, [rbp+57h+var_88]
0x1800ef7b7  mov     [rsp+0E0h+phkResult], rax
0x1800ef7bc  lea     r9, [rbp+57h+var_78]
0x1800ef7c0  xor     r8d, r8d
0x1800ef7c3  mov     rcx, rdi
0x1800ef7c6  mov     rax, rbx
0x1800ef7c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef7ce  mov     ebx, eax
0x1800ef7d0  test    eax, eax
0x1800ef7d2  jns     short loc_1800EF7DB
0x1800ef7d4  mov     edx, 0F5h
0x1800ef7d9  jmp     short loc_1800EF77F
0x1800ef7db  mov     rdi, [rbp+57h+var_88]
0x1800ef7df  mov     rax, [rdi]
0x1800ef7e2  mov     rbx, [rax+78h]
0x1800ef7e6  xor     edx, edx
0x1800ef7e8  lea     rcx, [rbp+57h+var_90]
0x1800ef7ec  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800ef7f1  mov     r8d, 2Fh ; '/'
0x1800ef7f7  lea     r9, [rbp+57h+var_90]
0x1800ef7fb  xor     edx, edx
0x1800ef7fd  mov     rcx, rdi
0x1800ef800  mov     rax, rbx
0x1800ef803  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef808  mov     ebx, eax
0x1800ef80a  test    eax, eax
0x1800ef80c  jns     short loc_1800EF818
0x1800ef80e  mov     edx, 0F6h
0x1800ef813  jmp     loc_1800EF77F
0x1800ef818  mov     [rbp+57h+hKey], r14
0x1800ef81c  lea     rdx, aSoftwareMicros_20; "Software\\Microsoft\\Windows\\DynamicMa"...
0x1800ef823  lea     rcx, [rbp+57h+var_40]
0x1800ef827  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800ef82c  nop
0x1800ef82d  mov     rdx, [rbp+57h+var_70]
0x1800ef831  lea     rcx, [rbp+57h+var_40]
0x1800ef835  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800ef83a  xor     edx, edx
0x1800ef83c  lea     rcx, [rbp+57h+hKey]
0x1800ef840  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800ef845  lea     rcx, [rbp+57h+var_40]
0x1800ef849  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800ef84e  mov     rdx, rax; lpSubKey
0x1800ef851  lea     rax, [rbp+57h+hKey]
0x1800ef855  mov     [rsp+0E0h+phkResult], rax; int
0x1800ef85a  mov     r9d, 20019h; samDesired
0x1800ef860  xor     r8d, r8d; ulOptions
0x1800ef863  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800ef86a  call    cs:__imp_RegOpenKeyExW
0x1800ef871  nop     dword ptr [rax+rax+00h]
0x1800ef876  mov     ebx, eax
0x1800ef878  cmp     eax, 2
0x1800ef87b  jnz     short loc_1800EF889
0x1800ef87d  mov     ebx, 80070057h
0x1800ef882  mov     edx, 0FEh
0x1800ef887  jmp     short loc_1800EF8A5
0x1800ef889  test    eax, eax
0x1800ef88b  jz      short loc_1800EF8BD
0x1800ef88d  jle     short loc_1800EF898
0x1800ef88f  movzx   ebx, ax
0x1800ef892  or      ebx, 80070000h
0x1800ef898  test    ebx, ebx
0x1800ef89a  jns     loc_1800EF9BC
0x1800ef8a0  mov     edx, 105h; void *
0x1800ef8a5  mov     r9d, ebx; char *
0x1800ef8a8  lea     r8, aOnecoreuapAdmi_97; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800ef8af  mov     rcx, [rbp+5Fh]; this
0x1800ef8b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ef8b8  jmp     loc_1800EF9BC
0x1800ef8bd  mov     esi, 400h
0x1800ef8c2  mov     [rbp+57h+cchValueName], esi
0x1800ef8c5  mov     edx, esi
0x1800ef8c7  lea     rcx, [rbp+57h+lpValueName]
0x1800ef8cb  call    ??$make_unique_hlocal@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<ushort [0]>(unsigned __int64)
0x1800ef8d0  nop
0x1800ef8d1  mov     r8, [rbp+57h+lpValueName]; lpValueName
0x1800ef8d5  test    r8, r8
0x1800ef8d8  jz      loc_1800EF984
0x1800ef8de  mov     edi, r14d
0x1800ef8e1  mov     [rsp+0E0h+lpcbData], r14; lpcbData
0x1800ef8e6  mov     [rsp+0E0h+lpData], r14; lpData
0x1800ef8eb  mov     [rsp+0E0h+lpType], r14; lpType
0x1800ef8f0  mov     [rsp+0E0h+phkResult], r14; lpReserved
0x1800ef8f5  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x1800ef8f9  mov     edx, edi; dwIndex
0x1800ef8fb  mov     rcx, [rbp+57h+hKey]; hKey
0x1800ef8ff  call    cs:__imp_RegEnumValueW
0x1800ef906  nop     dword ptr [rax+rax+00h]
0x1800ef90b  mov     ebx, eax
0x1800ef90d  test    eax, eax
0x1800ef90f  jnz     short loc_1800EF963
0x1800ef911  mov     [rbp+57h+cchValueName], esi
0x1800ef914  inc     edi
0x1800ef916  mov     rdx, [rbp+57h+lpValueName]
0x1800ef91a  lea     rcx, [rbp+57h+var_68]
0x1800ef91e  call    ??0?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@PEBGW4syntax_option_type@regex_constants@1@@Z; std::basic_regex<ushort,std::regex_traits<ushort>>::basic_regex<ushort,std::regex_traits<ushort>>(ushort const *,std::regex_constants::syntax_option_type)
0x1800ef923  nop
0x1800ef924  mov     rcx, [rbp+57h+var_90]
0x1800ef928  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1800ef92d  lea     rdx, [rcx+rax*2]
0x1800ef931  mov     dword ptr [rsp+0E0h+phkResult], 10h
0x1800ef939  lea     r9, [rbp+57h+var_68]
0x1800ef93d  call    ??$_Regex_match1@PEBGV?$allocator@V?$sub_match@PEBG@std@@@std@@GV?$regex_traits@G@2@PEBG@std@@YA_NPEBG0PEAV?$match_results@PEBGV?$allocator@V?$sub_match@PEBG@std@@@std@@@0@AEBV?$basic_regex@GV?$regex_traits@G@std@@@0@W4match_flag_type@regex_constants@0@_N@Z; std::_Regex_match1<ushort const *,std::allocator<std::sub_match<ushort const *>>,ushort,std::regex_traits<ushort>,ushort const *>(ushort const *,ushort const *,std::match_results<ushort const *> *,std::basic_regex<ushort,std::regex_traits<ushort>> const &,std::regex_constants::match_flag_type,bool)
0x1800ef942  test    al, al
0x1800ef944  jnz     short loc_1800EF955
0x1800ef946  lea     rcx, [rbp+57h+var_68]
0x1800ef94a  call    ??1?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@XZ; std::basic_regex<ushort,std::regex_traits<ushort>>::~basic_regex<ushort,std::regex_traits<ushort>>(void)
0x1800ef94f  mov     r8, [rbp+57h+lpValueName]
0x1800ef953  jmp     short loc_1800EF8E1
0x1800ef955  mov     ebx, r14d
0x1800ef958  lea     rcx, [rbp+57h+var_68]
0x1800ef95c  call    ??1?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@XZ; std::basic_regex<ushort,std::regex_traits<ushort>>::~basic_regex<ushort,std::regex_traits<ushort>>(void)
0x1800ef961  jmp     short loc_1800EF96A
0x1800ef963  cmp     eax, 103h
0x1800ef968  jz      short loc_1800EF97D
0x1800ef96a  test    edi, edi
0x1800ef96c  jz      short loc_1800EF97D
0x1800ef96e  test    ebx, ebx
0x1800ef970  jle     short loc_1800EF9A2
0x1800ef972  movzx   ebx, bx
0x1800ef975  or      ebx, 80070000h
0x1800ef97b  jmp     short loc_1800EF9A2
0x1800ef97d  mov     ebx, 80070057h
0x1800ef982  jmp     short loc_1800EF9A2
0x1800ef984  mov     rcx, [rbp+5Fh]; this
0x1800ef988  mov     ebx, 8007000Eh
0x1800ef98d  mov     r9d, ebx; char *
0x1800ef990  lea     r8, aOnecoreuapAdmi_97; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800ef997  mov     edx, 10Dh; void *
0x1800ef99c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ef9a1  nop
0x1800ef9a2  mov     rcx, [rbp+57h+lpValueName]; hMem
0x1800ef9a6  test    rcx, rcx
0x1800ef9a9  mov     [rbp+57h+lpValueName], r14
0x1800ef9ad  jz      short loc_1800EF9BC
0x1800ef9af  call    cs:__imp_LocalFree
0x1800ef9b6  nop     dword ptr [rax+rax+00h]
0x1800ef9bb  nop
0x1800ef9bc  lea     rcx, [rbp+57h+var_40]
0x1800ef9c0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800ef9c5  nop
0x1800ef9c6  lea     rcx, [rbp+57h+hKey]
0x1800ef9ca  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800ef9cf  nop
0x1800ef9d0  lea     rcx, [rbp+57h+var_90]
0x1800ef9d4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800ef9d9  nop
0x1800ef9da  lea     rcx, [rbp+57h+var_88]
0x1800ef9de  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800ef9e3  nop
0x1800ef9e4  lea     rcx, [rbp+57h+var_78]
0x1800ef9e8  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800ef9ed  mov     eax, ebx
0x1800ef9ef  mov     rcx, [rbp+57h+var_20]
0x1800ef9f3  xor     rcx, rsp; StackCookie
0x1800ef9f6  call    __security_check_cookie
0x1800ef9fb  lea     r11, [rsp+0E0h+var_10]
0x1800efa03  mov     rbx, [r11+20h]
0x1800efa07  mov     rsi, [r11+30h]
0x1800efa0b  mov     rsp, r11
0x1800efa0e  pop     r14
0x1800efa10  pop     rdi
0x1800efa11  pop     rbp
0x1800efa12  retn
```
