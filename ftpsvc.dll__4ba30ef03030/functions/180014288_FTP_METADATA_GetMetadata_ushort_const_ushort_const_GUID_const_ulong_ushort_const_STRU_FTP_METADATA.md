# FTP_METADATA::GetMetadata(ushort const *,ushort const *,_GUID const *,ulong *,ushort const * *,STRU *,FTP_METADATA * *)

- ea: `0x180014288`
- end: `0x180014c66`
- name: `?GetMetadata@FTP_METADATA@@SAJPEBG0PEBU_GUID@@PEAKPEAPEBGPEAVSTRU@@PEAPEAV1@@Z`
- size: `2526`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const struct _GUID *, unsigned int *, const unsigned __int16 **, struct STRU *, struct FTP_METADATA **)`
- caller_count: `4`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000c420`
- `0x18000f198`
- `0x18000fdd8`
- `0x180010370`

## callees

- `0x180001210`
- `0x180013d74`
- `0x180014288`
- `0x180014c6c`
- `0x1800150d0`
- `0x180015554`
- `0x180029b4c`
- `0x18002a880`
- `0x18002b2bc`
- `0x18004700f`
- `0x180047027`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800144b5`
- `OLEAUT32!__imp_SysAllocString` at `0x1800145c0`
- `OLEAUT32!__imp_SysAllocString` at `0x1800145df`
- `OLEAUT32!__imp_SysAllocString` at `0x18001480a`
- `OLEAUT32!__imp_SysAllocString` at `0x1800144b5`
- `OLEAUT32!__imp_SysAllocString` at `0x1800145c0`
- `OLEAUT32!__imp_SysAllocString` at `0x1800145df`
- `OLEAUT32!__imp_SysAllocString` at `0x18001480a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001460d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800146d5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800146e7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800146f5`
- `OLEAUT32!__imp_SysFreeString` at `0x180014705`
- `OLEAUT32!__imp_SysFreeString` at `0x180014a7c`
- `OLEAUT32!__imp_SysFreeString` at `0x180014bfd`
- `OLEAUT32!__imp_SysFreeString` at `0x18001460d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800146d5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800146e7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800146f5`
- `OLEAUT32!__imp_SysFreeString` at `0x180014705`
- `OLEAUT32!__imp_SysFreeString` at `0x180014a7c`
- `OLEAUT32!__imp_SysFreeString` at `0x180014bfd`
- `OLEAUT32!__imp_GetErrorInfo` at `0x18001452b`
- `OLEAUT32!__imp_GetErrorInfo` at `0x1800147f5`
- `OLEAUT32!__imp_GetErrorInfo` at `0x18001452b`
- `OLEAUT32!__imp_GetErrorInfo` at `0x1800147f5`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180014932`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180014932`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180014a6a`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180014a6a`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180014571`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180014571`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180014447`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180014886`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800149d5`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800149eb`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180014447`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180014886`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800149d5`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800149eb`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180014313`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180014339`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180014313`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180014339`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001445a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001446d`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001494b`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001445a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001446d`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001494b`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x180014434`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x1800146bf`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x180014b78`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x180014434`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x1800146bf`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x180014b78`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180014c29`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180014c34`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180014c29`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180014c34`

## string_xrefs

- `0x1800147ae`: `Invalid configuration.`
- `0x180014b96`: `Invalid configuration.`

## pseudocode

```c
__int64 __fastcall FTP_METADATA::GetMetadata(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const struct _GUID *a3,
        unsigned int *a4,
        const unsigned __int16 **a5,
        struct STRU *a6,
        struct FTP_METADATA **a7)
{
  OLECHAR *v10; // rbx
  FTP_METADATA *v11; // rsi
  OLECHAR *v12; // r12
  OLECHAR *v13; // r13
  __int64 v14; // rax
  CEtwTracer *v15; // rbx
  int v16; // eax
  __int64 v17; // rax
  int MappingExtension; // edi
  int v19; // edx
  __int64 v20; // r9
  int v21; // r15d
  __int64 v22; // rax
  int Key; // eax
  OLECHAR *v24; // rbx
  __int64 v25; // rax
  CEtwTracer *v26; // rbx
  const wchar_t *v27; // rax
  BSTR v28; // rax
  const unsigned __int16 *v29; // rdx
  int v30; // eax
  unsigned int v31; // ecx
  __int64 v32; // rdx
  FTP_METADATA *v33; // rax
  struct IAppHostElement *v34; // r14
  const unsigned __int16 *v35; // r15
  struct IErrorInfo **v36; // r8
  __int64 v37; // rax
  wchar_t *v38; // rbx
  CEtwTracer *v39; // r14
  int v40; // eax
  __int64 v41; // rax
  struct STRU *v42; // rbx
  bool v43; // sf
  int v45; // [rsp+40h] [rbp-C0h] BYREF
  IErrorInfo *pperrinfo; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v47; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t *String2; // [rsp+58h] [rbp-A8h] BYREF
  BSTR v49; // [rsp+60h] [rbp-A0h] BYREF
  struct IAppHostElement *v50; // [rsp+68h] [rbp-98h] BYREF
  FTP_METADATA *v51; // [rsp+70h] [rbp-90h] BYREF
  BSTR bstrString; // [rsp+78h] [rbp-88h] BYREF
  __int64 v53; // [rsp+80h] [rbp-80h] BYREF
  __int64 v54; // [rsp+88h] [rbp-78h] BYREF
  struct IAppHostMappingExtension *v55; // [rsp+90h] [rbp-70h] BYREF
  struct IAppHostAdminManager *v56; // [rsp+98h] [rbp-68h]
  const struct _GUID *v57; // [rsp+A0h] [rbp-60h]
  BSTR v58; // [rsp+A8h] [rbp-58h]
  unsigned int *v59; // [rsp+B0h] [rbp-50h]
  struct STRU *v60; // [rsp+B8h] [rbp-48h]
  const unsigned __int16 **v61; // [rsp+C0h] [rbp-40h]
  struct FTP_METADATA **v62; // [rsp+C8h] [rbp-38h]
  FTP_METADATA *v63; // [rsp+D0h] [rbp-30h]
  struct _EVENT_TRACE_HEADER v64; // [rsp+E0h] [rbp-20h] BYREF
  const struct _GUID *v65; // [rsp+110h] [rbp+10h]
  int v66; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v67; // [rsp+120h] [rbp+20h]
  int v68; // [rsp+128h] [rbp+28h]
  _BYTE v69[32]; // [rsp+130h] [rbp+30h] BYREF
  const unsigned __int16 *v70; // [rsp+150h] [rbp+50h]
  unsigned int v71; // [rsp+158h] [rbp+58h]
  unsigned int v72; // [rsp+160h] [rbp+60h]
  _BYTE v73[32]; // [rsp+168h] [rbp+68h] BYREF
  const OLECHAR *v74; // [rsp+188h] [rbp+88h]
  unsigned int v75; // [rsp+190h] [rbp+90h]
  int v76; // [rsp+198h] [rbp+98h]
  struct _EVENT_TRACE_HEADER v77; // [rsp+1A0h] [rbp+A0h] BYREF
  const struct _GUID *v78; // [rsp+1D0h] [rbp+D0h]
  int v79; // [rsp+1D8h] [rbp+D8h]
  wchar_t *v80; // [rsp+1E0h] [rbp+E0h]
  int v81; // [rsp+1E8h] [rbp+E8h]
  FTP_METADATA **v82; // [rsp+1F0h] [rbp+F0h]
  int v83; // [rsp+1F8h] [rbp+F8h]
  unsigned __int16 v84[256]; // [rsp+200h] [rbp+100h] BYREF
  unsigned __int16 v85[256]; // [rsp+400h] [rbp+300h] BYREF

