# CUSTOM_ERROR_TABLE::BuildTable(IHttpContext *,INativeSectionException * *)

- ea: `0x1800065f0`
- end: `0x1800070bb`
- name: `?BuildTable@CUSTOM_ERROR_TABLE@@QEAAJPEAVIHttpContext@@PEAPEAVINativeSectionException@@@Z`
- size: `2763`
- prototype: `__int64 __fastcall(CUSTOM_ERROR_TABLE *__hidden this, struct IHttpContext *, struct INativeSectionException **)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800012c0`

## callees

- `0x180001ff0`
- `0x180002b1c`
- `0x1800065f0`
- `0x1800070c4`
- `0x1800071ac`
- `0x180007524`
- `0x180007842`
- `0x180007870`
- `0x180008010`

## import_xrefs

- `msvcrt!iswalpha` at `0x180006a2f`
- `msvcrt!iswalpha` at `0x180006a2f`
- `msvcrt!wcschr` at `0x180006b70`
- `msvcrt!wcschr` at `0x180006b70`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180006c25`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180006c25`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x180006b90`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x180006b90`
- `iisutil!?GetString@LANG_STRING@@QEAAJPEBDKIPEAPEBGPEAK@Z` at `0x180006e06`
- `iisutil!?GetString@LANG_STRING@@QEAAJPEBDKIPEAPEBGPEAK@Z` at `0x180006e06`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180006e14`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180006e37`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000708b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180006e14`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180006e37`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000708b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180006bb2`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180006c45`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180006d0a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180006d4a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180006e6c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180006bb2`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180006c45`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180006d0a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180006d4a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180006e6c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180006809`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180006854`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180006ac6`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180006adf`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180006809`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180006854`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180006ac6`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180006adf`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x180006f90`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x180006fb7`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x180006f90`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x180006fb7`
- `iisutil!SAFE_snwprintf` at `0x180006e26`
- `iisutil!SAFE_snwprintf` at `0x180006e26`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000665c`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180006a96`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180006aa0`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180006da5`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000665c`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180006a96`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180006aa0`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180006da5`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180006e60`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180006e60`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180006cb6`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180006cb6`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180006b99`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180006b99`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180006d30`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180006d30`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180006ccb`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180006ccb`

## string_xrefs

- `0x18000671e`: `allowAbsolutePathsWhenDelegated`
- `0x1800067e3`: `defaultPath`
- `0x18000682b`: `detailedMoreInformationLink`
- `0x180006978`: `prefixLanguageFilePath`

## pseudocode

