# USER_SESSION::MapPath(ushort const *,FTP_METADATA *,STRU *)

- ea: `0x180011c38`
- end: `0x180012396`
- name: `?MapPath@USER_SESSION@@AEAAJPEBGPEAVFTP_METADATA@@PEAVSTRU@@@Z`
- size: `1886`
- prototype: `__int64 __fastcall(USER_SESSION *this, const unsigned __int16 *, struct FTP_METADATA *, struct STRU *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x18000fdd8`

## callees

- `0x180001210`
- `0x180011c38`
- `0x180018764`
- `0x180018ac0`
- `0x18002b2bc`
- `0x18004700f`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800120ba`
- `OLEAUT32!__imp_SysAllocString` at `0x1800120cf`
- `OLEAUT32!__imp_SysAllocString` at `0x1800120ba`
- `OLEAUT32!__imp_SysAllocString` at `0x1800120cf`
- `OLEAUT32!__imp_SysFreeString` at `0x180012318`
- `OLEAUT32!__imp_SysFreeString` at `0x180012326`
- `OLEAUT32!__imp_SysFreeString` at `0x180012336`
- `OLEAUT32!__imp_SysFreeString` at `0x180012318`
- `OLEAUT32!__imp_SysFreeString` at `0x180012326`
- `OLEAUT32!__imp_SysFreeString` at `0x180012336`
- `iisutil!MakePathCanonicalizationProof` at `0x18001221a`
- `iisutil!MakePathCanonicalizationProof` at `0x18001221a`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x18001205b`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x1800121f2`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x18001205b`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x1800121f2`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180011fe8`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001211d`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180011fe8`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001211d`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180011ca8`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180011ca8`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180012141`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001216c`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180012188`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800121af`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180012141`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001216c`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180012188`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800121af`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180011de8`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180011de8`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x180011d6b`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x180011ebb`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x1800122ec`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x180011d6b`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x180011ebb`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x1800122ec`
- `iisutil!PuDbgPrintError` at `0x180011f1c`
- `iisutil!PuDbgPrintError` at `0x180011f1c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180012364`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180012364`

## string_xrefs

- `0x180011ef1`: `Failed to build VDir Parent table from custom home directory string\n`
- `0x180011f03`: `USER_SESSION::MapPath`
- `0x180011f56`: `Failed to map path for custom isolation mode\n`

## pseudocode

