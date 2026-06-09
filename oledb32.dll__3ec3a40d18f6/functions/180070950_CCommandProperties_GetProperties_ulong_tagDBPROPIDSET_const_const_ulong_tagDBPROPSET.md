# CCommandProperties::GetProperties(ulong,tagDBPROPIDSET const * const,ulong *,tagDBPROPSET * *)

- ea: `0x180070950`
- end: `0x18007135b`
- name: `?GetProperties@CCommandProperties@@UEAAJKQEBUtagDBPROPIDSET@@PEAKPEAPEAUtagDBPROPSET@@@Z`
- size: `2571`
- prototype: `int(CCommandProperties *__hidden this, unsigned int, const struct tagDBPROPIDSET *const, unsigned int *, struct tagDBPROPSET **)`
- caller_count: `0`
- callee_count: `19`
- tags: `service_task, broker_com_uri`

## callees

- `0x180012250`
- `0x1800130d0`
- `0x180013394`
- `0x180013870`
- `0x180028e3c`
- `0x180029560`
- `0x180029c30`
- `0x18002b8ac`
- `0x18002ec0c`
- `0x18003c270`
- `0x18006ed60`
- `0x180070900`
- `0x180070950`
- `0x180076e50`
- `0x1800771ac`
- `0x1800772d4`
- `0x18007e6ca`
- `0x18007e700`
- `0x180087010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180070a0e`
- `KERNEL32!EnterCriticalSection` at `0x180070a0e`
- `KERNEL32!LeaveCriticalSection` at `0x180071258`
- `KERNEL32!LeaveCriticalSection` at `0x180071258`
- `OLEAUT32!__imp_VariantInit` at `0x180070f68`
- `OLEAUT32!__imp_VariantInit` at `0x18007115a`
- `OLEAUT32!__imp_VariantInit` at `0x180070f68`
- `OLEAUT32!__imp_VariantInit` at `0x18007115a`
- `ole32!CoTaskMemAlloc` at `0x180070d7c`
- `ole32!CoTaskMemAlloc` at `0x180070ebc`
- `ole32!CoTaskMemAlloc` at `0x1800710c2`
- `ole32!CoTaskMemAlloc` at `0x180070d7c`
- `ole32!CoTaskMemAlloc` at `0x180070ebc`
- `ole32!CoTaskMemAlloc` at `0x1800710c2`

## string_xrefs

- `0x180070a55`: `<CCommandProperties::GetProperties|OLEDB|ERR> `
- `0x180070d9f`: `<CCommandProperties::GetProperties|OLEDB|ERR> `
- `0x180070e64`: `<CCommandProperties::GetProperties|OLEDB|ERR> `
- `0x180070ee2`: `<CCommandProperties::GetProperties|OLEDB|ERR> `
- `0x180070ff5`: `<CCommandProperties::GetProperties|OLEDB|ERR> `
- `0x180071013`: `<CCommandProperties::GetProperties|OLEDB|ERR> `
- `0x1800710ed`: `<CCommandProperties::GetProperties|OLEDB|ERR> `
- `0x1800711f9`: `<CCommandProperties::GetProperties|OLEDB|ERR> `
- `0x180070a70`: `<CCommandProperties::GetProperties|Trace|HR> `
- `0x180070b32`: `<CCommandProperties::GetProperties|Trace|HR> `
- `0x180070d4d`: `<CCommandProperties::GetProperties|Trace|HR> `
- `0x180070dba`: `<CCommandProperties::GetProperties|Trace|HR> `
- `0x180070e7f`: `<CCommandProperties::GetProperties|Trace|HR> `
- `0x180070efd`: `<CCommandProperties::GetProperties|Trace|HR> `
- `0x18007102e`: `<CCommandProperties::GetProperties|Trace|HR> `
- `0x180071108`: `<CCommandProperties::GetProperties|Trace|HR> `
- `0x180071214`: `<CCommandProperties::GetProperties|Trace|HR> `
- `0x18007131c`: `<CCommandProperties::GetProperties|Trace|HR> `

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall CCommandProperties::GetProperties(
        struct tagDBPROPSET *this,
        unsigned int a2,
        const struct tagDBPROPIDSET *const a3,
        unsigned int *a4,
        struct tagDBPROPSET **a5)
{
  __int64 v7; // r15
  __int64 v9; // r13
  unsigned int v10; // edi
  unsigned int BidID; // eax
  unsigned int v12; // ebx
  const struct tagDBPROPIDSET *v13; // rax
  unsigned int i; // edx
  __int64 v15; // rcx
  __int64 Provider; // r15
  __int64 v17; // rbx
  unsigned int v18; // ecx
  struct tagDBPROPSET *v19; // rdx
  unsigned int IMallocCopyOfProps; // eax
  struct tagDBPROPSET *v21; // rax
  int v22; // ebx
  int v23; // r12d
  struct tagDBPROPSET *v24; // rbx
  unsigned int v25; // eax
  const struct tagDBPROPIDSET *v26; // rcx
  struct tagDBPROPSET *rgPropertyIDs; // rax
  __int64 cPropertyIDs; // rdx
  int v29; // ebx
  struct tagDBPROP *v30; // r15
  int v31; // ebx
  const struct tagDBPROPIDSET *v32; // rcx
  unsigned int v33; // eax
  struct tagDBPROPSET *v34; // rbx
  int v35; // ebx
  struct tagDBPROPSET *v36; // r15
  struct tagDBPROP *v37; // rbx
  struct tagDBPROPSET *v38; // rcx
  int v39; // ebx
  unsigned int *v41; // [rsp+30h] [rbp-178h]
  struct tagDBPROPSET **v42; // [rsp+38h] [rbp-170h]
  __int64 v43; // [rsp+40h] [rbp-168h] BYREF
  struct tagDBPROPSET *rgProperties; // [rsp+48h] [rbp-160h] BYREF
  __int64 v45; // [rsp+50h] [rbp-158h]
  struct tagDBPROPSET *v46; // [rsp+58h] [rbp-150h] BYREF
  const struct tagDBPROPIDSET *v47; // [rsp+60h] [rbp-148h]
  unsigned int v48; // [rsp+68h] [rbp-140h]
  __int64 v49; // [rsp+70h] [rbp-138h] BYREF
  struct tagDBPROPSET *v50; // [rsp+78h] [rbp-130h]
  int pExceptionObject; // [rsp+80h] [rbp-128h] BYREF
  int v52; // [rsp+84h] [rbp-124h] BYREF
  int v53; // [rsp+88h] [rbp-120h] BYREF
  int v54; // [rsp+8Ch] [rbp-11Ch] BYREF
  int v55; // [rsp+90h] [rbp-118h] BYREF
  unsigned int *v56; // [rsp+98h] [rbp-110h]
  struct tagDBPROPSET **v57; // [rsp+A0h] [rbp-108h]
  struct _GUID *p_guidPropertySet; // [rsp+A8h] [rbp-100h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+B0h] [rbp-F8h]
  struct tagDBPROP v60; // [rsp+C0h] [rbp-E8h] BYREF
  struct tagDBPROP v61; // [rsp+110h] [rbp-98h] BYREF

