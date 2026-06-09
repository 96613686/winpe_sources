# GetOnesettingsValues(ushort const *,ushort *)

- ea: `0x1800039c8`
- end: `0x1800041f7`
- name: `?GetOnesettingsValues@@YAJPEBGPEAG@Z`
- size: `2095`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180009140`

## callees

- `0x180002a68`
- `0x180002c04`
- `0x1800039c8`
- `0x180004200`
- `0x180004920`
- `0x1800055f4`
- `0x180007960`
- `0x180007a24`
- `0x180007ae0`
- `0x180007b54`
- `0x18000d258`
- `0x18000d824`
- `0x18000d910`
- `0x18000dc10`
- `0x18000e240`
- `0x1800191a2`
- `0x1800191f0`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180003ba3`
- `msvcrt!wcscpy_s` at `0x180003ba3`
- `msvcrt!wcsrchr` at `0x180003e67`
- `msvcrt!wcsrchr` at `0x180003e67`
- `msvcrt!_wcsicmp` at `0x180004086`
- `msvcrt!_wcsicmp` at `0x180004086`
- `KERNEL32!GetProcessHeap` at `0x180003a2d`
- `KERNEL32!GetProcessHeap` at `0x180003a53`
- `KERNEL32!GetProcessHeap` at `0x180003a9b`
- `KERNEL32!GetProcessHeap` at `0x180003ab9`
- `KERNEL32!GetProcessHeap` at `0x180003b01`
- `KERNEL32!GetProcessHeap` at `0x180003b1f`
- `KERNEL32!GetProcessHeap` at `0x180003a2d`
- `KERNEL32!GetProcessHeap` at `0x180003a53`
- `KERNEL32!GetProcessHeap` at `0x180003a9b`
- `KERNEL32!GetProcessHeap` at `0x180003ab9`
- `KERNEL32!GetProcessHeap` at `0x180003b01`
- `KERNEL32!GetProcessHeap` at `0x180003b1f`
- `KERNEL32!VerSetConditionMask` at `0x180003c5e`
- `KERNEL32!VerSetConditionMask` at `0x180003c6d`
- `KERNEL32!VerSetConditionMask` at `0x180003c7c`
- `KERNEL32!VerSetConditionMask` at `0x180003c5e`
- `KERNEL32!VerSetConditionMask` at `0x180003c6d`
- `KERNEL32!VerSetConditionMask` at `0x180003c7c`
- `KERNEL32!VerifyVersionInfoW` at `0x180003ca2`
- `KERNEL32!VerifyVersionInfoW` at `0x180003ca2`
- `ntdll!RtlFreeHeap` at `0x1800041a5`
- `ntdll!RtlFreeHeap` at `0x1800041a5`
- `ntdll!WinSqmIsOptedInEx` at `0x180003cbb`
- `ntdll!WinSqmIsOptedInEx` at `0x180003cbb`

## string_xrefs

- `0x180003b25`: `compat`
- `0x180003d1e`: `AslFileMappingCreate failed, 0x%x`
- `0x180003ebd`: `product name # company name # exe name: %ws`
- `0x180003ef3`: `AslFileGetVersionForPath failed with 0x%x`
- `0x18000407f`: `RECOMMENDEDLAYER`
- `0x18000409f`: `Cloud response of recommended layer: %ws`

## pseudocode

