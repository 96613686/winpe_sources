# NOTIFICATION_CONTEXT::CallModulesInternal(int,ulong,long,ulong,W3_CONTEXT_BASE *,IHttpEventProvider *)

- ea: `0x180006060`
- end: `0x180006c98`
- name: `?CallModulesInternal@NOTIFICATION_CONTEXT@@AEAA?AW4REQUEST_NOTIFICATION_STATUS@@HKJKPEAVW3_CONTEXT_BASE@@PEAVIHttpEventProvider@@@Z`
- size: `3128`
- prototype: `__int64 __fastcall(__int64, int, unsigned int, unsigned int, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180006010`

## callees

- `0x180006060`
- `0x180006ca0`
- `0x18000b810`
- `0x18000f7b0`
- `0x1800106a0`
- `0x180018c34`
- `0x18001924c`
- `0x180019648`
- `0x18001a404`
- `0x18003776a`
- `0x180037790`
- `0x180038010`

## import_xrefs

- `msvcrt!wcschr` at `0x1800061c2`
- `msvcrt!wcschr` at `0x180006210`
- `msvcrt!wcschr` at `0x1800061c2`
- `msvcrt!wcschr` at `0x180006210`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180006836`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180006836`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180006aaa`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180006aaa`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180006ba9`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180006ba9`
- `iisutil!?GetString@LANG_STRING@@QEAAJPEBDKIPEAPEBGPEAK@Z` at `0x180006b2d`
- `iisutil!?GetString@LANG_STRING@@QEAAJPEBDKIPEAPEBGPEAK@Z` at `0x180006b2d`
- `iisutil!SAFE_snwprintf` at `0x180006b7d`
- `iisutil!SAFE_snwprintf` at `0x180006b7d`

## string_xrefs

