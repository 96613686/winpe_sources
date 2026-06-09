# NOTIFICATION_CONTEXT::CallModulesInternal(int,ulong,long,ulong,W3_CONTEXT_BASE *,IHttpEventProvider *)

- ea: `0x180005bf0`
- end: `0x180006804`
- name: `?CallModulesInternal@NOTIFICATION_CONTEXT@@AEAA?AW4REQUEST_NOTIFICATION_STATUS@@HKJKPEAVW3_CONTEXT_BASE@@PEAVIHttpEventProvider@@@Z`
- size: `3092`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180005ba0`

## callees

- `0x180005bf0`
- `0x180006810`
- `0x18000d340`
- `0x18000f130`
- `0x18000f990`
- `0x180017800`
- `0x180017dcc`
- `0x1800181c0`
- `0x180018e98`
- `0x1800343ca`
- `0x1800343f0`
- `0x180035010`

## import_xrefs

- `msvcrt!wcschr` at `0x180005d52`
- `msvcrt!wcschr` at `0x180005d9f`
- `msvcrt!wcschr` at `0x180005d52`
- `msvcrt!wcschr` at `0x180005d9f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800063c2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800063c2`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180006630`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180006630`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000671d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000671d`
- `iisutil!?GetString@LANG_STRING@@QEAAJPEBDKIPEAPEBGPEAK@Z` at `0x1800066ad`
- `iisutil!?GetString@LANG_STRING@@QEAAJPEBDKIPEAPEBGPEAK@Z` at `0x1800066ad`
- `iisutil!SAFE_snwprintf` at `0x1800066f7`
- `iisutil!SAFE_snwprintf` at `0x1800066f7`

## string_xrefs

- `0x1800060c4`: `NOTIFY_MODULE_COMPLETION`
- `0x180006303`: `CompletionBytes`
- `0x180006208`: `RESOLVE_REQUEST_CACHE`
- `0x1800062b8`: `READ_ENTITY`
- `0x180006281`: `UPDATE_REQUEST_CACHE`
- `0x1800062af`: `MAP_PATH`

## pseudocode