```c
__int64 __fastcall GetOnesettingsValues(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  HANDLE ProcessHeap; // rax
  HANDLE v5; // rax
  HANDLE v6; // rax
  unsigned __int64 v7; // rdx
  unsigned __int16 **v8; // r9
  unsigned __int64 v9; // rdx
  unsigned __int16 **v10; // r9
  OneCore::Base::Telemetry::OneSettingsQuery *v11; // rcx
  unsigned int v12; // r8d
  const unsigned __int16 *v13; // r9
  void *v14; // r15
  ULONGLONG v15; // rax
  ULONGLONG v16; // rax
  ULONGLONG v17; // rax
  int v18; // ecx
  char IsWin10TelemetryTypeAllowed; // si
  int v20; // ebx
  int v21; // eax
  int Attributes; // eax
  const char *v23; // r9
  __int64 v24; // r8
  unsigned __int16 *v25; // rdi
  unsigned __int16 *v26; // r8
  int v27; // eax
  __int64 v28; // r8
  wchar_t *v29; // rax
  const unsigned __int16 *v30; // rax
  int v31; // eax
  int VersionForPath; // eax
  __int64 v33; // rdi
  __int64 v34; // rax
  int v35; // r14d
  int v36; // r13d
  int v37; // r12d
  int v38; // ebx
  __int64 v39; // rax
  const unsigned __int16 *v40; // rdx
  const unsigned __int16 *v41; // r9
  int v42; // eax
  unsigned __int16 *v43; // rsi
  unsigned __int64 v44; // rbx
  unsigned __int64 v45; // rax
  const wchar_t **v46; // r8
  unsigned __int64 v47; // rax
  __int64 *v48; // rax
  __int64 v49; // rcx
  int v50; // eax
  __int64 i; // rdi
  PVOID v52; // r8
  unsigned __int64 *v54; // [rsp+20h] [rbp-E0h]
  unsigned __int64 *v55; // [rsp+20h] [rbp-E0h]
  struct _SECURITY_ATTRIBUTES *v56; // [rsp+20h] [rbp-E0h]
  struct _SECURITY_ATTRIBUTES *v57; // [rsp+20h] [rbp-E0h]
  struct _SECURITY_ATTRIBUTES *v58; // [rsp+20h] [rbp-E0h]
  struct _SECURITY_ATTRIBUTES *v59; // [rsp+20h] [rbp-E0h]
  unsigned int v60; // [rsp+28h] [rbp-D8h]
  unsigned int v61; // [rsp+28h] [rbp-D8h]
  __int64 v62; // [rsp+28h] [rbp-D8h]
  int v63; // [rsp+40h] [rbp-C0h] BYREF
  int v64; // [rsp+44h] [rbp-BCh] BYREF
  struct _SECURITY_ATTRIBUTES *v65; // [rsp+48h] [rbp-B8h] BYREF
  void *v66; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v67; // [rsp+58h] [rbp-A8h]
  __int128 v68; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v69; // [rsp+70h] [rbp-90h]
  int v70; // [rsp+78h] [rbp-88h]
  __int64 v71; // [rsp+80h] [rbp-80h]
  wchar_t pszDest[260]; // [rsp+88h] [rbp-78h] BYREF
  wchar_t v73[260]; // [rsp+290h] [rbp+190h] BYREF
  wchar_t Destination[260]; // [rsp+498h] [rbp+398h] BYREF
  __int64 v75; // [rsp+6A0h] [rbp+5A0h]
  __int128 v76; // [rsp+6A8h] [rbp+5A8h]
  __int128 v77; // [rsp+6B8h] [rbp+5B8h]
  __int128 v78; // [rsp+6C8h] [rbp+5C8h]
  __int128 v79; // [rsp+6D8h] [rbp+5D8h] BYREF
  __int128 v80; // [rsp+6E8h] [rbp+5E8h]
  __int128 v81; // [rsp+6F8h] [rbp+5F8h]
  __int128 v82; // [rsp+708h] [rbp+608h]
  __int128 v83; // [rsp+718h] [rbp+618h]
  __int128 v84; // [rsp+728h] [rbp+628h]
  __int64 v85; // [rsp+738h] [rbp+638h]
  int v86; // [rsp+740h] [rbp+640h]
  _OSVERSIONINFOEXW VersionInformation; // [rsp+7B0h] [rbp+6B0h] BYREF
  _DWORD v88[4]; // [rsp+8D0h] [rbp+7D0h] BYREF
  PVOID P[28]; // [rsp+8E0h] [rbp+7E0h]
  unsigned __int16 *v90; // [rsp+9C0h] [rbp+8C0h]
  char v91; // [rsp+9C8h] [rbp+8C8h]
  unsigned __int16 *v92; // [rsp+9E0h] [rbp+8E0h]
  char v93; // [rsp+9E8h] [rbp+8E8h]
  unsigned __int16 v94[48]; // [rsp+D50h] [rbp+C50h] BYREF
  unsigned __int16 v95[264]; // [rsp+DB0h] [rbp+CB0h] BYREF

  v67 = a2;
  LODWORD(v65) = 0;
  v64 = 0;
  v63 = 0;
  v76 = 0;
  v77 = 0;
  v78 = 0;
  GetProcessHeap();
  v76 = 0;
  v77 = 0;
  v78 = 0;
  ProcessHeap = GetProcessHeap();
  v78 = 0x10u;
  v79 = 0;
  *(_QWORD *)&v76 = ProcessHeap;
  v80 = 0;
  v77 = 0u;
  v81 = 0;
  *((_QWORD *)&v76 + 1) = 8;
  GetProcessHeap();
  v79 = 0;
  v80 = 0;
  v81 = 0;
  v5 = GetProcessHeap();
  v81 = 0x10u;
  v82 = 0;
  *(_QWORD *)&v79 = v5;
  v83 = 0;
  v80 = 0u;
  v84 = 0;
  *((_QWORD *)&v79 + 1) = 8;
  GetProcessHeap();
  v82 = 0;
  v83 = 0;
  v84 = 0;
  v6 = GetProcessHeap();
  v84 = 0x10u;
  *(_QWORD *)&v82 = v6;
  v83 = 0u;
  *((_QWORD *)&v82 + 1) = 8;
  StringCchCopyExW(pszDest, v7, L"compat", v8, v54, v60);
  StringCchCopyExW(v73, v9, L"troubleshooter", v10, v55, v61);
  v69 = 0;
  v68 = 0;
  v71 = 0;
  v70 = 0;
  v75 = 0;
  wcscpy_s(Destination, 0x104u, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OneSettings");
  OneCore::Base::Telemetry::OneSettingsQuery::GetRegistryRedirectionLocation(
    v11,
    Destination,
    v12,
    v13,
    (const unsigned __int16 *)v56);
  v85 = 0;
  v86 = 0;
  v14 = 0;
  v66 = 0;
  memset_0(v95, 0, 0x208u);
  memset_0(v88, 0, 0x480u);
  *a2 = 0;
  AslLogCallPrintf(3, "GetOnesettingsValues", 67, "In GetOnesettingsValues");
  if ( `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCore'::`2'::AlreadyChecked )
  {
    IsWin10TelemetryTypeAllowed = `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCore'::`2'::IsOptedIn;
  }
  else
  {
    VersionInformation.dwOSVersionInfoSize = 284;
    *(_OWORD *)&VersionInformation.dwMajorVersion = 0;
    memset_0(VersionInformation.szCSDVersion, 0, sizeof(VersionInformation.szCSDVersion));
    *(_QWORD *)&VersionInformation.wServicePackMajor = 0;
    v15 = VerSetConditionMask(0, 2u, 3u);
    v16 = VerSetConditionMask(v15, 1u, 3u);
    v17 = VerSetConditionMask(v16, 0x20u, 3u);
    *(_QWORD *)&VersionInformation.dwMajorVersion = 10;
    VersionInformation.wServicePackMajor = 0;
    if ( VerifyVersionInfoW(&VersionInformation, 0x23u, v17) )
      IsWin10TelemetryTypeAllowed = Windows::Compat::Shared::Telemetry::PermissionsHelper::IsWin10TelemetryTypeAllowed(v18);
    else
      IsWin10TelemetryTypeAllowed = (unsigned int)WinSqmIsOptedInEx(4) == 1;
    `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCore'::`2'::IsOptedIn = IsWin10TelemetryTypeAllowed;
    `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCore'::`2'::AlreadyChecked = 1;
  }
  if ( !IsWin10TelemetryTypeAllowed )
  {
    v20 = -2147467259;
    AslLogCallPrintf(3, "GetOnesettingsValues", 72, "Not allowed to query cloud");
    goto LABEL_67;
  }
  v21 = AslFileMappingCreate(&v66, a1);
  v20 = v21 | 0x10000000;
  if ( v21 < 0 )
  {
    AslLogCallPrintf(1, "GetOnesettingsValues", 82, "AslFileMappingCreate failed, 0x%x", v21 | 0x10000000);
    v14 = v66;
    goto LABEL_67;
  }
  v14 = v66;
  Attributes = AslFileAllocAndGetAttributes(v88, v66, 384);
  v20 = Attributes | 0x10000000;
  if ( Attributes < 0 )
  {
    v23 = "AslFileAllocAndGetAttributes failed, 0x%x";
    v24 = 87;
LABEL_66:
    LODWORD(v57) = v20;
    AslLogCallPrintf(1, "GetOnesettingsValues", v24, v23, v57);
    goto LABEL_67;
  }
  v25 = (unsigned __int16 *)&word_18001DAC4;
  if ( (v93 & 1) != 0 )
  {
    v26 = (unsigned __int16 *)&word_18001DAC4;
    if ( v92 )
      v26 = v92;
    v27 = StringCchCatW(v95, 0x104u, v26);
    v20 = v27;
    if ( v27 < 0 )
    {
      v28 = 93;
LABEL_18:
      LODWORD(v57) = v27;
      AslLogCallPrintf(1, "GetOnesettingsValues", v28, "StringCchCat failed, 0x%x", v57);
      goto LABEL_67;
    }
  }
  v27 = StringCchCatW(v95, 0x104u, L"#");
  v20 = v27;
  if ( v27 < 0 )
  {
    v28 = 97;
    goto LABEL_18;
  }
  if ( (v91 & 1) != 0 )
  {
    if ( v90 )
      v25 = v90;
    v27 = StringCchCatW(v95, 0x104u, v25);
    v20 = v27;
    if ( v27 < 0 )
    {
      v28 = 103;
      goto LABEL_18;
    }
  }
  v27 = StringCchCatW(v95, 0x104u, L"#");
  v20 = v27;
  if ( v27 < 0 )
  {
    v28 = 107;
    goto LABEL_18;
  }
  v29 = wcsrchr(a1, 0x5Cu);
  if ( v29 )
    v30 = v29 + 1;
  else
    v30 = a1;
  v31 = StringCchCatW(v95, 0x104u, v30);
  v20 = v31;
  if ( v31 < 0 )
  {
    LODWORD(v57) = v31;
    AslLogCallPrintf(1, "GetOnesettingsValues", 120, "StringCchCat failed, 0x%x", v57);
    goto LABEL_67;
  }
  AslLogCallPrintf(3, "GetOnesettingsValues", 122, "product name # company name # exe name: %ws", v95);
  VersionForPath = AslFileGetVersionForPath(&v65, &v64, &v63, a1);
  v20 = VersionForPath | 0x10000000;
  if ( VersionForPath < 0 )
  {
    v23 = "AslFileGetVersionForPath failed with 0x%x";
    v24 = 130;
    goto LABEL_66;
  }
  v33 = -1;
  v34 = -1;
  do
    ++v34;
  while ( v95[v34] );
  if ( !v34 )
  {
    v20 = -2147024809;
    goto LABEL_65;
  }
  v20 = RtlNameValueArray::Append((RtlNameValueArray *)&v79, L"app", v95);
  if ( v20 < 0 )
  {
LABEL_65:
    v23 = "AddParameter failed with 0x%x";
    v24 = 133;
    goto LABEL_66;
  }
  v35 = v63;
  v36 = (int)v65;
  v37 = v64;
  LODWORD(v62) = v63;
  LODWORD(v57) = v64;
  v38 = StringCchPrintfW(v94, 0x2Cu, L"%d.%d.%d.%d", (unsigned int)v65, v57, v62, 0);
  if ( v38 >= 0 )
  {
    v39 = -1;
    do
      ++v39;
    while ( v94[v39] );
    if ( v39 )
    {
      v38 = RtlNameValueArray::Append((RtlNameValueArray *)&v79, L"appver", v94);
      if ( v38 >= 0 )
        v38 = 0;
    }
    else
    {
      v38 = -2147024809;
    }
  }
  AslLogCallPrintf(3, "GetOnesettingsValues", 136, "AddParameterAppVer %d.%d.%d; result: 0x%x.", v36, v37, v35, v38);
  v42 = OneCore::Base::Telemetry::OneSettingsQuery::Query(
          (OneCore::Base::Telemetry::OneSettingsQuery *)&v68,
          v40,
          IsWin10TelemetryTypeAllowed,
          v41,
          v58);
  v20 = v42;
  if ( v42 >= 0 )
  {
    v43 = v67;
    v44 = 0;
    v45 = v77;
    *v67 = 0;
    if ( !v45 )
      goto LABEL_55;
    while ( 1 )
    {
      v46 = 0;
      if ( v44 < v45 )
      {
        v47 = *((_QWORD *)&v76 + 1) * v44;
        if ( !is_mul_ok(*((unsigned __int64 *)&v76 + 1), v44)
          || (v46 = (const wchar_t **)(*((_QWORD *)&v78 + 1) + v47), *((_QWORD *)&v78 + 1) + v47 < *((_QWORD *)&v78 + 1)) )
        {
          v46 = 0;
        }
      }
      if ( !_wcsicmp(*v46, L"RECOMMENDEDLAYER") )
        break;
      v45 = v77;
      if ( ++v44 >= (unsigned __int64)v77 )
        goto LABEL_55;
    }
    v48 = 0;
    if ( v44 < (unsigned __int64)v77 )
    {
      if ( !is_mul_ok(*((unsigned __int64 *)&v76 + 1), v44)
        || (v48 = (__int64 *)(*((_QWORD *)&v78 + 1) + *((_QWORD *)&v76 + 1) * v44),
            (unsigned __int64)v48 < *((_QWORD *)&v78 + 1)) )
      {
        v48 = 0;
      }
    }
    v49 = *v48;
    do
      ++v33;
    while ( *(_WORD *)(v49 + 2 * v33) );
    v50 = StringCchCopyW(v43, 0x104u, (const unsigned __int16 *)(v49 + 2 + 2 * v33));
    v20 = v50;
    if ( v50 < 0 )
    {
      LODWORD(v59) = v50;
      AslLogCallPrintf(1, "GetOnesettingsValues", 146, "SettingsQuery.GetSettings failed with 0x%x", v59);
    }
    else
    {
LABEL_55:
      AslLogCallPrintf(3, "GetOnesettingsValues", 148, "Cloud response of recommended layer: %ws", v43);
      v20 = 0;
    }
  }
  else
  {
    LODWORD(v59) = v42;
    AslLogCallPrintf(1, "GetOnesettingsValues", 143, "SettingsQuery.Query failed with 0x%x", v59);
  }
