# MdmLogCollector::AddAreaEntry(ushort const *,ushort const *,std::function<long (ushort const *)>)

- ea: `0x1801099ac`
- end: `0x180109d47`
- name: `?AddAreaEntry@MdmLogCollector@@AEAAJPEBG0V?$function@$$A6AJPEBG@Z@std@@@Z`
- size: `923`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting`

## callers

- `0x18010a25c`

## callees

- `0x180019080`
- `0x180019594`
- `0x1800e68b0`
- `0x1800e7de8`
- `0x1800ed46c`
- `0x1800ef8c4`
- `0x1800efd9c`
- `0x1800f00e4`
- `0x180105294`
- `0x180109140`
- `0x1801099ac`
- `0x180193010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180109c8b`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180109c8b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180109c08`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180109c08`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180109b2e`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180109b2e`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180109be4`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180109be4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180109a31`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180109a31`

## string_xrefs

- `0x180109a9e`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x180109b45`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x180109c6b`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x180109c9f`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x180109bfe`: `MaxPerWildcardMatchesPerDirectory`

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
      (void *)0xC0,
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
           (void *)0xC6,
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
              break;
            }
            v23 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v22 + 16LL))(v22, v37);
            v10 = v23;
            if ( v23 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xE6,
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
           (void *)0xD2,
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
0x1801099ac  push    rbp
0x1801099ae  push    rbx
0x1801099af  push    rsi
0x1801099b0  push    rdi
0x1801099b1  push    r12
0x1801099b3  push    r14
0x1801099b5  push    r15
0x1801099b7  lea     rbp, [rsp-27h]
0x1801099bc  sub     rsp, 0C0h
0x1801099c3  mov     rax, cs:__security_cookie
0x1801099ca  xor     rax, rsp
0x1801099cd  mov     [rbp+57h+var_38], rax
0x1801099d1  mov     rdi, r9
0x1801099d4  mov     rbx, r8
0x1801099d7  mov     r15, rcx
0x1801099da  mov     [rbp+57h+var_60], r9
0x1801099de  lea     rcx, [rbp+57h+var_58]
0x1801099e2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1801099e7  nop
0x1801099e8  lea     rdx, psz; "\\"
0x1801099ef  lea     rcx, [rbp+57h+var_58]
0x1801099f3  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1801099f8  mov     rdx, rbx
0x1801099fb  lea     rcx, [rbp+57h+var_58]
0x1801099ff  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180109a04  nop
0x180109a05  xor     r12d, r12d
0x180109a08  mov     [rbp+57h+hKey], r12
0x180109a0c  lea     rcx, [rbp+57h+var_58]
0x180109a10  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180109a15  mov     rdx, rax; lpSubKey
0x180109a18  lea     rax, [rbp+57h+hKey]
0x180109a1c  mov     [rsp+0F0h+phkResult], rax; int
0x180109a21  mov     r9d, 20019h; samDesired
0x180109a27  xor     r8d, r8d; ulOptions
0x180109a2a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180109a31  call    cs:__imp_RegOpenKeyExW
0x180109a38  nop     dword ptr [rax+rax+00h]
0x180109a3d  mov     ebx, eax
0x180109a3f  test    eax, eax
0x180109a41  jle     short loc_180109A4C
0x180109a43  movzx   ebx, ax
0x180109a46  or      ebx, 80070000h
0x180109a4c  test    ebx, ebx
0x180109a4e  jns     loc_180109AEA
0x180109a54  mov     esi, 80070002h
0x180109a59  cmp     ebx, esi
0x180109a5b  jnz     short loc_180109A97
0x180109a5d  lea     rcx, [rbp+57h+hKey]
0x180109a61  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180109a66  nop
0x180109a67  lea     rcx, [rbp+57h+var_58]
0x180109a6b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180109a70  nop
0x180109a71  mov     rcx, [rdi+38h]
0x180109a75  test    rcx, rcx
0x180109a78  jz      short loc_180109A90
0x180109a7a  mov     rax, [rcx]
0x180109a7d  cmp     rcx, rdi
0x180109a80  setnz   dl
0x180109a83  mov     rax, [rax+20h]
0x180109a87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109a8c  mov     [rdi+38h], r12
0x180109a90  mov     eax, esi
0x180109a92  jmp     loc_180109D28
0x180109a97  mov     rcx, [rbp+5Fh]; this
0x180109a9b  mov     r9d, ebx; char *
0x180109a9e  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180109aa5  mov     edx, 0C0h; void *
0x180109aaa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180109aaf  nop
0x180109ab0  lea     rcx, [rbp+57h+hKey]
0x180109ab4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180109ab9  nop
0x180109aba  lea     rcx, [rbp+57h+var_58]
0x180109abe  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180109ac3  nop
0x180109ac4  mov     rcx, [rdi+38h]
0x180109ac8  test    rcx, rcx
0x180109acb  jz      short loc_180109AE3
0x180109acd  mov     rdx, [rcx]
0x180109ad0  mov     rax, [rdx+20h]
0x180109ad4  cmp     rcx, rdi
0x180109ad7  setnz   dl
0x180109ada  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109adf  mov     [rdi+38h], r12
0x180109ae3  mov     eax, ebx
0x180109ae5  jmp     loc_180109D28
0x180109aea  mov     [rbp+57h+cbMaxValueNameLen], r12d
0x180109aee  mov     [rbp+57h+cValues], r12d
0x180109af2  mov     [rsp+0F0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180109af7  mov     [rsp+0F0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x180109afc  mov     [rsp+0F0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x180109b01  lea     rax, [rbp+57h+cbMaxValueNameLen]
0x180109b05  mov     [rsp+0F0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180109b0a  lea     rax, [rbp+57h+cValues]
0x180109b0e  mov     [rsp+0F0h+lpcValues], rax; lpcValues
0x180109b13  mov     [rsp+0F0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x180109b18  mov     [rsp+0F0h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x180109b1d  mov     [rsp+0F0h+phkResult], r12; unsigned int
0x180109b22  xor     r9d, r9d; lpReserved
0x180109b25  xor     r8d, r8d; lpcchClass
0x180109b28  xor     edx, edx; lpClass
0x180109b2a  mov     rcx, [rbp+57h+hKey]; hKey
0x180109b2e  call    cs:__imp_RegQueryInfoKeyW
0x180109b35  nop     dword ptr [rax+rax+00h]
0x180109b3a  test    eax, eax
0x180109b3c  jz      short loc_180109B5D
0x180109b3e  mov     rcx, [rbp+5Fh]; this
0x180109b42  mov     r9d, eax; char *
0x180109b45  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180109b4c  mov     edx, 0C6h; void *
0x180109b51  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180109b56  mov     ebx, eax
0x180109b58  jmp     loc_180109AB0
0x180109b5d  cmp     [rbp+57h+cValues], r12d
0x180109b61  jz      loc_180109CF3
0x180109b67  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x180109b6a  inc     eax
0x180109b6c  mov     [rbp+57h+cbMaxValueNameLen], eax
0x180109b6f  mov     ecx, eax
0x180109b71  mov     eax, 2
0x180109b76  mul     rcx
0x180109b79  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180109b80  cmovb   rax, rcx
0x180109b84  mov     rcx, rax; unsigned __int64
0x180109b87  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180109b8c  mov     r14, rax
0x180109b8f  mov     [rbp+57h+var_70], rax
0x180109b93  mov     ebx, r12d
0x180109b96  cmp     ebx, [rbp+57h+cValues]
0x180109b99  jnb     loc_180109CE9
0x180109b9f  mov     ecx, [rbp+57h+cbMaxValueNameLen]
0x180109ba2  mov     [rbp+57h+cchValueName], ecx
0x180109ba5  mov     [rbp+57h+Type], 4
0x180109bac  mov     dword ptr [rbp+57h+Data], r12d
0x180109bb0  mov     [rbp+57h+cbData], 4
0x180109bb7  lea     rax, [rbp+57h+cbData]
0x180109bbb  mov     [rsp+0F0h+lpcValues], rax; lpcbData
0x180109bc0  lea     rax, [rbp+57h+Data]
0x180109bc4  mov     [rsp+0F0h+lpcbMaxClassLen], rax; lpData
0x180109bc9  lea     rax, [rbp+57h+Type]
0x180109bcd  mov     [rsp+0F0h+lpcbMaxSubKeyLen], rax; lpType
0x180109bd2  mov     [rsp+0F0h+phkResult], r12; unsigned int
0x180109bd7  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x180109bdb  mov     r8, r14; lpValueName
0x180109bde  mov     edx, ebx; dwIndex
0x180109be0  mov     rcx, [rbp+57h+hKey]; hKey
0x180109be4  call    cs:__imp_RegEnumValueW
0x180109beb  nop     dword ptr [rax+rax+00h]
0x180109bf0  test    eax, eax
0x180109bf2  jnz     loc_180109C98
0x180109bf8  cmp     [rbp+57h+Type], 4
0x180109bfc  jnz     short loc_180109C5D
0x180109bfe  lea     rdx, aMaxperwildcard; "MaxPerWildcardMatchesPerDirectory"
0x180109c05  mov     rcx, r14
0x180109c08  call    cs:__imp__o__wcsicmp
0x180109c0f  nop     dword ptr [rax+rax+00h]
0x180109c14  test    eax, eax
0x180109c16  jnz     short loc_180109C24
0x180109c18  mov     eax, dword ptr [rbp+57h+Data]
0x180109c1b  mov     [r15+0D8h], eax
0x180109c22  jmp     short loc_180109C5D
0x180109c24  mov     eax, [r15+0B0h]
0x180109c2b  test    eax, eax
0x180109c2d  jz      short loc_180109C3A
0x180109c2f  mov     ecx, dword ptr [rbp+57h+Data]
0x180109c32  test    ecx, ecx
0x180109c34  jz      short loc_180109C3A
0x180109c36  test    ecx, eax
0x180109c38  jz      short loc_180109C5D
0x180109c3a  mov     [rbp+57h+var_68], r14
0x180109c3e  mov     rcx, [rdi+38h]
0x180109c42  test    rcx, rcx
0x180109c45  jz      short loc_180109C8B
0x180109c47  mov     rax, [rcx]
0x180109c4a  lea     rdx, [rbp+57h+var_68]
0x180109c4e  mov     rax, [rax+10h]
0x180109c52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109c57  mov     esi, eax
0x180109c59  test    eax, eax
0x180109c5b  js      short loc_180109C64
0x180109c5d  inc     ebx
0x180109c5f  jmp     loc_180109B96
0x180109c64  mov     rcx, [rbp+5Fh]; this
0x180109c68  mov     r9d, esi; char *
0x180109c6b  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180109c72  mov     edx, 0E6h; void *
0x180109c77  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180109c7c  nop
0x180109c7d  lea     rcx, [rbp+57h+var_70]
0x180109c81  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x180109c86  jmp     loc_180109A5D
0x180109c8b  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x180109c92  nop     dword ptr [rax+rax+00h]
0x180109c97  int     3; Trap to Debugger
0x180109c98  mov     rcx, [rbp+5Fh]; this
0x180109c9c  mov     r9d, eax; char *
0x180109c9f  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180109ca6  mov     edx, 0D2h; void *
0x180109cab  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180109cb0  mov     ebx, eax
0x180109cb2  lea     rcx, [rbp+57h+var_70]
0x180109cb6  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x180109cbb  nop
0x180109cbc  lea     rcx, [rbp+57h+hKey]
0x180109cc0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180109cc5  nop
0x180109cc6  lea     rcx, [rbp+57h+var_58]
0x180109cca  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180109ccf  nop
0x180109cd0  mov     rcx, [rdi+38h]
0x180109cd4  test    rcx, rcx
0x180109cd7  jz      loc_180109AE3
0x180109cdd  mov     rax, [rcx]
0x180109ce0  mov     rax, [rax+20h]
0x180109ce4  jmp     loc_180109AD4
0x180109ce9  lea     rcx, [rbp+57h+var_70]
0x180109ced  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x180109cf2  nop
0x180109cf3  lea     rcx, [rbp+57h+hKey]
0x180109cf7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180109cfc  nop
0x180109cfd  lea     rcx, [rbp+57h+var_58]
0x180109d01  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180109d06  nop
0x180109d07  mov     rcx, [rdi+38h]
0x180109d0b  test    rcx, rcx
0x180109d0e  jz      short loc_180109D26
0x180109d10  cmp     rcx, rdi
0x180109d13  mov     rax, [rcx]
0x180109d16  setnz   dl
0x180109d19  mov     rax, [rax+20h]
0x180109d1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109d22  mov     [rdi+38h], r12
0x180109d26  xor     eax, eax
0x180109d28  mov     rcx, [rbp+57h+var_38]
0x180109d2c  xor     rcx, rsp; StackCookie
0x180109d2f  call    __security_check_cookie
0x180109d34  add     rsp, 0C0h
0x180109d3b  pop     r15
0x180109d3d  pop     r14
0x180109d3f  pop     r12
0x180109d41  pop     rdi
0x180109d42  pop     rsi
0x180109d43  pop     rbx
0x180109d44  pop     rbp
0x180109d45  retn
```
