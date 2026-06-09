# W3_CONTEXT::SetupStateMachine(void)

- ea: `0x180009e50`
- end: `0x18000aaac`
- name: `?SetupStateMachine@W3_CONTEXT@@QEAAXXZ`
- size: `3164`
- prototype: `void __fastcall(W3_CONTEXT *__hidden this)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x180009680`

## callees

- `0x180009030`
- `0x180009c40`
- `0x180009d44`
- `0x180009e50`
- `0x18000b640`
- `0x18000b810`
- `0x18000bce0`
- `0x18000e220`
- `0x180013660`
- `0x1800143d0`
- `0x1800176ac`
- `0x18001ab30`
- `0x18001b978`
- `0x180020e1c`
- `0x180020fac`
- `0x180023394`
- `0x18002368c`
- `0x180023774`
- `0x18002385c`
- `0x180023c9c`
- `0x180037790`
- `0x180037820`
- `0x180038010`

## import_xrefs

- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180009f76`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180009f92`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180009f76`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180009f92`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18000a71d`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18000a79b`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18000a71d`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18000a79b`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000a760`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000a80b`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000a760`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000a80b`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000a745`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000a7e2`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000a745`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000a7e2`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x18000a7ce`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x18000a7ce`

## string_xrefs

- `0x18000a927`: `Service Unavailable`

## pseudocode

