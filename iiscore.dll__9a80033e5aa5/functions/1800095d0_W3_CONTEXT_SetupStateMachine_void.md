# W3_CONTEXT::SetupStateMachine(void)

- ea: `0x1800095d0`
- end: `0x18000a1f0`
- name: `?SetupStateMachine@W3_CONTEXT@@QEAAXXZ`
- size: `3104`
- prototype: `void __fastcall(W3_CONTEXT *__hidden this)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x180008f10`

## callees

- `0x180008930`
- `0x1800093d0`
- `0x1800094c4`
- `0x1800095d0`
- `0x18000ad00`
- `0x18000aed0`
- `0x18000d1b8`
- `0x18000d340`
- `0x1800126d0`
- `0x180013330`
- `0x180016400`
- `0x180019558`
- `0x18001a368`
- `0x18001f29c`
- `0x18001f410`
- `0x180021718`
- `0x180021a10`
- `0x180021af8`
- `0x180021be0`
- `0x180022020`
- `0x1800343f0`
- `0x180034480`
- `0x180035010`

## import_xrefs

- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800096f6`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000970c`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800096f6`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000970c`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180009e8c`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180009ef8`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180009e8c`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180009ef8`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180009ec3`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180009f56`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180009ec3`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180009f56`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180009eae`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180009f33`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180009eae`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180009f33`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180009f25`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180009f25`

## string_xrefs

