# CDataLinkDialog_Connect::ConnectToDS(int *,ulong *,wchar_t *,ulong,IDBInitialize * *,IUnknown * *,int)

- ea: `0x180036300`
- end: `0x180037070`
- name: `?ConnectToDS@CDataLinkDialog_Connect@@AEAAJPEAHPEAKPEA_WKPEAPEAUIDBInitialize@@PEAPEAUIUnknown@@H@Z`
- size: `3440`
- prototype: `__int64 __fastcall(CDataLinkDialog_Connect *__hidden this, int *, unsigned int *, wchar_t *, unsigned int, struct IDBInitialize **, struct IUnknown **, int)`
- caller_count: `3`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18003b320`
- `0x18003bc30`
- `0x18003c8b0`

## callees

- `0x180003030`
- `0x1800030c0`
- `0x180003488`
- `0x180003d20`
- `0x180003d80`
- `0x180007050`
- `0x180036300`
- `0x180037080`
- `0x180038950`
- `0x1801a65e1`
- `0x1801ad6a0`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1800364a4`
- `ole32!CoCreateInstance` at `0x1800364a4`
- `ole32!CoTaskMemFree` at `0x180036ccf`
- `ole32!CoTaskMemFree` at `0x180036ce8`
- `ole32!CoTaskMemFree` at `0x180036ccf`
- `ole32!CoTaskMemFree` at `0x180036ce8`
- `USER32!LoadStringW` at `0x1800365db`
- `USER32!LoadStringW` at `0x1800368f9`
- `USER32!LoadStringW` at `0x180036ad4`
- `USER32!LoadStringW` at `0x180036b12`
- `USER32!LoadStringW` at `0x1800365db`
- `USER32!LoadStringW` at `0x1800368f9`
- `USER32!LoadStringW` at `0x180036ad4`
- `USER32!LoadStringW` at `0x180036b12`
- `USER32!MessageBoxW` at `0x180036b37`
- `USER32!MessageBoxW` at `0x180036b37`
- `OLEAUT32!__imp_VariantClear` at `0x180036cb1`
- `OLEAUT32!__imp_VariantClear` at `0x180036cb1`

## pseudocode

