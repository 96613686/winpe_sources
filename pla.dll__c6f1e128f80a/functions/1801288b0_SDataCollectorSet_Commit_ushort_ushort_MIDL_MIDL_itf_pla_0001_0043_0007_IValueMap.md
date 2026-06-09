# SDataCollectorSet::Commit(ushort *,ushort *,__MIDL___MIDL_itf_pla_0001_0043_0007,IValueMap * *)

- ea: `0x1801288b0`
- end: `0x180129adf`
- name: `?Commit@SDataCollectorSet@@UEAAJPEAG0W4__MIDL___MIDL_itf_pla_0001_0043_0007@@PEAPEAUIValueMap@@@Z`
- size: `4655`
- prototype: `__int64 __fastcall(SDataCollectorSet *__hidden this, unsigned __int16 *, unsigned __int16 *, enum __MIDL___MIDL_itf_pla_0001_0043_0007, struct IValueMap **)`
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800106d0`
- `0x180012ef0`
- `0x180018420`
- `0x1800198b0`
- `0x18002b3a0`
- `0x180034dc4`
- `0x180056ca0`
- `0x1800a2908`
- `0x1800d8af4`
- `0x1800e5f20`
- `0x1800e9cf0`
- `0x1800edc58`
- `0x1800f1dec`
- `0x180104334`
- `0x1801288b0`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801290bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012915c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801290bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012915c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801299df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801299df`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801289ca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801289ca`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1801291ed`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1801291ed`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18012914e`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18012914e`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x1801290ad`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x1801290ad`

## string_xrefs

- `0x180128987`: `SDataCollectorSet::Commit`
- `0x180128a94`: `SDataCollectorSet::Commit`
- `0x180128ba3`: `SDataCollectorSet::Commit`
- `0x180128d33`: `SDataCollectorSet::Commit`
- `0x1801298a7`: `SDataCollectorSet::Commit`

## pseudocode

```c
__int64 __fastcall SDataCollectorSet::Commit(
        SDataCollectorSet *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        enum __MIDL___MIDL_itf_pla_0001_0043_0007 a4,
        struct IValueMap **a5)
{
  unsigned __int16 *v7; // r12
  int v9; // eax
  unsigned __int64 v10; // rdx
  __int64 v11; // rsi
  int v12; // ebx
  __int64 v13; // rax
  int ExistingTask; // eax
  __int64 v15; // rax
  int v16; // ecx
  __int64 v17; // rax
  __int64 v18; // rax
  enum _TASK_LOGON_TYPE v19; // edi
  int Task; // eax
  __int64 v21; // rax
  int v22; // eax
  __int64 v23; // rax
  int v24; // eax
  __int64 v25; // rax
  int v26; // eax
  __int64 v27; // rax
  __int64 v28; // rax
  const WCHAR *v29; // rax
  DWORD LastError; // eax
  int v31; // eax
  __int64 v32; // rax
  DWORD v33; // eax
  int v34; // eax
  __int64 v35; // rax
  __int64 v36; // rax
  const char *v37; // rdx
  int v38; // r8d
  __int64 v39; // rax
  int v40; // eax
  __int64 v41; // rax
  const char *v42; // rdx
  int v43; // r8d
  __int64 v44; // rax
  int v45; // eax
  __int64 v46; // rax
  int v47; // eax
  __int64 v48; // rax
  int v49; // eax
  __int64 v50; // rax
  int v51; // eax
  __int64 v52; // rax
  unsigned __int16 *v53; // rdx
  int v54; // eax
  __int64 v55; // rax
  int IsEqualSddl; // eax
  __int64 v57; // rax
  unsigned __int16 *v58; // r9
  int v59; // eax
  __int64 v60; // rax
  __int64 v61; // rax
  __int64 v62; // rdx
  __int64 v63; // rax
  __int64 v64; // rcx
  __int64 v65; // rax
  __int64 v66; // rdx
  __int64 v67; // rax
  __int64 v68; // rcx
  struct IValueMap *v69; // rcx
  BSTR v70; // rax
  __int64 i; // rcx
  int ReferencedDomainName; // [rsp+20h] [rbp-E0h]
  struct IRegisteredTask **v74; // [rsp+38h] [rbp-C8h]
  __int64 v75; // [rsp+40h] [rbp-C0h]
  __int64 v76; // [rsp+48h] [rbp-B8h]
  __int64 v77; // [rsp+50h] [rbp-B0h]
  int v78; // [rsp+70h] [rbp-90h] BYREF
  int v79; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v80; // [rsp+80h] [rbp-80h]
  int v81; // [rsp+88h] [rbp-78h]
  LPCWSTR lpAccountName; // [rsp+90h] [rbp-70h] BYREF
  BSTR v83; // [rsp+98h] [rbp-68h] BYREF
  struct ITaskDefinition *v84; // [rsp+A0h] [rbp-60h] BYREF
  BSTR bstrString; // [rsp+A8h] [rbp-58h] BYREF
  BSTR v86; // [rsp+B0h] [rbp-50h] BYREF
  DWORD cbSid; // [rsp+B8h] [rbp-48h] BYREF
  SDataCollectorSet *v88; // [rsp+C0h] [rbp-40h]
  struct IValueMap *v89; // [rsp+C8h] [rbp-38h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+D0h] [rbp-30h] BYREF
  DWORD cchReferencedDomainName; // [rsp+D4h] [rbp-2Ch] BYREF
  struct IRegisteredTask *v92; // [rsp+D8h] [rbp-28h] BYREF
  LPCVOID lpMem; // [rsp+E0h] [rbp-20h]
  SDataCollectorSet *v94; // [rsp+E8h] [rbp-18h] BYREF
  struct IValueMap **v95; // [rsp+F0h] [rbp-10h]
  unsigned __int16 v96[64]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 v97[64]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE Sid[80]; // [rsp+200h] [rbp+100h] BYREF
  _BYTE pSid[80]; // [rsp+250h] [rbp+150h] BYREF
  unsigned __int16 v100[64]; // [rsp+2A0h] [rbp+1A0h] BYREF
  unsigned __int16 v101[64]; // [rsp+320h] [rbp+220h] BYREF
  unsigned __int16 v102[64]; // [rsp+3A0h] [rbp+2A0h] BYREF
  unsigned __int16 v103[64]; // [rsp+420h] [rbp+320h] BYREF
  unsigned __int16 v104[64]; // [rsp+4A0h] [rbp+3A0h] BYREF
  unsigned __int16 v105[64]; // [rsp+520h] [rbp+420h] BYREF
  unsigned __int16 v106[64]; // [rsp+5A0h] [rbp+4A0h] BYREF
  unsigned __int16 v107[64]; // [rsp+620h] [rbp+520h] BYREF
  unsigned __int16 v108[64]; // [rsp+6A0h] [rbp+5A0h] BYREF
  unsigned __int16 v109[64]; // [rsp+720h] [rbp+620h] BYREF
  unsigned __int16 v110[64]; // [rsp+7A0h] [rbp+6A0h] BYREF
  unsigned __int16 v111[64]; // [rsp+820h] [rbp+720h] BYREF
  unsigned __int16 v112[64]; // [rsp+8A0h] [rbp+7A0h] BYREF
  unsigned __int16 v113[64]; // [rsp+920h] [rbp+820h] BYREF
  unsigned __int16 v114[64]; // [rsp+9A0h] [rbp+8A0h] BYREF
  unsigned __int16 v115[64]; // [rsp+A20h] [rbp+920h] BYREF
  unsigned __int16 v116[64]; // [rsp+AA0h] [rbp+9A0h] BYREF
  unsigned __int16 v117[64]; // [rsp+B20h] [rbp+A20h] BYREF
  unsigned __int16 v118[64]; // [rsp+BA0h] [rbp+AA0h] BYREF
  unsigned __int16 v119[64]; // [rsp+C20h] [rbp+B20h] BYREF
  unsigned __int16 v120[64]; // [rsp+CA0h] [rbp+BA0h] BYREF
  unsigned __int16 v121[64]; // [rsp+D20h] [rbp+C20h] BYREF

