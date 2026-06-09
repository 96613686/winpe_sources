# SetupAllAutoLogForArea(Microsoft::WRL::ComPtr<IConfigManager2>,ushort const *,ushort const *,bool,int)

- ea: `0x180005f0c`
- end: `0x1800061f9`
- name: `?SetupAllAutoLogForArea@@YAJV?$ComPtr@UIConfigManager2@@@WRL@Microsoft@@PEBG1_NH@Z`
- size: `749`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64, char, LONG)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180006250`

## callees

- `0x1800017e0`
- `0x180001804`
- `0x180001cdc`
- `0x180003490`
- `0x180003714`
- `0x180003b10`
- `0x180003b88`
- `0x180004f58`
- `0x180005a14`
- `0x180005a38`
- `0x180005f0c`
- `0x1800064dc`
- `0x180007350`
- `0x1800073bc`
- `0x1800076e8`
- `0x180026010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180006046`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180006046`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18000611c`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18000611c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005fb8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005fb8`

## string_xrefs

- `0x180006058`: `onecoreuap\admin\enterprisemgmt\enterprisediagnosticsetw\dll\dmautologging.cpp`
- `0x18000607f`: `onecoreuap\admin\enterprisemgmt\enterprisediagnosticsetw\dll\dmautologging.cpp`
- `0x18000616f`: `onecoreuap\admin\enterprisemgmt\enterprisediagnosticsetw\dll\dmautologging.cpp`
- `0x180006195`: `onecoreuap\admin\enterprisemgmt\enterprisediagnosticsetw\dll\dmautologging.cpp`

## pseudocode

```c
__int64 __fastcall SetupAllAutoLogForArea(__int64 *a1, __int64 a2, __int64 a3, char a4, LONG a5)
{
  const WCHAR *v8; // rdx
  int v9; // edx
  unsigned int v10; // ebx
  int v11; // r8d
  LPCWSTR *v12; // r9
  const char *v13; // r9
  __int64 v14; // rdx
  unsigned int v15; // eax
  unsigned int v16; // ebx
  __int64 v17; // rdx
  unsigned __int64 v18; // rax
  unsigned __int64 v19; // rdx
  void *v20; // rcx
  DWORD i; // ebx
  unsigned int v22; // eax
  void *v23; // rdi
  __int64 v24; // rcx
  int v25; // eax
  unsigned int v26; // edi
  unsigned __int64 v27; // rdx
  unsigned __int64 v28; // rdx
  unsigned int phkResult; // [rsp+20h] [rbp-A1h]
  unsigned int phkResulta; // [rsp+20h] [rbp-A1h]
  int phkResultb; // [rsp+20h] [rbp-A1h]
  DWORD cbMaxValueNameLen; // [rsp+60h] [rbp-61h] BYREF
  DWORD cValues; // [rsp+64h] [rbp-5Dh] BYREF
  void *v35; // [rsp+68h] [rbp-59h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-51h] BYREF
  DWORD cchValueName; // [rsp+78h] [rbp-49h] BYREF
  _QWORD v38[3]; // [rsp+80h] [rbp-41h] BYREF
  char v39; // [rsp+98h] [rbp-29h]
  LPCWSTR lpSubKey[3]; // [rsp+A0h] [rbp-21h] BYREF
  unsigned __int64 v41; // [rsp+B8h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+57h]

  v38[1] = a1;
  std::wstring::wstring(lpSubKey, a3);
  std::_WChar_traits<unsigned short>::length(L"\\");
  std::wstring::_Append<unsigned short>(lpSubKey);
  std::_WChar_traits<unsigned short>::length(a2);
  std::wstring::_Append<unsigned short>(lpSubKey);
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v8 = (const WCHAR *)lpSubKey;
  if ( v41 > 7 )
    v8 = lpSubKey[0];
  v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v8, 0, 0x20019u, &hKey);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v12 = lpSubKey;
    if ( v41 > 7 )
      LODWORD(v12) = lpSubKey[0];
    WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, v11, (_DWORD)v12, v10);
  }
  if ( v10 )
  {
    v13 = (const char *)v10;
    v14 = 260;
LABEL_12:
    v16 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)v14,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisediagnosticsetw\\dll\\dmautologging.cpp",
            v13,
            phkResult);
    goto LABEL_30;
  }
  cbMaxValueNameLen = 0;
  cValues = 0;
  v15 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, 0, 0, 0);
  if ( v15 )
  {
    v13 = (const char *)v15;
    v14 = 266;
    goto LABEL_12;
  }
  if ( !cValues )
  {
    v16 = -2147024883;
    v17 = 267;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisediagnosticsetw\\dll\\dmautologging.cpp",
      (const char *)v16,
      phkResult);
    goto LABEL_30;
  }
  v18 = 2LL * ++cbMaxValueNameLen;
  if ( !is_mul_ok(cbMaxValueNameLen, 2u) )
    v18 = -1;
  v20 = operator new[](v18, (const struct std::nothrow_t *)&std::nothrow);
  v35 = v20;
  if ( !v20 )
  {
    v16 = -2147024882;
    v17 = 270;
    goto LABEL_15;
  }
  v38[2] = &v35;
  v39 = 1;
  for ( i = 0; i < cValues; ++i )
  {
    cchValueName = cbMaxValueNameLen;
    v22 = RegEnumValueW(hKey, i, (LPWSTR)v20, &cchValueName, 0, 0, 0, 0);
    if ( v22 )
    {
      v16 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x119,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisediagnosticsetw\\dll\\dmautologging.cpp",
              (const char *)v22,
              phkResulta);
      operator delete(v35, v28);
      goto LABEL_30;
    }
    v23 = v35;
    v24 = *a1;
    v38[0] = v24;
    if ( v24 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 8LL))(v24);
    v25 = SetupOneAutoLog(v38, a2, (__int64)v23, a4, a5);
    v26 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x11A,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisediagnosticsetw\\dll\\dmautologging.cpp",
        (const char *)(unsigned int)v25,
        phkResultb);
      operator delete(v35, v27);
      v16 = v26;
      goto LABEL_30;
    }
    v20 = v35;
  }
  operator delete(v20, v19);
  v16 = 0;
LABEL_30:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  std::wstring::~wstring(lpSubKey);
  Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(a1);
  return v16;
}

```