```c
__int64 __fastcall USER_SESSION::MapPath(
        USER_SESSION *this,
        const unsigned __int16 *a2,
        struct FTP_METADATA *a3,
        struct STRU *a4)
{
  OLECHAR *v7; // r12
  OLECHAR *v8; // r13
  __int64 v9; // rax
  __int64 v10; // r15
  CEtwTracer *v11; // rdi
  int v12; // eax
  __int64 v13; // rax
  int MappingExtension; // edi
  unsigned int v15; // r8d
  __int64 v16; // rdx
  _QWORD *v17; // rdi
  __int64 v18; // rax
  CEtwTracer *v19; // rbx
  const char *v20; // rax
  __int64 v21; // r8
  FTP_VDIR_PARENT_TABLE *v22; // rcx
  __int64 v23; // rdx
  const unsigned __int16 *v24; // r8
  const unsigned __int16 *v25; // rcx
  char *v26; // rax
  __int64 v27; // rcx
  unsigned __int16 v28; // ax
  const unsigned __int16 *v29; // rdx
  const OLECHAR *v30; // rdi
  int v31; // esi
  __int64 v32; // rax
  const OLECHAR *v33; // rcx
  const unsigned __int16 *v34; // rax
  const unsigned __int16 *v35; // rax
  unsigned __int16 v36; // ax
  const unsigned __int16 *v37; // rdx
  struct STRU *v38; // rbx
  __int64 v39; // rax
  const unsigned __int16 *v40; // rbx
  CEtwTracer *v41; // rsi
  int v42; // eax
  struct STRU *v44; // [rsp+40h] [rbp-C0h] BYREF
  struct IAppHostMappingExtension *v45; // [rsp+48h] [rbp-B8h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp-B0h] BYREF
  struct IAppHostAdminManager *v47; // [rsp+58h] [rbp-A8h]
  _QWORD *v48; // [rsp+60h] [rbp-A0h]
  _BYTE v49[32]; // [rsp+68h] [rbp-98h] BYREF
  const unsigned __int16 *v50; // [rsp+88h] [rbp-78h]
  unsigned int v51; // [rsp+90h] [rbp-70h]
  unsigned int v52; // [rsp+98h] [rbp-68h]
  struct _EVENT_TRACE_HEADER v53; // [rsp+A0h] [rbp-60h] BYREF
  char *v54; // [rsp+D0h] [rbp-30h]
  int v55; // [rsp+D8h] [rbp-28h]
  const unsigned __int16 *v56; // [rsp+E0h] [rbp-20h]
  int v57; // [rsp+E8h] [rbp-18h]
  struct _EVENT_TRACE_HEADER v58; // [rsp+F0h] [rbp-10h] BYREF
  char *v59; // [rsp+120h] [rbp+20h]
  int v60; // [rsp+128h] [rbp+28h]
  struct STRU **v61; // [rsp+130h] [rbp+30h]
  int v62; // [rsp+138h] [rbp+38h]
  unsigned __int16 v63[264]; // [rsp+140h] [rbp+40h] BYREF

  v44 = a4;
  v45 = 0;
  v7 = 0;
  v8 = 0;
  bstrString = 0;
  memset_0(v63, 0, 0x208u);
  STRU::STRU((STRU *)v49, v63, 0x104u);
  v9 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
  v10 = -1;
  if ( *(_DWORD *)(v9 + 8) && (*(_BYTE *)(v9 + 40) & 4) != 0 && *(_DWORD *)(v9 + 44) >= 4u )
  {
    v11 = (CEtwTracer *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
    memset_0(&v53.FieldTypeFlags, 0, 0x4Eu);
    v53.UserTime = 1703936;
    v53.Size = 80;
    v53.Class.Version = 1;
    v53.Class.Type = 1;
    v53.GuidPtr = (ULONGLONG)&`FtpProcessingEvents::GetAreaGuid'::`2'::AreaGuid;
    v54 = (char *)this + 1272;
    v55 = 16;
    v56 = a2;
    if ( a2 )
    {
      v13 = -1;
      do
        ++v13;
      while ( a2[v13] );
      v12 = 2 * v13 + 2;
    }
    else
    {
      v12 = 0;
    }
    v57 = v12;
    CEtwTracer::EtwTraceEvent(v11, &v53);
  }
  v47 = (struct IAppHostAdminManager *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 24LL))(g_pFtpServer);
  MappingExtension = Config_GetMappingExtension(v47, &v45);
  v16 = 0;
  if ( MappingExtension < 0 )
    goto LABEL_19;
  if ( *((_DWORD *)this + 3) != 5 )
    goto LABEL_38;
  if ( !*((_QWORD *)this + 43) && **(_WORD **)(*((_QWORD *)this + 118) + 264LL) )
  {
    v17 = operator new(0x48u);
    v48 = v17;
    if ( v17 )
    {
      STRU::STRU(v17 + 2);
      v17[1] = v17;
      *v17 = v17;
    }
    else
    {
      v17 = 0;
    }
    *((_QWORD *)this + 43) = v17;
    if ( !v17 )
    {
LABEL_18:
      MappingExtension = -2147024888;
      goto LABEL_19;
    }
    MappingExtension = FTP_VDIR_PARENT_TABLE::InitializeFromCustomHomeDirectoryInfo(
                         (FTP_VDIR_PARENT_TABLE *)v17,
                         *(const unsigned __int16 **)(*((_QWORD *)this + 118) + 264LL));
    v16 = 0;
    if ( MappingExtension < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) == 0 )
        goto LABEL_19;
      v20 = "Failed to build VDir Parent table from custom home directory string\r\n";
      v21 = 990;