  v95 = a5;
  v7 = a2;
  v79 = *((_DWORD *)this + 14);
  v80 = a2;
  v88 = this;
  v81 = 0;
  v84 = 0;
  lpAccountName = 0;
  v83 = 0;
  bstrString = 0;
  v86 = 0;
  lpMem = 0;
  v89 = 0;
  v92 = 0;
  v78 = 0;
  cbSid = 68;
  cchReferencedDomainName = 260;
  peUse = 0;
  v94 = this;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000400LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000400LL) )
  {
    EventingWriteEvent(&g_Eventing, PLA_EVENT_METHOD, 3, "SDataCollectorSet::Commit", 26, &v94, 8, &v79, 4, v76, v77);
  }
  if ( *((_DWORD *)this + 2) )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v9 = DataCollectorSet::Commit(this, v7, a3, a4, &v89);
  v11 = -1;
  v12 = v9;
  if ( v9 < 0 )
  {
    v79 = 0;
    v78 = v9;
    if ( (_DWORD)xmmword_180169738 )
    {
      v10 = 0x4000000000000800LL;
      if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v100, 0x4000000000000800uLL);
        v13 = -1;
        do
          ++v13;
        while ( v100[v13] );
LABEL_13:
        EventingWriteEvent(
          &g_Eventing,
          PLA_EVENT_ERROR,
          5,
          &v78,
          4,
          qword_180147320,
          1,
          &v79,
          4,
          "SDataCollectorSet::Commit",
          26);
        goto LABEL_41;
      }
    }
    goto LABEL_41;
  }
  ExistingTask = PlaTaskService::GetExistingTask((SDataCollectorSet *)((char *)this + 272), v7, &v84, &v92);
  v10 = 0;
  v12 = ExistingTask;
  if ( ExistingTask < 0 )
  {
    if ( ExistingTask != -2144337918 )
    {
      v79 = 0;
      v78 = ExistingTask;
      if ( (_DWORD)xmmword_180169738 )
      {
        v10 = 0x4000000000000800LL;
        if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v102, 0x4000000000000800uLL);
          v17 = -1;
          do
            ++v17;
          while ( v102[v17] );
          goto LABEL_13;
        }
      }
