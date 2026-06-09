# CleanupStaleMachineLanguageListEntries(void)

- ea: `0x14000eac8`
- end: `0x14000ee35`
- name: `?CleanupStaleMachineLanguageListEntries@@YAJXZ`
- size: `877`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14000d8b8`

## callees

- `0x140002190`
- `0x140002d24`
- `0x140003578`
- `0x1400042a4`
- `0x140005020`
- `0x14000513c`
- `0x140007eac`
- `0x140008558`
- `0x14000a914`
- `0x14000e970`
- `0x14000eac8`
- `0x14000f46c`
- `0x14000f8ac`
- `0x14000f8d0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14000eb8a`
- `ADVAPI32!RegCloseKey` at `0x14000ec20`
- `ADVAPI32!RegCloseKey` at `0x14000eceb`
- `ADVAPI32!RegCloseKey` at `0x14000edfa`
- `ADVAPI32!RegCloseKey` at `0x14000eb8a`
- `ADVAPI32!RegCloseKey` at `0x14000ec20`
- `ADVAPI32!RegCloseKey` at `0x14000eceb`
- `ADVAPI32!RegCloseKey` at `0x14000edfa`
- `ADVAPI32!RegOpenKeyExW` at `0x14000eb5f`
- `ADVAPI32!RegOpenKeyExW` at `0x14000eb5f`
- `ADVAPI32!RegDeleteTreeW` at `0x14000edbb`
- `ADVAPI32!RegDeleteTreeW` at `0x14000edbb`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000eb91`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000ec27`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000ecf2`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000ee01`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000eb91`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000ec27`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000ecf2`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000ee01`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14000eb05`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14000eb05`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14000ebdf`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14000ebdf`
- `ext-ms-win-resources-languageoverlay-l1-1-5!EnumerateInstalledLanguages` at `0x14000ecad`
- `ext-ms-win-resources-languageoverlay-l1-1-5!EnumerateInstalledLanguages` at `0x14000ecad`

## pseudocode

```c
__int64 CleanupStaleMachineLanguageListEntries(void)
{
  HRESULT v1; // eax
  unsigned int v2; // ebx
  unsigned int v3; // eax
  unsigned int v4; // r8d
  unsigned int v5; // ebx
  DWORD i; // ebx
  unsigned int v7; // eax
  unsigned int v8; // r8d
  unsigned int v9; // ebx
  __int64 v10; // r8
  int v11; // r9d
  int v12; // eax
  __int64 v13; // rbx
  _DWORD *v14; // rcx
  __int64 v15; // rcx
  __int64 j; // rbx
  __int64 v17; // rdi
  const WCHAR *v18; // rdx
  unsigned int v19; // eax
  void *v20; // rdx
  unsigned int v21; // r8d
  int phkResult; // [rsp+20h] [rbp-168h]
  unsigned int phkResulta; // [rsp+20h] [rbp-168h]
  unsigned int phkResultb; // [rsp+20h] [rbp-168h]
  DWORD cchName; // [rsp+40h] [rbp-148h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-140h] BYREF
  char v27; // [rsp+51h] [rbp-137h]
  __int128 v28; // [rsp+58h] [rbp-130h] BYREF
  __int64 v29; // [rsp+68h] [rbp-120h]
  char v30; // [rsp+70h] [rbp-118h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+78h] [rbp-110h] BYREF
  __int128 v32; // [rsp+88h] [rbp-100h]
  _BYTE Src[40]; // [rsp+98h] [rbp-F0h] BYREF
  WCHAR Name[88]; // [rsp+C0h] [rbp-C8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+0h]

  if ( !(unsigned __int8)IsEnumerateInstalledLanguagesPresent() )
    return 2147500033LL;
  v1 = CoInitializeEx(0, 0);
  v2 = v1;
  if ( v1 >= 0 )
  {
    v27 = 1;
    hKey = 0;
    v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\MUI\\UILanguages", 0, 0xF003Fu, &hKey);
    if ( v3 )
    {
      v5 = wil::details::in1diag3::Return_Win32(retaddr, (void *)0x100, v4, (const char *)v3, phkResulta);
      if ( hKey )
        RegCloseKey(hKey);
      CoUninitialize();
      return v5;
    }
    else
    {
      v28 = 0;
      v29 = 0;
      for ( i = 0; ; ++i )
      {
        cchName = 85;
        v7 = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0);
        if ( v7 == 259 )
          break;
        if ( v7 )
        {
          v9 = wil::details::in1diag3::Return_Win32(retaddr, (void *)0x117, v8, (const char *)v7, phkResultb);
          std::vector<std::wstring>::~vector<std::wstring>(&v28);
          if ( hKey )
            RegCloseKey(hKey);
LABEL_14:
          CoUninitialize();
          return v9;
        }
        *(_OWORD *)lpSubKey = 0;
        v32 = 0;
        v10 = -1;
        do
          ++v10;
        while ( Name[v10] );
        std::wstring::_Construct<1,unsigned short const *>(lpSubKey, Name, v10);
        std::vector<std::wstring>::insert((unsigned int)&v28, (unsigned int)&v30, v28, v11, (__int64)lpSubKey);
        std::wstring::~wstring(lpSubKey);
      }
      v12 = EnumerateInstalledLanguages(&lambda_8c0e91fe9ef6467722af19b13891000b_::_lambda_invoker_cdecl_, &v28);
      v9 = v12;
      if ( v12 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x12E,
          (unsigned int)"shell\\osshell\\cpls\\lpksetup\\utils\\languagepackcleanuputils.cpp",
          (const char *)(unsigned int)v12,
          phkResultb);
        std::vector<std::wstring>::~vector<std::wstring>(&v28);
        if ( hKey )
          RegCloseKey(hKey);
        goto LABEL_14;
      }
      if ( (__int64)(*((_QWORD *)&v28 + 1) - v28) >> 5 )
      {
        v13 = DelimitedStringFromItems<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>>(Src);
        v14 = (_DWORD *)*((_QWORD *)LanguagePackDiskCleanupTraceProvider::Instance() + 1);
        if ( v14 && *v14 )
        {
          LanguagePackDiskCleanupTraceProvider::Instance();
          *(_OWORD *)lpSubKey = *(_OWORD *)v13;
          v32 = *(_OWORD *)(v13 + 16);
          *(_QWORD *)(v13 + 16) = 0;
          *(_QWORD *)(v13 + 24) = 7;
          *(_WORD *)v13 = 0;
          LanguagePackDiskCleanupTraceProvider::LogCleanupActionInfo_(
            v15,
            L"Cleanup stale machine language list entries: ",
            lpSubKey);
        }
        std::wstring::~wstring(Src);
        v17 = *((_QWORD *)&v28 + 1);
        for ( j = v28; j != v17; j += 32 )
        {
          std::wstring::wstring(lpSubKey, j);
          v18 = (const WCHAR *)lpSubKey;
          if ( *((_QWORD *)&v32 + 1) > 7u )
            v18 = lpSubKey[0];
          v19 = RegDeleteTreeW(hKey, v18);
          if ( v19 )
            wil::details::in1diag3::_Log_Win32(retaddr, v20, v21, (const char *)v19, phkResultb);
          std::wstring::~wstring(lpSubKey);
        }
      }
      std::vector<std::wstring>::~vector<std::wstring>(&v28);
      if ( hKey )
        RegCloseKey(hKey);
      CoUninitialize();
      return 0;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF3,
      (unsigned int)"shell\\osshell\\cpls\\lpksetup\\utils\\languagepackcleanuputils.cpp",
      (const char *)(unsigned int)v1,
      phkResult);
    return v2;
  }
}