LABEL_26:
      PuDbgPrintError(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\user_session.cxx",
        v21,
        "USER_SESSION::MapPath",
        MappingExtension,
        v20);
      goto LABEL_19;
    }
  }
  v22 = (FTP_VDIR_PARENT_TABLE *)*((_QWORD *)this + 43);
  if ( !v22 )
  {
LABEL_38:
    v26 = (char *)a3 + 360;
    if ( *((_DWORD *)this + 3) == 2 && **(_WORD **)v26 == 47 && !*(_WORD *)(*(_QWORD *)v26 + 2LL) )
    {
      MappingExtension = STRU::Copy((STRU *)v49, *(const unsigned __int16 **)(*((_QWORD *)this + 118) + 264LL));
      if ( MappingExtension < 0 )
        goto LABEL_19;
      if ( v52 )
      {
        v27 = v52 - 1;
        if ( v50[v27] == 92 && (unsigned int)v27 < v51 >> 1 )
        {
          v50[v27] = 0;
          v52 = v27;
        }
      }
      if ( *a2 != 47 || a2[1] )
      {
        v28 = *a2;
        if ( *a2 )
        {
          while ( 1 )
          {
            v29 = L"\\";
            if ( v28 != 47 )
              v29 = a2;
            MappingExtension = STRU::Append((STRU *)v49, v29, 1u);
            if ( MappingExtension < 0 )
              goto LABEL_19;
            v28 = *++a2;
            if ( !*a2 )
              goto LABEL_76;
          }
        }
      }
      goto LABEL_76;
    }
    v30 = a2;
    v31 = 0;
    if ( *((_DWORD *)this + 3) == 1 && **(_WORD **)v26 == 47 && !*(_WORD *)(*(_QWORD *)v26 + 2LL) )
    {
      v30 = L"/";
      v31 = 1;
    }
    v32 = *((_QWORD *)this + 2);
    v33 = (const OLECHAR *)&dword_18004D454;
    if ( *(_QWORD *)(v32 + 8) )
      v33 = *(const OLECHAR **)(v32 + 8);
    v7 = SysAllocString(v33);
    if ( !v7 )
      goto LABEL_18;
    v8 = SysAllocString(v30);
    v16 = 0;
    if ( !v8 )
      goto LABEL_18;
    MappingExtension = ((__int64 (__fastcall *)(struct IAppHostMappingExtension *, OLECHAR *, OLECHAR *, BSTR *, _QWORD, _QWORD))v45->lpVtbl->MapPath)(
                         v45,
                         v7,
                         v8,
                         &bstrString,
                         0,
                         0);
    if ( MappingExtension >= 0 )
    {
      MappingExtension = STRU::Copy((STRU *)v49, bstrString);
      if ( MappingExtension >= 0 )
      {
        if ( !v31 )
        {
LABEL_76:
          v25 = v50;
          goto LABEL_77;
        }
        MappingExtension = STRU::Append((STRU *)v49, L"\\");
        if ( MappingExtension >= 0 )
        {
          v34 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 3) + 96LL))((char *)this + 24);
          MappingExtension = STRU::Append((STRU *)v49, v34);
          if ( MappingExtension >= 0 )
          {
            MappingExtension = STRU::Append((STRU *)v49, L"\\");
            if ( MappingExtension >= 0 )
            {
              v35 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 3) + 88LL))((char *)this + 24);
              MappingExtension = STRU::Append((STRU *)v49, v35);
              if ( MappingExtension >= 0 )
              {
                if ( *a2 != 47 || a2[1] )
                {
                  v36 = *a2;
                  if ( *a2 )
                  {
                    while ( 1 )
                    {
                      v37 = L"\\";
                      if ( v36 != 47 )
                        v37 = a2;
                      MappingExtension = STRU::Append((STRU *)v49, v37, 1u);
                      if ( MappingExtension < 0 )
                        goto LABEL_19;
                      v36 = *++a2;
                      if ( !*a2 )
                        goto LABEL_76;
                    }
                  }
                }
                goto LABEL_76;
              }
            }
          }
        }
      }
    }