LABEL_67:
  for ( i = 0; i != 36; ++i )
  {
    if ( ((__int64)P[4 * i + 1] & 1) != 0 && v88[8 * i] == 4 && ((__int64)P[4 * i + 1] & 4) != 0 )
    {
      v52 = P[4 * i];
      if ( v52 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v52);
    }
  }
  if ( v14 )
    AslFileMappingDelete(v14);
  OneCore::Base::Telemetry::OneSettingsQuery::~OneSettingsQuery((OneCore::Base::Telemetry::OneSettingsQuery *)&v68);
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x1800039c8  mov     [rsp-8+arg_10], rbx
0x1800039cd  push    rbp
0x1800039ce  push    rsi
0x1800039cf  push    rdi
0x1800039d0  push    r12
0x1800039d2  push    r13
0x1800039d4  push    r14
0x1800039d6  push    r15
0x1800039d8  lea     rbp, [rsp-0ED0h]
0x1800039e0  sub     rsp, 0FD0h
0x1800039e7  mov     rax, cs:__security_cookie
0x1800039ee  xor     rax, rsp
0x1800039f1  mov     [rbp+0F00h+var_40], rax
0x1800039f8  xorps   xmm0, xmm0
0x1800039fb  mov     [rsp+1000h+var_FA8], rdx
0x180003a00  xor     r12d, r12d
0x180003a03  mov     rbx, rdx
0x180003a06  mov     dword ptr [rsp+1000h+var_FB8], r12d
0x180003a0b  mov     r14, rcx
0x180003a0e  mov     [rsp+1000h+var_FBC], r12d
0x180003a13  mov     [rsp+1000h+var_FC0], r12d
0x180003a18  movups  [rbp+0F00h+var_958], xmm0
0x180003a1f  movups  [rbp+0F00h+var_948], xmm0
0x180003a26  movups  [rbp+0F00h+var_938], xmm0
0x180003a2d  call    cs:__imp_GetProcessHeap
0x180003a33  xorps   xmm0, xmm0
0x180003a36  lea     esi, [r12+10h]
0x180003a3b  movups  [rbp+0F00h+var_958], xmm0
0x180003a42  lea     edi, [rsi-8]
0x180003a45  movups  [rbp+0F00h+var_948], xmm0
0x180003a4c  movups  [rbp+0F00h+var_938], xmm0
0x180003a53  call    cs:__imp_GetProcessHeap
0x180003a59  xorps   xmm0, xmm0
0x180003a5c  mov     qword ptr [rbp+0F00h+var_938], rsi
0x180003a63  movups  [rbp+0F00h+var_928], xmm0
0x180003a6a  mov     qword ptr [rbp+0F00h+var_958], rax
0x180003a71  movups  [rbp+0F00h+var_918], xmm0
0x180003a78  mov     qword ptr [rbp+0F00h+var_948], r12
0x180003a7f  movups  [rbp+0F00h+var_908], xmm0
0x180003a86  mov     qword ptr [rbp+0F00h+var_948+8], r12
0x180003a8d  mov     qword ptr [rbp+0F00h+var_938+8], r12
0x180003a94  mov     qword ptr [rbp+0F00h+var_958+8], rdi
0x180003a9b  call    cs:__imp_GetProcessHeap
0x180003aa1  xorps   xmm0, xmm0
0x180003aa4  movups  [rbp+0F00h+var_928], xmm0
0x180003aab  movups  [rbp+0F00h+var_918], xmm0
0x180003ab2  movups  [rbp+0F00h+var_908], xmm0
0x180003ab9  call    cs:__imp_GetProcessHeap
0x180003abf  xorps   xmm0, xmm0
0x180003ac2  mov     qword ptr [rbp+0F00h+var_908], rsi
0x180003ac9  movups  [rbp+0F00h+var_8F8], xmm0
0x180003ad0  mov     qword ptr [rbp+0F00h+var_928], rax
0x180003ad7  movups  [rbp+0F00h+var_8E8], xmm0
0x180003ade  mov     qword ptr [rbp+0F00h+var_918], r12
0x180003ae5  movups  [rbp+0F00h+var_8D8], xmm0
0x180003aec  mov     qword ptr [rbp+0F00h+var_918+8], r12
0x180003af3  mov     qword ptr [rbp+0F00h+var_908+8], r12
0x180003afa  mov     qword ptr [rbp+0F00h+var_928+8], rdi
0x180003b01  call    cs:__imp_GetProcessHeap
0x180003b07  xorps   xmm0, xmm0
0x180003b0a  movups  [rbp+0F00h+var_8F8], xmm0
0x180003b11  movups  [rbp+0F00h+var_8E8], xmm0
0x180003b18  movups  [rbp+0F00h+var_8D8], xmm0
0x180003b1f  call    cs:__imp_GetProcessHeap
0x180003b25  lea     r8, aCompat; "compat"
0x180003b2c  mov     qword ptr [rbp+0F00h+var_8D8], rsi
0x180003b33  lea     rcx, [rbp+0F00h+pszDest]; pszDest
0x180003b37  mov     qword ptr [rbp+0F00h+var_8F8], rax
0x180003b3e  mov     qword ptr [rbp+0F00h+var_8E8], r12
0x180003b45  mov     qword ptr [rbp+0F00h+var_8E8+8], r12
0x180003b4c  mov     qword ptr [rbp+0F00h+var_8D8+8], r12
0x180003b53  mov     qword ptr [rbp+0F00h+var_8F8+8], rdi
0x180003b5a  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180003b5f  lea     r8, aTroubleshooter; "troubleshooter"
0x180003b66  lea     rcx, [rbp+0F00h+var_D70]; pszDest
0x180003b6d  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180003b72  xorps   xmm0, xmm0
0x180003b75  mov     [rsp+1000h+var_F90], r12
0x180003b7a  lea     r8, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180003b81  movdqa  [rsp+1000h+var_FA0], xmm0
0x180003b87  mov     edx, 104h; SizeInWords
0x180003b8c  mov     [rbp+0F00h+var_F80], r12
0x180003b90  lea     rcx, [rbp+0F00h+Destination]; Destination
0x180003b97  mov     [rsp+1000h+var_F88], r12d
0x180003b9c  mov     [rbp+0F00h+var_960], r12
0x180003ba3  call    cs:__imp_wcscpy_s
0x180003ba9  lea     rdx, [rbp+0F00h+Destination]; unsigned __int16 *
0x180003bb0  call    ?GetRegistryRedirectionLocation@OneSettingsQuery@Telemetry@Base@OneCore@@QEAAJPEAGKPEBG1@Z; OneCore::Base::Telemetry::OneSettingsQuery::GetRegistryRedirectionLocation(ushort *,ulong,ushort const *,ushort const *)
0x180003bb5  xor     edx, edx; Val
0x180003bb7  mov     [rbp+0F00h+var_8C8], r12
0x180003bbe  mov     r8d, 208h; Size
0x180003bc4  mov     [rbp+0F00h+var_8C0], r12d
0x180003bcb  mov     r15d, r12d
0x180003bce  mov     [rsp+1000h+var_FB0], r12
0x180003bd3  lea     rcx, [rbp+0F00h+var_250]; void *
0x180003bda  call    memset_0
0x180003bdf  xor     edx, edx; Val
0x180003be1  lea     rcx, [rbp+0F00h+var_730]; void *
0x180003be8  mov     r8d, 480h; Size
0x180003bee  call    memset_0
0x180003bf3  lea     rdi, aGetonesettings; "GetOnesettingsValues"
0x180003bfa  mov     [rbx], r12w
0x180003bfe  mov     rdx, rdi
0x180003c01  lea     r9, aInGetonesettin; "In GetOnesettingsValues"
0x180003c08  lea     r8d, [r12+43h]
0x180003c0d  lea     ecx, [rsi-0Dh]
0x180003c10  call    AslLogCallPrintf
0x180003c15  cmp     cs:?AlreadyChecked@?1??IsOptedIntoCore@PermissionsHelper@Telemetry@Shared@Compat@Windows@@SA_N_N@Z@4_NA, r12b; bool `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCore(bool)'::`2'::AlreadyChecked
0x180003c1c  lea     r13d, [r12+1]
0x180003c21  jnz     loc_180003CD8
0x180003c27  xorps   xmm0, xmm0
0x180003c2a  mov     [rbp+0F00h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x180003c34  xor     edx, edx; Val
0x180003c36  lea     rcx, [rbp+0F00h+VersionInformation.szCSDVersion]; void *
0x180003c3d  mov     r8d, 100h; Size
0x180003c43  movups  xmmword ptr [rbp+0F00h+VersionInformation.dwMajorVersion], xmm0
0x180003c4a  call    memset_0
0x180003c4f  mov     r8b, 3; Condition
0x180003c52  mov     qword ptr [rbp+0F00h+VersionInformation.wServicePackMajor], r12
0x180003c59  lea     edx, [rsi-0Eh]; TypeMask
0x180003c5c  xor     ecx, ecx; ConditionMask
0x180003c5e  call    cs:__imp_VerSetConditionMask
0x180003c64  mov     r8b, 3; Condition
0x180003c67  mov     edx, r13d; TypeMask
0x180003c6a  mov     rcx, rax; ConditionMask
0x180003c6d  call    cs:__imp_VerSetConditionMask
0x180003c73  mov     r8b, 3; Condition
0x180003c76  lea     edx, [rsi+10h]; TypeMask
0x180003c79  mov     rcx, rax; ConditionMask
0x180003c7c  call    cs:__imp_VerSetConditionMask
0x180003c82  lea     edx, [rsi+13h]; dwTypeMask
0x180003c85  mov     qword ptr [rbp+0F00h+VersionInformation.dwMajorVersion], 0Ah
0x180003c90  mov     r8, rax; dwlConditionMask
0x180003c93  mov     [rbp+0F00h+VersionInformation.wServicePackMajor], r12w
0x180003c9b  lea     rcx, [rbp+0F00h+VersionInformation]; lpVersionInformation
0x180003ca2  call    cs:__imp_VerifyVersionInfoW
0x180003ca8  test    eax, eax
0x180003caa  jz      short loc_180003CB6
0x180003cac  call    ?IsWin10TelemetryTypeAllowed@PermissionsHelper@Telemetry@Shared@Compat@Windows@@CA_NK@Z; Windows::Compat::Shared::Telemetry::PermissionsHelper::IsWin10TelemetryTypeAllowed(ulong)
0x180003cb1  mov     sil, al
0x180003cb4  jmp     short loc_180003CC8
0x180003cb6  mov     ecx, 4
0x180003cbb  call    cs:__imp_WinSqmIsOptedInEx
0x180003cc1  cmp     eax, r13d
0x180003cc4  setz    sil
0x180003cc8  mov     cs:?IsOptedIn@?1??IsOptedIntoCore@PermissionsHelper@Telemetry@Shared@Compat@Windows@@SA_N_N@Z@4_NA, sil; bool `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCore(bool)'::`2'::IsOptedIn
0x180003ccf  mov     cs:?AlreadyChecked@?1??IsOptedIntoCore@PermissionsHelper@Telemetry@Shared@Compat@Windows@@SA_N_N@Z@4_NA, r13b; bool `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCore(bool)'::`2'::AlreadyChecked
0x180003cd6  jmp     short loc_180003CDF
0x180003cd8  mov     sil, cs:?IsOptedIn@?1??IsOptedIntoCore@PermissionsHelper@Telemetry@Shared@Compat@Windows@@SA_N_N@Z@4_NA; bool `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCore(bool)'::`2'::IsOptedIn
0x180003cdf  test    sil, sil
0x180003ce2  jnz     short loc_180003D07
0x180003ce4  mov     r8d, 48h ; 'H'
0x180003cea  lea     r9, aNotAllowedToQu; "Not allowed to query cloud"
0x180003cf1  mov     rdx, rdi
0x180003cf4  mov     ebx, 80004005h
0x180003cf9  lea     ecx, [r8-45h]
0x180003cfd  call    AslLogCallPrintf
0x180003d02  jmp     loc_180004161
0x180003d07  mov     rdx, r14
0x180003d0a  lea     rcx, [rsp+1000h+var_FB0]
0x180003d0f  call    AslFileMappingCreate
0x180003d14  mov     ebx, eax
0x180003d16  or      ebx, 10000000h
0x180003d1c  jge     short loc_180003D44
0x180003d1e  lea     r9, aAslfilemapping_0; "AslFileMappingCreate failed, 0x%x"
0x180003d25  mov     dword ptr [rsp+1000h+var_FE0], ebx
0x180003d29  mov     r8d, 52h ; 'R'
0x180003d2f  mov     rdx, rdi
0x180003d32  mov     ecx, r13d
0x180003d35  call    AslLogCallPrintf
0x180003d3a  mov     r15, [rsp+1000h+var_FB0]
0x180003d3f  jmp     loc_180004161
0x180003d44  mov     r15, [rsp+1000h+var_FB0]
0x180003d49  lea     rcx, [rbp+0F00h+var_730]
0x180003d50  mov     rdx, r15
0x180003d53  mov     r8d, 180h
0x180003d59  call    AslFileAllocAndGetAttributes
0x180003d5e  mov     ebx, eax
0x180003d60  or      ebx, 10000000h
0x180003d66  jge     short loc_180003D7D
0x180003d68  lea     r9, aAslfileallocan_0; "AslFileAllocAndGetAttributes failed, 0x"...
0x180003d6f  mov     r8d, 57h ; 'W'
0x180003d75  mov     rdx, rdi
0x180003d78  jmp     loc_180004155
0x180003d7d  lea     rdi, word_18001DAC4
0x180003d84  test    [rbp+0F00h+var_618], r13b
0x180003d8b  jz      short loc_180003DD2
0x180003d8d  mov     rax, [rbp+0F00h+var_620]
0x180003d94  lea     rcx, [rbp+0F00h+var_250]; unsigned __int16 *
0x180003d9b  test    rax, rax
0x180003d9e  mov     r8, rdi
0x180003da1  mov     edx, 104h; unsigned __int64
0x180003da6  cmovnz  r8, rax; unsigned __int16 *
0x180003daa  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003daf  mov     ebx, eax
0x180003db1  test    eax, eax
0x180003db3  jns     short loc_180003DD2
0x180003db5  mov     r8d, 5Dh ; ']'
0x180003dbb  lea     r9, aStringcchcatFa; "StringCchCat failed, 0x%x"
0x180003dc2  mov     dword ptr [rsp+1000h+var_FE0], eax
0x180003dc6  lea     rdx, aGetonesettings; "GetOnesettingsValues"
0x180003dcd  jmp     loc_180004159
0x180003dd2  lea     r8, asc_18001D904; "#"
0x180003dd9  mov     edx, 104h; unsigned __int64
0x180003dde  lea     rcx, [rbp+0F00h+var_250]; unsigned __int16 *
0x180003de5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003dea  mov     ebx, eax
0x180003dec  test    eax, eax
0x180003dee  jns     short loc_180003DF8
0x180003df0  mov     r8d, 61h ; 'a'
0x180003df6  jmp     short loc_180003DBB
0x180003df8  test    [rbp+0F00h+var_638], r13b
0x180003dff  jz      short loc_180003E33
0x180003e01  mov     rax, [rbp+0F00h+var_640]
0x180003e08  lea     rcx, [rbp+0F00h+var_250]; unsigned __int16 *
0x180003e0f  test    rax, rax
0x180003e12  cmovnz  rdi, rax
0x180003e16  mov     r8, rdi; unsigned __int16 *
0x180003e19  mov     edi, 104h
0x180003e1e  mov     edx, edi; unsigned __int64
0x180003e20  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003e25  mov     ebx, eax
0x180003e27  test    eax, eax
0x180003e29  jns     short loc_180003E38
0x180003e2b  mov     r8d, 67h ; 'g'
0x180003e31  jmp     short loc_180003DBB
0x180003e33  mov     edi, 104h
0x180003e38  lea     r8, asc_18001D904; "#"
0x180003e3f  mov     rdx, rdi; unsigned __int64
0x180003e42  lea     rcx, [rbp+0F00h+var_250]; unsigned __int16 *
0x180003e49  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003e4e  mov     ebx, eax
0x180003e50  test    eax, eax
0x180003e52  jns     short loc_180003E5F
0x180003e54  mov     r8d, 6Bh ; 'k'
0x180003e5a  jmp     loc_180003DBB
0x180003e5f  mov     edx, 5Ch ; '\'; Ch
0x180003e64  mov     rcx, r14; Str
0x180003e67  call    cs:__imp_wcsrchr
0x180003e6d  test    rax, rax
0x180003e70  jnz     short loc_180003E77
0x180003e72  mov     rax, r14
0x180003e75  jmp     short loc_180003E7B
0x180003e77  add     rax, 2
0x180003e7b  mov     r8, rax; unsigned __int16 *
0x180003e7e  lea     rcx, [rbp+0F00h+var_250]; unsigned __int16 *
0x180003e85  mov     rdx, rdi; unsigned __int64
0x180003e88  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003e8d  lea     rdx, aGetonesettings; "GetOnesettingsValues"
0x180003e94  mov     ebx, eax
0x180003e96  test    eax, eax
0x180003e98  jns     short loc_180003EB0
0x180003e9a  mov     dword ptr [rsp+1000h+var_FE0], eax
0x180003e9e  lea     r9, aStringcchcatFa; "StringCchCat failed, 0x%x"
0x180003ea5  mov     r8d, 78h ; 'x'
0x180003eab  jmp     loc_180004159
0x180003eb0  mov     r8d, 7Ah ; 'z'
0x180003eb6  lea     rax, [rbp+0F00h+var_250]
0x180003ebd  lea     r9, aProductNameCom; "product name # company name # exe name:"...
0x180003ec4  mov     [rsp+1000h+var_FE0], rax
0x180003ec9  lea     ecx, [r8-77h]
0x180003ecd  call    AslLogCallPrintf
0x180003ed2  mov     r9, r14
0x180003ed5  lea     r8, [rsp+1000h+var_FC0]
0x180003eda  lea     rdx, [rsp+1000h+var_FBC]
0x180003edf  lea     rcx, [rsp+1000h+var_FB8]
0x180003ee4  call    AslFileGetVersionForPath
0x180003ee9  mov     ebx, eax
0x180003eeb  or      ebx, 10000000h
0x180003ef1  jge     short loc_180003F05
0x180003ef3  lea     r9, aAslfilegetvers; "AslFileGetVersionForPath failed with 0x"...
0x180003efa  mov     r8d, 82h
0x180003f00  jmp     loc_18000414E
0x180003f05  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180003f09  lea     rcx, [rbp+0F00h+var_250]
0x180003f10  mov     rax, rdi
0x180003f13  inc     rax
0x180003f16  cmp     [rcx+rax*2], r12w
0x180003f1b  jnz     short loc_180003F13
0x180003f1d  test    rax, rax
0x180003f20  jz      loc_18000413C
0x180003f26  lea     r8, [rbp+0F00h+var_250]; unsigned __int16 *
0x180003f2d  lea     rdx, aApp; "app"
0x180003f34  lea     rcx, [rbp+0F00h+var_928]; this
0x180003f3b  call    ?Append@RtlNameValueArray@@QEAAKPEBG0@Z; RtlNameValueArray::Append(ushort const *,ushort const *)
0x180003f40  mov     ebx, eax
0x180003f42  test    eax, eax
0x180003f44  js      loc_180004141
0x180003f4a  mov     r14d, [rsp+1000h+var_FC0]
0x180003f4f  lea     r8, aDDDD; "%d.%d.%d.%d"
0x180003f56  mov     r13d, dword ptr [rsp+1000h+var_FB8]
0x180003f5b  lea     rcx, [rbp+0F00h+var_2B0]; unsigned __int16 *
0x180003f62  mov     [rsp+1000h+var_FD0], r12d
0x180003f67  mov     r9d, r13d
0x180003f6a  mov     r12d, [rsp+1000h+var_FBC]
0x180003f6f  mov     edx, 2Ch ; ','; unsigned __int64
0x180003f74  mov     dword ptr [rsp+1000h+var_FD8], r14d
0x180003f79  mov     dword ptr [rsp+1000h+var_FE0], r12d
0x180003f7e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003f83  xor     ecx, ecx
  ... truncated ...
```