  v47 = a3;
  v7 = a2;
  HIDWORD(v43) = a2;
  rgProperties = this;
  v56 = a4;
  v57 = a5;
  v9 = *(_QWORD *)&this[1].guidPropertySet.Data4[4];
  v49 = -1;
  v10 = 0;
  if ( (bidGblFlags & 4) != 0 && off_1800C9600[0] )
  {
    BidID = CCCM::GetBidID((CCCM *)v9);
    v42 = a5;
    v41 = a4;
    bidScopeEnterW(&v49, off_1800C9600[0], BidID, (unsigned int)v7, v7, a3);
  }
  lpCriticalSection = (LPCRITICAL_SECTION)(v9 + 24);
  EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 24));
  if ( a4 )
    *a4 = 0;
  if ( a5 )
    *a5 = 0;
  if ( a4 && a5 )
  {
    if ( (_DWORD)v7 && !a3 )
    {
      v12 = -2147024809;
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(-2147024809, L"<CCommandProperties::GetProperties|OLEDB|ERR> ", 0x123u);
        if ( (bidGblFlags & 2) != 0 )
          v12 = bidTraceHR(off_1800C84B8[0], 297993, L"<CCommandProperties::GetProperties|Trace|HR> ", 2147942487LL);
      }
      goto LABEL_85;
    }
    v13 = a3;
    for ( i = 0; i < (unsigned int)v7; ++i )
    {
      v15 = *(_QWORD *)&v13->guidPropertySet.Data1 - *(_QWORD *)&DBPROPSET_PROPERTIESINERROR.Data1;
      if ( !v15 )
        v15 = *(_QWORD *)v13->guidPropertySet.Data4 - *(_QWORD *)DBPROPSET_PROPERTIESINERROR.Data4;
      if ( !v15 )
      {
        if ( (unsigned int)v7 > 1 || v13->cPropertyIDs || v13->rgPropertyIDs )
        {
          if ( (bidGblFlags & 2) != 0 )
            v12 = bidTraceHR(off_1800C84B8[0], 316425, L"<CCommandProperties::GetProperties|Trace|HR> ", 2147942487LL);
          else
            v12 = -2147024809;
        }
        else
        {
          Provider = GetProviderPointer<CCCM>(*(_QWORD *)&this[1].guidPropertySet.Data4[4], &IID_ICommandProperties);
          v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, const struct tagDBPROPIDSET *const, unsigned int *, struct tagDBPROPSET **))(*(_QWORD *)Provider + 24LL))(
                  Provider,
                  HIDWORD(v43),
                  a3,
                  a4,
                  a5);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)Provider + 16LL))(Provider);
        }
        goto LABEL_85;
      }
      ++v13;
    }
    if ( !*(_BYTE *)(v9 + 672) )
    {
      v17 = GetProviderPointer<CCCM>(*(_QWORD *)&this[1].guidPropertySet.Data4[4], &IID_ICommandProperties);
      LODWORD(v43) = 0;
      v46 = 0;
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD, __int64 *, struct tagDBPROPSET **))(*(_QWORD *)v17 + 24LL))(
        v17,
        0,
        0,
        &v43,
        &v46);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      CDBPROPContainer::AddNewPropSets((CDBPROPContainer *)(v9 + 576), v43, v46, 0, 0);
      CDBPROPContainer::AddNewPropSets((CDBPROPContainer *)(v9 + 680), v43, v46, 0, 0);
      FreePropSets(v43, v46);
      CSupportedPropDispenser::GetAllSupportedFoxProps(
        (CSupportedPropDispenser *)(v9 + 328),
        (unsigned int *)&v43,
        (const struct tagDBPROPSET **)&v46);
      CDBPROPContainer::AddNewPropSets((CDBPROPContainer *)(v9 + 576), v43, v46, 0, 0);
      CDBPROPContainer::AddNewPropSets((CDBPROPContainer *)(v9 + 680), v43, v46, 0, 0);
      memset_0(&v60, 0, sizeof(v60));
      v60.dwPropertyID = 260;
      v60.colid = DB_NULLID;
      v60.dwStatus = 0;
      v60.vValue.vt = 11;
      if ( LOBYTE(rgProperties[2].rgProperties) )
      {
        v60.dwOptions = 0;
        v60.vValue.iVal = 0;
      }
      else
      {
        v60.dwOptions = 1;
        v60.vValue.iVal = -1;
      }
      CDBPROPContainer::SetProperty((CDBPROPContainer *)(v9 + 576), &DBPROPSET_ROWSET, &v60, 0, 0);
      CDBPROPContainer::SetProperty((CDBPROPContainer *)(v9 + 680), &DBPROPSET_ROWSET, &v60, 0, 0);
      *(_BYTE *)(v9 + 672) = 1;
    }
    if ( !(_DWORD)v7 )
    {
      v18 = *(_DWORD *)(v9 + 640);
      v19 = *(struct tagDBPROPSET **)(v9 + 632);
      if ( (bidGblFlags & 2) != 0 )
      {
        IMallocCopyOfProps = CreateIMallocCopyOfProps(v18, v19, a4, a5, 0);
        v12 = bidTraceHR(off_1800C84B8[0], 379913, L"<CCommandProperties::GetProperties|Trace|HR> ", IMallocCopyOfProps);
      }
      else
      {
        v12 = CreateIMallocCopyOfProps(v18, v19, a4, a5, 0);
      }
      goto LABEL_85;
    }
    v21 = (struct tagDBPROPSET *)CoTaskMemAlloc(32 * v7);
    *a5 = v21;
    if ( !v21 )
    {
      v22 = -2147024882;
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(-2147024882, L"<CCommandProperties::GetProperties|OLEDB|ERR> ", 0x17Eu);
        if ( (bidGblFlags & 2) != 0 )
          v22 = bidTraceHR(off_1800C84B8[0], 391177, L"<CCommandProperties::GetProperties|Trace|HR> ", 2147942414LL);
      }
      pExceptionObject = v22;
      throw (long *)&pExceptionObject;
    }
    v23 = 0;
    LODWORD(v45) = 0;
    *a4 = v7;
    memset_0(*a5, 0, 32 * v7);
    v24 = *a5;
    v25 = 0;
    v26 = v47;
    while ( 1 )
    {
      v48 = v25;
      v50 = v24;
      if ( v25 >= (unsigned int)v7 )
      {
        if ( (_DWORD)v45 )
          v12 = v23 != 0 ? 265946 : -2147217887;
        else
          v12 = 0;
        goto LABEL_85;
      }
      rgPropertyIDs = (struct tagDBPROPSET *)v26->rgPropertyIDs;
      rgProperties = (struct tagDBPROPSET *)v26->rgPropertyIDs;
      p_guidPropertySet = &v26->guidPropertySet;
      v24->guidPropertySet = v26->guidPropertySet;
      cPropertyIDs = v26->cPropertyIDs;
      if ( (_DWORD)cPropertyIDs )
        break;
      rgProperties = *(struct tagDBPROPSET **)(v9 + 632);
      if ( FindPropSet(&v26->guidPropertySet, *(_DWORD *)(v9 + 640), rgProperties, &rgProperties) != -1 )
      {
        v36 = rgProperties;
        v37 = (struct tagDBPROP *)CoTaskMemAlloc(72LL * rgProperties->cProperties);
        v38 = v50;
        v50->rgProperties = v37;
        if ( !v37 )
        {
          v39 = -2147024882;
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(-2147024882, L"<CCommandProperties::GetProperties|OLEDB|ERR> ", 0x1BAu);
            if ( (bidGblFlags & 2) != 0 )
              v39 = bidTraceHR(off_1800C84B8[0], 452617, L"<CCommandProperties::GetProperties|Trace|HR> ", 2147942414LL);
          }
          v55 = v39;
          throw (long *)&v55;
        }
        v38->cProperties = v36->cProperties;
        rgProperties = (struct tagDBPROPSET *)v36->rgProperties;
        for ( HIDWORD(v45) = 0; HIDWORD(v45) < v36->cProperties; ++v37 )
        {
          VariantInit(&v37->vValue);
          CopyProperty(v37, (const struct tagDBPROP *)rgProperties, 1, 0);
          ++HIDWORD(v45);
          rgProperties = (struct tagDBPROPSET *)((char *)rgProperties + 72);
        }
        ++v23;
        v32 = v47;
        goto LABEL_76;
      }
      LODWORD(v45) = v45 + 1;
      v32 = v47;