```c
__int64 __fastcall NOTIFICATION_CONTEXT::CallModulesInternal(
        __int64 a1,
        int a2,
        unsigned int a3,
        unsigned int a4,
        int a5,
        __int64 a6,
        __int64 a7)
{
  _QWORD *v7; // rbx
  __int64 v8; // r11
  unsigned int v9; // esi
  unsigned int v10; // r13d
  int v11; // r10d
  _BYTE *v13; // r14
  unsigned int v14; // eax
  unsigned int *v15; // r12
  const wchar_t *v16; // rcx
  __int64 v17; // rax
  const wchar_t *v18; // rax
  wchar_t *v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rax
  bool v22; // zf
  wchar_t *v23; // rax
  __int64 v24; // rcx
  __int64 v25; // r14
  unsigned int v26; // eax
  __int64 v27; // rdx
  __int64 (__fastcall ***v28)(_QWORD); // rsi
  __int64 v29; // rax
  __int64 v30; // rbx
  const wchar_t *v31; // rdi
  const wchar_t *v32; // rax
  unsigned int v33; // eax
  __int64 v34; // rdx
  __int64 v35; // rdx
  __int64 v36; // rsi
  __int64 (__fastcall ***v37)(_QWORD, __int64, __int64); // rcx
  __int64 v38; // r8
  int v39; // edi
  __int64 v40; // rax
  _WORD *v41; // rax
  __int64 v42; // rcx
  int v43; // eax
  __int64 v44; // r8
  __int64 v45; // rdx
  __int64 v46; // r9
  __int64 v47; // rsi
  unsigned int *v48; // rdi
  __int64 v49; // r12
  struct IHttpTraceContext *v50; // r14
  int (__fastcall **v51)(__int64, GUID **, __int64); // rax
  unsigned int v52; // ebx
  int v53; // edi
  const unsigned __int16 *v54; // rax
  const struct _GUID *v55; // rdx
  const unsigned __int16 *v56; // rcx
  int v57; // eax
  __int64 v58; // rax
  const wchar_t *v59; // rax
  __int64 v60; // rax
  void (__fastcall *v61)(struct IHttpTraceContext *, _QWORD *); // rax
  void ***v62; // r9
  int (__fastcall **v63)(__int64, GUID **); // rcx
  struct IHttpTraceContext *v64; // r14
  __int64 v65; // rax
  __int64 v66; // rax
  char v67; // bl
  unsigned int v68; // edi
  const unsigned __int16 *v69; // rax
  const struct _GUID *v70; // rdx
  __int64 v71; // r12
  const unsigned __int16 *v72; // rax
  const struct _GUID *v73; // rdx
  __int64 v74; // rax
  __int64 v75; // r12
  __int64 v76; // rbx
  __int64 v77; // rax
  __int64 v78; // rax
  char v80[8]; // [rsp+20h] [rbp-E0h]
  _BYTE *v81; // [rsp+40h] [rbp-C0h]
  int v82; // [rsp+48h] [rbp-B8h]
  unsigned int v83; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int *v84; // [rsp+58h] [rbp-A8h]
  unsigned int v85; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v86; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v87; // [rsp+70h] [rbp-90h] BYREF
  GUID *v88; // [rsp+78h] [rbp-88h] BYREF
  __int128 v89; // [rsp+80h] [rbp-80h]
  int v90; // [rsp+90h] [rbp-70h] BYREF
  int v91; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v92; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v93; // [rsp+A8h] [rbp-58h]
  void **v94; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v95; // [rsp+B8h] [rbp-48h]
  unsigned int v96; // [rsp+BCh] [rbp-44h]
  int v97; // [rsp+C0h] [rbp-40h]
  _QWORD v98[4]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 *v99; // [rsp+F0h] [rbp-10h]
  int v100; // [rsp+F8h] [rbp-8h]
  int v101; // [rsp+FCh] [rbp-4h]
  unsigned int v102[4]; // [rsp+100h] [rbp+0h]
  int v103; // [rsp+110h] [rbp+10h]
  int v104; // [rsp+114h] [rbp+14h]
  int v105; // [rsp+118h] [rbp+18h]
  _QWORD v106[2]; // [rsp+11Ch] [rbp+1Ch] BYREF
  const wchar_t *v107; // [rsp+130h] [rbp+30h] BYREF
  int v108; // [rsp+138h] [rbp+38h]
  __int64 v109; // [rsp+140h] [rbp+40h]
  int v110; // [rsp+148h] [rbp+48h]
  __int64 v111; // [rsp+150h] [rbp+50h]
  const wchar_t *v112; // [rsp+158h] [rbp+58h]
  int v113; // [rsp+160h] [rbp+60h]
  const unsigned __int16 *v114; // [rsp+168h] [rbp+68h]
  int v115; // [rsp+170h] [rbp+70h]
  __int64 v116; // [rsp+178h] [rbp+78h]
  const wchar_t *v117; // [rsp+180h] [rbp+80h]
  int v118; // [rsp+188h] [rbp+88h]
  unsigned int *v119; // [rsp+190h] [rbp+90h]
  int v120; // [rsp+198h] [rbp+98h]
  const wchar_t *v121; // [rsp+1A0h] [rbp+A0h]
  const wchar_t *v122; // [rsp+1A8h] [rbp+A8h]
  int v123; // [rsp+1B0h] [rbp+B0h]
  int *v124; // [rsp+1B8h] [rbp+B8h]
  int v125; // [rsp+1C0h] [rbp+C0h]
  __int64 v126; // [rsp+1C8h] [rbp+C8h]
  const wchar_t *v127; // [rsp+1D0h] [rbp+D0h]
  int v128; // [rsp+1D8h] [rbp+D8h]
  unsigned int *v129; // [rsp+1E0h] [rbp+E0h]
  int v130; // [rsp+1E8h] [rbp+E8h]
  __int64 v131; // [rsp+1F0h] [rbp+F0h]
  const wchar_t *v132; // [rsp+1F8h] [rbp+F8h]
  int v133; // [rsp+200h] [rbp+100h]
  unsigned int *v134; // [rsp+208h] [rbp+108h]
  int v135; // [rsp+210h] [rbp+110h]
  __int64 v136; // [rsp+218h] [rbp+118h]

  v7 = (_QWORD *)a6;
  v8 = a7;
  v9 = 0;
  v94 = &NOTIFICATION_COMPLETION::`vftable';
  v10 = a4;
  v11 = a2;
  v83 = a3;
  v82 = a2;
  v86 = a6;
  v93 = a7;
  v95 = a4;
  v96 = a3;
  v97 = a5;
  if ( *(_DWORD *)(a6 + 88) )
    v13 = *(_BYTE **)(a6 + 96);
  else
    v13 = (_BYTE *)a6;
  v81 = v13;
  if ( *(_QWORD *)(a1 + 80) && *(_QWORD *)(a1 + 88) )
  {
    v14 = *(_DWORD *)(a1 + 124);
    if ( v14 == -1 )
    {
      v14 = *(_DWORD *)(*(_QWORD *)(a1 + 112)
                      + 4LL
                      * NOTIFICATION_CONTEXT::NotificationNumber(*(_DWORD *)(a1 + 8), *(unsigned __int8 *)(a1 + 12)));
      *(_DWORD *)(a1 + 124) = v14;
    }
    if ( *(_DWORD *)(*(_QWORD *)(a1 + 104) + 4LL * v14) != -1 )
    {
      v15 = (unsigned int *)(a1 + 8);
      while ( 1 )
      {
        v9 = *(_DWORD *)(a1 + 40);
        v84 = v15;
        if ( v9 != 1 )
        {
          *(_DWORD *)(a1 + 40) = 1;
          goto LABEL_122;
        }
        if ( !v11 && *v15 == 128 && !*(_BYTE *)(a1 + 12) )
        {
          v16 = *(const wchar_t **)(a1 + 128);
          if ( v16 )
          {
            v19 = wcschr(v16, 0x2Cu);
            if ( !v19 || v13[9036] )
            {
              v20 = *(_QWORD *)(a1 + 128);
              v21 = -1;
              do
                v22 = *(_WORD *)(v20 + 2 * v21++ + 2) == 0;
              while ( !v22 );
              v18 = (const wchar_t *)(v20 + 2 * v21);
            }
            else
            {
              v18 = v19 + 1;
            }
          }
          else
          {
            v17 = (*(__int64 (__fastcall **)(_QWORD *))(*v7 + 192LL))(v7);
            v18 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v17 + 16LL))(v17, 0);
          }
          *(_QWORD *)(a1 + 128) = v18;
          v23 = wcschr(v18, 0x2Cu);
          v24 = *(_QWORD *)(a1 + 128);
          if ( v23 )
          {
            LODWORD(v25) = ((__int64)v23 - v24) >> 1;
          }
          else
          {
            v25 = -1;
            do
              ++v25;
            while ( *(_WORD *)(v24 + 2 * v25) );
          }
          if ( (_DWORD)v25 )
            NOTIFICATION_CONTEXT::GetFirstModule((NOTIFICATION_CONTEXT *)a1);
          while ( 1 )
          {
            v26 = *(_DWORD *)(a1 + 124);
            if ( v26 == -1 )
              break;
            v27 = *(unsigned int *)(*(_QWORD *)(a1 + 104) + 4LL * v26);
            if ( (_DWORD)v27 == -1 )
              break;
            if ( (_DWORD)v25 )
            {
              v28 = *(__int64 (__fastcall ****)(_QWORD))(*(_QWORD *)(*(_QWORD *)(a1 + 80) + 32LL) + 8 * v27);
              v29 = (**v28)(v28);
              v30 = -1;
              do
                ++v30;
              while ( *(_WORD *)(v29 + 2 * v30) );
              if ( (_DWORD)v25 == (_DWORD)v30 )
              {
                v31 = *(const wchar_t **)(a1 + 128);
                v32 = (const wchar_t *)(**v28)(v28);
                if ( !wcsncmp_0(v31, v32, (unsigned int)v30) )
                  goto LABEL_40;
              }
            }
            if ( *v15 )
              ++*(_DWORD *)(a1 + 124);
          }
          if ( !(_DWORD)v25 )
            return 0;
LABEL_40:
          v33 = *(_DWORD *)(a1 + 124);
          if ( v33 == -1 || (v34 = *(unsigned int *)(*(_QWORD *)(a1 + 104) + 4LL * v33), (_DWORD)v34 == -1) )
          {
            v87 = 0;
            v85 = 0;
            STRU::STRU((STRU *)v98);
            v75 = v86;
            v9 = 2;
            W3_RESPONSE::SetStatus(
              *(W3_RESPONSE **)(v86 + 64),
              0x1F4u,
              "Internal Server Error",
              0x15u,
              -2147024883,
              0,
              0);
            if ( (int)LANG_STRING::GetString(
                        *((LANG_STRING **)g_pW3Server + 194),
                        *(const char **)(*(_QWORD *)(*(_QWORD *)(v75 + 48) + 40LL) + 528LL),
                        *(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)(v75 + 48) + 40LL) + 520LL),
                        0x31FFu,
                        &v87,
                        &v85) >= 0 )
            {
              v76 = *(_QWORD *)(a1 + 128);
              v77 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v75 + 192LL))(v75);
              v78 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v77 + 80LL))(v77);
              if ( (int)SAFE_snwprintf((struct STRU *)v98, v87, v78, (unsigned int)v25, v76) >= 0 )
                W3_RESPONSE::SetErrorDescription(*(W3_RESPONSE **)(v75 + 64), v99, v102[0], 1);
            }
            STRU::~STRU((STRU *)v98);
            return v9;
          }
          v35 = 8 * v34;
          v13 = v81;
          if ( !*(_QWORD *)(v35 + *(_QWORD *)(a1 + 88)) )
          {
            v36 = *(_QWORD *)(v35 + *(_QWORD *)(*(_QWORD *)(a1 + 80) + 32LL));
            v37 = *(__int64 (__fastcall ****)(_QWORD, __int64, __int64))(v36 + 24);
            if ( v37 )
            {
              v38 = v81 ? (__int64)(v81 + 24) : 0LL;
              v39 = (**v37)(v37, v35 + *(_QWORD *)(a1 + 88), v38);
              if ( v39 < 0 )
              {
                v71 = v86;
                v88 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
                v89 = 0;
                if ( (**(int (__fastcall ***)(__int64, GUID **))(v86 + 8))(v86 + 8, &v88) >= 0
                  && DWORD2(v89)
                  && DWORD1(v89) >= 2 )
                {
                  v72 = (const unsigned __int16 *)(**(__int64 (__fastcall ***)(__int64))v36)(v36);
                  IISGeneralEvents::GENERAL_MODULE_FACTORY_FAILED::RaiseEvent(
                    (struct IHttpTraceContext *)(v71 + 8),
                    v73,
                    v72,
                    v39);
                }
                v9 = 2;
                W3_RESPONSE::SetStatus(*(W3_RESPONSE **)(v71 + 64), 0x1F4u, "Internal Server Error", 0, v39, 0, 0);
                return v9;
              }
            }
          }
          v7 = (_QWORD *)v86;
          if ( v81[9038] )
          {
            v40 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v86 + 192LL))(v86);
            v41 = (_WORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v40 + 32LL))(v40, 0);
            v87 = 0;
            v90 = 0;
            if ( *v41 )
            {
              if ( (*(int (__fastcall **)(_BYTE *, const char *, const unsigned __int16 **, int *))(*(_QWORD *)v81
                                                                                                  + 120LL))(
                     v81,
                     "APP_WARMING_UP",
                     &v87,
                     &v90) >= 0
                && *(_BYTE *)v87 != 48 )
              {
                v9 = 2;
                v74 = (*(__int64 (__fastcall **)(_QWORD *))(*v7 + 32LL))(v7);
                *(_DWORD *)v80 = 0;
                (*(void (__fastcall **)(__int64, __int64, const char *, __int64, char *, _QWORD, _DWORD))(*(_QWORD *)v74 + 24LL))(
                  v74,
                  500,
                  "Internal Server Error",
                  21,
                  *(char **)v80,
                  0,
                  0);
                return v9;
              }
            }
          }
          v11 = v82;
          v8 = v93;
          v81[9037] = 1;
        }
        v42 = *(unsigned int *)(a1 + 124);
        if ( (_DWORD)v42 == -1 )
        {
          v43 = -1;
          v44 = 0xFFFFFFFFLL;
        }
        else
        {
          v44 = *(unsigned int *)(a1 + 124);
          v43 = *(_DWORD *)(*(_QWORD *)(a1 + 104) + 4 * v42);
        }
        if ( *(_DWORD *)(a1 + 16) == v43 )
          return 0;
        v45 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 32LL);
        if ( (_DWORD)v42 == -1 )
        {
          LODWORD(v46) = -1;
          v47 = *(_QWORD *)(v45 + 0x7FFFFFFF8LL);
        }
        else
        {
          v46 = *(unsigned int *)(*(_QWORD *)(a1 + 104) + 4 * v44);
          v47 = *(_QWORD *)(v45 + 8 * v46);
        }
        v48 = v84;
        v49 = *(_QWORD *)(*(_QWORD *)(a1 + 88) + 8LL * (unsigned int)v46);
        if ( *v84 == 0x20000000
          && !v11
          && *(_DWORD *)(v47 + 20)
          && !(*(unsigned int (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v8 + 8LL))(v8, v45, v44) )
        {
          v9 = 0;
          goto LABEL_127;
        }
        if ( v13[9098] )
          break;
LABEL_108:
        *(_DWORD *)(a1 + 48) = GetTickCount();
        v62 = &v94;
        if ( !v82 )
          v62 = 0;
        v9 = NOTIFICATION_CONTEXT::RequestDoWork(a1, v49, v7, v62, v93);
        if ( v9 != 1
          && v13[9098]
          && (v63 = (int (__fastcall **)(__int64, GUID **))v7[1],
              v64 = (struct IHttpTraceContext *)(v7 + 1),
              v88 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid,
              v89 = 0,
              (*v63)((__int64)(v7 + 1), &v88) >= 0)
          && DWORD2(v89)
          && DWORD1(v89) >= 5
          && ((_DWORD)v89 == 256 || (v89 & 0x100) != 0) )
        {
          v65 = *(unsigned int *)(a1 + 124);
          if ( (_DWORD)v65 == -1 )
            v66 = 0xFFFFFFFFLL;
          else
            v66 = *(unsigned int *)(*(_QWORD *)(a1 + 104) + 4 * v65);
          v15 = v84;
          v67 = *(_BYTE *)(a1 + 12);
          v68 = *v84;
          v69 = (const unsigned __int16 *)(***(__int64 (__fastcall ****)(_QWORD))(*(_QWORD *)(*(_QWORD *)(a1 + 80) + 32LL)
                                                                                + 8 * v66))(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 80) + 32LL) + 8 * v66));
          IISRequestNotificationEvents::NOTIFY_MODULE_END::RaiseEvent(v64, v70, v69, v68, v67, v9);
          v7 = (_QWORD *)v86;
        }
        else
        {
          v15 = v84;
        }