```c
__int64 __fastcall CDataLinkDialog_Connect::ConnectToDS(
        CDataLinkDialog_Connect *this,
        int *a2,
        unsigned int *a3,
        wchar_t *a4,
        unsigned int a5,
        struct IDBInitialize **a6,
        struct IUnknown **a7,
        int a8)
{
  wchar_t *v8; // r15
  CDataLinkDialog_Connect *v9; // r13
  struct IDBInitialize **v10; // r12
  struct tagDBPROPSET *v11; // rsi
  struct tagDBPROPSET *v12; // rdi
  GUID *p_guidPropertySet; // rbx
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r8
  unsigned int v18; // r9d
  unsigned int v19; // r8d
  HRESULT v20; // eax
  int v21; // eax
  UINT v22; // r15d
  unsigned __int64 v23; // r11
  __int64 *v24; // r8
  unsigned __int64 v25; // rbx
  unsigned int v26; // edx
  unsigned int v27; // r9d
  __int64 v28; // r10
  int v29; // eax
  WCHAR *v30; // rdi
  unsigned __int64 v31; // rbx
  unsigned int v32; // r12d
  __int64 v33; // r13
  CDataLinkDialog_Connect *v34; // rcx
  int v35; // r15d
  const wchar_t *v36; // rsi
  unsigned __int64 v37; // rcx
  WCHAR *v38; // rdx
  __int64 v39; // r8
  WCHAR v40; // ax
  WCHAR *v41; // rax
  __int64 v42; // rax
  unsigned __int64 v43; // rcx
  WCHAR *v44; // rdx
  __int64 v45; // r8
  WCHAR v46; // ax
  WCHAR *v47; // rax
  __int64 v48; // rax
  unsigned __int64 v49; // rcx
  WCHAR *v50; // rdx
  __int64 v51; // r8
  WCHAR v52; // ax
  WCHAR *v53; // rax
  __int64 v54; // rax
  UINT v55; // edx
  unsigned __int64 v56; // rcx
  WCHAR *v57; // rdx
  __int64 v58; // r8
  WCHAR v59; // ax
  WCHAR *v60; // rax
  __int64 v61; // rax
  unsigned __int64 v62; // rcx
  WCHAR *v63; // rdx
  __int64 v64; // r8
  WCHAR v65; // ax
  WCHAR *v66; // rax
  __int64 v67; // rax
  unsigned __int64 v68; // rcx
  WCHAR *v69; // rdx
  __int64 v70; // r8
  WCHAR v71; // ax
  WCHAR *v72; // rax
  __int64 v73; // rax
  int v74; // eax
  int v75; // ebx
  struct IUnknown *v76; // rcx
  int v77; // eax
  int v78; // eax
  int v79; // eax
  unsigned int i; // esi
  unsigned int v81; // ebx
  __int64 v82; // rdi
  char *v83; // rcx
  _QWORD *v84; // r8
  unsigned int *v85; // rcx
  int ppv; // [rsp+20h] [rbp-3138h]
  int v89; // [rsp+48h] [rbp-3110h]
  __int64 pExceptionObject; // [rsp+60h] [rbp-30F8h] BYREF
  __int64 v91; // [rsp+68h] [rbp-30F0h] BYREF
  __int64 v92; // [rsp+70h] [rbp-30E8h] BYREF
  wchar_t *v93; // [rsp+78h] [rbp-30E0h]
  struct IDBInitialize **v94; // [rsp+80h] [rbp-30D8h]
  __int64 v95; // [rsp+88h] [rbp-30D0h] BYREF
  __int64 v96; // [rsp+90h] [rbp-30C8h] BYREF
  __int64 v97; // [rsp+98h] [rbp-30C0h] BYREF
  struct IUnknown **v98; // [rsp+A0h] [rbp-30B8h]
  __int64 v99; // [rsp+A8h] [rbp-30B0h] BYREF
  __int64 v100; // [rsp+B0h] [rbp-30A8h] BYREF
  unsigned int *v101; // [rsp+B8h] [rbp-30A0h]
  int *v102; // [rsp+C0h] [rbp-3098h]
  struct IUnknown *v103; // [rsp+C8h] [rbp-3090h] BYREF
  LPVOID v104; // [rsp+D0h] [rbp-3088h] BYREF
  LPVOID pv; // [rsp+D8h] [rbp-3080h] BYREF
  __int64 v106; // [rsp+E0h] [rbp-3078h] BYREF
  int *v107; // [rsp+E8h] [rbp-3070h] BYREF
  int v108; // [rsp+F0h] [rbp-3068h]
  GUID v109; // [rsp+F4h] [rbp-3064h]
  int v110; // [rsp+104h] [rbp-3054h]
  unsigned int v111; // [rsp+108h] [rbp-3050h] BYREF
  int v112; // [rsp+10Ch] [rbp-304Ch] BYREF
  WCHAR v113; // [rsp+110h] [rbp-3048h] BYREF
  char v114[1022]; // [rsp+112h] [rbp-3046h] BYREF
  WCHAR Caption; // [rsp+510h] [rbp-2C48h] BYREF
  char v116[1022]; // [rsp+512h] [rbp-2C46h] BYREF
  WCHAR Buffer; // [rsp+910h] [rbp-2848h] BYREF
  char v118[10238]; // [rsp+912h] [rbp-2846h] BYREF

  v8 = a4;
  v93 = a4;
  v101 = a3;
  v102 = a2;
  v9 = this;
  v10 = a6;
  v94 = a6;
  v98 = a7;
  v89 = 0;
  *a6 = 0;
  *a7 = 0;
  v110 = 0;
  v111 = 0;
  pv = 0;
  v112 = 41;
  v107 = &v112;
  v108 = 1;
  v109 = DBPROPSET_DATASOURCEINFO;
  v103 = 0;
  v104 = 0;
  v106 = 0;
  v11 = (struct tagDBPROPSET *)*((_QWORD *)this + 4);
  v12 = (struct tagDBPROPSET *)*((_QWORD *)this + 3);
  if ( v12 != v11 )
  {
    p_guidPropertySet = &v12->guidPropertySet;
    v14 = *(_QWORD *)DBPROPSET_SQLSERVERDBINIT.Data4;
    v15 = *(_QWORD *)&DBPROPSET_SQLSERVERDBINIT.Data1;
    v16 = *(_QWORD *)DBPROPSET_DBINIT.Data4;
    v17 = *(_QWORD *)&DBPROPSET_DBINIT.Data1;
    do
    {
      if ( *(_QWORD *)&p_guidPropertySet->Data1 == v17 && *(_QWORD *)p_guidPropertySet->Data4 == v16 )
      {
        v18 = 7;
        v19 = 0;
      }
      else
      {
        if ( *(_QWORD *)&p_guidPropertySet->Data1 != v15 || *(_QWORD *)p_guidPropertySet->Data4 != v14 )
          goto LABEL_10;
        v18 = 15;
        v19 = 7;
      }
      CDataLinkDialog_Connect::CopyToPropSetHelper(v9, v12, v19, v18);
      v17 = *(_QWORD *)&DBPROPSET_DBINIT.Data1;
      v16 = *(_QWORD *)DBPROPSET_DBINIT.Data4;
      v15 = *(_QWORD *)&DBPROPSET_SQLSERVERDBINIT.Data1;
      v14 = *(_QWORD *)DBPROPSET_SQLSERVERDBINIT.Data4;
LABEL_10:
      ++v12;
      p_guidPropertySet += 2;
    }
    while ( v12 != v11 );
  }
  v20 = CoCreateInstance(&CLSID_MSOLEDBSQL19, 0, 1u, &IID_IDBProperties, &v104);
  if ( v20 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      _mm_lfence();
      bidTraceHR(off_180260360[0], 2777097, (unsigned int)v20);
    }
    v104 = 0;
    pExceptionObject = 0;
    throw (__int64 *)&pExceptionObject;
  }
  v21 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v104 + 40LL))(
          v104,
          (__int64)(*((_QWORD *)v9 + 4) - *((_QWORD *)v9 + 3)) >> 5);
  if ( v21 != -2147217887 && v21 != 265946 )
  {
    if ( v21 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        _mm_lfence();
        bidTraceHR(off_180260360[0], 2922505, (unsigned int)v21);
      }
      v91 = 0;
      throw (__int64 *)&v91;
    }
    goto LABEL_133;
  }
  if ( (bidGblFlags & 2) != 0 )
    bidTraceHR(off_180260360[0], 2785289, (unsigned int)v21);
  Buffer = 0;
  memset_0(v118, 0, 0x27FAu);
  v22 = 40079;
  v89 = 1;
  v23 = 0;
  v24 = (__int64 *)*((_QWORD *)v9 + 3);
  v25 = (__int64)(*((_QWORD *)v9 + 4) - (_QWORD)v24) >> 5;
  if ( v25 )
  {
    do
    {
      if ( *(_QWORD *)&DBPROPSET_SQLSERVERDBINIT.Data1 == *(__int64 *)((char *)v24 + 12)
        && *(_QWORD *)DBPROPSET_SQLSERVERDBINIT.Data4 == *(__int64 *)((char *)v24 + 20) )
      {
        v26 = 0;
        v27 = *((_DWORD *)v24 + 2);
        if ( v27 )
        {
          v28 = *v24;
          do
          {
            if ( *(_DWORD *)(v28 + 72LL * v26 + 8) )
            {
              if ( *(_DWORD *)(v28 + 72LL * v26) == 30 )
              {
                v22 = 40036;
                goto LABEL_31;
              }
              if ( *(_DWORD *)(v28 + 72LL * v26) == 31 )
              {
                v22 = 40037;
                goto LABEL_31;
              }
            }
            ++v26;
          }
          while ( v26 < v27 );
        }
      }
      ++v23;
      v24 += 4;
    }
    while ( v23 < v25 );
  }
LABEL_31:
  v29 = LoadStringW(g_hinstance_language, v22, &Buffer, 5118);
  v30 = (WCHAR *)&v118[2 * v29 - 2];
  v31 = 5118LL - v29;
  v32 = 0;
  v33 = 0;
  v34 = this;
  do
  {
    v35 = *((_DWORD *)v34 + 18 * v33 + 14);
    if ( !v35 )
      goto LABEL_130;
    v36 = 0;
    switch ( v32 )
    {
      case 0u:
        v36 = L"Data Source";
        break;
      case 1u:
        v36 = L"Integrated Security";
        break;
      case 2u:
        v36 = L"User ID";
        break;
      case 3u:
        v36 = L"Password";
        break;
      case 4u:
        v36 = L"Persist Security Info";
        break;
      case 5u:
        v36 = L"Initial Catalog";
        break;
      case 6u:
        v36 = L"Window Handle";
        break;
      case 7u:
        v36 = L"Initial File Name";
        break;
      case 8u:
        v36 = L"Old Password";
        break;
      case 9u:
        v36 = L"Server SPN";
        break;
      case 0xAu:
        v36 = L"Authentication";
        break;
      default:
        break;
    }
    if ( v31 )
    {
      if ( v31 > 0x7FFFFFFF )
      {
        *v30 = 0;
      }
      else
      {
        v37 = v31;
        v38 = v30;
        v39 = 0;
        do
        {
          if ( !(2147483646 - v31 + v37) )
            break;
          v40 = *(WCHAR *)((char *)v38 + (char *)L"\"" - (char *)v30);
          if ( !v40 )
            break;
          *v38++ = v40;
          ++v39;
          --v37;
        }
        while ( v37 );
        v41 = v38 - 1;
        if ( v37 )
          v41 = v38;
        *v41 = 0;
        v42 = v39 - 1;
        if ( v37 )
          v42 = v39;
        v30 += v42;
        v31 -= v42;
      }
      if ( v31 )
      {
        if ( v31 > 0x7FFFFFFF )
        {
          *v30 = 0;
        }
        else
        {
          v43 = v31;
          v44 = v30;
          v45 = 0;
          do
          {
            if ( !(v43 + 2147483646 - v31) )
              break;
            v46 = *(WCHAR *)((char *)v44 + (char *)v36 - (char *)v30);
            if ( !v46 )
              break;
            *v44++ = v46;
            ++v45;
            --v43;
          }
          while ( v43 );
          v47 = v44 - 1;
          if ( v43 )
            v47 = v44;
          *v47 = 0;
          v48 = v45 - 1;
          if ( v43 )
            v48 = v45;
          v30 += v48;
          v31 -= v48;
        }
        if ( v31 )
        {
          if ( v31 > 0x7FFFFFFF )
          {
            *v30 = 0;
          }
          else
          {
            v49 = v31;
            v50 = v30;
            v51 = 0;
            do
            {
              if ( !(v49 + 2147483646 - v31) )
                break;
              v52 = *(WCHAR *)((char *)v50 + (char *)L"\"\t" - (char *)v30);
              if ( !v52 )
                break;
              *v50++ = v52;
              ++v51;
              --v49;
            }
            while ( v49 );
            v53 = v50 - 1;
            if ( v49 )
              v53 = v50;
            *v53 = 0;
            v54 = v51 - 1;
            if ( v49 )
              v54 = v51;
            v30 += v54;
            v31 -= v54;
          }
        }
      }
    }
    v113 = 0;
    memset_0(v114, 0, sizeof(v114));
    if ( (bidGblFlags & 2) != 0 && off_180262F48[0] )
    {
      ppv = v35;
      bidTraceW(off_180260360[0], 2854912, off_180262F48[0], v36);
    }
    switch ( v35 )
    {
      case 1:
        v55 = 40082;
        break;
      case 2:
        v55 = 40083;
        break;
      case 3:
        v55 = 40084;
        break;
      case 4:
        v55 = 40085;
        break;
      case 5:
        v55 = 40086;
        break;
      case 6:
        v55 = 40087;
        break;
      case 7:
        v55 = 40088;
        break;
      case 8:
        v55 = 40089;
        break;
      default:
        v55 = 40090;
        break;
    }
    LoadStringW(g_hinstance_language, v55, &v113, 512);
    if ( v31 )
    {
      if ( v31 > 0x7FFFFFFF )
      {
        *v30 = 0;
      }
      else
      {
        v56 = v31;
        v57 = v30;
        v58 = 0;
        do
        {
          if ( !(2147483646 - v31 + v56) )
            break;
          v59 = *(WCHAR *)((char *)v57 + (char *)L"(" - (char *)v30);
          if ( !v59 )
            break;
          *v57++ = v59;
          ++v58;
          --v56;
        }
        while ( v56 );
        v60 = v57 - 1;
        if ( v56 )
          v60 = v57;
        *v60 = 0;
        v61 = v58 - 1;
        if ( v56 )
          v61 = v58;
        v30 += v61;
        v31 -= v61;
      }
      if ( v31 )
      {
        if ( v31 > 0x7FFFFFFF )
        {
          *v30 = 0;
        }
        else
        {
          v62 = v31;
          v63 = v30;
          v64 = 0;
          do
          {
            if ( !(2147483646 - v31 + v62) )
              break;
            v65 = *(WCHAR *)((char *)v63 + (char *)&v113 - (char *)v30);
            if ( !v65 )
              break;
            *v63++ = v65;
            ++v64;
            --v62;
          }
          while ( v62 );
          v66 = v63 - 1;
          if ( v62 )
            v66 = v63;
          *v66 = 0;
          v67 = v64 - 1;
          if ( v62 )
            v67 = v64;
          v30 += v67;
          v31 -= v67;
          if ( !v31 )
            goto LABEL_129;
        }
        if ( v31 > 0x7FFFFFFF )
        {
          *v30 = 0;
        }
        else
        {
          v68 = v31;
          v69 = v30;
          v70 = 0;
          do
          {
            if ( !(v68 + 2147483646 - v31) )
              break;
            v71 = *(WCHAR *)((char *)v69 + (char *)L")\n\r" - (char *)v30);
            if ( !v71 )
              break;
            *v69++ = v71;
            ++v70;
            --v68;
          }
          while ( v68 );
          v72 = v69 - 1;
          if ( v68 )
            v72 = v69;
          *v72 = 0;
          v73 = v70 - 1;
          if ( v68 )
            v73 = v70;
          v30 += v73;
          v31 -= v73;
        }
      }
    }
LABEL_129:
    v34 = this;
LABEL_130:
    ++v32;
    ++v33;
  }
  while ( v32 < 0xF );
  LoadStringW(g_hinstance_language, 0x9C90u, v30, v31);
  Caption = 0;
  memset_0(v116, 0, sizeof(v116));
  LoadStringW(g_hinstance_language, 0x9C83u, &Caption, 512);
  v9 = this;
  if ( MessageBoxW(*((HWND *)this + 2), &Buffer, &Caption, 0x14u) != 6 )
  {
    if ( (bidGblFlags & 2) != 0 && off_180262F50[0] && bidID != -1 )
      ((void (__fastcall *)(__int64, char *, __int64, wchar_t *, _QWORD))off_180248050[0])(
        bidID,
        off_180260360[0],
        2915328,
        off_180262F50[0],
        0);
    v92 = 0;
    throw (__int64 *)&v92;
  }
  v8 = v93;
  v10 = v94;
LABEL_133:
  v74 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, struct IUnknown **))v104)(v104, &IID_IDBInitialize, &v103);
  if ( v74 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      _mm_lfence();
      bidTraceHR(off_180260360[0], 2929673, (unsigned int)v74);
    }
    v103 = 0;
    v95 = 0;
    throw (__int64 *)&v95;
  }
  v75 = ((__int64 (__fastcall *)(struct IUnknown *))v103->lpVtbl[1].QueryInterface)(v103);
  if ( v75 < 0 )
  {
    if ( a8 )
      CDataLinkDialog_Connect::ConnectionMessageBox(v9, v103, &GUID_0c733a8b_2a1c_11ce_ade5_00aa0044773d);
    if ( (bidGblFlags & 2) != 0 )
    {
      _mm_lfence();
      bidTraceHR(off_180260360[0], 2939913, (unsigned int)v75);
    }
    if ( v75 != -2147217842 )
    {
      ((void (__fastcall *)(struct IUnknown *))v103->lpVtbl->Release)(v103);
      v103 = 0;
    }
    v96 = 0;
    throw (__int64 *)&v96;
  }
  v76 = v103;
  *v10 = (struct IDBInitialize *)v103;
  v77 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))v76->lpVtbl->QueryInterface)(
          v76,
          &IID_IDBCreateSession,
          &v106);
  if ( v77 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      _mm_lfence();
      bidTraceHR(off_180260360[0], 2954249, (unsigned int)v77);
    }
    v106 = 0;
    v97 = 0;
    throw (__int64 *)&v97;
  }
  v78 = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, struct IUnknown **, int))(*(_QWORD *)v106 + 24LL))(
          v106,
          0,
          &IID_IUnknown,
          v98,
          ppv);
  if ( v78 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      _mm_lfence();
      bidTraceHR(off_180260360[0], 2962441, (unsigned int)v78);
    }
    v99 = 0;
    throw (__int64 *)&v99;
  }
  if ( v8 )
  {
    v79 = (*(__int64 (__fastcall **)(LPVOID, __int64, int **, unsigned int *, LPVOID *))(*(_QWORD *)v104 + 24LL))(
            v104,
            1,
            &v107,
            &v111,
            &pv);
    if ( v79 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        _mm_lfence();
        bidTraceHR(off_180260360[0], 2972681, (unsigned int)v79);
      }
      v100 = 0;
      throw (__int64 *)&v100;
    }
    StringCchCopyW(v8, a5, *(const wchar_t **)(*(_QWORD *)pv + 56LL));
    for ( i = 0; i < v111; ++i )
    {
      v81 = 0;
      v82 = 32LL * i;
      v83 = (char *)pv;
      v84 = (char *)pv + v82;
      if ( *(_DWORD *)((char *)pv + v82 + 8) )
      {
        do
        {
          VariantClear((VARIANTARG *)(*v84 + 8 * (9LL * v81++ + 6)));
          v83 = (char *)pv;
          v84 = (char *)pv + v82;
        }
        while ( v81 < *(_DWORD *)((char *)pv + v82 + 8) );
      }
      CoTaskMemFree(*(LPVOID *)&v83[v82]);
    }
    CoTaskMemFree(pv);
  }
  v85 = v101;
  if ( v102 )
    *v102 = v89;
  if ( v85 )
    *v85 = 0;
  if ( v104 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v104 + 16LL))(v104);
    v104 = 0;
  }
  if ( v106 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v106 + 16LL))(v106);
  return 0;
}

```