LABEL_77:
      v25 = v48 + 1;
      v26 = v32 + 1;
      v47 = v26;
      ++v24;
    }
    if ( !rgPropertyIDs )
    {
      v29 = -2147024809;
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(-2147024809, L"<CCommandProperties::GetProperties|OLEDB|ERR> ", 0x192u);
        if ( (bidGblFlags & 2) != 0 )
          v29 = bidTraceHR(off_1800C84B8[0], 411657, L"<CCommandProperties::GetProperties|Trace|HR> ", 2147942487LL);
      }
      v52 = v29;
      throw (long *)&v52;
    }
    v30 = (struct tagDBPROP *)CoTaskMemAlloc(72 * cPropertyIDs);
    v24->rgProperties = v30;
    if ( !v30 )
    {
      v31 = -2147024882;
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(-2147024882, L"<CCommandProperties::GetProperties|OLEDB|ERR> ", 0x195u);
        if ( (bidGblFlags & 2) != 0 )
          v31 = bidTraceHR(off_1800C84B8[0], 414729, L"<CCommandProperties::GetProperties|Trace|HR> ", 2147942414LL);
      }
      v53 = v31;
      throw (long *)&v53;
    }
    v32 = v47;
    v24->cProperties = v47->cPropertyIDs;
    v33 = 0;
    v34 = rgProperties;
    while ( 1 )
    {
      HIDWORD(v45) = v33;
      if ( v33 >= v32->cPropertyIDs )
        break;
      memset_0(&v61, 0, sizeof(v61));
      VariantInit(&v30->vValue);
      v61.dwPropertyID = (DBPROPID)v34->rgProperties;
      if ( CDBPROPContainer::GetProperty((CDBPROPContainer *)(v9 + 576), p_guidPropertySet, &v61) )
      {
        v35 = CopyProperty(v30, &v61, 1, 0);
        if ( v35 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(v35, L"<CCommandProperties::GetProperties|OLEDB|ERR> ", 0x1AAu);
            if ( (bidGblFlags & 2) != 0 )
            {
              OLEDBTraceErr(v35, L"<CCommandProperties::GetProperties|OLEDB|ERR> ", 0x1AAu);
              if ( (bidGblFlags & 2) != 0 )
                v35 = bidTraceHR(
                        off_1800C84B8[0],
                        436233,
                        L"<CCommandProperties::GetProperties|Trace|HR> ",
                        (unsigned int)v35);
            }
          }
          v54 = v35;
          throw (long *)&v54;
        }
        ++v23;
        v34 = rgProperties;
      }
      else
      {
        v30->dwPropertyID = (DBPROPID)v34->rgProperties;
        v30->dwStatus = 1;
        v30->dwOptions = 0;
        v30->colid = DB_NULLID;
        LODWORD(v45) = v45 + 1;
      }
      v33 = HIDWORD(v45) + 1;
      v34 = (struct tagDBPROPSET *)((char *)v34 + 4);
      rgProperties = v34;
      ++v30;
      v32 = v47;
    }