  v59 = a4;
  v57 = a3;
  v60 = a6;
  v61 = a5;
  v62 = a7;
  memset_0(v84, 0, sizeof(v84));
  STRU::STRU((STRU *)v73, v84, 0x100u);
  memset_0(v85, 0, sizeof(v85));
  STRU::STRU((STRU *)v69, v85, 0x100u);
  v10 = 0;
  v56 = 0;
  v53 = 0;
  v55 = 0;
  v50 = 0;
  v54 = 0;
  pperrinfo = 0;
  v47 = 0;
  v11 = 0;
  v45 = 0;
  v12 = 0;
  v58 = 0;
  v13 = 0;
  v49 = 0;
  String2 = 0;
  bstrString = 0;
  v14 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
  if ( *(_DWORD *)(v14 + 8) && (*(_BYTE *)(v14 + 40) & 4) != 0 && *(_DWORD *)(v14 + 44) >= 4u )
  {
    v15 = (CEtwTracer *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
    memset_0(&v64.FieldTypeFlags, 0, 0x4Eu);
    v64.UserTime = 1703936;
    v64.Size = 80;
    v64.Class.Version = 1;
    v64.Class.Type = 4;
    v64.GuidPtr = (ULONGLONG)&`FtpProcessingEvents::GetAreaGuid'::`2'::AreaGuid;
    v65 = a3;
    v66 = 16;
    v67 = a2;
    if ( a2 )
    {
      v17 = -1;
      do
        ++v17;
      while ( a2[v17] );
      v16 = 2 * v17 + 2;
    }
    else
    {
      v16 = 0;
    }
    v68 = v16;
    CEtwTracer::EtwTraceEvent(v15, &v64);
    v10 = 0;
  }
  MappingExtension = STRU::Copy((STRU *)v73, L"MACHINE/WEBROOT/APPHOST/");
  if ( MappingExtension < 0 )
    goto LABEL_19;
  MappingExtension = STRU::Append((STRU *)v73, a1);
  if ( MappingExtension < 0 )
    goto LABEL_19;
  MappingExtension = STRU::Append((STRU *)v73, a2);
  if ( MappingExtension < 0 )
    goto LABEL_19;
  v19 = v76;
  while ( v74[v19 - 1] == 47 )
  {
    v20 = (unsigned int)(v19 - 1);
    if ( (unsigned int)v20 < v75 >> 1 )
    {
      v74[v20] = 0;
      --v19;
      v76 = v20;
    }
  }
  v12 = SysAllocString(v74);
  if ( !v12 )
  {
    MappingExtension = -2147024888;
LABEL_19:
    v21 = 0;
    goto LABEL_33;
  }
  v56 = (struct IAppHostAdminManager *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 24LL))(g_pFtpServer);
  MappingExtension = ((__int64 (__fastcall *)(struct IAppHostAdminManager *, __int64 *))v56->lpVtbl->get_ConfigManager)(
                       v56,
                       &v53);
  if ( MappingExtension < 0 )
    goto LABEL_19;
  MappingExtension = (*(__int64 (__fastcall **)(__int64, OLECHAR *, wchar_t **))(*(_QWORD *)v53 + 32LL))(
                       v53,
                       v12,
                       &String2);
  if ( MappingExtension < 0 )
    goto LABEL_22;
  v22 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 96LL))(g_pFtpServer);
  v51 = 0;
  Key = CLKRHashTable::FindKey(v22, String2, &v51);
  v11 = v51;
  if ( !Key )
  {
    v21 = 1;
    MappingExtension = 0;
    goto LABEL_33;
  }
  if ( !wcscmp_0(L"MACHINE/WEBROOT/APPHOST", String2) )
  {
LABEL_83:
    v33 = (FTP_METADATA *)operator new(0x3B0u);
    v63 = v33;
    if ( v33 )
      v11 = FTP_METADATA::FTP_METADATA(v33);
    else
      v11 = 0;
    if ( v11 )
    {
      v34 = v50;
      v35 = v70;
      MappingExtension = STRU::Copy((FTP_METADATA *)((char *)v11 + 16), String2);
      if ( MappingExtension >= 0 )
      {
        MappingExtension = STRU::Copy((FTP_METADATA *)((char *)v11 + 328), v35);
        if ( MappingExtension >= 0 )
        {
          MappingExtension = FTP_METADATA::InitializeIpRestrictionConfig(v11, &pperrinfo);
          if ( MappingExtension >= 0 )
          {
            MappingExtension = FTP_METADATA::InitializeUrlAuthorizationConfig(v11, &pperrinfo);
            if ( MappingExtension >= 0 )
            {
              MappingExtension = FTP_REQUEST_FILTER::Initialize(
                                   (FTP_METADATA *)((char *)v11 + 680),
                                   *((const unsigned __int16 **)v11 + 6),
                                   &pperrinfo);
              if ( MappingExtension >= 0 )
              {
                if ( v34 )
                  MappingExtension = FTP_METADATA::InitializeVDirUser(v11, v34, v36);
              }
            }
          }
        }
      }
      if ( MappingExtension >= 0 )
      {
        v37 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 96LL))(g_pFtpServer);
        CLKRHashTable::InsertRecord(v37, v11, 0);
      }
    }
    else
    {
      MappingExtension = -2147024888;
    }
    if ( !v10 )
      goto LABEL_32;
    goto LABEL_98;
  }
  MappingExtension = Config_GetMappingExtension(v56, &v55);
  if ( MappingExtension < 0 )
  {
    v21 = 0;
    goto LABEL_33;
  }
  v24 = SysAllocString(a1);
  v58 = v24;
  if ( !v24 )
  {
    MappingExtension = -2147024888;
    v21 = 0;
    goto LABEL_33;
  }
  v13 = SysAllocString(a2);
  if ( !v13 )
  {
    MappingExtension = -2147024888;
LABEL_32:
    v21 = v45;
    goto LABEL_33;
  }
  MappingExtension = ((__int64 (__fastcall *)(struct IAppHostMappingExtension *, OLECHAR *, OLECHAR *, _QWORD, struct IAppHostElement **, __int64 *))v55->lpVtbl->MapPath)(
                       v55,
                       v24,
                       v13,
                       0,
                       &v50,
                       &v54);
  if ( MappingExtension >= 0 )
  {
    v28 = SysAllocString(L"path");
    v10 = v28;
    v21 = 0;
    if ( !v28 )
    {
      MappingExtension = -2147024888;
      goto LABEL_33;
    }
    MappingExtension = (*(__int64 (__fastcall **)(__int64, BSTR, __int64 *))(*(_QWORD *)v54 + 88LL))(v54, v28, &v47);
    if ( MappingExtension < 0 )
      goto LABEL_98;
    MappingExtension = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v47 + 56LL))(v47, &bstrString);
    if ( MappingExtension < 0 )
      goto LABEL_98;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    v47 = 0;
    MappingExtension = STRU::Copy((STRU *)v69, bstrString);
    if ( MappingExtension < 0 )
      goto LABEL_98;
    MappingExtension = ((__int64 (__fastcall *)(struct IAppHostElement *, OLECHAR *, __int64 *))v50->lpVtbl->GetPropertyByName)(
                         v50,
                         v10,
                         &v47);
    if ( MappingExtension < 0 )
      goto LABEL_98;
    MappingExtension = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v47 + 56LL))(v47, &v49);
    if ( MappingExtension < 0 )
      goto LABEL_98;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    v47 = 0;
    v29 = v49;
    if ( v70[v72 - 1] == 47 )
    {
      if ( *v49 == 47 )
      {
        v30 = STRU::Append((STRU *)v69, v49 + 1);
        goto LABEL_77;
      }
    }
    else if ( *v49 != 47 && *v49 )
    {
      MappingExtension = STRU::Append((STRU *)v69, L"/", 1u);
      if ( MappingExtension < 0 )
        goto LABEL_98;
      v29 = v49;
    }
    v30 = STRU::Append((STRU *)v69, v29);
