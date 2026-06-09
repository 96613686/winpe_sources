# LOGGING::ActivateLogging(IHttpContext *,int)

- ea: `0x180001cd0`
- end: `0x180002566`
- name: `?ActivateLogging@LOGGING@@QEAAJPEAVIHttpContext@@H@Z`
- size: `2198`
- prototype: `__int64 __fastcall(LOGGING *this, struct IHttpContext *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180001080`

## callees

- `0x180001cd0`
- `0x1800025b0`
- `0x180003194`
- `0x180004afc`
- `0x1800056f2`
- `0x180005720`
- `0x180006010`

## import_xrefs

- `msvcrt!_ultoa_s` at `0x180001f5e`
- `msvcrt!_ultoa_s` at `0x180001f5e`
- `msvcrt!_wcsicmp` at `0x18000223c`
- `msvcrt!_wcsicmp` at `0x18000225a`
- `msvcrt!_wcsicmp` at `0x180002278`
- `msvcrt!_wcsicmp` at `0x18000223c`
- `msvcrt!_wcsicmp` at `0x18000225a`
- `msvcrt!_wcsicmp` at `0x180002278`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180002218`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180002218`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800021f7`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002446`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800024a8`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800021f7`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002446`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800024a8`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x1800021df`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x1800021df`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800021c0`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800021c0`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x180002128`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x180002128`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z` at `0x180002114`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z` at `0x18000245e`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z` at `0x180002114`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z` at `0x18000245e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002095`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002095`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180001f48`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180001f48`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180001f25`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180001f3d`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180001f25`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180001f3d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000222c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000224a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180002268`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000222c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000224a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180002268`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180001d5e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180001d5e`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180001f16`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180001f16`
- `iisutil!?QuerySize@STRA@@QEBAKXZ` at `0x180001f30`
- `iisutil!?QuerySize@STRA@@QEBAKXZ` at `0x180001f30`
- `iisutil!?SyncWithBuffer@STRA@@QEAAXXZ` at `0x1800020bb`
- `iisutil!?SyncWithBuffer@STRA@@QEAAXXZ` at `0x1800020bb`

## string_xrefs

- `0x180002195`: `customLogPluginClsid`

## pseudocode

```c
__int64 __fastcall LOGGING::ActivateLogging(LOGGING *this, struct IHttpContext *a2)
{
  int v3; // r12d
  LOGGING *v4; // r14
  CUSTOM_LOG_FIELDS *v5; // r13
  __int64 (__fastcall ***v6)(_QWORD, GUID *, __int64 *); // rax
  unsigned int v7; // edx
  int v8; // ebx
  __int64 v9; // rdi
  __int64 v10; // r15
  STRA *v11; // r14
  unsigned int CCH; // edi
  unsigned int v13; // esi
  __int64 v14; // rdi
  char *Str; // rax
  __int64 (__fastcall *v17)(__int64); // rax
  const unsigned __int16 *v18; // rax
  int v19; // eax
  const unsigned __int16 *v20; // rax
  const wchar_t *v21; // rax
  const wchar_t *v22; // rax
  const wchar_t *v23; // rax
  __int64 v24; // rdi
  __int64 v25; // rax
  bool v26; // cf
  size_t v27; // rax
  _QWORD *v28; // rax
  CUSTOM_LOG_FIELDS *i; // rsi
  unsigned int j; // edi
  unsigned int v31; // eax
  _DWORD *v32; // rsi
  bool v33; // zf
  __int64 v34; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v35; // [rsp+50h] [rbp-B8h] BYREF
  unsigned int v36; // [rsp+58h] [rbp-B0h] BYREF
  int v37; // [rsp+5Ch] [rbp-ACh] BYREF
  int v38; // [rsp+60h] [rbp-A8h] BYREF
  int v39; // [rsp+64h] [rbp-A4h] BYREF
  int v40; // [rsp+68h] [rbp-A0h] BYREF
  int v41; // [rsp+6Ch] [rbp-9Ch] BYREF
  __int64 v42; // [rsp+70h] [rbp-98h] BYREF
  __int64 v43; // [rsp+78h] [rbp-90h] BYREF
  __int64 v44; // [rsp+80h] [rbp-88h] BYREF
  __int64 v45; // [rsp+88h] [rbp-80h] BYREF
  __int64 v46; // [rsp+90h] [rbp-78h] BYREF
  __int64 v47; // [rsp+98h] [rbp-70h] BYREF
  __int64 v48; // [rsp+A0h] [rbp-68h] BYREF
  const unsigned __int16 *v49; // [rsp+A8h] [rbp-60h] BYREF
  const unsigned __int16 *v50; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v51; // [rsp+B8h] [rbp-50h] BYREF
  const unsigned __int16 *v52; // [rsp+C0h] [rbp-48h] BYREF
  LOGGING *v53; // [rsp+C8h] [rbp-40h]
  _BYTE v54[56]; // [rsp+D0h] [rbp-38h] BYREF
  unsigned __int16 v55[64]; // [rsp+108h] [rbp+0h] BYREF

  v3 = g_fDoCentralBinaryLogging;
  v4 = this;
  v53 = this;
  v44 = 0;
  v48 = 0;
  v34 = 0;
  v47 = 0;
  v39 = 0;
  v40 = 1;
  v38 = 0;
  v49 = 0;
  memset_0(v55, 0, sizeof(v55));
  STRU::STRU((STRU *)v54, v55, 0x40u);
  v5 = 0;
  v43 = 0;
  v46 = 0;
  v45 = 0;
  v35 = 0;
  v51 = 0;
  v36 = 0;
  v37 = 0;
  v50 = 0;
  v52 = 0;
  LODWORD(v42) = 0;
  v41 = 0;
  v6 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)s_pGlobalInfo + 56LL))(s_pGlobalInfo);
  v8 = (**v6)(v6, &IID_INativeConfigurationSystem, &v44);
  if ( v8 < 0 )
    goto LABEL_12;
  v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, __int64 *, __int64 *, _QWORD))(*(_QWORD *)v44 + 24LL))(
         v44,
         L"system.applicationHost/log",
         L"MACHINE/WEBROOT/APPHOST",
         &v43,
         &v51,
         0);
  if ( v8 < 0 )
    goto LABEL_12;
  v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v43 + 48LL))(
         v43,
         L"centralLogFileMode",
         &v41,
         0,
         0);
  if ( v8 < 0 )
    goto LABEL_12;
  v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v44 + 56LL))(v44, &v48);
  if ( v8 < 0 )
    goto LABEL_12;
  v9 = (**(__int64 (__fastcall ***)(struct IHttpContext *))a2)(a2);
  v10 = (**(unsigned int (__fastcall ***)(__int64))v9)(v9);
  v8 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, _QWORD))(*(_QWORD *)v48 + 32LL))(v48, v10, &v47, 0);
  if ( v8 < 0 )
    goto LABEL_12;
  v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v47 + 32LL))(v47, L"logFile", &v34);
  if ( v8 < 0 )
    goto LABEL_12;
  v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v34 + 72LL))(
         v34,
         L"logSiteId",
         &v39,
         0,
         0);
  if ( v8 < 0 )
    goto LABEL_12;
  if ( v39 )
  {
    v11 = (LOGGING *)((char *)v4 + 16);
    v8 = STRA::Copy(v11, "W3SVC", 5u);
    if ( v8 < 0 )
      goto LABEL_12;
    CCH = STRA::QueryCCH(v11);
    v13 = STRA::QuerySize(v11) - CCH;
    v14 = STRA::QueryCCH(v11);
    Str = STRA::QueryStr(v11);
    if ( _ultoa_s(v10, &Str[v14], v13, 10) )
    {
      v8 = -2147418113;
      goto LABEL_12;
    }
    STRA::SyncWithBuffer(v11);
    v4 = v53;
  }
  else
  {
    v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v43 + 72LL))(
           v43,
           L"logInUTF8",
           &v40,
           0,
           0);
    if ( v8 < 0 )
      goto LABEL_12;
    v17 = *(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL);
    if ( v40 )
    {
      v18 = (const unsigned __int16 *)v17(v9);
      v19 = STRA::CopyWToUTF8Unescaped((LOGGING *)((char *)v4 + 16), v18);
    }
    else
    {
      v20 = (const unsigned __int16 *)v17(v9);
      v19 = STRA::CopyW((LOGGING *)((char *)v4 + 16), v20);
    }
    v8 = v19;
    if ( v19 < 0 )
      goto LABEL_12;
  }
  if ( v3 )
  {
    *((_DWORD *)v4 + 3) = 1;
    goto LABEL_12;
  }
  v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v34 + 48LL))(
         v34,
         L"logFormat",
         &v38,
         0,
         0);
  if ( v8 >= 0 )
  {
    if ( v38 != 3 )
      goto LABEL_53;
    v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v34 + 64LL))(
           v34,
           L"customLogPluginClsid",
           &v49,
           0,
           0);
    if ( v8 < 0 )
      goto LABEL_12;
    if ( *v49 == 123 )
    {
      v8 = STRU::Copy((STRU *)v54, v49);
      if ( v8 < 0 )
        goto LABEL_12;
    }
    else
    {
      v8 = STRU::Copy((STRU *)v54, L"{", 1u);
      if ( v8 < 0 )
        goto LABEL_12;
      v8 = STRU::Append((STRU *)v54, v49);
      if ( v8 < 0 )
        goto LABEL_12;
      v8 = STRU::Append((STRU *)v54, L"}", 1u);
      if ( v8 < 0 )
        goto LABEL_12;
    }
    v21 = STRU::QueryStr((STRU *)v54);
    if ( !_wcsicmp(v21, L"{FF16065F-DE82-11CF-BC0A-00AA006111E0}")
      || (v22 = STRU::QueryStr((STRU *)v54), !_wcsicmp(v22, L"{FF160657-DE82-11CF-BC0A-00AA006111E0}"))
      || (v23 = STRU::QueryStr((STRU *)v54), !_wcsicmp(v23, L"{FF160663-DE82-11CF-BC0A-00AA006111E0}")) )
    {
LABEL_53:
      *((_DWORD *)v4 + 3) = 1;
    }
    v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *, _QWORD, _QWORD))(*(_QWORD *)v34 + 48LL))(
           v34,
           L"logTargetW3C",
           &v42,
           0,
           0);
    if ( v8 < 0 )
      goto LABEL_12;
    v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD, _QWORD))(*(_QWORD *)v34 + 48LL))(
           v34,
           L"maxLogLineLength",
           (__int64)v4 + 92,
           0,
           0);
    if ( v8 < 0 )
      goto LABEL_12;
    v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v34 + 32LL))(
           v34,
           L"customFields",
           &v46);
    if ( v8 < 0 )
      goto LABEL_12;
    v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD, _QWORD))(*(_QWORD *)v46 + 48LL))(
           v46,
           L"maxCustomFieldLength",
           (__int64)v4 + 96,
           0,
           0);
    if ( v8 < 0 )
      goto LABEL_12;
    v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v46 + 40LL))(v46, &v45);
    if ( v8 < 0 )
      goto LABEL_12;
    v8 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v45 + 24LL))(v45, &v36);
    if ( v8 < 0 )
      goto LABEL_12;
    v24 = v36;
    v25 = 176LL * v36;
    if ( !is_mul_ok(v36, 0xB0u) )
      v25 = -1;
    v26 = __CFADD__(v25, 8);
    v27 = v25 + 8;
    if ( v26 )
      v27 = -1;
    v28 = operator new(v27);
    if ( v28 )
    {
      *v28 = v24;
      v5 = (CUSTOM_LOG_FIELDS *)(v28 + 1);
      for ( i = (CUSTOM_LOG_FIELDS *)(v28 + 1); v24; --v24 )
      {
        CUSTOM_LOG_FIELDS::CUSTOM_LOG_FIELDS(i);
        i = (CUSTOM_LOG_FIELDS *)((char *)i + 176);
      }
      if ( v5 )
      {
        for ( j = 0; ; ++j )
        {
          v31 = v36;
          if ( j >= v36 )
            break;
          v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v45 + 32LL))(v45, j, &v35);
          if ( v8 < 0 )
            goto LABEL_12;
          v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v35 + 64LL))(
                 v35,
                 L"logFieldName",
                 &v50,
                 0,
                 0);
          if ( v8 < 0 )
            goto LABEL_12;
          v32 = (_DWORD *)((char *)v5 + 176 * j);
          v8 = STRU::Append((STRU *)v32, v50);
          if ( v8 < 0 )
            goto LABEL_12;
          v8 = STRA::CopyWToUTF8Unescaped((STRA *)(v32 + 14), v50);
          if ( v8 < 0 )
            goto LABEL_12;
          v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v35 + 64LL))(
                 v35,
                 L"sourceName",
                 &v52,
                 0,
                 0);
          if ( v8 < 0 )
            goto LABEL_12;
          v8 = STRU::Append((STRU *)(v32 + 28), v52);
          if ( v8 < 0 )
            goto LABEL_12;
          v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v35 + 48LL))(
                 v35,
                 L"sourceType",
                 &v37,
                 0,
                 0);
          if ( v8 < 0 )
            goto LABEL_12;
          v32[42] = v37;
          if ( v37 == 2 )
            *((_DWORD *)v4 + 30) = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
          v35 = 0;
        }
        v33 = v41 == 0;
        *((_QWORD *)v4 + 13) = v5;
        v5 = 0;
        *((_DWORD *)v4 + 28) = v31;
        *((_DWORD *)v4 + 29) = v33 && v38 == 2 && (v31 || (v42 & 2) != 0);
        goto LABEL_12;
      }
    }
    else
    {
      v5 = 0;
    }
    v8 = -2147024888;
  }