LABEL_19:
    v18 = (*(__int64 (__fastcall **)(FTP_SERVERP *, __int64))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer, v16);
    if ( *(_DWORD *)(v18 + 8) && (*(_BYTE *)(v18 + 40) & 4) != 0 && *(_DWORD *)(v18 + 44) >= 3u )
    {
      v19 = (CEtwTracer *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
      LODWORD(v44) = MappingExtension;
      memset_0(&v58.FieldTypeFlags, 0, 0x4Eu);
      v58.UserTime = 1703936;
      v58.Size = 80;
      v58.Class.Version = 1;
      v58.Class.Type = 3;
      v58.GuidPtr = (ULONGLONG)&`FtpProcessingEvents::GetAreaGuid'::`2'::AreaGuid;
      v59 = (char *)this + 1272;
      v60 = 16;
      v61 = &v44;
      v62 = 4;
      CEtwTracer::EtwTraceEvent(v19, &v58);
    }
    goto LABEL_87;
  }
  MappingExtension = FTP_VDIR_PARENT_TABLE::MapPath(v22, a2, v15, (struct STRU *)v49);
  if ( MappingExtension < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_19;
    v20 = "Failed to map path for custom isolation mode\r\n";
    v21 = 1008;
    goto LABEL_26;
  }
  if ( !v52 )
  {
    v38 = v44;
    goto LABEL_80;
  }
  v23 = v52 - 1;
  v24 = v50;
  if ( v50[v23] == 92 && v52 > 2 && v50[v52 - 2] != 92 && (unsigned int)v23 < v51 >> 1 )
  {
    v50[v23] = 0;
    v52 = v23;
    v24 = v50;
  }
  v25 = v24;
LABEL_77:
  v38 = v44;
  MappingExtension = MakePathCanonicalizationProof(v25, v44);
  if ( MappingExtension < 0 )
    goto LABEL_19;
LABEL_80:
  v39 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
  if ( *(_DWORD *)(v39 + 8) && (*(_BYTE *)(v39 + 40) & 4) != 0 && *(_DWORD *)(v39 + 44) >= 4u )
  {
    v40 = (const unsigned __int16 *)*((_QWORD *)v38 + 4);
    v41 = (CEtwTracer *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
    memset_0(&v53.FieldTypeFlags, 0, 0x4Eu);
    v53.UserTime = 1703936;
    v53.Size = 80;
    v53.Class.Version = 1;
    v53.Class.Type = 2;
    v53.GuidPtr = (ULONGLONG)&`FtpProcessingEvents::GetAreaGuid'::`2'::AreaGuid;
    v54 = (char *)this + 1272;
    v55 = 16;
    v56 = v40;
    v42 = 0;
    if ( v40 )
    {
      do
        ++v10;
      while ( v40[v10] );
      v42 = 2 * v10 + 2;
    }
    v57 = v42;
    CEtwTracer::EtwTraceEvent(v41, &v53);
  }
LABEL_87:
  if ( v45 )
  {
    ((void (__fastcall *)(struct IAppHostMappingExtension *))v45->lpVtbl->Release)(v45);
    v45 = 0;
  }
  if ( v7 )
    SysFreeString(v7);
  if ( v8 )
    SysFreeString(v8);
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v47 )
    (*(void (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 208LL))(g_pFtpServer);
  STRU::~STRU(v49);
  return (unsigned int)MappingExtension;
}

