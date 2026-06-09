# BootTraceSession::Query(ushort *,ushort *)

- ea: `0x18002bd20`
- end: `0x18002d176`
- name: `?Query@BootTraceSession@@UEAAJPEAG0@Z`
- size: `5206`
- prototype: `__int64 __fastcall(BootTraceSession *__hidden this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `21`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180002bd0`
- `0x180002ee4`
- `0x180004e98`
- `0x1800106d0`
- `0x1800123d4`
- `0x180015f98`
- `0x1800198b0`
- `0x18002b3a0`
- `0x18002bd20`
- `0x18002d17c`
- `0x18002d6bc`
- `0x18002d820`
- `0x18002db7c`
- `0x18002dda0`
- `0x1800370c8`
- `0x18004cb20`
- `0x180099d3c`
- `0x1800eef90`
- `0x18013ae76`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d0aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d0aa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002bd8c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002bd8c`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002c908`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002c908`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c112`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c1ad`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c112`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c1ad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d0d2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d0e5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d0d2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d0e5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002bfcb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002bfcb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002bfb8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002bfb8`

## pseudocode

```c
__int64 __fastcall BootTraceSession::Query(BootTraceSession *this, unsigned __int16 *a2, unsigned __int16 *a3)
{
  _QWORD *v6; // r14
  int v7; // eax
  int v8; // edi
  __int64 v9; // rbx
  __int64 *v10; // r9
  __int64 *v11; // rax
  LPCOLESTR v12; // rbx
  int v13; // eax
  __int64 v14; // rbx
  int v15; // eax
  __int64 v16; // rbx
  HANDLE ProcessHeap; // rax
  const OLECHAR *v18; // rax
  int v19; // edx
  unsigned __int64 v20; // rcx
  __int64 v21; // rbx
  LSTATUS v22; // eax
  int v23; // eax
  __int64 v24; // rbx
  LSTATUS v25; // eax
  __int64 v26; // rbx
  __int64 v27; // rdx
  int v28; // eax
  int v29; // eax
  int v30; // eax
  int v31; // eax
  int v32; // eax
  int v33; // eax
  enum __MIDL___MIDL_itf_pla_0001_0043_0005 v34; // eax
  __int64 v35; // r8
  __int64 v36; // r9
  int v37; // eax
  unsigned int v38; // r9d
  int v39; // eax
  OLECHAR *v40; // rdi
  unsigned __int64 v41; // rdx
  int v42; // eax
  int v43; // eax
  unsigned int v44; // r9d
  const OLECHAR *v45; // rdi
  BootTraceSession *v46; // rcx
  HRESULT v47; // eax
  int v48; // eax
  int v49; // eax
  _QWORD *Class; // rax
  _QWORD *v51; // rsi
  __int64 v52; // rax
  int v53; // eax
  int v54; // eax
  int v55; // eax
  int v56; // eax
  int Providers; // eax
  int v58; // eax
  int AutologgerSecurity; // eax
  __int64 v60; // rbx
  int v62; // [rsp+70h] [rbp-90h] BYREF
  LPCOLESTR lpsz; // [rsp+78h] [rbp-88h]
  __int64 v64; // [rsp+80h] [rbp-80h] BYREF
  _QWORD *v65; // [rsp+88h] [rbp-78h]
  unsigned int v66; // [rsp+90h] [rbp-70h] BYREF
  HKEY phkResult; // [rsp+98h] [rbp-68h] BYREF
  struct ITraceDataCollector *v68; // [rsp+A0h] [rbp-60h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v70; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v71; // [rsp+B8h] [rbp-48h] BYREF
  GUID v72; // [rsp+C0h] [rbp-40h] BYREF
  GUID pclsid; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v74[64]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v75[64]; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int16 v76[64]; // [rsp+1E0h] [rbp+E0h] BYREF
  unsigned __int16 v77[64]; // [rsp+260h] [rbp+160h] BYREF
  unsigned __int16 v78[64]; // [rsp+2E0h] [rbp+1E0h] BYREF
  unsigned __int16 v79[64]; // [rsp+360h] [rbp+260h] BYREF
  unsigned __int16 v80[64]; // [rsp+3E0h] [rbp+2E0h] BYREF
  unsigned __int16 v81[64]; // [rsp+460h] [rbp+360h] BYREF
  unsigned __int16 v82[64]; // [rsp+4E0h] [rbp+3E0h] BYREF
  unsigned __int16 v83[64]; // [rsp+560h] [rbp+460h] BYREF
  unsigned __int16 v84[64]; // [rsp+5E0h] [rbp+4E0h] BYREF
  unsigned __int16 v85[64]; // [rsp+660h] [rbp+560h] BYREF
  unsigned __int16 v86[64]; // [rsp+6E0h] [rbp+5E0h] BYREF
  unsigned __int16 v87[64]; // [rsp+760h] [rbp+660h] BYREF
  unsigned __int16 v88[64]; // [rsp+7E0h] [rbp+6E0h] BYREF
  unsigned __int16 v89[64]; // [rsp+860h] [rbp+760h] BYREF
  unsigned __int16 v90[64]; // [rsp+8E0h] [rbp+7E0h] BYREF
  unsigned __int16 v91[64]; // [rsp+960h] [rbp+860h] BYREF
  unsigned __int16 v92[64]; // [rsp+9E0h] [rbp+8E0h] BYREF
  unsigned __int16 v93[64]; // [rsp+A60h] [rbp+960h] BYREF
  unsigned __int16 v94[64]; // [rsp+AE0h] [rbp+9E0h] BYREF
  unsigned __int16 v95[64]; // [rsp+B60h] [rbp+A60h] BYREF
  unsigned __int16 v96[64]; // [rsp+BE0h] [rbp+AE0h] BYREF
  unsigned __int16 v97[64]; // [rsp+C60h] [rbp+B60h] BYREF
  unsigned __int16 v98[64]; // [rsp+CE0h] [rbp+BE0h] BYREF
  unsigned __int16 v99[64]; // [rsp+D60h] [rbp+C60h] BYREF
  unsigned __int16 v100[64]; // [rsp+DE0h] [rbp+CE0h] BYREF
  unsigned __int16 v101[64]; // [rsp+E60h] [rbp+D60h] BYREF

  v66 = 0;
  v6 = 0;
  hKey = 0;
  pclsid = 0;
  phkResult = 0;
  v68 = 0;
  v65 = 0;
  v70 = 0;
  v71 = 0;
  if ( *((_DWORD *)this + 2) )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v7 = DataCollectorSet::Query(this, a2, a3);
  v8 = v7;
  if ( v7 < 0 )
  {
    v62 = v7;
    LODWORD(v64) = 0;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v74, 0x4000000000000800uLL);
      v9 = -1;
      do
        ++v9;
      while ( v74[v9] );
      v10 = (__int64 *)&v62;
      v11 = &v64;
      goto LABEL_10;
    }
    goto LABEL_11;
  }
  v13 = (*(__int64 (__fastcall **)(BootTraceSession *, struct ITraceDataCollector **))(*(_QWORD *)this + 656LL))(
          this,
          &v68);
  v8 = v13;
  if ( v13 < 0 )
  {
    LODWORD(v64) = v13;
    v62 = 0;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v75, 0x4000000000000800uLL);
      v14 = -1;
      do
        ++v14;
      while ( v75[v14] );