LABEL_41:
      if ( (a4 & 0x1000) != 0 )
        goto LABEL_208;
      goto LABEL_184;
    }
    v81 = 0;
    v16 = 0;
    if ( (a4 & 0xF) == 2 )
    {
      v12 = -2144337918;
      v79 = 0;
      v78 = -2144337918;
      if ( (_DWORD)xmmword_180169738 )
      {
        v10 = 0x4000000000000800LL;
        if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v103, 0x4000000000000800uLL);
          v18 = -1;
          do
            ++v18;
          while ( v103[v18] );
          EventingWriteEvent(
            &g_Eventing,
            PLA_EVENT_ERROR,
            5,
            &v78,
            4,
            qword_180147320,
            1,
            &v79,
            4,
            "SDataCollectorSet::Commit",
            26);
        }
      }
      v81 = 0;
      goto LABEL_41;
    }
  }
  else
  {
    if ( (a4 & 0xF) == 1 )
    {
      v12 = -2144337737;
      v78 = -2144337737;
      v79 = 0;
      if ( (_DWORD)xmmword_180169738 )
      {
        v10 = 0x4000000000000800LL;
        if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v101, 0x4000000000000800uLL);
          v15 = -1;
          do
            ++v15;
          while ( v101[v15] );
          EventingWriteEvent(
            &g_Eventing,
            PLA_EVENT_ERROR,
            5,
            &v78,
            4,
            qword_180147320,
            1,
            &v79,
            4,
            "SDataCollectorSet::Commit",
            26);
        }
      }
      v81 = 1;
      goto LABEL_41;
    }
    v16 = 1;
    v81 = 1;
  }
  if ( (a4 & 0x1000) != 0 )
  {
    v12 = 0;
    goto LABEL_208;
  }
  v19 = TASK_LOGON_NONE;
  if ( v16 )
    goto LABEL_58;
  Task = PlaTaskService::GetTask((SDataCollectorSet *)((char *)this + 272), &v84);
  v12 = Task;
  if ( Task >= 0 )
  {
    v22 = PlaiSetTaskSettings(v84, v7);
    v12 = v22;
    if ( v22 < 0 )
    {
      v79 = 0;
      v78 = v22;
      if ( (_DWORD)xmmword_180169738 )
      {
        v10 = 0x4000000000000800LL;
        if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v105, 0x4000000000000800uLL);
          v23 = -1;
          do
            ++v23;
          while ( v105[v23] );
          goto LABEL_183;
        }
      }
      goto LABEL_185;
    }
LABEL_58:
    v24 = SDataCollectorSet::CommitTriggers(this, v84);
    v12 = v24;
    if ( v24 < 0 )
    {
      v79 = 0;
      v78 = v24;
      if ( (_DWORD)xmmword_180169738 )
      {
        v10 = 0x4000000000000800LL;
        if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v106, 0x4000000000000800uLL);
          v25 = -1;
          do
            ++v25;
          while ( v106[v25] );
          goto LABEL_183;
        }
      }
      goto LABEL_185;
    }
    v26 = (*(__int64 (__fastcall **)(SDataCollectorSet *, LPCWSTR *))(*(_QWORD *)this + 408LL))(this, &lpAccountName);
    v12 = v26;
    if ( v26 < 0 )
    {
      v79 = 0;
      v78 = v26;
      if ( (_DWORD)xmmword_180169738 )
      {
        v10 = 0x4000000000000800LL;
        if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v107, 0x4000000000000800uLL);
          v27 = -1;
          do
            ++v27;
          while ( v107[v27] );
          goto LABEL_183;
        }
      }
      goto LABEL_185;
    }
    if ( *((_DWORD *)v88 + 60) )
    {
      if ( !lpAccountName || !*lpAccountName )
      {
        PlaiFreeString((BSTR)lpAccountName);
        lpAccountName = 0;
        v29 = PlaiAllocStringEx(L"System", v42, v43);
        lpAccountName = v29;
        if ( !v29 )
        {
          v12 = -2147024882;
          v78 = -2147024882;
          v79 = 0;
          if ( !(_DWORD)xmmword_180169738 )
            goto LABEL_184;
          v10 = 0x4000000000000800LL;
          if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_184;
          }
          PlaiWhoAmI(v114, 0x4000000000000800uLL);
          v44 = -1;
          do
            ++v44;
          while ( v114[v44] );
          goto LABEL_183;
        }
        v19 = TASK_LOGON_SERVICE_ACCOUNT;
        goto LABEL_130;
      }
      v19 = TASK_LOGON_PASSWORD;
      v40 = (*(__int64 (__fastcall **)(SDataCollectorSet *, BSTR *))(*(_QWORD *)v88 + 576LL))(v88, &v86);
      v12 = v40;
      if ( v40 < 0 )
      {
        v78 = v40;
        v79 = 0;
        if ( !(_DWORD)xmmword_180169738 )
          goto LABEL_184;
        v10 = 0x4000000000000800LL;
        if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_184;
        }
        PlaiWhoAmI(v113, 0x4000000000000800uLL);
        v41 = -1;
        do
          ++v41;
        while ( v113[v41] );
        goto LABEL_183;
      }
    }
    else
    {
      if ( !v81 )
      {
        v19 = TASK_LOGON_SERVICE_ACCOUNT;
        PlaiFreeString((BSTR)lpAccountName);
        lpAccountName = 0;
        v29 = PlaiAllocStringEx(L"System", v37, v38);
        lpAccountName = v29;
        if ( !v29 )
        {
          v12 = -2147024882;
          v79 = 0;
          v78 = -2147024882;
          if ( !(_DWORD)xmmword_180169738 )
            goto LABEL_184;
          v10 = 0x4000000000000800LL;
          if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_184;
          }
          PlaiWhoAmI(v112, 0x4000000000000800uLL);
          v39 = -1;
          do
            ++v39;
          while ( v112[v39] );
          goto LABEL_183;
        }
        goto LABEL_130;
      }
      lpMem = PlaiAlloc(0x208u, 1, 0, qword_180147320, ReferencedDomainName);
      if ( !lpMem )
      {
        v12 = -2147024882;
        v78 = -2147024882;
        v79 = 0;
        if ( !(_DWORD)xmmword_180169738 )
          goto LABEL_184;
        v10 = 0x4000000000000800LL;
        if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_184;
        }
        PlaiWhoAmI(v108, 0x4000000000000800uLL);
        v28 = -1;
        do
          ++v28;
        while ( v108[v28] );
        goto LABEL_183;
      }
      v29 = lpAccountName;
      if ( !lpAccountName )
      {
LABEL_130:
        v45 = PlaiSetTaskRunLevel(v84, v19, v29, v86);
        v12 = v45;
        if ( v45 < 0 )
        {
          v78 = v45;
          v79 = 0;
          if ( !(_DWORD)xmmword_180169738 )
            goto LABEL_184;
          v10 = 0x4000000000000800LL;
          if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_184;
          }
          PlaiWhoAmI(v115, 0x4000000000000800uLL);
          v46 = -1;
          do
            ++v46;
          while ( v115[v46] );
          goto LABEL_183;
        }
        PlaiFreeString(bstrString);
        bstrString = 0;
        v47 = (*(__int64 (__fastcall **)(SDataCollectorSet *, BSTR *))(*(_QWORD *)v88 + 416LL))(v88, &bstrString);
        v12 = v47;
        if ( v47 < 0 )
        {
          v78 = v47;
          v79 = 0;
          if ( !(_DWORD)xmmword_180169738 )
            goto LABEL_184;
          v10 = 0x4000000000000800LL;
          if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_184;
          }
          PlaiWhoAmI(v116, 0x4000000000000800uLL);
          v48 = -1;
          do
            ++v48;
          while ( v116[v48] );
          goto LABEL_183;
        }
        v49 = ((__int64 (__fastcall *)(struct ITaskDefinition *, BSTR))v84->lpVtbl->put_Data)(v84, bstrString);
        v12 = v49;
        if ( v49 < 0 )
        {
          v78 = v49;
          v79 = 0;
          if ( !(_DWORD)xmmword_180169738 )
            goto LABEL_184;
          v10 = 0x4000000000000800LL;
          if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_184;
          }
          PlaiWhoAmI(v117, 0x4000000000000800uLL);
          v50 = -1;
          do
            ++v50;
          while ( v117[v50] );
          goto LABEL_183;
        }
        v51 = (*(__int64 (__fastcall **)(SDataCollectorSet *, BSTR *))(*(_QWORD *)v88 + 424LL))(v88, &v83);
        v12 = v51;
        if ( v51 < 0 )
        {
          v78 = v51;
          v79 = 0;
          if ( !(_DWORD)xmmword_180169738 )
            goto LABEL_184;
          v10 = 0x4000000000000800LL;
          if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_184;
          }
          PlaiWhoAmI(v118, 0x4000000000000800uLL);
          v52 = -1;
          do
            ++v52;
          while ( v118[v52] );
          goto LABEL_183;
        }
        v53 = v83;
        if ( !v83 )
        {
          v54 = PlaiCreateSddl(1u, &v83);
          v12 = v54;
          if ( v54 < 0 )
          {
            v78 = v54;
            v79 = 0;
            if ( !(_DWORD)xmmword_180169738 )
              goto LABEL_184;
            v10 = 0x4000000000000800LL;
            if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
            {
              goto LABEL_184;
            }
            PlaiWhoAmI(v119, 0x4000000000000800uLL);
            v55 = -1;
            do
              ++v55;
            while ( v119[v55] );
            goto LABEL_183;
          }
          v53 = v83;
        }
        IsEqualSddl = PlaiIsEqualSddl(v92, v53, &v78);
        v12 = IsEqualSddl;
        if ( IsEqualSddl >= 0 )
        {
          if ( v78 )
          {
            PlaiFreeString(v83);
            v58 = 0;
            v83 = 0;
          }
          else
          {
            v58 = v83;
          }
          v59 = PlaTaskService::Save(
                  (__int64 **)this + 34,
                  v84,
                  v80,
                  v58,
                  (unsigned __int16 *)lpAccountName,
                  v86,
                  v19,
                  0);
          v12 = v59;
          if ( v59 >= 0 )
            goto LABEL_184;
          v79 = 0;
          v78 = v59;
          if ( !(_DWORD)xmmword_180169738 )
            goto LABEL_184;
          v10 = 0x4000000000000800LL;
          if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_184;
          }
          PlaiWhoAmI(v121, 0x4000000000000800uLL);
          v60 = -1;
          do
            ++v60;
          while ( v121[v60] );
        }
        else
        {
          v78 = IsEqualSddl;
          v79 = 0;
          if ( !(_DWORD)xmmword_180169738 )
            goto LABEL_184;
          v10 = 0x4000000000000800LL;
          if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_184;
          }
          PlaiWhoAmI(v120, 0x4000000000000800uLL);
          v57 = -1;
          do
            ++v57;
          while ( v120[v57] );
        }