```c
void __fastcall W3_CONTEXT::SetupStateMachine(W3_CONTEXT *this)
{
  __int64 v1; // rax
  char *v3; // rcx
  __int64 v4; // r13
  W3_REQUEST *v5; // rcx
  const char *HttpMethod; // rbx
  const unsigned __int16 *v7; // rdi
  __int64 v8; // rsi
  __int64 v9; // r14
  const unsigned __int16 *v10; // rax
  const struct _GUID *v11; // rdx
  int v12; // ebx
  W3_SERVER *v13; // rdi
  __int64 v14; // r14
  _QWORD *Ptr; // rax
  __int64 v16; // rbx
  _QWORD *v17; // r12
  unsigned int *v18; // rbx
  __int64 v19; // rdi
  int (__fastcall ***v20)(_QWORD, GUID **); // rax
  __int64 v21; // rax
  _QWORD *v22; // rsi
  __int64 (__fastcall **v23)(_QWORD); // rax
  __int64 (__fastcall *v24)(_QWORD *); // rax
  __int64 v25; // rax
  bool v26; // zf
  int v27; // eax
  int v28; // edi
  __int64 (__fastcall **v29)(_QWORD); // rax
  __int64 (__fastcall *v30)(_QWORD *); // rax
  __int64 v31; // rax
  __int64 v32; // rcx
  const wchar_t *v33; // rax
  int v34; // r14d
  char *v35; // rsi
  NOTIFICATION_CONTEXT **v36; // rdi
  struct IHttpTraceContext *v37; // r12
  int v38; // edx
  __int64 v39; // rax
  __int64 v40; // rcx
  signed __int32 v41; // ecx
  __int64 v42; // rax
  unsigned __int32 v43; // ecx
  int v44; // edx
  W3_URL_INFO *v45; // rax
  W3_URL_INFO *v46; // rax
  W3_SITE *v47; // rax
  W3_SITE *v48; // rax
  W3_METADATA *v49; // rax
  W3_METADATA *v50; // rax
  W3_APPLICATION *v51; // rax
  W3_APPLICATION *v52; // rax
  unsigned int v53; // ebx
  __int64 v54; // rax
  int (__fastcall *v55)(W3_CONTEXT *, const char *, char **, int *); // rax
  const struct _GUID *v56; // rdx
  const char *Str; // rax
  const struct _GUID *v58; // rdx
  const char *v59; // rax
  const struct _GUID *v60; // rdx
  unsigned __int16 v61; // dx
  const char *v62; // r8
  __int16 v63; // r9
  const struct _GUID *v64; // rdx
  __int64 v65; // rax
  __int64 v66; // rcx
  void (__fastcall ***v67)(_QWORD, __int64, __int64); // rbx
  __int64 v68; // rdx
  int v69; // [rsp+20h] [rbp-E0h]
  int v70; // [rsp+40h] [rbp-C0h] BYREF
  char *v71; // [rsp+48h] [rbp-B8h] BYREF
  char *v72; // [rsp+50h] [rbp-B0h] BYREF
  GUID *v73; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v74; // [rsp+60h] [rbp-A0h]
  GUID *v75; // [rsp+70h] [rbp-90h] BYREF
  __int64 v76; // [rsp+78h] [rbp-88h]
  GUID *v77; // [rsp+80h] [rbp-80h]
  __int64 v78; // [rsp+88h] [rbp-78h]
  const wchar_t *v79; // [rsp+90h] [rbp-70h]
  int v80; // [rsp+98h] [rbp-68h]
  int v81; // [rsp+9Ch] [rbp-64h]
  __int128 v82; // [rsp+A0h] [rbp-60h]
  int v83; // [rsp+B0h] [rbp-50h]
  int v84; // [rsp+B4h] [rbp-4Ch]
  int v85; // [rsp+B8h] [rbp-48h]
  _QWORD v86[2]; // [rsp+BCh] [rbp-44h] BYREF
  char *v87; // [rsp+D0h] [rbp-30h] BYREF
  char *v88; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v89[2]; // [rsp+E0h] [rbp-20h] BYREF
  int v90; // [rsp+F0h] [rbp-10h]
  const wchar_t *v91; // [rsp+100h] [rbp+0h] BYREF
  int v92; // [rsp+108h] [rbp+8h]
  __int64 v93; // [rsp+110h] [rbp+10h]
  int v94; // [rsp+118h] [rbp+18h]
  __int64 v95; // [rsp+120h] [rbp+20h]
  const wchar_t *v96; // [rsp+128h] [rbp+28h]
  int v97; // [rsp+130h] [rbp+30h]
  __int64 v98; // [rsp+138h] [rbp+38h]
  int v99; // [rsp+140h] [rbp+40h]
  __int64 v100; // [rsp+148h] [rbp+48h]
  const wchar_t *v101; // [rsp+150h] [rbp+50h]
  int v102; // [rsp+158h] [rbp+58h]
  int *v103; // [rsp+160h] [rbp+60h]
  int v104; // [rsp+168h] [rbp+68h]
  const wchar_t *v105; // [rsp+170h] [rbp+70h]
  char v106[8192]; // [rsp+180h] [rbp+80h] BYREF

  v89[1] = this;
  v89[0] = &PRE_BEGIN_PROVIDER::`vftable';
  v1 = *((_QWORD *)this + 6);
  v90 = 0;
  v3 = (char *)this + 8;
  v73 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v4 = *(_QWORD *)(v1 + 40);
  v74 = 0;
  if ( !this )
    v3 = 0;
  v71 = v3;
  if ( (**(int (__fastcall ***)(char *, GUID **))v3)(v3, &v73) >= 0 && DWORD2(v74) )
  {
    v5 = (W3_REQUEST *)*((_QWORD *)this + 6);
    *((_BYTE *)this + 9098) = 1;
    HttpMethod = W3_REQUEST::GetHttpMethod(v5);
    v7 = *(const unsigned __int16 **)(v4 + 72);
    v8 = *(_QWORD *)(v4 + 832);
    v9 = *(_QWORD *)(v4 + 8);
    v10 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(W3_SERVER *))(*(_QWORD *)g_pW3Server + 8LL))(g_pW3Server);
    IISGeneralEvents::GENERAL_REQUEST_START::RaiseEvent(
      (W3_CONTEXT *)((char *)this + 8),
      v11,
      HIDWORD(*(_QWORD *)(v4 + 24)),
      v10,
      v9,
      v8,
      v7,
      HttpMethod);
  }
  v12 = W3_CONTEXT::SetupStateMachinePhase1(this);
  if ( v12 < 0 )
  {
    (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 49) + 376LL))(*((_QWORD *)this + 49), 1);
    v36 = (NOTIFICATION_CONTEXT **)((char *)this + 2000);
  }
  else
  {
    v13 = g_pW3Server;
    v14 = 0;
    LODWORD(v72) = 0;
    Ptr = BUFFER::QueryPtr((W3_SERVER *)((char *)g_pW3Server + 560));
    v16 = *((unsigned int *)v13 + 286);
    v17 = Ptr;
    v18 = (unsigned int *)((char *)BUFFER::QueryPtr((W3_SERVER *)((char *)v13 + 1056)) + 4 * v16);
    v19 = (*(__int64 (__fastcall **)(_QWORD *))(v89[0] + 8LL))(v89);
    v20 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 272LL))(v19);
    v73 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
    v74 = 0;
    if ( (**v20)(v20, &v73) >= 0 && DWORD1(v74) >= 5 && DWORD2(v74) && ((_DWORD)v74 == 256 || (v74 & 0x100) != 0) )
      v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 272LL))(v19);
    while ( 1 )
    {
      v21 = *v18;
      if ( (_DWORD)v21 == -1 )
        break;
      v22 = (_QWORD *)v17[v21];
      if ( v14 )
      {
        v77 = &`IISRequestNotificationEvents::GetAreaGuid'::`2'::AreaGuid;
        memset(v86, 0, 12);
        v76 = 256;
        v75 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
        v23 = (__int64 (__fastcall **)(_QWORD))*v22;
        v78 = 4;
        v79 = L"PRE_BEGIN_REQUEST_START";
        v80 = 1;
        v24 = (__int64 (__fastcall *)(_QWORD *))*v23;
        v81 = 5;
        v85 = 2;
        v82 = 0;
        v83 = 0;
        v84 = 1;
        v91 = L"ContextId";
        v92 = 72;
        v93 = 0;
        v94 = 16;
        v95 = 0;
        v96 = L"ModuleName";
        v97 = 31;
        v98 = v24(v22);
        if ( v98 )
        {
          v25 = -1;
          do
            v26 = *(_WORD *)(v98 + 2 * v25++ + 2) == 0;
          while ( !v26 );
          v27 = 2 * v25 + 2;
        }
        else
        {
          v27 = 0;
        }
        v99 = v27;
        v100 = 0;
        *(_QWORD *)((char *)v86 + 4) = &v91;
        (*(void (__fastcall **)(__int64, GUID **))(*(_QWORD *)v14 + 16LL))(v14, &v75);
        v28 = VIRTUAL_MODULE::GlobalDoWork((__int64)v22, 256, (__int64)v89);
        v70 = v28;
        v76 = 256;
        memset(v86, 0, 12);
        v91 = L"ContextId";
        v75 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
        v78 = 5;
        v77 = &`IISRequestNotificationEvents::GetAreaGuid'::`2'::AreaGuid;
        v79 = L"PRE_BEGIN_REQUEST_END";
        v83 = 0;
        v93 = 0;
        v95 = 0;
        v96 = L"ModuleName";
        v29 = (__int64 (__fastcall **)(_QWORD))*v22;
        v80 = 1;
        v81 = 5;
        v85 = 3;
        v30 = (__int64 (__fastcall *)(_QWORD *))*v29;
        v82 = 0;
        v84 = 1;
        v92 = 72;
        v94 = 16;
        v97 = 31;
        v31 = v30(v22);
        v98 = v31;
        v32 = v31;
        if ( v31 )
        {
          v31 = -1;
          do
            v26 = *(_WORD *)(v32 + 2 * v31++ + 2) == 0;
          while ( !v26 );
          LODWORD(v31) = 2 * v31 + 2;
        }
        v99 = v31;
        v101 = L"NotificationStatus";
        v103 = &v70;
        v100 = 0;
        v102 = 19;
        v104 = 4;
        if ( v70 )
        {
          if ( v70 == 1 )
            v33 = L"NOTIFICATION_HANDLED";
          else
            v33 = 0;
        }
        else
        {
          v33 = L"NOTIFICATION_CONTINUE";
        }
        v105 = v33;
        *(_QWORD *)((char *)v86 + 4) = &v91;
        (*(void (__fastcall **)(__int64, GUID **))(*(_QWORD *)v14 + 16LL))(v14, &v75);
      }
      else
      {
        v28 = VIRTUAL_MODULE::GlobalDoWork(v17[v21], 256, (__int64)v89);
      }
      if ( v28 == 1 )
      {
        v34 = 1;
        goto LABEL_26;
      }
      ++v18;
    }
    v34 = (int)v72;