LABEL_18:
      v10 = &v64;
      v11 = (__int64 *)&v62;
LABEL_10:
      EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, v10, 4, byte_180147320, 1, v11, 4);
      v12 = 0;
      v6 = 0;
      goto LABEL_234;
    }
    goto LABEL_11;
  }
  v15 = TraceSession::put_Name(this, a2);
  v8 = v15;
  if ( v15 < 0 )
  {
    LODWORD(v64) = v15;
    v62 = 0;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v76, 0x4000000000000800uLL);
      v16 = -1;
      do
        ++v16;
      while ( v76[v16] );
      goto LABEL_18;
    }
LABEL_11:
    v12 = 0;
    goto LABEL_234;
  }
  ProcessHeap = GetProcessHeap();
  v18 = (const OLECHAR *)HeapAlloc(ProcessHeap, 0, 0x800u);
  v19 = xmmword_180169738;
  v20 = qword_180169748;
  v12 = v18;
  v62 = 0;
  lpsz = v18;
  v64 = 2048;
  *(_QWORD *)&v72.Data1 = v18;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000200LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000200LL) )
  {
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_ALLOC, 4, byte_180147320, 1, &v62, 4, &v72, 8);
    v20 = qword_180169748;
    v19 = xmmword_180169738;
  }
  if ( !v12 )
  {
    v62 = 0;
    v8 = -2147024882;
    LODWORD(v64) = -2147024882;
    if ( !v19 || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0 || v20 != (v20 & 0x4000000000000800LL) )
      goto LABEL_233;
    PlaiWhoAmI(v77, 0x4000000000000800uLL);
    v21 = -1;
    do
      ++v21;
    while ( v77[v21] );
    goto LABEL_231;
  }
  v22 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\WMI\\AutoLogger", 0, 0x20019u, &hKey);
  v23 = PlaiHResultFromWin32(v22);
  v8 = v23;
  if ( v23 < 0 )
  {
    LODWORD(v64) = v23;
    v62 = 0;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_233;
    }
    PlaiWhoAmI(v78, 0x4000000000000800uLL);
    v24 = -1;
    do
      ++v24;
    while ( v78[v24] );
    goto LABEL_231;
  }
  v25 = RegOpenKeyExW(hKey, a2, 0, 0x20019u, &phkResult);
  if ( v25 == 2 )
  {
    v8 = -2144337918;
LABEL_226:
    LODWORD(v64) = v8;
    v62 = 0;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_233;
    }
    PlaiWhoAmI(v101, 0x4000000000000800uLL);
    v60 = -1;
    do
      ++v60;
    while ( v101[v60] );
    goto LABEL_231;
  }
  v8 = PlaiHResultFromWin32(v25);
  if ( v8 < 0 )
    goto LABEL_226;
  v26 = -1;
  if ( PlaiGetRegDword(phkResult, L"Start", &v66) < 0 )
    goto LABEL_253;
  v27 = 0xFFFFFFFFLL;
  if ( !v66 )
    v27 = 0;
  v28 = (*(__int64 (__fastcall **)(BootTraceSession *, __int64))(*(_QWORD *)this + 400LL))(this, v27);
  v8 = v28;
  if ( v28 >= 0 )
  {
LABEL_253:
    if ( PlaiGetRegDword(phkResult, L"BufferSize", &v66) >= 0 )
    {
      v29 = ((__int64 (__fastcall *)(struct ITraceDataCollector *, _QWORD))v68->lpVtbl->put_BufferSize)(v68, v66);
      v8 = v29;
      if ( v29 < 0 )
      {
        LODWORD(v64) = v29;
        v62 = 0;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_232;
        }
        PlaiWhoAmI(v80, 0x4000000000000800uLL);
        do
          ++v26;
        while ( v80[v26] );
        goto LABEL_231;
      }
    }
    if ( PlaiGetRegDword(phkResult, L"MinimumBuffers", &v66) >= 0 )
    {
      v30 = ((__int64 (__fastcall *)(struct ITraceDataCollector *, _QWORD))v68->lpVtbl->put_MinimumBuffers)(v68, v66);
      v8 = v30;
      if ( v30 < 0 )
      {
        LODWORD(v64) = v30;
        v62 = 0;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_232;
        }
        PlaiWhoAmI(v81, 0x4000000000000800uLL);
        do
          ++v26;
        while ( v81[v26] );
        goto LABEL_231;
      }
    }
    if ( PlaiGetRegDword(phkResult, L"MaximumBuffers", &v66) >= 0 )
    {
      v31 = ((__int64 (__fastcall *)(struct ITraceDataCollector *, _QWORD))v68->lpVtbl->put_MaximumBuffers)(v68, v66);
      v8 = v31;
      if ( v31 < 0 )
      {
        LODWORD(v64) = v31;
        v62 = 0;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_232;
        }
        PlaiWhoAmI(v82, 0x4000000000000800uLL);
        do
          ++v26;
        while ( v82[v26] );
        goto LABEL_231;
      }
    }
    if ( PlaiGetRegDword(phkResult, L"FlushTimer", &v66) >= 0 )
    {
      v32 = ((__int64 (__fastcall *)(struct ITraceDataCollector *, _QWORD))v68->lpVtbl->put_FlushTimer)(v68, v66);
      v8 = v32;
      if ( v32 < 0 )
      {
        LODWORD(v64) = v32;
        v62 = 0;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_232;
        }
        PlaiWhoAmI(v83, 0x4000000000000800uLL);
        do
          ++v26;
        while ( v83[v26] );
        goto LABEL_231;
      }
    }
    if ( PlaiGetRegDword(phkResult, L"MaxFileSize", &v66) < 0 )
      v66 = 100;
    v33 = (*(__int64 (__fastcall **)(BootTraceSession *))(*(_QWORD *)this + 232LL))(this);
    v8 = v33;
    if ( v33 < 0 )
    {
      LODWORD(v64) = v33;
      v62 = 0;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_232;
      }
      PlaiWhoAmI(v84, 0x4000000000000800uLL);
      do
        ++v26;
      while ( v84[v26] );
      goto LABEL_231;
    }
    if ( PlaiGetRegDword(phkResult, L"ClockType", &v66) >= 0 )
    {
      v34 = PlaiDwordToClockType(v66);
      v37 = (*(__int64 (__fastcall **)(__int64, _QWORD))(v35 + 312))(v36, (unsigned int)v34);
      v8 = v37;
      if ( v37 < 0 )
      {
        LODWORD(v64) = v37;
        v62 = 0;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_232;
        }
        PlaiWhoAmI(v85, 0x4000000000000800uLL);
        do
          ++v26;
        while ( v85[v26] );
        goto LABEL_231;
      }
    }
    if ( PlaiGetRegDword(phkResult, L"LogFileMode", &v66) < 0 )
    {
      v66 = 1;
    }
    else
    {
      v39 = (*(__int64 (__fastcall **)(BootTraceSession *, _QWORD))(*(_QWORD *)this + 624LL))(this, v66);
      v8 = v39;
      if ( v39 < 0 )
      {
        LODWORD(v64) = v39;
        v62 = 0;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_232;
        }
        PlaiWhoAmI(v86, 0x4000000000000800uLL);
        do
          ++v26;
        while ( v86[v26] );
        goto LABEL_231;
      }
    }
    v40 = (OLECHAR *)lpsz;
    if ( PlaiGetRegString(phkResult, L"FileName", (unsigned __int16 *)lpsz, v38, 1) < 0 )
    {
      if ( (v66 & 7) == 0 )
      {
        *v40 = 0;
LABEL_132:
        v8 = TraceSession::SetFileMode(this, v68, v40, v66);
        if ( v8 < 0 )
        {
          LODWORD(v64) = v8;
          v62 = 0;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_232;
          }
          PlaiWhoAmI(v89, 0x4000000000000800uLL);
          do
            ++v26;
          while ( v89[v26] );
          goto LABEL_231;
        }
        v45 = lpsz;
        if ( PlaiGetRegString(phkResult, L"Guid", (unsigned __int16 *)lpsz, v44, 0) < 0 )
          goto LABEL_202;
        v47 = CLSIDFromString(v45, &pclsid);
        v8 = v47;
        if ( v47 < 0 )
        {
          LODWORD(v64) = v47;
          v62 = 0;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_232;
          }
          PlaiWhoAmI(v90, 0x4000000000000800uLL);
          do
            ++v26;
          while ( v90[v26] );
          goto LABEL_231;
        }
        v72 = pclsid;
        v48 = ((__int64 (__fastcall *)(struct ITraceDataCollector *, GUID *))v68->lpVtbl->put_Guid)(v68, &v72);
        v8 = v48;
        if ( v48 < 0 )
        {
          LODWORD(v64) = v48;
          v62 = 0;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_232;
          }
          PlaiWhoAmI(v91, 0x4000000000000800uLL);
          do
            ++v26;
          while ( v91[v26] );
          goto LABEL_231;
        }
        if ( !memcmp_0(&pclsid, &SystemTraceControlGuid, 0x10u)
          || !memcmp_0(&pclsid, &CKCLGuid, 0x10u)
          || !memcmp_0(&pclsid, &CritSecGuid, 0x10u)
          || !memcmp_0(&pclsid, &HeapGuid, 0x10u) )
        {
          v49 = ((__int64 (__fastcall *)(struct ITraceDataCollector *, __int64 *))v68->lpVtbl->get_TraceDataProviders)(
                  v68,
                  &v70);
          v8 = v49;
          if ( v49 < 0 )
          {
            v62 = 0;
            LODWORD(v64) = v49;
            if ( !(_DWORD)xmmword_180169738
              || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
            {
              goto LABEL_232;
            }
            PlaiWhoAmI(v92, 0x4000000000000800uLL);
            do
              ++v26;
            while ( v92[v26] );
            goto LABEL_231;
          }
          Class = (_QWORD *)CreateClassObject<TraceDataProvider>(byte_180147320, 0);
          v65 = Class;
          v51 = Class;
          if ( !Class )
          {
            v8 = -2147024882;
            LODWORD(v64) = -2147024882;
            v62 = 0;
            if ( !(_DWORD)xmmword_180169738
              || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
            {
              goto LABEL_172;
            }
            PlaiWhoAmI(v93, 0x4000000000000800uLL);
            do
              ++v26;
            while ( v93[v26] );
            goto LABEL_171;
          }
          v52 = *Class;
          v72 = pclsid;
          v53 = (*(__int64 (__fastcall **)(_QWORD *, GUID *))(v52 + 80))(v51, &v72);
          v8 = v53;
          if ( v53 < 0 )
          {
            LODWORD(v64) = v53;
            v62 = 0;
            if ( !(_DWORD)xmmword_180169738
              || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
            {
              goto LABEL_172;
            }
            PlaiWhoAmI(v94, 0x4000000000000800uLL);
            do
              ++v26;
            while ( v94[v26] );
            goto LABEL_171;
          }
          v54 = (*(__int64 (__fastcall **)(_QWORD *, __int64 *))(*v51 + 96LL))(v51, &v71);
          v8 = v54;
          if ( v54 < 0 )
          {
            LODWORD(v64) = v54;
            v62 = 0;
            if ( !(_DWORD)xmmword_180169738
              || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
            {
              goto LABEL_172;
            }
            PlaiWhoAmI(v95, 0x4000000000000800uLL);
            do
              ++v26;
            while ( v95[v26] );
            goto LABEL_171;
          }
          if ( PlaiGetRegDword(phkResult, L"EnableKernelFlags", &v66) >= 0 )
          {
            v55 = PlaiPutUlValue<IValueMap>(v71, v66);
            v8 = v55;
            if ( v55 < 0 )
            {
              LODWORD(v64) = v55;
              v62 = 0;
              if ( !(_DWORD)xmmword_180169738
                || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
              {
                goto LABEL_172;
              }
              PlaiWhoAmI(v96, 0x4000000000000800uLL);
              do
                ++v26;
              while ( v96[v26] );
              goto LABEL_171;
            }
          }
          v56 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v70 + 80LL))(v70, v51);
          v8 = v56;
          if ( v56 < 0 )
          {
            v62 = 0;
            LODWORD(v64) = v56;
            if ( !(_DWORD)xmmword_180169738
              || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
            {
              goto LABEL_172;
            }
            PlaiWhoAmI(v97, 0x4000000000000800uLL);
            do
              ++v26;
            while ( v97[v26] );
            goto LABEL_171;
          }
        }
        else
        {
LABEL_202:
          Providers = BootTraceSession::QueryProviders(v46, hKey, a2, v68);
          v8 = Providers;
          if ( Providers < 0 )
          {
            v62 = 0;
            LODWORD(v64) = Providers;
            if ( !(_DWORD)xmmword_180169738
              || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
            {
              goto LABEL_232;
            }
            PlaiWhoAmI(v98, 0x4000000000000800uLL);
            do
              ++v26;
            while ( v98[v26] );
            goto LABEL_231;
          }
        }
        v58 = ((__int64 (__fastcall *)(struct ITraceDataCollector *, GUID *))v68->lpVtbl->get_Guid)(v68, &pclsid);
        v8 = v58;
        if ( v58 >= 0 )
        {
          PlaiFreeString(*((BSTR *)this + 31));
          *((_QWORD *)this + 31) = 0;
          if ( (int)PlaiGetAutologgerSecurity(&pclsid, (unsigned __int16 **)this + 31) >= 0
            || (AutologgerSecurity = PlaiGetAutologgerSecurity(
                                       &DefaultTraceSecurityGuid,
                                       (unsigned __int16 **)this + 31),
                v8 = AutologgerSecurity,
                AutologgerSecurity >= 0) )
          {
            v8 = 0;
            goto LABEL_172;
          }
          v62 = 0;
          LODWORD(v64) = AutologgerSecurity;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_172;
          }
          PlaiWhoAmI(v100, 0x4000000000000800uLL);
          do
            ++v26;
          while ( v100[v26] );
        }
        else
        {
          v62 = 0;
          LODWORD(v64) = v58;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_172;
          }
          PlaiWhoAmI(v99, 0x4000000000000800uLL);
          do
            ++v26;
          while ( v99[v26] );
        }
LABEL_171:
        EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v64, 4, byte_180147320, 1, &v62, 4);
LABEL_172:
        v12 = lpsz;
        v6 = v65;
        goto LABEL_234;
      }
      v43 = StringCchPrintfW(v40, 0x400u, L"%s\\LogFiles\\Wmi\\%s.etl", &g_SysDirectory, a2);
      v8 = v43;
      if ( v43 < 0 )
      {
        LODWORD(v64) = v43;
        v62 = 0;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_232;
        }
        PlaiWhoAmI(v88, 0x4000000000000800uLL);
        do
          ++v26;
        while ( v88[v26] );
        goto LABEL_231;
      }
    }
    else
    {
      v42 = PlaiExpandVariables(v40, v41, v40);
      v8 = v42;
      if ( v42 < 0 )
      {
        LODWORD(v64) = v42;
        v62 = 0;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_232;
        }
        PlaiWhoAmI(v87, 0x4000000000000800uLL);
        do
          ++v26;
        while ( v87[v26] );
        goto LABEL_231;
      }
    }
    v40 = (OLECHAR *)lpsz;
    goto LABEL_132;
  }
  LODWORD(v64) = v28;
  v62 = 0;
  if ( !(_DWORD)xmmword_180169738
    || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
    || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
  {
    goto LABEL_232;
  }
  PlaiWhoAmI(v79, 0x4000000000000800uLL);
  do
    ++v26;
  while ( v79[v26] );
LABEL_231:
  EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v64, 4, byte_180147320, 1, &v62, 4);