LABEL_183:
        EventingWriteEvent(
          &g_Eventing,
          PLA_EVENT_ERROR,
          5,
          &v78,
          4,
          qword_180147320,
          1,
          &v79,
          4,
          "SDataCollectorSet::Commit",
          26);
LABEL_184:
        v7 = v80;
        goto LABEL_185;
      }
      if ( !LookupAccountNameW(0, lpAccountName, Sid, &cbSid, (LPWSTR)lpMem, &cchReferencedDomainName, &peUse) )
      {
        LastError = GetLastError();
        v31 = PlaiHResultFromWin32(LastError);
        v12 = v31;
        if ( v31 < 0 )
        {
          v79 = 0;
          v78 = v31;
          if ( !(_DWORD)xmmword_180169738 )
            goto LABEL_184;
          v10 = 0x4000000000000800LL;
          if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_184;
          }
          PlaiWhoAmI(v109, 0x4000000000000800uLL);
          v32 = -1;
          do
            ++v32;
          while ( v109[v32] );
          goto LABEL_183;
        }
      }
      if ( !CreateWellKnownSid(WinLocalSystemSid, 0, pSid, &cbSid) )
      {
        v33 = GetLastError();
        v34 = PlaiHResultFromWin32(v33);
        v12 = v34;
        if ( v34 < 0 )
        {
          v79 = 0;
          v78 = v34;
          if ( !(_DWORD)xmmword_180169738 )
            goto LABEL_184;
          v10 = 0x4000000000000800LL;
          if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_184;
          }
          PlaiWhoAmI(v110, 0x4000000000000800uLL);
          v35 = -1;
          do
            ++v35;
          while ( v110[v35] );
          goto LABEL_183;
        }
      }
      if ( !EqualSid(pSid, Sid) )
      {
        v12 = -2144337661;
        v78 = -2144337661;
        v79 = 0;
        if ( !(_DWORD)xmmword_180169738 )
          goto LABEL_184;
        v10 = 0x4000000000000800LL;
        if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_184;
        }
        PlaiWhoAmI(v111, 0x4000000000000800uLL);
        v36 = -1;
        do
          ++v36;
        while ( v111[v36] );
        goto LABEL_183;
      }
    }
    v29 = lpAccountName;
    goto LABEL_130;
  }
  v79 = 0;
  v78 = Task;
  if ( (_DWORD)xmmword_180169738 )
  {
    v10 = 0x4000000000000800LL;
    if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v104, 0x4000000000000800uLL);
      v21 = -1;
      do
        ++v21;
      while ( v104[v21] );
      goto LABEL_183;
    }
  }
