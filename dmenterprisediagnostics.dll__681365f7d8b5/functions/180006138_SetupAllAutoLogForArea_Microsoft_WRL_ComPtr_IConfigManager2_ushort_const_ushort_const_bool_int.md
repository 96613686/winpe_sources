# SetupAllAutoLogForArea(Microsoft::WRL::ComPtr<IConfigManager2>,ushort const *,ushort const *,bool,int)

- ea: `0x180006138`
- end: `0x18000643b`
- name: `?SetupAllAutoLogForArea@@YAJV?$ComPtr@UIConfigManager2@@@WRL@Microsoft@@PEBG1_NH@Z`
- size: `771`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800064a0`

## callees

- `0x180001800`
- `0x180001824`
- `0x180001cfc`
- `0x1800034e4`
- `0x180003768`
- `0x180003b14`
- `0x180003b94`
- `0x1800050e0`
- `0x180005c14`
- `0x180005c3c`
- `0x180006138`
- `0x180006730`
- `0x180007618`
- `0x18000768c`
- `0x180007a14`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180006278`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180006278`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180006354`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180006354`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800061e4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800061e4`

## string_xrefs

- `0x180006290`: `onecoreuap\admin\enterprisemgmt\enterprisediagnosticsetw\dll\dmautologging.cpp`
- `0x1800062b7`: `onecoreuap\admin\enterprisemgmt\enterprisediagnosticsetw\dll\dmautologging.cpp`
- `0x1800063b0`: `onecoreuap\admin\enterprisemgmt\enterprisediagnosticsetw\dll\dmautologging.cpp`
- `0x1800063d6`: `onecoreuap\admin\enterprisemgmt\enterprisediagnosticsetw\dll\dmautologging.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SetupAllAutoLogForArea(__int64 *a1, __int64 a2, __int64 a3, char a4, int a5)
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
  int v23; // r9d
  int v24; // edi
  __int64 v25; // rcx
  int v26; // eax
  unsigned int v27; // edi
  unsigned __int64 v28; // rdx
  unsigned __int64 v29; // rdx
  unsigned int phkResult; // [rsp+20h] [rbp-A1h]
  unsigned int phkResulta; // [rsp+20h] [rbp-A1h]
  int phkResultb; // [rsp+20h] [rbp-A1h]
  DWORD cbMaxValueNameLen; // [rsp+60h] [rbp-61h] BYREF
  DWORD cValues; // [rsp+64h] [rbp-5Dh] BYREF
  void *v36; // [rsp+68h] [rbp-59h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-51h] BYREF
  DWORD cchValueName; // [rsp+78h] [rbp-49h] BYREF
  _QWORD v39[3]; // [rsp+80h] [rbp-41h] BYREF
  char v40; // [rsp+98h] [rbp-29h]
  LPCWSTR lpSubKey[3]; // [rsp+A0h] [rbp-21h] BYREF
  unsigned __int64 v42; // [rsp+B8h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+57h]

  v39[1] = a1;
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
  if ( v42 > 7 )
    v8 = lpSubKey[0];
  v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v8, 0, 0x20019u, &hKey);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v12 = lpSubKey;
    if ( v42 > 7 )
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
  v36 = v20;
  if ( !v20 )
  {
    v16 = -2147024882;
    v17 = 270;
    goto LABEL_15;
  }
  v39[2] = &v36;
  v40 = 1;
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
      operator delete(v36, v29);
      goto LABEL_30;
    }
    v24 = (int)v36;
    v25 = *a1;
    v39[0] = v25;
    if ( v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 8LL))(v25);
    LOBYTE(v23) = a4;
    v26 = SetupOneAutoLog((unsigned int)v39, a2, v24, v23, a5);
    v27 = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x11A,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisediagnosticsetw\\dll\\dmautologging.cpp",
        (const char *)(unsigned int)v26,
        phkResultb);
      operator delete(v36, v28);
      v16 = v27;
      goto LABEL_30;
    }
    v20 = v36;
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
0x180006138  push    rbp
0x18000613a  push    rbx
0x18000613b  push    rsi
0x18000613c  push    rdi
0x18000613d  push    r12
0x18000613f  push    r13
0x180006141  push    r14
0x180006143  push    r15
0x180006145  lea     rbp, [rsp-17h]
0x18000614a  sub     rsp, 0D8h
0x180006151  mov     rax, cs:__security_cookie
0x180006158  xor     rax, rsp
0x18000615b  mov     [rbp+4Fh+var_50], rax
0x18000615f  mov     r12b, r9b
0x180006162  mov     r15, rdx
0x180006165  mov     rsi, rcx
0x180006168  mov     [rbp+4Fh+var_88], rcx
0x18000616c  mov     rdx, r8
0x18000616f  lea     rcx, [rbp+4Fh+lpSubKey]
0x180006173  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180006178  nop
0x180006179  lea     rcx, asc_18002A930; "\\"
0x180006180  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180006185  mov     r8, rax
0x180006188  mov     rdx, rcx
0x18000618b  lea     rcx, [rbp+4Fh+lpSubKey]; Src
0x18000618f  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180006194  mov     rcx, r15
0x180006197  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18000619c  mov     r8, rax
0x18000619f  mov     rdx, r15
0x1800061a2  lea     rcx, [rbp+4Fh+lpSubKey]; Src
0x1800061a6  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800061ab  xor     r13d, r13d
0x1800061ae  mov     [rbp+4Fh+hKey], r13
0x1800061b2  xor     edx, edx
0x1800061b4  lea     rcx, [rbp+4Fh+hKey]
0x1800061b8  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800061bd  lea     rdx, [rbp+4Fh+lpSubKey]
0x1800061c1  cmp     [rbp+4Fh+var_58], 7
0x1800061c6  cmova   rdx, [rbp+4Fh+lpSubKey]; lpSubKey
0x1800061cb  lea     rax, [rbp+4Fh+hKey]
0x1800061cf  mov     [rsp+110h+phkResult], rax; phkResult
0x1800061d4  mov     r9d, 20019h; samDesired
0x1800061da  xor     r8d, r8d; ulOptions
0x1800061dd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800061e4  call    cs:__imp_RegOpenKeyExW
0x1800061eb  nop     dword ptr [rax+rax+00h]
0x1800061f0  mov     ebx, eax
0x1800061f2  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x1800061f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180006200  cmp     rcx, rax
0x180006203  jz      short loc_180006226
0x180006205  test    byte ptr [rcx+1Ch], 2
0x180006209  jz      short loc_180006226
0x18000620b  lea     r9, [rbp+4Fh+lpSubKey]
0x18000620f  cmp     [rbp+4Fh+var_58], 7
0x180006214  cmova   r9, [rbp+4Fh+lpSubKey]
0x180006219  mov     dword ptr [rsp+110h+phkResult], ebx
0x18000621d  mov     rcx, [rcx+10h]
0x180006221  call    WPP_SF_SD
0x180006226  test    ebx, ebx
0x180006228  jz      short loc_180006234
0x18000622a  mov     r9d, ebx
0x18000622d  mov     edx, 104h
0x180006232  jmp     short loc_180006290
0x180006234  mov     [rbp+4Fh+cbMaxValueNameLen], r13d
0x180006238  mov     [rbp+4Fh+cValues], r13d
0x18000623c  mov     [rsp+110h+lpftLastWriteTime], r13; lpftLastWriteTime
0x180006241  mov     [rsp+110h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x180006246  mov     [rsp+110h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x18000624b  lea     rax, [rbp+4Fh+cbMaxValueNameLen]
0x18000624f  mov     [rsp+110h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180006254  lea     rax, [rbp+4Fh+cValues]
0x180006258  mov     [rsp+110h+lpcValues], rax; lpcValues
0x18000625d  mov     [rsp+110h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x180006262  mov     [rsp+110h+lpcbMaxSubKeyLen], r13; lpcbMaxSubKeyLen
0x180006267  mov     [rsp+110h+phkResult], r13; int
0x18000626c  xor     r9d, r9d; lpReserved
0x18000626f  xor     r8d, r8d; lpcchClass
0x180006272  xor     edx, edx; lpClass
0x180006274  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180006278  call    cs:__imp_RegQueryInfoKeyW
0x18000627f  nop     dword ptr [rax+rax+00h]
0x180006284  test    eax, eax
0x180006286  jz      short loc_1800062A7
0x180006288  mov     r9d, eax; char *
0x18000628b  mov     edx, 10Ah; void *
0x180006290  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180006297  mov     rcx, [rbp+57h]; this
0x18000629b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800062a0  mov     ebx, eax
0x1800062a2  jmp     loc_1800063FC
0x1800062a7  cmp     [rbp+4Fh+cValues], r13d
0x1800062ab  jnz     short loc_1800062CF
0x1800062ad  mov     ebx, 8007000Dh
0x1800062b2  mov     edx, 10Bh; void *
0x1800062b7  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800062be  mov     r9d, ebx; char *
0x1800062c1  mov     rcx, [rbp+57h]; this
0x1800062c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800062ca  jmp     loc_1800063FC
0x1800062cf  mov     ecx, [rbp+4Fh+cbMaxValueNameLen]
0x1800062d2  inc     ecx
0x1800062d4  mov     [rbp+4Fh+cbMaxValueNameLen], ecx
0x1800062d7  mov     eax, 2
0x1800062dc  mul     rcx
0x1800062df  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800062e6  cmovb   rax, rcx
0x1800062ea  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800062f1  mov     rcx, rax; unsigned __int64
0x1800062f4  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800062f9  mov     rcx, rax; void *
0x1800062fc  mov     [rbp+4Fh+var_A8], rax
0x180006300  test    rax, rax
0x180006303  jnz     short loc_180006311
0x180006305  mov     ebx, 8007000Eh
0x18000630a  mov     edx, 10Eh
0x18000630f  jmp     short loc_1800062B7
0x180006311  lea     rax, [rbp+4Fh+var_A8]
0x180006315  mov     [rbp+4Fh+var_80], rax
0x180006319  mov     [rbp+4Fh+var_78], 1
0x18000631d  mov     ebx, r13d
0x180006320  mov     r14d, [rbp+4Fh+arg_20]
0x180006324  cmp     ebx, [rbp+4Fh+cValues]
0x180006327  jnb     loc_1800063F4
0x18000632d  mov     eax, [rbp+4Fh+cbMaxValueNameLen]
0x180006330  mov     [rbp+4Fh+cchValueName], eax
0x180006333  mov     [rsp+110h+lpcValues], r13; lpcbData
0x180006338  mov     [rsp+110h+lpcbMaxClassLen], r13; lpData
0x18000633d  mov     [rsp+110h+lpcbMaxSubKeyLen], r13; lpType
0x180006342  mov     [rsp+110h+phkResult], r13; unsigned int
0x180006347  lea     r9, [rbp+4Fh+cchValueName]; lpcchValueName
0x18000634b  mov     r8, rcx; lpValueName
0x18000634e  mov     edx, ebx; dwIndex
0x180006350  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180006354  call    cs:__imp_RegEnumValueW
0x18000635b  nop     dword ptr [rax+rax+00h]
0x180006360  test    eax, eax
0x180006362  jnz     short loc_1800063CF
0x180006364  mov     rdi, [rbp+4Fh+var_A8]
0x180006368  mov     rcx, [rsi]
0x18000636b  mov     [rbp+4Fh+var_90], rcx
0x18000636f  test    rcx, rcx
0x180006372  jz      short loc_180006381
0x180006374  mov     rax, [rcx]
0x180006377  mov     rax, [rax+8]
0x18000637b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006380  nop
0x180006381  mov     dword ptr [rsp+110h+phkResult], r14d; int
0x180006386  mov     r9b, r12b
0x180006389  mov     r8, rdi
0x18000638c  mov     rdx, r15
0x18000638f  lea     rcx, [rbp+4Fh+var_90]
0x180006393  call    ?SetupOneAutoLog@@YAJV?$ComPtr@UIConfigManager2@@@WRL@Microsoft@@PEBG1_NH@Z; SetupOneAutoLog(Microsoft::WRL::ComPtr<IConfigManager2>,ushort const *,ushort const *,bool,int)
0x180006398  mov     edi, eax
0x18000639a  test    eax, eax
0x18000639c  js      short loc_1800063A9
0x18000639e  inc     ebx
0x1800063a0  mov     rcx, [rbp+4Fh+var_A8]
0x1800063a4  jmp     loc_180006324
0x1800063a9  mov     rcx, [rbp+57h]; this
0x1800063ad  mov     r9d, edi; char *
0x1800063b0  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800063b7  mov     edx, 11Ah; void *
0x1800063bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800063c1  nop
0x1800063c2  mov     rcx, [rbp+4Fh+var_A8]; void *
0x1800063c6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800063cb  mov     ebx, edi
0x1800063cd  jmp     short loc_1800063FC
0x1800063cf  mov     rcx, [rbp+57h]; this
0x1800063d3  mov     r9d, eax; char *
0x1800063d6  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800063dd  mov     edx, 119h; void *
0x1800063e2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800063e7  mov     ebx, eax
0x1800063e9  mov     rcx, [rbp+4Fh+var_A8]; void *
0x1800063ed  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800063f2  jmp     short loc_1800063FC
0x1800063f4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800063f9  mov     ebx, r13d
0x1800063fc  lea     rcx, [rbp+4Fh+hKey]
0x180006400  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180006405  nop
0x180006406  lea     rcx, [rbp+4Fh+lpSubKey]
0x18000640a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000640f  nop
0x180006410  mov     rcx, rsi
0x180006413  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x180006418  mov     eax, ebx
0x18000641a  mov     rcx, [rbp+4Fh+var_50]
0x18000641e  xor     rcx, rsp; StackCookie
0x180006421  call    __security_check_cookie
0x180006426  add     rsp, 0D8h
0x18000642d  pop     r15
0x18000642f  pop     r14
0x180006431  pop     r13
0x180006433  pop     r12
0x180006435  pop     rdi
0x180006436  pop     rsi
0x180006437  pop     rbx
0x180006438  pop     rbp
0x180006439  retn
```