LABEL_232:
  v12 = lpsz;
LABEL_233:
  v6 = 0;
LABEL_234:
  if ( *((_DWORD *)this + 2) )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( v12 )
    PlaiFree(v12, 1);
  PlaiFreeString(0);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( v6 )
    (*(void (__fastcall **)(_QWORD *))(*v6 + 16LL))(v6);
  if ( v70 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 16LL))(v70);
    v70 = 0;
  }
  if ( v71 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
    v71 = 0;
  }
  if ( v68 )
    ((void (__fastcall *)(struct ITraceDataCollector *))v68->lpVtbl->Release)(v68);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18002bd20  mov     [rsp-8+arg_18], rbx
0x18002bd25  push    rbp
0x18002bd26  push    rsi
0x18002bd27  push    rdi
0x18002bd28  push    r12
0x18002bd2a  push    r13
0x18002bd2c  push    r14
0x18002bd2e  push    r15
0x18002bd30  lea     rbp, [rsp-0DF0h]
0x18002bd38  sub     rsp, 0EF0h
0x18002bd3f  mov     rax, cs:__security_cookie
0x18002bd46  xor     rax, rsp
0x18002bd49  mov     [rbp+0E20h+var_40], rax
0x18002bd50  xor     r15d, r15d
0x18002bd53  xorps   xmm0, xmm0
0x18002bd56  mov     rbx, r8
0x18002bd59  mov     rsi, rdx
0x18002bd5c  mov     r13, rcx
0x18002bd5f  mov     [rbp+0E20h+var_E90], r15d
0x18002bd63  mov     r14d, r15d
0x18002bd66  mov     [rbp+0E20h+hKey], r15
0x18002bd6a  movups  xmmword ptr [rbp+0E20h+pclsid.Data1], xmm0
0x18002bd6e  mov     [rbp+0E20h+var_E88], r15
0x18002bd72  mov     [rbp+0E20h+var_E80], r15
0x18002bd76  mov     [rbp+0E20h+var_E98], r15
0x18002bd7a  mov     [rbp+0E20h+var_E70], r15
0x18002bd7e  mov     [rbp+0E20h+var_E68], r15
0x18002bd82  cmp     [rcx+8], r15d
0x18002bd86  jz      short loc_18002BD92
0x18002bd88  add     rcx, 10h; lpCriticalSection
0x18002bd8c  call    cs:__imp_EnterCriticalSection
0x18002bd92  mov     r8, rbx; unsigned __int16 *
0x18002bd95  mov     rdx, rsi; unsigned __int16 *
0x18002bd98  mov     rcx, r13; this
0x18002bd9b  call    ?Query@DataCollectorSet@@UEAAJPEAG0@Z; DataCollectorSet::Query(ushort *,ushort *)
0x18002bda0  mov     edi, eax
0x18002bda2  test    eax, eax
0x18002bda4  jns     loc_18002BE8E
0x18002bdaa  xor     esi, esi
0x18002bdac  mov     [rsp+0F20h+var_EB0], eax
0x18002bdb0  cmp     dword ptr cs:xmmword_180169738, esi
0x18002bdb6  mov     dword ptr [rbp+0E20h+var_EA0], esi
0x18002bdb9  jz      loc_18002BE86
0x18002bdbf  mov     rdx, 4000000000000800h; unsigned __int64
0x18002bdc9  test    qword ptr cs:xmmword_180169738+8, rdx
0x18002bdd0  jz      loc_18002BE86
0x18002bdd6  mov     rax, cs:qword_180169748
0x18002bddd  and     rax, rdx
0x18002bde0  cmp     cs:qword_180169748, rax
0x18002bde7  jnz     loc_18002BE86
0x18002bded  lea     rcx, [rbp+0E20h+var_E40]; unsigned __int16 *
0x18002bdf1  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18002bdf6  lea     rax, [rbp+0E20h+var_E40]
0x18002bdfa  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002bdfe  inc     rbx
0x18002be01  cmp     [rax+rbx*2], si
0x18002be05  jnz     short loc_18002BDFE
0x18002be07  lea     rax, [rbp+0E20h+var_E40]
0x18002be0b  lea     ecx, [rbx+rbx]
0x18002be0e  add     rcx, 2
0x18002be12  lea     r9, [rsp+0F20h+var_EB0]
0x18002be17  mov     [rsp+0F20h+var_EC0], rcx
0x18002be1c  mov     [rsp+0F20h+var_EC8], rax
0x18002be21  lea     rax, aBoottracesessi_1; "BootTraceSession::Query"
0x18002be28  mov     [rsp+0F20h+var_ED0], 18h
0x18002be31  mov     [rsp+0F20h+var_ED8], rax
0x18002be36  lea     rax, [rbp+0E20h+var_EA0]
0x18002be3a  mov     r14d, 4
0x18002be40  lea     r15, byte_180147320
0x18002be47  mov     [rsp+0F20h+var_EE0], r14
0x18002be4c  lea     rdx, PLA_EVENT_ERROR
0x18002be53  mov     [rsp+0F20h+var_EE8], rax
0x18002be58  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18002be5f  mov     [rsp+0F20h+var_EF0], 1
0x18002be68  mov     [rsp+0F20h+var_EF8], r15
0x18002be6d  lea     r8d, [r14+1]
0x18002be71  mov     [rsp+0F20h+phkResult], r14
0x18002be76  call    EventingWriteEvent
0x18002be7b  mov     rbx, rsi
0x18002be7e  mov     r14, rbx
0x18002be81  jmp     loc_18002D0A0
0x18002be86  mov     rbx, rsi
0x18002be89  jmp     loc_18002D0A0
0x18002be8e  mov     rax, [r13+0]
0x18002be92  lea     rdx, [rbp+0E20h+var_E80]
0x18002be96  mov     rcx, r13
0x18002be99  mov     rax, [rax+290h]
0x18002bea0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bea5  mov     edi, eax
0x18002bea7  test    eax, eax
0x18002bea9  jns     loc_18002BF38
0x18002beaf  xor     esi, esi
0x18002beb1  mov     dword ptr [rbp+0E20h+var_EA0], eax
0x18002beb4  cmp     dword ptr cs:xmmword_180169738, esi
0x18002beba  mov     [rsp+0F20h+var_EB0], esi
0x18002bebe  jz      short loc_18002BE86
0x18002bec0  mov     rdx, 4000000000000800h; unsigned __int64
0x18002beca  test    qword ptr cs:xmmword_180169738+8, rdx
0x18002bed1  jz      short loc_18002BE86
0x18002bed3  mov     rax, cs:qword_180169748
0x18002beda  and     rax, rdx
0x18002bedd  cmp     cs:qword_180169748, rax
0x18002bee4  jnz     short loc_18002BE86
0x18002bee6  lea     rcx, [rbp+0E20h+var_DC0]; unsigned __int16 *
0x18002beea  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18002beef  lea     rax, [rbp+0E20h+var_DC0]
0x18002bef3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002bef7  inc     rbx
0x18002befa  cmp     [rax+rbx*2], si
0x18002befe  jnz     short loc_18002BEF7
0x18002bf00  lea     rax, [rbp+0E20h+var_DC0]
0x18002bf04  lea     ecx, [rbx+rbx]
0x18002bf07  add     rcx, 2
0x18002bf0b  lea     r9, [rbp+0E20h+var_EA0]
0x18002bf0f  mov     [rsp+0F20h+var_EC0], rcx
0x18002bf14  mov     [rsp+0F20h+var_EC8], rax
0x18002bf19  lea     rax, aBoottracesessi_1; "BootTraceSession::Query"
0x18002bf20  mov     [rsp+0F20h+var_ED0], 18h
0x18002bf29  mov     [rsp+0F20h+var_ED8], rax
0x18002bf2e  lea     rax, [rsp+0F20h+var_EB0]
0x18002bf33  jmp     loc_18002BE3A
0x18002bf38  mov     rdx, rsi; unsigned __int16 *
0x18002bf3b  mov     rcx, r13; this
0x18002bf3e  call    ?put_Name@TraceSession@@UEAAJPEAG@Z; TraceSession::put_Name(ushort *)
0x18002bf43  mov     edi, eax
0x18002bf45  test    eax, eax
0x18002bf47  jns     short loc_18002BFB8
0x18002bf49  xor     esi, esi
0x18002bf4b  mov     dword ptr [rbp+0E20h+var_EA0], eax
0x18002bf4e  cmp     dword ptr cs:xmmword_180169738, esi
0x18002bf54  mov     [rsp+0F20h+var_EB0], esi
0x18002bf58  jz      loc_18002BE86
0x18002bf5e  mov     rdx, 4000000000000800h; unsigned __int64
0x18002bf68  test    qword ptr cs:xmmword_180169738+8, rdx
0x18002bf6f  jz      loc_18002BE86
0x18002bf75  mov     rax, cs:qword_180169748
0x18002bf7c  and     rax, rdx
0x18002bf7f  cmp     cs:qword_180169748, rax
0x18002bf86  jnz     loc_18002BE86
0x18002bf8c  lea     rcx, [rbp+0E20h+var_D40]; unsigned __int16 *
0x18002bf93  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18002bf98  lea     rax, [rbp+0E20h+var_D40]
0x18002bf9f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002bfa3  inc     rbx
0x18002bfa6  cmp     [rax+rbx*2], si
0x18002bfaa  jnz     short loc_18002BFA3
0x18002bfac  lea     rax, [rbp+0E20h+var_D40]
0x18002bfb3  jmp     loc_18002BF04
0x18002bfb8  call    cs:__imp_GetProcessHeap
0x18002bfbe  mov     edi, 800h
0x18002bfc3  xor     edx, edx; dwFlags
0x18002bfc5  mov     rcx, rax; hHeap
0x18002bfc8  mov     r8d, edi; dwBytes
0x18002bfcb  call    cs:__imp_HeapAlloc
0x18002bfd1  mov     edx, dword ptr cs:xmmword_180169738
0x18002bfd7  lea     r12, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18002bfde  mov     rcx, cs:qword_180169748
0x18002bfe5  mov     rbx, rax
0x18002bfe8  mov     [rsp+0F20h+var_EB0], r15d
0x18002bfed  mov     r14d, 4
0x18002bff3  mov     [rsp+0F20h+lpsz], rax
0x18002bff8  lea     r15, byte_180147320
0x18002bfff  mov     [rbp+0E20h+var_EA0], rdi
0x18002c003  mov     qword ptr [rbp+0E20h+var_E60], rax
0x18002c007  test    edx, edx
0x18002c009  jz      short loc_18002C083
0x18002c00b  mov     r8, 4000000000000200h
0x18002c015  test    qword ptr cs:xmmword_180169738+8, r8
0x18002c01c  jz      short loc_18002C083
0x18002c01e  mov     rax, rcx
0x18002c021  and     rax, r8
0x18002c024  cmp     rcx, rax
0x18002c027  jnz     short loc_18002C083
0x18002c029  lea     ecx, [r14+4]
0x18002c02d  mov     r9, r15
0x18002c030  mov     [rsp+0F20h+var_ED0], rcx
0x18002c035  lea     rax, [rbp+0E20h+var_EA0]
0x18002c039  mov     [rsp+0F20h+var_ED8], rax
0x18002c03e  lea     rdx, PLA_EVENT_ALLOC
0x18002c045  mov     [rsp+0F20h+var_EE0], rcx
0x18002c04a  lea     rax, [rbp+0E20h+var_E60]
0x18002c04e  mov     [rsp+0F20h+var_EE8], rax
0x18002c053  mov     r8d, r14d
0x18002c056  lea     rax, [rsp+0F20h+var_EB0]
0x18002c05b  mov     [rsp+0F20h+var_EF0], r14
0x18002c060  mov     [rsp+0F20h+var_EF8], rax
0x18002c065  mov     rcx, r12
0x18002c068  mov     [rsp+0F20h+phkResult], 1
0x18002c071  call    EventingWriteEvent
0x18002c076  mov     rcx, cs:qword_180169748
0x18002c07d  mov     edx, dword ptr cs:xmmword_180169738
0x18002c083  test    rbx, rbx
0x18002c086  jnz     short loc_18002C0F2
0x18002c088  xor     esi, esi
0x18002c08a  mov     eax, 8007000Eh
0x18002c08f  mov     [rsp+0F20h+var_EB0], esi
0x18002c093  mov     edi, eax
0x18002c095  mov     dword ptr [rbp+0E20h+var_EA0], eax
0x18002c098  test    edx, edx
0x18002c09a  jz      loc_18002D09D
0x18002c0a0  mov     rdx, 4000000000000800h; unsigned __int64
0x18002c0aa  test    qword ptr cs:xmmword_180169738+8, rdx
0x18002c0b1  jz      loc_18002D09D
0x18002c0b7  mov     rax, rcx
0x18002c0ba  and     rax, rdx
0x18002c0bd  cmp     rcx, rax
0x18002c0c0  jnz     loc_18002D09D
0x18002c0c6  lea     rcx, [rbp+0E20h+var_CC0]; unsigned __int16 *
0x18002c0cd  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18002c0d2  lea     rax, [rbp+0E20h+var_CC0]
0x18002c0d9  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002c0dd  inc     rbx
0x18002c0e0  cmp     [rax+rbx*2], si
0x18002c0e4  jnz     short loc_18002C0DD
0x18002c0e6  lea     rax, [rbp+0E20h+var_CC0]
0x18002c0ed  jmp     loc_18002D037
0x18002c0f2  lea     rax, [rbp+0E20h+hKey]
0x18002c0f6  mov     r9d, 20019h; samDesired
0x18002c0fc  xor     r8d, r8d; ulOptions
0x18002c0ff  mov     [rsp+0F20h+phkResult], rax; phkResult
0x18002c104  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Control\\WMI"...
0x18002c10b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002c112  call    cs:__imp_RegOpenKeyExW
0x18002c118  mov     ecx, eax; unsigned int
0x18002c11a  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18002c11f  mov     edi, eax
0x18002c121  test    eax, eax
0x18002c123  jns     short loc_18002C194
0x18002c125  xor     esi, esi
0x18002c127  mov     dword ptr [rbp+0E20h+var_EA0], eax
0x18002c12a  cmp     dword ptr cs:xmmword_180169738, esi
0x18002c130  mov     [rsp+0F20h+var_EB0], esi
0x18002c134  jz      loc_18002D09D
0x18002c13a  mov     rdx, 4000000000000800h; unsigned __int64
0x18002c144  test    qword ptr cs:xmmword_180169738+8, rdx
0x18002c14b  jz      loc_18002D09D
0x18002c151  mov     rax, cs:qword_180169748
0x18002c158  and     rax, rdx
0x18002c15b  cmp     cs:qword_180169748, rax
0x18002c162  jnz     loc_18002D09D
0x18002c168  lea     rcx, [rbp+0E20h+var_C40]; unsigned __int16 *
0x18002c16f  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18002c174  lea     rax, [rbp+0E20h+var_C40]
0x18002c17b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002c17f  inc     rbx
0x18002c182  cmp     [rax+rbx*2], si
0x18002c186  jnz     short loc_18002C17F
0x18002c188  lea     rax, [rbp+0E20h+var_C40]
0x18002c18f  jmp     loc_18002D037
0x18002c194  mov     rcx, [rbp+0E20h+hKey]; hKey
0x18002c198  lea     rax, [rbp+0E20h+var_E88]
0x18002c19c  mov     r9d, 20019h; samDesired
0x18002c1a2  mov     [rsp+0F20h+phkResult], rax; phkResult
0x18002c1a7  xor     r8d, r8d; ulOptions
0x18002c1aa  mov     rdx, rsi; lpSubKey
0x18002c1ad  call    cs:__imp_RegOpenKeyExW
0x18002c1b3  cmp     eax, 2
0x18002c1b6  jz      loc_18002CFC8
0x18002c1bc  mov     ecx, eax; unsigned int
0x18002c1be  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18002c1c3  mov     edi, eax
0x18002c1c5  test    eax, eax
0x18002c1c7  js      loc_18002CFCD
0x18002c1cd  mov     rcx, [rbp+0E20h+var_E88]; HKEY
0x18002c1d1  lea     r8, [rbp+0E20h+var_E90]; unsigned int *
0x18002c1d5  lea     rdx, aStart; "Start"
0x18002c1dc  call    ?PlaiGetRegDword@@YAJPEAUHKEY__@@PEBGPEAK@Z; PlaiGetRegDword(HKEY__ *,ushort const *,ulong *)
0x18002c1e1  xor     ecx, ecx
0x18002c1e3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002c1e7  test    eax, eax
0x18002c1e9  js      loc_18002C27C
0x18002c1ef  mov     edx, ebx
0x18002c1f1  mov     rax, [r13+0]
0x18002c1f5  cmp     [rbp+0E20h+var_E90], ecx
0x18002c1f8  jnz     short loc_18002C1FC
0x18002c1fa  mov     edx, ecx
0x18002c1fc  mov     rax, [rax+190h]
0x18002c203  mov     rcx, r13
0x18002c206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c20b  mov     edi, eax
0x18002c20d  test    eax, eax
0x18002c20f  jns     short loc_18002C27C
0x18002c211  xor     esi, esi
0x18002c213  mov     dword ptr [rbp+0E20h+var_EA0], eax
0x18002c216  cmp     dword ptr cs:xmmword_180169738, esi
0x18002c21c  mov     [rsp+0F20h+var_EB0], esi
0x18002c220  jz      loc_18002D098
0x18002c226  mov     rdx, 4000000000000800h; unsigned __int64
0x18002c230  test    qword ptr cs:xmmword_180169738+8, rdx
0x18002c237  jz      loc_18002D098
0x18002c23d  mov     rax, cs:qword_180169748
0x18002c244  and     rax, rdx
0x18002c247  cmp     cs:qword_180169748, rax
0x18002c24e  jnz     loc_18002D098
0x18002c254  lea     rcx, [rbp+0E20h+var_BC0]; unsigned __int16 *
0x18002c25b  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18002c260  lea     rax, [rbp+0E20h+var_BC0]
0x18002c267  inc     rbx
0x18002c26a  cmp     [rax+rbx*2], si
0x18002c26e  jnz     short loc_18002C267
  ... truncated ...
```