LABEL_77:
    MappingExtension = v30;
    if ( v30 >= 0 )
    {
      v31 = v72;
      while ( v31 > 1 )
      {
        v32 = v31 - 1;
        if ( v70[v32] != 47 )
          break;
        if ( (unsigned int)v32 < v71 >> 1 )
        {
          v70[v32] = 0;
          --v31;
          v72 = v32;
        }
      }
      goto LABEL_83;
    }
LABEL_98:
    SysFreeString(v10);
    goto LABEL_32;
  }
LABEL_22:
  v21 = 0;
  if ( GetErrorInfo(0, &pperrinfo) < 0 )
    pperrinfo = 0;
LABEL_33:
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  v25 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
  if ( MappingExtension >= 0 )
  {
    if ( *(_DWORD *)(v25 + 8) && (*(_BYTE *)(v25 + 40) & 4) != 0 && *(_DWORD *)(v25 + 44) >= 4u )
    {
      v38 = String2;
      v39 = (CEtwTracer *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
      LODWORD(v51) = v21;
      memset_0(&v77.FieldTypeFlags, 0, 0x5Eu);
      v77.UserTime = 1703936;
      v77.Size = 96;
      v77.Class.Version = 1;
      v77.Class.Type = 5;
      v77.GuidPtr = (ULONGLONG)&`FtpProcessingEvents::GetAreaGuid'::`2'::AreaGuid;
      v78 = v57;
      v79 = 16;
      v80 = v38;
      if ( v38 )
      {
        v41 = -1;
        do
          ++v41;
        while ( v38[v41] );
        v40 = 2 * v41 + 2;
      }
      else
      {
        v40 = 0;
      }
      v81 = v40;
      v82 = &v51;
      v83 = 4;
      CEtwTracer::EtwTraceEvent(v39, &v77);
    }
  }
  else if ( *(_DWORD *)(v25 + 8) && (*(_BYTE *)(v25 + 40) & 4) != 0 && *(_DWORD *)(v25 + 44) >= 3u )
  {
    v45 = MappingExtension;
    v26 = (CEtwTracer *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
    memset_0(&v64.FieldTypeFlags, 0, 0x4Eu);
    v64.UserTime = 1703936;
    v64.Size = 80;
    v64.Class.Version = 1;
    v64.Class.Type = 6;
    v64.GuidPtr = (ULONGLONG)&`FtpProcessingEvents::GetAreaGuid'::`2'::AreaGuid;
    v65 = v57;
    v66 = 16;
    v67 = (const unsigned __int16 *)&v45;
    v68 = 4;
    CEtwTracer::EtwTraceEvent(v26, &v64);
  }
  if ( v12 )
    SysFreeString(v12);
  if ( v58 )
    SysFreeString(v58);
  if ( v13 )
    SysFreeString(v13);
  if ( v49 )
  {
    SysFreeString(v49);
    v49 = 0;
  }
  if ( v47 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    v47 = 0;
  }
  if ( v53 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
    v53 = 0;
  }
  if ( v50 )
  {
    ((void (__fastcall *)(struct IAppHostElement *))v50->lpVtbl->Release)(v50);
    v50 = 0;
  }
  if ( v54 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
    v54 = 0;
  }
  if ( v55 )
  {
    ((void (__fastcall *)(struct IAppHostMappingExtension *))v55->lpVtbl->Release)(v55);
    v55 = 0;
  }
  if ( MappingExtension >= 0 )
  {
    *v62 = v11;
  }
  else
  {
    *v59 = 18;
    if ( pperrinfo )
    {
      v42 = v60;
      v43 = (int)BuildExceptionInfo(pperrinfo, v60) < 0;
      v27 = L"Invalid configuration.";
      if ( !v43 )
        v27 = (const wchar_t *)*((_QWORD *)v42 + 4);
    }
    else
    {
      v27 = L"Invalid configuration.";
    }
    *v61 = v27;
    if ( v11 && _InterlockedExchangeAdd((volatile signed __int32 *)v11 + 3, 0xFFFFFFFF) == 1 )
      (**(void (__fastcall ***)(FTP_METADATA *, __int64))v11)(v11, 1);
  }
  if ( pperrinfo )
  {
    ((void (__fastcall *)(IErrorInfo *))pperrinfo->lpVtbl->Release)(pperrinfo);
    pperrinfo = 0;
  }
  if ( String2 )
  {
    SysFreeString(String2);
    String2 = 0;
  }
  if ( v56 )
    (*(void (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 208LL))(g_pFtpServer);
  STRU::~STRU(v69);
  STRU::~STRU(v73);
  return (unsigned int)MappingExtension;
}

```

## disassembly

```asm
0x180014288  mov     [rsp-8+arg_10], rbx
0x18001428d  push    rbp
0x18001428e  push    rsi
0x18001428f  push    rdi
0x180014290  push    r12
0x180014292  push    r13
0x180014294  push    r14
0x180014296  push    r15
0x180014298  lea     rbp, [rsp-510h]
0x1800142a0  sub     rsp, 610h
0x1800142a7  mov     rax, cs:__security_cookie
0x1800142ae  xor     rax, rsp
0x1800142b1  mov     [rbp+540h+var_40], rax
0x1800142b8  mov     [rbp+540h+var_590], r9
0x1800142bc  mov     rdi, r8
0x1800142bf  mov     [rbp+540h+var_5A0], r8
0x1800142c3  mov     r14, rdx
0x1800142c6  mov     r15, rcx
0x1800142c9  mov     rax, [rbp+540h+arg_28]
0x1800142d0  mov     [rbp+540h+var_588], rax
0x1800142d4  mov     rax, [rbp+540h+arg_20]
0x1800142db  mov     [rbp+540h+var_580], rax
0x1800142df  mov     rax, [rbp+540h+arg_30]
0x1800142e6  mov     [rbp+540h+var_578], rax
0x1800142ea  mov     esi, 200h
0x1800142ef  mov     r8d, esi; Size
0x1800142f2  xor     edx, edx; Val
0x1800142f4  lea     rcx, [rbp+540h+var_440]; void *
0x1800142fb  call    memset_0
0x180014300  mov     ebx, 100h
0x180014305  mov     r8d, ebx
0x180014308  lea     rdx, [rbp+540h+var_440]
0x18001430f  lea     rcx, [rbp+540h+var_4D8]
0x180014313  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180014319  nop
0x18001431a  mov     r8d, esi; Size
0x18001431d  xor     edx, edx; Val
0x18001431f  lea     rcx, [rbp+540h+var_240]; void *
0x180014326  call    memset_0
0x18001432b  mov     r8d, ebx
0x18001432e  lea     rdx, [rbp+540h+var_240]
0x180014335  lea     rcx, [rbp+540h+var_510]
0x180014339  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18001433f  nop
0x180014340  xor     ebx, ebx
0x180014342  mov     [rbp+540h+var_5A8], rbx
0x180014346  mov     [rbp+540h+var_5C0], rbx
0x18001434a  mov     [rbp+540h+var_5B0], rbx
0x18001434e  mov     [rsp+640h+var_5D8], rbx
0x180014353  mov     [rbp+540h+var_5B8], rbx
0x180014357  mov     [rsp+640h+pperrinfo], rbx
0x18001435c  mov     [rsp+640h+var_5F0], rbx
0x180014361  mov     esi, ebx
0x180014363  mov     [rsp+640h+var_600], ebx
0x180014367  mov     r12d, ebx
0x18001436a  mov     [rbp+540h+var_598], rbx
0x18001436e  mov     r13d, ebx
0x180014371  mov     [rsp+640h+var_5E0], rbx
0x180014376  mov     [rsp+640h+String2], rbx
0x18001437b  mov     [rsp+640h+bstrString], rbx
0x180014380  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x180014387  mov     rax, [rcx]
0x18001438a  mov     rax, [rax+20h]
0x18001438e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014393  cmp     [rax+8], ebx
0x180014396  jz      loc_18001443C
0x18001439c  test    byte ptr [rax+28h], 4
0x1800143a0  jz      loc_18001443C
0x1800143a6  cmp     dword ptr [rax+2Ch], 4
0x1800143aa  jb      loc_18001443C
0x1800143b0  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x1800143b7  mov     rax, [rcx]
0x1800143ba  mov     rax, [rax+20h]
0x1800143be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143c3  mov     rbx, rax
0x1800143c6  xor     edx, edx; Val
0x1800143c8  lea     r8d, [r13+4Eh]; Size
0x1800143cc  lea     rcx, [rbp+540h+var_55E]; void *
0x1800143d0  call    memset_0
0x1800143d5  mov     [rbp+540h+var_534], 1A0000h
0x1800143dc  lea     eax, [r13+50h]
0x1800143e0  mov     [rbp+540h+var_560], ax
0x1800143e4  lea     eax, [r13+1]
0x1800143e8  mov     [rbp+540h+var_55A], ax
0x1800143ec  mov     [rbp+540h+var_55C], 4
0x1800143f0  lea     rax, ?AreaGuid@?1??GetAreaGuid@FtpProcessingEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `FtpProcessingEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x1800143f7  mov     [rbp+540h+var_548], rax
0x1800143fb  mov     [rbp+540h+var_530], rdi
0x1800143ff  mov     [rbp+540h+var_528], 10h
0x180014406  mov     [rbp+540h+var_520], r14
0x18001440a  xor     ecx, ecx
0x18001440c  test    r14, r14
0x18001440f  jnz     short loc_180014415
0x180014411  mov     eax, ecx
0x180014413  jmp     short loc_18001442A
0x180014415  or      rax, 0FFFFFFFFFFFFFFFFh
0x180014419  inc     rax
0x18001441c  cmp     [r14+rax*2], cx
0x180014421  jnz     short loc_180014419
0x180014423  lea     eax, ds:2[rax*2]
0x18001442a  mov     [rbp+540h+var_518], eax
0x18001442d  lea     rdx, [rbp+540h+var_560]
0x180014431  mov     rcx, rbx
0x180014434  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z; CEtwTracer::EtwTraceEvent(_EVENT_TRACE_HEADER *)
0x18001443a  xor     ebx, ebx
0x18001443c  lea     rdx, aMachineWebroot_0; "MACHINE/WEBROOT/APPHOST/"
0x180014443  lea     rcx, [rbp+540h+var_4D8]
0x180014447  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001444d  mov     edi, eax
0x18001444f  test    eax, eax
0x180014451  js      short loc_1800144C8
0x180014453  mov     rdx, r15
0x180014456  lea     rcx, [rbp+540h+var_4D8]
0x18001445a  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180014460  mov     edi, eax
0x180014462  test    eax, eax
0x180014464  js      short loc_1800144C8
0x180014466  mov     rdx, r14
0x180014469  lea     rcx, [rbp+540h+var_4D8]
0x18001446d  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180014473  mov     edi, eax
0x180014475  test    eax, eax
0x180014477  js      short loc_1800144C8
0x180014479  mov     edx, [rbp+540h+var_4A8]
0x18001447f  jmp     short loc_1800144A0
0x180014481  lea     r9d, [rdx-1]
0x180014485  mov     eax, [rbp+540h+var_4B0]
0x18001448b  shr     eax, 1
0x18001448d  cmp     r9d, eax
0x180014490  jnb     short loc_1800144A7
0x180014492  mov     [r8+r9*2], bx
0x180014497  mov     edx, r9d
0x18001449a  mov     [rbp+540h+var_4A8], edx
0x1800144a0  mov     r8, [rbp+540h+var_4B8]
0x1800144a7  lea     eax, [rdx-1]
0x1800144aa  cmp     word ptr [r8+rax*2], 2Fh ; '/'
0x1800144b0  jz      short loc_180014481
0x1800144b2  mov     rcx, r8; psz
0x1800144b5  call    cs:__imp_SysAllocString
0x1800144bb  mov     r12, rax
0x1800144be  test    rax, rax
0x1800144c1  jnz     short loc_1800144D0
0x1800144c3  mov     edi, 80070008h
0x1800144c8  mov     r15d, esi
0x1800144cb  jmp     loc_1800145FD
0x1800144d0  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x1800144d7  mov     rax, [rcx]
0x1800144da  mov     rax, [rax+18h]
0x1800144de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800144e3  mov     r8, rax
0x1800144e6  mov     [rbp+540h+var_5A8], rax
0x1800144ea  mov     rcx, [rax]
0x1800144ed  mov     rax, [rcx+30h]
0x1800144f1  lea     rdx, [rbp+540h+var_5C0]
0x1800144f5  mov     rcx, r8
0x1800144f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800144fd  mov     edi, eax
0x1800144ff  test    eax, eax
0x180014501  js      short loc_1800144C8
0x180014503  mov     r9, [rbp+540h+var_5C0]
0x180014507  mov     rcx, [r9]
0x18001450a  mov     rax, [rcx+20h]
0x18001450e  lea     r8, [rsp+640h+String2]
0x180014513  mov     rdx, r12
0x180014516  mov     rcx, r9
0x180014519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001451e  mov     edi, eax
0x180014520  test    eax, eax
0x180014522  jns     short loc_18001454C
0x180014524  lea     rdx, [rsp+640h+pperrinfo]; pperrinfo
0x180014529  xor     ecx, ecx; dwReserved
0x18001452b  call    cs:__imp_GetErrorInfo
0x180014531  mov     r15d, esi
0x180014534  mov     r14d, 1
0x18001453a  test    eax, eax
0x18001453c  jns     loc_180014603
0x180014542  mov     [rsp+640h+pperrinfo], rbx
0x180014547  jmp     loc_180014603
0x18001454c  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x180014553  mov     rax, [rcx]
0x180014556  mov     rax, [rax+60h]
0x18001455a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001455f  mov     [rsp+640h+var_5D0], rbx
0x180014564  lea     r8, [rsp+640h+var_5D0]
0x180014569  mov     rdx, [rsp+640h+String2]
0x18001456e  mov     rcx, rax
0x180014571  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x180014577  mov     rsi, [rsp+640h+var_5D0]
0x18001457c  test    eax, eax
0x18001457e  jnz     short loc_18001458B
0x180014580  lea     r14d, [rax+1]
0x180014584  mov     r15d, r14d
0x180014587  mov     edi, ebx
0x180014589  jmp     short loc_180014603
0x18001458b  mov     rdx, [rsp+640h+String2]; String2
0x180014590  lea     rcx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180014597  call    wcscmp_0
0x18001459c  test    eax, eax
0x18001459e  jz      loc_18001498E
0x1800145a4  lea     rdx, [rbp+540h+var_5B0]; struct IAppHostMappingExtension **
0x1800145a8  mov     rcx, [rbp+540h+var_5A8]; struct IAppHostAdminManager *
0x1800145ac  call    ?Config_GetMappingExtension@@YAJPEAUIAppHostAdminManager@@PEAPEAUIAppHostMappingExtension@@@Z; Config_GetMappingExtension(IAppHostAdminManager *,IAppHostMappingExtension * *)
0x1800145b1  mov     edi, eax
0x1800145b3  xor     ebx, ebx
0x1800145b5  test    eax, eax
0x1800145b7  js      loc_180014A87
0x1800145bd  mov     rcx, r15; psz
0x1800145c0  call    cs:__imp_SysAllocString
0x1800145c6  mov     rbx, rax
0x1800145c9  mov     [rbp+540h+var_598], rax
0x1800145cd  test    rax, rax
0x1800145d0  jnz     short loc_1800145DC
0x1800145d2  mov     edi, 80070008h
0x1800145d7  mov     r15d, r13d
0x1800145da  jmp     short loc_1800145FB
0x1800145dc  mov     rcx, r14; psz
0x1800145df  call    cs:__imp_SysAllocString
0x1800145e5  mov     r13, rax
0x1800145e8  test    rax, rax
0x1800145eb  jnz     loc_1800147BA
0x1800145f1  mov     edi, 80070008h
0x1800145f6  mov     r15d, [rsp+640h+var_600]
0x1800145fb  xor     ebx, ebx
0x1800145fd  mov     r14d, 1
0x180014603  mov     rcx, [rsp+640h+bstrString]; bstrString
0x180014608  test    rcx, rcx
0x18001460b  jz      short loc_180014618
0x18001460d  call    cs:__imp_SysFreeString
0x180014613  mov     [rsp+640h+bstrString], rbx
0x180014618  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18001461f  mov     rax, [rcx]
0x180014622  mov     rax, [rax+20h]
0x180014626  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001462b  test    edi, edi
0x18001462d  jns     loc_180014A8F
0x180014633  cmp     [rax+8], ebx
0x180014636  jz      loc_1800146C7
0x18001463c  test    byte ptr [rax+28h], 4
0x180014640  jz      loc_1800146C7
0x180014646  cmp     dword ptr [rax+2Ch], 3
0x18001464a  jb      short loc_1800146C7
0x18001464c  mov     [rsp+640h+var_600], edi
0x180014650  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x180014657  mov     rax, [rcx]
0x18001465a  mov     rax, [rax+20h]
0x18001465e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014663  mov     rbx, rax
0x180014666  xor     edx, edx; Val
0x180014668  lea     r8d, [rdx+4Eh]; Size
0x18001466c  lea     rcx, [rbp+540h+var_55E]; void *
0x180014670  call    memset_0
0x180014675  mov     [rbp+540h+var_534], 1A0000h
0x18001467c  mov     eax, 50h ; 'P'
0x180014681  mov     [rbp+540h+var_560], ax
0x180014685  mov     [rbp+540h+var_55A], r14w
0x18001468a  mov     [rbp+540h+var_55C], 6
0x18001468e  lea     rax, ?AreaGuid@?1??GetAreaGuid@FtpProcessingEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `FtpProcessingEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x180014695  mov     [rbp+540h+var_548], rax
0x180014699  mov     rax, [rbp+540h+var_5A0]
0x18001469d  mov     [rbp+540h+var_530], rax
0x1800146a1  mov     [rbp+540h+var_528], 10h
0x1800146a8  lea     rax, [rsp+640h+var_600]
0x1800146ad  mov     [rbp+540h+var_520], rax
0x1800146b1  mov     [rbp+540h+var_518], 4
0x1800146b8  lea     rdx, [rbp+540h+var_560]
0x1800146bc  mov     rcx, rbx
0x1800146bf  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z; CEtwTracer::EtwTraceEvent(_EVENT_TRACE_HEADER *)
0x1800146c5  xor     ebx, ebx
0x1800146c7  mov     r15d, 1
0x1800146cd  test    r12, r12
0x1800146d0  jz      short loc_1800146DB
0x1800146d2  mov     rcx, r12; bstrString
0x1800146d5  call    cs:__imp_SysFreeString
0x1800146db  mov     rax, [rbp+540h+var_598]
0x1800146df  test    rax, rax
0x1800146e2  jz      short loc_1800146ED
0x1800146e4  mov     rcx, rax; bstrString
0x1800146e7  call    cs:__imp_SysFreeString
0x1800146ed  test    r13, r13
0x1800146f0  jz      short loc_1800146FB
0x1800146f2  mov     rcx, r13; bstrString
0x1800146f5  call    cs:__imp_SysFreeString
0x1800146fb  mov     rcx, [rsp+640h+var_5E0]; bstrString
0x180014700  test    rcx, rcx
0x180014703  jz      short loc_180014710
0x180014705  call    cs:__imp_SysFreeString
0x18001470b  mov     [rsp+640h+var_5E0], rbx
0x180014710  mov     rcx, [rsp+640h+var_5F0]
0x180014715  test    rcx, rcx
0x180014718  jz      short loc_18001472B
0x18001471a  mov     rax, [rcx]
0x18001471d  mov     rax, [rax+10h]
0x180014721  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014726  mov     [rsp+640h+var_5F0], rbx
0x18001472b  mov     rcx, [rbp+540h+var_5C0]
0x18001472f  test    rcx, rcx
0x180014732  jz      short loc_180014744
0x180014734  mov     rax, [rcx]
0x180014737  mov     rax, [rax+10h]
0x18001473b  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
