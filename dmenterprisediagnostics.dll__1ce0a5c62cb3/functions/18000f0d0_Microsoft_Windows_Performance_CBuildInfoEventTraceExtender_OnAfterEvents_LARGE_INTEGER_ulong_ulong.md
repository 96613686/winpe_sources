# Microsoft::Windows::Performance::CBuildInfoEventTraceExtender::OnAfterEvents(_LARGE_INTEGER,ulong,ulong)

- ea: `0x18000f0d0`
- end: `0x18000f569`
- name: `?OnAfterEvents@CBuildInfoEventTraceExtender@Performance@Windows@Microsoft@@UEAAJT_LARGE_INTEGER@@KK@Z`
- size: `1177`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CBuildInfoEventTraceExtender *__hidden this, union _LARGE_INTEGER, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800017e0`
- `0x1800023c0`
- `0x180003714`
- `0x180003b10`
- `0x18000b1e0`
- `0x18000eee4`
- `0x18000efbc`
- `0x18000f0d0`
- `0x18000f570`
- `0x18000f5c8`
- `0x18000f638`
- `0x180026010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__gmtime64` at `0x18000f1a4`
- `api-ms-win-crt-private-l1-1-0!_o__gmtime64` at `0x18000f1a4`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x18000f2ee`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x18000f2ee`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000f33a`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000f366`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000f33a`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000f366`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f196`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f1b2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f196`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f1b2`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18000f2fd`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18000f2fd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000f41d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000f41d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f432`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f432`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000f217`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000f217`

## string_xrefs

- `0x18000f410`: `ntdll.dll`
- `0x18000f173`: `InstallDate`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CBuildInfoEventTraceExtender::OnAfterEvents(
        Microsoft::Windows::Performance::CBuildInfoEventTraceExtender *this,
        union _LARGE_INTEGER a2,
        unsigned int a3,
        unsigned int a4)
{
  unsigned int v4; // r14d
  unsigned int v7; // r15d
  unsigned __int16 *v8; // rdi
  WORD *v9; // rdi
  WORD v10; // dx
  WORD v11; // r11
  WORD v12; // ax
  WORD v13; // r10
  WORD v14; // r9
  WORD v15; // r8
  BOOL v16; // eax
  struct _FILETIME v17; // rcx
  unsigned int v18; // esi
  SYSTEMTIME *p_SystemTime; // rcx
  __int64 v20; // rax
  __int64 v21; // rsi
  SYSTEMTIME *v22; // rcx
  __int64 v23; // r14
  size_t v24; // rax
  size_t v25; // r15
  __int64 v26; // r12
  unsigned __int16 *v27; // rdi
  unsigned int v28; // esi
  unsigned int v29; // esi
  unsigned __int16 *v30; // rdi
  SYSTEMTIME *v31; // rax
  int v32; // edi
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  __int64 v35; // rcx
  __int64 v36; // rcx
  unsigned int v38[2]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v39; // [rsp+38h] [rbp-C8h] BYREF
  struct _FILETIME FileTime; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v41; // [rsp+48h] [rbp-B8h]
  unsigned int v42; // [rsp+4Ch] [rbp-B4h]
  _QWORD v43[4]; // [rsp+50h] [rbp-B0h] BYREF
  _WORD v44[2]; // [rsp+70h] [rbp-90h] BYREF
  char v45; // [rsp+74h] [rbp-8Ch]
  union _LARGE_INTEGER v46; // [rsp+80h] [rbp-80h]
  struct _GUID v47; // [rsp+88h] [rbp-78h]
  struct _FILETIME *v48; // [rsp+B8h] [rbp-48h]
  unsigned int v49; // [rsp+C0h] [rbp-40h]
  unsigned int v50; // [rsp+C4h] [rbp-3Ch]
  _WORD v51[2]; // [rsp+D0h] [rbp-30h] BYREF
  char v52; // [rsp+D4h] [rbp-2Ch]
  union _LARGE_INTEGER v53; // [rsp+E0h] [rbp-20h]
  struct _GUID v54; // [rsp+E8h] [rbp-18h]
  _QWORD v55[4]; // [rsp+100h] [rbp+0h] BYREF
  int v56; // [rsp+120h] [rbp+20h]
  unsigned int v57; // [rsp+124h] [rbp+24h]
  SYSTEMTIME SystemTime; // [rsp+130h] [rbp+30h] BYREF
  __int64 v59; // [rsp+140h] [rbp+40h]
  unsigned __int64 v60; // [rsp+148h] [rbp+48h]
  __int128 v61; // [rsp+150h] [rbp+50h] BYREF
  struct _FILETIME v62; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int16 v63; // [rsp+168h] [rbp+68h] BYREF
  char v64; // [rsp+16Ah] [rbp+6Ah] BYREF
  wchar_t Source[16]; // [rsp+970h] [rbp+870h] BYREF

  v4 = a3;
  v41 = a3;
  v42 = a4;
  v7 = a4;
  memset_0(&v62, 0, 0x80Cu);
  memset(v43, 0, 24);
  v8 = &v63;
  v61 = 0;
  if ( (unsigned int)ATL::CRegKey::Open(
                       (ATL::CRegKey *)v43,
                       HKEY_LOCAL_MACHINE,
                       L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion",
                       1u) )
    goto LABEL_30;
  v39 = 0;
  if ( !(unsigned int)ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)v43, L"InstallDate", &v39) )
  {
    *(_QWORD *)v38 = (int)v39;
    *(_DWORD *)_o__errno() = 0;
    v9 = (WORD *)_o__gmtime64(v38);
    if ( v9 )
    {
      if ( !*(_DWORD *)_o__errno() )
      {
        v10 = v9[12];
        v11 = *v9;
        v12 = v9[8] + 1;
        v13 = v9[2];
        v14 = v9[4];
        v15 = v9[6];
        SystemTime.wYear = v9[10] + 1900;
        SystemTime.wDayOfWeek = v10;
        SystemTime.wMonth = v12;
        SystemTime.wDay = v15;
        SystemTime.wHour = v14;
        SystemTime.wMinute = v13;
        SystemTime.wSecond = v11;
        SystemTime.wMilliseconds = 0;
        FileTime = 0;
        v16 = SystemTimeToFileTime(&SystemTime, &FileTime);
        v17 = v62;
        if ( v16 )
          v17 = FileTime;
        v62 = v17;
      }
    }
  }
  v18 = 1025;
  v38[0] = 1025;
  if ( (unsigned int)ATL::CRegKey::QueryStringValue((ATL::CRegKey *)v43, L"BuildLabEx", &v63, v38) )
  {
    v38[0] = 1025;
    if ( (unsigned int)ATL::CRegKey::QueryStringValue((ATL::CRegKey *)v43, L"BuildLab", &v63, v38) )
    {
      v63 = 0;
      v8 = (unsigned __int16 *)&v64;
      goto LABEL_24;
    }
  }
  else
  {
    FileTime.dwLowDateTime = 0;
    if ( !(unsigned int)ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)v43, L"UBR", (unsigned int *)&FileTime) )
    {
      std::wstring::wstring((__int64)&SystemTime, (__int64)&v63);
      p_SystemTime = &SystemTime;
      if ( v60 > 7 )
        p_SystemTime = *(SYSTEMTIME **)&SystemTime.wYear;
      v20 = std::_Traits_find_ch<std::char_traits<unsigned short>>(p_SystemTime, v59, 0);
      if ( v20 == -1 )
        goto LABEL_20;
      v21 = v20 + 1;
      v22 = &SystemTime;
      if ( v60 > 7 )
        v22 = *(SYSTEMTIME **)&SystemTime.wYear;
      v23 = std::_Traits_find_ch<std::char_traits<unsigned short>>(v22, v59, v20 + 1);
      if ( v23 == -1
        || (_o__ultow_s(FileTime.dwLowDateTime, Source, 16, 10),
            v24 = wcsnlen(Source, 0x10u),
            v25 = v24,
            v26 = v59 - v23 + 1,
            v24 + v26 + v21 > 0x402) )
      {
LABEL_20:
        std::wstring::~wstring((__int64)&SystemTime);
        v32 = -2147467259;
LABEL_32:
        ATL::CRegKey::Close((ATL::CRegKey *)v43);
        return (unsigned int)v32;
      }
      v27 = &v63 + v21;
      v28 = 1026 - v21;
      _o_wcsncpy_s(v27, v28, Source, v24);
      v29 = v28 - v25;
      v30 = &v27[v25];
      v31 = &SystemTime;
      *(_QWORD *)v38 = v30;
      if ( v60 > 7 )
        v31 = *(SYSTEMTIME **)&SystemTime.wYear;
      _o_wcsncpy_s(v30, v29, (char *)v31 + 2 * v23, v26);
      v18 = v29 - v26;
      v8 = &v30[v26];
      std::wstring::~wstring((__int64)&SystemTime);
      v4 = v41;
      v7 = v42;
      goto LABEL_24;
    }
  }
  v18 = 1026 - v38[0];
  v8 = &v63 + v38[0];
LABEL_24:
  v38[0] = v18;
  if ( (unsigned int)ATL::CRegKey::QueryStringValue((ATL::CRegKey *)v43, L"ProductName", v8, v38) )
  {
    *v8 = 0;
    LODWORD(v8) = (_DWORD)v8 + 2;
  }
  else
  {
    LODWORD(v8) = (_DWORD)v8 + 2 * v38[0];
  }
  Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "RtlGetDeviceFamilyInfoEnum");
    if ( ProcAddress )
      ((void (__fastcall *)(__int128 *, char *, char *))ProcAddress)(&v61, (char *)&v61 + 8, (char *)&v61 + 12);
  }
LABEL_30:
  ATL::CRegKey::Close((ATL::CRegKey *)v43);
  memset_0(v44, 0, 0x58u);
  v35 = *((_QWORD *)this + 2);
  v48 = &v62;
  v44[0] = v7;
  v46 = a2;
  v49 = (_DWORD)v8 - ((unsigned int)v55 + 96);
  v47 = SystemConfigExGuid;
  v45 = 32;
  v50 = v4;
  v32 = (*(__int64 (__fastcall **)(__int64, _WORD *, _QWORD, _QWORD))(*(_QWORD *)v35 + 192LL))(v35, v44, 0, 0);
  if ( v32 < 0 )
    goto LABEL_32;
  memset_0(v51, 0, 0x58u);
  v36 = *((_QWORD *)this + 2);
  v55[3] = &v61;
  v54 = SystemConfigExGuid;
  v51[0] = v7;
  v53 = a2;
  v52 = 37;
  v56 = 16;
  v57 = v4;
  v32 = (*(__int64 (__fastcall **)(__int64, _WORD *, _QWORD, _QWORD))(*(_QWORD *)v36 + 192LL))(v36, v51, 0, 0);
  if ( v32 < 0 )
    goto LABEL_32;
  ATL::CRegKey::Close((ATL::CRegKey *)v43);
  return Microsoft::Windows::Performance::CEventTraceExtenderBase::OnAfterEvents(this, a2, v4, v7);
}

```