```c
__int64 __fastcall CUSTOM_ERROR_TABLE::BuildTable(
        CUSTOM_ERROR_TABLE *this,
        struct IHttpContext *a2,
        struct INativeSectionException **a3)
{
  __int64 (__fastcall **v6)(struct IHttpContext *); // rax
  char *v7; // rbx
  __int64 (__fastcall *v8)(struct IHttpContext *); // rax
  __int64 (__fastcall ***v9)(_QWORD); // rax
  unsigned __int16 *v10; // r12
  void (__fastcall ***v11)(_QWORD, GUID *, struct INativeConfigurationSystem **); // rax
  unsigned int v12; // edx
  int AlternateHostName; // r14d
  _DWORD *v14; // rsi
  unsigned int i; // edi
  wchar_t *v16; // rcx
  const unsigned __int16 *v17; // r12
  unsigned __int64 v18; // rax
  char *v19; // rax
  char *v20; // rax
  char **v21; // rcx
  unsigned __int64 v22; // rax
  BUFFER *Buffer; // rax
  __int64 (__fastcall *v24)(__int64, __int64, wchar_t *, unsigned __int16 *, unsigned int *, _QWORD, _QWORD, _QWORD); // rsi
  unsigned __int16 *Str; // rbx
  wchar_t *v26; // rdi
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 (__fastcall *v29)(__int64, __int64, wchar_t *, unsigned __int16 *, unsigned int *, _QWORD, _QWORD, _QWORD); // rsi
  unsigned __int16 *v30; // rbx
  wchar_t *v31; // rdi
  __int64 v32; // rax
  __int64 v33; // rax
  const unsigned __int16 *v34; // rax
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rax
  const char *v38; // rax
  __int64 v39; // rsi
  void (__fastcall *v40)(__int64, unsigned __int16 *, _QWORD, __int64); // rdi
  unsigned int CCH; // ebx
  unsigned __int16 *v42; // rax
  unsigned __int16 *v43; // r12
  int v44; // eax
  __int64 v45; // rax
  __int64 (__fastcall ***v46)(_QWORD); // rax
  unsigned int v47; // eax
  const unsigned __int16 *v48; // r9
  unsigned int Size; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v51; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v52; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v53; // [rsp+68h] [rbp-98h] BYREF
  wchar_t *v54; // [rsp+70h] [rbp-90h] BYREF
  struct INativeConfigurationSystem *v55; // [rsp+78h] [rbp-88h] BYREF
  int v56; // [rsp+80h] [rbp-80h] BYREF
  __int64 v57; // [rsp+88h] [rbp-78h] BYREF
  const unsigned __int16 *v58; // [rsp+90h] [rbp-70h] BYREF
  const unsigned __int16 *v59; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v60; // [rsp+A0h] [rbp-60h] BYREF
  int v61; // [rsp+A4h] [rbp-5Ch] BYREF
  int v62; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v63; // [rsp+B0h] [rbp-50h] BYREF
  const unsigned __int16 *v64; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v65; // [rsp+C0h] [rbp-40h] BYREF
  struct INativeConfigurationElement *v66; // [rsp+C8h] [rbp-38h] BYREF
  const unsigned __int16 *v67; // [rsp+D0h] [rbp-30h] BYREF
  const unsigned __int16 *v68; // [rsp+D8h] [rbp-28h] BYREF
  wchar_t *String1; // [rsp+E0h] [rbp-20h] BYREF
  struct INativeSectionException **v70; // [rsp+E8h] [rbp-18h]
  unsigned __int16 *v71; // [rsp+F0h] [rbp-10h]
  _BYTE v72[56]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v73[56]; // [rsp+130h] [rbp+30h] BYREF

  v70 = a3;
  v55 = 0;
  v52 = 0;
  v67 = 0;
  v68 = 0;
  v63 = 0;
  v60 = 0;
  v51 = 0;
  v61 = 0;
  v62 = 0;
  v56 = 0;
  v59 = 0;
  v64 = 0;
  STRU::STRU((STRU *)v72);
  v6 = *(__int64 (__fastcall ***)(struct IHttpContext *))a2;
  v7 = 0;
  v57 = 0;
  v66 = 0;
  v65 = 0;
  v8 = v6[20];
  String1 = 0;
  v9 = (__int64 (__fastcall ***)(_QWORD))v8(a2);
  v10 = (unsigned __int16 *)(**v9)(v9);
  v71 = v10;
  v11 = (void (__fastcall ***)(_QWORD, GUID *, struct INativeConfigurationSystem **))(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)s_pGlobalInfo + 56LL))(s_pGlobalInfo);
  (**v11)(v11, &IID_INativeConfigurationSystem, &v55);
  AlternateHostName = (*(__int64 (__fastcall **)(struct INativeConfigurationSystem *, const wchar_t *, unsigned __int16 *, __int64 *, struct INativeSectionException **, _QWORD))(*(_QWORD *)v55 + 24LL))(
                        v55,
                        L"system.webServer/httpErrors",
                        v10,
                        &v52,
                        a3,
                        0);
  if ( AlternateHostName < 0 )
    goto LABEL_83;
  v14 = (_DWORD *)((char *)this + 260);
  AlternateHostName = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v52 + 72LL))(
                        v52,
                        L"allowAbsolutePathsWhenDelegated",
                        (char *)this + 260,
                        0,
                        0);
  if ( AlternateHostName < 0 )
    goto LABEL_83;
  AlternateHostName = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v52 + 48LL))(
                        v52,
                        L"errorMode",
                        (char *)this + 252,
                        0,
                        0);
  if ( AlternateHostName < 0 )
    goto LABEL_83;
  AlternateHostName = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v52 + 48LL))(
                        v52,
                        L"existingResponse",
                        (char *)this + 256,
                        0,
                        0);
  if ( AlternateHostName < 0 )
    goto LABEL_83;
  AlternateHostName = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v52 + 48LL))(
                        v52,
                        L"defaultResponseMode",
                        (char *)this + 248,
                        0,
                        0);
  if ( AlternateHostName < 0 )
    goto LABEL_83;
  AlternateHostName = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v52 + 64LL))(
                        v52,
                        L"defaultPath",
                        &v67,
                        0,
                        0);
  if ( AlternateHostName < 0 )
    goto LABEL_83;
  AlternateHostName = STRU::Copy((CUSTOM_ERROR_TABLE *)((char *)this + 24), v67);
  if ( AlternateHostName < 0 )
    goto LABEL_83;
  AlternateHostName = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v52 + 64LL))(
                        v52,
                        L"detailedMoreInformationLink",
                        &v68,
                        0,
                        0);
  if ( AlternateHostName < 0 )
    goto LABEL_83;
  AlternateHostName = STRU::Copy((CUSTOM_ERROR_TABLE *)((char *)this + 136), v68);
  if ( AlternateHostName < 0 )
    goto LABEL_83;
  AlternateHostName = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v52 + 40LL))(v52, &v63);
  if ( AlternateHostName < 0 )
    goto LABEL_83;
  AlternateHostName = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v63 + 24LL))(v63, &v60);
  if ( AlternateHostName < 0 )
    goto LABEL_83;
  v53 = 0;
  for ( i = 0; ; ++i )
  {
    LODWORD(v58) = i;
    if ( i >= v60 )
      break;
    AlternateHostName = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v63 + 32LL))(v63, i, &v51);
    if ( AlternateHostName < 0 )
      goto LABEL_75;
    AlternateHostName = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v51 + 48LL))(
                          v51,
                          L"statusCode",
                          &v61,
                          0,
                          0);
    if ( AlternateHostName < 0 )
      goto LABEL_75;
    AlternateHostName = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v51 + 48LL))(
                          v51,
                          L"subStatusCode",
                          &v62,
                          0,
                          0);
    if ( AlternateHostName < 0 )
      goto LABEL_75;
    AlternateHostName = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v51 + 48LL))(
                          v51,
                          L"responseMode",
                          &v56,
                          0,
                          0);
    if ( AlternateHostName < 0 )
      goto LABEL_75;
    AlternateHostName = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v51 + 64LL))(
                          v51,
                          L"prefixLanguageFilePath",
                          &v59,
                          0,
                          0);
    if ( AlternateHostName < 0 )
      goto LABEL_75;
    AlternateHostName = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v51 + 64LL))(
                          v51,
                          L"path",
                          &v64,
                          0,
                          0);
    if ( AlternateHostName < 0 )
      goto LABEL_75;
    if ( !v56 )
    {
      v54 = 0;
      AlternateHostName = (*(__int64 (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v51 + 256LL))(v51, &v54);
      if ( AlternateHostName < 0 )
        goto LABEL_75;
      v16 = v54;
      if ( !v54 )
        goto LABEL_75;
      v17 = v64;
      if ( *v59 )
        v17 = v59;
      if ( *v17 != 92 || v17[1] != 92 )
      {
        if ( !iswalpha(*v17) || v17[1] != 58 || v17[2] != 92 )
        {
          AlternateHostName = (*(__int64 (__fastcall **)(struct INativeConfigurationSystem *, __int64 *))(*(_QWORD *)v55 + 56LL))(
                                v55,
                                &v57);
          if ( AlternateHostName < 0 )
            goto LABEL_75;
          v22 = -1;
          do
            ++v22;
          while ( v54[v22] );
          if ( v22 <= 0x18 || (v54 += 24, (v54 = wcschr(v54, 0x2Fu)) == 0) )
            v54 = L"/";
          Buffer = STRU::QueryBuffer((STRU *)v72);
          Size = BUFFER::QuerySize(Buffer);
          v24 = *(__int64 (__fastcall **)(__int64, __int64, wchar_t *, unsigned __int16 *, unsigned int *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v57 + 40LL);
          Str = STRU::QueryStr((STRU *)v72);
          v26 = v54;
          v27 = (**(__int64 (__fastcall ***)(struct IHttpContext *))a2)(a2);
          v28 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v27 + 8LL))(v27);
          AlternateHostName = v24(v57, v28, v26, Str, &Size, 0, 0, 0);
          if ( AlternateHostName == -2147024774 )
          {
            AlternateHostName = STRU::Resize((STRU *)v72, Size);
            if ( AlternateHostName < 0 )
              goto LABEL_75;
            v29 = *(__int64 (__fastcall **)(__int64, __int64, wchar_t *, unsigned __int16 *, unsigned int *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v57 + 40LL);
            v30 = STRU::QueryStr((STRU *)v72);
            v31 = v54;
            v32 = (**(__int64 (__fastcall ***)(struct IHttpContext *))a2)(a2);
            v33 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v32 + 8LL))(v32);
            AlternateHostName = v29(v57, v33, v31, v30, &Size, 0, 0, 0);
          }
          v7 = 0;
          if ( AlternateHostName < 0 )
            goto LABEL_83;
          STRU::SyncWithBuffer((STRU *)v72);
          AlternateHostName = STRU::Append((STRU *)v72, L"\\", 1u);
          if ( AlternateHostName < 0 )
            goto LABEL_83;
          v34 = v59;
          v35 = -1;
          do
            ++v35;
          while ( v59[v35] );
          if ( v35 == 1 && *v59 == 46 )
          {
            v53 = 1;
          }
          else if ( !v53 )
          {
            AlternateHostName = STRU::Append((STRU *)v72, v17);
            if ( AlternateHostName < 0 )
              goto LABEL_83;
            v34 = v59;
          }
          if ( *v34 )
            v59 = STRU::QueryStr((STRU *)v72);
          else
            v64 = STRU::QueryStr((STRU *)v72);
          i = (unsigned int)v58;
          v14 = (_DWORD *)((char *)this + 260);
          goto LABEL_35;
        }
        v16 = v54;
      }
      if ( !*v14 )
      {
        v18 = -1;
        do
          ++v18;
        while ( v16[v18] );
        if ( v18 > 0x17 )
        {
          LOWORD(Size) = 0;
          v58 = 0;
          v53 = 0;
          STRU::STRU((STRU *)v73);
          AlternateHostName = -2147024883;
          v37 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 24LL))(a2);
          v38 = (const char *)(*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v37 + 16LL))(
                                v37,
                                23,
                                &Size);
          if ( (int)LANG_STRING::GetString(
                      (LANG_STRING *)CUSTOM_ERROR_HANDLER::sm_pLangString,
                      v38,
                      (unsigned __int16)Size,
                      0x3236u,
                      &v58,
                      &v53) >= 0 )
          {
            if ( (int)SAFE_snwprintf((struct STRU *)v73, v58, v17) >= 0 )
            {
              v39 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 32LL))(a2);
              v40 = *(void (__fastcall **)(__int64, unsigned __int16 *, _QWORD, __int64))(*(_QWORD *)v39 + 192LL);
              CCH = STRU::QueryCCH((STRU *)v73);
              v42 = STRU::QueryStr((STRU *)v73);
              v40(v39, v42, CCH, 1);
            }
            STRU::~STRU((STRU *)v73);
          }
          else
          {
            STRU::~STRU((STRU *)v73);
          }
          goto LABEL_75;
        }
      }
    }
LABEL_35:
    v19 = (char *)operator new(0x90u);
    v7 = v19;
    if ( !v19 )
    {
      AlternateHostName = -2147024888;
LABEL_75:
      v7 = 0;
      goto LABEL_83;
    }
    STRU::STRU((STRU *)(v19 + 24));
    STRU::STRU((STRU *)(v7 + 80));
    *((_QWORD *)v7 + 1) = v7;
    *(_QWORD *)v7 = v7;
    *((_WORD *)v7 + 8) = v61;
    *((_DWORD *)v7 + 34) = v56;
    AlternateHostName = STRU::Copy((STRU *)(v7 + 80), v64);
    if ( AlternateHostName < 0 )
      goto LABEL_83;
    AlternateHostName = STRU::Copy((STRU *)(v7 + 24), v59);
    if ( AlternateHostName < 0 )
      goto LABEL_83;
    v20 = (char *)this + 8;
    if ( v62 == -1 )
    {
      *((_WORD *)v7 + 9) = -1;
      v21 = (char **)*((_QWORD *)this + 2);
      if ( *v21 != v20 )
        goto LABEL_73;
      *(_QWORD *)v7 = v20;
      *((_QWORD *)v7 + 1) = v21;
      *v21 = v7;
      *((_QWORD *)this + 2) = v7;
    }
    else
    {
      *((_WORD *)v7 + 9) = v62;
      v36 = *(_QWORD *)v20;
      if ( *(char **)(*(_QWORD *)v20 + 8LL) != v20 )
LABEL_73:
        __fastfail(3u);
      *(_QWORD *)v7 = v36;
      *((_QWORD *)v7 + 1) = v20;
      *(_QWORD *)(v36 + 8) = v7;
      *(_QWORD *)v20 = v7;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
    v51 = 0;
  }
  v43 = v71;
  AlternateHostName = (*(__int64 (__fastcall **)(struct INativeConfigurationSystem *, const wchar_t *, unsigned __int16 *, struct INativeConfigurationElement **, struct INativeSectionException **, __int64 *))(*(_QWORD *)v55 + 24LL))(
                        v55,
                        L"system.webServer/staticContent",
                        v71,
                        &v66,
                        v70,
                        &v65);
  v7 = 0;
  if ( AlternateHostName >= 0 )
  {
    AlternateHostName = (*(__int64 (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v65 + 24LL))(v65, &String1);
    if ( AlternateHostName >= 0 )
    {
      v44 = wcscmp_0(String1, L"MACHINE/WEBROOT/APPHOST");
      AlternateHostName = MIME_MAP::Initialize((CUSTOM_ERROR_TABLE *)((char *)this + 264), v66, v44 == 0);
      if ( AlternateHostName >= 0 )
      {
        v45 = (**(__int64 (__fastcall ***)(struct IHttpContext *))a2)(a2);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 8LL))(v45);
        v46 = (__int64 (__fastcall ***)(_QWORD))(**(__int64 (__fastcall ***)(struct IHttpContext *))a2)(a2);
        v47 = (**v46)(v46);
        if ( (int)CUSTOM_ERROR_TABLE::ReadFrebConfig(this, v55, v47, v48) < 0 )
          STRU::Reset((CUSTOM_ERROR_TABLE *)((char *)this + 80));
        AlternateHostName = CUSTOM_ERROR_TABLE::ReadAlternateHostName(this, v55, v43);
        if ( AlternateHostName < 0 )
        {
          STRU::Reset((CUSTOM_ERROR_TABLE *)((char *)this + 192));
          AlternateHostName = 0;
        }
      }
    }
  }
LABEL_83:
  if ( v65 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
    v65 = 0;
  }
  if ( v66 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v66 + 16LL))(v66);
    v66 = 0;
  }
  if ( v7 )
    CUSTOM_ERROR_ENTRY::`scalar deleting destructor'((CUSTOM_ERROR_ENTRY *)v7, v12);
  if ( v51 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
    v51 = 0;
  }
  if ( v63 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
    v63 = 0;
  }
  if ( v52 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
    v52 = 0;
  }
  if ( v57 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
    v57 = 0;
  }
  if ( v55 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationSystem *))(*(_QWORD *)v55 + 16LL))(v55);
    v55 = 0;
  }
  STRU::~STRU((STRU *)v72);
  return (unsigned int)AlternateHostName;
}

