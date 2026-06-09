# BootTraceSession::Commit(ushort *,ushort *,__MIDL___MIDL_itf_pla_0001_0043_0007,IValueMap * *)

- ea: `0x1800cc090`
- end: `0x1800cdac9`
- name: `?Commit@BootTraceSession@@UEAAJPEAG0W4__MIDL___MIDL_itf_pla_0001_0043_0007@@PEAPEAUIValueMap@@@Z`
- size: `6713`
- prototype: `__int64 __fastcall(BootTraceSession *__hidden this, unsigned __int16 *, unsigned __int16 *, enum __MIDL___MIDL_itf_pla_0001_0043_0007, struct IValueMap **)`
- caller_count: `0`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800106d0`
- `0x180012ef0`
- `0x180024ea0`
- `0x180026850`
- `0x18002b3a0`
- `0x1800429d0`
- `0x180069150`
- `0x18008c6c0`
- `0x180094338`
- `0x1800afac0`
- `0x1800bd0c0`
- `0x1800cc090`
- `0x1800e5f20`
- `0x180113c34`
- `0x1801147b8`
- `0x18011a5f8`
- `0x18013ae76`
- `0x18013aee0`
- `0x18013af70`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cd9dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cd9dc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cc1a8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cc1a8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800cc423`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800cc4c0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800cc423`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800cc4c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cda11`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cda24`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cda11`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cda24`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800ccd45`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800ccd45`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800cc541`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800cc541`
- `RPCRT4!UuidCreate` at `0x1800cd6e3`
- `RPCRT4!UuidCreate` at `0x1800cd6e3`

## string_xrefs

- `0x1800cc165`: `BootTraceSession::Commit`
- `0x1800cc257`: `BootTraceSession::Commit`
- `0x1800cc33d`: `BootTraceSession::Commit`
- `0x1800cd97e`: `BootTraceSession::Commit`

## pseudocode

```c
__int64 __fastcall BootTraceSession::Commit(
        BootTraceSession *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        enum __MIDL___MIDL_itf_pla_0001_0043_0007 a4,
        struct IValueMap **a5)
{
  int v9; // eax
  int v10; // edi
  unsigned __int16 *v11; // r12
  __int64 v12; // rbx
  __int64 v13; // rbx
  int v14; // eax
  __int64 v15; // rbx
  LSTATUS v16; // eax
  int v17; // eax
  __int64 v18; // rbx
  LSTATUS v19; // eax
  int v20; // ecx
  LSTATUS v21; // eax
  int v22; // eax
  __int64 v23; // rbx
  int v24; // eax
  __int64 v25; // rbx
  int v26; // eax
  __int64 v27; // rbx
  int v28; // eax
  __int64 v29; // rbx
  int v30; // eax
  __int64 v31; // rbx
  int v32; // eax
  __int64 v33; // rbx
  int v34; // eax
  __int64 v35; // rbx
  int v36; // eax
  __int64 v37; // rbx
  int v38; // eax
  __int64 v39; // rbx
  int v40; // eax
  __int64 v41; // rbx
  int v42; // eax
  __int64 v43; // rbx
  int v44; // eax
  __int64 v45; // rbx
  int v46; // eax
  __int64 v47; // rbx
  const unsigned __int16 *bstrVal; // r8
  int v49; // eax
  __int64 v50; // rbx
  LSTATUS v51; // eax
  __int64 v52; // rbx
  int v53; // eax
  __int64 v54; // rbx
  int v55; // eax
  __int64 v56; // rbx
  int v57; // eax
  __int64 v58; // rbx
  int v59; // eax
  __int64 v60; // rbx
  __int64 v61; // rax
  int v62; // eax
  __int64 v63; // rbx
  LONG lVal; // r8d
  int v65; // eax
  BootTraceSession *v66; // rcx
  __int64 v67; // rbx
  int v68; // eax
  __int64 v69; // rbx
  int v70; // eax
  BootTraceSession *v71; // rcx
  __int64 v72; // rbx
  __int64 v73; // rbx
  int TraceDataProvider; // eax
  int v75; // eax
  int Ul; // eax
  int v77; // eax
  int v78; // eax
  int v79; // eax
  int v80; // eax
  int v81; // eax
  _WORD *v82; // rcx
  RPC_STATUS v83; // eax
  int v84; // eax
  int v85; // eax
  int v86; // eax
  int v87; // eax
  struct IValueMap *v88; // rcx
  int phkResult; // [rsp+20h] [rbp-E0h]
  _DWORD v91[4]; // [rsp+70h] [rbp-90h] BYREF
  UUID v92; // [rsp+80h] [rbp-80h] BYREF
  HKEY v93; // [rsp+90h] [rbp-70h] BYREF
  struct ITraceDataCollector *v94; // [rsp+98h] [rbp-68h] BYREF
  struct tagVARIANT v95; // [rsp+A0h] [rbp-60h] BYREF
  int v96; // [rsp+B8h] [rbp-48h] BYREF
  enum __MIDL___MIDL_itf_pla_0001_0043_0005 v97; // [rsp+BCh] [rbp-44h] BYREF
  HKEY hKey; // [rsp+C0h] [rbp-40h] BYREF
  struct ITraceDataProvider *v99; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v100; // [rsp+D0h] [rbp-30h] BYREF
  struct IValueMap *v101; // [rsp+D8h] [rbp-28h] BYREF
  DWORD dwDisposition[4]; // [rsp+E0h] [rbp-20h] BYREF
  UUID Buf1; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 v104[64]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 v105[64]; // [rsp+180h] [rbp+80h] BYREF
  unsigned __int16 v106[64]; // [rsp+200h] [rbp+100h] BYREF
  unsigned __int16 v107[64]; // [rsp+280h] [rbp+180h] BYREF
  unsigned __int16 v108[64]; // [rsp+300h] [rbp+200h] BYREF
  unsigned __int16 v109[64]; // [rsp+380h] [rbp+280h] BYREF
  unsigned __int16 v110[64]; // [rsp+400h] [rbp+300h] BYREF
  unsigned __int16 v111[64]; // [rsp+480h] [rbp+380h] BYREF
  unsigned __int16 v112[64]; // [rsp+500h] [rbp+400h] BYREF
  unsigned __int16 v113[64]; // [rsp+580h] [rbp+480h] BYREF
  unsigned __int16 v114[64]; // [rsp+600h] [rbp+500h] BYREF
  unsigned __int16 v115[64]; // [rsp+680h] [rbp+580h] BYREF
  unsigned __int16 v116[64]; // [rsp+700h] [rbp+600h] BYREF
  unsigned __int16 v117[64]; // [rsp+780h] [rbp+680h] BYREF
  unsigned __int16 v118[64]; // [rsp+800h] [rbp+700h] BYREF
  unsigned __int16 v119[64]; // [rsp+880h] [rbp+780h] BYREF
  unsigned __int16 v120[64]; // [rsp+900h] [rbp+800h] BYREF
  unsigned __int16 v121[64]; // [rsp+980h] [rbp+880h] BYREF
  unsigned __int16 v122[64]; // [rsp+A00h] [rbp+900h] BYREF
  unsigned __int16 v123[64]; // [rsp+A80h] [rbp+980h] BYREF
  unsigned __int16 v124[64]; // [rsp+B00h] [rbp+A00h] BYREF
  unsigned __int16 v125[64]; // [rsp+B80h] [rbp+A80h] BYREF
  unsigned __int16 v126[64]; // [rsp+C00h] [rbp+B00h] BYREF
  unsigned __int16 v127[64]; // [rsp+C80h] [rbp+B80h] BYREF
  unsigned __int16 v128[64]; // [rsp+D00h] [rbp+C00h] BYREF
  unsigned __int16 v129[64]; // [rsp+D80h] [rbp+C80h] BYREF
  unsigned __int16 v130[64]; // [rsp+E00h] [rbp+D00h] BYREF
  unsigned __int16 v131[64]; // [rsp+E80h] [rbp+D80h] BYREF
  unsigned __int16 v132[64]; // [rsp+F00h] [rbp+E00h] BYREF
  unsigned __int16 v133[64]; // [rsp+F80h] [rbp+E80h] BYREF
  unsigned __int16 v134[64]; // [rsp+1000h] [rbp+F00h] BYREF
  unsigned __int16 v135[64]; // [rsp+1080h] [rbp+F80h] BYREF
  unsigned __int16 v136[64]; // [rsp+1100h] [rbp+1000h] BYREF
  unsigned __int16 v137[64]; // [rsp+1180h] [rbp+1080h] BYREF
  unsigned __int16 v138[64]; // [rsp+1200h] [rbp+1100h] BYREF
  unsigned __int16 v139[64]; // [rsp+1280h] [rbp+1180h] BYREF
  unsigned __int16 v140[64]; // [rsp+1300h] [rbp+1200h] BYREF
  unsigned __int16 v141[64]; // [rsp+1380h] [rbp+1280h] BYREF
  unsigned __int16 v142[64]; // [rsp+1400h] [rbp+1300h] BYREF
  unsigned __int16 v143[64]; // [rsp+1480h] [rbp+1380h] BYREF