LABEL_76:
    LODWORD(v7) = HIDWORD(v43);
    v24 = v50;
    goto LABEL_77;
  }
  v12 = -2147024809;
  if ( (bidGblFlags & 2) != 0 )
  {
    OLEDBTraceErr(-2147024809, L"<CCommandProperties::GetProperties|OLEDB|ERR> ", 0x122u);
    if ( (bidGblFlags & 2) != 0 )
      v12 = bidTraceHR(off_1800C84B8[0], 296969, L"<CCommandProperties::GetProperties|Trace|HR> ", 2147942487LL);
  }
LABEL_85:
  LeaveCriticalSection(lpCriticalSection);
  if ( (bidGblFlags & 2) != 0 )
  {
    if ( (v12 & 0x80000000) != 0 )
    {
      if ( off_1800C93D8[0] )
      {
        if ( a4 )
          v10 = *a4;
        bidTraceW(
          off_1800C84B8[0],
          507904,
          off_1800C93D8[0],
          v12,
          v10,
          (_DWORD)a5,
          v41,
          v42,
          v43,
          rgProperties,
          v45,
          (_DWORD)v46,
          v47,
          v48,
          v49,
          (_DWORD)v50);
      }
    }
    else if ( off_1800C93E0[0] )
    {
      bidTraceW(
        off_1800C84B8[0],
        507904,
        off_1800C93E0[0],
        v12,
        *a4,
        *a4,
        a5,
        v42,
        v43,
        rgProperties,
        v45,
        (_DWORD)v46,
        v47,
        v48,
        v49,
        (_DWORD)v50);
    }
    if ( (bidGblFlags & 4) != 0 && v49 != -1 && bidID != -1 )
      ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *))off_1800BC0E8[0])(bidID, 0, 0, &v49);
    if ( (bidGblFlags & 2) != 0 )
      return (unsigned int)bidTraceHR(off_1800C84B8[0], 508937, L"<CCommandProperties::GetProperties|Trace|HR> ", v12);
  }
  return v12;
}