## disassembly

```asm
0x180036300  push    rbx
0x180036302  push    rsi
0x180036303  push    rdi
0x180036304  push    r12
0x180036306  push    r13
0x180036308  push    r14
0x18003630a  push    r15
0x18003630c  mov     eax, 3120h
0x180036311  call    _alloca_probe
0x180036316  sub     rsp, rax
0x180036319  mov     rax, cs:__security_cookie
0x180036320  xor     rax, rsp
0x180036323  mov     [rsp+3158h+var_48], rax
0x18003632b  mov     r15, r9
0x18003632e  mov     [rsp+3158h+var_30E0], r9
0x180036333  mov     [rsp+3158h+var_30A0], r8
0x18003633b  mov     [rsp+3158h+var_3098], rdx
0x180036343  mov     r13, rcx
0x180036346  mov     [rsp+3158h+var_3118], rcx
0x18003634b  mov     [rsp+3158h+var_3108], rdx
0x180036350  mov     [rsp+3158h+var_3100], r8
0x180036355  mov     r12, [rsp+3158h+arg_28]
0x18003635d  mov     [rsp+3158h+var_30D8], r12
0x180036365  mov     rax, [rsp+3158h+arg_30]
0x18003636d  mov     [rsp+3158h+var_30B8], rax
0x180036375  xor     r14d, r14d
0x180036378  mov     [rsp+3158h+var_3110], r14d
0x18003637d  mov     [rsp+3158h+var_3124], r14d
0x180036382  mov     [r12], r14
0x180036386  mov     [rax], r14
0x180036389  mov     [rsp+3158h+var_3054], r14d
0x180036391  mov     [rsp+3158h+var_3050], r14d
0x180036399  mov     [rsp+3158h+pv], r14
0x1800363a1  mov     [rsp+3158h+var_304C], 29h ; ')'
0x1800363ac  lea     rax, [rsp+3158h+var_304C]
0x1800363b4  mov     [rsp+3158h+var_3070], rax
0x1800363bc  mov     [rsp+3158h+var_3068], 1
0x1800363c7  movups  xmm0, xmmword ptr cs:DBPROPSET_DATASOURCEINFO.Data1
0x1800363ce  movups  [rsp+3158h+var_3064], xmm0
0x1800363d6  mov     [rsp+3158h+var_3090], r14
0x1800363de  mov     [rsp+3158h+var_3088], r14
0x1800363e6  mov     [rsp+3158h+var_3078], r14
0x1800363ee  mov     rsi, [rcx+20h]
0x1800363f2  mov     rdi, [rcx+18h]
0x1800363f6  cmp     rdi, rsi
0x1800363f9  jz      loc_180036481
0x1800363ff  lea     rbx, [rdi+0Ch]
0x180036403  mov     rax, qword ptr cs:DBPROPSET_SQLSERVERDBINIT.Data4
0x18003640a  mov     rcx, qword ptr cs:DBPROPSET_SQLSERVERDBINIT.Data1
0x180036411  mov     rdx, qword ptr cs:DBPROPSET_DBINIT.Data4
0x180036418  mov     r8, qword ptr cs:DBPROPSET_DBINIT.Data1
0x18003641f  nop
0x180036420  cmp     [rbx], r8
0x180036423  jnz     short loc_180036436
0x180036425  cmp     [rbx+8], rdx
0x180036429  jnz     short loc_180036436
0x18003642b  mov     r9d, 7
0x180036431  xor     r8d, r8d
0x180036434  jmp     short loc_18003644D
0x180036436  cmp     [rbx], rcx
0x180036439  jnz     short loc_180036474
0x18003643b  cmp     [rbx+8], rax
0x18003643f  jnz     short loc_180036474
0x180036441  mov     r9d, 0Fh; unsigned int
0x180036447  mov     r8d, 7; unsigned int
0x18003644d  mov     rdx, rdi; struct tagDBPROPSET *
0x180036450  mov     rcx, r13; this
0x180036453  call    ?CopyToPropSetHelper@CDataLinkDialog_Connect@@AEAAXPEAUtagDBPROPSET@@KK@Z; CDataLinkDialog_Connect::CopyToPropSetHelper(tagDBPROPSET *,ulong,ulong)
0x180036458  mov     r8, qword ptr cs:DBPROPSET_DBINIT.Data1
0x18003645f  mov     rdx, qword ptr cs:DBPROPSET_DBINIT.Data4
0x180036466  mov     rcx, qword ptr cs:DBPROPSET_SQLSERVERDBINIT.Data1
0x18003646d  mov     rax, qword ptr cs:DBPROPSET_SQLSERVERDBINIT.Data4
0x180036474  add     rdi, 20h ; ' '
0x180036478  add     rbx, 20h ; ' '
0x18003647c  cmp     rdi, rsi
0x18003647f  jnz     short loc_180036420
0x180036481  lea     rax, [rsp+3158h+var_3088]
0x180036489  mov     qword ptr [rsp+3158h+ppv], rax; ppv
0x18003648e  lea     r9, IID_IDBProperties; riid
0x180036495  xor     edx, edx; pUnkOuter
0x180036497  mov     r8d, 1; dwClsContext
0x18003649d  lea     rcx, CLSID_MSOLEDBSQL19; rclsid
0x1800364a4  call    cs:__imp_CoCreateInstance
0x1800364aa  mov     [rsp+3158h+var_3128], eax
0x1800364ae  test    eax, eax
0x1800364b0  js      loc_180036D8B
0x1800364b6  mov     r8, [r13+18h]
0x1800364ba  mov     rdx, [r13+20h]
0x1800364be  sub     rdx, r8
0x1800364c1  sar     rdx, 5
0x1800364c5  mov     rcx, [rsp+3158h+var_3088]
0x1800364cd  mov     rax, [rcx]
0x1800364d0  mov     rax, [rax+28h]
0x1800364d4  call    cs:__guard_dispatch_icall_fptr
0x1800364da  mov     [rsp+3158h+var_3128], eax
0x1800364de  cmp     eax, 80040E21h
0x1800364e3  jz      short loc_1800364F9
0x1800364e5  cmp     eax, 40EDAh
0x1800364ea  jz      short loc_1800364F9
0x1800364ec  test    eax, eax
0x1800364ee  js      loc_180036DD1
0x1800364f4  jmp     loc_180036B53
0x1800364f9  test    byte ptr cs:_bidGblFlags, 2
0x180036500  jz      short loc_180036516
0x180036502  mov     r8d, eax
0x180036505  mov     edx, 2A8009h
0x18003650a  mov     rcx, cs:off_180260360; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x180036511  call    _bidTraceHR
0x180036516  mov     [rsp+3158h+Buffer], r14w
0x18003651f  xor     edx, edx; Val
0x180036521  mov     r8d, 27FAh; Size
0x180036527  lea     rcx, [rsp+3158h+var_2846]; void *
0x18003652f  call    memset_0
0x180036534  mov     r15d, 9C8Fh
0x18003653a  mov     [rsp+3158h+var_3110], 1
0x180036542  mov     r11, r14
0x180036545  mov     r8, [r13+18h]
0x180036549  mov     rbx, [r13+20h]
0x18003654d  sub     rbx, r8
0x180036550  sar     rbx, 5
0x180036554  test    rbx, rbx
0x180036557  jz      short loc_1800365C1
0x180036559  mov     rdi, qword ptr cs:DBPROPSET_SQLSERVERDBINIT.Data4
0x180036560  mov     rsi, qword ptr cs:DBPROPSET_SQLSERVERDBINIT.Data1
0x180036567  cmp     rsi, [r8+0Ch]
0x18003656b  jnz     short loc_1800365A5
0x18003656d  cmp     rdi, [r8+14h]
0x180036571  jnz     short loc_1800365A5
0x180036573  mov     edx, r14d
0x180036576  mov     r9d, [r8+8]
0x18003657a  test    r9d, r9d
0x18003657d  jz      short loc_1800365A5
0x18003657f  mov     r10, [r8]
0x180036582  mov     eax, edx
0x180036584  lea     rcx, [rax+rax*8]
0x180036588  cmp     dword ptr [r10+rcx*8+8], 0
0x18003658e  jz      short loc_18003659E
0x180036590  mov     eax, [r10+rcx*8]
0x180036594  sub     eax, 1Eh
0x180036597  jz      short loc_1800365BB
0x180036599  cmp     eax, 1
0x18003659c  jz      short loc_1800365B3
0x18003659e  inc     edx
0x1800365a0  cmp     edx, r9d
0x1800365a3  jb      short loc_180036582
0x1800365a5  inc     r11
0x1800365a8  add     r8, 20h ; ' '
0x1800365ac  cmp     r11, rbx
0x1800365af  jb      short loc_180036567
0x1800365b1  jmp     short loc_1800365C1
0x1800365b3  mov     r15d, 9C65h
0x1800365b9  jmp     short loc_1800365C1
0x1800365bb  mov     r15d, 9C64h
0x1800365c1  mov     ebx, 13FEh
0x1800365c6  mov     r9d, ebx; cchBufferMax
0x1800365c9  lea     r8, [rsp+3158h+Buffer]; lpBuffer
0x1800365d1  mov     edx, r15d; uID
0x1800365d4  mov     rcx, cs:?g_hinstance_language@@3PEAUHINSTANCE__@@EA; hInstance
0x1800365db  call    cs:__imp_LoadStringW
0x1800365e1  movsxd  rcx, eax
0x1800365e4  lea     rdi, [rsp+3158h+Buffer]
0x1800365ec  lea     rdi, [rdi+rcx*2]
0x1800365f0  sub     rbx, rcx
0x1800365f3  mov     r12d, r14d
0x1800365f6  mov     r13, r14
0x1800365f9  lea     rdx, cs:180000000h
0x180036600  mov     rcx, [rsp+3158h+var_3118]
0x180036605  nop     word ptr [rax+rax+00000000h]
0x180036610  lea     rax, ds:0[r13*8]
0x180036618  add     rax, r13
0x18003661b  mov     r15d, [rcx+rax*8+38h]
0x180036620  test    r15d, r15d
0x180036623  jz      loc_180036AB2
0x180036629  mov     rsi, r14
0x18003662c  cmp     r12d, 0Ah; switch 11 cases
0x180036630  ja      short def_18003663F; jumptable 000000018003663F default case
0x180036632  mov     eax, r12d
0x180036635  mov     ecx, ds:(jpt_18003663F - 180000000h)[rdx+rax*4]
0x18003663c  add     rcx, rdx
0x18003663f  jmp     rcx; switch jump
0x180036641  mov     rsi, cs:off_1801C7E50; jumptable 000000018003663F case 0
0x180036648  jmp     short def_18003663F; jumptable 000000018003663F default case
0x18003664a  mov     rsi, cs:off_1801C7E18; jumptable 000000018003663F case 1
0x180036651  jmp     short def_18003663F; jumptable 000000018003663F default case
0x180036653  mov     rsi, cs:off_1801C8198; jumptable 000000018003663F case 9
0x18003665a  jmp     short def_18003663F; jumptable 000000018003663F default case
0x18003665c  mov     rsi, cs:off_1801C7E40; jumptable 000000018003663F case 2
0x180036663  jmp     short def_18003663F; jumptable 000000018003663F default case
0x180036665  mov     rsi, cs:off_1801C7E28; jumptable 000000018003663F case 3
0x18003666c  jmp     short def_18003663F; jumptable 000000018003663F default case
0x18003666e  mov     rsi, cs:off_1801C7E38; jumptable 000000018003663F case 4
0x180036675  jmp     short def_18003663F; jumptable 000000018003663F default case
0x180036677  mov     rsi, cs:off_1801C7FE0; jumptable 000000018003663F case 5
0x18003667e  jmp     short def_18003663F; jumptable 000000018003663F default case
0x180036680  mov     rsi, cs:off_1801C7E58; jumptable 000000018003663F case 6
0x180036687  jmp     short def_18003663F; jumptable 000000018003663F default case
0x180036689  mov     rsi, cs:off_1801C7FE8; jumptable 000000018003663F case 7
0x180036690  jmp     short def_18003663F; jumptable 000000018003663F default case
0x180036692  mov     rsi, cs:off_1801C8100; jumptable 000000018003663F case 8
0x180036699  jmp     short def_18003663F; jumptable 000000018003663F default case
0x18003669b  mov     rsi, cs:off_1801C81D0; jumptable 000000018003663F case 10
0x1800366a2  test    rbx, rbx; jumptable 000000018003663F default case
0x1800366a5  jz      loc_180036838
0x1800366ab  cmp     rbx, 7FFFFFFFh
0x1800366b2  ja      short loc_18003671F
0x1800366b4  mov     rcx, rbx
0x1800366b7  mov     rdx, rdi
0x1800366ba  mov     r8, r14
0x1800366bd  mov     r9d, 7FFFFFFEh
0x1800366c3  sub     r9, rbx
0x1800366c6  lea     r10, asc_1801C0B40; "\""
0x1800366cd  sub     r10, rdi
0x1800366d0  lea     rax, [r9+rcx]
0x1800366d4  test    rax, rax
0x1800366d7  jz      short loc_1800366F3
0x1800366d9  movzx   eax, word ptr [r10+rdx]
0x1800366de  test    ax, ax
0x1800366e1  jz      short loc_1800366F3
0x1800366e3  mov     [rdx], ax
0x1800366e6  add     rdx, 2
0x1800366ea  inc     r8
0x1800366ed  sub     rcx, 1
0x1800366f1  jnz     short loc_1800366D0
0x1800366f3  lea     rax, [rdx-2]
0x1800366f7  test    rcx, rcx
0x1800366fa  cmovnz  rax, rdx
0x1800366fe  mov     [rax], r14w
0x180036702  lea     rax, [r8-1]
0x180036706  cmovnz  rax, r8
0x18003670a  lea     r8, [rdi+rax*2]
0x18003670e  mov     rdx, rbx
0x180036711  sub     rdx, rax
0x180036714  test    rcx, rcx
0x180036717  mov     rdi, r8
0x18003671a  mov     rbx, rdx
0x18003671d  jmp     short loc_18003672C
0x18003671f  test    rbx, rbx
0x180036722  jz      loc_180036838
0x180036728  mov     [rdi], r14w
0x18003672c  test    rbx, rbx
0x18003672f  jz      loc_180036838
0x180036735  cmp     rbx, 7FFFFFFFh
0x18003673c  ja      short loc_1800367A5
0x18003673e  mov     rcx, rbx
0x180036741  mov     rdx, rdi
0x180036744  mov     r8, r14
0x180036747  mov     r9d, 7FFFFFFEh
0x18003674d  sub     r9, rbx
0x180036750  mov     r10, rsi
0x180036753  sub     r10, rdi
0x180036756  lea     rax, [rcx+r9]
0x18003675a  test    rax, rax
0x18003675d  jz      short loc_180036779
0x18003675f  movzx   eax, word ptr [rdx+r10]
0x180036764  test    ax, ax
0x180036767  jz      short loc_180036779
0x180036769  mov     [rdx], ax
0x18003676c  add     rdx, 2
0x180036770  inc     r8
0x180036773  sub     rcx, 1
0x180036777  jnz     short loc_180036756
0x180036779  lea     rax, [rdx-2]
0x18003677d  test    rcx, rcx
0x180036780  cmovnz  rax, rdx
0x180036784  mov     [rax], r14w
0x180036788  lea     rax, [r8-1]
0x18003678c  cmovnz  rax, r8
0x180036790  lea     r8, [rdi+rax*2]
0x180036794  mov     rdx, rbx
0x180036797  sub     rdx, rax
0x18003679a  test    rcx, rcx
0x18003679d  mov     rdi, r8
0x1800367a0  mov     rbx, rdx
0x1800367a3  jmp     short loc_1800367B2
0x1800367a5  test    rbx, rbx
0x1800367a8  jz      loc_180036838
0x1800367ae  mov     [rdi], r14w
0x1800367b2  test    rbx, rbx
0x1800367b5  jz      loc_180036838
0x1800367bb  cmp     rbx, 7FFFFFFFh
0x1800367c2  ja      short loc_18003682F
0x1800367c4  mov     rcx, rbx
0x1800367c7  mov     rdx, rdi
0x1800367ca  mov     r8, r14
0x1800367cd  mov     r9d, 7FFFFFFEh
0x1800367d3  sub     r9, rbx
0x1800367d6  lea     r10, asc_1801C0B44; "\"\t"
0x1800367dd  sub     r10, rdi
0x1800367e0  lea     rax, [rcx+r9]
0x1800367e4  test    rax, rax
0x1800367e7  jz      short loc_180036803
0x1800367e9  movzx   eax, word ptr [rdx+r10]
0x1800367ee  test    ax, ax
0x1800367f1  jz      short loc_180036803
0x1800367f3  mov     [rdx], ax
0x1800367f6  add     rdx, 2
0x1800367fa  inc     r8
0x1800367fd  sub     rcx, 1
0x180036801  jnz     short loc_1800367E0
0x180036803  lea     rax, [rdx-2]
  ... truncated ...
```