  hKey = 0;
  v93 = 0;
  dwDisposition[0] = 0;
  memset(&v95, 0, sizeof(v95));
  v97 = plaTimeStamp;
  Buf1 = 0;
  v94 = 0;
  v99 = 0;
  v100 = 0;
  v96 = 0;
  v101 = 0;
  PlaiVariantInit(&v95);
  v91[0] = *((_DWORD *)this + 14);
  *(_QWORD *)&v92.Data1 = this;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000400LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000400LL) )
  {
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_METHOD, 3, "BootTraceSession::Commit", 25, &v92, 8, v91, 4);
  }
  if ( *((_DWORD *)this + 2) )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v9 = DataCollectorSet::Commit(this, a2, a3, a4, &v101);
  v10 = v9;
  if ( v9 >= 0 )
  {
    v11 = (unsigned __int16 *)PlaiAlloc(0x50u, 1, 0, byte_180147320, phkResult);
    if ( !v11 )
    {
      v10 = -2147024882;
      v92.Data1 = 0;
      v91[0] = -2147024882;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_310;
      }
      PlaiWhoAmI(v105, 0x4000000000000800uLL);
      v13 = -1;
      do
        ++v13;
      while ( v105[v13] );
      goto LABEL_309;
    }
    v14 = (*(__int64 (__fastcall **)(BootTraceSession *, struct ITraceDataCollector **))(*(_QWORD *)this + 656LL))(
            this,
            &v94);
    v10 = v14;
    if ( v14 < 0 )
    {
      v91[0] = v14;
      v92.Data1 = 0;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_310;
      }
      PlaiWhoAmI(v106, 0x4000000000000800uLL);
      v15 = -1;
      do
        ++v15;
      while ( v106[v15] );
      goto LABEL_309;
    }
    v16 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\WMI\\AutoLogger", 0, 0x2001Fu, &hKey);
    v17 = PlaiHResultFromWin32(v16);
    v10 = v17;
    if ( v17 < 0 )
    {
      v91[0] = v17;
      v92.Data1 = 0;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_310;
      }
      PlaiWhoAmI(v107, 0x4000000000000800uLL);
      v18 = -1;
      do
        ++v18;
      while ( v107[v18] );
      goto LABEL_309;
    }
    v19 = RegOpenKeyExW(hKey, a2, 0, 0x2001Fu, &v93);
    if ( (int)PlaiHResultFromWin32(v19) >= 0 )
    {
      if ( (a4 & 0xF) == 1 )
      {
        v10 = -2144337737;
        goto LABEL_310;
      }
      v20 = 1;
    }
    else
    {
      v20 = 0;
      if ( (a4 & 0xF) == 2 )
      {
        v10 = -2144337918;
        goto LABEL_310;
      }
    }
    if ( (a4 & 0x1000) != 0 )
    {
      v10 = 0;
      goto LABEL_310;
    }
    if ( !v20 )
    {
      v21 = RegCreateKeyExW(hKey, a2, 0, 0, 0, 0x2001Fu, 0, &v93, dwDisposition);
      v22 = PlaiHResultFromWin32(v21);
      v10 = v22;
      if ( v22 < 0 )
      {
        v92.Data1 = 0;
        v91[0] = v22;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_310;
        }
        PlaiWhoAmI(v108, 0x4000000000000800uLL);
        v23 = -1;
        do
          ++v23;
        while ( v108[v23] );
        goto LABEL_309;
      }
    }
    PlaiVariantClear(&v95);
    v24 = ((__int64 (__fastcall *)(struct ITraceDataCollector *, ULONG *))v94->lpVtbl->get_BufferSize)(
            v94,
            &v95.decVal.Lo32);
    v10 = v24;
    if ( v24 < 0 )
    {
      v92.Data1 = 0;
      v91[0] = v24;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_310;
      }
      PlaiWhoAmI(v109, 0x4000000000000800uLL);
      v25 = -1;
      do
        ++v25;
      while ( v109[v25] );
      goto LABEL_309;
    }
    v95.vt = 19;
    v26 = PlaiSetRegDword(v93, L"BufferSize", v95.cyVal.Lo);
    v10 = v26;
    if ( v26 < 0 )
    {
      v92.Data1 = 0;
      v91[0] = v26;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_310;
      }
      PlaiWhoAmI(v110, 0x4000000000000800uLL);
      v27 = -1;
      do
        ++v27;
      while ( v110[v27] );
      goto LABEL_309;
    }
    PlaiVariantClear(&v95);
    v28 = ((__int64 (__fastcall *)(struct ITraceDataCollector *, ULONG *))v94->lpVtbl->get_FlushTimer)(
            v94,
            &v95.decVal.Lo32);
    v10 = v28;
    if ( v28 < 0 )
    {
      v92.Data1 = 0;
      v91[0] = v28;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_310;
      }
      PlaiWhoAmI(v111, 0x4000000000000800uLL);
      v29 = -1;
      do
        ++v29;
      while ( v111[v29] );
      goto LABEL_309;
    }
    v95.vt = 19;
    v30 = PlaiSetRegDword(v93, L"FlushTimer", v95.cyVal.Lo);
    v10 = v30;
    if ( v30 < 0 )
    {
      v92.Data1 = 0;
      v91[0] = v30;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_310;
      }
      PlaiWhoAmI(v112, 0x4000000000000800uLL);
      v31 = -1;
      do
        ++v31;
      while ( v112[v31] );
      goto LABEL_309;
    }
    PlaiVariantClear(&v95);
    v32 = ((__int64 (__fastcall *)(struct ITraceDataCollector *, ULONG *))v94->lpVtbl->get_MaximumBuffers)(
            v94,
            &v95.decVal.Lo32);
    v10 = v32;
    if ( v32 < 0 )
    {
      v92.Data1 = 0;
      v91[0] = v32;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_310;
      }
      PlaiWhoAmI(v113, 0x4000000000000800uLL);
      v33 = -1;
      do
        ++v33;
      while ( v113[v33] );
      goto LABEL_309;
    }
    v95.vt = 19;
    v34 = PlaiSetRegDword(v93, L"MaximumBuffers", v95.cyVal.Lo);
    v10 = v34;
    if ( v34 < 0 )
    {
      v92.Data1 = 0;
      v91[0] = v34;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_310;
      }
      PlaiWhoAmI(v114, 0x4000000000000800uLL);
      v35 = -1;
      do
        ++v35;
      while ( v114[v35] );
      goto LABEL_309;
    }
    PlaiVariantClear(&v95);
    v36 = ((__int64 (__fastcall *)(struct ITraceDataCollector *, ULONG *))v94->lpVtbl->get_MinimumBuffers)(
            v94,
            &v95.decVal.Lo32);
    v10 = v36;
    if ( v36 < 0 )
    {
      v92.Data1 = 0;
      v91[0] = v36;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_310;
      }
      PlaiWhoAmI(v115, 0x4000000000000800uLL);
      v37 = -1;
      do
        ++v37;
      while ( v115[v37] );
      goto LABEL_309;
    }
    v95.vt = 19;
    v38 = PlaiSetRegDword(v93, L"MinimumBuffers", v95.cyVal.Lo);
    v10 = v38;
    if ( v38 < 0 )
    {
      v92.Data1 = 0;
      v91[0] = v38;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_310;
      }
      PlaiWhoAmI(v116, 0x4000000000000800uLL);
      v39 = -1;
      do
        ++v39;
      while ( v116[v39] );
      goto LABEL_309;
    }
    PlaiVariantClear(&v95);
    v40 = (*(__int64 (__fastcall **)(BootTraceSession *, CY *))(*(_QWORD *)this + 392LL))(this, &v95.cyVal);
    v10 = v40;
    if ( v40 < 0 )
    {
      v92.Data1 = 0;
      v91[0] = v40;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_310;
      }
      PlaiWhoAmI(v117, 0x4000000000000800uLL);
      v41 = -1;
      do
        ++v41;
      while ( v117[v41] );
      goto LABEL_309;
    }
    v95.vt = 11;
    v95.lVal = v95.iVal != 0;
    v42 = PlaiSetRegDword(v93, L"Start", v95.cyVal.Lo);
    v10 = v42;
    if ( v42 < 0 )
    {
      v92.Data1 = 0;
      v91[0] = v42;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_310;
      }
      PlaiWhoAmI(v118, 0x4000000000000800uLL);
      v43 = -1;
      do
        ++v43;
      while ( v118[v43] );
      goto LABEL_309;
    }
    v44 = ((__int64 (__fastcall *)(struct ITraceDataCollector *, int *))v94->lpVtbl->get_StreamMode)(v94, &v96);
    v10 = v44;
    if ( v44 < 0 )
    {
      v92.Data1 = 0;
      v91[0] = v44;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_310;
      }
      PlaiWhoAmI(v119, 0x4000000000000800uLL);
      v45 = -1;
      do
        ++v45;
      while ( v119[v45] );
      goto LABEL_309;
    }
    if ( (v96 & 1) != 0 )
    {
      PlaiVariantClear(&v95);
      v46 = ((__int64 (__fastcall *)(struct ITraceDataCollector *, ULONG *))v94->lpVtbl->get_OutputLocation)(
              v94,
              &v95.decVal.Lo32);
      v10 = v46;
      if ( v46 < 0 )
      {
        v92.Data1 = 0;
        v91[0] = v46;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_310;
        }
        PlaiWhoAmI(v120, 0x4000000000000800uLL);
        v47 = -1;
        do
          ++v47;
        while ( v120[v47] );
        goto LABEL_309;
      }
      bstrVal = (const unsigned __int16 *)&szPassword;
      v95.vt = 8;
      if ( v95.llVal )
        bstrVal = v95.bstrVal;
      v49 = PlaiSetRegString(v93, L"FileName", bstrVal);
      v10 = v49;
      if ( v49 < 0 )
      {
        v92.Data1 = 0;
        v91[0] = v49;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_310;
        }
        PlaiWhoAmI(v121, 0x4000000000000800uLL);
        v50 = -1;
        do
          ++v50;
        while ( v121[v50] );
        goto LABEL_309;
      }
    }
    else
    {
      v51 = RegDeleteValueW(v93, L"FileName");
      v10 = PlaiHResultFromWin32(v51);
      if ( (int)(v10 + 0x80000000) >= 0 && v10 != -2147024894 )
      {
        v92.Data1 = 0;
        v91[0] = v10;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_310;
        }
        PlaiWhoAmI(v122, 0x4000000000000800uLL);
        v52 = -1;
        do
          ++v52;
        while ( v122[v52] );
        goto LABEL_309;
      }
    }
    v53 = ((__int64 (__fastcall *)(struct ITraceDataCollector *, enum __MIDL___MIDL_itf_pla_0001_0043_0005 *))v94->lpVtbl->get_ClockType)(
            v94,
            &v97);
    v10 = v53;
    if ( v53 < 0 )
    {
      v92.Data1 = 0;
      v91[0] = v53;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_310;
      }
      PlaiWhoAmI(v123, 0x4000000000000800uLL);
      v54 = -1;
      do
        ++v54;
      while ( v123[v54] );
      goto LABEL_309;
    }
    PlaiVariantClear(&v95);
    v95.vt = 3;
    v95.lVal = PlaiClockTypeToDword(v97);
    v55 = PlaiSetRegDword(v93, L"ClockType", v95.cyVal.Lo);
    v10 = v55;
    if ( v55 < 0 )
    {
      v92.Data1 = 0;
      v91[0] = v55;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_310;
      }
      PlaiWhoAmI(v124, 0x4000000000000800uLL);
      v56 = -1;
      do
        ++v56;
      while ( v124[v56] );
      goto LABEL_309;
    }
    PlaiVariantClear(&v95);
    v57 = (*(__int64 (__fastcall **)(BootTraceSession *, CY *))(*(_QWORD *)this + 224LL))(this, &v95.cyVal);
    v10 = v57;
    if ( v57 < 0 )
    {
      v92.Data1 = 0;
      v91[0] = v57;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_310;
      }
      PlaiWhoAmI(v125, 0x4000000000000800uLL);
      v58 = -1;
      do
        ++v58;
      while ( v125[v58] );
      goto LABEL_309;
    }
    v95.vt = 19;
    v59 = PlaiSetRegDword(v93, L"MaxFileSize", v95.cyVal.Lo);
    v10 = v59;
    if ( v59 < 0 )
    {
      v92.Data1 = 0;
      v91[0] = v59;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_310;
      }
      PlaiWhoAmI(v126, 0x4000000000000800uLL);
      v60 = -1;
      do
        ++v60;
      while ( v126[v60] );
      goto LABEL_309;
    }
    v61 = *(_QWORD *)this;
    v95.vt = 19;
    v62 = (*(__int64 (__fastcall **)(BootTraceSession *, CY *))(v61 + 616))(this, &v95.cyVal);
    v10 = v62;
    if ( v62 < 0 )
    {
      v92.Data1 = 0;
      v91[0] = v62;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_310;
      }
      PlaiWhoAmI(v127, 0x4000000000000800uLL);
      v63 = -1;
      do
        ++v63;
      while ( v127[v63] );
      goto LABEL_309;
    }
    lVal = v95.lVal;
    if ( (v96 & 1) != 0 )
    {
      lVal = v95.lVal | 0x1200;
      v95.lVal |= 0x1200u;
    }
    if ( (v96 & 2) != 0 )
    {
      lVal |= 0x100u;
      v95.lVal = lVal;
    }
    if ( (v96 & 4) != 0 )
    {
      lVal |= 0x400u;
      v95.lVal = lVal;
    }
    v65 = PlaiSetRegDword(v93, L"LogFileMode", lVal);
    v10 = v65;
    if ( v65 < 0 )
    {
      v92.Data1 = 0;
      v91[0] = v65;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_310;
      }
      PlaiWhoAmI(v128, 0x4000000000000800uLL);
      v67 = -1;
      do
        ++v67;
      while ( v128[v67] );
      goto LABEL_309;
    }
    v68 = BootTraceSession::DeleteProviders(v66, v93);
    v10 = v68;
    if ( v68 < 0 )
    {
      v92.Data1 = 0;
      v91[0] = v68;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_310;
      }
      PlaiWhoAmI(v129, 0x4000000000000800uLL);
      v69 = -1;
      do
        ++v69;
      while ( v129[v69] );
      goto LABEL_309;
    }
    PlaiVariantClear(&v95);
    v70 = ((__int64 (__fastcall *)(struct ITraceDataCollector *, ULONG *))v94->lpVtbl->get_IsKernelTrace)(
            v94,
            &v95.decVal.Lo32);
    v10 = v70;
    if ( v70 < 0 )
    {
      v92.Data1 = 0;
      v91[0] = v70;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_310;
      }
      PlaiWhoAmI(v130, 0x4000000000000800uLL);
      v72 = -1;
      do
        ++v72;
      while ( v130[v72] );
      goto LABEL_309;
    }
    v73 = -1;
    v95.vt = 11;
    if ( v95.iVal == -1 )
    {
      TraceDataProvider = TraceDataCollector::get_TraceDataProvider(v94, &v99);
      v10 = TraceDataProvider;
      if ( TraceDataProvider < 0 )
      {
        v92.Data1 = 0;
        v91[0] = TraceDataProvider;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_310;
        }
        PlaiWhoAmI(v131, 0x4000000000000800uLL);
        do
          ++v73;
        while ( v131[v73] );
        goto LABEL_309;
      }
      v75 = ((__int64 (__fastcall *)(struct ITraceDataProvider *, __int64 *))v99->lpVtbl->get_KeywordsAny)(v99, &v100);
      v10 = v75;
      if ( v75 < 0 )
      {
        v92.Data1 = 0;
        v91[0] = v75;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_310;
        }
        PlaiWhoAmI(v132, 0x4000000000000800uLL);
        do
          ++v73;
        while ( v132[v73] );
        goto LABEL_309;
      }
      PlaiVariantClear(&v95);
      Ul = PlaiGetUlValue<IValueMap>(v100, &v95.decVal.Lo32);
      v10 = Ul;
      if ( Ul < 0 )
      {
        v92.Data1 = 0;
        v91[0] = Ul;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_310;
        }
        PlaiWhoAmI(v133, 0x4000000000000800uLL);
        do
          ++v73;
        while ( v133[v73] );
        goto LABEL_309;
      }
      v77 = PlaiSetRegDword(v93, L"EnableKernelFlags", v95.cyVal.Lo);
      v10 = v77;
      if ( v77 < 0 )
      {
        v92.Data1 = 0;
        v91[0] = v77;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_310;
        }
        PlaiWhoAmI(v134, 0x4000000000000800uLL);
        do
          ++v73;
        while ( v134[v73] );
        goto LABEL_309;
      }
      v78 = ((__int64 (__fastcall *)(struct ITraceDataProvider *, UUID *))v99->lpVtbl->get_Guid)(v99, &Buf1);
      v10 = v78;
      if ( v78 < 0 )
      {
        v92.Data1 = 0;
        v91[0] = v78;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_310;
        }
        PlaiWhoAmI(v135, 0x4000000000000800uLL);
        do
          ++v73;
        while ( v135[v73] );
        goto LABEL_309;
      }
      v92 = Buf1;
      v79 = ((__int64 (__fastcall *)(struct ITraceDataCollector *, UUID *))v94->lpVtbl->put_Guid)(v94, &v92);
      v10 = v79;
      if ( v79 < 0 )
      {
        v92.Data1 = 0;
        v91[0] = v79;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_310;
        }
        PlaiWhoAmI(v136, 0x4000000000000800uLL);
        do
          ++v73;
        while ( v136[v73] );
        goto LABEL_309;
      }
    }
    else
    {
      v80 = BootTraceSession::CommitProviders(v71, v93, v94);
      v10 = v80;
      if ( v80 < 0 )
      {
        v92.Data1 = 0;
        v91[0] = v80;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_310;
        }
        PlaiWhoAmI(v137, 0x4000000000000800uLL);
        do
          ++v73;
        while ( v137[v73] );
        goto LABEL_309;
      }
    }
    v81 = ((__int64 (__fastcall *)(struct ITraceDataCollector *, UUID *))v94->lpVtbl->get_Guid)(v94, &Buf1);
    v10 = v81;
    if ( v81 < 0 )
    {
      v92.Data1 = 0;
      v91[0] = v81;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_310;
      }
      PlaiWhoAmI(v138, 0x4000000000000800uLL);
      do
        ++v73;
      while ( v138[v73] );
      goto LABEL_309;
    }
    v82 = (_WORD *)*((_QWORD *)this + 31);
    if ( !v82 || !*v82 )
      goto LABEL_296;
    if ( !memcmp_0(&Buf1, &NullGuid, 0x10u) )
    {
      v83 = UuidCreate(&Buf1);
      v10 = v83;
      if ( v83 < 0 )
      {
        v92.Data1 = 0;
        v91[0] = v83;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_310;
        }
        PlaiWhoAmI(v139, 0x4000000000000800uLL);
        do
          ++v73;
        while ( v139[v73] );
        goto LABEL_309;
      }
      v92 = Buf1;
      v84 = ((__int64 (__fastcall *)(struct ITraceDataCollector *, UUID *))v94->lpVtbl->put_Guid)(v94, &v92);
      v10 = v84;
      if ( v84 < 0 )
      {
        v92.Data1 = 0;
        v91[0] = v84;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_310;
        }
        PlaiWhoAmI(v140, 0x4000000000000800uLL);
        do
          ++v73;
        while ( v140[v73] );
        goto LABEL_309;
      }
    }
    v85 = PlaiSetEtwSecurity(&Buf1, *((const unsigned __int16 **)this + 31));
    v10 = v85;
    if ( v85 < 0 )
    {
      v92.Data1 = 0;
      v91[0] = v85;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_310;
      }
      PlaiWhoAmI(v141, 0x4000000000000800uLL);
      do
        ++v73;
      while ( v141[v73] );
    }
    else
    {
LABEL_296:
      v86 = PlaiGuidToString(&Buf1, v11, 0x28u);
      v10 = v86;
      if ( v86 >= 0 )
      {
        v87 = PlaiSetRegString(v93, L"Guid", v11);
        v10 = v87;
        if ( v87 >= 0 )
          goto LABEL_310;
        v92.Data1 = 0;
        v91[0] = v87;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_310;
        }
        PlaiWhoAmI(v143, 0x4000000000000800uLL);
        do
          ++v73;
        while ( v143[v73] );
      }
      else
      {
        v92.Data1 = 0;
        v91[0] = v86;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_310;
        }
        PlaiWhoAmI(v142, 0x4000000000000800uLL);
        do
          ++v73;
        while ( v142[v73] );
      }
    }