- `0x180006534`: `NOTIFY_MODULE_COMPLETION`
- `0x180006777`: `CompletionBytes`
- `0x18000667c`: `RESOLVE_REQUEST_CACHE`
- `0x18000672c`: `READ_ENTITY`
- `0x1800066f5`: `UPDATE_REQUEST_CACHE`
- `0x180006723`: `MAP_PATH`

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
0x180006060  mov     [rsp-8+arg_18], rbx
0x180006065  push    rbp
0x180006066  push    rsi
0x180006067  push    r13
0x180006069  push    r14
0x18000606b  push    r15
0x18000606d  lea     rbp, [rsp-130h]
0x180006075  sub     rsp, 230h
0x18000607c  mov     rax, cs:__security_cookie
0x180006083  xor     rax, rsp
0x180006086  mov     [rbp+150h+var_30], rax
0x18000608d  mov     rbx, [rbp+150h+arg_28]
0x180006094  lea     rax, ??_7NOTIFICATION_COMPLETION@@6B@; const NOTIFICATION_COMPLETION::`vftable'
0x18000609b  mov     r11, [rbp+150h+arg_30]
0x1800060a2  xor     esi, esi
0x1800060a4  mov     [rbp+150h+var_1A0], rax
0x1800060a8  mov     r13d, r9d
0x1800060ab  mov     eax, [rbp+150h+arg_20]
0x1800060b1  mov     r10d, edx
0x1800060b4  mov     r15, rcx
0x1800060b7  mov     [rsp+250h+var_200], r8d
0x1800060bc  mov     [rsp+250h+var_208], edx
0x1800060c0  mov     [rsp+250h+var_1E8], rbx
0x1800060c5  mov     [rbp+150h+var_1A8], r11
0x1800060c9  mov     [rbp+150h+var_198], r9d
0x1800060cd  mov     [rbp+150h+var_194], r8d
0x1800060d1  mov     [rbp+150h+var_190], eax
0x1800060d4  cmp     [rbx+58h], esi
0x1800060d7  jz      short loc_1800060DF
0x1800060d9  mov     r14, [rbx+60h]
0x1800060dd  jmp     short loc_1800060E2
0x1800060df  mov     r14, rbx
0x1800060e2  mov     [rsp+250h+var_210], r14
0x1800060e7  cmp     [rcx+50h], rsi
0x1800060eb  jz      loc_180006BC9
0x1800060f1  cmp     [rcx+58h], rsi
0x1800060f5  jz      loc_180006BC9
0x1800060fb  mov     eax, [rcx+7Ch]
0x1800060fe  mov     [rsp+250h+arg_8], rdi
0x180006106  mov     edi, 0FFFFFFFFh
0x18000610b  cmp     eax, edi
0x18000610d  jnz     short loc_180006128
0x18000610f  movzx   edx, byte ptr [rcx+0Ch]; int
0x180006113  mov     ecx, [rcx+8]; unsigned int
0x180006116  call    ?NotificationNumber@NOTIFICATION_CONTEXT@@CAKKH@Z; NOTIFICATION_CONTEXT::NotificationNumber(ulong,int)
0x18000611b  mov     edx, eax
0x18000611d  mov     rax, [r15+70h]
0x180006121  mov     eax, [rax+rdx*4]
0x180006124  mov     [r15+7Ch], eax
0x180006128  mov     ecx, eax
0x18000612a  mov     rax, [r15+68h]
0x18000612e  cmp     [rax+rcx*4], edi
0x180006131  jz      loc_180006BC1
0x180006137  mov     [rsp+250h+arg_10], r12
0x18000613f  lea     r12, [r15+8]
0x180006143  nop     dword ptr [rax+00h]
0x180006147  nop     word ptr [rax+rax+00000000h]
0x180006150  mov     esi, [r15+28h]
0x180006154  mov     [rsp+250h+var_1F8], r12
0x180006159  cmp     esi, 1
0x18000615c  jz      short loc_18000616B
0x18000615e  mov     dword ptr [r15+28h], 1
0x180006166  jmp     loc_18000692C
0x18000616b  test    r10d, r10d
0x18000616e  jnz     loc_1800063EB
0x180006174  cmp     dword ptr [r12], 80h
0x18000617c  jnz     loc_1800063EB
0x180006182  cmp     [r15+0Ch], r10b
0x180006186  jnz     loc_1800063EB
0x18000618c  mov     rcx, [r15+80h]; Str
0x180006193  test    rcx, rcx
0x180006196  jnz     short loc_1800061BD
0x180006198  mov     rax, [rbx]
0x18000619b  mov     rcx, rbx
0x18000619e  mov     rax, [rax+0C0h]
0x1800061a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061aa  mov     rcx, rax
0x1800061ad  xor     edx, edx
0x1800061af  mov     rax, [rax]
0x1800061b2  mov     rax, [rax+10h]
0x1800061b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061bb  jmp     short loc_180006201
0x1800061bd  mov     edx, 2Ch ; ','; Ch
0x1800061c2  call    cs:__imp_wcschr
0x1800061c9  nop     dword ptr [rax+rax+00h]
0x1800061ce  test    rax, rax
0x1800061d1  jz      short loc_1800061E3
0x1800061d3  cmp     byte ptr [r14+234Ch], 0
0x1800061db  jnz     short loc_1800061E3
0x1800061dd  add     rax, 2
0x1800061e1  jmp     short loc_180006201
0x1800061e3  mov     rcx, [r15+80h]
0x1800061ea  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800061f1  cmp     word ptr [rcx+rax*2+2], 0
0x1800061f7  lea     rax, [rax+1]
0x1800061fb  jnz     short loc_1800061F1
0x1800061fd  lea     rax, [rcx+rax*2]
0x180006201  mov     edx, 2Ch ; ','; Ch
0x180006206  mov     [r15+80h], rax
0x18000620d  mov     rcx, rax; Str
0x180006210  call    cs:__imp_wcschr
0x180006217  nop     dword ptr [rax+rax+00h]
0x18000621c  mov     rcx, [r15+80h]
0x180006223  test    rax, rax
0x180006226  jnz     short loc_18000623D
0x180006228  mov     r14, 0FFFFFFFFFFFFFFFFh
0x18000622f  nop
0x180006230  inc     r14
0x180006233  cmp     word ptr [rcx+r14*2], 0
0x180006239  jnz     short loc_180006230
0x18000623b  jmp     short loc_180006246
0x18000623d  sub     rax, rcx
0x180006240  sar     rax, 1
0x180006243  mov     r14d, eax
0x180006246  test    r14d, r14d
0x180006249  jz      short loc_180006253
0x18000624b  mov     rcx, r15; this
0x18000624e  call    ?GetFirstModule@NOTIFICATION_CONTEXT@@IEAAXXZ; NOTIFICATION_CONTEXT::GetFirstModule(void)
0x180006253  mov     eax, [r15+7Ch]
0x180006257  cmp     eax, edi
0x180006259  jz      loc_1800062E1
0x18000625f  mov     ecx, eax
0x180006261  mov     rax, [r15+68h]
0x180006265  mov     edx, [rax+rcx*4]
0x180006268  cmp     edx, edi
0x18000626a  jz      short loc_1800062E1
0x18000626c  test    r14d, r14d
0x18000626f  jz      short loc_1800062CD
0x180006271  mov     rax, [r15+50h]
0x180006275  mov     rcx, [rax+20h]
0x180006279  mov     rsi, [rcx+rdx*8]
0x18000627d  mov     rcx, rsi
0x180006280  mov     rax, [rsi]
0x180006283  mov     rax, [rax]
0x180006286  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000628b  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180006292  inc     rbx
0x180006295  cmp     word ptr [rax+rbx*2], 0
0x18000629a  jnz     short loc_180006292
0x18000629c  cmp     r14d, ebx
0x18000629f  jnz     short loc_1800062CD
0x1800062a1  mov     rax, [rsi]
0x1800062a4  mov     rcx, rsi
0x1800062a7  mov     rdi, [r15+80h]
0x1800062ae  mov     rax, [rax]
0x1800062b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062b6  mov     rdx, rax; String2
0x1800062b9  mov     r8d, ebx; MaxCount
0x1800062bc  mov     rcx, rdi; String1
0x1800062bf  call    wcsncmp_0
0x1800062c4  mov     edi, 0FFFFFFFFh
0x1800062c9  test    eax, eax
0x1800062cb  jz      short loc_1800062EA
0x1800062cd  cmp     dword ptr [r12], 0
0x1800062d2  jz      loc_180006253
0x1800062d8  inc     dword ptr [r15+7Ch]
0x1800062dc  jmp     loc_180006253
0x1800062e1  test    r14d, r14d
0x1800062e4  jz      loc_180006BB7
0x1800062ea  mov     eax, [r15+7Ch]
0x1800062ee  cmp     eax, edi
0x1800062f0  jz      loc_180006A9B
0x1800062f6  mov     ecx, eax
0x1800062f8  mov     rax, [r15+68h]
0x1800062fc  mov     edx, [rax+rcx*4]
0x1800062ff  cmp     edx, edi
0x180006301  jz      loc_180006A9B
0x180006307  mov     r9, [r15+58h]
0x18000630b  lea     rdx, ds:0[rdx*8]
0x180006313  mov     r14, [rsp+250h+var_210]
0x180006318  add     r9, rdx
0x18000631b  cmp     qword ptr [r9], 0
0x18000631f  jnz     short loc_180006361
0x180006321  mov     rax, [r15+50h]
0x180006325  mov     rcx, [rax+20h]
0x180006329  mov     rsi, [rdx+rcx]
0x18000632d  mov     rcx, [rsi+18h]
0x180006331  test    rcx, rcx
0x180006334  jz      short loc_180006361
0x180006336  mov     rax, [rcx]
0x180006339  test    r14, r14
0x18000633c  jz      short loc_180006344
0x18000633e  lea     r8, [r14+18h]
0x180006342  jmp     short loc_180006347
0x180006344  xor     r8d, r8d
0x180006347  mov     rax, [rax]
0x18000634a  mov     rdx, r9
0x18000634d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006352  mov     edi, eax
0x180006354  test    eax, eax
0x180006356  js      loc_1800069B5
0x18000635c  mov     edi, 0FFFFFFFFh
0x180006361  cmp     byte ptr [r14+234Eh], 0
0x180006369  mov     rbx, [rsp+250h+var_1E8]
0x18000636e  jz      short loc_1800063DA
0x180006370  mov     rax, [rbx]
0x180006373  mov     rcx, rbx
0x180006376  mov     rax, [rax+0C0h]
0x18000637d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006382  mov     rcx, rax
0x180006385  xor     edx, edx
0x180006387  mov     rax, [rax]
0x18000638a  mov     rax, [rax+20h]
0x18000638e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006393  mov     [rsp+250h+var_1E0], 0
0x18000639c  mov     [rbp+150h+var_1C0], 0
0x1800063a3  cmp     word ptr [rax], 0
0x1800063a7  jz      short loc_1800063DA
0x1800063a9  mov     rax, [r14]
0x1800063ac  lea     r9, [rbp+150h+var_1C0]
0x1800063b0  lea     r8, [rsp+250h+var_1E0]
0x1800063b5  mov     rcx, r14
0x1800063b8  lea     rdx, aAppWarmingUp; "APP_WARMING_UP"
0x1800063bf  mov     rax, [rax+78h]
0x1800063c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063c8  test    eax, eax
0x1800063ca  js      short loc_1800063DA
0x1800063cc  mov     rax, [rsp+250h+var_1E0]
0x1800063d1  cmp     byte ptr [rax], 30h ; '0'
0x1800063d4  jnz     loc_180006A45
0x1800063da  mov     r10d, [rsp+250h+var_208]
0x1800063df  mov     r11, [rbp+150h+var_1A8]
0x1800063e3  mov     byte ptr [r14+234Dh], 1
0x1800063eb  mov     ecx, [r15+7Ch]
0x1800063ef  cmp     ecx, edi
0x1800063f1  jnz     short loc_1800063FA
0x1800063f3  mov     eax, edi
0x1800063f5  mov     r8, rdi
0x1800063f8  jmp     short loc_180006404
0x1800063fa  mov     rax, [r15+68h]
0x1800063fe  mov     r8, rcx
0x180006401  mov     eax, [rax+rcx*4]
0x180006404  cmp     [r15+10h], eax
0x180006408  jz      loc_180006BB7
0x18000640e  mov     rax, [r15+50h]
0x180006412  mov     rdx, [rax+20h]
0x180006416  cmp     ecx, edi
0x180006418  jnz     short loc_18000642D
0x18000641a  mov     rax, 7FFFFFFF8h
0x180006424  mov     r9d, edi
0x180006427  mov     rsi, [rdx+rax]
0x18000642b  jmp     short loc_18000643D
0x18000642d  mov     rax, [r15+68h]
0x180006431  mov     ecx, [rax+r8*4]
0x180006435  mov     r9d, [rax+r8*4]
0x180006439  mov     rsi, [rdx+rcx*8]
0x18000643d  mov     rdi, [rsp+250h+var_1F8]
0x180006442  mov     rcx, [r15+58h]
0x180006446  mov     eax, r9d
0x180006449  cmp     dword ptr [rdi], 20000000h
0x18000644f  mov     r12, [rcx+rax*8]
0x180006453  jnz     short loc_18000647A
0x180006455  test    r10d, r10d
0x180006458  jnz     short loc_18000647A
0x18000645a  cmp     [rsi+14h], r10d
0x18000645e  jz      short loc_18000647A
0x180006460  mov     rax, [r11]
0x180006463  mov     rcx, r11
0x180006466  mov     rax, [rax+8]
0x18000646a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000646f  test    eax, eax
0x180006471  jnz     short loc_18000647A
0x180006473  xor     esi, esi
0x180006475  jmp     loc_180006958
0x18000647a  cmp     byte ptr [r14+238Ah], 0
0x180006482  jz      loc_18000682F
0x180006488  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18000648f  xorps   xmm0, xmm0
0x180006492  mov     [rsp+250h+var_1D8], rax
0x180006497  lea     r14, [rbx+8]
0x18000649b  mov     rax, [r14]
0x18000649e  lea     rdx, [rsp+250h+var_1D8]
0x1800064a3  mov     rcx, r14
0x1800064a6  movdqu  [rbp+150h+var_1D0], xmm0
0x1800064ab  mov     rax, [rax]
0x1800064ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064b3  test    eax, eax
0x1800064b5  js      loc_18000682A
0x1800064bb  cmp     dword ptr [rbp+150h+var_1D0+8], 0
0x1800064bf  jz      loc_18000682A
0x1800064c5  cmp     dword ptr [rbp+150h+var_1D0+4], 5
0x1800064c9  jb      loc_18000682A
0x1800064cf  mov     rax, qword ptr [rbp+150h+var_1D0]
0x1800064d3  cmp     eax, 100h
0x1800064d8  jz      short loc_1800064E4
0x1800064da  bt      eax, 8
0x1800064de  jnb     loc_18000682A
0x1800064e4  mov     rax, [rsi]
0x1800064e7  mov     rcx, rsi
0x1800064ea  mov     ebx, [rdi]
0x1800064ec  movzx   edi, byte ptr [r15+0Ch]
0x1800064f1  mov     rax, [rax]
0x1800064f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064f9  cmp     [rsp+250h+var_208], 0
0x1800064fe  jz      loc_180006813
0x180006504  mov     rcx, rax
0x180006507  mov     [rbp+150h+var_1B8], edi
0x18000650a  mov     eax, [rsp+250h+var_200]
0x18000650e  lea     rdi, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180006515  mov     [rbp+150h+var_1B0], eax
  ... truncated ...
```
