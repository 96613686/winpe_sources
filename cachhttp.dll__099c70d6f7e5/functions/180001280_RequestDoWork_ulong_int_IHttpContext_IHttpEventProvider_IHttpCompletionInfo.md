# RequestDoWork(ulong,int,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)

- ea: `0x180001280`
- end: `0x180001dca`
- name: `?RequestDoWork@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KHPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z`
- size: `2890`
- prototype: `__int64(int, __int64, struct IHttpContext *, __int64, ...)`
- caller_count: `17`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180001200`
- `0x180001220`
- `0x180001240`
- `0x180001260`
- `0x1800066e0`
- `0x180006740`
- `0x1800067a0`
- `0x180006800`
- `0x180006860`
- `0x1800068c0`
- `0x180006920`
- `0x180006a50`
- `0x180006ab0`
- `0x180006b10`
- `0x180006d70`
- `0x180006dd0`
- `0x180006ef0`

## callees

- `0x180001280`
- `0x180001dd0`
- `0x1800020d0`
- `0x180002a4c`
- `0x180002f20`
- `0x1800040e8`
- `0x180004220`
- `0x1800054e8`
- `0x180005a0c`
- `0x180006fd0`
- `0x180007080`
- `0x180009010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x1800018fc`
- `msvcrt!wcsrchr` at `0x1800018fc`
- `msvcrt!_wcsicmp` at `0x180001928`
- `msvcrt!_wcsicmp` at `0x180001928`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18000191c`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18000191c`
- `iisutil!?QueryStr@STRA@@QEBAPEBDXZ` at `0x180001c5d`
- `iisutil!?QueryStr@STRA@@QEBAPEBDXZ` at `0x180001c73`
- `iisutil!?QueryStr@STRA@@QEBAPEBDXZ` at `0x180001c91`
- `iisutil!?QueryStr@STRA@@QEBAPEBDXZ` at `0x180001db1`
- `iisutil!?QueryStr@STRA@@QEBAPEBDXZ` at `0x180001c5d`
- `iisutil!?QueryStr@STRA@@QEBAPEBDXZ` at `0x180001c73`
- `iisutil!?QueryStr@STRA@@QEBAPEBDXZ` at `0x180001c91`
- `iisutil!?QueryStr@STRA@@QEBAPEBDXZ` at `0x180001db1`

## string_xrefs

- `0x180001d81`: `no-cache`

## pseudocode

```c
__int64 RequestDoWork(int a1, __int64 a2, struct IHttpContext *a3, __int64 a4, ...)
{
  int v4; // r13d
  int v5; // edi
  unsigned int v6; // r12d
  __int64 v9; // r14
  __int64 v10; // r15
  int v11; // ebx
  int v12; // ebx
  int v13; // ebx
  int (__fastcall ***v15)(_QWORD, GUID **); // rax
  int (__fastcall **v16)(_QWORD, GUID **); // rcx
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  OUTPUT_CACHE *v21; // rcx
  int v22; // ebx
  __int64 v23; // rax
  struct IHttpCachePolicy *v24; // rbx
  unsigned int v25; // r12d
  int (__fastcall ***v26)(_QWORD, GUID **); // rax
  struct IHttpTraceContext *v27; // rax
  const struct _GUID *v28; // rdx
  int (__fastcall ***v29)(_QWORD, GUID **); // rax
  int (__fastcall **v30)(_QWORD, GUID **); // rcx
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  OUTPUT_CACHE *v34; // rcx
  int (__fastcall ***v35)(_QWORD, GUID **); // rax
  void (__fastcall ***v36)(_QWORD, __int64, __int64); // r9
  void (__fastcall *v37)(_QWORD, __int64, __int64); // rax
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rbx
  __int64 v41; // rax
  __int64 v42; // rbx
  __int64 (__fastcall ***v43)(_QWORD); // rax
  struct _HTTP_CACHE_POLICY *v44; // rax
  __int64 v45; // rdx
  __int64 v46; // rax
  __int64 v47; // r15
  __int64 v48; // rdi
  __int64 v49; // r15
  __int64 v50; // r13
  const wchar_t *v51; // rax
  _QWORD *v52; // rbx
  _QWORD *v53; // rsi
  wchar_t *v54; // rax
  const wchar_t *v55; // r14
  const wchar_t *Str; // rax
  OUTPUT_META_CONTEXT *v57; // rax
  __int64 v58; // rax
  unsigned int v59; // edi
  __int64 v60; // rax
  unsigned int v61; // ebx
  struct IHttpTraceContext *v62; // rax
  const struct _GUID *v63; // rdx
  struct IHttpTraceContext *v64; // rax
  const struct _GUID *v65; // rdx
  struct IHttpTraceContext *v66; // rax
  const struct _GUID *v67; // rdx
  __int64 v68; // rax
  __int64 v69; // rbx
  __int64 v70; // rax
  int v71; // ecx
  const char *v72; // rcx
  void (__fastcall *v73)(__int64, const char *); // rbx
  const char *v74; // rax
  int v75; // ecx
  int v76; // ecx
  int v77; // ecx
  void (__fastcall *v78)(__int64, const char *); // rbx
  const char *v79; // rax
  __int64 v80; // [rsp+40h] [rbp-38h] BYREF
  __int64 v81; // [rsp+48h] [rbp-30h] BYREF
  __int64 v82; // [rsp+50h] [rbp-28h] BYREF
  GUID *v83; // [rsp+58h] [rbp-20h] BYREF
  __int128 v84; // [rsp+60h] [rbp-18h]
  int v85; // [rsp+C0h] [rbp+48h] BYREF
  int v86; // [rsp+C8h] [rbp+50h] BYREF
  unsigned int v87; // [rsp+D0h] [rbp+58h] BYREF
  __int64 v88; // [rsp+D8h] [rbp+60h]
  struct INativeSectionException *v89; // [rsp+E0h] [rbp+68h] BYREF
  va_list va; // [rsp+E0h] [rbp+68h]
  va_list va1; // [rsp+E8h] [rbp+70h] BYREF

  va_start(va1, a4);
  va_start(va, a4);
  va_arg(va1, _QWORD);
  v88 = a4;
  v86 = 1;
  v89 = 0;
  v4 = 0;
  v80 = 0;
  v5 = 0;
  v82 = 0;
  v6 = 0;
  v85 = 0;
  v87 = 0;
  v9 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 32LL))(a3);
  v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  v81 = 0;
  if ( (*(int (__fastcall **)(struct IHttpServer *, _QWORD, __int64 *))(*(_QWORD *)g_pGlobalInfo + 200LL))(
         g_pGlobalInfo,
         0,
         &v81) >= 0
    && (*(int (__fastcall **)(__int64, GUID *, __int64, GUID *, __int64 *))(*(_QWORD *)v81 + 224LL))(
         v81,
         &GUID_cb1c40ca_70f2_41a0_add2_881f5ef57388,
         v10,
         &GUID_9f4ba807_050e_4495_ae55_8870f7e9194a,
         &v82) >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v82 + 112LL))(v82);
  }
  v11 = a1 - 1;
  if ( !v11 )
  {
    v46 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 160LL))(a3);
    v47 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v46 + 24LL))(v46);
    v48 = (**(__int64 (__fastcall ***)(__int64, void *))v47)(v47, g_pModuleId);
    if ( !v48 )
    {
      v57 = (OUTPUT_META_CONTEXT *)operator new(0x28u);
      v48 = (__int64)v57;
      if ( !v57 )
      {
        v22 = -2147024888;
        goto LABEL_67;
      }
      *((_QWORD *)v57 + 4) = 0;
      *(_QWORD *)v57 = &OUTPUT_META_CONTEXT::`vftable';
      *((_QWORD *)v57 + 3) = (char *)v57 + 16;
      *((_QWORD *)v57 + 2) = (char *)v57 + 16;
      v22 = OUTPUT_META_CONTEXT::Initialize(v57, a3, (struct INativeSectionException **)va);
      if ( v22 < 0 )
      {
        (**(void (__fastcall ***)(__int64))v48)(v48);
        goto LABEL_67;
      }
      v22 = (*(__int64 (__fastcall **)(__int64, __int64, void *))(*(_QWORD *)v47 + 8LL))(v47, v48, g_pModuleId);
      if ( v22 < 0 )
      {
        (**(void (__fastcall ***)(__int64))v48)(v48);
        if ( v22 != -2147024811 )
          goto LABEL_67;
        v48 = (**(__int64 (__fastcall ***)(__int64, void *))v47)(v47, g_pModuleId);
      }
    }
    v49 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 32LL))(a3);
    v50 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
    if ( !*(_DWORD *)(v48 + 12) )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v49 + 112LL))(v49, 2);
    if ( !*(_DWORD *)(v48 + 8) )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 80LL))(v50);
    v51 = (const wchar_t *)(*(__int64 (__fastcall **)(struct IHttpContext *, _QWORD))(*(_QWORD *)a3 + 176LL))(a3, 0);
    v52 = (_QWORD *)(v48 + 16);
    if ( (_QWORD *)*v52 != v52 )
    {
      v54 = wcsrchr(v51, 0x2Eu);
      v53 = (_QWORD *)*v52;
      v55 = (const wchar_t *)&qword_18000AC90;
      if ( v54 )
        v55 = v54;
      while ( v53 != v52 )
      {
        Str = STRU::QueryStr((STRU *)(v53 + 2));
        if ( !_wcsicmp(v55, Str) )
        {
          if ( !v53 )
            return 0;
          goto LABEL_91;
        }
        v53 = (_QWORD *)*v53;
      }
    }
    v53 = *(_QWORD **)(v48 + 32);
    if ( !v53 )
      return 0;
LABEL_91:
    if ( *((_BYTE *)v53 + 201) )
      *(_QWORD *)(**(__int64 (__fastcall ***)(__int64))v50)(v50) = v53[24];
    else
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v49 + 112LL))(v49, 2);
    v68 = *(_QWORD *)v50;
    if ( !*((_BYTE *)v53 + 200) )
    {
      (*(void (__fastcall **)(__int64))(v68 + 80))(v50);
      return 0;
    }
    v69 = v53[23];
    *(_QWORD *)(*(__int64 (__fastcall **)(__int64))(v68 + 16))(v50) = v69;
    if ( !*((_DWORD *)v53 + 46) )
    {
LABEL_98:
      if ( *STRA::QueryStr((STRA *)(v53 + 9)) )
      {
        v78 = *(void (__fastcall **)(__int64, const char *))(*(_QWORD *)v50 + 24LL);
        v79 = STRA::QueryStr((STRA *)(v53 + 9));
        v78(v50, v79);
      }
      if ( *STRA::QueryStr((STRA *)(v53 + 16)) )
      {
        v73 = *(void (__fastcall **)(__int64, const char *))(*(_QWORD *)v50 + 40LL);
        v74 = STRA::QueryStr((STRA *)(v53 + 16));
        v73(v50, v74);
      }
      return 0;
    }
    v70 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v49 + 8LL))(v49);
    v71 = *((_DWORD *)v53 + 51);
    if ( v71 != 1 )
    {
      if ( !v71 || (v75 = v71 - 2) == 0 )
      {
        v72 = "public";
        *(_WORD *)(v70 + 56) = 6;
        goto LABEL_97;
      }
      v76 = v75 - 1;
      if ( !v76 || (v77 = v76 - 1) == 0 )
      {
        v72 = "no-cache";
        *(_WORD *)(v70 + 56) = 8;
        goto LABEL_97;
      }
      if ( v77 != 1 )
        goto LABEL_98;
    }
    v72 = "private";
    *(_WORD *)(v70 + 56) = 7;
LABEL_97:
    *(_QWORD *)(v70 + 64) = v72;
    goto LABEL_98;
  }
  v12 = v11 - 7;
  if ( v12 )
  {
    v13 = v12 - 504;
    if ( v13 )
    {
      if ( v13 == 536870400 )
      {
        v38 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 152LL))(a3);
        if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v38 + 8LL))(v38) )
        {
          v39 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
          if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v39 + 104LL))(v39) )
          {
            v40 = v88;
            if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v88 + 8LL))(v88) )
            {
              if ( ((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40) & 2) == 0 )
              {
                v41 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 24LL))(a3);
                if ( *(_DWORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v41 + 8LL))(v41) + 36) == 4
                  && *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9) + 8) == 200 )
                {
                  if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v9 + 120LL))(v9) )
                  {
                    v42 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 32LL))(a3);
                    v43 = (__int64 (__fastcall ***)(_QWORD))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
                    v44 = (struct _HTTP_CACHE_POLICY *)(**v43)(v43);
                    if ( v44->Policy )
                    {
                      if ( (int)SetupCacheInvalidator(a3, v44) >= 0 )
                      {
                        v45 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 8LL))(v45);
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
      return 0;
    }
    v15 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 272LL))(a3);
    v83 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
    v16 = *v15;
    v84 = 0;
    if ( (*v16)(v15, &v83) >= 0 && DWORD2(v84) && DWORD1(v84) >= 4 && ((_DWORD)v84 == 128 || (v84 & 0x80u) != 0LL) )
    {
      v58 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      v59 = *(_DWORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58) + 4);
      v60 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      v61 = *(_DWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
      v62 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 272LL))(a3);
      IISCacheEvents::OUTPUT_CACHE_UPDATE_START::RaiseEvent(v62, v63, v61, v59);
    }
    v17 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 152LL))(a3);
    if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v17 + 8LL))(v17) )
    {
      v25 = 2;
      goto LABEL_21;
    }
    if ( (*(unsigned int (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 40LL))(a3) )
    {
      v25 = 3;
      goto LABEL_21;
    }
    if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v9 + 136LL))(v9) )
    {
      v25 = 4;
      goto LABEL_21;
    }
    v18 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 24LL))(a3);
    if ( *(_DWORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 8LL))(v18) + 36) != 4 )
    {
      v25 = 5;
      goto LABEL_21;
    }
    if ( *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9) + 8) != 200 )
    {
      v25 = 6;
      goto LABEL_21;
    }
    v19 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v19 + 88LL))(v19) )
    {
      v25 = 12;
      goto LABEL_21;
    }
    v20 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v20 + 72LL))(v20) )
    {
LABEL_20:
      v25 = 7;
LABEL_21:
      v26 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 272LL))(a3);
      v83 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
      v84 = 0;
      if ( (**v26)(v26, &v83) >= 0 && DWORD2(v84) && DWORD1(v84) >= 4 && ((_DWORD)v84 == 128 || (v84 & 0x80u) != 0LL) )
      {
        v27 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 272LL))(a3);
        IISCacheEvents::OUTPUT_CACHE_UPDATE_END::RaiseEvent(v27, v28, v25);
      }
      return 0;
    }
    v22 = OUTPUT_CACHE::Initialize(v21, (struct INativeSectionException **)va);
    if ( v22 >= 0 )
    {
      v23 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 32LL))(a3);
      v24 = (struct IHttpCachePolicy *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      if ( *(_DWORD *)(*(__int64 (__fastcall **)(struct IHttpCachePolicy *))(*(_QWORD *)v24 + 16LL))(v24) )
      {
        if ( (int)AddResponse(a3, v24, (enum IISCacheEvents::OUTPUT_CACHE_UPDATE_END::enumResult *)&v86) >= 0 )
          (*(void (__fastcall **)(struct IHttpCachePolicy *))(*(_QWORD *)v24 + 96LL))(v24);
        v25 = v86;
        goto LABEL_21;
      }
      goto LABEL_20;
    }
    goto LABEL_67;
  }
  v29 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 272LL))(a3);
  v83 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v30 = *v29;
  v84 = 0;
  if ( (*v30)(v29, &v83) >= 0 && DWORD2(v84) && DWORD1(v84) >= 4 && ((_DWORD)v84 == 128 || (v84 & 0x80u) != 0LL) )
  {
    v64 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 272LL))(a3);
    IISCacheEvents::OUTPUT_CACHE_LOOKUP_START::RaiseEvent(v64, v65);
  }
  v31 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v31 + 72LL))(v31) )
  {
    v6 = 4;
LABEL_31:
    v35 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 272LL))(a3);
    v83 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
    v84 = 0;
    if ( (**v35)(v35, &v83) >= 0 && DWORD2(v84) && DWORD1(v84) >= 4 && ((_DWORD)v84 == 128 || (v84 & 0x80u) != 0LL) )
    {
      v66 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 272LL))(a3);
      IISCacheEvents::OUTPUT_CACHE_LOOKUP_END::RaiseEvent(v66, v67, v6);
    }
    v36 = (void (__fastcall ***)(_QWORD, __int64, __int64))(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 96LL))(g_pGlobalInfo);
    v37 = **v36;
    if ( v4 )
    {
      v37(v36, 23, 1);
      return 2;
    }
    v37(v36, 24, 1);
    return 0;
  }
  v32 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 24LL))(a3);
  v33 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v32 + 8LL))(v32);
  if ( !g_fAnyResponseCached || *(_DWORD *)(v33 + 36) != 4 )
    goto LABEL_31;
  v22 = OUTPUT_CACHE::Initialize(v34, (struct INativeSectionException **)va);
  if ( v22 >= 0 )
  {
    RetrieveResponse(a3, &v85, (enum IISCacheEvents::OUTPUT_CACHE_LOOKUP_END::enumResult *)&v87, v5);
    v4 = v85;
    v6 = v87;
    goto LABEL_31;
  }
LABEL_67:
  *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9) + 536) = 0;
  if ( v89 )
    (**(void (__fastcall ***)(struct INativeSectionException *, GUID *, __int64 *))v89)(
      v89,
      &IID_IAppHostConfigException,
      &v80);
  (*(void (__fastcall **)(__int64, __int64, const char *, __int64, int, __int64, _DWORD))(*(_QWORD *)v9 + 24LL))(
    v9,
    500,
    "Internal Server Error",
    19,
    v22,
    v80,
    0);
  if ( v80 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
    v80 = 0;
  }
  if ( v89 )
    (*(void (__fastcall **)(struct INativeSectionException *))(*(_QWORD *)v89 + 16LL))(v89);
  return 2;
}

```

## disassembly

```asm
0x180001280  mov     [rsp-40h+arg_18], r9
0x180001285  mov     [rsp-40h+arg_8], edx
0x180001289  push    rbp
0x18000128a  push    rbx
0x18000128b  push    rsi
0x18000128c  push    rdi
0x18000128d  push    r12
0x18000128f  push    r13
0x180001291  push    r14
0x180001293  push    r15
0x180001295  mov     rbp, rsp
0x180001298  sub     rsp, 78h
0x18000129c  xor     eax, eax
0x18000129e  mov     [rbp+arg_8], 1
0x1800012a5  mov     [rbp+arg_20], rax
0x1800012a9  mov     r13d, eax
0x1800012ac  mov     [rbp+var_38], rax
0x1800012b0  mov     edi, eax
0x1800012b2  mov     [rbp+var_28], rax
0x1800012b6  mov     r12d, eax
0x1800012b9  mov     [rbp+arg_0], eax
0x1800012bc  mov     ebx, ecx
0x1800012be  mov     [rbp+arg_10], eax
0x1800012c1  mov     rcx, r8
0x1800012c4  mov     rax, [r8]
0x1800012c7  mov     rsi, r8
0x1800012ca  mov     rax, [rax+20h]
0x1800012ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800012d3  mov     r14, rax
0x1800012d6  mov     rcx, r14
0x1800012d9  mov     rax, [rax]
0x1800012dc  mov     rax, [rax+10h]
0x1800012e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800012e5  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x1800012ec  lea     r8, [rbp+var_30]
0x1800012f0  mov     r15, rax
0x1800012f3  mov     [rbp+var_30], rdi
0x1800012f7  xor     edx, edx
0x1800012f9  mov     rax, [rcx]
0x1800012fc  mov     rax, [rax+0C8h]
0x180001303  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001308  test    eax, eax
0x18000130a  js      short loc_18000134F
0x18000130c  mov     rcx, [rbp+var_30]
0x180001310  lea     rdx, [rbp+var_28]
0x180001314  mov     [rsp+78h+var_58], rdx
0x180001319  lea     r9, _GUID_9f4ba807_050e_4495_ae55_8870f7e9194a
0x180001320  mov     r8, r15
0x180001323  lea     rdx, _GUID_cb1c40ca_70f2_41a0_add2_881f5ef57388
0x18000132a  mov     rax, [rcx]
0x18000132d  mov     rax, [rax+0E0h]
0x180001334  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001339  test    eax, eax
0x18000133b  js      short loc_18000134F
0x18000133d  mov     rcx, [rbp+var_28]
0x180001341  mov     rax, [rcx]
0x180001344  mov     rax, [rax+70h]
0x180001348  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000134d  mov     edi, eax
0x18000134f  sub     ebx, 1
0x180001352  jz      loc_18000183F
0x180001358  sub     ebx, 7
0x18000135b  jz      loc_18000159D
0x180001361  sub     ebx, 1F8h
0x180001367  jz      short loc_180001388
0x180001369  cmp     ebx, 1FFFFE00h
0x18000136f  jz      loc_1800016BA
0x180001375  xor     eax, eax
0x180001377  add     rsp, 78h
0x18000137b  pop     r15
0x18000137d  pop     r14
0x18000137f  pop     r13
0x180001381  pop     r12
0x180001383  pop     rdi
0x180001384  pop     rsi
0x180001385  pop     rbx
0x180001386  pop     rbp
0x180001387  retn
0x180001388  mov     rax, [rsi]
0x18000138b  mov     rcx, rsi
0x18000138e  mov     rax, [rax+110h]
0x180001395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000139a  mov     r8, rax
0x18000139d  lea     r15, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x1800013a4  xorps   xmm0, xmm0
0x1800013a7  mov     [rbp+var_20], r15
0x1800013ab  lea     rdx, [rbp+var_20]
0x1800013af  mov     rcx, [rax]
0x1800013b2  movdqu  [rbp+var_18], xmm0
0x1800013b7  mov     rax, [rcx]
0x1800013ba  mov     rcx, r8
0x1800013bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013c2  test    eax, eax
0x1800013c4  js      short loc_1800013D0
0x1800013c6  cmp     dword ptr [rbp+var_18+8], r12d
0x1800013ca  jnz     loc_180001AC7
0x1800013d0  mov     rax, [rsi]
0x1800013d3  mov     rcx, rsi
0x1800013d6  mov     rax, [rax+98h]
0x1800013dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013e2  mov     rdx, rax
0x1800013e5  mov     rcx, [rax]
0x1800013e8  mov     rax, [rcx+8]
0x1800013ec  mov     rcx, rdx
0x1800013ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013f4  test    eax, eax
0x1800013f6  jz      loc_180001834
0x1800013fc  mov     rax, [rsi]
0x1800013ff  mov     rcx, rsi
0x180001402  mov     rax, [rax+28h]
0x180001406  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000140b  test    eax, eax
0x18000140d  jnz     loc_180001CCA
0x180001413  mov     rax, [r14]
0x180001416  mov     rcx, r14
0x180001419  mov     rax, [rax+88h]
0x180001420  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001425  test    eax, eax
0x180001427  jnz     loc_180001974
0x18000142d  mov     rax, [rsi]
0x180001430  mov     rcx, rsi
0x180001433  mov     rax, [rax+18h]
0x180001437  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000143c  mov     rdx, rax
0x18000143f  mov     rcx, [rax]
0x180001442  mov     rax, [rcx+8]
0x180001446  mov     rcx, rdx
0x180001449  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000144e  cmp     dword ptr [rax+24h], 4
0x180001452  jnz     loc_180001CD5
0x180001458  mov     rax, [r14]
0x18000145b  mov     rcx, r14
0x18000145e  mov     rax, [rax+8]
0x180001462  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001467  mov     ecx, 0C8h
0x18000146c  cmp     [rax+8], cx
0x180001470  jnz     loc_180001829
0x180001476  mov     rax, [r14]
0x180001479  mov     rcx, r14
0x18000147c  mov     rax, [rax+10h]
0x180001480  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001485  mov     rdx, rax
0x180001488  mov     rcx, [rax]
0x18000148b  mov     rax, [rcx+58h]
0x18000148f  mov     rcx, rdx
0x180001492  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001497  test    eax, eax
0x180001499  jnz     loc_180001CE0
0x18000149f  mov     rax, [r14]
0x1800014a2  mov     rcx, r14
0x1800014a5  mov     rax, [rax+10h]
0x1800014a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800014ae  mov     rdx, rax
0x1800014b1  mov     rcx, [rax]
0x1800014b4  mov     rax, [rcx+48h]
0x1800014b8  mov     rcx, rdx
0x1800014bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800014c0  test    eax, eax
0x1800014c2  jz      short loc_180001513
0x1800014c4  lea     rdx, [rbp+arg_20]; struct INativeSectionException **
0x1800014c8  call    ?Initialize@OUTPUT_CACHE@@QEAAJPEAPEAVINativeSectionException@@@Z; OUTPUT_CACHE::Initialize(INativeSectionException * *)
0x1800014cd  mov     ebx, eax
0x1800014cf  test    eax, eax
0x1800014d1  js      loc_18000199A
0x1800014d7  mov     rax, [rsi]
0x1800014da  mov     rcx, rsi
0x1800014dd  mov     rax, [rax+20h]
0x1800014e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800014e6  mov     rdx, rax
0x1800014e9  mov     rcx, [rax]
0x1800014ec  mov     rax, [rcx+10h]
0x1800014f0  mov     rcx, rdx
0x1800014f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800014f8  mov     rbx, rax
0x1800014fb  mov     rcx, [rax]
0x1800014fe  mov     rax, [rcx+10h]
0x180001502  mov     rcx, rbx
0x180001505  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000150a  cmp     [rax], r12d
0x18000150d  jnz     loc_180001CEB
0x180001513  mov     r12d, 7
0x180001519  mov     rax, [rsi]
0x18000151c  mov     rcx, rsi
0x18000151f  mov     rax, [rax+110h]
0x180001526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000152b  mov     r8, rax
0x18000152e  mov     [rbp+var_20], r15
0x180001532  xorps   xmm0, xmm0
0x180001535  lea     rdx, [rbp+var_20]
0x180001539  movdqu  [rbp+var_18], xmm0
0x18000153e  mov     rcx, [rax]
0x180001541  mov     rax, [rcx]
0x180001544  mov     rcx, r8
0x180001547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000154c  test    eax, eax
0x18000154e  js      loc_180001375
0x180001554  cmp     dword ptr [rbp+var_18+8], r13d
0x180001558  jz      loc_180001375
0x18000155e  cmp     dword ptr [rbp+var_18+4], 4
0x180001562  jb      loc_180001375
0x180001568  mov     rax, qword ptr [rbp+var_18]
0x18000156c  cmp     eax, 80h
0x180001571  jz      short loc_18000157B
0x180001573  test    al, al
0x180001575  jns     loc_180001375
0x18000157b  mov     rax, [rsi]
0x18000157e  mov     rcx, rsi
0x180001581  mov     rax, [rax+110h]
0x180001588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000158d  mov     r8d, r12d; unsigned int
0x180001590  mov     rcx, rax; struct IHttpTraceContext *
0x180001593  call    ?RaiseEvent@OUTPUT_CACHE_UPDATE_END@IISCacheEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@K@Z; IISCacheEvents::OUTPUT_CACHE_UPDATE_END::RaiseEvent(IHttpTraceContext *,_GUID const *,ulong)
0x180001598  jmp     loc_180001375
0x18000159d  mov     rax, [rsi]
0x1800015a0  mov     rcx, rsi
0x1800015a3  mov     rax, [rax+110h]
0x1800015aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800015af  mov     r8, rax
0x1800015b2  lea     r15, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x1800015b9  xorps   xmm0, xmm0
0x1800015bc  mov     [rbp+var_20], r15
0x1800015c0  lea     rdx, [rbp+var_20]
0x1800015c4  mov     rcx, [rax]
0x1800015c7  movdqu  [rbp+var_18], xmm0
0x1800015cc  mov     rax, [rcx]
0x1800015cf  mov     rcx, r8
0x1800015d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800015d7  test    eax, eax
0x1800015d9  js      short loc_1800015E5
0x1800015db  cmp     dword ptr [rbp+var_18+8], r12d
0x1800015df  jnz     loc_180001B50
0x1800015e5  mov     rax, [r14]
0x1800015e8  mov     rcx, r14
0x1800015eb  mov     rax, [rax+10h]
0x1800015ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800015f4  mov     rdx, rax
0x1800015f7  mov     rcx, [rax]
0x1800015fa  mov     rax, [rcx+48h]
0x1800015fe  mov     rcx, rdx
0x180001601  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001606  test    eax, eax
0x180001608  jz      loc_180001D16
0x18000160e  mov     rax, [rsi]
0x180001611  mov     rcx, rsi
0x180001614  mov     rax, [rax+18h]
0x180001618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000161d  mov     rdx, rax
0x180001620  mov     rcx, [rax]
0x180001623  mov     rax, [rcx+8]
0x180001627  mov     rcx, rdx
0x18000162a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000162f  cmp     cs:?g_fAnyResponseCached@@3HA, r12d; int g_fAnyResponseCached
0x180001636  jnz     loc_18000193B
0x18000163c  mov     rax, [rsi]
0x18000163f  mov     rcx, rsi
0x180001642  mov     rax, [rax+110h]
0x180001649  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000164e  mov     r8, rax
0x180001651  mov     [rbp+var_20], r15
0x180001655  xorps   xmm0, xmm0
0x180001658  lea     rdx, [rbp+var_20]
0x18000165c  movdqu  [rbp+var_18], xmm0
0x180001661  mov     rcx, [rax]
0x180001664  mov     rax, [rcx]
0x180001667  mov     rcx, r8
0x18000166a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000166f  test    eax, eax
0x180001671  js      short loc_18000167D
0x180001673  cmp     dword ptr [rbp+var_18+8], 0
0x180001677  jnz     loc_180001B8C
0x18000167d  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x180001684  mov     rax, [rcx]
0x180001687  mov     rax, [rax+60h]
0x18000168b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001690  mov     r9, rax
0x180001693  mov     r8d, 1
0x180001699  mov     rcx, [rax]
0x18000169c  mov     rax, [rcx]
0x18000169f  mov     rcx, r9
0x1800016a2  test    r13d, r13d
0x1800016a5  jnz     loc_180001815
0x1800016ab  mov     edx, 18h
0x1800016b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800016b5  jmp     loc_180001375
0x1800016ba  mov     rax, [rsi]
0x1800016bd  mov     rcx, rsi
0x1800016c0  mov     rax, [rax+98h]
0x1800016c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800016cc  mov     rdx, rax
0x1800016cf  mov     rcx, [rax]
0x1800016d2  mov     rax, [rcx+8]
0x1800016d6  mov     rcx, rdx
0x1800016d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800016de  test    eax, eax
0x1800016e0  jz      loc_180001375
0x1800016e6  mov     rax, [r14]
0x1800016e9  mov     rcx, r14
0x1800016ec  mov     rax, [rax+10h]
0x1800016f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800016f5  mov     rdx, rax
  ... truncated ...
```