LABEL_309:
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, v91, 4, byte_180147320, 1, &v92, 4);
    goto LABEL_310;
  }
  v92.Data1 = v9;
  v11 = 0;
  v91[0] = 0;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v104, 0x4000000000000800uLL);
    v12 = -1;
    do
      ++v12;
    while ( v104[v12] );
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v92, 4, byte_180147320, 1, v91, 4);
  }
LABEL_310:
  if ( *((_DWORD *)this + 2) )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( v10 >= 0 && a5 )
  {
    v88 = v101;
    *a5 = v101;
    ((void (__fastcall *)(struct IValueMap *))v88->lpVtbl->AddRef)(v88);
  }
  PlaiVariantClear(&v95);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v93 )
  {
    RegCloseKey(v93);
    v93 = 0;
  }
  if ( v99 )
  {
    ((void (__fastcall *)(struct ITraceDataProvider *))v99->lpVtbl->Release)(v99);
    v99 = 0;
  }
  if ( v100 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v100 + 16LL))(v100);
    v100 = 0;
  }
  if ( v94 )
  {
    ((void (__fastcall *)(struct ITraceDataCollector *))v94->lpVtbl->Release)(v94);
    v94 = 0;
  }
  if ( v101 )
  {
    ((void (__fastcall *)(struct IValueMap *))v101->lpVtbl->Release)(v101);
    v101 = 0;
  }
  if ( v11 )
    PlaiFree(v11, 1);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800cc090  push    rbp