## disassembly

```asm
0x18000f0d0  push    rbp
0x18000f0d2  push    rbx
0x18000f0d3  push    rsi
0x18000f0d4  push    rdi
0x18000f0d5  push    r12
0x18000f0d7  push    r13
0x18000f0d9  push    r14
0x18000f0db  push    r15
0x18000f0dd  lea     rbp, [rsp-8A8h]
0x18000f0e5  sub     rsp, 9A8h
0x18000f0ec  mov     rax, cs:__security_cookie
0x18000f0f3  xor     rax, rsp
0x18000f0f6  mov     [rbp+8E0h+var_50], rax
0x18000f0fd  mov     r14d, r8d
0x18000f100  mov     [rsp+9E0h+var_998], r8d
0x18000f105  mov     rbx, rdx
0x18000f108  mov     [rsp+9E0h+var_994], r9d
0x18000f10d  mov     r13, rcx
0x18000f110  xor     edx, edx; Val
0x18000f112  mov     r8d, 80Ch; Size
0x18000f118  lea     rcx, [rbp+8E0h+var_880]; void *
0x18000f11c  mov     r15d, r9d
0x18000f11f  call    memset_0
0x18000f124  xor     r12d, r12d
0x18000f127  lea     r8, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18000f12e  xorps   xmm0, xmm0
0x18000f131  mov     [rsp+9E0h+var_990], r12
0x18000f136  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18000f13d  mov     [rsp+9E0h+var_988], r12
0x18000f142  lea     rcx, [rsp+9E0h+var_990]; this
0x18000f147  mov     [rsp+9E0h+var_980], r12
0x18000f14c  lea     esi, [r12+1]
0x18000f151  mov     r9d, esi; unsigned int
0x18000f154  lea     rdi, [rbp+8E0h+var_878]
0x18000f158  movups  [rbp+8E0h+var_890], xmm0
0x18000f15c  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000f161  test    eax, eax
0x18000f163  jnz     loc_18000F44E
0x18000f169  lea     r8, [rsp+9E0h+var_9A8]; unsigned int *
0x18000f16e  mov     [rsp+9E0h+var_9A8], r12d
0x18000f173  lea     rdx, aInstalldate; "InstallDate"
0x18000f17a  lea     rcx, [rsp+9E0h+var_990]; this
0x18000f17f  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x18000f184  test    eax, eax
0x18000f186  jnz     loc_18000F22D
0x18000f18c  movsxd  rax, [rsp+9E0h+var_9A8]
0x18000f191  mov     qword ptr [rsp+9E0h+var_9B0], rax
0x18000f196  call    cs:__imp__o__errno
0x18000f19c  lea     rcx, [rsp+9E0h+var_9B0]
0x18000f1a1  mov     [rax], r12d
0x18000f1a4  call    cs:__imp__o__gmtime64
0x18000f1aa  mov     rdi, rax
0x18000f1ad  test    rax, rax
0x18000f1b0  jz      short loc_18000F22D
0x18000f1b2  call    cs:__imp__o__errno
0x18000f1b8  cmp     [rax], r12d
0x18000f1bb  jnz     short loc_18000F22D
0x18000f1bd  movzx   edx, word ptr [rdi+18h]
0x18000f1c1  mov     ecx, 76Ch
0x18000f1c6  add     cx, [rdi+14h]
0x18000f1ca  movzx   eax, word ptr [rdi+10h]
0x18000f1ce  movzx   r11d, word ptr [rdi]
0x18000f1d2  add     ax, si
0x18000f1d5  movzx   r10d, word ptr [rdi+4]
0x18000f1da  movzx   r9d, word ptr [rdi+8]
0x18000f1df  movzx   r8d, word ptr [rdi+0Ch]
0x18000f1e4  mov     [rbp+8E0h+SystemTime.wYear], cx
0x18000f1e8  lea     rcx, [rbp+8E0h+SystemTime]; lpSystemTime
0x18000f1ec  mov     [rbp+8E0h+SystemTime.wDayOfWeek], dx
0x18000f1f0  lea     rdx, [rsp+9E0h+FileTime]; lpFileTime
0x18000f1f5  mov     [rbp+8E0h+SystemTime.wMonth], ax
0x18000f1f9  mov     [rbp+8E0h+SystemTime.wDay], r8w
0x18000f1fe  mov     [rbp+8E0h+SystemTime.wHour], r9w
0x18000f203  mov     [rbp+8E0h+SystemTime.wMinute], r10w
0x18000f208  mov     [rbp+8E0h+SystemTime.wSecond], r11w
0x18000f20d  mov     [rbp+8E0h+SystemTime.wMilliseconds], r12w
0x18000f212  mov     qword ptr [rsp+9E0h+FileTime.dwLowDateTime], r12
0x18000f217  call    cs:__imp_SystemTimeToFileTime
0x18000f21d  mov     rcx, [rbp+8E0h+var_880]
0x18000f221  test    eax, eax
0x18000f223  cmovnz  rcx, qword ptr [rsp+9E0h+FileTime.dwLowDateTime]
0x18000f229  mov     [rbp+8E0h+var_880], rcx
0x18000f22d  mov     esi, 401h
0x18000f232  lea     r9, [rsp+9E0h+var_9B0]; unsigned int *
0x18000f237  lea     r8, [rbp+8E0h+var_878]; unsigned __int16 *
0x18000f23b  mov     [rsp+9E0h+var_9B0], esi
0x18000f23f  lea     rdx, aBuildlabex; "BuildLabEx"
0x18000f246  lea     rcx, [rsp+9E0h+var_990]; this
0x18000f24b  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x18000f250  lea     rcx, [rsp+9E0h+var_990]; this
0x18000f255  test    eax, eax
0x18000f257  jnz     loc_18000F39E
0x18000f25d  lea     r8, [rsp+9E0h+FileTime]; unsigned int *
0x18000f262  mov     [rsp+9E0h+FileTime.dwLowDateTime], r12d
0x18000f267  lea     rdx, aUbr; "UBR"
0x18000f26e  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x18000f273  test    eax, eax
0x18000f275  jnz     loc_18000F3BB
0x18000f27b  lea     rdx, [rbp+8E0h+var_878]
0x18000f27f  lea     rcx, [rbp+8E0h+SystemTime]
0x18000f283  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000f288  cmp     [rbp+8E0h+var_898], 7
0x18000f28d  lea     rcx, [rbp+8E0h+SystemTime]
0x18000f291  mov     rdx, [rbp+8E0h+var_8A0]
0x18000f295  cmova   rcx, qword ptr [rbp+8E0h+SystemTime.wYear]
0x18000f29a  xor     r8d, r8d
0x18000f29d  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x18000f2a2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000f2a6  jz      loc_18000F38B
0x18000f2ac  cmp     [rbp+8E0h+var_898], 7
0x18000f2b1  lea     rsi, [rax+1]
0x18000f2b5  mov     rdx, [rbp+8E0h+var_8A0]
0x18000f2b9  lea     rcx, [rbp+8E0h+SystemTime]
0x18000f2bd  cmova   rcx, qword ptr [rbp+8E0h+SystemTime.wYear]
0x18000f2c2  mov     r8, rsi
0x18000f2c5  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x18000f2ca  mov     r14, rax
0x18000f2cd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000f2d1  jz      loc_18000F38B
0x18000f2d7  mov     ecx, [rsp+9E0h+FileTime.dwLowDateTime]
0x18000f2db  lea     rdx, [rbp+8E0h+Source]
0x18000f2e2  mov     edi, 10h
0x18000f2e7  mov     r8d, edi
0x18000f2ea  lea     r9d, [rdi-6]
0x18000f2ee  call    cs:__imp__o__ultow_s
0x18000f2f4  mov     edx, edi; MaxCount
0x18000f2f6  lea     rcx, [rbp+8E0h+Source]; Source
0x18000f2fd  call    cs:__imp_wcsnlen
0x18000f303  mov     r12, [rbp+8E0h+var_8A0]
0x18000f307  mov     edx, 402h
0x18000f30c  sub     r12, r14
0x18000f30f  mov     r15, rax
0x18000f312  inc     r12
0x18000f315  lea     rcx, [r12+rsi]
0x18000f319  add     rcx, rax
0x18000f31c  cmp     rcx, rdx
0x18000f31f  ja      short loc_18000F38B
0x18000f321  sub     edx, esi
0x18000f323  lea     rdi, [rbp+8E0h+var_878]
0x18000f327  lea     rdi, [rdi+rsi*2]
0x18000f32b  mov     r9, rax
0x18000f32e  mov     rcx, rdi
0x18000f331  mov     esi, edx
0x18000f333  lea     r8, [rbp+8E0h+Source]
0x18000f33a  call    cs:__imp__o_wcsncpy_s
0x18000f340  sub     esi, r15d
0x18000f343  lea     rdi, [rdi+r15*2]
0x18000f347  cmp     [rbp+8E0h+var_898], 7
0x18000f34c  lea     rax, [rbp+8E0h+SystemTime]
0x18000f350  mov     edx, esi
0x18000f352  mov     qword ptr [rsp+9E0h+var_9B0], rdi
0x18000f357  cmova   rax, qword ptr [rbp+8E0h+SystemTime.wYear]
0x18000f35c  mov     r9, r12
0x18000f35f  mov     rcx, rdi
0x18000f362  lea     r8, [rax+r14*2]
0x18000f366  call    cs:__imp__o_wcsncpy_s
0x18000f36c  lea     rcx, [rbp+8E0h+SystemTime]
0x18000f370  sub     esi, r12d
0x18000f373  lea     rdi, [rdi+r12*2]
0x18000f377  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000f37c  mov     r14d, [rsp+9E0h+var_998]
0x18000f381  xor     r12d, r12d
0x18000f384  mov     r15d, [rsp+9E0h+var_994]
0x18000f389  jmp     short loc_18000F3DB
0x18000f38b  lea     rcx, [rbp+8E0h+SystemTime]
0x18000f38f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000f394  mov     edi, 80004005h
0x18000f399  jmp     loc_18000F51D
0x18000f39e  lea     r9, [rsp+9E0h+var_9B0]; unsigned int *
0x18000f3a3  mov     [rsp+9E0h+var_9B0], esi
0x18000f3a7  lea     r8, [rbp+8E0h+var_878]; unsigned __int16 *
0x18000f3ab  lea     rdx, aBuildlab; "BuildLab"
0x18000f3b2  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x18000f3b7  test    eax, eax
0x18000f3b9  jnz     short loc_18000F3D2
0x18000f3bb  mov     eax, [rsp+9E0h+var_9B0]
0x18000f3bf  lea     rdi, [rbp+8E0h+var_878]
0x18000f3c3  mov     esi, 402h
0x18000f3c8  sub     esi, [rsp+9E0h+var_9B0]
0x18000f3cc  lea     rdi, [rdi+rax*2]
0x18000f3d0  jmp     short loc_18000F3DB
0x18000f3d2  mov     [rbp+8E0h+var_878], r12w
0x18000f3d7  lea     rdi, [rbp+8E0h+var_876]
0x18000f3db  lea     r9, [rsp+9E0h+var_9B0]; unsigned int *
0x18000f3e0  mov     [rsp+9E0h+var_9B0], esi
0x18000f3e4  mov     r8, rdi; unsigned __int16 *
0x18000f3e7  lea     rdx, aProductname; "ProductName"
0x18000f3ee  lea     rcx, [rsp+9E0h+var_990]; this
0x18000f3f3  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x18000f3f8  test    eax, eax
0x18000f3fa  jnz     short loc_18000F406
0x18000f3fc  mov     eax, [rsp+9E0h+var_9B0]
0x18000f400  lea     rdi, [rdi+rax*2]
0x18000f404  jmp     short loc_18000F40E
0x18000f406  mov     [rdi], r12w
0x18000f40a  add     rdi, 2
0x18000f40e  xor     edx, edx; hFile
0x18000f410  lea     rcx, LibFileName; "ntdll.dll"
0x18000f417  mov     r8d, 800h; dwFlags
0x18000f41d  call    cs:__imp_LoadLibraryExW
0x18000f423  test    rax, rax
0x18000f426  jz      short loc_18000F44E
0x18000f428  lea     rdx, aRtlgetdevicefa; "RtlGetDeviceFamilyInfoEnum"
0x18000f42f  mov     rcx, rax; hModule
0x18000f432  call    cs:__imp_GetProcAddress
0x18000f438  test    rax, rax
0x18000f43b  jz      short loc_18000F44E
0x18000f43d  lea     r8, [rbp+8E0h+var_890+0Ch]
0x18000f441  lea     rdx, [rbp+8E0h+var_890+8]
0x18000f445  lea     rcx, [rbp+8E0h+var_890]
0x18000f449  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f44e  lea     rcx, [rsp+9E0h+var_990]; this
0x18000f453  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000f458  mov     esi, 58h ; 'X'
0x18000f45d  lea     rcx, [rsp+9E0h+var_970]; void *
0x18000f462  mov     r8d, esi; Size
0x18000f465  xor     edx, edx; Val
0x18000f467  call    memset_0
0x18000f46c  movups  xmm0, xmmword ptr cs:SystemConfigExGuid.Data1
0x18000f473  mov     rcx, [r13+10h]
0x18000f477  lea     rax, [rbp+8E0h+var_880]
0x18000f47b  mov     [rbp+8E0h+var_928], rax
0x18000f47f  lea     rdx, [rsp+9E0h+var_970]
0x18000f484  lea     rax, [rbp+8E0h+var_880]
0x18000f488  mov     [rsp+9E0h+var_970], r15w
0x18000f48e  sub     edi, eax
0x18000f490  mov     [rbp+8E0h+var_960], rbx
0x18000f494  mov     [rbp+8E0h+var_920], edi
0x18000f497  xor     r9d, r9d
0x18000f49a  movdqu  [rbp+8E0h+var_958], xmm0
0x18000f49f  mov     [rsp+9E0h+var_96C], 20h ; ' '
0x18000f4a4  xor     r8d, r8d
0x18000f4a7  mov     [rbp+8E0h+var_91C], r14d
0x18000f4ab  mov     rax, [rcx]
0x18000f4ae  mov     rax, [rax+0C0h]
0x18000f4b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4ba  mov     edi, eax
0x18000f4bc  test    eax, eax
0x18000f4be  js      short loc_18000F51D
0x18000f4c0  mov     r8d, esi; Size
0x18000f4c3  lea     rcx, [rbp+8E0h+var_910]; void *
0x18000f4c7  xor     edx, edx; Val
0x18000f4c9  call    memset_0
0x18000f4ce  movups  xmm0, xmmword ptr cs:SystemConfigExGuid.Data1
0x18000f4d5  mov     rcx, [r13+10h]
0x18000f4d9  lea     rax, [rbp+8E0h+var_890]
0x18000f4dd  mov     [rbp+8E0h+var_8C8], rax
0x18000f4e1  lea     rdx, [rbp+8E0h+var_910]
0x18000f4e5  movdqu  [rbp+8E0h+var_8F8], xmm0
0x18000f4ea  mov     [rbp+8E0h+var_910], r15w
0x18000f4ef  xor     r9d, r9d
0x18000f4f2  mov     [rbp+8E0h+var_900], rbx
0x18000f4f6  xor     r8d, r8d
0x18000f4f9  mov     [rbp+8E0h+var_90C], 25h ; '%'
0x18000f4fd  mov     [rbp+8E0h+var_8C0], 10h
0x18000f504  mov     [rbp+8E0h+var_8BC], r14d
0x18000f508  mov     rax, [rcx]
0x18000f50b  mov     rax, [rax+0C0h]
0x18000f512  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f517  mov     edi, eax
0x18000f519  test    eax, eax
0x18000f51b  jns     short loc_18000F52B
0x18000f51d  lea     rcx, [rsp+9E0h+var_990]; this
0x18000f522  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000f527  mov     eax, edi
0x18000f529  jmp     short loc_18000F546
0x18000f52b  lea     rcx, [rsp+9E0h+var_990]; this
0x18000f530  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000f535  mov     r9d, r15d; unsigned int
0x18000f538  mov     r8d, r14d; unsigned int
0x18000f53b  mov     rdx, rbx; union _LARGE_INTEGER
0x18000f53e  mov     rcx, r13; this
0x18000f541  call    ?OnAfterEvents@CEventTraceExtenderBase@Performance@Windows@Microsoft@@UEAAJT_LARGE_INTEGER@@KK@Z; Microsoft::Windows::Performance::CEventTraceExtenderBase::OnAfterEvents(_LARGE_INTEGER,ulong,ulong)
0x18000f546  mov     rcx, [rbp+8E0h+var_50]
0x18000f54d  xor     rcx, rsp; StackCookie
0x18000f550  call    __security_check_cookie
0x18000f555  add     rsp, 9A8h
0x18000f55c  pop     r15
0x18000f55e  pop     r14
0x18000f560  pop     r13
0x18000f562  pop     r12
0x18000f564  pop     rdi
0x18000f565  pop     rsi
0x18000f566  pop     rbx
0x18000f567  pop     rbp
0x18000f568  retn
```