LABEL_185:
  if ( v81 )
  {
    if ( v12 >= 0 )
    {
      if ( (int)PlaiWhoAmI(v96, v10) < 0 )
        v96[0] = 0;
      v61 = -1;
      do
        ++v61;
      while ( v96[v61] );
      v62 = (unsigned int)(2 * v61) + 2LL;
      if ( v7 )
      {
        v63 = -1;
        do
          ++v63;
        while ( v7[v63] );
        v64 = (unsigned int)(2 * v63) + 2LL;
      }
      else
      {
        v64 = 0;
      }
      EventingWriteEvent(&g_Eventing, PLA_EVENTLOG_DCS_EDIT, 2, v7, v64, v96, v62, v74, v75, v76, v77);
    }
  }
  else if ( v12 >= 0 )
  {
    if ( (int)PlaiWhoAmI(v97, v10) < 0 )
      v97[0] = 0;
    v65 = -1;
    do
      ++v65;
    while ( v97[v65] );
    v66 = (unsigned int)(2 * v65) + 2LL;
    if ( v7 )
    {
      v67 = -1;
      do
        ++v67;
      while ( v7[v67] );
      v68 = (unsigned int)(2 * v67) + 2LL;
    }
    else
    {
      v68 = 0;
    }
    EventingWriteEvent(&g_Eventing, PLA_EVENTLOG_DCS_CREATE, 2, v7, v68, v97, v66, v74, v75, v76, v77);
  }
LABEL_208:
  if ( *((_DWORD *)v88 + 2) )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v88 + 16));
  if ( v12 >= 0 && v95 )
  {
    v69 = v89;
    *v95 = v89;
    ((void (__fastcall *)(struct IValueMap *, unsigned __int64))v69->lpVtbl->AddRef)(v69, v10);
  }
  v70 = v86;
  if ( v86 )
  {
    do
      ++v11;
    while ( v86[v11] );
    for ( i = 2 * v11; i; --i )
    {
      *(_BYTE *)v70 = 0;
      v70 = (BSTR)((char *)v70 + 1);
    }
  }
  if ( lpMem )
    PlaiFree(lpMem, 1);
  PlaiFreeString(bstrString);
  bstrString = 0;
  PlaiFreeString((BSTR)lpAccountName);
  lpAccountName = 0;
  PlaiFreeString(v83);
  v83 = 0;
  PlaiFreeString(v86);
  v86 = 0;
  if ( v84 )
  {
    ((void (__fastcall *)(struct ITaskDefinition *))v84->lpVtbl->Release)(v84);
    v84 = 0;
  }
  if ( v89 )
  {
    ((void (__fastcall *)(struct IValueMap *))v89->lpVtbl->Release)(v89);
    v89 = 0;
  }
  if ( v92 )
    ((void (__fastcall *)(struct IRegisteredTask *))v92->lpVtbl->Release)(v92);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1801288b0  push    rbp