- `0x18000a06c`: `Service Unavailable`

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
  __int64 (__fastcall ***v22)(_QWORD); // rsi
  __int64 (__fastcall **v23)(_QWORD); // rax
  __int64 (__fastcall *v24)(_QWORD); // rax
  __int64 v25; // rax
  bool v26; // zf
  int v27; // eax
  int v28; // edi
  __int64 (__fastcall **v29)(_QWORD); // rax
  __int64 (__fastcall *v30)(_QWORD); // rax
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
  unsigned __int16 v63; // r9
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
      v22 = (__int64 (__fastcall ***)(_QWORD))v17[v21];
      if ( v14 )
      {
        v77 = &`IISRequestNotificationEvents::GetAreaGuid'::`2'::AreaGuid;
        memset(v86, 0, 12);
        v76 = 256;
        v75 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
        v23 = *v22;
        v78 = 4;
        v79 = L"PRE_BEGIN_REQUEST_START";
        v80 = 1;
        v24 = *v23;
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
        v28 = VIRTUAL_MODULE::GlobalDoWork(v22, 256, v89);
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
        v29 = *v22;
        v80 = 1;
        v81 = 5;
        v85 = 3;
        v30 = *v29;
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
        v28 = VIRTUAL_MODULE::GlobalDoWork(v17[v21], 256, v89);
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
0x1800095d0  push    rbp
0x1800095d2  push    rbx
0x1800095d3  push    rsi
0x1800095d4  push    rdi
0x1800095d5  push    r12
0x1800095d7  push    r13
0x1800095d9  push    r14
0x1800095db  push    r15
0x1800095dd  lea     rbp, [rsp-2098h]
0x1800095e5  mov     eax, 2198h
0x1800095ea  call    _alloca_probe
0x1800095ef  sub     rsp, rax
0x1800095f2  mov     rax, cs:__security_cookie
0x1800095f9  xor     rax, rsp
0x1800095fc  mov     [rbp+20D0h+var_50], rax
0x180009603  mov     [rbp+20D0h+var_20E8], rcx
0x180009607  lea     rax, ??_7PRE_BEGIN_PROVIDER@@6B@; const PRE_BEGIN_PROVIDER::`vftable'
0x18000960e  mov     [rbp+20D0h+var_20F0], rax
0x180009612  lea     rsi, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180009619  mov     rax, [rcx+30h]
0x18000961d  lea     rdx, [rsp+21D0h+var_2178]
0x180009622  mov     r15, rcx
0x180009625  mov     [rbp+20D0h+var_20E0], 0
0x18000962c  add     rcx, 8
0x180009630  mov     [rsp+21D0h+var_2178], rsi
0x180009635  xorps   xmm0, xmm0
0x180009638  mov     r13, [rax+28h]
0x18000963c  xor     eax, eax
0x18000963e  test    r15, r15
0x180009641  movdqu  [rsp+21D0h+var_2170], xmm0
0x180009647  cmovz   rcx, rax
0x18000964b  mov     [rsp+21D0h+var_2188], rcx
0x180009650  mov     rax, [rcx]
0x180009653  mov     rax, [rax]
0x180009656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000965b  test    eax, eax
0x18000965d  js      short loc_1800096CB
0x18000965f  cmp     dword ptr [rsp+21D0h+var_2170+8], 0
0x180009664  jz      short loc_1800096CB
0x180009666  mov     rcx, [r15+30h]; this
0x18000966a  mov     byte ptr [r15+238Ah], 1
0x180009672  call    ?GetHttpMethod@W3_REQUEST@@QEBAPEBDXZ; W3_REQUEST::GetHttpMethod(void)
0x180009677  mov     rcx, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x18000967e  mov     rbx, rax
0x180009681  mov     rdi, [r13+48h]
0x180009685  mov     rsi, [r13+340h]
0x18000968c  mov     r14, [r13+8]
0x180009690  mov     rdx, [rcx]
0x180009693  mov     rax, [rdx+8]
0x180009697  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000969c  mov     r8, [r13+18h]
0x1800096a0  lea     rcx, [r15+8]; struct IHttpTraceContext *
0x1800096a4  mov     [rsp+21D0h+var_2198], rbx; char *
0x1800096a9  mov     r9, rax; unsigned __int16 *
0x1800096ac  mov     [rsp+21D0h+var_21A0], rdi; unsigned __int16 *
0x1800096b1  shr     r8, 20h; unsigned int
0x1800096b5  mov     [rsp+21D0h+var_21A8], rsi; char
0x1800096ba  mov     [rsp+21D0h+var_21B0], r14; char
0x1800096bf  call    ?RaiseEvent@GENERAL_REQUEST_START@IISGeneralEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@KPEBG_K32PEBD@Z; IISGeneralEvents::GENERAL_REQUEST_START::RaiseEvent(IHttpTraceContext *,_GUID const *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort const *,char const *)
0x1800096c4  lea     rsi, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x1800096cb  mov     rcx, r15; this
0x1800096ce  call    ?SetupStateMachinePhase1@W3_CONTEXT@@QEAAJXZ; W3_CONTEXT::SetupStateMachinePhase1(void)
0x1800096d3  mov     ebx, eax
0x1800096d5  test    eax, eax
0x1800096d7  js      loc_180009D0F
0x1800096dd  mov     rdi, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x1800096e4  xor     r14d, r14d
0x1800096e7  mov     dword ptr [rsp+21D0h+var_2180], 0
0x1800096ef  lea     rcx, [rdi+230h]
0x1800096f6  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800096fc  mov     ebx, [rdi+478h]
0x180009702  lea     rcx, [rdi+420h]
0x180009709  mov     r12, rax
0x18000970c  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180009712  mov     rcx, [rbp+20D0h+var_20F0]
0x180009716  lea     rbx, [rax+rbx*4]
0x18000971a  mov     rax, [rcx+8]
0x18000971e  lea     rcx, [rbp+20D0h+var_20F0]
0x180009722  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009727  mov     rdi, rax
0x18000972a  mov     rcx, [rax]
0x18000972d  mov     rax, [rcx+110h]
0x180009734  mov     rcx, rdi
0x180009737  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000973c  mov     r8, rax
0x18000973f  mov     [rsp+21D0h+var_2178], rsi
0x180009744  xorps   xmm0, xmm0
0x180009747  lea     rdx, [rsp+21D0h+var_2178]
0x18000974c  movdqu  [rsp+21D0h+var_2170], xmm0
0x180009752  mov     rcx, [rax]
0x180009755  mov     rax, [rcx]
0x180009758  mov     rcx, r8
0x18000975b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009760  test    eax, eax
0x180009762  js      short loc_18000976F
0x180009764  cmp     dword ptr [rsp+21D0h+var_2170+4], 5
0x180009769  jnb     loc_180009D38
0x18000976f  mov     eax, [rbx]
0x180009771  lea     r8, aModulename; "ModuleName"
0x180009778  lea     rdx, aContextid; "ContextId"
0x18000977f  lea     r9, aPreBeginReques_1; "PRE_BEGIN_REQUEST_START"
0x180009786  lea     rcx, ?AreaGuid@?1??GetAreaGuid@IISRequestNotificationEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISRequestNotificationEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18000978d  cmp     eax, 0FFFFFFFFh
0x180009790  jz      loc_180009B65
0x180009796  mov     rsi, [r12+rax*8]
0x18000979a  test    r14, r14
0x18000979d  jz      loc_180009B4D
0x1800097a3  xor     eax, eax
0x1800097a5  mov     [rbp+20D0h+var_2150], rcx
0x1800097a9  mov     [rbp+20D0h+var_2114], rax
0x1800097ad  xor     edi, edi
0x1800097af  mov     [rbp+20D0h+var_210C], eax
0x1800097b2  xorps   xmm0, xmm0
0x1800097b5  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x1800097bc  mov     [rsp+21D0h+var_2158], 100h
0x1800097c5  mov     [rsp+21D0h+var_2160], rax
0x1800097ca  mov     rcx, rsi
0x1800097cd  mov     rax, [rsi]
0x1800097d0  mov     [rbp+20D0h+var_2148], 4
0x1800097d8  mov     [rbp+20D0h+var_2140], r9
0x1800097dc  mov     [rbp+20D0h+var_2138], 1
0x1800097e3  mov     rax, [rax]
0x1800097e6  mov     [rbp+20D0h+var_2134], 5
0x1800097ed  mov     [rbp+20D0h+var_2118], 2
0x1800097f4  movdqa  [rbp+20D0h+var_2130], xmm0
0x1800097f9  mov     [rbp+20D0h+var_2120], edi
0x1800097fc  mov     [rbp+20D0h+var_211C], 1
0x180009803  mov     [rbp+20D0h+var_20D0], rdx
0x180009807  mov     [rbp+20D0h+var_20C8], 48h ; 'H'
0x18000980e  mov     [rbp+20D0h+var_20C0], rdi
0x180009812  mov     [rbp+20D0h+var_20B8], 10h
0x180009819  mov     [rbp+20D0h+var_20B0], rdi
0x18000981d  mov     [rbp+20D0h+var_20A8], r8
0x180009821  mov     [rbp+20D0h+var_20A0], 1Fh
0x180009828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000982d  mov     [rbp+20D0h+var_2098], rax
0x180009831  mov     rcx, rax
0x180009834  test    rax, rax
0x180009837  jz      loc_1800099B0
0x18000983d  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180009844  cmp     [rcx+rax*2+2], di
0x180009849  lea     rax, [rax+1]
0x18000984d  jnz     short loc_180009844
0x18000984f  lea     eax, ds:2[rax*2]
0x180009856  mov     [rbp+20D0h+var_2090], eax
0x180009859  lea     rdx, [rsp+21D0h+var_2160]
0x18000985e  lea     rax, [rbp+20D0h+var_20D0]
0x180009862  mov     [rbp+20D0h+var_2088], rdi
0x180009866  mov     [rbp+20D0h+var_2114+4], rax
0x18000986a  mov     rcx, r14
0x18000986d  mov     rax, [r14]
0x180009870  mov     rax, [rax+10h]
0x180009874  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009879  lea     r8, [rbp+20D0h+var_20F0]
0x18000987d  mov     edx, 100h
0x180009882  mov     rcx, rsi
0x180009885  call    ?GlobalDoWork@VIRTUAL_MODULE@@QEAA?AW4GLOBAL_NOTIFICATION_STATUS@@KPEAVIHttpEventProvider@@@Z; VIRTUAL_MODULE::GlobalDoWork(ulong,IHttpEventProvider *)
0x18000988a  mov     edi, eax
0x18000988c  mov     [rsp+21D0h+var_2190], eax
0x180009890  xor     eax, eax
0x180009892  mov     [rsp+21D0h+var_2158], 100h
0x18000989b  mov     [rbp+20D0h+var_2114], rax
0x18000989f  lea     rcx, aContextid; "ContextId"
0x1800098a6  mov     [rbp+20D0h+var_210C], eax
0x1800098a9  xorps   xmm0, xmm0
0x1800098ac  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x1800098b3  mov     [rbp+20D0h+var_20D0], rcx
0x1800098b7  mov     [rsp+21D0h+var_2160], rax
0x1800098bc  mov     rcx, rsi
0x1800098bf  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISRequestNotificationEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISRequestNotificationEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x1800098c6  mov     [rbp+20D0h+var_2148], 5
0x1800098ce  mov     [rbp+20D0h+var_2150], rax
0x1800098d2  lea     rax, aPreBeginReques_0; "PRE_BEGIN_REQUEST_END"
0x1800098d9  mov     [rbp+20D0h+var_2140], rax
0x1800098dd  xor     eax, eax
0x1800098df  mov     [rbp+20D0h+var_2120], eax
0x1800098e2  mov     [rbp+20D0h+var_20C0], rax
0x1800098e6  mov     [rbp+20D0h+var_20B0], rax
0x1800098ea  lea     rax, aModulename; "ModuleName"
0x1800098f1  mov     [rbp+20D0h+var_20A8], rax
0x1800098f5  mov     rax, [rsi]
0x1800098f8  mov     [rbp+20D0h+var_2138], 1
0x1800098ff  mov     [rbp+20D0h+var_2134], 5
0x180009906  mov     [rbp+20D0h+var_2118], 3
0x18000990d  mov     rax, [rax]
0x180009910  movdqa  [rbp+20D0h+var_2130], xmm0
0x180009915  mov     [rbp+20D0h+var_211C], 1
0x18000991c  mov     [rbp+20D0h+var_20C8], 48h ; 'H'
0x180009923  mov     [rbp+20D0h+var_20B8], 10h
0x18000992a  mov     [rbp+20D0h+var_20A0], 1Fh
0x180009931  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009936  mov     [rbp+20D0h+var_2098], rax
0x18000993a  mov     rcx, rax
0x18000993d  test    rax, rax
0x180009940  jnz     short loc_1800099B7
0x180009942  mov     [rbp+20D0h+var_2090], eax
0x180009945  lea     rax, aNotificationst; "NotificationStatus"
0x18000994c  mov     [rbp+20D0h+var_2080], rax
0x180009950  lea     rax, [rsp+21D0h+var_2190]
0x180009955  mov     [rbp+20D0h+var_2070], rax
0x180009959  mov     eax, [rsp+21D0h+var_2190]
0x18000995d  mov     [rbp+20D0h+var_2088], 0
0x180009965  mov     [rbp+20D0h+var_2078], 13h
0x18000996c  mov     [rbp+20D0h+var_2068], 4
0x180009973  test    eax, eax
0x180009975  jnz     loc_180009D73
0x18000997b  lea     rax, aNotificationCo; "NOTIFICATION_CONTINUE"
0x180009982  mov     [rbp+20D0h+var_2060], rax
0x180009986  lea     rdx, [rsp+21D0h+var_2160]
0x18000998b  lea     rax, [rbp+20D0h+var_20D0]
0x18000998f  mov     rcx, r14
0x180009992  mov     [rbp+20D0h+var_2114+4], rax
0x180009996  mov     rax, [r14]
0x180009999  mov     rax, [rax+10h]
0x18000999d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099a2  cmp     edi, 1
0x1800099a5  jz      short loc_1800099D8
0x1800099a7  add     rbx, 4
0x1800099ab  jmp     loc_18000976F
0x1800099b0  mov     eax, edi
0x1800099b2  jmp     loc_180009856
0x1800099b7  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800099be  xchg    ax, ax
0x1800099c0  cmp     word ptr [rcx+rax*2+2], 0
0x1800099c6  lea     rax, [rax+1]
0x1800099ca  jnz     short loc_1800099C0
0x1800099cc  lea     eax, ds:2[rax*2]
0x1800099d3  jmp     loc_180009942
0x1800099d8  mov     r14d, 1
0x1800099de  mov     rsi, [rsp+21D0h+var_2188]
0x1800099e3  lea     rdi, [r15+7D0h]
0x1800099ea  mov     rax, [rdi]
0x1800099ed  mov     dword ptr [rax+8], 1
0x1800099f4  cmp     byte ptr [r15+238Ah], 0
0x1800099fc  jnz     loc_180009D8B
0x180009a02  lea     r12, [r15+8]
0x180009a06  mov     rcx, r15; this
0x180009a09  call    ?SetupStateMachinePhase2@W3_CONTEXT@@QEAAJXZ; W3_CONTEXT::SetupStateMachinePhase2(void)
0x180009a0e  mov     ebx, eax
0x180009a10  test    eax, eax
0x180009a12  js      loc_180009BA9
0x180009a18  mov     rax, [r15+30h]
0x180009a1c  mov     rcx, [rax+28h]
0x180009a20  cmp     dword ptr [rcx+24h], 4
0x180009a24  jnz     loc_180009F61
0x180009a2a  test    r14d, r14d
0x180009a2d  jnz     loc_180009F81
0x180009a33  mov     rax, [r15]
0x180009a36  mov     rcx, r15
0x180009a39  mov     rax, [rax+70h]
0x180009a3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a42  test    al, 4
0x180009a44  jnz     short loc_180009A5A
0x180009a46  mov     rax, [r15+1F98h]
0x180009a4d  cmp     [rax+0D9h], r14b
0x180009a54  jz      loc_180009F8B
0x180009a5a  mov     rax, [r15+22D0h]
0x180009a61  mov     edx, [rax+0ECh]
0x180009a67  mov     rax, [r15+30h]
0x180009a6b  mov     rcx, [rax+28h]
0x180009a6f  mov     rax, [rcx+348h]
0x180009a76  test    dl, 8
0x180009a79  jnz     loc_180009FA2
0x180009a7f  bt      edx, 8
0x180009a83  jb      loc_180009FE6
0x180009a89  mov     rcx, [r15+2340h]
0x180009a90  test    rcx, rcx
0x180009a93  jz      short loc_180009AAA
0x180009a95  mov     rax, [rcx]
0x180009a98  mov     rax, [rax+38h]
0x180009a9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009aa1  cmp     eax, 3
0x180009aa4  jnz     loc_180009B6F
0x180009aaa  mov     rax, [r15]
0x180009aad  mov     rcx, r15
0x180009ab0  mov     rax, [rax+0E8h]
0x180009ab7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009abc  test    rax, rax
0x180009abf  jnz     short loc_180009AFF
0x180009ac1  mov     rax, [r15+1F98h]
0x180009ac8  mov     ecx, 1
0x180009acd  lock xadd [rax+0D4h], ecx
0x180009ad5  mov     rax, [r15+1F98h]
0x180009adc  inc     ecx
0x180009ade  mov     byte ptr [r15+1FA1h], 1
0x180009ae6  cmp     byte ptr [rax+0D8h], 0
0x180009aed  jz      loc_18000A067
0x180009af3  cmp     ecx, [rax+0D0h]
0x180009af9  ja      loc_18000A067
0x180009aff  mov     rax, [r15]
0x180009b02  mov     rcx, r15
0x180009b05  mov     rax, [rax+0E8h]
0x180009b0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b11  test    rax, rax
0x180009b14  jnz     short loc_180009B2A; jumptable 000000018000A0F9 case 5
0x180009b16  mov     rax, [r15+30h]
0x180009b1a  mov     rcx, [rax+28h]
0x180009b1e  mov     edx, [rcx+24h]
0x180009b21  cmp     edx, 4
0x180009b24  jnz     loc_18000A0CB
  ... truncated ...
```