```

## disassembly

```asm
0x1800065f0  mov     [rsp-8+arg_18], rbx
0x1800065f5  push    rbp
0x1800065f6  push    rsi
0x1800065f7  push    rdi
0x1800065f8  push    r12
0x1800065fa  push    r13
0x1800065fc  push    r14
0x1800065fe  push    r15
0x180006600  lea     rbp, [rsp-70h]
0x180006605  sub     rsp, 170h
0x18000660c  mov     rax, cs:__security_cookie
0x180006613  xor     rax, rsp
0x180006616  mov     [rbp+0A0h+var_38], rax
0x18000661a  xor     esi, esi
0x18000661c  mov     [rbp+0A0h+var_B8], r8
0x180006620  mov     r15, rcx
0x180006623  mov     [rsp+1A0h+var_128], rsi
0x180006628  lea     rcx, [rbp+0A0h+var_A8]
0x18000662c  mov     [rsp+1A0h+var_140], rsi
0x180006631  mov     [rbp+0A0h+var_D0], rsi
0x180006635  mov     rdi, r8
0x180006638  mov     [rbp+0A0h+var_C8], rsi
0x18000663c  mov     r13, rdx
0x18000663f  mov     [rbp+0A0h+var_F0], rsi
0x180006643  mov     [rbp+0A0h+var_100], esi
0x180006646  mov     [rsp+1A0h+var_148], rsi
0x18000664b  mov     [rbp+0A0h+var_FC], esi
0x18000664e  mov     [rbp+0A0h+var_F8], esi
0x180006651  mov     [rbp+0A0h+var_120], esi
0x180006654  mov     [rbp+0A0h+var_108], rsi
0x180006658  mov     [rbp+0A0h+var_E8], rsi
0x18000665c  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180006662  mov     rax, [r13+0]
0x180006666  mov     rcx, r13
0x180006669  mov     ebx, esi
0x18000666b  mov     [rbp+0A0h+var_118], rsi
0x18000666f  mov     [rbp+0A0h+var_D8], rsi
0x180006673  mov     [rbp+0A0h+var_E0], rsi
0x180006677  mov     rax, [rax+0A0h]
0x18000667e  mov     [rbp+0A0h+String1], rsi
0x180006682  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006687  mov     rdx, rax
0x18000668a  mov     rcx, [rax]
0x18000668d  mov     rax, [rcx]
0x180006690  mov     rcx, rdx
0x180006693  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006698  mov     rcx, cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * s_pGlobalInfo
0x18000669f  mov     r12, rax
0x1800066a2  mov     [rbp+0A0h+var_B0], rax
0x1800066a6  mov     rdx, [rcx]
0x1800066a9  mov     rax, [rdx+38h]
0x1800066ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066b2  mov     r9, rax
0x1800066b5  lea     r8, [rsp+1A0h+var_128]
0x1800066ba  lea     rdx, IID_INativeConfigurationSystem
0x1800066c1  mov     rcx, [rax]
0x1800066c4  mov     rax, [rcx]
0x1800066c7  mov     rcx, r9
0x1800066ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066cf  mov     rcx, [rsp+1A0h+var_128]
0x1800066d4  lea     r9, [rsp+1A0h+var_140]
0x1800066d9  mov     [rsp+1A0h+var_178], rsi
0x1800066de  lea     rdx, aSystemWebserve_0; "system.webServer/httpErrors"
0x1800066e5  mov     r8, r12
0x1800066e8  mov     [rsp+1A0h+var_180], rdi
0x1800066ed  mov     rax, [rcx]
0x1800066f0  mov     rax, [rax+18h]
0x1800066f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066f9  xor     r12d, r12d
0x1800066fc  mov     r14d, eax
0x1800066ff  test    eax, eax
0x180006701  js      loc_180006FC5
0x180006707  mov     rcx, [rsp+1A0h+var_140]
0x18000670c  lea     rsi, [r15+104h]
0x180006713  xor     r9d, r9d
0x180006716  mov     [rsp+1A0h+var_180], r12
0x18000671b  mov     r8, rsi
0x18000671e  lea     rdx, aAllowabsolutep; "allowAbsolutePathsWhenDelegated"
0x180006725  mov     rax, [rcx]
0x180006728  mov     rax, [rax+48h]
0x18000672c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006731  mov     r14d, eax
0x180006734  test    eax, eax
0x180006736  js      loc_180006FC5
0x18000673c  mov     rcx, [rsp+1A0h+var_140]
0x180006741  lea     r8, [r15+0FCh]
0x180006748  xor     r9d, r9d
0x18000674b  mov     [rsp+1A0h+var_180], r12
0x180006750  lea     rdx, aErrormode; "errorMode"
0x180006757  mov     rax, [rcx]
0x18000675a  mov     rax, [rax+30h]
0x18000675e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006763  mov     r14d, eax
0x180006766  test    eax, eax
0x180006768  js      loc_180006FC5
0x18000676e  mov     rcx, [rsp+1A0h+var_140]
0x180006773  lea     r8, [r15+100h]
0x18000677a  xor     r9d, r9d
0x18000677d  mov     [rsp+1A0h+var_180], r12
0x180006782  lea     rdx, aExistingrespon; "existingResponse"
0x180006789  mov     rax, [rcx]
0x18000678c  mov     rax, [rax+30h]
0x180006790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006795  mov     r14d, eax
0x180006798  test    eax, eax
0x18000679a  js      loc_180006FC5
0x1800067a0  mov     rcx, [rsp+1A0h+var_140]
0x1800067a5  lea     r8, [r15+0F8h]
0x1800067ac  xor     r9d, r9d
0x1800067af  mov     [rsp+1A0h+var_180], r12
0x1800067b4  lea     rdx, aDefaultrespons; "defaultResponseMode"
0x1800067bb  mov     rax, [rcx]
0x1800067be  mov     rax, [rax+30h]
0x1800067c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067c7  mov     r14d, eax
0x1800067ca  test    eax, eax
0x1800067cc  js      loc_180006FC5
0x1800067d2  mov     rcx, [rsp+1A0h+var_140]
0x1800067d7  lea     r8, [rbp+0A0h+var_D0]
0x1800067db  xor     r9d, r9d
0x1800067de  mov     [rsp+1A0h+var_180], r12
0x1800067e3  lea     rdx, aDefaultpath; "defaultPath"
0x1800067ea  mov     rax, [rcx]
0x1800067ed  mov     rax, [rax+40h]
0x1800067f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067f6  mov     r14d, eax
0x1800067f9  test    eax, eax
0x1800067fb  js      loc_180006FC5
0x180006801  mov     rdx, [rbp+0A0h+var_D0]
0x180006805  lea     rcx, [r15+18h]
0x180006809  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000680f  mov     r14d, eax
0x180006812  test    eax, eax
0x180006814  js      loc_180006FC5
0x18000681a  mov     rcx, [rsp+1A0h+var_140]
0x18000681f  lea     r8, [rbp+0A0h+var_C8]
0x180006823  xor     r9d, r9d
0x180006826  mov     [rsp+1A0h+var_180], r12
0x18000682b  lea     rdx, aDetailedmorein; "detailedMoreInformationLink"
0x180006832  mov     rax, [rcx]
0x180006835  mov     rax, [rax+40h]
0x180006839  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000683e  mov     r14d, eax
0x180006841  test    eax, eax
0x180006843  js      loc_180006FC5
0x180006849  mov     rdx, [rbp+0A0h+var_C8]
0x18000684d  lea     rcx, [r15+88h]
0x180006854  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000685a  mov     r14d, eax
0x18000685d  test    eax, eax
0x18000685f  js      loc_180006FC5
0x180006865  mov     rcx, [rsp+1A0h+var_140]
0x18000686a  lea     rdx, [rbp+0A0h+var_F0]
0x18000686e  mov     rax, [rcx]
0x180006871  mov     rax, [rax+28h]
0x180006875  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000687a  mov     r14d, eax
0x18000687d  test    eax, eax
0x18000687f  js      loc_180006FC5
0x180006885  mov     rcx, [rbp+0A0h+var_F0]
0x180006889  lea     rdx, [rbp+0A0h+var_100]
0x18000688d  mov     rax, [rcx]
0x180006890  mov     rax, [rax+18h]
0x180006894  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006899  mov     r14d, eax
0x18000689c  test    eax, eax
0x18000689e  js      loc_180006FC5
0x1800068a4  mov     [rsp+1A0h+var_138], r12d
0x1800068a9  mov     edi, r12d
0x1800068ac  mov     dword ptr [rbp+0A0h+var_110], edi
0x1800068af  cmp     edi, [rbp+0A0h+var_100]
0x1800068b2  jnb     loc_180006EA0
0x1800068b8  mov     rcx, [rbp+0A0h+var_F0]
0x1800068bc  lea     r8, [rsp+1A0h+var_148]
0x1800068c1  mov     edx, edi
0x1800068c3  mov     rax, [rcx]
0x1800068c6  mov     rax, [rax+20h]
0x1800068ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068cf  mov     r14d, eax
0x1800068d2  test    eax, eax
0x1800068d4  js      loc_180006E98
0x1800068da  mov     rcx, [rsp+1A0h+var_148]
0x1800068df  lea     r8, [rbp+0A0h+var_FC]
0x1800068e3  xor     r9d, r9d
0x1800068e6  mov     [rsp+1A0h+var_180], r12
0x1800068eb  lea     rdx, aStatuscode; "statusCode"
0x1800068f2  mov     rax, [rcx]
0x1800068f5  mov     rax, [rax+30h]
0x1800068f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068fe  mov     r14d, eax
0x180006901  test    eax, eax
0x180006903  js      loc_180006E98
0x180006909  mov     rcx, [rsp+1A0h+var_148]
0x18000690e  lea     r8, [rbp+0A0h+var_F8]
0x180006912  xor     r9d, r9d
0x180006915  mov     [rsp+1A0h+var_180], r12
0x18000691a  lea     rdx, aSubstatuscode; "subStatusCode"
0x180006921  mov     rax, [rcx]
0x180006924  mov     rax, [rax+30h]
0x180006928  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000692d  mov     r14d, eax
0x180006930  test    eax, eax
0x180006932  js      loc_180006E98
0x180006938  mov     rcx, [rsp+1A0h+var_148]
0x18000693d  lea     r8, [rbp+0A0h+var_120]
0x180006941  xor     r9d, r9d
0x180006944  mov     [rsp+1A0h+var_180], r12
0x180006949  lea     rdx, aResponsemode; "responseMode"
0x180006950  mov     rax, [rcx]
0x180006953  mov     rax, [rax+30h]
0x180006957  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000695c  mov     r14d, eax
0x18000695f  test    eax, eax
0x180006961  js      loc_180006E98
0x180006967  mov     rcx, [rsp+1A0h+var_148]
0x18000696c  lea     r8, [rbp+0A0h+var_108]
0x180006970  xor     r9d, r9d
0x180006973  mov     [rsp+1A0h+var_180], r12
0x180006978  lea     rdx, aPrefixlanguage; "prefixLanguageFilePath"
0x18000697f  mov     rax, [rcx]
0x180006982  mov     rax, [rax+40h]
0x180006986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000698b  mov     r14d, eax
0x18000698e  test    eax, eax
0x180006990  js      loc_180006E98
0x180006996  mov     rcx, [rsp+1A0h+var_148]
0x18000699b  lea     r8, [rbp+0A0h+var_E8]
0x18000699f  xor     r9d, r9d
0x1800069a2  mov     [rsp+1A0h+var_180], r12
0x1800069a7  lea     rdx, aPath; "path"
0x1800069ae  mov     rax, [rcx]
0x1800069b1  mov     rax, [rax+40h]
0x1800069b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069ba  mov     r14d, eax
0x1800069bd  test    eax, eax
0x1800069bf  js      loc_180006E98
0x1800069c5  cmp     [rbp+0A0h+var_120], r12d
0x1800069c9  jnz     loc_180006A7C
0x1800069cf  mov     rcx, [rsp+1A0h+var_148]
0x1800069d4  lea     rdx, [rsp+1A0h+var_130]
0x1800069d9  mov     [rsp+1A0h+var_130], r12
0x1800069de  mov     rax, [rcx]
0x1800069e1  mov     rax, [rax+100h]
0x1800069e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069ed  mov     r14d, eax
0x1800069f0  test    eax, eax
0x1800069f2  js      loc_180006E98
0x1800069f8  mov     rcx, [rsp+1A0h+var_130]
0x1800069fd  test    rcx, rcx
0x180006a00  jz      loc_180006E98
0x180006a06  mov     rax, [rbp+0A0h+var_108]
0x180006a0a  xor     r14d, r14d
0x180006a0d  mov     r12, [rbp+0A0h+var_E8]
0x180006a11  cmp     [rax], r14w
0x180006a15  cmovnz  r12, rax
0x180006a19  cmp     word ptr [r12], 5Ch ; '\'
0x180006a1f  jnz     short loc_180006A2A
0x180006a21  cmp     word ptr [r12+2], 5Ch ; '\'
0x180006a28  jz      short loc_180006A5C
0x180006a2a  movzx   ecx, word ptr [r12]; C
0x180006a2f  call    cs:__imp_iswalpha
0x180006a35  test    eax, eax
0x180006a37  jz      loc_180006B26
0x180006a3d  cmp     word ptr [r12+2], 3Ah ; ':'
0x180006a44  jnz     loc_180006B26
0x180006a4a  cmp     word ptr [r12+4], 5Ch ; '\'
0x180006a51  jnz     loc_180006B26
0x180006a57  mov     rcx, [rsp+1A0h+var_130]
0x180006a5c  cmp     [rsi], r14d
0x180006a5f  jnz     short loc_180006A79
0x180006a61  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006a65  inc     rax
0x180006a68  cmp     [rcx+rax*2], r14w
0x180006a6d  jnz     short loc_180006A65
0x180006a6f  cmp     rax, 17h
0x180006a73  ja      loc_180006D92
0x180006a79  xor     r12d, r12d
0x180006a7c  mov     ecx, 90h; Size
0x180006a81  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006a86  mov     rbx, rax
0x180006a89  test    rax, rax
0x180006a8c  jz      loc_180006E92
0x180006a92  lea     rcx, [rax+18h]
0x180006a96  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180006a9c  lea     rcx, [rbx+50h]
0x180006aa0  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180006aa6  mov     [rbx+8], rbx
0x180006aaa  lea     rcx, [rbx+50h]
0x180006aae  mov     [rbx], rbx
0x180006ab1  movzx   eax, word ptr [rbp+0A0h+var_FC]
0x180006ab5  mov     [rbx+10h], ax
0x180006ab9  mov     eax, [rbp+0A0h+var_120]
0x180006abc  mov     [rbx+88h], eax
0x180006ac2  mov     rdx, [rbp+0A0h+var_E8]
0x180006ac6  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180006acc  mov     r14d, eax
0x180006acf  test    eax, eax
0x180006ad1  js      loc_180006FC5
0x180006ad7  mov     rdx, [rbp+0A0h+var_108]
0x180006adb  lea     rcx, [rbx+18h]
  ... truncated ...
```
