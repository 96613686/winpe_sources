# Microsoft::Windows::Performance::CBuildInfoEventTraceExtender::OnAfterEvents(_LARGE_INTEGER,ulong,ulong)

- ea: `0x18000f760`
- end: `0x18000fc3a`
- name: `?OnAfterEvents@CBuildInfoEventTraceExtender@Performance@Windows@Microsoft@@UEAAJT_LARGE_INTEGER@@KK@Z`
- size: `1242`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CBuildInfoEventTraceExtender *__hidden this, union _LARGE_INTEGER, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001800`
- `0x1800023e0`
- `0x180003768`
- `0x180003b14`
- `0x18000b750`
- `0x18000f558`
- `0x18000f63c`
- `0x18000f760`
- `0x18000fc40`
- `0x18000fca0`
- `0x18000fd18`
- `0x180027010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__gmtime64` at `0x18000f83a`
- `api-ms-win-crt-private-l1-1-0!_o__gmtime64` at `0x18000f83a`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x18000f99a`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x18000f99a`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000f9f2`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000fa24`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000f9f2`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000fa24`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f826`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f852`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f826`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f852`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18000f9af`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18000f9af`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000fae1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000fae1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fafc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fafc`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000f8bd`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000f8bd`

## string_xrefs

- `0x18000fad4`: `ntdll.dll`
- `0x18000f803`: `InstallDate`

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
      std::wstring::wstring(&SystemTime, &v63);
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
        std::wstring::~wstring(&SystemTime);
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
      std::wstring::~wstring(&SystemTime);
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
0x18000f760  push    rbp
0x18000f762  push    rbx
0x18000f763  push    rsi
0x18000f764  push    rdi
0x18000f765  push    r12
0x18000f767  push    r13
0x18000f769  push    r14
0x18000f76b  push    r15
0x18000f76d  lea     rbp, [rsp-8A8h]
0x18000f775  sub     rsp, 9A8h
0x18000f77c  mov     rax, cs:__security_cookie
0x18000f783  xor     rax, rsp
0x18000f786  mov     [rbp+8E0h+var_50], rax
0x18000f78d  mov     r14d, r8d
0x18000f790  mov     [rsp+9E0h+var_998], r8d
0x18000f795  mov     rbx, rdx
0x18000f798  mov     [rsp+9E0h+var_994], r9d
0x18000f79d  mov     r13, rcx
0x18000f7a0  xor     edx, edx; Val
0x18000f7a2  mov     r8d, 80Ch; Size
0x18000f7a8  lea     rcx, [rbp+8E0h+var_880]; void *
0x18000f7ac  mov     r15d, r9d
0x18000f7af  call    memset_0
0x18000f7b4  xor     r12d, r12d
0x18000f7b7  lea     r8, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18000f7be  xorps   xmm0, xmm0
0x18000f7c1  mov     [rsp+9E0h+var_990], r12
0x18000f7c6  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18000f7cd  mov     [rsp+9E0h+var_988], r12
0x18000f7d2  lea     rcx, [rsp+9E0h+var_990]; this
0x18000f7d7  mov     [rsp+9E0h+var_980], r12
0x18000f7dc  lea     esi, [r12+1]
0x18000f7e1  mov     r9d, esi; unsigned int
0x18000f7e4  lea     rdi, [rbp+8E0h+var_878]
0x18000f7e8  movups  [rbp+8E0h+var_890], xmm0
0x18000f7ec  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000f7f1  test    eax, eax
0x18000f7f3  jnz     loc_18000FB1E
0x18000f7f9  lea     r8, [rsp+9E0h+var_9A8]; unsigned int *
0x18000f7fe  mov     [rsp+9E0h+var_9A8], r12d
0x18000f803  lea     rdx, aInstalldate; "InstallDate"
0x18000f80a  lea     rcx, [rsp+9E0h+var_990]; this
0x18000f80f  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x18000f814  test    eax, eax
0x18000f816  jnz     loc_18000F8D9
0x18000f81c  movsxd  rax, [rsp+9E0h+var_9A8]
0x18000f821  mov     qword ptr [rsp+9E0h+var_9B0], rax
0x18000f826  call    cs:__imp__o__errno
0x18000f82d  nop     dword ptr [rax+rax+00h]
0x18000f832  lea     rcx, [rsp+9E0h+var_9B0]
0x18000f837  mov     [rax], r12d
0x18000f83a  call    cs:__imp__o__gmtime64
0x18000f841  nop     dword ptr [rax+rax+00h]
0x18000f846  mov     rdi, rax
0x18000f849  test    rax, rax
0x18000f84c  jz      loc_18000F8D9
0x18000f852  call    cs:__imp__o__errno
0x18000f859  nop     dword ptr [rax+rax+00h]
0x18000f85e  cmp     [rax], r12d
0x18000f861  jnz     short loc_18000F8D9
0x18000f863  movzx   edx, word ptr [rdi+18h]
0x18000f867  mov     ecx, 76Ch
0x18000f86c  add     cx, [rdi+14h]
0x18000f870  movzx   eax, word ptr [rdi+10h]
0x18000f874  movzx   r11d, word ptr [rdi]
0x18000f878  add     ax, si
0x18000f87b  movzx   r10d, word ptr [rdi+4]
0x18000f880  movzx   r9d, word ptr [rdi+8]
0x18000f885  movzx   r8d, word ptr [rdi+0Ch]
0x18000f88a  mov     [rbp+8E0h+SystemTime.wYear], cx
0x18000f88e  lea     rcx, [rbp+8E0h+SystemTime]; lpSystemTime
0x18000f892  mov     [rbp+8E0h+SystemTime.wDayOfWeek], dx
0x18000f896  lea     rdx, [rsp+9E0h+FileTime]; lpFileTime
0x18000f89b  mov     [rbp+8E0h+SystemTime.wMonth], ax
0x18000f89f  mov     [rbp+8E0h+SystemTime.wDay], r8w
0x18000f8a4  mov     [rbp+8E0h+SystemTime.wHour], r9w
0x18000f8a9  mov     [rbp+8E0h+SystemTime.wMinute], r10w
0x18000f8ae  mov     [rbp+8E0h+SystemTime.wSecond], r11w
0x18000f8b3  mov     [rbp+8E0h+SystemTime.wMilliseconds], r12w
0x18000f8b8  mov     qword ptr [rsp+9E0h+FileTime.dwLowDateTime], r12
0x18000f8bd  call    cs:__imp_SystemTimeToFileTime
0x18000f8c4  nop     dword ptr [rax+rax+00h]
0x18000f8c9  mov     rcx, [rbp+8E0h+var_880]
0x18000f8cd  test    eax, eax
0x18000f8cf  cmovnz  rcx, qword ptr [rsp+9E0h+FileTime.dwLowDateTime]
0x18000f8d5  mov     [rbp+8E0h+var_880], rcx
0x18000f8d9  mov     esi, 401h
0x18000f8de  lea     r9, [rsp+9E0h+var_9B0]; unsigned int *
0x18000f8e3  lea     r8, [rbp+8E0h+var_878]; unsigned __int16 *
0x18000f8e7  mov     [rsp+9E0h+var_9B0], esi
0x18000f8eb  lea     rdx, aBuildlabex; "BuildLabEx"
0x18000f8f2  lea     rcx, [rsp+9E0h+var_990]; this
0x18000f8f7  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x18000f8fc  lea     rcx, [rsp+9E0h+var_990]; this
0x18000f901  test    eax, eax
0x18000f903  jnz     loc_18000FA62
0x18000f909  lea     r8, [rsp+9E0h+FileTime]; unsigned int *
0x18000f90e  mov     [rsp+9E0h+FileTime.dwLowDateTime], r12d
0x18000f913  lea     rdx, aUbr; "UBR"
0x18000f91a  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x18000f91f  test    eax, eax
0x18000f921  jnz     loc_18000FA7F
0x18000f927  lea     rdx, [rbp+8E0h+var_878]
0x18000f92b  lea     rcx, [rbp+8E0h+SystemTime]
0x18000f92f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000f934  cmp     [rbp+8E0h+var_898], 7
0x18000f939  lea     rcx, [rbp+8E0h+SystemTime]
0x18000f93d  mov     rdx, [rbp+8E0h+var_8A0]
0x18000f941  cmova   rcx, qword ptr [rbp+8E0h+SystemTime.wYear]
0x18000f946  xor     r8d, r8d
0x18000f949  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x18000f94e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000f952  jz      loc_18000FA4F
0x18000f958  cmp     [rbp+8E0h+var_898], 7
0x18000f95d  lea     rsi, [rax+1]
0x18000f961  mov     rdx, [rbp+8E0h+var_8A0]
0x18000f965  lea     rcx, [rbp+8E0h+SystemTime]
0x18000f969  cmova   rcx, qword ptr [rbp+8E0h+SystemTime.wYear]
0x18000f96e  mov     r8, rsi
0x18000f971  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x18000f976  mov     r14, rax
0x18000f979  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000f97d  jz      loc_18000FA4F
0x18000f983  mov     ecx, [rsp+9E0h+FileTime.dwLowDateTime]
0x18000f987  lea     rdx, [rbp+8E0h+Source]
0x18000f98e  mov     edi, 10h
0x18000f993  mov     r8d, edi
0x18000f996  lea     r9d, [rdi-6]
0x18000f99a  call    cs:__imp__o__ultow_s
0x18000f9a1  nop     dword ptr [rax+rax+00h]
0x18000f9a6  mov     edx, edi; MaxCount
0x18000f9a8  lea     rcx, [rbp+8E0h+Source]; Source
0x18000f9af  call    cs:__imp_wcsnlen
0x18000f9b6  nop     dword ptr [rax+rax+00h]
0x18000f9bb  mov     r12, [rbp+8E0h+var_8A0]
0x18000f9bf  mov     edx, 402h
0x18000f9c4  sub     r12, r14
0x18000f9c7  mov     r15, rax
0x18000f9ca  inc     r12
0x18000f9cd  lea     rcx, [r12+rsi]
0x18000f9d1  add     rcx, rax
0x18000f9d4  cmp     rcx, rdx
0x18000f9d7  ja      short loc_18000FA4F
0x18000f9d9  sub     edx, esi
0x18000f9db  lea     rdi, [rbp+8E0h+var_878]
0x18000f9df  lea     rdi, [rdi+rsi*2]
0x18000f9e3  mov     r9, rax
0x18000f9e6  mov     rcx, rdi
0x18000f9e9  mov     esi, edx
0x18000f9eb  lea     r8, [rbp+8E0h+Source]
0x18000f9f2  call    cs:__imp__o_wcsncpy_s
0x18000f9f9  nop     dword ptr [rax+rax+00h]
0x18000f9fe  sub     esi, r15d
0x18000fa01  lea     rdi, [rdi+r15*2]
0x18000fa05  cmp     [rbp+8E0h+var_898], 7
0x18000fa0a  lea     rax, [rbp+8E0h+SystemTime]
0x18000fa0e  mov     edx, esi
0x18000fa10  mov     qword ptr [rsp+9E0h+var_9B0], rdi
0x18000fa15  cmova   rax, qword ptr [rbp+8E0h+SystemTime.wYear]
0x18000fa1a  mov     r9, r12
0x18000fa1d  mov     rcx, rdi
0x18000fa20  lea     r8, [rax+r14*2]
0x18000fa24  call    cs:__imp__o_wcsncpy_s
0x18000fa2b  nop     dword ptr [rax+rax+00h]
0x18000fa30  lea     rcx, [rbp+8E0h+SystemTime]
0x18000fa34  sub     esi, r12d
0x18000fa37  lea     rdi, [rdi+r12*2]
0x18000fa3b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000fa40  mov     r14d, [rsp+9E0h+var_998]
0x18000fa45  xor     r12d, r12d
0x18000fa48  mov     r15d, [rsp+9E0h+var_994]
0x18000fa4d  jmp     short loc_18000FA9F
0x18000fa4f  lea     rcx, [rbp+8E0h+SystemTime]
0x18000fa53  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000fa58  mov     edi, 80004005h
0x18000fa5d  jmp     loc_18000FBED
0x18000fa62  lea     r9, [rsp+9E0h+var_9B0]; unsigned int *
0x18000fa67  mov     [rsp+9E0h+var_9B0], esi
0x18000fa6b  lea     r8, [rbp+8E0h+var_878]; unsigned __int16 *
0x18000fa6f  lea     rdx, aBuildlab; "BuildLab"
0x18000fa76  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x18000fa7b  test    eax, eax
0x18000fa7d  jnz     short loc_18000FA96
0x18000fa7f  mov     eax, [rsp+9E0h+var_9B0]
0x18000fa83  lea     rdi, [rbp+8E0h+var_878]
0x18000fa87  mov     esi, 402h
0x18000fa8c  sub     esi, [rsp+9E0h+var_9B0]
0x18000fa90  lea     rdi, [rdi+rax*2]
0x18000fa94  jmp     short loc_18000FA9F
0x18000fa96  mov     [rbp+8E0h+var_878], r12w
0x18000fa9b  lea     rdi, [rbp+8E0h+var_876]
0x18000fa9f  lea     r9, [rsp+9E0h+var_9B0]; unsigned int *
0x18000faa4  mov     [rsp+9E0h+var_9B0], esi
0x18000faa8  mov     r8, rdi; unsigned __int16 *
0x18000faab  lea     rdx, aProductname; "ProductName"
0x18000fab2  lea     rcx, [rsp+9E0h+var_990]; this
0x18000fab7  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x18000fabc  test    eax, eax
0x18000fabe  jnz     short loc_18000FACA
0x18000fac0  mov     eax, [rsp+9E0h+var_9B0]
0x18000fac4  lea     rdi, [rdi+rax*2]
0x18000fac8  jmp     short loc_18000FAD2
0x18000faca  mov     [rdi], r12w
0x18000face  add     rdi, 2
0x18000fad2  xor     edx, edx; hFile
0x18000fad4  lea     rcx, LibFileName; "ntdll.dll"
0x18000fadb  mov     r8d, 800h; dwFlags
0x18000fae1  call    cs:__imp_LoadLibraryExW
0x18000fae8  nop     dword ptr [rax+rax+00h]
0x18000faed  test    rax, rax
0x18000faf0  jz      short loc_18000FB1E
0x18000faf2  lea     rdx, aRtlgetdevicefa; "RtlGetDeviceFamilyInfoEnum"
0x18000faf9  mov     rcx, rax; hModule
0x18000fafc  call    cs:__imp_GetProcAddress
0x18000fb03  nop     dword ptr [rax+rax+00h]
0x18000fb08  test    rax, rax
0x18000fb0b  jz      short loc_18000FB1E
0x18000fb0d  lea     r8, [rbp+8E0h+var_890+0Ch]
0x18000fb11  lea     rdx, [rbp+8E0h+var_890+8]
0x18000fb15  lea     rcx, [rbp+8E0h+var_890]
0x18000fb19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb1e  lea     rcx, [rsp+9E0h+var_990]; this
0x18000fb23  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000fb28  mov     esi, 58h ; 'X'
0x18000fb2d  lea     rcx, [rsp+9E0h+var_970]; void *
0x18000fb32  mov     r8d, esi; Size
0x18000fb35  xor     edx, edx; Val
0x18000fb37  call    memset_0
0x18000fb3c  movups  xmm0, xmmword ptr cs:SystemConfigExGuid.Data1
0x18000fb43  mov     rcx, [r13+10h]
0x18000fb47  lea     rax, [rbp+8E0h+var_880]
0x18000fb4b  mov     [rbp+8E0h+var_928], rax
0x18000fb4f  lea     rdx, [rsp+9E0h+var_970]
0x18000fb54  lea     rax, [rbp+8E0h+var_880]
0x18000fb58  mov     [rsp+9E0h+var_970], r15w
0x18000fb5e  sub     edi, eax
0x18000fb60  mov     [rbp+8E0h+var_960], rbx
0x18000fb64  mov     [rbp+8E0h+var_920], edi
0x18000fb67  xor     r9d, r9d
0x18000fb6a  movdqu  [rbp+8E0h+var_958], xmm0
0x18000fb6f  mov     [rsp+9E0h+var_96C], 20h ; ' '
0x18000fb74  xor     r8d, r8d
0x18000fb77  mov     [rbp+8E0h+var_91C], r14d
0x18000fb7b  mov     rax, [rcx]
0x18000fb7e  mov     rax, [rax+0C0h]
0x18000fb85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb8a  mov     edi, eax
0x18000fb8c  test    eax, eax
0x18000fb8e  js      short loc_18000FBED
0x18000fb90  mov     r8d, esi; Size
0x18000fb93  lea     rcx, [rbp+8E0h+var_910]; void *
0x18000fb97  xor     edx, edx; Val
0x18000fb99  call    memset_0
0x18000fb9e  movups  xmm0, xmmword ptr cs:SystemConfigExGuid.Data1
0x18000fba5  mov     rcx, [r13+10h]
0x18000fba9  lea     rax, [rbp+8E0h+var_890]
0x18000fbad  mov     [rbp+8E0h+var_8C8], rax
0x18000fbb1  lea     rdx, [rbp+8E0h+var_910]
0x18000fbb5  movdqu  [rbp+8E0h+var_8F8], xmm0
0x18000fbba  mov     [rbp+8E0h+var_910], r15w
0x18000fbbf  xor     r9d, r9d
0x18000fbc2  mov     [rbp+8E0h+var_900], rbx
0x18000fbc6  xor     r8d, r8d
0x18000fbc9  mov     [rbp+8E0h+var_90C], 25h ; '%'
0x18000fbcd  mov     [rbp+8E0h+var_8C0], 10h
0x18000fbd4  mov     [rbp+8E0h+var_8BC], r14d
0x18000fbd8  mov     rax, [rcx]
0x18000fbdb  mov     rax, [rax+0C0h]
0x18000fbe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fbe7  mov     edi, eax
0x18000fbe9  test    eax, eax
0x18000fbeb  jns     short loc_18000FBFB
0x18000fbed  lea     rcx, [rsp+9E0h+var_990]; this
0x18000fbf2  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000fbf7  mov     eax, edi
0x18000fbf9  jmp     short loc_18000FC16
0x18000fbfb  lea     rcx, [rsp+9E0h+var_990]; this
0x18000fc00  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000fc05  mov     r9d, r15d; unsigned int
0x18000fc08  mov     r8d, r14d; unsigned int
0x18000fc0b  mov     rdx, rbx; union _LARGE_INTEGER
0x18000fc0e  mov     rcx, r13; this
0x18000fc11  call    ?OnAfterEvents@CEventTraceExtenderBase@Performance@Windows@Microsoft@@UEAAJT_LARGE_INTEGER@@KK@Z; Microsoft::Windows::Performance::CEventTraceExtenderBase::OnAfterEvents(_LARGE_INTEGER,ulong,ulong)
0x18000fc16  mov     rcx, [rbp+8E0h+var_50]
0x18000fc1d  xor     rcx, rsp; StackCookie
0x18000fc20  call    __security_check_cookie
0x18000fc25  add     rsp, 9A8h
0x18000fc2c  pop     r15
0x18000fc2e  pop     r14
0x18000fc30  pop     r13
0x18000fc32  pop     r12
0x18000fc34  pop     rdi
0x18000fc35  pop     rsi
0x18000fc36  pop     rbx
0x18000fc37  pop     rbp
0x18000fc38  retn
```