0x1800cc092  push    rbx
0x1800cc093  push    rsi
0x1800cc094  push    rdi
0x1800cc095  push    r12
0x1800cc097  push    r13
0x1800cc099  push    r14
0x1800cc09b  push    r15
0x1800cc09d  lea     rbp, [rsp-1418h]
0x1800cc0a5  mov     eax, 1518h
0x1800cc0aa  call    _alloca_probe
0x1800cc0af  sub     rsp, rax
0x1800cc0b2  mov     rax, cs:__security_cookie
0x1800cc0b9  xor     rax, rsp
0x1800cc0bc  mov     [rbp+1450h+var_50], rax
0x1800cc0c3  mov     r13, [rbp+1450h+arg_20]
0x1800cc0ca  xor     r14d, r14d
0x1800cc0cd  xorps   xmm0, xmm0
0x1800cc0d0  mov     [rbp+1450h+hKey], r14
0x1800cc0d4  mov     r15, rcx
0x1800cc0d7  mov     [rbp+1450h+var_14C0], r14
0x1800cc0db  xor     eax, eax
0x1800cc0dd  mov     [rbp+1450h+dwDisposition], r14d
0x1800cc0e1  lea     rcx, [rbp+1450h+var_14B0]; struct tagVARIANT *
0x1800cc0e5  mov     qword ptr [rbp+1450h+var_14B0+10h], rax
0x1800cc0e9  movups  xmmword ptr [rbp+1450h+var_14B0], xmm0
0x1800cc0ed  mov     [rbp+1450h+var_1494], r14d
0x1800cc0f1  mov     ebx, r9d
0x1800cc0f4  movups  [rbp+1450h+Buf1], xmm0
0x1800cc0f8  mov     [rbp+1450h+var_14B8], r14
0x1800cc0fc  mov     rdi, r8
0x1800cc0ff  mov     [rbp+1450h+var_1488], r14
0x1800cc103  mov     rsi, rdx
0x1800cc106  mov     [rbp+1450h+var_1480], r14
0x1800cc10a  mov     [rbp+1450h+var_1498], r14d
0x1800cc10e  mov     [rbp+1450h+var_1478], r14
0x1800cc112  call    ?PlaiVariantInit@@YAJPEAUtagVARIANT@@@Z; PlaiVariantInit(tagVARIANT *)
0x1800cc117  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800cc11e  mov     eax, [r15+38h]
0x1800cc122  mov     [rsp+1550h+var_14E0], eax
0x1800cc126  mov     qword ptr [rbp+1450h+var_14D0], r15
0x1800cc12a  jz      short loc_1800CC19E
0x1800cc12c  mov     rdx, 4000000000000400h
0x1800cc136  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800cc13d  jz      short loc_1800CC19E
0x1800cc13f  mov     rax, cs:qword_180169748
0x1800cc146  and     rax, rdx
0x1800cc149  cmp     cs:qword_180169748, rax
0x1800cc150  jnz     short loc_1800CC19E
0x1800cc152  mov     [rsp+1550h+lpdwDisposition], 4
0x1800cc15b  lea     rax, [rsp+1550h+var_14E0]
0x1800cc160  mov     [rsp+1550h+var_1518], rax
0x1800cc165  lea     r9, aBoottracesessi; "BootTraceSession::Commit"
0x1800cc16c  lea     rax, [rbp+1450h+var_14D0]
0x1800cc170  mov     [rsp+1550h+lpSecurityAttributes], 8
0x1800cc179  mov     qword ptr [rsp+1550h+samDesired], rax
0x1800cc17e  lea     r8d, [r14+3]
0x1800cc182  lea     rdx, PLA_EVENT_METHOD
0x1800cc189  mov     [rsp+1550h+phkResult], 19h
0x1800cc192  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800cc199  call    EventingWriteEvent
0x1800cc19e  cmp     [r15+8], r14d
0x1800cc1a2  jz      short loc_1800CC1AE
0x1800cc1a4  lea     rcx, [r15+10h]; lpCriticalSection
0x1800cc1a8  call    cs:__imp_EnterCriticalSection
0x1800cc1ae  lea     rax, [rbp+1450h+var_1478]
0x1800cc1b2  mov     r9d, ebx; enum __MIDL___MIDL_itf_pla_0001_0043_0007
0x1800cc1b5  mov     r8, rdi; unsigned __int16 *
0x1800cc1b8  mov     [rsp+1550h+phkResult], rax; int
0x1800cc1bd  mov     rdx, rsi; unsigned __int16 *
0x1800cc1c0  mov     rcx, r15; this
0x1800cc1c3  call    ?Commit@DataCollectorSet@@UEAAJPEAG0W4__MIDL___MIDL_itf_pla_0001_0043_0007@@PEAPEAUIValueMap@@@Z; DataCollectorSet::Commit(ushort *,ushort *,__MIDL___MIDL_itf_pla_0001_0043_0007,IValueMap * *)
0x1800cc1c8  mov     edi, eax
0x1800cc1ca  test    eax, eax
0x1800cc1cc  jns     loc_1800CC293
0x1800cc1d2  xor     esi, esi
0x1800cc1d4  mov     dword ptr [rbp+1450h+var_14D0], eax
0x1800cc1d7  cmp     dword ptr cs:xmmword_180169738, esi
0x1800cc1dd  mov     r12d, esi
0x1800cc1e0  mov     [rsp+1550h+var_14E0], esi
0x1800cc1e4  jz      loc_1800CD9D2
0x1800cc1ea  mov     rdx, 4000000000000800h; unsigned __int64
0x1800cc1f4  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800cc1fb  jz      loc_1800CD9D2
0x1800cc201  mov     rax, cs:qword_180169748
0x1800cc208  and     rax, rdx
0x1800cc20b  cmp     cs:qword_180169748, rax
0x1800cc212  jnz     loc_1800CD9D2
0x1800cc218  lea     rcx, [rbp+1450h+var_1450]; unsigned __int16 *
0x1800cc21c  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800cc221  lea     rax, [rbp+1450h+var_1450]
0x1800cc225  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800cc229  inc     rbx
0x1800cc22c  cmp     [rax+rbx*2], si
0x1800cc230  jnz     short loc_1800CC229
0x1800cc232  lea     rax, [rbp+1450h+var_1450]
0x1800cc236  mov     edx, 4
0x1800cc23b  lea     ecx, [rbx+rbx]
0x1800cc23e  add     rcx, 2
0x1800cc242  lea     r14, byte_180147320
0x1800cc249  mov     [rsp+1550h+var_14F0], rcx
0x1800cc24e  lea     r9, [rbp+1450h+var_14D0]
0x1800cc252  mov     [rsp+1550h+var_14F8], rax
0x1800cc257  lea     rax, aBoottracesessi; "BootTraceSession::Commit"
0x1800cc25e  mov     [rsp+1550h+var_1500], 19h
0x1800cc267  mov     [rsp+1550h+var_1508], rax
0x1800cc26c  lea     rax, [rsp+1550h+var_14E0]
0x1800cc271  mov     [rsp+1550h+lpdwDisposition], rdx
0x1800cc276  mov     [rsp+1550h+var_1518], rax
0x1800cc27b  mov     [rsp+1550h+lpSecurityAttributes], 1
0x1800cc284  mov     qword ptr [rsp+1550h+samDesired], r14
0x1800cc289  mov     [rsp+1550h+phkResult], rdx
0x1800cc28e  jmp     loc_1800CD9B9
0x1800cc293  xor     r8d, r8d; int
0x1800cc296  lea     r14, byte_180147320
0x1800cc29d  mov     r9, r14; char *
0x1800cc2a0  lea     edx, [r8+1]; int
0x1800cc2a4  lea     ecx, [rdx+4Fh]; dwBytes
0x1800cc2a7  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x1800cc2ac  mov     r12, rax
0x1800cc2af  test    rax, rax
0x1800cc2b2  jnz     loc_1800CC378
0x1800cc2b8  xor     esi, esi
0x1800cc2ba  mov     edi, 8007000Eh
0x1800cc2bf  cmp     dword ptr cs:xmmword_180169738, esi
0x1800cc2c5  mov     dword ptr [rbp+1450h+var_14D0], esi
0x1800cc2c8  mov     [rsp+1550h+var_14E0], edi
0x1800cc2cc  jz      loc_1800CD9D2
0x1800cc2d2  mov     rdx, 4000000000000800h; unsigned __int64
0x1800cc2dc  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800cc2e3  jz      loc_1800CD9D2
0x1800cc2e9  mov     rax, cs:qword_180169748
0x1800cc2f0  and     rax, rdx
0x1800cc2f3  cmp     cs:qword_180169748, rax
0x1800cc2fa  jnz     loc_1800CD9D2
0x1800cc300  lea     rcx, [rbp+1450h+var_13D0]; unsigned __int16 *
0x1800cc307  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800cc30c  lea     rax, [rbp+1450h+var_13D0]
0x1800cc313  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800cc317  inc     rbx
0x1800cc31a  cmp     [rax+rbx*2], si
0x1800cc31e  jnz     short loc_1800CC317
0x1800cc320  lea     rax, [rbp+1450h+var_13D0]
0x1800cc327  mov     edx, 4
0x1800cc32c  lea     ecx, [rbx+rbx]
0x1800cc32f  add     rcx, 2
0x1800cc333  mov     [rsp+1550h+var_14F0], rcx
0x1800cc338  mov     [rsp+1550h+var_14F8], rax
0x1800cc33d  lea     rax, aBoottracesessi; "BootTraceSession::Commit"
0x1800cc344  mov     [rsp+1550h+var_1500], 19h
0x1800cc34d  mov     [rsp+1550h+var_1508], rax
0x1800cc352  lea     rax, [rbp+1450h+var_14D0]
0x1800cc356  mov     [rsp+1550h+lpdwDisposition], rdx
0x1800cc35b  mov     [rsp+1550h+var_1518], rax
0x1800cc360  mov     [rsp+1550h+lpSecurityAttributes], 1
0x1800cc369  mov     qword ptr [rsp+1550h+samDesired], r14
0x1800cc36e  mov     [rsp+1550h+phkResult], rdx
0x1800cc373  jmp     loc_1800CD9B4
0x1800cc378  mov     rax, [r15]
0x1800cc37b  lea     rdx, [rbp+1450h+var_14B8]
0x1800cc37f  mov     rcx, r15
0x1800cc382  mov     rax, [rax+290h]
0x1800cc389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cc38e  mov     edi, eax
0x1800cc390  test    eax, eax
0x1800cc392  jns     short loc_1800CC403
0x1800cc394  xor     esi, esi
0x1800cc396  mov     [rsp+1550h+var_14E0], eax
0x1800cc39a  cmp     dword ptr cs:xmmword_180169738, esi
0x1800cc3a0  mov     dword ptr [rbp+1450h+var_14D0], esi
0x1800cc3a3  jz      loc_1800CD9D2
0x1800cc3a9  mov     rdx, 4000000000000800h; unsigned __int64
0x1800cc3b3  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800cc3ba  jz      loc_1800CD9D2
0x1800cc3c0  mov     rax, cs:qword_180169748
0x1800cc3c7  and     rax, rdx
0x1800cc3ca  cmp     cs:qword_180169748, rax
0x1800cc3d1  jnz     loc_1800CD9D2
0x1800cc3d7  lea     rcx, [rbp+1450h+var_1350]; unsigned __int16 *
0x1800cc3de  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800cc3e3  lea     rax, [rbp+1450h+var_1350]
0x1800cc3ea  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800cc3ee  inc     rbx
0x1800cc3f1  cmp     [rax+rbx*2], si
0x1800cc3f5  jnz     short loc_1800CC3EE
0x1800cc3f7  lea     rax, [rbp+1450h+var_1350]
0x1800cc3fe  jmp     loc_1800CC327
0x1800cc403  lea     rax, [rbp+1450h+hKey]
0x1800cc407  mov     r9d, 2001Fh; samDesired
0x1800cc40d  xor     r8d, r8d; ulOptions
0x1800cc410  mov     [rsp+1550h+phkResult], rax; phkResult
0x1800cc415  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Control\\WMI"...
0x1800cc41c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800cc423  call    cs:__imp_RegOpenKeyExW
0x1800cc429  mov     ecx, eax; unsigned int
0x1800cc42b  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800cc430  mov     edi, eax
0x1800cc432  test    eax, eax
0x1800cc434  jns     short loc_1800CC4A5
0x1800cc436  xor     esi, esi
0x1800cc438  mov     [rsp+1550h+var_14E0], eax
0x1800cc43c  cmp     dword ptr cs:xmmword_180169738, esi
0x1800cc442  mov     dword ptr [rbp+1450h+var_14D0], esi
0x1800cc445  jz      loc_1800CD9D2
0x1800cc44b  mov     rdx, 4000000000000800h; unsigned __int64
0x1800cc455  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800cc45c  jz      loc_1800CD9D2
0x1800cc462  mov     rax, cs:qword_180169748
0x1800cc469  and     rax, rdx
0x1800cc46c  cmp     cs:qword_180169748, rax
0x1800cc473  jnz     loc_1800CD9D2
0x1800cc479  lea     rcx, [rbp+1450h+var_12D0]; unsigned __int16 *
0x1800cc480  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800cc485  lea     rax, [rbp+1450h+var_12D0]
0x1800cc48c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800cc490  inc     rbx
0x1800cc493  cmp     [rax+rbx*2], si
0x1800cc497  jnz     short loc_1800CC490
0x1800cc499  lea     rax, [rbp+1450h+var_12D0]
0x1800cc4a0  jmp     loc_1800CC327
0x1800cc4a5  mov     rcx, [rbp+1450h+hKey]; hKey
0x1800cc4a9  lea     rax, [rbp+1450h+var_14C0]
0x1800cc4ad  mov     edi, 2001Fh
0x1800cc4b2  mov     [rsp+1550h+phkResult], rax; phkResult
0x1800cc4b7  mov     r9d, edi; samDesired
0x1800cc4ba  xor     r8d, r8d; ulOptions
0x1800cc4bd  mov     rdx, rsi; lpSubKey
0x1800cc4c0  call    cs:__imp_RegOpenKeyExW
0x1800cc4c6  mov     ecx, eax; unsigned int
0x1800cc4c8  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800cc4cd  xor     edx, edx
0x1800cc4cf  test    eax, eax
0x1800cc4d1  mov     eax, ebx
0x1800cc4d3  jns     short loc_1800CC4E6
0x1800cc4d5  and     eax, 0Fh
0x1800cc4d8  mov     ecx, edx
0x1800cc4da  cmp     eax, 2
0x1800cc4dd  jnz     short loc_1800CC4FE
0x1800cc4df  mov     edi, 80300002h
0x1800cc4e4  jmp     short loc_1800CC4F2
0x1800cc4e6  and     eax, 0Fh
0x1800cc4e9  cmp     al, 1
0x1800cc4eb  jnz     short loc_1800CC4F9
0x1800cc4ed  mov     edi, 803000B7h
0x1800cc4f2  xor     esi, esi
0x1800cc4f4  jmp     loc_1800CD9D2
0x1800cc4f9  mov     ecx, 1
0x1800cc4fe  bt      ebx, 0Ch
0x1800cc502  jnb     short loc_1800CC50D
0x1800cc504  xor     esi, esi
0x1800cc506  mov     edi, esi
0x1800cc508  jmp     loc_1800CD9D2
0x1800cc50d  test    ecx, ecx
0x1800cc50f  jnz     loc_1800CC5C3
0x1800cc515  mov     rcx, [rbp+1450h+hKey]; hKey
0x1800cc519  lea     rax, [rbp+1450h+dwDisposition]
0x1800cc51d  mov     [rsp+1550h+lpdwDisposition], rax; lpdwDisposition
0x1800cc522  xor     r9d, r9d; lpClass
0x1800cc525  lea     rax, [rbp+1450h+var_14C0]
0x1800cc529  xor     r8d, r8d; Reserved
0x1800cc52c  mov     [rsp+1550h+var_1518], rax; phkResult
0x1800cc531  mov     [rsp+1550h+lpSecurityAttributes], rdx; lpSecurityAttributes
0x1800cc536  mov     [rsp+1550h+samDesired], edi; samDesired
0x1800cc53a  mov     dword ptr [rsp+1550h+phkResult], edx; dwOptions
0x1800cc53e  mov     rdx, rsi; lpSubKey
0x1800cc541  call    cs:__imp_RegCreateKeyExW
0x1800cc547  mov     ecx, eax; unsigned int
0x1800cc549  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800cc54e  xor     esi, esi
0x1800cc550  mov     edi, eax
0x1800cc552  test    eax, eax
0x1800cc554  jns     short loc_1800CC5C5
0x1800cc556  cmp     dword ptr cs:xmmword_180169738, esi
0x1800cc55c  mov     dword ptr [rbp+1450h+var_14D0], esi
0x1800cc55f  mov     [rsp+1550h+var_14E0], eax
0x1800cc563  jz      loc_1800CD9D2
0x1800cc569  mov     rdx, 4000000000000800h; unsigned __int64
0x1800cc573  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800cc57a  jz      loc_1800CD9D2
0x1800cc580  mov     rax, cs:qword_180169748
0x1800cc587  and     rax, rdx
0x1800cc58a  cmp     cs:qword_180169748, rax
0x1800cc591  jnz     loc_1800CD9D2
0x1800cc597  lea     rcx, [rbp+1450h+var_1250]; unsigned __int16 *
0x1800cc59e  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800cc5a3  lea     rax, [rbp+1450h+var_1250]
0x1800cc5aa  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800cc5ae  inc     rbx
0x1800cc5b1  cmp     [rax+rbx*2], si
0x1800cc5b5  jnz     short loc_1800CC5AE
0x1800cc5b7  lea     rax, [rbp+1450h+var_1250]
0x1800cc5be  jmp     loc_1800CC327
0x1800cc5c3  xor     esi, esi
0x1800cc5c5  lea     rcx, [rbp+1450h+var_14B0]; struct tagVARIANT *
0x1800cc5c9  call    ?PlaiVariantClear@@YAJPEAUtagVARIANT@@@Z; PlaiVariantClear(tagVARIANT *)
0x1800cc5ce  mov     rcx, [rbp+1450h+var_14B8]
0x1800cc5d2  lea     rdx, [rbp+1450h+var_14B0+8]
0x1800cc5d6  mov     rax, [rcx]
0x1800cc5d9  mov     rax, [rax+100h]
0x1800cc5e0  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
