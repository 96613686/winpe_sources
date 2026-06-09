# MdmLogCollector::AddAreaEntry(ushort const *,ushort const *,std::function<long (ushort const *)>)

- ea: `0x18010863c`
- end: `0x1801089b8`
- name: `?AddAreaEntry@MdmLogCollector@@AEAAJPEBG0V?$function@$$A6AJPEBG@Z@std@@@Z`
- size: `892`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting`

## callers

- `0x180108ec8`

## callees

- `0x180019000`
- `0x180019514`
- `0x1800e66dc`
- `0x1800e7c08`
- `0x1800ece5c`
- `0x1800ef188`
- `0x1800ef5d8`
- `0x1800ef900`
- `0x180104108`
- `0x180107e60`
- `0x18010863c`
- `0x180191010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180108903`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180108903`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180108886`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180108886`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1801087b8`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1801087b8`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180108868`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180108868`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801086c1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801086c1`

## string_xrefs

- `0x180108728`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x1801087c9`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x1801088e3`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x180108911`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010887c`: `MaxPerWildcardMatchesPerDirectory`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall MdmLogCollector::AddAreaEntry(__int64 a1, __int64 a2, __int64 a3, __int64 *a4)
{
  const WCHAR *v7; // rax
  LSTATUS v8; // eax
  unsigned int v9; // ebx
  unsigned int v10; // esi
  __int64 v11; // rdx
  __int64 *v12; // rcx
  __int64 *v14; // rcx
  __int64 v15; // rdx
  void (__fastcall *v16)(__int64 *, __int64); // rax
  unsigned int v17; // eax
  WCHAR *v18; // r14
  DWORD i; // ebx
  unsigned int v20; // eax
  int v21; // eax
  __int64 v22; // rcx
  int v23; // eax
  __int64 v24; // rdx
  __int64 *v25; // rcx
  int phkResult; // [rsp+20h] [rbp-79h]
  unsigned int phkResulta; // [rsp+20h] [rbp-79h]
  unsigned int phkResultb; // [rsp+20h] [rbp-79h]
  HKEY hKey; // [rsp+60h] [rbp-39h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+68h] [rbp-31h] BYREF
  DWORD cValues; // [rsp+6Ch] [rbp-2Dh] BYREF
  BYTE Data[4]; // [rsp+70h] [rbp-29h] BYREF
  DWORD Type; // [rsp+74h] [rbp-25h] BYREF
  DWORD cbData; // [rsp+78h] [rbp-21h] BYREF
  DWORD cchValueName; // [rsp+7Ch] [rbp-1Dh] BYREF
  WCHAR *v36; // [rsp+80h] [rbp-19h] BYREF
  _QWORD v37[2]; // [rsp+88h] [rbp-11h] BYREF
  _BYTE v38[32]; // [rsp+98h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v37[1] = a4;
  std::wstring::wstring(v38, a2);
  std::wstring::append(v38, L"\\");
  std::wstring::append(v38, a3);
  hKey = 0;
  v7 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v38);
  v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v7, 0, 0x20019u, &hKey);
  v9 = v8;
  if ( v8 > 0 )
    v9 = (unsigned __int16)v8 | 0x80070000;
  if ( (v9 & 0x80000000) != 0 )
  {
    v10 = -2147024894;
    if ( v9 == -2147024894 )
    {
LABEL_5:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      std::wstring::_Tidy_deallocate(v38);
      v12 = (__int64 *)a4[7];
      if ( v12 )
      {
        LOBYTE(v11) = v12 != a4;
        (*(void (__fastcall **)(__int64 *, __int64))(*v12 + 32))(v12, v11);
        a4[7] = 0;
      }
      return v10;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC1,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
      (const char *)v9,
      phkResult);
    goto LABEL_9;
  }
  cbMaxValueNameLen = 0;
  cValues = 0;
  v17 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, 0, 0, 0);
  if ( v17 )
  {
    v9 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0xC7,
           (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
           (const char *)v17,
           phkResulta);
LABEL_9:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    std::wstring::_Tidy_deallocate(v38);
    v14 = (__int64 *)a4[7];
    if ( !v14 )
      return v9;
    v15 = *v14;
    v16 = *(void (__fastcall **)(__int64 *, __int64))(*v14 + 32);
LABEL_11:
    LOBYTE(v15) = v14 != a4;
    v16(v14, v15);
    a4[7] = 0;
    return v9;
  }
  if ( cValues )
  {
    v18 = (WCHAR *)operator new[](saturated_mul(++cbMaxValueNameLen, 2u));
    v36 = v18;
    for ( i = 0; ; ++i )
    {
      if ( i >= cValues )
      {
        std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v36);
        goto LABEL_33;
      }
      cchValueName = cbMaxValueNameLen;
      Type = 4;
      *(_DWORD *)Data = 0;
      cbData = 4;
      v20 = RegEnumValueW(hKey, i, v18, &cchValueName, 0, &Type, Data, &cbData);
      if ( v20 )
        break;
      if ( Type == 4 )
      {
        if ( (unsigned int)_o__wcsicmp(v18, L"MaxPerWildcardMatchesPerDirectory") )
        {
          v21 = *(_DWORD *)(a1 + 176);
          if ( !v21 || !*(_DWORD *)Data || (v21 & *(_DWORD *)Data) != 0 )
          {
            v37[0] = v18;
            v22 = a4[7];
            if ( !v22 )
            {
              std::_Xbad_function_call();
              __debugbreak();
            }
            v23 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v22 + 16LL))(v22, v37);
            v10 = v23;
            if ( v23 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xE7,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
                (const char *)(unsigned int)v23,
                phkResultb);
              std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v36);
              goto LABEL_5;
            }
          }
        }
        else
        {
          *(_DWORD *)(a1 + 216) = *(_DWORD *)Data;
        }
      }
    }
    v9 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0xD3,
           (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
           (const char *)v20,
           phkResultb);
    std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v36);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    std::wstring::_Tidy_deallocate(v38);
    v14 = (__int64 *)a4[7];
    if ( !v14 )
      return v9;
    v16 = *(void (__fastcall **)(__int64 *, __int64))(*v14 + 32);
    goto LABEL_11;
  }
LABEL_33:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  std::wstring::_Tidy_deallocate(v38);
  v25 = (__int64 *)a4[7];
  if ( v25 )
  {
    LOBYTE(v24) = v25 != a4;
    (*(void (__fastcall **)(__int64 *, __int64))(*v25 + 32))(v25, v24);
    a4[7] = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18010863c  push    rbp
0x18010863e  push    rbx
0x18010863f  push    rsi
0x180108640  push    rdi
0x180108641  push    r12
0x180108643  push    r14
0x180108645  push    r15
0x180108647  lea     rbp, [rsp-27h]
0x18010864c  sub     rsp, 0C0h
0x180108653  mov     rax, cs:__security_cookie
0x18010865a  xor     rax, rsp
0x18010865d  mov     [rbp+57h+var_38], rax
0x180108661  mov     rdi, r9
0x180108664  mov     rbx, r8
0x180108667  mov     r15, rcx
0x18010866a  mov     [rbp+57h+var_60], r9
0x18010866e  lea     rcx, [rbp+57h+var_58]
0x180108672  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180108677  nop
0x180108678  lea     rdx, psz; "\\"
0x18010867f  lea     rcx, [rbp+57h+var_58]
0x180108683  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180108688  mov     rdx, rbx
0x18010868b  lea     rcx, [rbp+57h+var_58]
0x18010868f  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180108694  nop
0x180108695  xor     r12d, r12d
0x180108698  mov     [rbp+57h+hKey], r12
0x18010869c  lea     rcx, [rbp+57h+var_58]
0x1801086a0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801086a5  mov     rdx, rax; lpSubKey
0x1801086a8  lea     rax, [rbp+57h+hKey]
0x1801086ac  mov     [rsp+0F0h+phkResult], rax; int
0x1801086b1  mov     r9d, 20019h; samDesired
0x1801086b7  xor     r8d, r8d; ulOptions
0x1801086ba  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801086c1  call    cs:__imp_RegOpenKeyExW
0x1801086c7  mov     ebx, eax
0x1801086c9  test    eax, eax
0x1801086cb  jle     short loc_1801086D6
0x1801086cd  movzx   ebx, ax
0x1801086d0  or      ebx, 80070000h
0x1801086d6  test    ebx, ebx
0x1801086d8  jns     loc_180108774
0x1801086de  mov     esi, 80070002h
0x1801086e3  cmp     ebx, esi
0x1801086e5  jnz     short loc_180108721
0x1801086e7  lea     rcx, [rbp+57h+hKey]
0x1801086eb  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801086f0  nop
0x1801086f1  lea     rcx, [rbp+57h+var_58]
0x1801086f5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801086fa  nop
0x1801086fb  mov     rcx, [rdi+38h]
0x1801086ff  test    rcx, rcx
0x180108702  jz      short loc_18010871A
0x180108704  mov     rax, [rcx]
0x180108707  cmp     rcx, rdi
0x18010870a  setnz   dl
0x18010870d  mov     rax, [rax+20h]
0x180108711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180108716  mov     [rdi+38h], r12
0x18010871a  mov     eax, esi
0x18010871c  jmp     loc_18010899A
0x180108721  mov     rcx, [rbp+5Fh]; this
0x180108725  mov     r9d, ebx; char *
0x180108728  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010872f  mov     edx, 0C1h; void *
0x180108734  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180108739  nop
0x18010873a  lea     rcx, [rbp+57h+hKey]
0x18010873e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180108743  nop
0x180108744  lea     rcx, [rbp+57h+var_58]
0x180108748  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010874d  nop
0x18010874e  mov     rcx, [rdi+38h]
0x180108752  test    rcx, rcx
0x180108755  jz      short loc_18010876D
0x180108757  mov     rdx, [rcx]
0x18010875a  mov     rax, [rdx+20h]
0x18010875e  cmp     rcx, rdi
0x180108761  setnz   dl
0x180108764  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180108769  mov     [rdi+38h], r12
0x18010876d  mov     eax, ebx
0x18010876f  jmp     loc_18010899A
0x180108774  mov     [rbp+57h+cbMaxValueNameLen], r12d
0x180108778  mov     [rbp+57h+cValues], r12d
0x18010877c  mov     [rsp+0F0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180108781  mov     [rsp+0F0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x180108786  mov     [rsp+0F0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x18010878b  lea     rax, [rbp+57h+cbMaxValueNameLen]
0x18010878f  mov     [rsp+0F0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180108794  lea     rax, [rbp+57h+cValues]
0x180108798  mov     [rsp+0F0h+lpcValues], rax; lpcValues
0x18010879d  mov     [rsp+0F0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x1801087a2  mov     [rsp+0F0h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x1801087a7  mov     [rsp+0F0h+phkResult], r12; unsigned int
0x1801087ac  xor     r9d, r9d; lpReserved
0x1801087af  xor     r8d, r8d; lpcchClass
0x1801087b2  xor     edx, edx; lpClass
0x1801087b4  mov     rcx, [rbp+57h+hKey]; hKey
0x1801087b8  call    cs:__imp_RegQueryInfoKeyW
0x1801087be  test    eax, eax
0x1801087c0  jz      short loc_1801087E1
0x1801087c2  mov     rcx, [rbp+5Fh]; this
0x1801087c6  mov     r9d, eax; char *
0x1801087c9  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801087d0  mov     edx, 0C7h; void *
0x1801087d5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801087da  mov     ebx, eax
0x1801087dc  jmp     loc_18010873A
0x1801087e1  cmp     [rbp+57h+cValues], r12d
0x1801087e5  jz      loc_180108965
0x1801087eb  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x1801087ee  inc     eax
0x1801087f0  mov     [rbp+57h+cbMaxValueNameLen], eax
0x1801087f3  mov     ecx, eax
0x1801087f5  mov     eax, 2
0x1801087fa  mul     rcx
0x1801087fd  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180108804  cmovb   rax, rcx
0x180108808  mov     rcx, rax; unsigned __int64
0x18010880b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180108810  mov     r14, rax
0x180108813  mov     [rbp+57h+var_70], rax
0x180108817  mov     ebx, r12d
0x18010881a  cmp     ebx, [rbp+57h+cValues]
0x18010881d  jnb     loc_18010895B
0x180108823  mov     ecx, [rbp+57h+cbMaxValueNameLen]
0x180108826  mov     [rbp+57h+cchValueName], ecx
0x180108829  mov     [rbp+57h+Type], 4
0x180108830  mov     dword ptr [rbp+57h+Data], r12d
0x180108834  mov     [rbp+57h+cbData], 4
0x18010883b  lea     rax, [rbp+57h+cbData]
0x18010883f  mov     [rsp+0F0h+lpcValues], rax; lpcbData
0x180108844  lea     rax, [rbp+57h+Data]
0x180108848  mov     [rsp+0F0h+lpcbMaxClassLen], rax; lpData
0x18010884d  lea     rax, [rbp+57h+Type]
0x180108851  mov     [rsp+0F0h+lpcbMaxSubKeyLen], rax; lpType
0x180108856  mov     [rsp+0F0h+phkResult], r12; unsigned int
0x18010885b  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x18010885f  mov     r8, r14; lpValueName
0x180108862  mov     edx, ebx; dwIndex
0x180108864  mov     rcx, [rbp+57h+hKey]; hKey
0x180108868  call    cs:__imp_RegEnumValueW
0x18010886e  test    eax, eax
0x180108870  jnz     loc_18010890A
0x180108876  cmp     [rbp+57h+Type], 4
0x18010887a  jnz     short loc_1801088D5
0x18010887c  lea     rdx, aMaxperwildcard; "MaxPerWildcardMatchesPerDirectory"
0x180108883  mov     rcx, r14
0x180108886  call    cs:__imp__o__wcsicmp
0x18010888c  test    eax, eax
0x18010888e  jnz     short loc_18010889C
0x180108890  mov     eax, dword ptr [rbp+57h+Data]
0x180108893  mov     [r15+0D8h], eax
0x18010889a  jmp     short loc_1801088D5
0x18010889c  mov     eax, [r15+0B0h]
0x1801088a3  test    eax, eax
0x1801088a5  jz      short loc_1801088B2
0x1801088a7  mov     ecx, dword ptr [rbp+57h+Data]
0x1801088aa  test    ecx, ecx
0x1801088ac  jz      short loc_1801088B2
0x1801088ae  test    ecx, eax
0x1801088b0  jz      short loc_1801088D5
0x1801088b2  mov     [rbp+57h+var_68], r14
0x1801088b6  mov     rcx, [rdi+38h]
0x1801088ba  test    rcx, rcx
0x1801088bd  jz      short loc_180108903
0x1801088bf  mov     rax, [rcx]
0x1801088c2  lea     rdx, [rbp+57h+var_68]
0x1801088c6  mov     rax, [rax+10h]
0x1801088ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801088cf  mov     esi, eax
0x1801088d1  test    eax, eax
0x1801088d3  js      short loc_1801088DC
0x1801088d5  inc     ebx
0x1801088d7  jmp     loc_18010881A
0x1801088dc  mov     rcx, [rbp+5Fh]; this
0x1801088e0  mov     r9d, esi; char *
0x1801088e3  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801088ea  mov     edx, 0E7h; void *
0x1801088ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801088f4  nop
0x1801088f5  lea     rcx, [rbp+57h+var_70]
0x1801088f9  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x1801088fe  jmp     loc_1801086E7
0x180108903  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x180108909  int     3; Trap to Debugger
0x18010890a  mov     rcx, [rbp+5Fh]; this
0x18010890e  mov     r9d, eax; char *
0x180108911  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180108918  mov     edx, 0D3h; void *
0x18010891d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180108922  mov     ebx, eax
0x180108924  lea     rcx, [rbp+57h+var_70]
0x180108928  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18010892d  nop
0x18010892e  lea     rcx, [rbp+57h+hKey]
0x180108932  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180108937  nop
0x180108938  lea     rcx, [rbp+57h+var_58]
0x18010893c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180108941  nop
0x180108942  mov     rcx, [rdi+38h]
0x180108946  test    rcx, rcx
0x180108949  jz      loc_18010876D
0x18010894f  mov     rax, [rcx]
0x180108952  mov     rax, [rax+20h]
0x180108956  jmp     loc_18010875E
0x18010895b  lea     rcx, [rbp+57h+var_70]
0x18010895f  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x180108964  nop
0x180108965  lea     rcx, [rbp+57h+hKey]
0x180108969  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010896e  nop
0x18010896f  lea     rcx, [rbp+57h+var_58]
0x180108973  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180108978  nop
0x180108979  mov     rcx, [rdi+38h]
0x18010897d  test    rcx, rcx
0x180108980  jz      short loc_180108998
0x180108982  cmp     rcx, rdi
0x180108985  mov     rax, [rcx]
0x180108988  setnz   dl
0x18010898b  mov     rax, [rax+20h]
0x18010898f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180108994  mov     [rdi+38h], r12
0x180108998  xor     eax, eax
0x18010899a  mov     rcx, [rbp+57h+var_38]
0x18010899e  xor     rcx, rsp; StackCookie
0x1801089a1  call    __security_check_cookie
0x1801089a6  add     rsp, 0C0h
0x1801089ad  pop     r15
0x1801089af  pop     r14
0x1801089b1  pop     r12
0x1801089b3  pop     rdi
0x1801089b4  pop     rsi
0x1801089b5  pop     rbx
0x1801089b6  pop     rbp
0x1801089b7  retn
```