LABEL_122:
        if ( v9 == 2 )
        {
          v13 = v81;
          if ( ((*v15 - 1024) & 0xFFFFFBFF) == 0 )
            v9 = 0;
        }
        else
        {
          if ( v9 == 1 )
            return v9;
          v13 = v81;
        }
LABEL_127:
        if ( *(_BYTE *)(a1 + 13) || v9 == 2 )
          return v9;
        v15 = v84;
        if ( *v84 != 128 || *(_BYTE *)(a1 + 12) )
          ++*(_DWORD *)(a1 + 124);
        if ( *(_DWORD *)(*(_QWORD *)(a1 + 104) + 4LL * *(unsigned int *)(a1 + 124)) == -1 )
          return v9;
        v8 = v93;
        v11 = 0;
        v82 = 0;
        v10 = 0;
        v83 = 0;
      }
      v88 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
      v50 = (struct IHttpTraceContext *)(v7 + 1);
      v51 = (int (__fastcall **)(__int64, GUID **, __int64))v7[1];
      v89 = 0;
      if ( (*v51)((__int64)(v7 + 1), &v88, v44) < 0
        || !DWORD2(v89)
        || DWORD1(v89) < 5
        || (_DWORD)v89 != 256 && (v89 & 0x100) == 0 )
      {
        goto LABEL_107;
      }
      v52 = *v48;
      v53 = *(unsigned __int8 *)(a1 + 12);
      v54 = (const unsigned __int16 *)(**(__int64 (__fastcall ***)(__int64))v47)(v47);
      if ( !v82 )
      {
        IISRequestNotificationEvents::NOTIFY_MODULE_START::RaiseEvent(v50, v55, v54, v52, v53);
        v7 = (_QWORD *)v86;
LABEL_107:
        v13 = v81;
        goto LABEL_108;
      }
      v56 = v54;
      v91 = v53;
      v92 = v83;
      v85 = v10;
      memset(v106, 0, 12);
      v98[2] = &`IISRequestNotificationEvents::GetAreaGuid'::`2'::AreaGuid;
      v99 = L"NOTIFY_MODULE_COMPLETION";
      v107 = L"ContextId";
      v112 = L"ModuleName";
      v83 = v52;
      v98[1] = 256;
      v98[3] = 3;
      v98[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
      v100 = 1;
      v101 = 5;
      v105 = 6;
      *(_OWORD *)v102 = 0;
      v103 = 0;
      v104 = 1;
      v108 = 72;
      v109 = 0;
      v110 = 16;
      v111 = 0;
      v113 = 31;
      v114 = v54;
      if ( v54 )
      {
        v58 = -1;
        do
          v22 = v56[++v58] == 0;
        while ( !v22 );
        v57 = 2 * v58 + 2;
      }
      else
      {
        v57 = 0;
      }
      v115 = v57;
      v117 = L"Notification";
      v119 = &v83;
      v116 = 0;
      v118 = 19;
      v120 = 4;
      if ( v52 <= 0x100 )
      {
        if ( v52 == 256 )
        {
          v59 = L"RELEASE_REQUEST_STATE";
        }
        else
        {
          switch ( v52 )
          {
            case 1u:
              v59 = L"BEGIN_REQUEST";
              break;
            case 2u:
              v59 = L"AUTHENTICATE_REQUEST";
              break;
            case 4u:
              v59 = L"AUTHORIZE_REQUEST";
              break;
            case 8u:
              v59 = L"RESOLVE_REQUEST_CACHE";
              break;
            case 0x10u:
              v59 = L"MAP_REQUEST_HANDLER";
              break;
            case 0x20u:
              v59 = L"REQUEST_ACQUIRE_STATE";
              break;
            case 0x40u:
              v59 = L"PRE_EXECUTE_REQUEST_HANDLER";
              break;
            case 0x80u:
              v59 = L"EXECUTE_REQUEST_HANDLER";
              break;
            default:
              goto LABEL_101;
          }
        }
        goto LABEL_105;
      }
      if ( v52 > 0x10000000 )
      {
        switch ( v52 )
        {
          case 0x20000000u:
            v59 = L"SEND_RESPONSE";
            goto LABEL_105;
          case 0x40000000u:
            v59 = L"READ_ENTITY";
            goto LABEL_105;
          case 0x80000000:
            v59 = L"MAP_PATH";
            goto LABEL_105;
        }
      }
      else
      {
        switch ( v52 )
        {
          case 0x10000000u:
            v59 = L"CUSTOM_NOTIFICATION";
            goto LABEL_105;
          case 0x200u:
            v59 = L"UPDATE_REQUEST_CACHE";
            goto LABEL_105;
          case 0x400u:
            v59 = L"LOG_REQUEST";
            goto LABEL_105;
          case 0x800u:
            v59 = L"END_REQUEST";
LABEL_105:
            v121 = v59;
            v123 = 11;
            v122 = L"fIsPostNotificationEvent";
            v125 = 4;
            v124 = &v91;
            v127 = L"CompletionBytes";
            v129 = &v92;
            v132 = L"ErrorCode";
            v134 = &v85;
            *(_QWORD *)((char *)v106 + 4) = &v107;
            v60 = *(_QWORD *)v50;
            v126 = 0;
            v128 = 19;
            v130 = 4;
            v61 = *(void (__fastcall **)(struct IHttpTraceContext *, _QWORD *))(v60 + 16);
            v131 = 0;
            v133 = 19;
            v135 = 4;
            v136 = 0;
            v61(v50, v98);
            v7 = (_QWORD *)v86;
            v13 = v81;
            goto LABEL_108;
        }
      }
LABEL_101:
      v59 = 0;
      goto LABEL_105;
    }
  }
  return v9;
}