LABEL_12:
  if ( v43 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    v43 = 0;
  }
  if ( v51 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
    v51 = 0;
  }
  if ( v34 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    v34 = 0;
  }
  if ( v47 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    v47 = 0;
  }
  if ( v48 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
    v48 = 0;
  }
  if ( v44 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    v44 = 0;
  }
  if ( v45 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    v45 = 0;
  }
  if ( v46 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
    v46 = 0;
  }
  if ( v35 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    v35 = 0;
  }
  if ( v5 )
    CUSTOM_LOG_FIELDS::`vector deleting destructor'(v5, v7);
  STRU::~STRU((STRU *)v54);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180001cd0  mov     r11, rsp
0x180001cd3  push    rbp
0x180001cd4  push    rbx
0x180001cd5  push    r13
0x180001cd7  lea     rbp, [r11-0C8h]
0x180001cde  sub     rsp, 1B0h
0x180001ce5  mov     rax, cs:__security_cookie
0x180001cec  xor     rax, rsp
0x180001cef  mov     [rbp+0C0h+var_40], rax
0x180001cf6  mov     [r11+18h], rsi
0x180001cfa  mov     r8d, 80h; Size
0x180001d00  xor     esi, esi
0x180001d02  mov     [r11-20h], rdi
0x180001d06  mov     [r11-28h], r12
0x180001d0a  mov     rdi, rdx
0x180001d0d  mov     r12d, cs:?g_fDoCentralBinaryLogging@@3HA; int g_fDoCentralBinaryLogging
0x180001d14  xor     edx, edx; Val
0x180001d16  mov     [r11-30h], r14
0x180001d1a  mov     r14, rcx
0x180001d1d  mov     [rbp+0C0h+var_100], rcx
0x180001d21  lea     rcx, [rbp+0C0h+var_C0]; void *
0x180001d25  mov     [rsp+1C0h+var_148], rsi
0x180001d2a  mov     [rbp+0C0h+var_128], rsi
0x180001d2e  mov     [rsp+1C0h+var_180], rsi
0x180001d33  mov     [rbp+0C0h+var_130], rsi
0x180001d37  mov     [rsp+1C0h+var_164], esi
0x180001d3b  mov     [rsp+1C0h+var_160], 1
0x180001d43  mov     [rsp+1C0h+var_168], esi
0x180001d47  mov     [rbp+0C0h+var_120], rsi
0x180001d4b  call    memset_0
0x180001d50  mov     r8d, 40h ; '@'
0x180001d56  lea     rdx, [rbp+0C0h+var_C0]
0x180001d5a  lea     rcx, [rbp+0C0h+var_F8]
0x180001d5e  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180001d64  mov     rcx, cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * s_pGlobalInfo
0x180001d6b  mov     r13d, esi
0x180001d6e  mov     [rsp+1C0h+var_150], rsi
0x180001d73  mov     [rbp+0C0h+var_138], rsi
0x180001d77  mov     [rbp+0C0h+var_140], rsi
0x180001d7b  mov     qword ptr [rsp+1C0h+var_178], rsi
0x180001d80  mov     [rbp+0C0h+var_110], rsi
0x180001d84  mov     [rsp+1C0h+var_170], esi
0x180001d88  mov     [rsp+1C0h+var_16C], esi
0x180001d8c  mov     [rbp+0C0h+var_118], rsi
0x180001d90  mov     [rbp+0C0h+var_108], rsi
0x180001d94  mov     dword ptr [rsp+1C0h+var_158], esi
0x180001d98  mov     [rsp+1C0h+var_15C], esi
0x180001d9c  mov     rax, [rcx]
0x180001d9f  mov     rax, [rax+38h]
0x180001da3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001da8  mov     r9, rax
0x180001dab  lea     r8, [rsp+1C0h+var_148]
0x180001db0  lea     rdx, IID_INativeConfigurationSystem
0x180001db7  mov     rcx, [rax]
0x180001dba  mov     rax, [rcx]
0x180001dbd  mov     rcx, r9
0x180001dc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001dc5  mov     ebx, eax
0x180001dc7  test    eax, eax
0x180001dc9  js      loc_180001F7B
0x180001dcf  mov     rcx, [rsp+1C0h+var_148]
0x180001dd4  lea     rdx, [rbp+0C0h+var_110]
0x180001dd8  mov     [rsp+28h], rsi
0x180001ddd  lea     r9, [rsp+1C0h+var_150]
0x180001de2  mov     [rsp+1C0h+var_1A0], rdx
0x180001de7  lea     r8, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180001dee  lea     rdx, aSystemApplicat; "system.applicationHost/log"
0x180001df5  mov     rax, [rcx]
0x180001df8  mov     rax, [rax+18h]
0x180001dfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e01  mov     ebx, eax
0x180001e03  test    eax, eax
0x180001e05  js      loc_180001F7B
0x180001e0b  mov     rcx, [rsp+1C0h+var_150]
0x180001e10  lea     r8, [rsp+1C0h+var_15C]
0x180001e15  xor     r9d, r9d
0x180001e18  mov     [rsp+1C0h+var_1A0], rsi
0x180001e1d  lea     rdx, aCentrallogfile; "centralLogFileMode"
0x180001e24  mov     rax, [rcx]
0x180001e27  mov     rax, [rax+30h]
0x180001e2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e30  mov     ebx, eax
0x180001e32  test    eax, eax
0x180001e34  js      loc_180001F7B
0x180001e3a  mov     rcx, [rsp+1C0h+var_148]
0x180001e3f  lea     rdx, [rbp+0C0h+var_128]
0x180001e43  mov     rax, [rcx]
0x180001e46  mov     rax, [rax+38h]
0x180001e4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e4f  mov     ebx, eax
0x180001e51  test    eax, eax
0x180001e53  js      loc_180001F7B
0x180001e59  mov     rax, [rdi]
0x180001e5c  mov     rcx, rdi
0x180001e5f  mov     [rsp+1C0h+var_30], r15
0x180001e67  mov     rax, [rax]
0x180001e6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e6f  mov     rdi, rax
0x180001e72  mov     rcx, [rax]
0x180001e75  mov     rax, [rcx]
0x180001e78  mov     rcx, rdi
0x180001e7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e80  mov     rcx, [rbp+0C0h+var_128]
0x180001e84  lea     r8, [rbp+0C0h+var_130]
0x180001e88  mov     r15d, eax
0x180001e8b  xor     r9d, r9d
0x180001e8e  mov     rdx, [rcx]
0x180001e91  mov     rax, [rdx+20h]
0x180001e95  mov     edx, r15d
0x180001e98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e9d  mov     ebx, eax
0x180001e9f  test    eax, eax
0x180001ea1  js      loc_180001F73
0x180001ea7  mov     rcx, [rbp+0C0h+var_130]
0x180001eab  lea     r8, [rsp+1C0h+var_180]
0x180001eb0  lea     rdx, aLogfile; "logFile"
0x180001eb7  mov     rax, [rcx]
0x180001eba  mov     rax, [rax+20h]
0x180001ebe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ec3  mov     ebx, eax
0x180001ec5  test    eax, eax
0x180001ec7  js      loc_180001F73
0x180001ecd  mov     rcx, [rsp+1C0h+var_180]
0x180001ed2  lea     r8, [rsp+1C0h+var_164]
0x180001ed7  xor     r9d, r9d
0x180001eda  mov     [rsp+1C0h+var_1A0], rsi
0x180001edf  lea     rdx, aLogsiteid; "logSiteId"
0x180001ee6  mov     rax, [rcx]
0x180001ee9  mov     rax, [rax+48h]
0x180001eed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ef2  mov     ebx, eax
0x180001ef4  test    eax, eax
0x180001ef6  js      short loc_180001F73
0x180001ef8  cmp     [rsp+1C0h+var_164], esi
0x180001efc  jz      loc_1800020C9
0x180001f02  add     r14, 10h
0x180001f06  lea     rdx, aW3svc; "W3SVC"
0x180001f0d  mov     rcx, r14
0x180001f10  mov     r8d, 5
0x180001f16  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x180001f1c  mov     ebx, eax
0x180001f1e  test    eax, eax
0x180001f20  js      short loc_180001F73
0x180001f22  mov     rcx, r14
0x180001f25  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x180001f2b  mov     rcx, r14
0x180001f2e  mov     edi, eax
0x180001f30  call    cs:__imp_?QuerySize@STRA@@QEBAKXZ; STRA::QuerySize(void)
0x180001f36  sub     eax, edi
0x180001f38  mov     rcx, r14
0x180001f3b  mov     esi, eax
0x180001f3d  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x180001f43  mov     rcx, r14
0x180001f46  mov     edi, eax
0x180001f48  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180001f4e  mov     r9d, 0Ah; Radix
0x180001f54  mov     r8d, esi; BufferCount
0x180001f57  mov     ecx, r15d; Value
0x180001f5a  lea     rdx, [rdi+rax]; Buffer
0x180001f5e  call    cs:__imp__ultoa_s
0x180001f64  test    eax, eax
0x180001f66  jz      loc_1800020B8
0x180001f6c  mov     ebx, 8000FFFFh
0x180001f71  xor     esi, esi
0x180001f73  mov     r15, [rsp+1C0h+var_30]
0x180001f7b  mov     rcx, [rsp+1C0h+var_150]
0x180001f80  mov     r14, [rsp+1C0h+var_28]
0x180001f88  mov     r12, [rsp+1C0h+var_20]
0x180001f90  mov     rdi, [rsp+1A8h]
0x180001f98  test    rcx, rcx
0x180001f9b  jz      short loc_180001FAE
0x180001f9d  mov     rax, [rcx]
0x180001fa0  mov     rax, [rax+10h]
0x180001fa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fa9  mov     [rsp+1C0h+var_150], rsi
0x180001fae  mov     rcx, [rbp+0C0h+var_110]
0x180001fb2  test    rcx, rcx
0x180001fb5  jz      short loc_180001FC7
0x180001fb7  mov     rax, [rcx]
0x180001fba  mov     rax, [rax+10h]
0x180001fbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fc3  mov     [rbp+0C0h+var_110], rsi
0x180001fc7  mov     rcx, [rsp+1C0h+var_180]
0x180001fcc  test    rcx, rcx
0x180001fcf  jz      short loc_180001FE2
0x180001fd1  mov     rax, [rcx]
0x180001fd4  mov     rax, [rax+10h]
0x180001fd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fdd  mov     [rsp+1C0h+var_180], rsi
0x180001fe2  mov     rcx, [rbp+0C0h+var_130]
0x180001fe6  test    rcx, rcx
0x180001fe9  jz      short loc_180001FFB
0x180001feb  mov     rax, [rcx]
0x180001fee  mov     rax, [rax+10h]
0x180001ff2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ff7  mov     [rbp+0C0h+var_130], rsi
0x180001ffb  mov     rcx, [rbp+0C0h+var_128]
0x180001fff  test    rcx, rcx
0x180002002  jz      short loc_180002014
0x180002004  mov     rax, [rcx]
0x180002007  mov     rax, [rax+10h]
0x18000200b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002010  mov     [rbp+0C0h+var_128], rsi
0x180002014  mov     rcx, [rsp+1C0h+var_148]
0x180002019  test    rcx, rcx
0x18000201c  jz      short loc_18000202F
0x18000201e  mov     rax, [rcx]
0x180002021  mov     rax, [rax+10h]
0x180002025  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000202a  mov     [rsp+1C0h+var_148], rsi
0x18000202f  mov     rcx, [rbp+0C0h+var_140]
0x180002033  test    rcx, rcx
0x180002036  jz      short loc_180002048
0x180002038  mov     rax, [rcx]
0x18000203b  mov     rax, [rax+10h]
0x18000203f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002044  mov     [rbp+0C0h+var_140], rsi
0x180002048  mov     rcx, [rbp+0C0h+var_138]
0x18000204c  test    rcx, rcx
0x18000204f  jz      short loc_180002061
0x180002051  mov     rax, [rcx]
0x180002054  mov     rax, [rax+10h]
0x180002058  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000205d  mov     [rbp+0C0h+var_138], rsi
0x180002061  mov     rcx, qword ptr [rsp+1C0h+var_178]
0x180002066  test    rcx, rcx
0x180002069  jz      short loc_18000207C
0x18000206b  mov     rax, [rcx]
0x18000206e  mov     rax, [rax+10h]
0x180002072  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002077  mov     qword ptr [rsp+1C0h+var_178], rsi
0x18000207c  mov     rsi, [rsp+1C0h+arg_10]
0x180002084  test    r13, r13
0x180002087  jz      short loc_180002091
0x180002089  mov     rcx, r13; this
0x18000208c  call    ??_ECUSTOM_LOG_FIELDS@@QEAAPEAXI@Z; CUSTOM_LOG_FIELDS::`vector deleting destructor'(uint)
0x180002091  lea     rcx, [rbp+0C0h+var_F8]
0x180002095  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000209b  mov     eax, ebx
0x18000209d  mov     rcx, [rbp+0C0h+var_40]
0x1800020a4  xor     rcx, rsp; StackCookie
0x1800020a7  call    __security_check_cookie
0x1800020ac  add     rsp, 1B0h
0x1800020b3  pop     r13
0x1800020b5  pop     rbx
0x1800020b6  pop     rbp
0x1800020b7  retn
0x1800020b8  mov     rcx, r14
0x1800020bb  call    cs:__imp_?SyncWithBuffer@STRA@@QEAAXXZ; STRA::SyncWithBuffer(void)
0x1800020c1  mov     r14, [rbp+0C0h+var_100]
0x1800020c5  xor     esi, esi
0x1800020c7  jmp     short loc_180002138
0x1800020c9  mov     rcx, [rsp+1C0h+var_150]
0x1800020ce  lea     r8, [rsp+1C0h+var_160]
0x1800020d3  xor     r9d, r9d
0x1800020d6  mov     [rsp+1C0h+var_1A0], rsi
0x1800020db  lea     rdx, aLoginutf8; "logInUTF8"
0x1800020e2  mov     rax, [rcx]
0x1800020e5  mov     rax, [rax+48h]
0x1800020e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020ee  mov     ebx, eax
0x1800020f0  test    eax, eax
0x1800020f2  js      loc_180001F73
0x1800020f8  mov     rcx, rdi
0x1800020fb  mov     rax, [rdi]
0x1800020fe  mov     rax, [rax+8]
0x180002102  cmp     [rsp+1C0h+var_160], esi
0x180002106  jz      short loc_18000211C
0x180002108  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000210d  mov     rdx, rax
0x180002110  lea     rcx, [r14+10h]
0x180002114  call    cs:__imp_?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z; STRA::CopyWToUTF8Unescaped(ushort const *)
0x18000211a  jmp     short loc_18000212E
0x18000211c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002121  mov     rdx, rax
0x180002124  lea     rcx, [r14+10h]
0x180002128  call    cs:__imp_?CopyW@STRA@@QEAAJPEBG@Z; STRA::CopyW(ushort const *)
0x18000212e  mov     ebx, eax
0x180002130  test    eax, eax
0x180002132  js      loc_180001F73
0x180002138  test    r12d, r12d
0x18000213b  jz      short loc_18000214A
0x18000213d  mov     dword ptr [r14+0Ch], 1
0x180002145  jmp     loc_180001F73
0x18000214a  mov     rcx, [rsp+1C0h+var_180]
0x18000214f  lea     r8, [rsp+1C0h+var_168]
0x180002154  xor     r9d, r9d
0x180002157  mov     [rsp+1C0h+var_1A0], rsi
0x18000215c  lea     rdx, aLogformat; "logFormat"
0x180002163  mov     rax, [rcx]
0x180002166  mov     rax, [rax+30h]
0x18000216a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000216f  mov     ebx, eax
0x180002171  test    eax, eax
0x180002173  js      loc_180001F73
0x180002179  cmp     [rsp+1C0h+var_168], 3
0x18000217e  jnz     loc_180002282
0x180002184  mov     rcx, [rsp+1C0h+var_180]
0x180002189  lea     r8, [rbp+0C0h+var_120]
0x18000218d  xor     r9d, r9d
  ... truncated ...
```