LABEL_26:
    v35 = v71;
    v36 = (NOTIFICATION_CONTEXT **)((char *)this + 2000);
    *(_DWORD *)(*((_QWORD *)this + 250) + 8LL) = 1;
    if ( *((_BYTE *)this + 9098) )
    {
      v53 = 0;
      if ( (unsigned int)WWWServerTraceProvider::CheckTracingEnabled(v35, 0, 4) )
      {
        v54 = *(_QWORD *)this;
        v71 = 0;
        v88 = 0;
        v87 = 0;
        v55 = *(int (__fastcall **)(W3_CONTEXT *, const char *, char **, int *))(v54 + 120);
        v72 = 0;
        v70 = 0;
        if ( v55(this, "REMOTE_ADDR", &v71, &v70) < 0
          || (*(int (__fastcall **)(W3_CONTEXT *, const char *, char **, int *))(*(_QWORD *)this + 120LL))(
               this,
               "REMOTE_PORT",
               &v88,
               &v70) < 0
          || (*(int (__fastcall **)(W3_CONTEXT *, const char *, char **, int *))(*(_QWORD *)this + 120LL))(
               this,
               "LOCAL_ADDR",
               &v87,
               &v70) < 0 )
        {
          v37 = (W3_CONTEXT *)((char *)this + 8);
        }
        else
        {
          v37 = (W3_CONTEXT *)((char *)this + 8);
          if ( (*(int (__fastcall **)(W3_CONTEXT *, const char *, char **, int *))(*(_QWORD *)this + 120LL))(
                 this,
                 "SERVER_PORT",
                 &v72,
                 &v70) >= 0 )
            IISGeneralEvents::GENERAL_ENDPOINT_INFORMATION::RaiseEvent(
              (W3_CONTEXT *)((char *)this + 8),
              v56,
              v71,
              v88,
              v87,
              v72);
        }
        STRA::STRA((STRA *)&v91, v106, 0x800u);
        if ( GetAllHeaders(*(const struct _HTTP_REQUEST_V2 **)(*((_QWORD *)this + 6) + 40LL), (struct STRA *)&v91, 0) >= 0 )
        {
          Str = STRA::QueryStr((STRA *)&v91);
          IISGeneralEvents::GENERAL_REQUEST_HEADERS::RaiseEvent(v37, v58, Str);
        }
        STRA::~STRA((STRA *)&v91);
      }
      else
      {
        v37 = (W3_CONTEXT *)((char *)this + 8);
      }
      if ( (unsigned int)WWWServerTraceProvider::CheckTracingEnabled(v37, 0, 5) )
      {
        STRA::STRA((STRA *)&v91, v106, 0x2000u);
        if ( *(_WORD *)(v4 + 816) )
        {
          do
          {
            if ( (int)STRA::Copy(
                        (STRA *)&v91,
                        *(const char **)(32LL * v53 + *(_QWORD *)(v4 + 824) + 8),
                        *(_DWORD *)(32LL * v53 + *(_QWORD *)(v4 + 824) + 16)) >= 0 )
            {
              v59 = STRA::QueryStr((STRA *)&v91);
              IISGeneralEvents::GENERAL_REQUEST_ENTITY::RaiseEvent(v37, v60, v59);
            }
            ++v53;
          }
          while ( v53 < *(unsigned __int16 *)(v4 + 816) );
        }
        STRA::~STRA((STRA *)&v91);
      }
    }
    else
    {
      v37 = (W3_CONTEXT *)((char *)this + 8);
    }
    v12 = W3_CONTEXT::SetupStateMachinePhase2(this);
    if ( v12 < 0 )
    {
      (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 49) + 376LL))(*((_QWORD *)this + 49), 1);
      goto LABEL_50;
    }
    if ( *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 6) + 40LL) + 36LL) != 4 )
      (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 49) + 376LL))(*((_QWORD *)this + 49), 22);
    if ( v34 )
    {
      v12 = v90;
      goto LABEL_50;
    }
    if ( ((*(__int64 (__fastcall **)(W3_CONTEXT *))(*(_QWORD *)this + 112LL))(this) & 4) == 0
      && !*(_BYTE *)(*((_QWORD *)this + 1011) + 217LL) )
    {
      v61 = 403;
      v62 = "Forbidden";
      v63 = 18;
LABEL_106:
      v69 = 0;
      goto LABEL_107;
    }
    v38 = *(_DWORD *)(*((_QWORD *)this + 1114) + 236LL);
    v39 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 6) + 40LL) + 840LL);
    if ( (v38 & 8) != 0 && !v39 )
    {
      v63 = 4;
LABEL_96:
      v62 = "Forbidden";
      v12 = -2147024891;
      v61 = 403;
      v69 = -2147024891;
LABEL_107:
      v66 = *((_QWORD *)this + 8);
      ++*(_DWORD *)(v66 + 624);
      *(_WORD *)(v66 + 592) = 0;
      W3_RESPONSE::SetStatus(*((W3_RESPONSE **)this + 8), v61, v62, v63, v69, 0, 0);
      goto LABEL_50;
    }
    if ( (v38 & 0x100) != 0 && (!v39 || *(_WORD *)(v39 + 2) < 0x80u) )
    {
      if ( *((_BYTE *)this + 9098) && (unsigned int)WWWServerTraceProvider::CheckTracingEnabled(v35, 4, 3) )
        IISSecurityEvents::SECURITY_REJECTED_REQUIRE_SSL_128::RaiseEvent(v37, v64);
      v63 = 5;
      goto LABEL_96;
    }
    v40 = *((_QWORD *)this + 1128);
    if ( !v40 || (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v40 + 56LL))(v40) == 3 )
    {
LABEL_38:
      if ( (*(__int64 (__fastcall **)(W3_CONTEXT *))(*(_QWORD *)this + 232LL))(this)
        || (v41 = _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)this + 1011) + 212LL), 1u),
            v42 = *((_QWORD *)this + 1011),
            v43 = v41 + 1,
            *((_BYTE *)this + 8097) = 1,
            *(_BYTE *)(v42 + 216))
        && v43 <= *(_DWORD *)(v42 + 208) )
      {
        if ( !(*(__int64 (__fastcall **)(W3_CONTEXT *))(*(_QWORD *)this + 232LL))(this) )
        {
          v44 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 6) + 40LL) + 36LL);
          if ( v44 != 4 )
          {
            v67 = (void (__fastcall ***)(_QWORD, __int64, __int64))(*((_QWORD *)this + 1009) + 656LL);
            switch ( v44 )
            {
              case 3:
                v68 = 11;
                goto LABEL_126;
              case 5:
                return;
              case 6:
                v68 = 12;
                goto LABEL_126;
              case 7:
                (**v67)(v67, 14, 1);
                (**v67)(v67, 1, 1);
                v68 = 2;
                goto LABEL_126;
              case 8:
                v68 = 15;
                goto LABEL_126;
              case 9:
                v68 = 16;
                goto LABEL_126;
              case 12:
                v68 = 17;
                goto LABEL_126;
              case 13:
                v68 = 18;
                goto LABEL_126;
              case 14:
                v68 = 20;
                goto LABEL_126;
              case 15:
                v68 = 21;
                goto LABEL_126;
              case 16:
                v68 = 19;
                goto LABEL_126;
              case 17:
                v68 = 23;
                goto LABEL_126;
              case 18:
                v68 = 24;
                goto LABEL_126;
              case 19:
                v68 = 22;
                goto LABEL_126;
              default:
                v68 = 25;
LABEL_126:
                (**v67)(v67, v68, 1);
                break;
            }
          }
        }
        return;
      }
      v61 = 503;
      v62 = "Service Unavailable";
      v63 = 2;
      goto LABEL_106;
    }
    if ( (*(__int64 (__fastcall **)(W3_CONTEXT *, _QWORD))(*(_QWORD *)this + 184LL))(this, 0) )
    {
      if ( *((_BYTE *)this + 9097) )
        *((_DWORD *)*v36 + 2) = 1024;
      goto LABEL_38;
    }
    v65 = *((_QWORD *)this + 8);
    if ( !*(_BYTE *)(v65 + 1260) )
    {
      ++*(_DWORD *)(v65 + 624);
      if ( *(_WORD *)(v65 + 64) < 0x190u )
      {
        v62 = "Internal Server Error";
        v63 = 0;
        v69 = -2147024888;
        v61 = 500;
        goto LABEL_107;
      }
    }
  }