```

## disassembly

```asm
0x180070950  push    rbx
0x180070952  push    rsi
0x180070953  push    rdi
0x180070954  push    r12
0x180070956  push    r13
0x180070958  push    r14
0x18007095a  push    r15
0x18007095c  sub     rsp, 170h
0x180070963  mov     rax, cs:__security_cookie
0x18007096a  xor     rax, rsp
0x18007096d  mov     [rsp+1A8h+var_48], rax
0x180070975  mov     rsi, r9
0x180070978  mov     rbx, r8
0x18007097b  mov     [rsp+1A8h+var_148], rbx
0x180070980  mov     r15d, edx
0x180070983  mov     [rsp+1A8h+var_164], r15d
0x180070988  mov     r12, rcx
0x18007098b  mov     [rsp+1A8h+var_160], rcx
0x180070990  mov     [rsp+1A8h+var_110], r9
0x180070998  mov     r14, [rsp+1A8h+arg_20]
0x1800709a0  mov     [rsp+1A8h+var_108], r14
0x1800709a8  mov     r13, [rcx+38h]
0x1800709ac  mov     [rsp+1A8h+var_138], 0FFFFFFFFFFFFFFFFh
0x1800709b5  xor     edi, edi
0x1800709b7  test    byte ptr cs:_bidGblFlags, 4
0x1800709be  jz      short loc_1800709FF
0x1800709c0  mov     rax, cs:off_1800C9600; "<ICommandProperties::GetProperties|API|"...
0x1800709c7  test    rax, rax
0x1800709ca  jz      short loc_1800709FF
0x1800709cc  mov     rcx, r13; this
0x1800709cf  call    ?GetBidID@CCCM@@QEAAHXZ; CCCM::GetBidID(void)
0x1800709d4  mov     rdx, cs:off_1800C9600; "<ICommandProperties::GetProperties|API|"...
0x1800709db  mov     [rsp+1A8h+var_170], r14
0x1800709e0  mov     [rsp+1A8h+var_178], rsi
0x1800709e5  mov     [rsp+1A8h+var_180], rbx
0x1800709ea  mov     dword ptr [rsp+1A8h+var_188], r15d
0x1800709ef  mov     r9d, r15d
0x1800709f2  mov     r8d, eax
0x1800709f5  lea     rcx, [rsp+1A8h+var_138]
0x1800709fa  call    _bidScopeEnterW
0x1800709ff  lea     rax, [r13+18h]
0x180070a03  mov     [rsp+1A8h+lpCriticalSection], rax
0x180070a0b  mov     rcx, rax; lpCriticalSection
0x180070a0e  call    cs:__imp_EnterCriticalSection
0x180070a14  nop
0x180070a15  test    rsi, rsi
0x180070a18  jz      short loc_180070A1C
0x180070a1a  mov     [rsi], edi
0x180070a1c  test    r14, r14
0x180070a1f  jz      short loc_180070A24
0x180070a21  mov     [r14], rdi
0x180070a24  test    rsi, rsi
0x180070a27  jz      loc_1800711E4
0x180070a2d  test    r14, r14
0x180070a30  jz      loc_1800711E4
0x180070a36  test    r15d, r15d
0x180070a39  jz      short loc_180070A93
0x180070a3b  test    rbx, rbx
0x180070a3e  jnz     short loc_180070A93
0x180070a40  mov     eax, cs:_bidGblFlags
0x180070a46  mov     ebx, 80070057h
0x180070a4b  test    al, 2
0x180070a4d  jz      short loc_180070A8A
0x180070a4f  mov     r8d, 123h; unsigned int
0x180070a55  lea     rdx, aCcommandproper_1; "<CCommandProperties::GetProperties|OLED"...
0x180070a5c  mov     ecx, ebx; int
0x180070a5e  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180070a63  mov     eax, cs:_bidGblFlags
0x180070a69  test    al, 2
0x180070a6b  jz      short loc_180070A8A
0x180070a6d  mov     r9d, ebx
0x180070a70  lea     r8, aCcommandproper_5; "<CCommandProperties::GetProperties|Trac"...
0x180070a77  mov     edx, 48C09h
0x180070a7c  mov     rcx, cs:off_1800C84B8; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180070a83  call    _bidTraceHR
0x180070a88  mov     ebx, eax
0x180070a8a  or      r15, 0FFFFFFFFFFFFFFFFh
0x180070a8e  jmp     loc_180071250
0x180070a93  mov     rax, rbx
0x180070a96  mov     edx, edi
0x180070a98  cmp     edx, r15d
0x180070a9b  jnb     loc_180070B5C
0x180070aa1  mov     rcx, [rax+0Ch]
0x180070aa5  sub     rcx, qword ptr cs:DBPROPSET_PROPERTIESINERROR.Data1
0x180070aac  jnz     short loc_180070AB9
0x180070aae  mov     rcx, [rax+14h]
0x180070ab2  sub     rcx, qword ptr cs:DBPROPSET_PROPERTIESINERROR.Data4
0x180070ab9  test    rcx, rcx
0x180070abc  jz      short loc_180070AC6
0x180070abe  inc     edx
0x180070ac0  add     rax, 20h ; ' '
0x180070ac4  jmp     short loc_180070A98
0x180070ac6  cmp     r15d, 1
0x180070aca  ja      short loc_180070B23
0x180070acc  cmp     [rax+8], edi
0x180070acf  jnz     short loc_180070B23
0x180070ad1  cmp     [rax], rdi
0x180070ad4  jnz     short loc_180070B23
0x180070ad6  lea     rdx, IID_ICommandProperties
0x180070add  mov     rcx, [r12+38h]
0x180070ae2  call    ??$GetProviderPointer@VCCCM@@@@YAPEAXPEAV?$CComObject@VCCCM@@@ATL@@AEBU_GUID@@@Z; GetProviderPointer<CCCM>(ATL::CComObject<CCCM> *,_GUID const &)
0x180070ae7  mov     r15, rax
0x180070aea  mov     rcx, [rax]
0x180070aed  mov     rax, [rcx+18h]
0x180070af1  mov     qword ptr [rsp+1A8h+var_188], r14
0x180070af6  mov     r9, rsi
0x180070af9  mov     r8, rbx
0x180070afc  mov     edx, [rsp+1A8h+var_164]
0x180070b00  mov     rcx, r15
0x180070b03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070b08  mov     ebx, eax
0x180070b0a  mov     rax, [r15]
0x180070b0d  mov     rcx, r15
0x180070b10  mov     rax, [rax+10h]
0x180070b14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070b19  nop
0x180070b1a  or      r15, 0FFFFFFFFFFFFFFFFh
0x180070b1e  jmp     loc_180071250
0x180070b23  test    byte ptr cs:_bidGblFlags, 2
0x180070b2a  jz      short loc_180070B4E
0x180070b2c  mov     r9d, 80070057h
0x180070b32  lea     r8, aCcommandproper_5; "<CCommandProperties::GetProperties|Trac"...
0x180070b39  mov     edx, 4D409h
0x180070b3e  mov     rcx, cs:off_1800C84B8; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180070b45  call    _bidTraceHR
0x180070b4a  mov     ebx, eax
0x180070b4c  jmp     short loc_180070B53
0x180070b4e  mov     ebx, 80070057h
0x180070b53  or      r15, 0FFFFFFFFFFFFFFFFh
0x180070b57  jmp     loc_180071250
0x180070b5c  cmp     [r13+2A0h], dil
0x180070b63  jnz     loc_180070D17
0x180070b69  lea     rdx, IID_ICommandProperties
0x180070b70  mov     rcx, [r12+38h]
0x180070b75  call    ??$GetProviderPointer@VCCCM@@@@YAPEAXPEAV?$CComObject@VCCCM@@@ATL@@AEBU_GUID@@@Z; GetProviderPointer<CCCM>(ATL::CComObject<CCCM> *,_GUID const &)
0x180070b7a  mov     rbx, rax
0x180070b7d  mov     [rsp+1A8h+var_168], edi
0x180070b81  mov     [rsp+1A8h+var_150], rdi
0x180070b86  mov     rcx, [rax]
0x180070b89  mov     rax, [rcx+18h]
0x180070b8d  lea     rcx, [rsp+1A8h+var_150]
0x180070b92  mov     qword ptr [rsp+1A8h+var_188], rcx
0x180070b97  lea     r9, [rsp+1A8h+var_168]
0x180070b9c  xor     r8d, r8d
0x180070b9f  xor     edx, edx
0x180070ba1  mov     rcx, rbx
0x180070ba4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070ba9  mov     rax, [rbx]
0x180070bac  mov     rcx, rbx
0x180070baf  mov     rax, [rax+10h]
0x180070bb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070bb8  lea     rbx, [r13+240h]
0x180070bbf  mov     [rsp+1A8h+var_188], dil; bool
0x180070bc4  xor     r9d, r9d; bool
0x180070bc7  mov     r8, [rsp+1A8h+var_150]; struct tagDBPROPSET *
0x180070bcc  mov     edx, [rsp+1A8h+var_168]; unsigned int
0x180070bd0  mov     rcx, rbx; this
0x180070bd3  call    ?AddNewPropSets@CDBPROPContainer@@QEAAJKPEAUtagDBPROPSET@@_N1@Z; CDBPROPContainer::AddNewPropSets(ulong,tagDBPROPSET *,bool,bool)
0x180070bd8  lea     r12, [r13+2A8h]
0x180070bdf  mov     [rsp+1A8h+var_188], dil; bool
0x180070be4  xor     r9d, r9d; bool
0x180070be7  mov     r8, [rsp+1A8h+var_150]; struct tagDBPROPSET *
0x180070bec  mov     edx, [rsp+1A8h+var_168]; unsigned int
0x180070bf0  mov     rcx, r12; this
0x180070bf3  call    ?AddNewPropSets@CDBPROPContainer@@QEAAJKPEAUtagDBPROPSET@@_N1@Z; CDBPROPContainer::AddNewPropSets(ulong,tagDBPROPSET *,bool,bool)
0x180070bf8  mov     rdx, [rsp+1A8h+var_150]; struct tagDBPROPSET *
0x180070bfd  mov     ecx, [rsp+1A8h+var_168]; unsigned int
0x180070c01  call    ?FreePropSets@@YAXKPEAUtagDBPROPSET@@@Z; FreePropSets(ulong,tagDBPROPSET *)
0x180070c06  lea     rcx, [r13+148h]; this
0x180070c0d  lea     r8, [rsp+1A8h+var_150]; struct tagDBPROPSET **
0x180070c12  lea     rdx, [rsp+1A8h+var_168]; unsigned int *
0x180070c17  call    ?GetAllSupportedFoxProps@CSupportedPropDispenser@@QEAA_NPEAKPEAPEBUtagDBPROPSET@@@Z; CSupportedPropDispenser::GetAllSupportedFoxProps(ulong *,tagDBPROPSET const * *)
0x180070c1c  mov     [rsp+1A8h+var_188], dil; bool
0x180070c21  xor     r9d, r9d; bool
0x180070c24  mov     r8, [rsp+1A8h+var_150]; struct tagDBPROPSET *
0x180070c29  mov     edx, [rsp+1A8h+var_168]; unsigned int
0x180070c2d  mov     rcx, rbx; this
0x180070c30  call    ?AddNewPropSets@CDBPROPContainer@@QEAAJKPEAUtagDBPROPSET@@_N1@Z; CDBPROPContainer::AddNewPropSets(ulong,tagDBPROPSET *,bool,bool)
0x180070c35  mov     [rsp+1A8h+var_188], dil; bool
0x180070c3a  xor     r9d, r9d; bool
0x180070c3d  mov     r8, [rsp+1A8h+var_150]; struct tagDBPROPSET *
0x180070c42  mov     edx, [rsp+1A8h+var_168]; unsigned int
0x180070c46  mov     rcx, r12; this
0x180070c49  call    ?AddNewPropSets@CDBPROPContainer@@QEAAJKPEAUtagDBPROPSET@@_N1@Z; CDBPROPContainer::AddNewPropSets(ulong,tagDBPROPSET *,bool,bool)
0x180070c4e  xor     edx, edx; Val
0x180070c50  lea     r8d, [rdx+48h]; Size
0x180070c54  lea     rcx, [rsp+1A8h+var_E8]; void *
0x180070c5c  call    memset_0
0x180070c61  mov     [rsp+1A8h+var_E8.dwPropertyID], 104h
0x180070c6c  movups  xmm0, xmmword ptr cs:DB_NULLID.uGuid
0x180070c73  movaps  xmmword ptr [rsp+1A8h+var_E8.colid.uGuid], xmm0
0x180070c7b  movups  xmm1, xmmword ptr cs:DB_NULLID.eKind
0x180070c82  movaps  xmmword ptr [rsp+1A8h+var_E8.colid.eKind], xmm1
0x180070c8a  mov     [rsp+1A8h+var_E8.dwStatus], edi
0x180070c91  mov     eax, 0Bh
0x180070c96  mov     word ptr [rsp+1A8h+var_E8.vValue], ax
0x180070c9e  mov     rax, [rsp+1A8h+var_160]
0x180070ca3  cmp     [rax+40h], dil
0x180070ca7  jz      short loc_180070CBA
0x180070ca9  mov     [rsp+1A8h+var_E8.dwOptions], edi
0x180070cb0  mov     word ptr [rsp+1A8h+var_E8.vValue+8], di
0x180070cb8  jmp     short loc_180070CD1
0x180070cba  mov     [rsp+1A8h+var_E8.dwOptions], 1
0x180070cc5  or      rax, 0FFFFFFFFFFFFFFFFh
0x180070cc9  mov     word ptr [rsp+1A8h+var_E8.vValue+8], ax
0x180070cd1  mov     [rsp+1A8h+var_188], dil; bool
0x180070cd6  xor     r9d, r9d; bool
0x180070cd9  lea     r8, [rsp+1A8h+var_E8]; struct tagDBPROP *
0x180070ce1  lea     rdx, DBPROPSET_ROWSET; struct _GUID *
0x180070ce8  mov     rcx, rbx; this
0x180070ceb  call    ?SetProperty@CDBPROPContainer@@QEAAHAEBU_GUID@@AEAUtagDBPROP@@_N2@Z; CDBPROPContainer::SetProperty(_GUID const &,tagDBPROP &,bool,bool)
0x180070cf0  mov     [rsp+1A8h+var_188], dil; bool
0x180070cf5  xor     r9d, r9d; bool
0x180070cf8  lea     r8, [rsp+1A8h+var_E8]; struct tagDBPROP *
0x180070d00  lea     rdx, DBPROPSET_ROWSET; struct _GUID *
0x180070d07  mov     rcx, r12; this
0x180070d0a  call    ?SetProperty@CDBPROPContainer@@QEAAHAEBU_GUID@@AEAUtagDBPROP@@_N2@Z; CDBPROPContainer::SetProperty(_GUID const &,tagDBPROP &,bool,bool)
0x180070d0f  mov     byte ptr [r13+2A0h], 1
0x180070d17  test    r15d, r15d
0x180070d1a  jnz     short loc_180070D72
0x180070d1c  mov     ecx, [r13+280h]; unsigned int
0x180070d23  mov     rdx, [r13+278h]; struct tagDBPROPSET *
0x180070d2a  mov     [rsp+1A8h+var_188], dil; bool
0x180070d2f  mov     r9, r14; struct tagDBPROPSET **
0x180070d32  mov     r8, rsi; unsigned int *
0x180070d35  test    byte ptr cs:_bidGblFlags, 2
0x180070d3c  jz      short loc_180070D62
0x180070d3e  call    ?CreateIMallocCopyOfProps@@YAJKPEAUtagDBPROPSET@@PEAKPEAPEAU1@_N@Z; CreateIMallocCopyOfProps(ulong,tagDBPROPSET *,ulong *,tagDBPROPSET * *,bool)
0x180070d43  mov     rcx, cs:off_1800C84B8; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180070d4a  mov     r9d, eax
0x180070d4d  lea     r8, aCcommandproper_5; "<CCommandProperties::GetProperties|Trac"...
0x180070d54  mov     edx, 5CC09h
0x180070d59  call    _bidTraceHR
0x180070d5e  mov     ebx, eax
0x180070d60  jmp     short loc_180070D69
0x180070d62  call    ?CreateIMallocCopyOfProps@@YAJKPEAUtagDBPROPSET@@PEAKPEAPEAU1@_N@Z; CreateIMallocCopyOfProps(ulong,tagDBPROPSET *,ulong *,tagDBPROPSET * *,bool)
0x180070d67  mov     ebx, eax
0x180070d69  or      r15, 0FFFFFFFFFFFFFFFFh
0x180070d6d  jmp     loc_180071250
0x180070d72  mov     rbx, r15
0x180070d75  shl     rbx, 5
0x180070d79  mov     rcx, rbx; cb
0x180070d7c  call    cs:__imp_CoTaskMemAlloc
0x180070d82  mov     [r14], rax
0x180070d85  test    rax, rax
0x180070d88  jnz     short loc_180070DEF
0x180070d8a  mov     eax, cs:_bidGblFlags
0x180070d90  mov     ebx, 8007000Eh
0x180070d95  test    al, 2
0x180070d97  jz      short loc_180070DD4
0x180070d99  mov     r8d, 17Eh; unsigned int
0x180070d9f  lea     rdx, aCcommandproper_1; "<CCommandProperties::GetProperties|OLED"...
0x180070da6  mov     ecx, ebx; int
0x180070da8  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180070dad  mov     eax, cs:_bidGblFlags
0x180070db3  test    al, 2
0x180070db5  jz      short loc_180070DD4
0x180070db7  mov     r9d, ebx
0x180070dba  lea     r8, aCcommandproper_5; "<CCommandProperties::GetProperties|Trac"...
0x180070dc1  mov     edx, 5F809h
0x180070dc6  mov     rcx, cs:off_1800C84B8; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180070dcd  call    _bidTraceHR
0x180070dd2  mov     ebx, eax
0x180070dd4  mov     [rsp+1A8h+pExceptionObject], ebx
0x180070ddb  lea     rdx, _TI1J; pThrowInfo
0x180070de2  lea     rcx, [rsp+1A8h+pExceptionObject]; pExceptionObject
0x180070dea  call    _CxxThrowException_0
0x180070def  mov     r12d, edi
0x180070df2  mov     [rsp+1A8h+var_158], edi
0x180070df6  mov     [rsi], r15d
0x180070df9  mov     r8, rbx; Size
0x180070dfc  xor     edx, edx; Val
0x180070dfe  mov     rcx, [r14]; void *
0x180070e01  call    memset_0
0x180070e06  mov     rbx, [r14]
0x180070e09  mov     eax, edi
0x180070e0b  mov     rcx, [rsp+1A8h+var_148]
0x180070e10  mov     [rsp+1A8h+var_140], eax
0x180070e14  mov     [rsp+1A8h+var_130], rbx
0x180070e19  cmp     eax, r15d
0x180070e1c  jnb     loc_1800711C2
0x180070e22  mov     rax, [rcx]
0x180070e25  mov     [rsp+1A8h+var_160], rax
0x180070e2a  lea     r10, [rcx+0Ch]
0x180070e2e  mov     [rsp+1A8h+var_100], r10
0x180070e36  movups  xmm0, xmmword ptr [r10]
0x180070e3a  movdqu  xmmword ptr [rbx+0Ch], xmm0
0x180070e3f  mov     edx, [rcx+8]
0x180070e42  test    edx, edx
0x180070e44  jz      loc_180071088
0x180070e4a  test    rax, rax
0x180070e4d  jnz     short loc_180070EB4
0x180070e4f  mov     eax, cs:_bidGblFlags
0x180070e55  mov     ebx, 80070057h
0x180070e5a  test    al, 2
0x180070e5c  jz      short loc_180070E99
0x180070e5e  mov     r8d, 192h; unsigned int
0x180070e64  lea     rdx, aCcommandproper_1; "<CCommandProperties::GetProperties|OLED"...
0x180070e6b  mov     ecx, ebx; int
0x180070e6d  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
  ... truncated ...
```