```

## disassembly

```asm
0x180011c38  mov     [rsp-8+arg_10], rbx
0x180011c3d  push    rbp
0x180011c3e  push    rsi
0x180011c3f  push    rdi
0x180011c40  push    r12
0x180011c42  push    r13
0x180011c44  push    r14
0x180011c46  push    r15
0x180011c48  lea     rbp, [rsp-260h]
0x180011c50  sub     rsp, 360h
0x180011c57  mov     rax, cs:__security_cookie
0x180011c5e  xor     rax, rsp
0x180011c61  mov     [rbp+290h+var_40], rax
0x180011c68  mov     [rsp+390h+var_350], r9
0x180011c6d  mov     rsi, r8
0x180011c70  mov     rbx, rdx
0x180011c73  mov     r14, rcx
0x180011c76  xor     edi, edi
0x180011c78  mov     [rsp+390h+var_348], rdi
0x180011c7d  mov     r12d, edi
0x180011c80  mov     r13d, edi
0x180011c83  mov     [rsp+390h+bstrString], rdi
0x180011c88  xor     edx, edx; Val
0x180011c8a  mov     r8d, 208h; Size
0x180011c90  lea     rcx, [rbp+290h+var_250]; void *
0x180011c94  call    memset_0
0x180011c99  mov     r8d, 104h
0x180011c9f  lea     rdx, [rbp+290h+var_250]
0x180011ca3  lea     rcx, [rsp+390h+var_328]
0x180011ca8  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180011cae  nop
0x180011caf  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x180011cb6  mov     rax, [rcx]
0x180011cb9  mov     rax, [rax+20h]
0x180011cbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011cc2  or      r15, 0FFFFFFFFFFFFFFFFh
0x180011cc6  cmp     [rax+8], edi
0x180011cc9  jz      loc_180011D71
0x180011ccf  test    byte ptr [rax+28h], 4
0x180011cd3  jz      loc_180011D71
0x180011cd9  cmp     dword ptr [rax+2Ch], 4
0x180011cdd  jb      loc_180011D71
0x180011ce3  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x180011cea  mov     rax, [rcx]
0x180011ced  mov     rax, [rax+20h]
0x180011cf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011cf6  mov     rdi, rax
0x180011cf9  xor     edx, edx; Val
0x180011cfb  lea     r8d, [r13+4Eh]; Size
0x180011cff  lea     rcx, [rbp+290h+var_2EE]; void *
0x180011d03  call    memset_0
0x180011d08  mov     [rbp+290h+var_2C4], 1A0000h
0x180011d0f  lea     eax, [r13+50h]
0x180011d13  mov     [rbp+290h+var_2F0], ax
0x180011d17  lea     eax, [r13+1]
0x180011d1b  mov     [rbp+290h+var_2EA], ax
0x180011d1f  mov     [rbp+290h+var_2EC], al
0x180011d22  lea     rax, ?AreaGuid@?1??GetAreaGuid@FtpProcessingEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `FtpProcessingEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x180011d29  mov     [rbp+290h+var_2D8], rax
0x180011d2d  lea     rax, [r14+4F8h]
0x180011d34  mov     [rbp+290h+var_2C0], rax
0x180011d38  mov     [rbp+290h+var_2B8], 10h
0x180011d3f  mov     [rbp+290h+var_2B0], rbx
0x180011d43  xor     ecx, ecx
0x180011d45  test    rbx, rbx
0x180011d48  jnz     short loc_180011D4E
0x180011d4a  mov     eax, ecx
0x180011d4c  jmp     short loc_180011D61
0x180011d4e  mov     rax, r15
0x180011d51  inc     rax
0x180011d54  cmp     [rbx+rax*2], cx
0x180011d58  jnz     short loc_180011D51
0x180011d5a  lea     eax, ds:2[rax*2]
0x180011d61  mov     [rbp+290h+var_2A8], eax
0x180011d64  lea     rdx, [rbp+290h+var_2F0]
0x180011d68  mov     rcx, rdi
0x180011d6b  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z; CEtwTracer::EtwTraceEvent(_EVENT_TRACE_HEADER *)
0x180011d71  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x180011d78  mov     rax, [rcx]
0x180011d7b  mov     rax, [rax+18h]
0x180011d7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d84  mov     [rsp+390h+var_338], rax
0x180011d89  lea     rdx, [rsp+390h+var_348]; struct IAppHostMappingExtension **
0x180011d8e  mov     rcx, rax; struct IAppHostAdminManager *
0x180011d91  call    ?Config_GetMappingExtension@@YAJPEAUIAppHostAdminManager@@PEAPEAUIAppHostMappingExtension@@@Z; Config_GetMappingExtension(IAppHostAdminManager *,IAppHostMappingExtension * *)
0x180011d96  mov     edi, eax
0x180011d98  xor     edx, edx
0x180011d9a  test    eax, eax
0x180011d9c  js      short loc_180011E0F
0x180011d9e  cmp     dword ptr [r14+0Ch], 5
0x180011da3  jnz     loc_180011FAC
0x180011da9  cmp     [r14+158h], rdx
0x180011db0  jnz     loc_180011F27
0x180011db6  mov     rax, [r14+3B0h]
0x180011dbd  mov     rcx, [rax+108h]
0x180011dc4  cmp     [rcx], dx
0x180011dc7  jz      loc_180011F27
0x180011dcd  lea     ecx, [rdx+48h]; Size
0x180011dd0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011dd5  mov     rdi, rax
0x180011dd8  mov     [rsp+390h+var_330], rax
0x180011ddd  xor     eax, eax
0x180011ddf  test    rdi, rdi
0x180011de2  jz      short loc_180011DF7
0x180011de4  lea     rcx, [rdi+10h]
0x180011de8  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180011dee  mov     [rdi+8], rdi
0x180011df2  mov     [rdi], rdi
0x180011df5  jmp     short loc_180011DFA
0x180011df7  mov     rdi, rax
0x180011dfa  mov     [r14+158h], rdi
0x180011e01  test    rdi, rdi
0x180011e04  jnz     loc_180011EC6
0x180011e0a  mov     edi, 80070008h
0x180011e0f  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x180011e16  mov     rax, [rcx]
0x180011e19  mov     rax, [rax+20h]
0x180011e1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e22  xor     r15d, r15d
0x180011e25  cmp     [rax+8], r15d
0x180011e29  jz      loc_1800122F5
0x180011e2f  test    byte ptr [rax+28h], 4
0x180011e33  jz      loc_1800122F5
0x180011e39  cmp     dword ptr [rax+2Ch], 3
0x180011e3d  jb      loc_1800122F5
0x180011e43  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x180011e4a  mov     rax, [rcx]
0x180011e4d  mov     rax, [rax+20h]
0x180011e51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e56  mov     rbx, rax
0x180011e59  mov     dword ptr [rsp+390h+var_350], edi
0x180011e5d  xor     edx, edx; Val
0x180011e5f  lea     r8d, [r15+4Eh]; Size
0x180011e63  lea     rcx, [rbp+290h+var_29E]; void *
0x180011e67  call    memset_0
0x180011e6c  mov     [rbp+290h+var_274], 1A0000h
0x180011e73  lea     eax, [r15+50h]
0x180011e77  mov     [rbp+290h+var_2A0], ax
0x180011e7b  lea     eax, [r15+1]
0x180011e7f  mov     [rbp+290h+var_29A], ax
0x180011e83  mov     [rbp+290h+var_29C], 3
0x180011e87  lea     rax, ?AreaGuid@?1??GetAreaGuid@FtpProcessingEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `FtpProcessingEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x180011e8e  mov     [rbp+290h+var_288], rax
0x180011e92  lea     rcx, [r14+4F8h]
0x180011e99  mov     [rbp+290h+var_270], rcx
0x180011e9d  mov     [rbp+290h+var_268], 10h
0x180011ea4  lea     rax, [rsp+390h+var_350]
0x180011ea9  mov     [rbp+290h+var_260], rax
0x180011ead  mov     [rbp+290h+var_258], 4
0x180011eb4  lea     rdx, [rbp+290h+var_2A0]
0x180011eb8  mov     rcx, rbx
0x180011ebb  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z; CEtwTracer::EtwTraceEvent(_EVENT_TRACE_HEADER *)
0x180011ec1  jmp     loc_1800122F5
0x180011ec6  mov     rdx, [r14+3B0h]
0x180011ecd  mov     rdx, [rdx+108h]; unsigned __int16 *
0x180011ed4  mov     rcx, rdi; this
0x180011ed7  call    ?InitializeFromCustomHomeDirectoryInfo@FTP_VDIR_PARENT_TABLE@@QEAAJPEBG@Z; FTP_VDIR_PARENT_TABLE::InitializeFromCustomHomeDirectoryInfo(ushort const *)
0x180011edc  mov     edi, eax
0x180011ede  xor     edx, edx
0x180011ee0  test    eax, eax
0x180011ee2  jns     short loc_180011F27
0x180011ee4  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180011eeb  jz      loc_180011E0F
0x180011ef1  lea     rax, aFailedToBuildV_0; "Failed to build VDir Parent table from "...
0x180011ef8  mov     r8d, 3DEh
0x180011efe  mov     [rsp+390h+var_368], rax
0x180011f03  lea     r9, aUserSessionMap; "USER_SESSION::MapPath"
0x180011f0a  mov     dword ptr [rsp+390h+var_370], edi
0x180011f0e  lea     rdx, aInetsrvIisIisr_36; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x180011f15  mov     rcx, cs:g_pDebug
0x180011f1c  call    cs:__imp_PuDbgPrintError
0x180011f22  jmp     loc_180011E0F
0x180011f27  mov     rcx, [r14+158h]; this
0x180011f2e  test    rcx, rcx
0x180011f31  jz      short loc_180011FAC
0x180011f33  lea     r9, [rsp+390h+var_328]; struct STRU *
0x180011f38  mov     rdx, rbx; unsigned __int16 *
0x180011f3b  call    ?MapPath@FTP_VDIR_PARENT_TABLE@@QEAAJPEBGKPEAVSTRU@@@Z; FTP_VDIR_PARENT_TABLE::MapPath(ushort const *,ulong,STRU *)
0x180011f40  mov     edi, eax
0x180011f42  xor     r10d, r10d
0x180011f45  test    eax, eax
0x180011f47  jns     short loc_180011F65
0x180011f49  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180011f50  jz      loc_180011E0F
0x180011f56  lea     rax, aFailedToMapPat; "Failed to map path for custom isolation"...
0x180011f5d  mov     r8d, 3F0h
0x180011f63  jmp     short loc_180011EFE
0x180011f65  mov     eax, [rbp+290h+var_2F8]
0x180011f68  test    eax, eax
0x180011f6a  jz      loc_18001222C
0x180011f70  lea     edx, [rax-1]
0x180011f73  mov     r8, [rbp+290h+var_308]
0x180011f77  cmp     word ptr [r8+rdx*2], 5Ch ; '\'
0x180011f7d  jnz     short loc_180011FA4
0x180011f7f  cmp     eax, 2
0x180011f82  jbe     short loc_180011FA4
0x180011f84  add     eax, 0FFFFFFFEh
0x180011f87  cmp     word ptr [r8+rax*2], 5Ch ; '\'
0x180011f8d  jz      short loc_180011FA4
0x180011f8f  mov     eax, [rbp+290h+var_300]
0x180011f92  shr     eax, 1
0x180011f94  cmp     edx, eax
0x180011f96  jnb     short loc_180011FA4
0x180011f98  mov     [r8+rdx*2], r10w
0x180011f9d  mov     [rbp+290h+var_2F8], edx
0x180011fa0  mov     r8, [rbp+290h+var_308]
0x180011fa4  mov     rcx, r8
0x180011fa7  jmp     loc_180012212
0x180011fac  lea     rax, [rsi+168h]
0x180011fb3  cmp     dword ptr [r14+0Ch], 2
0x180011fb8  jnz     loc_18001207C
0x180011fbe  mov     rcx, [rax]
0x180011fc1  cmp     word ptr [rcx], 2Fh ; '/'
0x180011fc5  jnz     loc_18001207C
0x180011fcb  cmp     [rcx+2], dx
0x180011fcf  jnz     loc_18001207C
0x180011fd5  mov     rdx, [r14+3B0h]
0x180011fdc  mov     rdx, [rdx+108h]
0x180011fe3  lea     rcx, [rsp+390h+var_328]
0x180011fe8  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180011fee  mov     edi, eax
0x180011ff0  xor     r9d, r9d
0x180011ff3  test    eax, eax
0x180011ff5  js      loc_180011E0F
0x180011ffb  mov     ecx, [rbp+290h+var_2F8]
0x180011ffe  test    ecx, ecx
0x180012000  jz      short loc_180012021
0x180012002  dec     ecx
0x180012004  mov     r8, [rbp+290h+var_308]
0x180012008  cmp     word ptr [r8+rcx*2], 5Ch ; '\'
0x18001200e  jnz     short loc_180012021
0x180012010  mov     eax, [rbp+290h+var_300]
0x180012013  shr     eax, 1
0x180012015  cmp     ecx, eax
0x180012017  jnb     short loc_180012021
0x180012019  mov     [r8+rcx*2], r9w
0x18001201e  mov     [rbp+290h+var_2F8], ecx
0x180012021  cmp     word ptr [rbx], 2Fh ; '/'
0x180012025  jnz     short loc_180012032
0x180012027  cmp     [rbx+2], r9w
0x18001202c  jz      loc_18001220E
0x180012032  movzx   eax, word ptr [rbx]
0x180012035  test    ax, ax
0x180012038  jz      loc_18001220E
0x18001203e  mov     esi, 1
0x180012043  mov     r8d, esi
0x180012046  lea     rcx, [rsp+390h+var_328]
0x18001204b  cmp     ax, 2Fh ; '/'
0x18001204f  lea     rdx, asc_18004BD10; "\\"
0x180012056  jz      short loc_18001205B
0x180012058  mov     rdx, rbx
0x18001205b  call    cs:__imp_?Append@STRU@@QEAAJPEBGK@Z; STRU::Append(ushort const *,ulong)
0x180012061  mov     edi, eax
0x180012063  test    eax, eax
0x180012065  js      loc_180011E0F
0x18001206b  add     rbx, 2
0x18001206f  movzx   eax, word ptr [rbx]
0x180012072  test    ax, ax
0x180012075  jnz     short loc_180012043
0x180012077  jmp     loc_18001220E
0x18001207c  mov     rdi, rbx
0x18001207f  mov     esi, edx
0x180012081  mov     r8d, 1
0x180012087  cmp     [r14+0Ch], r8d
0x18001208b  jnz     short loc_1800120A6
0x18001208d  mov     rcx, [rax]
0x180012090  cmp     word ptr [rcx], 2Fh ; '/'
0x180012094  jnz     short loc_1800120A6
0x180012096  cmp     [rcx+2], dx
0x18001209a  jnz     short loc_1800120A6
0x18001209c  lea     rdi, asc_18004BD14; "/"
0x1800120a3  mov     esi, r8d
0x1800120a6  mov     rax, [r14+10h]
0x1800120aa  lea     rcx, dword_18004D454
0x1800120b1  cmp     [rax+8], rdx
0x1800120b5  cmovnz  rcx, [rax+8]; psz
0x1800120ba  call    cs:__imp_SysAllocString
0x1800120c0  mov     r12, rax
0x1800120c3  test    rax, rax
0x1800120c6  jz      loc_180011E0A
0x1800120cc  mov     rcx, rdi; psz
0x1800120cf  call    cs:__imp_SysAllocString
0x1800120d5  mov     r13, rax
0x1800120d8  xor     edx, edx
0x1800120da  test    rax, rax
0x1800120dd  jz      loc_180011E0A
0x1800120e3  mov     rcx, [rsp+390h+var_348]
0x1800120e8  mov     rax, [rcx]
0x1800120eb  mov     [rsp+390h+var_368], rdx
0x1800120f0  mov     [rsp+390h+var_370], rdx
0x1800120f5  lea     r9, [rsp+390h+bstrString]
0x1800120fa  mov     r8, r13
0x1800120fd  mov     rdx, r12
0x180012100  mov     rax, [rax+30h]
0x180012104  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012109  mov     edi, eax
0x18001210b  test    eax, eax
0x18001210d  js      loc_180011E0F
0x180012113  mov     rdx, [rsp+390h+bstrString]
0x180012118  lea     rcx, [rsp+390h+var_328]
  ... truncated ...
```