0x1801288b2  push    rbx
0x1801288b3  push    rsi
0x1801288b4  push    rdi
0x1801288b5  push    r12
0x1801288b7  push    r13
0x1801288b9  push    r14
0x1801288bb  push    r15
0x1801288bd  lea     rbp, [rsp-0CB8h]
0x1801288c5  sub     rsp, 0DB8h
0x1801288cc  mov     rax, cs:__security_cookie
0x1801288d3  xor     rax, rsp
0x1801288d6  mov     [rbp+0CF0h+var_50], rax
0x1801288dd  mov     rax, [rbp+0CF0h+arg_20]
0x1801288e4  xor     r14d, r14d
0x1801288e7  cmp     dword ptr cs:xmmword_180169738, r14d
0x1801288ee  mov     edi, r9d
0x1801288f1  mov     [rbp+0CF0h+var_D00], rax
0x1801288f5  mov     rbx, r8
0x1801288f8  mov     eax, [rcx+38h]
0x1801288fb  mov     r12, rdx
0x1801288fe  mov     [rsp+0DF0h+var_D78], eax
0x180128902  mov     r15, rcx
0x180128905  mov     [rbp+0CF0h+var_D70], rdx
0x180128909  mov     [rbp+0CF0h+var_D30], rcx
0x18012890d  mov     [rbp+0CF0h+var_D68], r14d
0x180128911  mov     [rbp+0CF0h+var_D50], r14
0x180128915  mov     [rbp+0CF0h+lpAccountName], r14
0x180128919  mov     [rbp+0CF0h+var_D58], r14
0x18012891d  mov     [rbp+0CF0h+bstrString], r14
0x180128921  mov     [rbp+0CF0h+var_D40], r14
0x180128925  mov     [rbp+0CF0h+lpMem], r14
0x180128929  mov     [rbp+0CF0h+var_D28], r14
0x18012892d  mov     [rbp+0CF0h+var_D18], r14
0x180128931  mov     [rsp+0DF0h+var_D80], r14d
0x180128936  mov     [rbp+0CF0h+cbSid], 44h ; 'D'
0x18012893d  mov     [rbp+0CF0h+var_D1C], 104h
0x180128944  mov     [rbp+0CF0h+var_D20], r14d
0x180128948  mov     [rbp+0CF0h+var_D08], rcx
0x18012894c  jz      short loc_1801289C0
0x18012894e  mov     rdx, 4000000000000400h
0x180128958  test    qword ptr cs:xmmword_180169738+8, rdx
0x18012895f  jz      short loc_1801289C0
0x180128961  mov     rax, cs:qword_180169748
0x180128968  and     rax, rdx
0x18012896b  cmp     cs:qword_180169748, rax
0x180128972  jnz     short loc_1801289C0
0x180128974  mov     [rsp+0DF0h+var_DB0], 4
0x18012897d  lea     rax, [rsp+0DF0h+var_D78]
0x180128982  mov     [rsp+0DF0h+var_DB8], rax
0x180128987  lea     r9, aSdatacollector_7; "SDataCollectorSet::Commit"
0x18012898e  lea     rax, [rbp+0CF0h+var_D08]
0x180128992  mov     [rsp+0DF0h+peUse], 8
0x18012899b  mov     [rsp+0DF0h+cchReferencedDomainName], rax
0x1801289a0  lea     r8d, [r14+3]
0x1801289a4  lea     rdx, PLA_EVENT_METHOD
0x1801289ab  mov     [rsp+0DF0h+ReferencedDomainName], 1Ah
0x1801289b4  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1801289bb  call    EventingWriteEvent
0x1801289c0  cmp     [r15+8], r14d
0x1801289c4  jz      short loc_1801289D0
0x1801289c6  lea     rcx, [r15+10h]; lpCriticalSection
0x1801289ca  call    cs:__imp_EnterCriticalSection
0x1801289d0  lea     rax, [rbp+0CF0h+var_D28]
0x1801289d4  mov     r9d, edi; enum __MIDL___MIDL_itf_pla_0001_0043_0007
0x1801289d7  mov     r8, rbx; unsigned __int16 *
0x1801289da  mov     [rsp+0DF0h+ReferencedDomainName], rax; int
0x1801289df  mov     rdx, r12; unsigned __int16 *
0x1801289e2  mov     rcx, r15; this
0x1801289e5  call    ?Commit@DataCollectorSet@@UEAAJPEAG0W4__MIDL___MIDL_itf_pla_0001_0043_0007@@PEAPEAUIValueMap@@@Z; DataCollectorSet::Commit(ushort *,ushort *,__MIDL___MIDL_itf_pla_0001_0043_0007,IValueMap * *)
0x1801289ea  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1801289ee  mov     ebx, eax
0x1801289f0  lea     r13d, [rsi+2]
0x1801289f4  test    eax, eax
0x1801289f6  jns     loc_180128AD8
0x1801289fc  cmp     dword ptr cs:xmmword_180169738, r14d
0x180128a03  mov     [rsp+0DF0h+var_D78], r14d
0x180128a08  mov     [rsp+0DF0h+var_D80], eax
0x180128a0c  jz      loc_180128D82
0x180128a12  mov     rdx, 4000000000000800h; unsigned __int64
0x180128a1c  test    qword ptr cs:xmmword_180169738+8, rdx
0x180128a23  jz      loc_180128D82
0x180128a29  mov     rax, cs:qword_180169748
0x180128a30  and     rax, rdx
0x180128a33  cmp     cs:qword_180169748, rax
0x180128a3a  jnz     loc_180128D82
0x180128a40  lea     rcx, [rbp+0CF0h+var_B50]; unsigned __int16 *
0x180128a47  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180128a4c  lea     rcx, [rbp+0CF0h+var_B50]
0x180128a53  mov     rax, rsi
0x180128a56  inc     rax
0x180128a59  cmp     [rcx+rax*2], r14w
0x180128a5e  jnz     short loc_180128A56
0x180128a60  lea     ecx, [rax+rax]
0x180128a63  lea     rax, [rbp+0CF0h+var_B50]
0x180128a6a  add     rcx, 2
0x180128a6e  lea     r12, qword_180147320
0x180128a75  mov     [rsp+0DF0h+var_D90], rcx
0x180128a7a  lea     r9, [rsp+0DF0h+var_D80]
0x180128a7f  mov     [rsp+0DF0h+var_D98], rax
0x180128a84  lea     rdx, PLA_EVENT_ERROR
0x180128a8b  mov     [rsp+0DF0h+var_DA0], 1Ah
0x180128a94  lea     rax, aSdatacollector_7; "SDataCollectorSet::Commit"
0x180128a9b  mov     [rsp+0DF0h+var_DA8], rax
0x180128aa0  mov     ecx, 4
0x180128aa5  mov     [rsp+0DF0h+var_DB0], rcx
0x180128aaa  lea     rax, [rsp+0DF0h+var_D78]
0x180128aaf  mov     [rsp+0DF0h+var_DB8], rax
0x180128ab4  mov     [rsp+0DF0h+peUse], r13
0x180128ab9  lea     r8d, [rcx+1]
0x180128abd  mov     [rsp+0DF0h+cchReferencedDomainName], r12
0x180128ac2  mov     [rsp+0DF0h+ReferencedDomainName], rcx
0x180128ac7  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180128ace  call    EventingWriteEvent
0x180128ad3  jmp     loc_180128D82
0x180128ad8  lea     r14, [r15+110h]
0x180128adf  mov     rdx, r12; unsigned __int16 *
0x180128ae2  mov     rcx, r14; this
0x180128ae5  lea     r9, [rbp+0CF0h+var_D18]; struct IRegisteredTask **
0x180128ae9  lea     r8, [rbp+0CF0h+var_D50]; struct ITaskDefinition **
0x180128aed  call    ?GetExistingTask@PlaTaskService@@QEAAJPEAGPEAPEAUITaskDefinition@@PEAPEAUIRegisteredTask@@@Z; PlaTaskService::GetExistingTask(ushort *,ITaskDefinition * *,IRegisteredTask * *)
0x180128af2  xor     edx, edx
0x180128af4  mov     ebx, eax
0x180128af6  test    eax, eax
0x180128af8  js      loc_180128C0B
0x180128afe  mov     eax, edi
0x180128b00  and     eax, 0Fh
0x180128b03  cmp     eax, r13d
0x180128b06  jnz     loc_180128BF2
0x180128b0c  cmp     dword ptr cs:xmmword_180169738, edx
0x180128b12  mov     ebx, 803000B7h
0x180128b17  mov     [rsp+0DF0h+var_D80], ebx
0x180128b1b  mov     [rsp+0DF0h+var_D78], edx
0x180128b1f  jz      loc_180128BE9
0x180128b25  mov     rdx, 4000000000000800h; unsigned __int64
0x180128b2f  test    qword ptr cs:xmmword_180169738+8, rdx
0x180128b36  jz      loc_180128BE9
0x180128b3c  mov     rax, cs:qword_180169748
0x180128b43  and     rax, rdx
0x180128b46  cmp     cs:qword_180169748, rax
0x180128b4d  jnz     loc_180128BE9
0x180128b53  lea     rcx, [rbp+0CF0h+var_AD0]; unsigned __int16 *
0x180128b5a  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180128b5f  lea     rcx, [rbp+0CF0h+var_AD0]
0x180128b66  mov     rax, rsi
0x180128b69  xor     r14d, r14d
0x180128b6c  inc     rax
0x180128b6f  cmp     [rcx+rax*2], r14w
0x180128b74  jnz     short loc_180128B6C
0x180128b76  lea     ecx, [rax+rax]
0x180128b79  add     rcx, 2
0x180128b7d  lea     rax, [rbp+0CF0h+var_AD0]
0x180128b84  mov     [rsp+0DF0h+var_D90], rcx
0x180128b89  lea     r12, qword_180147320
0x180128b90  mov     [rsp+0DF0h+var_D98], rax
0x180128b95  lea     r9, [rsp+0DF0h+var_D80]
0x180128b9a  mov     [rsp+0DF0h+var_DA0], 1Ah
0x180128ba3  lea     rax, aSdatacollector_7; "SDataCollectorSet::Commit"
0x180128baa  mov     [rsp+0DF0h+var_DA8], rax
0x180128baf  lea     rdx, PLA_EVENT_ERROR
0x180128bb6  mov     ecx, 4
0x180128bbb  lea     rax, [rsp+0DF0h+var_D78]
0x180128bc0  mov     [rsp+0DF0h+var_DB0], rcx
0x180128bc5  mov     [rsp+0DF0h+var_DB8], rax
0x180128bca  mov     [rsp+0DF0h+peUse], r13
0x180128bcf  lea     r8d, [rcx+1]
0x180128bd3  mov     [rsp+0DF0h+cchReferencedDomainName], r12
0x180128bd8  mov     [rsp+0DF0h+ReferencedDomainName], rcx
0x180128bdd  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180128be4  call    EventingWriteEvent
0x180128be9  mov     [rbp+0CF0h+var_D68], r13d
0x180128bed  jmp     loc_180128D82
0x180128bf2  mov     ecx, r13d
0x180128bf5  mov     [rbp+0CF0h+var_D68], ecx
0x180128bf8  bt      edi, 0Ch
0x180128bfc  jnb     loc_180128D93
0x180128c02  xor     edi, edi
0x180128c04  mov     ebx, edi
0x180128c06  jmp     loc_1801299D2
0x180128c0b  mov     r8d, 80300002h
0x180128c11  cmp     eax, r8d
0x180128c14  jz      short loc_180128C8A
0x180128c16  cmp     dword ptr cs:xmmword_180169738, edx
0x180128c1c  mov     [rsp+0DF0h+var_D78], edx
0x180128c20  mov     [rsp+0DF0h+var_D80], eax
0x180128c24  jz      loc_180128D82
0x180128c2a  mov     rdx, 4000000000000800h; unsigned __int64
0x180128c34  test    qword ptr cs:xmmword_180169738+8, rdx
0x180128c3b  jz      loc_180128D82
0x180128c41  mov     rax, cs:qword_180169748
0x180128c48  and     rax, rdx
0x180128c4b  cmp     cs:qword_180169748, rax
0x180128c52  jnz     loc_180128D82
0x180128c58  lea     rcx, [rbp+0CF0h+var_A50]; unsigned __int16 *
0x180128c5f  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180128c64  lea     rcx, [rbp+0CF0h+var_A50]
0x180128c6b  mov     rax, rsi
0x180128c6e  xor     r14d, r14d
0x180128c71  inc     rax
0x180128c74  cmp     [rcx+rax*2], r14w
0x180128c79  jnz     short loc_180128C71
0x180128c7b  lea     ecx, [rax+rax]
0x180128c7e  lea     rax, [rbp+0CF0h+var_A50]
0x180128c85  jmp     loc_180128A6A
0x180128c8a  mov     eax, edi
0x180128c8c  mov     [rbp+0CF0h+var_D68], edx
0x180128c8f  and     eax, 0Fh
0x180128c92  mov     ecx, edx
0x180128c94  cmp     eax, 2
0x180128c97  jnz     loc_180128BF8
0x180128c9d  cmp     dword ptr cs:xmmword_180169738, edx
0x180128ca3  mov     ebx, r8d
0x180128ca6  mov     [rsp+0DF0h+var_D78], edx
0x180128caa  mov     [rsp+0DF0h+var_D80], r8d
0x180128caf  jz      loc_180128D7B
0x180128cb5  mov     rdx, 4000000000000800h; unsigned __int64
0x180128cbf  test    qword ptr cs:xmmword_180169738+8, rdx
0x180128cc6  jz      loc_180128D7B
0x180128ccc  mov     rax, cs:qword_180169748
0x180128cd3  and     rax, rdx
0x180128cd6  cmp     cs:qword_180169748, rax
0x180128cdd  jnz     loc_180128D7B
0x180128ce3  lea     rcx, [rbp+0CF0h+var_9D0]; unsigned __int16 *
0x180128cea  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180128cef  lea     rcx, [rbp+0CF0h+var_9D0]
0x180128cf6  mov     rax, rsi
0x180128cf9  xor     r14d, r14d
0x180128cfc  inc     rax
0x180128cff  cmp     [rcx+rax*2], r14w
0x180128d04  jnz     short loc_180128CFC
0x180128d06  lea     ecx, [rax+rax]
0x180128d09  add     rcx, 2
0x180128d0d  lea     rax, [rbp+0CF0h+var_9D0]
0x180128d14  mov     [rsp+0DF0h+var_D90], rcx
0x180128d19  lea     r12, qword_180147320
0x180128d20  mov     [rsp+0DF0h+var_D98], rax
0x180128d25  lea     r9, [rsp+0DF0h+var_D80]
0x180128d2a  mov     [rsp+0DF0h+var_DA0], 1Ah
0x180128d33  lea     rax, aSdatacollector_7; "SDataCollectorSet::Commit"
0x180128d3a  mov     [rsp+0DF0h+var_DA8], rax
0x180128d3f  lea     rdx, PLA_EVENT_ERROR
0x180128d46  mov     ecx, 4
0x180128d4b  lea     rax, [rsp+0DF0h+var_D78]
0x180128d50  mov     [rsp+0DF0h+var_DB0], rcx
0x180128d55  mov     [rsp+0DF0h+var_DB8], rax
0x180128d5a  mov     [rsp+0DF0h+peUse], r13
0x180128d5f  lea     r8d, [rcx+1]
0x180128d63  mov     [rsp+0DF0h+cchReferencedDomainName], r12
0x180128d68  mov     [rsp+0DF0h+ReferencedDomainName], rcx
0x180128d6d  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180128d74  call    EventingWriteEvent
0x180128d79  jmp     short loc_180128D7E
0x180128d7b  xor     r14d, r14d
0x180128d7e  mov     [rbp+0CF0h+var_D68], r14d
0x180128d82  bt      edi, 0Ch
0x180128d86  jb      loc_1801299D0
0x180128d8c  xor     edi, edi
0x180128d8e  jmp     loc_1801298DD
0x180128d93  xor     edi, edi
0x180128d95  test    ecx, ecx
0x180128d97  jnz     loc_180128EAE
0x180128d9d  lea     rdx, [rbp+0CF0h+var_D50]; struct ITaskDefinition **
0x180128da1  mov     rcx, r14; this
0x180128da4  call    ?GetTask@PlaTaskService@@QEAAJPEAPEAUITaskDefinition@@@Z; PlaTaskService::GetTask(ITaskDefinition * *)
0x180128da9  mov     ebx, eax
0x180128dab  test    eax, eax
0x180128dad  jns     short loc_180128E2C
0x180128daf  cmp     dword ptr cs:xmmword_180169738, edi
0x180128db5  mov     [rsp+0DF0h+var_D78], edi
0x180128db9  mov     [rsp+0DF0h+var_D80], eax
0x180128dbd  jz      loc_1801298E1
0x180128dc3  mov     rdx, 4000000000000800h; unsigned __int64
0x180128dcd  test    qword ptr cs:xmmword_180169738+8, rdx
0x180128dd4  jz      loc_1801298E1
0x180128dda  mov     rax, cs:qword_180169748
0x180128de1  and     rax, rdx
0x180128de4  cmp     cs:qword_180169748, rax
0x180128deb  jnz     loc_1801298E1
0x180128df1  lea     rcx, [rbp+0CF0h+var_950]; unsigned __int16 *
0x180128df8  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180128dfd  lea     rcx, [rbp+0CF0h+var_950]
0x180128e04  mov     rax, rsi
0x180128e07  inc     rax
0x180128e0a  cmp     [rcx+rax*2], di
0x180128e0e  jnz     short loc_180128E07
0x180128e10  lea     ecx, [rax+rax]
0x180128e13  lea     rax, [rbp+0CF0h+var_950]
0x180128e1a  lea     r12, qword_180147320
0x180128e21  mov     r8d, 5
0x180128e27  jmp     loc_18012987F
0x180128e2c  mov     rcx, [rbp+0CF0h+var_D50]; struct ITaskDefinition *
0x180128e30  mov     rdx, r12; unsigned __int16 *
0x180128e33  call    ?PlaiSetTaskSettings@@YAJPEAUITaskDefinition@@PEAG@Z; PlaiSetTaskSettings(ITaskDefinition *,ushort *)
0x180128e38  mov     ebx, eax
0x180128e3a  test    eax, eax
0x180128e3c  jns     short loc_180128EAE
0x180128e3e  cmp     dword ptr cs:xmmword_180169738, edi
0x180128e44  mov     [rsp+0DF0h+var_D78], edi
0x180128e48  mov     [rsp+0DF0h+var_D80], eax
0x180128e4c  jz      loc_1801298E1
  ... truncated ...
```