```

## disassembly

```asm
0x180005bf0  mov     [rsp-8+arg_18], rbx
0x180005bf5  push    rbp
0x180005bf6  push    rsi
0x180005bf7  push    r13
0x180005bf9  push    r14
0x180005bfb  push    r15
0x180005bfd  lea     rbp, [rsp-130h]
0x180005c05  sub     rsp, 230h
0x180005c0c  mov     rax, cs:__security_cookie
0x180005c13  xor     rax, rsp
0x180005c16  mov     [rbp+150h+var_30], rax
0x180005c1d  mov     rbx, [rbp+150h+arg_28]
0x180005c24  lea     rax, ??_7NOTIFICATION_COMPLETION@@6B@; const NOTIFICATION_COMPLETION::`vftable'
0x180005c2b  mov     r11, [rbp+150h+arg_30]
0x180005c32  xor     esi, esi
0x180005c34  mov     [rbp+150h+var_1A0], rax
0x180005c38  mov     r13d, r9d
0x180005c3b  mov     eax, [rbp+150h+arg_20]
0x180005c41  mov     r10d, edx
0x180005c44  mov     r15, rcx
0x180005c47  mov     [rsp+250h+var_200], r8d
0x180005c4c  mov     [rsp+250h+var_208], edx
0x180005c50  mov     [rsp+250h+var_1E8], rbx
0x180005c55  mov     [rbp+150h+var_1A8], r11
0x180005c59  mov     [rbp+150h+var_198], r9d
0x180005c5d  mov     [rbp+150h+var_194], r8d
0x180005c61  mov     [rbp+150h+var_190], eax
0x180005c64  cmp     [rbx+58h], esi
0x180005c67  jz      short loc_180005C6F
0x180005c69  mov     r14, [rbx+60h]
0x180005c6d  jmp     short loc_180005C72
0x180005c6f  mov     r14, rbx
0x180005c72  mov     [rsp+250h+var_210], r14
0x180005c77  cmp     [rcx+50h], rsi
0x180005c7b  jz      loc_180006737
0x180005c81  cmp     [rcx+58h], rsi
0x180005c85  jz      loc_180006737
0x180005c8b  mov     eax, [rcx+7Ch]
0x180005c8e  mov     [rsp+250h+arg_8], rdi
0x180005c96  mov     edi, 0FFFFFFFFh
0x180005c9b  cmp     eax, edi
0x180005c9d  jnz     short loc_180005CB8
0x180005c9f  movzx   edx, byte ptr [rcx+0Ch]; int
0x180005ca3  mov     ecx, [rcx+8]; unsigned int
0x180005ca6  call    ?NotificationNumber@NOTIFICATION_CONTEXT@@CAKKH@Z; NOTIFICATION_CONTEXT::NotificationNumber(ulong,int)
0x180005cab  mov     edx, eax
0x180005cad  mov     rax, [r15+70h]
0x180005cb1  mov     eax, [rax+rdx*4]
0x180005cb4  mov     [r15+7Ch], eax
0x180005cb8  mov     ecx, eax
0x180005cba  mov     rax, [r15+68h]
0x180005cbe  cmp     [rax+rcx*4], edi
0x180005cc1  jz      loc_18000672F
0x180005cc7  mov     [rsp+250h+arg_10], r12
0x180005ccf  lea     r12, [r15+8]
0x180005cd3  nop     dword ptr [rax+00h]
0x180005cd7  nop     word ptr [rax+rax+00000000h]
0x180005ce0  mov     esi, [r15+28h]
0x180005ce4  mov     [rsp+250h+var_1F8], r12
0x180005ce9  cmp     esi, 1
0x180005cec  jz      short loc_180005CFB
0x180005cee  mov     dword ptr [r15+28h], 1
0x180005cf6  jmp     loc_1800064B2
0x180005cfb  test    r10d, r10d
0x180005cfe  jnz     loc_180005F7B
0x180005d04  cmp     dword ptr [r12], 80h
0x180005d0c  jnz     loc_180005F7B
0x180005d12  cmp     [r15+0Ch], r10b
0x180005d16  jnz     loc_180005F7B
0x180005d1c  mov     rcx, [r15+80h]; Str
0x180005d23  test    rcx, rcx
0x180005d26  jnz     short loc_180005D4D
0x180005d28  mov     rax, [rbx]
0x180005d2b  mov     rcx, rbx
0x180005d2e  mov     rax, [rax+0C0h]
0x180005d35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d3a  mov     rcx, rax
0x180005d3d  xor     edx, edx
0x180005d3f  mov     rax, [rax]
0x180005d42  mov     rax, [rax+10h]
0x180005d46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d4b  jmp     short loc_180005D90
0x180005d4d  mov     edx, 2Ch ; ','; Ch
0x180005d52  call    cs:__imp_wcschr
0x180005d58  test    rax, rax
0x180005d5b  jz      short loc_180005D6D
0x180005d5d  cmp     byte ptr [r14+234Ch], 0
0x180005d65  jnz     short loc_180005D6D
0x180005d67  add     rax, 2
0x180005d6b  jmp     short loc_180005D90
0x180005d6d  mov     rcx, [r15+80h]
0x180005d74  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180005d7b  nop     dword ptr [rax+rax+00h]
0x180005d80  cmp     word ptr [rcx+rax*2+2], 0
0x180005d86  lea     rax, [rax+1]
0x180005d8a  jnz     short loc_180005D80
0x180005d8c  lea     rax, [rcx+rax*2]
0x180005d90  mov     edx, 2Ch ; ','; Ch
0x180005d95  mov     [r15+80h], rax
0x180005d9c  mov     rcx, rax; Str
0x180005d9f  call    cs:__imp_wcschr
0x180005da5  mov     rcx, [r15+80h]
0x180005dac  test    rax, rax
0x180005daf  jnz     short loc_180005DCD
0x180005db1  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180005db8  nop     dword ptr [rax+rax+00000000h]
0x180005dc0  inc     r14
0x180005dc3  cmp     word ptr [rcx+r14*2], 0
0x180005dc9  jnz     short loc_180005DC0
0x180005dcb  jmp     short loc_180005DD6
0x180005dcd  sub     rax, rcx
0x180005dd0  sar     rax, 1
0x180005dd3  mov     r14d, eax
0x180005dd6  test    r14d, r14d
0x180005dd9  jz      short loc_180005DE3
0x180005ddb  mov     rcx, r15; this
0x180005dde  call    ?GetFirstModule@NOTIFICATION_CONTEXT@@IEAAXXZ; NOTIFICATION_CONTEXT::GetFirstModule(void)
0x180005de3  mov     eax, [r15+7Ch]
0x180005de7  cmp     eax, edi
0x180005de9  jz      loc_180005E71
0x180005def  mov     ecx, eax
0x180005df1  mov     rax, [r15+68h]
0x180005df5  mov     edx, [rax+rcx*4]
0x180005df8  cmp     edx, edi
0x180005dfa  jz      short loc_180005E71
0x180005dfc  test    r14d, r14d
0x180005dff  jz      short loc_180005E5D
0x180005e01  mov     rax, [r15+50h]
0x180005e05  mov     rcx, [rax+20h]
0x180005e09  mov     rsi, [rcx+rdx*8]
0x180005e0d  mov     rcx, rsi
0x180005e10  mov     rax, [rsi]
0x180005e13  mov     rax, [rax]
0x180005e16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e1b  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180005e22  inc     rbx
0x180005e25  cmp     word ptr [rax+rbx*2], 0
0x180005e2a  jnz     short loc_180005E22
0x180005e2c  cmp     r14d, ebx
0x180005e2f  jnz     short loc_180005E5D
0x180005e31  mov     rax, [rsi]
0x180005e34  mov     rcx, rsi
0x180005e37  mov     rdi, [r15+80h]
0x180005e3e  mov     rax, [rax]
0x180005e41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e46  mov     rdx, rax; String2
0x180005e49  mov     r8d, ebx; MaxCount
0x180005e4c  mov     rcx, rdi; String1
0x180005e4f  call    wcsncmp_0
0x180005e54  mov     edi, 0FFFFFFFFh
0x180005e59  test    eax, eax
0x180005e5b  jz      short loc_180005E7A
0x180005e5d  cmp     dword ptr [r12], 0
0x180005e62  jz      loc_180005DE3
0x180005e68  inc     dword ptr [r15+7Ch]
0x180005e6c  jmp     loc_180005DE3
0x180005e71  test    r14d, r14d
0x180005e74  jz      loc_180006725
0x180005e7a  mov     eax, [r15+7Ch]
0x180005e7e  cmp     eax, edi
0x180005e80  jz      loc_180006621
0x180005e86  mov     ecx, eax
0x180005e88  mov     rax, [r15+68h]
0x180005e8c  mov     edx, [rax+rcx*4]
0x180005e8f  cmp     edx, edi
0x180005e91  jz      loc_180006621
0x180005e97  mov     r9, [r15+58h]
0x180005e9b  lea     rdx, ds:0[rdx*8]
0x180005ea3  mov     r14, [rsp+250h+var_210]
0x180005ea8  add     r9, rdx
0x180005eab  cmp     qword ptr [r9], 0
0x180005eaf  jnz     short loc_180005EF1
0x180005eb1  mov     rax, [r15+50h]
0x180005eb5  mov     rcx, [rax+20h]
0x180005eb9  mov     rsi, [rdx+rcx]
0x180005ebd  mov     rcx, [rsi+18h]
0x180005ec1  test    rcx, rcx
0x180005ec4  jz      short loc_180005EF1
0x180005ec6  mov     rax, [rcx]
0x180005ec9  test    r14, r14
0x180005ecc  jz      short loc_180005ED4
0x180005ece  lea     r8, [r14+18h]
0x180005ed2  jmp     short loc_180005ED7
0x180005ed4  xor     r8d, r8d
0x180005ed7  mov     rax, [rax]
0x180005eda  mov     rdx, r9
0x180005edd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ee2  mov     edi, eax
0x180005ee4  test    eax, eax
0x180005ee6  js      loc_18000653B
0x180005eec  mov     edi, 0FFFFFFFFh
0x180005ef1  cmp     byte ptr [r14+234Eh], 0
0x180005ef9  mov     rbx, [rsp+250h+var_1E8]
0x180005efe  jz      short loc_180005F6A
0x180005f00  mov     rax, [rbx]
0x180005f03  mov     rcx, rbx
0x180005f06  mov     rax, [rax+0C0h]
0x180005f0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f12  mov     rcx, rax
0x180005f15  xor     edx, edx
0x180005f17  mov     rax, [rax]
0x180005f1a  mov     rax, [rax+20h]
0x180005f1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f23  mov     [rsp+250h+var_1E0], 0
0x180005f2c  mov     [rbp+150h+var_1C0], 0
0x180005f33  cmp     word ptr [rax], 0
0x180005f37  jz      short loc_180005F6A
0x180005f39  mov     rax, [r14]
0x180005f3c  lea     r9, [rbp+150h+var_1C0]
0x180005f40  lea     r8, [rsp+250h+var_1E0]
0x180005f45  mov     rcx, r14
0x180005f48  lea     rdx, aAppWarmingUp; "APP_WARMING_UP"
0x180005f4f  mov     rax, [rax+78h]
0x180005f53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f58  test    eax, eax
0x180005f5a  js      short loc_180005F6A
0x180005f5c  mov     rax, [rsp+250h+var_1E0]
0x180005f61  cmp     byte ptr [rax], 30h ; '0'
0x180005f64  jnz     loc_1800065CB
0x180005f6a  mov     r10d, [rsp+250h+var_208]
0x180005f6f  mov     r11, [rbp+150h+var_1A8]
0x180005f73  mov     byte ptr [r14+234Dh], 1
0x180005f7b  mov     ecx, [r15+7Ch]
0x180005f7f  cmp     ecx, edi
0x180005f81  jnz     short loc_180005F8A
0x180005f83  mov     eax, edi
0x180005f85  mov     r8, rdi
0x180005f88  jmp     short loc_180005F94
0x180005f8a  mov     rax, [r15+68h]
0x180005f8e  mov     r8, rcx
0x180005f91  mov     eax, [rax+rcx*4]
0x180005f94  cmp     [r15+10h], eax
0x180005f98  jz      loc_180006725
0x180005f9e  mov     rax, [r15+50h]
0x180005fa2  mov     rdx, [rax+20h]
0x180005fa6  cmp     ecx, edi
0x180005fa8  jnz     short loc_180005FBD
0x180005faa  mov     rax, 7FFFFFFF8h
0x180005fb4  mov     r9d, edi
0x180005fb7  mov     rsi, [rdx+rax]
0x180005fbb  jmp     short loc_180005FCD
0x180005fbd  mov     rax, [r15+68h]
0x180005fc1  mov     ecx, [rax+r8*4]
0x180005fc5  mov     r9d, [rax+r8*4]
0x180005fc9  mov     rsi, [rdx+rcx*8]
0x180005fcd  mov     rdi, [rsp+250h+var_1F8]
0x180005fd2  mov     rcx, [r15+58h]
0x180005fd6  mov     eax, r9d
0x180005fd9  cmp     dword ptr [rdi], 20000000h
0x180005fdf  mov     r12, [rcx+rax*8]
0x180005fe3  jnz     short loc_18000600A
0x180005fe5  test    r10d, r10d
0x180005fe8  jnz     short loc_18000600A
0x180005fea  cmp     [rsi+14h], r10d
0x180005fee  jz      short loc_18000600A
0x180005ff0  mov     rax, [r11]
0x180005ff3  mov     rcx, r11
0x180005ff6  mov     rax, [rax+8]
0x180005ffa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fff  test    eax, eax
0x180006001  jnz     short loc_18000600A
0x180006003  xor     esi, esi
0x180006005  jmp     loc_1800064DE
0x18000600a  cmp     byte ptr [r14+238Ah], 0
0x180006012  jz      loc_1800063BB
0x180006018  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18000601f  xorps   xmm0, xmm0
0x180006022  mov     [rsp+250h+var_1D8], rax
0x180006027  lea     r14, [rbx+8]
0x18000602b  mov     rax, [r14]
0x18000602e  lea     rdx, [rsp+250h+var_1D8]
0x180006033  mov     rcx, r14
0x180006036  movdqu  [rbp+150h+var_1D0], xmm0
0x18000603b  mov     rax, [rax]
0x18000603e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006043  test    eax, eax
0x180006045  js      loc_1800063B6
0x18000604b  cmp     dword ptr [rbp+150h+var_1D0+8], 0
0x18000604f  jz      loc_1800063B6
0x180006055  cmp     dword ptr [rbp+150h+var_1D0+4], 5
0x180006059  jb      loc_1800063B6
0x18000605f  mov     rax, qword ptr [rbp+150h+var_1D0]
0x180006063  cmp     eax, 100h
0x180006068  jz      short loc_180006074
0x18000606a  bt      eax, 8
0x18000606e  jnb     loc_1800063B6
0x180006074  mov     rax, [rsi]
0x180006077  mov     rcx, rsi
0x18000607a  mov     ebx, [rdi]
0x18000607c  movzx   edi, byte ptr [r15+0Ch]
0x180006081  mov     rax, [rax]
0x180006084  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006089  cmp     [rsp+250h+var_208], 0
0x18000608e  jz      loc_18000639F
0x180006094  mov     rcx, rax
0x180006097  mov     [rbp+150h+var_1B8], edi
0x18000609a  mov     eax, [rsp+250h+var_200]
0x18000609e  lea     rdi, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x1800060a5  mov     [rbp+150h+var_1B0], eax
0x1800060a8  xorps   xmm0, xmm0
  ... truncated ...
```
