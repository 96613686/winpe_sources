# LDataCollectorSet::Commit(ushort *,ushort *,__MIDL___MIDL_itf_pla_0001_0043_0007,IValueMap * *)

- ea: `0x1800b16b0`
- end: `0x1800b27a1`
- name: `?Commit@LDataCollectorSet@@UEAAJPEAG0W4__MIDL___MIDL_itf_pla_0001_0043_0007@@PEAPEAUIValueMap@@@Z`
- size: `4337`
- prototype: `__int64 __fastcall(LDataCollectorSet *this, wchar_t *String2, unsigned __int16 *, unsigned int, struct IValueMap **)`
- caller_count: `0`
- callee_count: `23`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800106d0`
- `0x180012ef0`
- `0x180018420`
- `0x1800198b0`
- `0x18005b290`
- `0x1800a6750`
- `0x1800b16b0`
- `0x1800b3bb0`
- `0x1800da7f0`
- `0x1800e5f20`
- `0x18012e4e0`
- `0x18012ec18`
- `0x18012f530`
- `0x180130b28`
- `0x180131e1c`
- `0x180132c88`
- `0x180132f38`
- `0x1801332a8`
- `0x18013ae9a`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b2640`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b2640`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b17be`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b17be`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b240c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b240c`

## string_xrefs

- `0x1800b177b`: `LDataCollectorSet::Commit`
- `0x1800b1880`: `LDataCollectorSet::Commit`
- `0x1800b19ce`: `LDataCollectorSet::Commit`
- `0x1800b1e29`: `LDataCollectorSet::Commit`
- `0x1800b25f3`: `LDataCollectorSet::Commit`

## pseudocode

