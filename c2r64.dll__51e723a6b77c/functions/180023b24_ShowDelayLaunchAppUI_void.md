# ShowDelayLaunchAppUI(void)

- ea: `0x180023b24`
- end: `0x180023fb7`
- name: `?ShowDelayLaunchAppUI@@YAXXZ`
- size: `1171`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180019848`

## callees

- `0x1800054e0`
- `0x180007778`
- `0x180007d08`
- `0x180007d40`
- `0x180009488`
- `0x18000adf0`
- `0x18000ae28`
- `0x18000c0a4`
- `0x18000c2dc`
- `0x1800130d0`
- `0x18001b620`
- `0x180023b24`
- `0x180023ff4`
- `0x18002418c`
- `0x1800242f0`
- `0x18002437c`
- `0x180024bd8`
- `0x180024c10`
- `0x180024fdc`
- `0x180025030`
- `0x18003c290`
- `0x18003e690`
- `0x1800473f0`

## import_xrefs

- `KERNEL32!GetCommandLineW` at `0x180023b54`
- `KERNEL32!GetCommandLineW` at `0x180023b54`
- `KERNEL32!GetTickCount64` at `0x180023bf7`
- `KERNEL32!GetTickCount64` at `0x180023bf7`

## pseudocode

```c
// Hidden C++ exception states: #wind=30
void ShowDelayLaunchAppUI(void)
{
  LPWSTR CommandLineW; // rax
  __int64 v1; // r9
  int SubKey; // ebx
  ULONGLONG TickCount64; // rax
  const WCHAR *v4; // rax
  _QWORD *v5; // rax
  __int64 ClientFolder; // rax
  __int128 *v7; // rax
  const WCHAR *v8; // rcx
  unsigned int stats; // eax
  bool v10; // bl
  __int64 v11; // rdx
  __int64 v12; // rcx
  int v13; // edx
  _BYTE v14[32]; // [rsp+0h] [rbp-1E8h] BYREF
  int v15; // [rsp+40h] [rbp-1A8h]
  _QWORD v16[2]; // [rsp+50h] [rbp-198h] BYREF
  LPCWSTR *v17; // [rsp+60h] [rbp-188h]
  const OException *v18; // [rsp+68h] [rbp-180h] BYREF
  __int128 v19; // [rsp+70h] [rbp-178h] BYREF
  __m128i si128; // [rsp+80h] [rbp-168h]
  LPCWSTR lpFileName[3]; // [rsp+90h] [rbp-158h] BYREF
  unsigned __int64 v22; // [rsp+A8h] [rbp-140h]
  std::_Ref_count_base *v23[2]; // [rsp+B0h] [rbp-138h] BYREF
  __int64 v24; // [rsp+C0h] [rbp-128h]
  __int64 v25; // [rsp+C8h] [rbp-120h]
  _QWORD v26[4]; // [rsp+D0h] [rbp-118h] BYREF
  _QWORD v27[4]; // [rsp+F0h] [rbp-F8h] BYREF
  _QWORD v28[4]; // [rsp+110h] [rbp-D8h] BYREF
  _QWORD v29[2]; // [rsp+130h] [rbp-B8h] BYREF
  _BYTE v30[48]; // [rsp+140h] [rbp-A8h] BYREF
  _QWORD v31[3]; // [rsp+170h] [rbp-78h] BYREF
  _BYTE v32[32]; // [rsp+188h] [rbp-60h] BYREF
  _BYTE v33[8]; // [rsp+1A8h] [rbp-40h] BYREF
  _BYTE v34[32]; // [rsp+1B0h] [rbp-38h] BYREF

  v15 = 0;
  CommandLineW = GetCommandLineW();
  std::wstring::wstring(v27, CommandLineW);
  ORegistryKey::ORegistryKey((ORegistryKey *)v29);
  try
  {
    std::wstring::wstring(v23, L"Software\\Microsoft\\Office\\ClickToRun\\DelayLaunchApps");
    LOBYTE(v1) = 1;
    SubKey = ORegistryKey::CreateSubKey(ORegistry::CurrentUser, v29, v23, v1, 1);
    std::wstring::_Tidy_deallocate(v23);
    v16[0] = v23;
    v23[0] = (std::_Ref_count_base *)19937;
    v24 = 0;
    v25 = 15;
    if ( SubKey )
    {
      TickCount64 = GetTickCount64();
      v4 = (const WCHAR *)std::to_wstring(lpFileName, TickCount64);
      ORegistryKey::SetValue((__int64)v29, v4, (const BYTE *)v27, 1);
      std::wstring::~wstring(lpFileName);
    }
  }
  catch ( const OException *v18 )
  {
    LODWORD(v23[0]) = GetLastError();
    LODWORD(v17) = *((_DWORD *)v18 + 129);
    v16[0] = (char *)v18 + 4;
    LogLineFormat<74,wchar_t const *,unsigned int,unsigned long>(
      (_DWORD)v18,
      v13,
      (unsigned int)v14 + 80,
      (unsigned int)v14 + 96,
      (__int64)v23);
    ORegistryKey::~ORegistryKey((ORegistryKey *)v29);
    std::wstring::~wstring(v27);
    return;
  }
  std::wstring::wstring(v28, L"/waittolaunch");
  v16[0] = &v19;
  v19 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v19) = 0;
  std::wstring::wstring(v26, L"OfficeC2RClient.exe");
  v5 = (_QWORD *)C2R::ConfigurationSettings::CurrentConfigurationSettings(v23);
  ClientFolder = C2R::ConfigurationSettings::get_ClientFolder(*v5, lpFileName);
  OPath::Combine(ClientFolder, v26, &v19);
  std::wstring::_Tidy_deallocate(lpFileName);
  v17 = lpFileName;
  lpFileName[0] = (LPCWSTR)19937;
  lpFileName[2] = 0;
  v22 = 15;
  if ( v23[1] )
    std::_Ref_count_base::_Decref(v23[1]);
  *(__m128i *)v23 = _mm_load_si128((const __m128i *)&_xmm);
  std::wstring::_Tidy_deallocate(v26);
  v16[0] = v26;
  v26[0] = 19937;
  v26[2] = 0;
  v26[3] = 15;
  v17 = lpFileName;
  v7 = &v19;
  if ( si128.m128i_i64[1] > 7uLL )
    v7 = (__int128 *)v19;
  v16[0] = v7;
  v16[1] = si128.m128i_i64[0];
  std::wstring::wstring(lpFileName, v16);
  v15 = 0;
  LODWORD(v16[0]) = 0;
  v8 = (const WCHAR *)lpFileName;
  if ( v22 > 7 )
    v8 = lpFileName[0];
  stats = _std_fs_get_stats(v8);
  std::filesystem::file_status::_Refresh(v16, stats, v26);
  if ( LODWORD(v16[0]) )
    v10 = LODWORD(v16[0]) != 1;
  else
    v10 = 0;
  std::wstring::~wstring(lpFileName);
  if ( v10 )
  {
    OProcess::OProcess((OProcess *)v31);
    OProcess::Start(v31, &v19, v28);
    v31[0] = &OProcess::`vftable';
    std::unique_ptr<void *,HandleCloser>::~unique_ptr<void *,HandleCloser>(v34);
    std::unique_ptr<void *,HandleCloser>::~unique_ptr<void *,HandleCloser>(v33);
    std::wstring::~wstring(v32);
    OSynchronization::~OSynchronization((OSynchronization *)v31);
  }
  else
  {
    LogLineFormat<41,std::wstring>(v12, v11, &v19);
  }
  std::wstring::_Tidy_deallocate(&v19);
  v16[0] = &v19;
  *(_QWORD *)&v19 = 19937;
  si128.m128i_i64[0] = 0;
  si128.m128i_i64[1] = 15;
  std::wstring::_Tidy_deallocate(v28);
  v17 = (LPCWSTR *)v28;
  v28[0] = 19937;
  v28[2] = 0;
  v28[3] = 15;
  v29[0] = &ORegistryKey::`vftable';
  ORegistryKey::Clear((ORegistryKey *)v29);
  std::wstring::~wstring(v30);
  v29[0] = &RefCounted::`vftable';
  std::wstring::_Tidy_deallocate(v27);
  v23[0] = (std::_Ref_count_base *)v27;
  v27[0] = 19937;
  v27[2] = 0;
  v27[3] = 15;
}

```

## disassembly

```asm
0x180023b24  mov     [rsp+arg_0], rbx
0x180023b29  mov     [rsp+arg_8], rsi
0x180023b2e  mov     [rsp+arg_10], rdi
0x180023b33  push    r14
0x180023b35  sub     rsp, 1E0h
0x180023b3c  mov     rax, cs:__security_cookie
0x180023b43  xor     rax, rsp
0x180023b46  mov     [rsp+1E8h+var_18], rax
0x180023b4e  xor     edi, edi
0x180023b50  mov     [rsp+1E8h+var_1A8], edi
0x180023b54  call    cs:__imp_GetCommandLineW
0x180023b5a  mov     rdx, rax
0x180023b5d  lea     rcx, [rsp+1E8h+var_F8]
0x180023b65  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180023b6a  nop
0x180023b6b  lea     rcx, [rsp+1E8h+var_B8]; this
0x180023b73  call    ??0ORegistryKey@@QEAA@XZ; ORegistryKey::ORegistryKey(void)
0x180023b78  nop
0x180023b79  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Office\\ClickToRun"...
0x180023b80  lea     rcx, [rsp+1E8h+var_138]
0x180023b88  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180023b8d  nop
0x180023b8e  mov     [rsp+1E8h+var_1C8], 1
0x180023b96  mov     r9b, 1
0x180023b99  lea     r8, [rsp+1E8h+var_138]
0x180023ba1  lea     rdx, [rsp+1E8h+var_B8]
0x180023ba9  lea     rcx, ?CurrentUser@ORegistry@@2VORegistryKey@@A; ORegistryKey ORegistry::CurrentUser
0x180023bb0  call    ?CreateSubKey@ORegistryKey@@QEAAKAEAV1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NW4REGKEY_ACCESS_MODE@ORegistry@@KK@Z; ORegistryKey::CreateSubKey(ORegistryKey &,std::wstring const &,bool,ORegistry::REGKEY_ACCESS_MODE,ulong,ulong)
0x180023bb5  mov     ebx, eax
0x180023bb7  lea     rcx, [rsp+1E8h+var_138]
0x180023bbf  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180023bc4  nop
0x180023bc5  lea     rax, [rsp+1E8h+var_138]
0x180023bcd  mov     [rsp+1E8h+var_198], rax
0x180023bd2  mov     esi, 4DE1h
0x180023bd7  mov     [rsp+1E8h+var_138], rsi
0x180023bdf  mov     [rsp+1E8h+var_128], rdi
0x180023be7  lea     r14d, [rdi+0Fh]
0x180023beb  mov     [rsp+1E8h+var_120], r14
0x180023bf3  test    ebx, ebx
0x180023bf5  jz      short loc_180023C38
0x180023bf7  call    cs:__imp_GetTickCount64
0x180023bfd  mov     rdx, rax
0x180023c00  lea     rcx, [rsp+1E8h+lpFileName]
0x180023c08  call    ?to_wstring@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@_K@Z; std::to_wstring(unsigned __int64)
0x180023c0d  nop
0x180023c0e  mov     r9b, 1
0x180023c11  lea     r8, [rsp+1E8h+var_F8]
0x180023c19  mov     rdx, rax
0x180023c1c  lea     rcx, [rsp+1E8h+var_B8]
0x180023c24  call    ?SetValue@ORegistryKey@@QEBAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0_N@Z; ORegistryKey::SetValue(std::wstring const &,std::wstring const &,bool)
0x180023c29  nop
0x180023c2a  lea     rcx, [rsp+1E8h+lpFileName]; void *
0x180023c32  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023c37  nop
0x180023c38  lea     rdx, aWaittolaunch; "/waittolaunch"
0x180023c3f  lea     rcx, [rsp+1E8h+var_D8]
0x180023c47  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180023c4c  nop
0x180023c4d  lea     rax, [rsp+1E8h+var_178]
0x180023c52  mov     [rsp+1E8h+var_198], rax
0x180023c57  xorps   xmm0, xmm0
0x180023c5a  movups  [rsp+1E8h+var_178], xmm0
0x180023c5f  mov     qword ptr [rsp+1E8h+var_168], rdi
0x180023c67  mov     qword ptr [rsp+1E8h+var_168+8], rdi
0x180023c6f  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180023c77  movdqu  [rsp+1E8h+var_168], xmm0
0x180023c80  mov     word ptr [rsp+1E8h+var_178], di
0x180023c85  lea     rdx, aOfficec2rclien_0; "OfficeC2RClient.exe"
0x180023c8c  lea     rcx, [rsp+1E8h+var_118]
0x180023c94  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180023c99  nop
0x180023c9a  lea     rcx, [rsp+1E8h+var_138]
0x180023ca2  call    ?CurrentConfigurationSettings@ConfigurationSettings@C2R@@SA?AV?$shared_ptr@VConfigurationSettings@C2R@@@std@@XZ; C2R::ConfigurationSettings::CurrentConfigurationSettings(void)
0x180023ca7  nop
0x180023ca8  lea     rdx, [rsp+1E8h+lpFileName]
0x180023cb0  mov     rcx, [rax]
0x180023cb3  call    ?get_ClientFolder@ConfigurationSettings@C2R@@QEAA?BV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; C2R::ConfigurationSettings::get_ClientFolder(void)
0x180023cb8  nop
0x180023cb9  lea     r8, [rsp+1E8h+var_178]
0x180023cbe  lea     rdx, [rsp+1E8h+var_118]
0x180023cc6  mov     rcx, rax
0x180023cc9  call    ?Combine@OPath@@SAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEAV23@@Z; OPath::Combine(std::wstring const &,std::wstring const &,std::wstring &)
0x180023cce  nop
0x180023ccf  lea     rcx, [rsp+1E8h+lpFileName]
0x180023cd7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180023cdc  nop
0x180023cdd  lea     rax, [rsp+1E8h+lpFileName]
0x180023ce5  mov     [rsp+1E8h+var_188], rax
0x180023cea  mov     [rsp+1E8h+lpFileName], rsi
0x180023cf2  mov     [rsp+1E8h+var_148], rdi
0x180023cfa  mov     [rsp+1E8h+var_140], r14
0x180023d02  mov     rcx, [rsp+1E8h+var_138+8]; this
0x180023d0a  test    rcx, rcx
0x180023d0d  jz      short loc_180023D15
0x180023d0f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180023d14  nop
0x180023d15  movdqa  xmm0, cs:__xmm@0000000000004de10000000000004de1
0x180023d1d  movdqu  xmmword ptr [rsp+1E8h+var_138], xmm0
0x180023d26  lea     rcx, [rsp+1E8h+var_118]
0x180023d2e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180023d33  nop
0x180023d34  lea     rax, [rsp+1E8h+var_118]
0x180023d3c  mov     [rsp+1E8h+var_198], rax
0x180023d41  mov     [rsp+1E8h+var_118], rsi
0x180023d49  mov     [rsp+1E8h+var_108], rdi
0x180023d51  mov     [rsp+1E8h+var_100], r14
0x180023d59  lea     rax, [rsp+1E8h+lpFileName]
0x180023d61  mov     [rsp+1E8h+var_188], rax
0x180023d66  lea     rax, [rsp+1E8h+var_178]
0x180023d6b  cmp     qword ptr [rsp+1E8h+var_168+8], 7
0x180023d74  cmova   rax, qword ptr [rsp+1E8h+var_178]
0x180023d7a  mov     [rsp+1E8h+var_198], rax
0x180023d7f  mov     rax, qword ptr [rsp+1E8h+var_168]
0x180023d87  mov     [rsp+1E8h+var_190], rax
0x180023d8c  lea     rdx, [rsp+1E8h+var_198]
0x180023d91  lea     rcx, [rsp+1E8h+lpFileName]
0x180023d99  call    ??$?0V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@1@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(std::wstring_view const &,std::allocator<wchar_t> const &)
0x180023d9e  mov     eax, 2
0x180023da3  mov     [rsp+1E8h+var_1A8], eax
0x180023da7  and     eax, 0FFFFFFFDh
0x180023daa  mov     [rsp+1E8h+var_1A8], eax
0x180023dae  or      eax, 1
0x180023db1  mov     [rsp+1E8h+var_1A8], eax
0x180023db5  and     eax, 0FFFFFFFEh
0x180023db8  mov     [rsp+1E8h+var_1A8], eax
0x180023dbc  mov     dword ptr [rsp+1E8h+var_198], edi
0x180023dc0  lea     rcx, [rsp+1E8h+lpFileName]
0x180023dc8  cmp     [rsp+1E8h+var_140], 7
0x180023dd1  cmova   rcx, [rsp+1E8h+lpFileName]; lpFileName
0x180023dda  or      r9d, 0FFFFFFFFh
0x180023dde  mov     r8d, 3
0x180023de4  lea     rdx, [rsp+1E8h+var_118]
0x180023dec  call    __std_fs_get_stats
0x180023df1  lea     r8, [rsp+1E8h+var_118]
0x180023df9  mov     edx, eax
0x180023dfb  lea     rcx, [rsp+1E8h+var_198]
0x180023e00  call    ?_Refresh@file_status@filesystem@std@@QEAAXW4__std_win_error@@AEBU__std_fs_stats@@@Z; std::filesystem::file_status::_Refresh(__std_win_error,__std_fs_stats const &)
0x180023e05  mov     ecx, dword ptr [rsp+1E8h+var_198]
0x180023e09  test    ecx, ecx
0x180023e0b  jz      short loc_180023E15
0x180023e0d  cmp     ecx, 1
0x180023e10  setnz   bl
0x180023e13  jmp     short loc_180023E18
0x180023e15  mov     bl, dil
0x180023e18  lea     rcx, [rsp+1E8h+lpFileName]; void *
0x180023e20  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023e25  test    bl, bl
0x180023e27  jz      short loc_180023E98
0x180023e29  lea     rcx, [rsp+1E8h+var_78]; this
0x180023e31  call    ??0OProcess@@QEAA@XZ; OProcess::OProcess(void)
0x180023e36  nop
0x180023e37  lea     r8, [rsp+1E8h+var_D8]
0x180023e3f  lea     rdx, [rsp+1E8h+var_178]
0x180023e44  lea     rcx, [rsp+1E8h+var_78]
0x180023e4c  call    ?Start@OProcess@@QEAAKAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0_N1@Z; OProcess::Start(std::wstring const &,std::wstring const &,bool,bool)
0x180023e51  nop
0x180023e52  lea     rax, ??_7OProcess@@6B@; const OProcess::`vftable'
0x180023e59  mov     [rsp+1E8h+var_78], rax
0x180023e61  lea     rcx, [rsp+1E8h+var_38]
0x180023e69  call    ??1?$unique_ptr@PEAXUHandleCloser@@@std@@QEAA@XZ; std::unique_ptr<void *,HandleCloser>::~unique_ptr<void *,HandleCloser>(void)
0x180023e6e  lea     rcx, [rsp+1E8h+var_40]
0x180023e76  call    ??1?$unique_ptr@PEAXUHandleCloser@@@std@@QEAA@XZ; std::unique_ptr<void *,HandleCloser>::~unique_ptr<void *,HandleCloser>(void)
0x180023e7b  lea     rcx, [rsp+1E8h+var_60]; void *
0x180023e83  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023e88  lea     rcx, [rsp+1E8h+var_78]; this
0x180023e90  call    ??1OSynchronization@@UEAA@XZ; OSynchronization::~OSynchronization(void)
0x180023e95  nop
0x180023e96  jmp     short loc_180023EA3
0x180023e98  lea     r8, [rsp+1E8h+var_178]
0x180023e9d  call    ??$LogLineFormat@$0CJ@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@@YAXW4Severity@Logging@Mso@@AEAY0CJ@$$CB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; LogLineFormat<41,std::wstring>(Mso::Logging::Severity,wchar_t const (&)[41],std::wstring const &)
0x180023ea2  nop
0x180023ea3  lea     rcx, [rsp+1E8h+var_178]
0x180023ea8  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180023ead  nop
0x180023eae  lea     rax, [rsp+1E8h+var_178]
0x180023eb3  mov     [rsp+1E8h+var_198], rax
0x180023eb8  mov     qword ptr [rsp+1E8h+var_178], rsi
0x180023ebd  mov     qword ptr [rsp+1E8h+var_168], rdi
0x180023ec5  mov     qword ptr [rsp+1E8h+var_168+8], r14
0x180023ecd  lea     rcx, [rsp+1E8h+var_D8]
0x180023ed5  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180023eda  nop
0x180023edb  lea     rax, [rsp+1E8h+var_D8]
0x180023ee3  mov     [rsp+1E8h+var_188], rax
0x180023ee8  mov     [rsp+1E8h+var_D8], rsi
0x180023ef0  mov     [rsp+1E8h+var_C8], rdi
0x180023ef8  mov     [rsp+1E8h+var_C0], r14
0x180023f00  lea     rax, ??_7ORegistryKey@@6B@; const ORegistryKey::`vftable'
0x180023f07  mov     [rsp+1E8h+var_B8], rax
0x180023f0f  lea     rcx, [rsp+1E8h+var_B8]; this
0x180023f17  call    ?Clear@ORegistryKey@@AEAAXXZ; ORegistryKey::Clear(void)
0x180023f1c  nop
0x180023f1d  lea     rcx, [rsp+1E8h+var_A8]; void *
0x180023f25  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023f2a  nop
0x180023f2b  lea     rax, ??_7RefCounted@@6B@; const RefCounted::`vftable'
0x180023f32  mov     [rsp+1E8h+var_B8], rax
0x180023f3a  lea     rcx, [rsp+1E8h+var_F8]
0x180023f42  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180023f47  nop
0x180023f48  lea     rax, [rsp+1E8h+var_F8]
0x180023f50  mov     [rsp+1E8h+var_138], rax
0x180023f58  mov     [rsp+1E8h+var_F8], rsi
0x180023f60  mov     [rsp+1E8h+var_E8], rdi
0x180023f68  mov     [rsp+1E8h+var_E0], r14
0x180023f70  jmp     short loc_180023F8D
0x180023f72  lea     rcx, [rsp+1E8h+var_B8]; this
0x180023f7a  call    ??1ORegistryKey@@UEAA@XZ; ORegistryKey::~ORegistryKey(void)
0x180023f7f  nop
0x180023f80  lea     rcx, [rsp+1E8h+var_F8]; void *
0x180023f88  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023f8d  mov     rcx, [rsp+1E8h+var_18]
0x180023f95  xor     rcx, rsp; StackCookie
0x180023f98  call    __security_check_cookie
0x180023f9d  lea     r11, [rsp+1E8h+var_8]
0x180023fa5  mov     rbx, [r11+10h]
0x180023fa9  mov     rsi, [r11+18h]
0x180023fad  mov     rdi, [r11+20h]
0x180023fb1  mov     rsp, r11
0x180023fb4  pop     r14
0x180023fb6  retn
```