```

## disassembly

```asm
0x14000eac8  mov     [rsp+arg_0], rbx
0x14000eacd  mov     [rsp+arg_8], rsi
0x14000ead2  push    rdi
0x14000ead3  sub     rsp, 180h
0x14000eada  mov     rax, cs:__security_cookie
0x14000eae1  xor     rax, rsp
0x14000eae4  mov     [rsp+188h+var_18], rax
0x14000eaec  call    IsEnumerateInstalledLanguagesPresent
0x14000eaf1  xor     esi, esi
0x14000eaf3  test    al, al
0x14000eaf5  jnz     short loc_14000EB01
0x14000eaf7  mov     eax, 80004001h
0x14000eafc  jmp     loc_14000EE0F
0x14000eb01  xor     edx, edx; dwCoInit
0x14000eb03  xor     ecx, ecx; pvReserved
0x14000eb05  call    cs:__imp_CoInitializeEx
0x14000eb0b  mov     ebx, eax
0x14000eb0d  test    eax, eax
0x14000eb0f  jns     short loc_14000EB34
0x14000eb11  mov     rcx, [rsp+188h]; this
0x14000eb19  mov     r9d, eax; char *
0x14000eb1c  lea     r8, aShellOsshellCp; "shell\\osshell\\cpls\\lpksetup\\utils\\"...
0x14000eb23  mov     edx, 0F3h; void *
0x14000eb28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000eb2d  mov     eax, ebx
0x14000eb2f  jmp     loc_14000EE0F
0x14000eb34  mov     [rsp+188h+var_137], 1
0x14000eb39  mov     [rsp+188h+hKey], rsi
0x14000eb3e  lea     rax, [rsp+188h+hKey]
0x14000eb43  mov     [rsp+188h+phkResult], rax; unsigned int
0x14000eb48  mov     r9d, 0F003Fh; samDesired
0x14000eb4e  xor     r8d, r8d; ulOptions
0x14000eb51  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\MUI"...
0x14000eb58  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000eb5f  call    cs:__imp_RegOpenKeyExW
0x14000eb65  test    eax, eax
0x14000eb67  jz      short loc_14000EB9E
0x14000eb69  mov     rcx, [rsp+188h]; this
0x14000eb71  mov     r9d, eax; char *
0x14000eb74  mov     edx, 100h; void *
0x14000eb79  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14000eb7e  mov     ebx, eax
0x14000eb80  mov     rcx, [rsp+188h+hKey]; hKey
0x14000eb85  test    rcx, rcx
0x14000eb88  jz      short loc_14000EB91
0x14000eb8a  call    cs:__imp_RegCloseKey
0x14000eb90  nop
0x14000eb91  call    cs:__imp_CoUninitialize
0x14000eb97  mov     eax, ebx
0x14000eb99  jmp     loc_14000EE0F
0x14000eb9e  xorps   xmm0, xmm0
0x14000eba1  movdqu  [rsp+188h+var_130], xmm0
0x14000eba7  mov     [rsp+188h+var_120], rsi
0x14000ebac  mov     ebx, esi
0x14000ebae  mov     edi, 55h ; 'U'
0x14000ebb3  mov     [rsp+188h+cchName], edi
0x14000ebb7  mov     [rsp+188h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x14000ebbc  mov     [rsp+188h+lpcchClass], rsi; lpcchClass
0x14000ebc1  mov     [rsp+188h+lpClass], rsi; lpClass
0x14000ebc6  mov     [rsp+188h+phkResult], rsi; unsigned int
0x14000ebcb  lea     r9, [rsp+188h+cchName]; lpcchName
0x14000ebd0  lea     r8, [rsp+188h+Name]; lpName
0x14000ebd8  mov     edx, ebx; dwIndex
0x14000ebda  mov     rcx, [rsp+188h+hKey]; hKey
0x14000ebdf  call    cs:__imp_RegEnumKeyExW
0x14000ebe5  cmp     eax, 103h
0x14000ebea  jz      loc_14000ECA1
0x14000ebf0  test    eax, eax
0x14000ebf2  jz      short loc_14000EC34
0x14000ebf4  mov     rcx, [rsp+188h]; this
0x14000ebfc  mov     r9d, eax; char *
0x14000ebff  mov     edx, 117h; void *
0x14000ec04  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14000ec09  mov     ebx, eax
0x14000ec0b  lea     rcx, [rsp+188h+var_130]
0x14000ec10  call    ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x14000ec15  nop
0x14000ec16  mov     rcx, [rsp+188h+hKey]; hKey
0x14000ec1b  test    rcx, rcx
0x14000ec1e  jz      short loc_14000EC27
0x14000ec20  call    cs:__imp_RegCloseKey
0x14000ec26  nop
0x14000ec27  call    cs:__imp_CoUninitialize
0x14000ec2d  mov     eax, ebx
0x14000ec2f  jmp     loc_14000EE0F
0x14000ec34  xorps   xmm0, xmm0
0x14000ec37  movups  xmmword ptr [rsp+188h+lpSubKey], xmm0
0x14000ec3c  xorps   xmm1, xmm1
0x14000ec3f  movdqu  [rsp+188h+var_100], xmm1
0x14000ec48  lea     rax, [rsp+188h+Name]
0x14000ec50  or      r8, 0FFFFFFFFFFFFFFFFh
0x14000ec54  inc     r8
0x14000ec57  cmp     [rax+r8*2], si
0x14000ec5c  jnz     short loc_14000EC54
0x14000ec5e  lea     rdx, [rsp+188h+Name]
0x14000ec66  lea     rcx, [rsp+188h+lpSubKey]
0x14000ec6b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14000ec70  nop
0x14000ec71  lea     rax, [rsp+188h+lpSubKey]
0x14000ec76  mov     [rsp+188h+phkResult], rax
0x14000ec7b  mov     r8, qword ptr [rsp+188h+var_130]
0x14000ec80  lea     rdx, [rsp+188h+var_118]
0x14000ec85  lea     rcx, [rsp+188h+var_130]
0x14000ec8a  call    ?insert@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@2@_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::insert(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,unsigned __int64,std::wstring const &)
0x14000ec8f  nop
0x14000ec90  lea     rcx, [rsp+188h+lpSubKey]
0x14000ec95  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000ec9a  inc     ebx
0x14000ec9c  jmp     loc_14000EBB3
0x14000eca1  lea     rdx, [rsp+188h+var_130]
0x14000eca6  lea     rcx, _lambda_8c0e91fe9ef6467722af19b13891000b____lambda_invoker_cdecl_
0x14000ecad  call    cs:__imp_EnumerateInstalledLanguages
0x14000ecb3  mov     ebx, eax
0x14000ecb5  test    eax, eax
0x14000ecb7  jns     short loc_14000ECFF
0x14000ecb9  mov     rcx, [rsp+188h]; this
0x14000ecc1  mov     r9d, eax; char *
0x14000ecc4  lea     r8, aShellOsshellCp; "shell\\osshell\\cpls\\lpksetup\\utils\\"...
0x14000eccb  mov     edx, 12Eh; void *
0x14000ecd0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000ecd5  nop
0x14000ecd6  lea     rcx, [rsp+188h+var_130]
0x14000ecdb  call    ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x14000ece0  nop
0x14000ece1  mov     rcx, [rsp+188h+hKey]; hKey
0x14000ece6  test    rcx, rcx
0x14000ece9  jz      short loc_14000ECF2
0x14000eceb  call    cs:__imp_RegCloseKey
0x14000ecf1  nop
0x14000ecf2  call    cs:__imp_CoUninitialize
0x14000ecf8  mov     eax, ebx
0x14000ecfa  jmp     loc_14000EE0F
0x14000ecff  mov     r8, qword ptr [rsp+188h+var_130+8]
0x14000ed04  mov     rax, r8
0x14000ed07  mov     rdx, qword ptr [rsp+188h+var_130]
0x14000ed0c  sub     rax, rdx
0x14000ed0f  sar     rax, 5
0x14000ed13  test    rax, rax
0x14000ed16  jz      loc_14000EDE5
0x14000ed1c  lea     rcx, [rsp+188h+Src]; Src
0x14000ed24  call    ??$DelimitedStringFromItems@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@1@0G@Z; DelimitedStringFromItems<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,ushort)
0x14000ed29  mov     rbx, rax
0x14000ed2c  call    ?Instance@LanguagePackDiskCleanupTraceProvider@@KAPEAV1@XZ; LanguagePackDiskCleanupTraceProvider::Instance(void)
0x14000ed31  mov     rcx, [rax+8]
0x14000ed35  test    rcx, rcx
0x14000ed38  jz      short loc_14000ED79
0x14000ed3a  mov     ecx, [rcx]
0x14000ed3c  test    ecx, ecx
0x14000ed3e  jz      short loc_14000ED79
0x14000ed40  call    ?Instance@LanguagePackDiskCleanupTraceProvider@@KAPEAV1@XZ; LanguagePackDiskCleanupTraceProvider::Instance(void)
0x14000ed45  movups  xmm0, xmmword ptr [rbx]
0x14000ed48  movups  xmmword ptr [rsp+188h+lpSubKey], xmm0
0x14000ed4d  movups  xmm1, xmmword ptr [rbx+10h]
0x14000ed51  movups  [rsp+188h+var_100], xmm1
0x14000ed59  mov     [rbx+10h], rsi
0x14000ed5d  mov     qword ptr [rbx+18h], 7
0x14000ed65  mov     [rbx], si
0x14000ed68  lea     r8, [rsp+188h+lpSubKey]
0x14000ed6d  lea     rdx, aCleanupStaleMa; "Cleanup stale machine language list ent"...
0x14000ed74  call    ?LogCleanupActionInfo_@LanguagePackDiskCleanupTraceProvider@@QEAAXPEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; LanguagePackDiskCleanupTraceProvider::LogCleanupActionInfo_(ushort const *,std::wstring)
0x14000ed79  lea     rcx, [rsp+188h+Src]
0x14000ed81  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000ed86  mov     rbx, qword ptr [rsp+188h+var_130]
0x14000ed8b  mov     rdi, qword ptr [rsp+188h+var_130+8]
0x14000ed90  cmp     rbx, rdi
0x14000ed93  jz      short loc_14000EDE5
0x14000ed95  mov     rdx, rbx
0x14000ed98  lea     rcx, [rsp+188h+lpSubKey]
0x14000ed9d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14000eda2  lea     rdx, [rsp+188h+lpSubKey]
0x14000eda7  cmp     qword ptr [rsp+188h+var_100+8], 7
0x14000edb0  cmova   rdx, [rsp+188h+lpSubKey]; lpSubKey
0x14000edb6  mov     rcx, [rsp+188h+hKey]; hKey
0x14000edbb  call    cs:__imp_RegDeleteTreeW
0x14000edc1  test    eax, eax
0x14000edc3  jz      short loc_14000EDD5
0x14000edc5  mov     rcx, [rsp+188h]; this
0x14000edcd  mov     r9d, eax; char *
0x14000edd0  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x14000edd5  lea     rcx, [rsp+188h+lpSubKey]
0x14000edda  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000eddf  add     rbx, 20h ; ' '
0x14000ede3  jmp     short loc_14000ED90
0x14000ede5  lea     rcx, [rsp+188h+var_130]
0x14000edea  call    ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x14000edef  nop
0x14000edf0  mov     rcx, [rsp+188h+hKey]; hKey
0x14000edf5  test    rcx, rcx
0x14000edf8  jz      short loc_14000EE01
0x14000edfa  call    cs:__imp_RegCloseKey
0x14000ee00  nop
0x14000ee01  call    cs:__imp_CoUninitialize
0x14000ee07  xor     eax, eax
0x14000ee09  jmp     short loc_14000EE0F
0x14000ee0b  mov     eax, [rsp+188h+cchName]
0x14000ee0f  mov     rcx, [rsp+188h+var_18]
0x14000ee17  xor     rcx, rsp; StackCookie
0x14000ee1a  call    __security_check_cookie
0x14000ee1f  lea     r11, [rsp+188h+var_8]
0x14000ee27  mov     rbx, [r11+10h]
0x14000ee2b  mov     rsi, [r11+18h]
0x14000ee2f  mov     rsp, r11
0x14000ee32  pop     rdi
0x14000ee33  retn
```