LABEL_50:
  *((_DWORD *)*v36 + 2) = 1024;
  if ( *((_QWORD *)this + 1115) )
    goto LABEL_129;
  v45 = (W3_URL_INFO *)operator new(0x540u);
  if ( !v45 )
  {
    *((_QWORD *)this + 1115) = 0;
    return;
  }
  v46 = W3_URL_INFO::W3_URL_INFO(v45);
  *((_QWORD *)this + 1115) = v46;
  if ( v46 )
  {
LABEL_129:
    if ( *((_QWORD *)this + 1009) )
      goto LABEL_130;
    v47 = (W3_SITE *)operator new(0x2A0u);
    if ( !v47 )
    {
      *((_QWORD *)this + 1009) = 0;
      return;
    }
    v48 = W3_SITE::W3_SITE(v47, HIDWORD(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 6) + 40LL) + 24LL)));
    *((_QWORD *)this + 1009) = v48;
    if ( v48 )
    {
LABEL_130:
      if ( *((_QWORD *)this + 1114) )
        goto LABEL_60;
      v49 = (W3_METADATA *)operator new(0x148u);
      if ( !v49 )
      {
        *((_QWORD *)this + 1114) = 0;
        return;
      }
      v50 = W3_METADATA::W3_METADATA(v49);
      *((_QWORD *)this + 1114) = v50;
      if ( v50 )
      {
        *((_BYTE *)this + 8103) = 1;
LABEL_60:
        if ( !*((_QWORD *)this + 1011) )
        {
          v51 = (W3_APPLICATION *)operator new(0x6A0u);
          if ( v51 )
          {
            v52 = W3_APPLICATION::W3_APPLICATION(v51);
            *((_QWORD *)this + 1011) = v52;
            if ( v52 )
            {
              *((_BYTE *)this + 8096) = 1;
              (**((void (__fastcall ***)(__int64, _QWORD))v52 + 1))((__int64)v52 + 8, (unsigned int)v12);
              NOTIFICATION_CONTEXT::SetModuleList(*v36, (W3_SERVER *)((char *)g_pW3Server + 560));
              NOTIFICATION_CONTEXT::SetupCHttpModuleList(*v36, this, (W3_CONTEXT *)((char *)this + 24));
            }
          }
          else
          {
            *((_QWORD *)this + 1011) = 0;
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180009e50  push    rbp
0x180009e52  push    rbx
0x180009e53  push    rsi
0x180009e54  push    rdi
0x180009e55  push    r12
0x180009e57  push    r13
0x180009e59  push    r14
0x180009e5b  push    r15
0x180009e5d  lea     rbp, [rsp-2098h]
0x180009e65  mov     eax, 2198h
0x180009e6a  call    _alloca_probe
0x180009e6f  sub     rsp, rax
0x180009e72  mov     rax, cs:__security_cookie
0x180009e79  xor     rax, rsp
0x180009e7c  mov     [rbp+20D0h+var_50], rax
0x180009e83  mov     [rbp+20D0h+var_20E8], rcx
0x180009e87  lea     rax, ??_7PRE_BEGIN_PROVIDER@@6B@; const PRE_BEGIN_PROVIDER::`vftable'
0x180009e8e  mov     [rbp+20D0h+var_20F0], rax
0x180009e92  lea     rsi, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180009e99  mov     rax, [rcx+30h]
0x180009e9d  lea     rdx, [rsp+21D0h+var_2178]
0x180009ea2  mov     r15, rcx
0x180009ea5  mov     [rbp+20D0h+var_20E0], 0
0x180009eac  add     rcx, 8
0x180009eb0  mov     [rsp+21D0h+var_2178], rsi
0x180009eb5  xorps   xmm0, xmm0
0x180009eb8  mov     r13, [rax+28h]
0x180009ebc  xor     eax, eax
0x180009ebe  test    r15, r15
0x180009ec1  movdqu  [rsp+21D0h+var_2170], xmm0
0x180009ec7  cmovz   rcx, rax
0x180009ecb  mov     [rsp+21D0h+var_2188], rcx
0x180009ed0  mov     rax, [rcx]
0x180009ed3  mov     rax, [rax]
0x180009ed6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009edb  test    eax, eax
0x180009edd  js      short loc_180009F4B
0x180009edf  cmp     dword ptr [rsp+21D0h+var_2170+8], 0
0x180009ee4  jz      short loc_180009F4B
0x180009ee6  mov     rcx, [r15+30h]; this
0x180009eea  mov     byte ptr [r15+238Ah], 1
0x180009ef2  call    ?GetHttpMethod@W3_REQUEST@@QEBAPEBDXZ; W3_REQUEST::GetHttpMethod(void)
0x180009ef7  mov     rcx, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x180009efe  mov     rbx, rax
0x180009f01  mov     rdi, [r13+48h]
0x180009f05  mov     rsi, [r13+340h]
0x180009f0c  mov     r14, [r13+8]
0x180009f10  mov     rdx, [rcx]
0x180009f13  mov     rax, [rdx+8]
0x180009f17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f1c  mov     r8, [r13+18h]
0x180009f20  lea     rcx, [r15+8]; struct IHttpTraceContext *
0x180009f24  mov     [rsp+21D0h+var_2198], rbx; char *
0x180009f29  mov     r9, rax; unsigned __int16 *
0x180009f2c  mov     [rsp+21D0h+var_21A0], rdi; unsigned __int16 *
0x180009f31  shr     r8, 20h; unsigned int
0x180009f35  mov     [rsp+21D0h+var_21A8], rsi; char
0x180009f3a  mov     [rsp+21D0h+var_21B0], r14; char
0x180009f3f  call    ?RaiseEvent@GENERAL_REQUEST_START@IISGeneralEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@KPEBG_K32PEBD@Z; IISGeneralEvents::GENERAL_REQUEST_START::RaiseEvent(IHttpTraceContext *,_GUID const *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort const *,char const *)
0x180009f44  lea     rsi, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180009f4b  mov     rcx, r15; this
0x180009f4e  call    ?SetupStateMachinePhase1@W3_CONTEXT@@QEAAJXZ; W3_CONTEXT::SetupStateMachinePhase1(void)
0x180009f53  mov     ebx, eax
0x180009f55  test    eax, eax
0x180009f57  js      loc_18000A5A0
0x180009f5d  mov     rdi, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x180009f64  xor     r14d, r14d
0x180009f67  mov     dword ptr [rsp+21D0h+var_2180], 0
0x180009f6f  lea     rcx, [rdi+230h]
0x180009f76  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180009f7d  nop     dword ptr [rax+rax+00h]
0x180009f82  mov     ebx, [rdi+478h]
0x180009f88  lea     rcx, [rdi+420h]
0x180009f8f  mov     r12, rax
0x180009f92  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180009f99  nop     dword ptr [rax+rax+00h]
0x180009f9e  mov     rcx, [rbp+20D0h+var_20F0]
0x180009fa2  lea     rbx, [rax+rbx*4]
0x180009fa6  mov     rax, [rcx+8]
0x180009faa  lea     rcx, [rbp+20D0h+var_20F0]
0x180009fae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fb3  mov     rdi, rax
0x180009fb6  mov     rcx, [rax]
0x180009fb9  mov     rax, [rcx+110h]
0x180009fc0  mov     rcx, rdi
0x180009fc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fc8  mov     r8, rax
0x180009fcb  mov     [rsp+21D0h+var_2178], rsi
0x180009fd0  xorps   xmm0, xmm0
0x180009fd3  lea     rdx, [rsp+21D0h+var_2178]
0x180009fd8  movdqu  [rsp+21D0h+var_2170], xmm0
0x180009fde  mov     rcx, [rax]
0x180009fe1  mov     rax, [rcx]
0x180009fe4  mov     rcx, r8
0x180009fe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fec  test    eax, eax
0x180009fee  js      short loc_180009FFB
0x180009ff0  cmp     dword ptr [rsp+21D0h+var_2170+4], 5
0x180009ff5  jnb     loc_18000A5C9
0x180009ffb  mov     eax, [rbx]
0x180009ffd  lea     r8, aModulename; "ModuleName"
0x18000a004  lea     rdx, aContextid; "ContextId"
0x18000a00b  lea     r9, aPreBeginReques_1; "PRE_BEGIN_REQUEST_START"
0x18000a012  lea     rcx, ?AreaGuid@?1??GetAreaGuid@IISRequestNotificationEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISRequestNotificationEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18000a019  cmp     eax, 0FFFFFFFFh
0x18000a01c  jz      loc_18000A3F6
0x18000a022  mov     rsi, [r12+rax*8]
0x18000a026  test    r14, r14
0x18000a029  jz      loc_18000A3DE
0x18000a02f  xor     eax, eax
0x18000a031  mov     [rbp+20D0h+var_2150], rcx
0x18000a035  mov     [rbp+20D0h+var_2114], rax
0x18000a039  xor     edi, edi
0x18000a03b  mov     [rbp+20D0h+var_210C], eax
0x18000a03e  xorps   xmm0, xmm0
0x18000a041  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18000a048  mov     [rsp+21D0h+var_2158], 100h
0x18000a051  mov     [rsp+21D0h+var_2160], rax
0x18000a056  mov     rcx, rsi
0x18000a059  mov     rax, [rsi]
0x18000a05c  mov     [rbp+20D0h+var_2148], 4
0x18000a064  mov     [rbp+20D0h+var_2140], r9
0x18000a068  mov     [rbp+20D0h+var_2138], 1
0x18000a06f  mov     rax, [rax]
0x18000a072  mov     [rbp+20D0h+var_2134], 5
0x18000a079  mov     [rbp+20D0h+var_2118], 2
0x18000a080  movdqa  [rbp+20D0h+var_2130], xmm0
0x18000a085  mov     [rbp+20D0h+var_2120], edi
0x18000a088  mov     [rbp+20D0h+var_211C], 1
0x18000a08f  mov     [rbp+20D0h+var_20D0], rdx
0x18000a093  mov     [rbp+20D0h+var_20C8], 48h ; 'H'
0x18000a09a  mov     [rbp+20D0h+var_20C0], rdi
0x18000a09e  mov     [rbp+20D0h+var_20B8], 10h
0x18000a0a5  mov     [rbp+20D0h+var_20B0], rdi
0x18000a0a9  mov     [rbp+20D0h+var_20A8], r8
0x18000a0ad  mov     [rbp+20D0h+var_20A0], 1Fh
0x18000a0b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0b9  mov     [rbp+20D0h+var_2098], rax
0x18000a0bd  mov     rcx, rax
0x18000a0c0  test    rax, rax
0x18000a0c3  jz      loc_18000A23C
0x18000a0c9  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000a0d0  cmp     [rcx+rax*2+2], di
0x18000a0d5  lea     rax, [rax+1]
0x18000a0d9  jnz     short loc_18000A0D0
0x18000a0db  lea     eax, ds:2[rax*2]
0x18000a0e2  mov     [rbp+20D0h+var_2090], eax
0x18000a0e5  lea     rdx, [rsp+21D0h+var_2160]
0x18000a0ea  lea     rax, [rbp+20D0h+var_20D0]
0x18000a0ee  mov     [rbp+20D0h+var_2088], rdi
0x18000a0f2  mov     [rbp+20D0h+var_2114+4], rax
0x18000a0f6  mov     rcx, r14
0x18000a0f9  mov     rax, [r14]
0x18000a0fc  mov     rax, [rax+10h]
0x18000a100  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a105  lea     r8, [rbp+20D0h+var_20F0]
0x18000a109  mov     edx, 100h
0x18000a10e  mov     rcx, rsi
0x18000a111  call    ?GlobalDoWork@VIRTUAL_MODULE@@QEAA?AW4GLOBAL_NOTIFICATION_STATUS@@KPEAVIHttpEventProvider@@@Z; VIRTUAL_MODULE::GlobalDoWork(ulong,IHttpEventProvider *)
0x18000a116  mov     edi, eax
0x18000a118  mov     [rsp+21D0h+var_2190], eax
0x18000a11c  xor     eax, eax
0x18000a11e  mov     [rsp+21D0h+var_2158], 100h
0x18000a127  mov     [rbp+20D0h+var_2114], rax
0x18000a12b  lea     rcx, aContextid; "ContextId"
0x18000a132  mov     [rbp+20D0h+var_210C], eax
0x18000a135  xorps   xmm0, xmm0
0x18000a138  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18000a13f  mov     [rbp+20D0h+var_20D0], rcx
0x18000a143  mov     [rsp+21D0h+var_2160], rax
0x18000a148  mov     rcx, rsi
0x18000a14b  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISRequestNotificationEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISRequestNotificationEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18000a152  mov     [rbp+20D0h+var_2148], 5
0x18000a15a  mov     [rbp+20D0h+var_2150], rax
0x18000a15e  lea     rax, aPreBeginReques_0; "PRE_BEGIN_REQUEST_END"
0x18000a165  mov     [rbp+20D0h+var_2140], rax
0x18000a169  xor     eax, eax
0x18000a16b  mov     [rbp+20D0h+var_2120], eax
0x18000a16e  mov     [rbp+20D0h+var_20C0], rax
0x18000a172  mov     [rbp+20D0h+var_20B0], rax
0x18000a176  lea     rax, aModulename; "ModuleName"
0x18000a17d  mov     [rbp+20D0h+var_20A8], rax
0x18000a181  mov     rax, [rsi]
0x18000a184  mov     [rbp+20D0h+var_2138], 1
0x18000a18b  mov     [rbp+20D0h+var_2134], 5
0x18000a192  mov     [rbp+20D0h+var_2118], 3
0x18000a199  mov     rax, [rax]
0x18000a19c  movdqa  [rbp+20D0h+var_2130], xmm0
0x18000a1a1  mov     [rbp+20D0h+var_211C], 1
0x18000a1a8  mov     [rbp+20D0h+var_20C8], 48h ; 'H'
0x18000a1af  mov     [rbp+20D0h+var_20B8], 10h
0x18000a1b6  mov     [rbp+20D0h+var_20A0], 1Fh
0x18000a1bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1c2  mov     [rbp+20D0h+var_2098], rax
0x18000a1c6  mov     rcx, rax
0x18000a1c9  test    rax, rax
0x18000a1cc  jnz     short loc_18000A243
0x18000a1ce  mov     [rbp+20D0h+var_2090], eax
0x18000a1d1  lea     rax, aNotificationst; "NotificationStatus"
0x18000a1d8  mov     [rbp+20D0h+var_2080], rax
0x18000a1dc  lea     rax, [rsp+21D0h+var_2190]
0x18000a1e1  mov     [rbp+20D0h+var_2070], rax
0x18000a1e5  mov     eax, [rsp+21D0h+var_2190]
0x18000a1e9  mov     [rbp+20D0h+var_2088], 0
0x18000a1f1  mov     [rbp+20D0h+var_2078], 13h
0x18000a1f8  mov     [rbp+20D0h+var_2068], 4
0x18000a1ff  test    eax, eax
0x18000a201  jnz     loc_18000A604
0x18000a207  lea     rax, aNotificationCo; "NOTIFICATION_CONTINUE"
0x18000a20e  mov     [rbp+20D0h+var_2060], rax
0x18000a212  lea     rdx, [rsp+21D0h+var_2160]
0x18000a217  lea     rax, [rbp+20D0h+var_20D0]
0x18000a21b  mov     rcx, r14
0x18000a21e  mov     [rbp+20D0h+var_2114+4], rax
0x18000a222  mov     rax, [r14]
0x18000a225  mov     rax, [rax+10h]
0x18000a229  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a22e  cmp     edi, 1
0x18000a231  jz      short loc_18000A268
0x18000a233  add     rbx, 4
0x18000a237  jmp     loc_180009FFB
0x18000a23c  mov     eax, edi
0x18000a23e  jmp     loc_18000A0E2
0x18000a243  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000a24a  nop     word ptr [rax+rax+00h]
0x18000a250  cmp     word ptr [rcx+rax*2+2], 0
0x18000a256  lea     rax, [rax+1]
0x18000a25a  jnz     short loc_18000A250
0x18000a25c  lea     eax, ds:2[rax*2]
0x18000a263  jmp     loc_18000A1CE
0x18000a268  mov     r14d, 1
0x18000a26e  mov     rsi, [rsp+21D0h+var_2188]
0x18000a273  lea     rdi, [r15+7D0h]
0x18000a27a  mov     rax, [rdi]
0x18000a27d  mov     dword ptr [rax+8], 1
0x18000a284  cmp     byte ptr [r15+238Ah], 0
0x18000a28c  jnz     loc_18000A61C
0x18000a292  lea     r12, [r15+8]
0x18000a296  mov     rcx, r15; this
0x18000a299  call    ?SetupStateMachinePhase2@W3_CONTEXT@@QEAAJXZ; W3_CONTEXT::SetupStateMachinePhase2(void)
0x18000a29e  mov     ebx, eax
0x18000a2a0  test    eax, eax
0x18000a2a2  js      loc_18000A43A
0x18000a2a8  mov     rax, [r15+30h]
0x18000a2ac  mov     rcx, [rax+28h]
0x18000a2b0  cmp     dword ptr [rcx+24h], 4
0x18000a2b4  jnz     loc_18000A81C
0x18000a2ba  test    r14d, r14d
0x18000a2bd  jnz     loc_18000A83C
0x18000a2c3  mov     rax, [r15]
0x18000a2c6  mov     rcx, r15
0x18000a2c9  mov     rax, [rax+70h]
0x18000a2cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2d2  test    al, 4
0x18000a2d4  jnz     short loc_18000A2EA
0x18000a2d6  mov     rax, [r15+1F98h]
0x18000a2dd  cmp     [rax+0D9h], r14b
0x18000a2e4  jz      loc_18000A846
0x18000a2ea  mov     rax, [r15+22D0h]
0x18000a2f1  mov     edx, [rax+0ECh]
0x18000a2f7  mov     rax, [r15+30h]
0x18000a2fb  mov     rcx, [rax+28h]
0x18000a2ff  mov     rax, [rcx+348h]
0x18000a306  test    dl, 8
0x18000a309  jnz     loc_18000A85D
0x18000a30f  bt      edx, 8
0x18000a313  jb      loc_18000A8A1
0x18000a319  mov     rcx, [r15+2340h]
0x18000a320  test    rcx, rcx
0x18000a323  jz      short loc_18000A33A
0x18000a325  mov     rax, [rcx]
0x18000a328  mov     rax, [rax+38h]
0x18000a32c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a331  cmp     eax, 3
0x18000a334  jnz     loc_18000A400
0x18000a33a  mov     rax, [r15]
0x18000a33d  mov     rcx, r15
0x18000a340  mov     rax, [rax+0E8h]
0x18000a347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a34c  test    rax, rax
0x18000a34f  jnz     short loc_18000A38F
0x18000a351  mov     rax, [r15+1F98h]
0x18000a358  mov     ecx, 1
0x18000a35d  lock xadd [rax+0D4h], ecx
0x18000a365  mov     rax, [r15+1F98h]
0x18000a36c  inc     ecx
0x18000a36e  mov     byte ptr [r15+1FA1h], 1
0x18000a376  cmp     byte ptr [rax+0D8h], 0
0x18000a37d  jz      loc_18000A922
0x18000a383  cmp     ecx, [rax+0D0h]
0x18000a389  ja      loc_18000A922
0x18000a38f  mov     rax, [r15]
0x18000a392  mov     rcx, r15
0x18000a395  mov     rax, [rax+0E8h]
0x18000a39c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3a1  test    rax, rax
0x18000a3a4  jnz     short loc_18000A3BA; jumptable 000000018000A9B4 case 5
0x18000a3a6  mov     rax, [r15+30h]
0x18000a3aa  mov     rcx, [rax+28h]
0x18000a3ae  mov     edx, [rcx+24h]
  ... truncated ...
```