## disassembly

```asm
0x180005f0c  push    rbp
0x180005f0e  push    rbx
0x180005f0f  push    rsi
0x180005f10  push    rdi
0x180005f11  push    r12
0x180005f13  push    r13
0x180005f15  push    r14
0x180005f17  push    r15
0x180005f19  lea     rbp, [rsp-17h]
0x180005f1e  sub     rsp, 0D8h
0x180005f25  mov     rax, cs:__security_cookie
0x180005f2c  xor     rax, rsp
0x180005f2f  mov     [rbp+4Fh+var_50], rax
0x180005f33  mov     r12b, r9b
0x180005f36  mov     r15, rdx
0x180005f39  mov     rsi, rcx
0x180005f3c  mov     [rbp+4Fh+var_88], rcx
0x180005f40  mov     rdx, r8
0x180005f43  lea     rcx, [rbp+4Fh+lpSubKey]
0x180005f47  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180005f4c  nop
0x180005f4d  lea     rcx, asc_180029930; "\\"
0x180005f54  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180005f59  mov     r8, rax
0x180005f5c  mov     rdx, rcx
0x180005f5f  lea     rcx, [rbp+4Fh+lpSubKey]; Src
0x180005f63  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180005f68  mov     rcx, r15
0x180005f6b  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180005f70  mov     r8, rax
0x180005f73  mov     rdx, r15
0x180005f76  lea     rcx, [rbp+4Fh+lpSubKey]; Src
0x180005f7a  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180005f7f  xor     r13d, r13d
0x180005f82  mov     [rbp+4Fh+hKey], r13
0x180005f86  xor     edx, edx
0x180005f88  lea     rcx, [rbp+4Fh+hKey]
0x180005f8c  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180005f91  lea     rdx, [rbp+4Fh+lpSubKey]
0x180005f95  cmp     [rbp+4Fh+var_58], 7
0x180005f9a  cmova   rdx, [rbp+4Fh+lpSubKey]; lpSubKey
0x180005f9f  lea     rax, [rbp+4Fh+hKey]
0x180005fa3  mov     [rsp+110h+phkResult], rax; phkResult
0x180005fa8  mov     r9d, 20019h; samDesired
0x180005fae  xor     r8d, r8d; ulOptions
0x180005fb1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180005fb8  call    cs:__imp_RegOpenKeyExW
0x180005fbe  mov     ebx, eax
0x180005fc0  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x180005fc7  mov     rcx, cs:WPP_GLOBAL_Control
0x180005fce  cmp     rcx, rax
0x180005fd1  jz      short loc_180005FF4
0x180005fd3  test    byte ptr [rcx+1Ch], 2
0x180005fd7  jz      short loc_180005FF4
0x180005fd9  lea     r9, [rbp+4Fh+lpSubKey]
0x180005fdd  cmp     [rbp+4Fh+var_58], 7
0x180005fe2  cmova   r9, [rbp+4Fh+lpSubKey]
0x180005fe7  mov     dword ptr [rsp+110h+phkResult], ebx
0x180005feb  mov     rcx, [rcx+10h]
0x180005fef  call    WPP_SF_SD
0x180005ff4  test    ebx, ebx
0x180005ff6  jz      short loc_180006002
0x180005ff8  mov     r9d, ebx
0x180005ffb  mov     edx, 104h
0x180006000  jmp     short loc_180006058
0x180006002  mov     [rbp+4Fh+cbMaxValueNameLen], r13d
0x180006006  mov     [rbp+4Fh+cValues], r13d
0x18000600a  mov     [rsp+110h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18000600f  mov     [rsp+110h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x180006014  mov     [rsp+110h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x180006019  lea     rax, [rbp+4Fh+cbMaxValueNameLen]
0x18000601d  mov     [rsp+110h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180006022  lea     rax, [rbp+4Fh+cValues]
0x180006026  mov     [rsp+110h+lpcValues], rax; lpcValues
0x18000602b  mov     [rsp+110h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x180006030  mov     [rsp+110h+lpcbMaxSubKeyLen], r13; lpcbMaxSubKeyLen
0x180006035  mov     [rsp+110h+phkResult], r13; int
0x18000603a  xor     r9d, r9d; lpReserved
0x18000603d  xor     r8d, r8d; lpcchClass
0x180006040  xor     edx, edx; lpClass
0x180006042  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180006046  call    cs:__imp_RegQueryInfoKeyW
0x18000604c  test    eax, eax
0x18000604e  jz      short loc_18000606F
0x180006050  mov     r9d, eax; char *
0x180006053  mov     edx, 10Ah; void *
0x180006058  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18000605f  mov     rcx, [rbp+57h]; this
0x180006063  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180006068  mov     ebx, eax
0x18000606a  jmp     loc_1800061BB
0x18000606f  cmp     [rbp+4Fh+cValues], r13d
0x180006073  jnz     short loc_180006097
0x180006075  mov     ebx, 8007000Dh
0x18000607a  mov     edx, 10Bh; void *
0x18000607f  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180006086  mov     r9d, ebx; char *
0x180006089  mov     rcx, [rbp+57h]; this
0x18000608d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006092  jmp     loc_1800061BB
0x180006097  mov     ecx, [rbp+4Fh+cbMaxValueNameLen]
0x18000609a  inc     ecx
0x18000609c  mov     [rbp+4Fh+cbMaxValueNameLen], ecx
0x18000609f  mov     eax, 2
0x1800060a4  mul     rcx
0x1800060a7  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800060ae  cmovb   rax, rcx
0x1800060b2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800060b9  mov     rcx, rax; unsigned __int64
0x1800060bc  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800060c1  mov     rcx, rax; void *
0x1800060c4  mov     [rbp+4Fh+var_A8], rax
0x1800060c8  test    rax, rax
0x1800060cb  jnz     short loc_1800060D9
0x1800060cd  mov     ebx, 8007000Eh
0x1800060d2  mov     edx, 10Eh
0x1800060d7  jmp     short loc_18000607F
0x1800060d9  lea     rax, [rbp+4Fh+var_A8]
0x1800060dd  mov     [rbp+4Fh+var_80], rax
0x1800060e1  mov     [rbp+4Fh+var_78], 1
0x1800060e5  mov     ebx, r13d
0x1800060e8  mov     r14d, [rbp+4Fh+arg_20]
0x1800060ec  cmp     ebx, [rbp+4Fh+cValues]
0x1800060ef  jnb     loc_1800061B3
0x1800060f5  mov     eax, [rbp+4Fh+cbMaxValueNameLen]
0x1800060f8  mov     [rbp+4Fh+cchValueName], eax
0x1800060fb  mov     [rsp+110h+lpcValues], r13; lpcbData
0x180006100  mov     [rsp+110h+lpcbMaxClassLen], r13; lpData
0x180006105  mov     [rsp+110h+lpcbMaxSubKeyLen], r13; lpType
0x18000610a  mov     [rsp+110h+phkResult], r13; unsigned int
0x18000610f  lea     r9, [rbp+4Fh+cchValueName]; lpcchValueName
0x180006113  mov     r8, rcx; lpValueName
0x180006116  mov     edx, ebx; dwIndex
0x180006118  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18000611c  call    cs:__imp_RegEnumValueW
0x180006122  test    eax, eax
0x180006124  jnz     short loc_18000618E
0x180006126  mov     rdi, [rbp+4Fh+var_A8]
0x18000612a  mov     rcx, [rsi]
0x18000612d  mov     [rbp+4Fh+var_90], rcx
0x180006131  test    rcx, rcx
0x180006134  jz      short loc_180006143
0x180006136  mov     rax, [rcx]
0x180006139  mov     rax, [rax+8]
0x18000613d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006142  nop
0x180006143  mov     dword ptr [rsp+110h+phkResult], r14d; int
0x180006148  mov     r9b, r12b
0x18000614b  mov     r8, rdi
0x18000614e  mov     rdx, r15
0x180006151  lea     rcx, [rbp+4Fh+var_90]
0x180006155  call    ?SetupOneAutoLog@@YAJV?$ComPtr@UIConfigManager2@@@WRL@Microsoft@@PEBG1_NH@Z; SetupOneAutoLog(Microsoft::WRL::ComPtr<IConfigManager2>,ushort const *,ushort const *,bool,int)
0x18000615a  mov     edi, eax
0x18000615c  test    eax, eax
0x18000615e  js      short loc_180006168
0x180006160  inc     ebx
0x180006162  mov     rcx, [rbp+4Fh+var_A8]
0x180006166  jmp     short loc_1800060EC
0x180006168  mov     rcx, [rbp+57h]; this
0x18000616c  mov     r9d, edi; char *
0x18000616f  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180006176  mov     edx, 11Ah; void *
0x18000617b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006180  nop
0x180006181  mov     rcx, [rbp+4Fh+var_A8]; void *
0x180006185  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000618a  mov     ebx, edi
0x18000618c  jmp     short loc_1800061BB
0x18000618e  mov     rcx, [rbp+57h]; this
0x180006192  mov     r9d, eax; char *
0x180006195  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18000619c  mov     edx, 119h; void *
0x1800061a1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800061a6  mov     ebx, eax
0x1800061a8  mov     rcx, [rbp+4Fh+var_A8]; void *
0x1800061ac  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800061b1  jmp     short loc_1800061BB
0x1800061b3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800061b8  mov     ebx, r13d
0x1800061bb  lea     rcx, [rbp+4Fh+hKey]
0x1800061bf  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800061c4  nop
0x1800061c5  lea     rcx, [rbp+4Fh+lpSubKey]
0x1800061c9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800061ce  nop
0x1800061cf  mov     rcx, rsi
0x1800061d2  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x1800061d7  mov     eax, ebx
0x1800061d9  mov     rcx, [rbp+4Fh+var_50]
0x1800061dd  xor     rcx, rsp; StackCookie
0x1800061e0  call    __security_check_cookie
0x1800061e5  add     rsp, 0D8h
0x1800061ec  pop     r15
0x1800061ee  pop     r14
0x1800061f0  pop     r13
0x1800061f2  pop     r12
0x1800061f4  pop     rdi
0x1800061f5  pop     rsi
0x1800061f6  pop     rbx
0x1800061f7  pop     rbp
0x1800061f8  retn
```