```c
__int64 __fastcall LDataCollectorSet::Commit(
        LDataCollectorSet *this,
        wchar_t *String2,
        unsigned __int16 *a3,
        unsigned int a4,
        struct IValueMap **a5)
{
  struct IValueMap **v5; // rbx
  signed int v10; // eax
  int v11; // edi
  __int64 v12; // rbx
  unsigned __int16 *v13; // r14
  __int32 v14; // ebx
  __int64 v15; // rbx
  int v16; // eax
  __int64 v17; // rbx
  int v18; // eax
  __int64 v19; // rbx
  int v20; // eax
  __int64 v21; // rbx
  int v22; // eax
  __int64 v23; // rbx
  bool v24; // zf
  int v25; // eax
  int v26; // eax
  __int64 v27; // rbx
  int v28; // edx
  int v29; // ecx
  int v30; // eax
  __int64 v31; // rbx
  __int64 v32; // rbx
  int v33; // eax
  __int64 v34; // rax
  int v35; // eax
  __int64 v36; // rax
  int v37; // eax
  const char *v38; // rdx
  int v39; // r8d
  __int64 v40; // rax
  int v41; // eax
  __int64 v42; // rax
  int v43; // eax
  int v44; // ecx
  int v45; // ecx
  int v46; // eax
  int v47; // eax
  int v48; // eax
  int v49; // eax
  __int16 v50; // r14
  int v51; // edi
  int v52; // eax
  HKEY v53; // rsi
  int v54; // eax
  unsigned int v55; // r9d
  int LogFileNameW; // eax
  struct IValueMap *v57; // rcx
  OLECHAR *v58; // rcx
  int v60; // [rsp+20h] [rbp-E0h]
  __int64 v61; // [rsp+48h] [rbp-B8h]
  __int64 v62; // [rsp+50h] [rbp-B0h]
  unsigned int v63; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  struct IValueMap **v65; // [rsp+80h] [rbp-80h]
  unsigned __int16 *v66; // [rsp+88h] [rbp-78h]
  __int16 v67; // [rsp+90h] [rbp-70h] BYREF
  struct IDataCollector *v68; // [rsp+98h] [rbp-68h] BYREF
  int v69; // [rsp+A0h] [rbp-60h] BYREF
  struct IValueMap *v70; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v71; // [rsp+B0h] [rbp-50h] BYREF
  LDataCollectorSet *v72; // [rsp+B8h] [rbp-48h] BYREF
  LDataCollectorSet *v73; // [rsp+C0h] [rbp-40h]
  int v74; // [rsp+D0h] [rbp-30h] BYREF
  BSTR v75; // [rsp+D8h] [rbp-28h] BYREF
  BSTR v76; // [rsp+E0h] [rbp-20h] BYREF
  int v77; // [rsp+E8h] [rbp-18h]
  _BYTE v78[8]; // [rsp+F8h] [rbp-8h] BYREF
  BSTR v79; // [rsp+100h] [rbp+0h] BYREF
  BSTR v80[2]; // [rsp+108h] [rbp+8h] BYREF
  int v81; // [rsp+11Ch] [rbp+1Ch]
  _BYTE v82[8]; // [rsp+120h] [rbp+20h] BYREF
  BSTR bstrString; // [rsp+128h] [rbp+28h] BYREF
  int v84; // [rsp+130h] [rbp+30h]
  LPCVOID lpMem; // [rsp+198h] [rbp+98h]
  BSTR v86; // [rsp+1B0h] [rbp+B0h]
  BSTR v87; // [rsp+1B8h] [rbp+B8h]
  OLECHAR *v88; // [rsp+1C0h] [rbp+C0h]
  BSTR v89; // [rsp+1C8h] [rbp+C8h]
  BSTR v90; // [rsp+1D0h] [rbp+D0h]
  unsigned __int16 v91[64]; // [rsp+1F0h] [rbp+F0h] BYREF
  unsigned __int16 v92[64]; // [rsp+270h] [rbp+170h] BYREF
  unsigned __int16 v93[64]; // [rsp+2F0h] [rbp+1F0h] BYREF
  unsigned __int16 v94[64]; // [rsp+370h] [rbp+270h] BYREF
  unsigned __int16 v95[64]; // [rsp+3F0h] [rbp+2F0h] BYREF
  unsigned __int16 v96[64]; // [rsp+470h] [rbp+370h] BYREF
  unsigned __int16 v97[64]; // [rsp+4F0h] [rbp+3F0h] BYREF
  unsigned __int16 v98[64]; // [rsp+570h] [rbp+470h] BYREF
  unsigned __int16 v99[64]; // [rsp+5F0h] [rbp+4F0h] BYREF
  unsigned __int16 v100[64]; // [rsp+670h] [rbp+570h] BYREF
  unsigned __int16 v101[64]; // [rsp+6F0h] [rbp+5F0h] BYREF
  unsigned __int16 v102[64]; // [rsp+770h] [rbp+670h] BYREF
  unsigned __int16 v103[64]; // [rsp+7F0h] [rbp+6F0h] BYREF
  unsigned __int16 v104[64]; // [rsp+870h] [rbp+770h] BYREF
  unsigned __int16 v105[64]; // [rsp+8F0h] [rbp+7F0h] BYREF
  unsigned __int16 v106[64]; // [rsp+970h] [rbp+870h] BYREF
  unsigned __int16 v107[64]; // [rsp+9F0h] [rbp+8F0h] BYREF
  unsigned __int16 v108[64]; // [rsp+A70h] [rbp+970h] BYREF
  unsigned __int16 v109[64]; // [rsp+AF0h] [rbp+9F0h] BYREF
  unsigned __int16 v110[64]; // [rsp+B70h] [rbp+A70h] BYREF

  v5 = a5;
  v73 = this;
  v65 = a5;
  v67 = 0;
  v69 = 0;
  v66 = 0;
  v71 = 0;
  v68 = 0;
  v70 = 0;
  v63 = 1024;
  memset_0(&v74, 0, 0x118u);
  LODWORD(hKey) = *((_DWORD *)this + 14);
  v72 = this;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000400LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000400LL) )
  {
    EventingWriteEvent(&g_Eventing, PLA_EVENT_METHOD, 3, "LDataCollectorSet::Commit", 26, &v72, 8, &hKey, 4, v61, v62);
  }
  if ( *((_DWORD *)this + 2) )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v10 = DataCollectorSet::Commit(this, String2, a3, a4, &v70);
  v11 = v10;
  if ( v10 < 0 )
  {
    v63 = v10;
    LODWORD(hKey) = 0;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      v13 = 0;
      goto LABEL_208;
    }
    PlaiWhoAmI(v91, 0x4000000000000800uLL);
    v12 = -1;
    do
      ++v12;
    while ( v91[v12] );
    EventingWriteEvent(
      &g_Eventing,
      PLA_EVENT_ERROR,
      5,
      &v63,
      4,
      qword_180147320,
      1,
      &hKey,
      4,
      "LDataCollectorSet::Commit",
      26);
    goto LABEL_14;
  }
  v14 = a4 & 0xF;
  if ( (int)PlaliGetInfoW(String2, a3, &v71, 0) < 0 )
  {
    if ( v14 == 2 )
    {
      v11 = -2144337918;
LABEL_14:
      v13 = 0;
      goto LABEL_207;
    }
  }
  else if ( v14 == 1 )
  {
    v11 = -2144337737;
LABEL_19:
    v13 = v66;
    goto LABEL_207;
  }
  if ( (a4 & 0x1000) != 0 )
  {
    v11 = 0;
LABEL_24:
    v13 = 0;
    goto LABEL_207;
  }
  v11 = (*(__int64 (__fastcall **)(LDataCollectorSet *, struct IDataCollector **))(*(_QWORD *)this + 616LL))(this, &v68);
  if ( v11 < 0 )
  {
    v63 = 0;
    if ( v11 == -1073738773 )
      v11 = -2144337662;
    LODWORD(hKey) = v11;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_24;
    }
    PlaiWhoAmI(v92, 0x4000000000000800uLL);
    v15 = -1;
    do
      ++v15;
    while ( v92[v15] );
    goto LABEL_33;
  }
  v16 = ((__int64 (__fastcall *)(struct IDataCollector *, wchar_t *))v68->lpVtbl->put_Name)(v68, String2);
  v11 = v16;
  if ( v16 < 0 )
  {
    v63 = 0;
    LODWORD(hKey) = v16;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_24;
    }
    PlaiWhoAmI(v93, 0x4000000000000800uLL);
    v17 = -1;
    do
      ++v17;
    while ( v93[v17] );
LABEL_33:
    EventingWriteEvent(
      &g_Eventing,
      PLA_EVENT_ERROR,
      5,
      &hKey,
      4,
      qword_180147320,
      1,
      &v63,
      4,
      "LDataCollectorSet::Commit",
      26);
    goto LABEL_19;
  }
  v18 = (*(__int64 (__fastcall **)(LDataCollectorSet *, BSTR *))(*(_QWORD *)this + 176LL))(this, &v79);
  v11 = v18;
  if ( v18 < 0 )
  {
    v63 = 0;
    LODWORD(hKey) = v18;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_24;
    }
    PlaiWhoAmI(v94, 0x4000000000000800uLL);
    v19 = -1;
    do
      ++v19;
    while ( v94[v19] );
    goto LABEL_33;
  }
  if ( v18 != 3145984 )
    v74 |= 0x2000u;
  v20 = (*(__int64 (__fastcall **)(LDataCollectorSet *, _BYTE *))(*(_QWORD *)this + 80LL))(this, v78);
  v11 = v20;
  if ( v20 < 0 )
  {
    v63 = 0;
    LODWORD(hKey) = v20;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_24;
    }
    PlaiWhoAmI(v95, 0x4000000000000800uLL);
    v21 = -1;
    do
      ++v21;
    while ( v95[v21] );
    goto LABEL_33;
  }
  if ( v20 != 3145984 )
    v74 |= 0x10000000u;
  v22 = ((__int64 (__fastcall *)(struct IDataCollector *, BSTR *))v68->lpVtbl->get_FileName)(v68, v80);
  v11 = v22;
  if ( v22 < 0 )
  {
    v63 = 0;
    LODWORD(hKey) = v22;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_24;
    }
    PlaiWhoAmI(v96, 0x4000000000000800uLL);
    v23 = -1;
    do
      ++v23;
    while ( v96[v23] );
    goto LABEL_33;
  }
  v24 = v22 == 3145984;
  v25 = v74;
  if ( !v24 )
    v25 = v74 | 0x10;
  v74 = v25 | 0x20;
  v26 = ((__int64 (__fastcall *)(struct IDataCollector *, int *))v68->lpVtbl->get_FileNameFormat)(v68, &v69);
  v11 = v26;
  if ( v26 < 0 )
  {
    v63 = 0;
    LODWORD(hKey) = v26;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_24;
    }
    PlaiWhoAmI(v97, 0x4000000000000800uLL);
    v27 = -1;
    do
      ++v27;
    while ( v97[v27] );
    goto LABEL_33;
  }
  v28 = v69 & 0xFF00;
  if ( (v69 & 0xFF00) != 0 )
  {
    if ( v28 == 256 )
    {
      v81 = 0;
    }
    else if ( v28 == 512 )
    {
      v81 = 1;
    }
    else if ( v28 == 1024 )
    {
      v81 = 2;
    }
    else if ( v28 == 2048 )
    {
      v81 = 3;
    }
    else
    {
      if ( v28 == 4096 )
      {
        v29 = 4;
      }
      else
      {
        if ( v28 == 0x2000 )
        {
          v81 = 5;
          goto LABEL_93;
        }
        v29 = 6;
        if ( v28 != 0x4000 )
          v29 = 0;
      }
      v81 = v29;
    }
  }
  else
  {
    v81 = -1;
  }
LABEL_93:
  v74 |= 0x40u;
  v30 = ((__int64 (__fastcall *)(struct IDataCollector *, __int16 *))v68->lpVtbl->get_LogOverwrite)(v68, &v67);
  v11 = v30;
  if ( v30 < 0 )
  {
    v63 = 0;
    LODWORD(hKey) = v30;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_24;
    }
    PlaiWhoAmI(v98, 0x4000000000000800uLL);
    v31 = -1;
    do
      ++v31;
    while ( v98[v31] );
    goto LABEL_33;
  }
  v32 = -1;
  if ( v67 == -1 )
    v84 |= 1u;
  v33 = ((__int64 (__fastcall *)(struct IDataCollector *, __int16 *))v68->lpVtbl->get_LogAppend)(v68, &v67);
  v11 = v33;
  if ( v33 < 0 )
  {
    v63 = 0;
    LODWORD(hKey) = v33;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_24;
    }
    PlaiWhoAmI(v99, 0x4000000000000800uLL);
    do
      ++v32;
    while ( v99[v32] );
    goto LABEL_33;
  }
  if ( v67 == -1 )
    v84 |= 2u;
  v34 = *(_QWORD *)this;
  v74 |= 0x4000u;
  v35 = (*(__int64 (__fastcall **)(LDataCollectorSet *, _BYTE *))(v34 + 240))(this, v82);
  v11 = v35;
  if ( v35 < 0 )
  {
    v63 = 0;
    LODWORD(hKey) = v35;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_24;
    }
    PlaiWhoAmI(v100, 0x4000000000000800uLL);
    do
      ++v32;
    while ( v100[v32] );
    goto LABEL_33;
  }
  v36 = *(_QWORD *)this;
  v74 |= 8u;
  v37 = (*(__int64 (__fastcall **)(LDataCollectorSet *, BSTR *))(v36 + 320))(this, &bstrString);
  v11 = v37;
  if ( v37 < 0 )
  {
    v63 = 0;
    LODWORD(hKey) = v37;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_24;
    }
    PlaiWhoAmI(v101, 0x4000000000000800uLL);
    do
      ++v32;
    while ( v101[v32] );
    goto LABEL_33;
  }
  if ( !bstrString || !*bstrString )
  {
    PlaiFreeString(bstrString);
    bstrString = 0;
    bstrString = PlaiAllocStringEx((const unsigned __int16 *)&szPassword, v38, v39);
  }
  if ( *((_DWORD *)this + 60) )
  {
    v40 = *(_QWORD *)this;
    v74 |= 1u;
    v41 = (*(__int64 (__fastcall **)(LDataCollectorSet *, BSTR *))(v40 + 408))(this, &v75);
    v11 = v41;
    if ( v41 < 0 )
    {
      v63 = 0;
      LODWORD(hKey) = v41;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_24;
      }
      PlaiWhoAmI(v102, 0x4000000000000800uLL);
      do
        ++v32;
      while ( v102[v32] );
      goto LABEL_33;
    }
    v42 = *(_QWORD *)this;
    v74 |= 0x80000000;
    v43 = (*(__int64 (__fastcall **)(LDataCollectorSet *, BSTR *))(v42 + 576))(this, &v76);
    v11 = v43;
    if ( v43 < 0 )
    {
      v63 = 0;
      LODWORD(hKey) = v43;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_24;
      }
      PlaiWhoAmI(v103, 0x4000000000000800uLL);
      do
        ++v32;
      while ( v103[v32] );
      goto LABEL_33;
    }
  }
  v44 = *((_DWORD *)this + 68);
  if ( v44 )
  {
    v45 = v44 - 1;
    if ( v45 )
    {
      if ( v45 == 1 )
      {
        v46 = LAlertDataCollector::Commit((struct IDataCollectorSet *)this, v68, (struct _PDH_PLALI_INFO_W *)&v74);
        v11 = v46;
        if ( v46 < 0 )
        {
          v63 = 0;
          LODWORD(hKey) = v46;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_24;
          }
          PlaiWhoAmI(v104, 0x4000000000000800uLL);
          do
            ++v32;
          while ( v104[v32] );
          goto LABEL_33;
        }
      }
    }
    else
    {
      v47 = LTraceDataCollector::Commit((struct IDataCollectorSet *)this, v68, (struct _PDH_PLALI_INFO_W *)&v74);
      v11 = v47;
      if ( v47 < 0 )
      {
        v63 = 0;
        LODWORD(hKey) = v47;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_24;
        }
        PlaiWhoAmI(v105, 0x4000000000000800uLL);
        do
          ++v32;
        while ( v105[v32] );
        goto LABEL_33;
      }
    }
  }
  else
  {
    v48 = LPerformanceCounterDataCollector::Commit(
            (struct IDataCollectorSet *)this,
            v68,
            (struct _PDH_PLALI_INFO_W *)&v74);
    v11 = v48;
    if ( v48 < 0 )
    {
      v63 = 0;
      LODWORD(hKey) = v48;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_24;
      }
      PlaiWhoAmI(v106, 0x4000000000000800uLL);
      do
        ++v32;
      while ( v106[v32] );
      goto LABEL_33;
    }
  }
  v49 = (*(__int64 (__fastcall **)(LDataCollectorSet *, int *))(*(_QWORD *)this + 632LL))(this, &v74);
  v11 = v49;
  if ( v49 < 0 )
  {
    v63 = 0;
    LODWORD(hKey) = v49;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_24;
    }
    PlaiWhoAmI(v107, 0x4000000000000800uLL);
    do
      ++v32;
    while ( v107[v32] );
    goto LABEL_33;
  }
  hKey = 0;
  if ( !String2 )
    goto LABEL_232;
  v50 = v74;
  v51 = PlaliSetRunAs(String2, a3, (struct _PDH_PLALI_INFO_W *)&v74);
  if ( v51 )
    goto LABEL_184;
  v52 = PlaliConnectAndLockQuery(a3, String2, &hKey, 1);
  v53 = hKey;
  v51 = v52;
  if ( !v52 )
  {
    v51 = PlaliSetInfo(hKey, (struct _PDH_PLALI_INFO_W *)&v74);
    PlaliWriteRegistryLastModified(v53);
    if ( v51 >= 0 )
    {
      v51 = PlaliSynchronize(a3);
      if ( v51 >= 0 && (v50 & 0x400) != 0 )
        PlaliUpdateServiceMode(a3);
    }
  }
  if ( v53 )
    RegCloseKey(v53);
  if ( v51 )
  {
LABEL_184:
    if ( v51 < 0 )
    {
LABEL_232:
      v54 = PlaliCreateW(String2, a3, (struct _PDH_PLALI_INFO_W *)&v74);
      v11 = v54;
      if ( v54 < 0 )
      {
        v63 = 0;
        LODWORD(hKey) = v54;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          v13 = v66;
          goto LABEL_207;
        }
        PlaiWhoAmI(v108, 0x4000000000000800uLL);
        do
          ++v32;
        while ( v108[v32] );
        goto LABEL_33;
      }
    }
  }
  v13 = (unsigned __int16 *)PlaiAlloc(0x800u, 1, 0, qword_180147320, v60);
  if ( v13 )
  {
    LogFileNameW = PlaliGetLogFileNameW(String2, a3, (struct _PDH_PLALI_INFO_W *)&v74, v55, &v63, v13);
    v11 = LogFileNameW;
    if ( LogFileNameW >= 0 )
      goto LABEL_207;
    v63 = 0;
    LODWORD(hKey) = LogFileNameW;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_207;
    }
    PlaiWhoAmI(v110, 0x4000000000000800uLL);
    do
      ++v32;
    while ( v110[v32] );
  }
  else
  {
    v11 = -2147024882;
    LODWORD(hKey) = -2147024882;
    v63 = 0;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_207;
    }
    PlaiWhoAmI(v109, 0x4000000000000800uLL);
    do
      ++v32;
    while ( v109[v32] );
  }
  EventingWriteEvent(
    &g_Eventing,
    PLA_EVENT_ERROR,
    5,
    &hKey,
    4,
    qword_180147320,
    1,
    &v63,
    4,
    "LDataCollectorSet::Commit",
    26);
LABEL_207:
  v5 = v65;
LABEL_208:
  if ( *((_DWORD *)v73 + 2) )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v73 + 16));
  if ( v11 >= 0 && v5 )
  {
    v57 = v70;
    *v5 = v70;
    ((void (__fastcall *)(struct IValueMap *))v57->lpVtbl->AddRef)(v57);
  }
  if ( v13 )
    PlaiFree(v13, 1);
  if ( v68 )
  {
    ((void (__fastcall *)(struct IDataCollector *))v68->lpVtbl->Release)(v68);
    v68 = 0;
  }
  if ( v70 )
  {
    ((void (__fastcall *)(struct IValueMap *))v70->lpVtbl->Release)(v70);
    v70 = 0;
  }
  PlaiFreeString(v79);
  v79 = 0;
  PlaiFreeString(v80[0]);
  v80[0] = 0;
  PlaiFreeString(bstrString);
  bstrString = 0;
  PlaiFreeString(v75);
  v75 = 0;
  PlaiFreeString(v76);
  v76 = 0;
  if ( v77 )
  {
    if ( v77 == 1 )
    {
      v58 = v86;
LABEL_226:
      PlaiFreeString(v58);
      return (unsigned int)v11;
    }
    if ( v77 == 2 )
    {
      if ( lpMem )
      {
        PlaiFree(lpMem, 1);
        lpMem = 0;
      }
      PlaiFreeString(v90);
      v90 = 0;
      PlaiFreeString(v89);
      v89 = 0;
      PlaiFreeString(v87);
      v58 = v88;
      v87 = 0;
      goto LABEL_226;
    }
  }
  else if ( lpMem )
  {
    PlaiFree(lpMem, 1);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800b16b0  push    rbp
0x1800b16b2  push    rbx
0x1800b16b3  push    rsi
0x1800b16b4  push    rdi
0x1800b16b5  push    r12
0x1800b16b7  push    r13
0x1800b16b9  push    r14
0x1800b16bb  push    r15
0x1800b16bd  lea     rbp, [rsp-0B08h]
0x1800b16c5  sub     rsp, 0C08h
0x1800b16cc  mov     rax, cs:__security_cookie
0x1800b16d3  xor     rax, rsp
0x1800b16d6  mov     [rbp+0B40h+var_50], rax
0x1800b16dd  mov     rbx, [rbp+0B40h+arg_20]
0x1800b16e4  xor     r13d, r13d
0x1800b16e7  mov     r15, r8
0x1800b16ea  mov     [rbp+0B40h+var_B80], rcx
0x1800b16ee  mov     r12, rdx
0x1800b16f1  mov     [rbp+0B40h+var_BC0], rbx
0x1800b16f5  mov     r14, rcx
0x1800b16f8  mov     [rbp+0B40h+var_BB0], r13w
0x1800b16fd  xor     edx, edx; Val
0x1800b16ff  mov     [rbp+0B40h+var_BA0], r13d
0x1800b1703  mov     r8d, 118h; Size
0x1800b1709  mov     [rbp+0B40h+var_BB8], r13
0x1800b170d  lea     rcx, [rbp+0B40h+var_B70]; void *
0x1800b1711  mov     [rbp+0B40h+var_B90], r13d
0x1800b1715  mov     [rbp+0B40h+var_BA8], r13
0x1800b1719  mov     esi, r9d
0x1800b171c  mov     [rbp+0B40h+var_B98], r13
0x1800b1720  mov     [rsp+0C40h+var_BD0], 400h
0x1800b1728  call    memset_0
0x1800b172d  cmp     dword ptr cs:xmmword_180169738, r13d
0x1800b1734  mov     eax, [r14+38h]
0x1800b1738  mov     dword ptr [rsp+0C40h+hKey], eax
0x1800b173c  mov     [rbp+0B40h+var_B88], r14
0x1800b1740  jz      short loc_1800B17B4
0x1800b1742  mov     rdx, 4000000000000400h
0x1800b174c  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800b1753  jz      short loc_1800B17B4
0x1800b1755  mov     rax, cs:qword_180169748
0x1800b175c  and     rax, rdx
0x1800b175f  cmp     cs:qword_180169748, rax
0x1800b1766  jnz     short loc_1800B17B4
0x1800b1768  mov     [rsp+0C40h+var_C00], 4
0x1800b1771  lea     rax, [rsp+0C40h+hKey]
0x1800b1776  mov     [rsp+0C40h+var_C08], rax
0x1800b177b  lea     r9, aLdatacollector_5; "LDataCollectorSet::Commit"
0x1800b1782  lea     rax, [rbp+0B40h+var_B88]
0x1800b1786  mov     [rsp+0C40h+var_C10], 8
0x1800b178f  mov     [rsp+0C40h+var_C18], rax
0x1800b1794  lea     r8d, [r13+3]
0x1800b1798  lea     rdx, PLA_EVENT_METHOD
0x1800b179f  mov     [rsp+0C40h+var_C20], 1Ah
0x1800b17a8  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800b17af  call    EventingWriteEvent
0x1800b17b4  cmp     [r14+8], r13d
0x1800b17b8  jz      short loc_1800B17C4
0x1800b17ba  lea     rcx, [r14+10h]; lpCriticalSection
0x1800b17be  call    cs:__imp_EnterCriticalSection
0x1800b17c4  lea     rax, [rbp+0B40h+var_B98]
0x1800b17c8  mov     r9d, esi; enum __MIDL___MIDL_itf_pla_0001_0043_0007
0x1800b17cb  mov     r8, r15; unsigned __int16 *
0x1800b17ce  mov     [rsp+0C40h+var_C20], rax; int
0x1800b17d3  mov     rdx, r12; unsigned __int16 *
0x1800b17d6  mov     rcx, r14; this
0x1800b17d9  call    ?Commit@DataCollectorSet@@UEAAJPEAG0W4__MIDL___MIDL_itf_pla_0001_0043_0007@@PEAPEAUIValueMap@@@Z; DataCollectorSet::Commit(ushort *,ushort *,__MIDL___MIDL_itf_pla_0001_0043_0007,IValueMap * *)
0x1800b17de  mov     edi, eax
0x1800b17e0  test    eax, eax
0x1800b17e2  jns     loc_1800B18D3
0x1800b17e8  xor     esi, esi
0x1800b17ea  mov     [rsp+0C40h+var_BD0], eax
0x1800b17ee  cmp     dword ptr cs:xmmword_180169738, esi
0x1800b17f4  mov     dword ptr [rsp+0C40h+hKey], esi
0x1800b17f8  jz      loc_1800B18CB
0x1800b17fe  mov     rdx, 4000000000000800h; unsigned __int64
0x1800b1808  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800b180f  jz      loc_1800B18CB
0x1800b1815  mov     rax, cs:qword_180169748
0x1800b181c  and     rax, rdx
0x1800b181f  cmp     cs:qword_180169748, rax
0x1800b1826  jnz     loc_1800B18CB
0x1800b182c  lea     rcx, [rbp+0B40h+var_A50]; unsigned __int16 *
0x1800b1833  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800b1838  lea     rax, [rbp+0B40h+var_A50]
0x1800b183f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800b1843  inc     rbx
0x1800b1846  cmp     [rax+rbx*2], si
0x1800b184a  jnz     short loc_1800B1843
0x1800b184c  lea     rax, [rbp+0B40h+var_A50]
0x1800b1853  lea     ecx, [rbx+rbx]
0x1800b1856  add     rcx, 2
0x1800b185a  lea     rsi, qword_180147320
0x1800b1861  mov     [rsp+0C40h+var_BE0], rcx
0x1800b1866  lea     r9, [rsp+0C40h+var_BD0]
0x1800b186b  mov     [rsp+0C40h+var_BE8], rax
0x1800b1870  lea     rdx, PLA_EVENT_ERROR
0x1800b1877  mov     [rsp+0C40h+var_BF0], 1Ah
0x1800b1880  lea     rax, aLdatacollector_5; "LDataCollectorSet::Commit"
0x1800b1887  mov     [rsp+0C40h+var_BF8], rax
0x1800b188c  mov     ecx, 4
0x1800b1891  mov     [rsp+0C40h+var_C00], rcx
0x1800b1896  lea     rax, [rsp+0C40h+hKey]
0x1800b189b  mov     [rsp+0C40h+var_C08], rax
0x1800b18a0  mov     [rsp+0C40h+var_C10], 1
0x1800b18a9  lea     r8d, [rcx+1]
0x1800b18ad  mov     [rsp+0C40h+var_C18], rsi
0x1800b18b2  mov     [rsp+0C40h+var_C20], rcx
0x1800b18b7  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800b18be  call    EventingWriteEvent
0x1800b18c3  mov     r14, r13
0x1800b18c6  jmp     loc_1800B262D
0x1800b18cb  mov     r14, rsi
0x1800b18ce  jmp     loc_1800B2633
0x1800b18d3  mov     ebx, esi
0x1800b18d5  lea     r8, [rbp+0B40h+var_B90]; unsigned int *
0x1800b18d9  xor     r9d, r9d; struct _PDH_PLALI_INFO_W *
0x1800b18dc  mov     rdx, r15; unsigned __int16 *
0x1800b18df  mov     rcx, r12; unsigned __int16 *
0x1800b18e2  and     ebx, 0Fh
0x1800b18e5  call    ?PlaliGetInfoW@@YAJPEBG0PEAKPEAU_PDH_PLALI_INFO_W@@@Z; PlaliGetInfoW(ushort const *,ushort const *,ulong *,_PDH_PLALI_INFO_W *)
0x1800b18ea  test    eax, eax
0x1800b18ec  js      short loc_1800B1907
0x1800b18ee  mov     r13d, 1
0x1800b18f4  cmp     ebx, r13d
0x1800b18f7  jnz     short loc_1800B1919
0x1800b18f9  mov     edi, 803000B7h
0x1800b18fe  mov     r14, [rbp+0B40h+var_BB8]
0x1800b1902  jmp     loc_1800B262D
0x1800b1907  cmp     ebx, 2
0x1800b190a  jnz     short loc_1800B1913
0x1800b190c  mov     edi, 80300002h
0x1800b1911  jmp     short loc_1800B18C3
0x1800b1913  mov     r13d, 1
0x1800b1919  bt      esi, 0Ch
0x1800b191d  jnb     short loc_1800B192B
0x1800b191f  xor     esi, esi
0x1800b1921  mov     edi, esi
0x1800b1923  mov     r14, rsi
0x1800b1926  jmp     loc_1800B262F
0x1800b192b  mov     rax, [r14]
0x1800b192e  lea     rdx, [rbp+0B40h+var_BA8]
0x1800b1932  mov     rcx, r14
0x1800b1935  mov     rax, [rax+268h]
0x1800b193c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1941  xor     esi, esi
0x1800b1943  mov     edi, eax
0x1800b1945  test    eax, eax
0x1800b1947  jns     loc_1800B1A29
0x1800b194d  cmp     edi, 0C0000BEBh
0x1800b1953  mov     [rsp+0C40h+var_BD0], esi
0x1800b1957  mov     eax, 80300102h
0x1800b195c  cmovz   edi, eax
0x1800b195f  cmp     dword ptr cs:xmmword_180169738, esi
0x1800b1965  mov     dword ptr [rsp+0C40h+hKey], edi
0x1800b1969  jz      short loc_1800B1923
0x1800b196b  mov     rdx, 4000000000000800h; unsigned __int64
0x1800b1975  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800b197c  jz      short loc_1800B1923
0x1800b197e  mov     rax, cs:qword_180169748
0x1800b1985  and     rax, rdx
0x1800b1988  cmp     cs:qword_180169748, rax
0x1800b198f  jnz     short loc_1800B1923
0x1800b1991  lea     rcx, [rbp+0B40h+var_9D0]; unsigned __int16 *
0x1800b1998  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800b199d  lea     rax, [rbp+0B40h+var_9D0]
0x1800b19a4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800b19a8  inc     rbx
0x1800b19ab  cmp     [rax+rbx*2], si
0x1800b19af  jnz     short loc_1800B19A8
0x1800b19b1  lea     rax, [rbp+0B40h+var_9D0]
0x1800b19b8  lea     ecx, [rbx+rbx]
0x1800b19bb  add     rcx, 2
0x1800b19bf  mov     [rsp+0C40h+var_BE0], rcx
0x1800b19c4  mov     ecx, 4
0x1800b19c9  mov     [rsp+0C40h+var_BE8], rax
0x1800b19ce  lea     rax, aLdatacollector_5; "LDataCollectorSet::Commit"
0x1800b19d5  mov     [rsp+0C40h+var_BF0], 1Ah
0x1800b19de  mov     [rsp+0C40h+var_BF8], rax
0x1800b19e3  lea     rax, [rsp+0C40h+var_BD0]
0x1800b19e8  mov     [rsp+0C40h+var_C00], rcx
0x1800b19ed  lea     r8d, [rcx+1]
0x1800b19f1  mov     [rsp+0C40h+var_C08], rax
0x1800b19f6  mov     [rsp+0C40h+var_C10], r13
0x1800b19fb  lea     rsi, qword_180147320
0x1800b1a02  mov     [rsp+0C40h+var_C18], rsi
0x1800b1a07  lea     r9, [rsp+0C40h+hKey]
0x1800b1a0c  mov     [rsp+0C40h+var_C20], rcx
0x1800b1a11  lea     rdx, PLA_EVENT_ERROR
0x1800b1a18  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800b1a1f  call    EventingWriteEvent
0x1800b1a24  jmp     loc_1800B18FE
0x1800b1a29  mov     rcx, [rbp+0B40h+var_BA8]
0x1800b1a2d  mov     rdx, r12
0x1800b1a30  mov     rax, [rcx]
0x1800b1a33  mov     rax, [rax+0C8h]
0x1800b1a3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1a3f  mov     edi, eax
0x1800b1a41  test    eax, eax
0x1800b1a43  jns     short loc_1800B1AB3
0x1800b1a45  cmp     dword ptr cs:xmmword_180169738, esi
0x1800b1a4b  mov     [rsp+0C40h+var_BD0], esi
0x1800b1a4f  mov     dword ptr [rsp+0C40h+hKey], eax
0x1800b1a53  jz      loc_1800B1923
0x1800b1a59  mov     rdx, 4000000000000800h; unsigned __int64
0x1800b1a63  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800b1a6a  jz      loc_1800B1923
0x1800b1a70  mov     rax, cs:qword_180169748
0x1800b1a77  and     rax, rdx
0x1800b1a7a  cmp     cs:qword_180169748, rax
0x1800b1a81  jnz     loc_1800B1923
0x1800b1a87  lea     rcx, [rbp+0B40h+var_950]; unsigned __int16 *
0x1800b1a8e  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800b1a93  lea     rax, [rbp+0B40h+var_950]
0x1800b1a9a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800b1a9e  inc     rbx
0x1800b1aa1  cmp     [rax+rbx*2], si
0x1800b1aa5  jnz     short loc_1800B1A9E
0x1800b1aa7  lea     rax, [rbp+0B40h+var_950]
0x1800b1aae  jmp     loc_1800B19B8
0x1800b1ab3  mov     rax, [r14]
0x1800b1ab6  lea     rdx, [rbp+0B40h+var_B40]
0x1800b1aba  mov     rcx, r14
0x1800b1abd  mov     rax, [rax+0B0h]
0x1800b1ac4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1ac9  mov     edi, eax
0x1800b1acb  test    eax, eax
0x1800b1acd  jns     short loc_1800B1B3D
0x1800b1acf  cmp     dword ptr cs:xmmword_180169738, esi
0x1800b1ad5  mov     [rsp+0C40h+var_BD0], esi
0x1800b1ad9  mov     dword ptr [rsp+0C40h+hKey], eax
0x1800b1add  jz      loc_1800B1923
0x1800b1ae3  mov     rdx, 4000000000000800h; unsigned __int64
0x1800b1aed  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800b1af4  jz      loc_1800B1923
0x1800b1afa  mov     rax, cs:qword_180169748
0x1800b1b01  and     rax, rdx
0x1800b1b04  cmp     cs:qword_180169748, rax
0x1800b1b0b  jnz     loc_1800B1923
0x1800b1b11  lea     rcx, [rbp+0B40h+var_8D0]; unsigned __int16 *
0x1800b1b18  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800b1b1d  lea     rax, [rbp+0B40h+var_8D0]
0x1800b1b24  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800b1b28  inc     rbx
0x1800b1b2b  cmp     [rax+rbx*2], si
0x1800b1b2f  jnz     short loc_1800B1B28
0x1800b1b31  lea     rax, [rbp+0B40h+var_8D0]
0x1800b1b38  jmp     loc_1800B19B8
0x1800b1b3d  mov     ebx, 300100h
0x1800b1b42  cmp     eax, ebx
0x1800b1b44  jz      short loc_1800B1B4B
0x1800b1b46  bts     [rbp+0B40h+var_B70], 0Dh
0x1800b1b4b  mov     rax, [r14]
0x1800b1b4e  lea     rdx, [rbp+0B40h+var_B48]
0x1800b1b52  mov     rcx, r14
0x1800b1b55  mov     rax, [rax+50h]
0x1800b1b59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1b5e  mov     edi, eax
0x1800b1b60  test    eax, eax
0x1800b1b62  jns     short loc_1800B1BD2
0x1800b1b64  cmp     dword ptr cs:xmmword_180169738, esi
0x1800b1b6a  mov     [rsp+0C40h+var_BD0], esi
0x1800b1b6e  mov     dword ptr [rsp+0C40h+hKey], eax
0x1800b1b72  jz      loc_1800B1923
0x1800b1b78  mov     rdx, 4000000000000800h; unsigned __int64
0x1800b1b82  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800b1b89  jz      loc_1800B1923
0x1800b1b8f  mov     rax, cs:qword_180169748
0x1800b1b96  and     rax, rdx
0x1800b1b99  cmp     cs:qword_180169748, rax
0x1800b1ba0  jnz     loc_1800B1923
0x1800b1ba6  lea     rcx, [rbp+0B40h+var_850]; unsigned __int16 *
0x1800b1bad  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800b1bb2  lea     rax, [rbp+0B40h+var_850]
0x1800b1bb9  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800b1bbd  inc     rbx
0x1800b1bc0  cmp     [rax+rbx*2], si
0x1800b1bc4  jnz     short loc_1800B1BBD
0x1800b1bc6  lea     rax, [rbp+0B40h+var_850]
0x1800b1bcd  jmp     loc_1800B19B8
0x1800b1bd2  cmp     eax, ebx
0x1800b1bd4  jz      short loc_1800B1BDB
0x1800b1bd6  bts     [rbp+0B40h+var_B70], 1Ch
0x1800b1bdb  mov     rcx, [rbp+0B40h+var_BA8]
0x1800b1bdf  lea     rdx, [rbp+0B40h+var_B38]
0x1800b1be3  mov     rax, [rcx]
0x1800b1be6  mov     rax, [rax+50h]
0x1800b1bea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1bef  mov     edi, eax
0x1800b1bf1  test    eax, eax
0x1800b1bf3  jns     short loc_1800B1C63
0x1800b1bf5  cmp     dword ptr cs:xmmword_180169738, esi
0x1800b1bfb  mov     [rsp+0C40h+var_BD0], esi
0x1800b1bff  mov     dword ptr [rsp+0C40h+hKey], eax
0x1800b1c03  jz      loc_1800B1923
0x1800b1c09  mov     rdx, 4000000000000800h; unsigned __int64
0x1800b1c13  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800b1c1a  jz      loc_1800B1923
0x1800b1c20  mov     rax, cs:qword_180169748
0x1800b1c27  and     rax, rdx
  ... truncated ...
```
