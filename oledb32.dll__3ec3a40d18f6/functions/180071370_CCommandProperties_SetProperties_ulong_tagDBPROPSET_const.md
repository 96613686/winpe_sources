# CCommandProperties::SetProperties(ulong,tagDBPROPSET * const)

- ea: `0x180071370`
- end: `0x1800719cb`
- name: `?SetProperties@CCommandProperties@@UEAAJKQEAUtagDBPROPSET@@@Z`
- size: `1627`
- prototype: `int(CCommandProperties *__hidden this, unsigned int, struct tagDBPROPSET *const)`
- caller_count: `0`
- callee_count: `17`
- tags: `broker_com_uri`

## callees

- `0x1800130d0`
- `0x180013870`
- `0x180029560`
- `0x180029c30`
- `0x18002b8ac`
- `0x18002bc80`
- `0x18002ec0c`
- `0x18003c270`
- `0x180048870`
- `0x18006ed60`
- `0x180070900`
- `0x180071370`
- `0x1800772d4`
- `0x180077f08`
- `0x18007e6ca`
- `0x18007e700`
- `0x180087010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180071423`
- `KERNEL32!EnterCriticalSection` at `0x180071423`
- `KERNEL32!LeaveCriticalSection` at `0x1800718f5`
- `KERNEL32!LeaveCriticalSection` at `0x1800718f5`

## string_xrefs

- `0x180071495`: `<CCommandProperties::SetProperties|OLEDB|ERR> `
- `0x1800714b4`: `<CCommandProperties::SetProperties|OLEDB|ERR> `
- `0x1800714d0`: `<CCommandProperties::SetProperties|Trace|HR> `
- `0x18007198c`: `<CCommandProperties::SetProperties|Trace|HR> `

## pseudocode

```c
__int64 __fastcall CCommandProperties::SetProperties(
        CCommandProperties *this,
        unsigned int a2,
        struct tagDBPROPSET *const a3)
{
  struct tagDBPROPSET *v3; // r13
  unsigned int v4; // r12d
  __int64 v6; // rsi
  unsigned int BidID; // eax
  unsigned int v8; // edi
  struct tagDBPROPSET *v9; // r8
  unsigned int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rdx
  struct tagDBPROP *rgProperties; // rdi
  const struct _GUID *p_guidPropertySet; // r14
  __int64 v15; // rax
  ULONG i; // r15d
  unsigned int v17; // eax
  CDBPROPContainer *v18; // rcx
  struct tagDBPROP *v19; // r8
  ULONG v20; // r15d
  bool v21; // cf
  unsigned int v22; // edi
  unsigned int v24; // ebx
  bool v25[4]; // [rsp+20h] [rbp-118h]
  struct tagDBPROPSET *v26; // [rsp+28h] [rbp-110h]
  __int64 v27; // [rsp+30h] [rbp-108h]
  int v28; // [rsp+38h] [rbp-100h]
  unsigned int pExceptionObject; // [rsp+48h] [rbp-F0h] BYREF
  unsigned int v31; // [rsp+4Ch] [rbp-ECh] BYREF
  struct tagDBPROPSET *v32; // [rsp+50h] [rbp-E8h]
  __int64 v33; // [rsp+58h] [rbp-E0h]
  __int64 v34; // [rsp+60h] [rbp-D8h] BYREF
  struct tagDBPROPSET *v35; // [rsp+68h] [rbp-D0h] BYREF
  struct tagDBPROPSET *v36; // [rsp+70h] [rbp-C8h]
  unsigned int v37; // [rsp+78h] [rbp-C0h] BYREF
  CCommandProperties *v38; // [rsp+80h] [rbp-B8h]
  __int64 Provider; // [rsp+88h] [rbp-B0h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+90h] [rbp-A8h]
  struct tagDBPROP v41; // [rsp+A0h] [rbp-98h] BYREF

  v3 = a3;
  v4 = a2;
  v38 = this;
  v36 = a3;
  v33 = 0;
  v6 = *((_QWORD *)this + 7);
  memset_0(&v41, 0, sizeof(v41));
  v34 = -1;
  if ( (bidGblFlags & 4) != 0 && off_1800C9608[0] )
  {
    BidID = CCCM::GetBidID((CCCM *)v6);
    v26 = v3;
    *(_DWORD *)v25 = v4;
    bidScopeEnterW(&v34, off_1800C9608[0], BidID, v4);
  }
  lpCriticalSection = (LPCRITICAL_SECTION)(v6 + 24);
  EnterCriticalSection((LPCRITICAL_SECTION)(v6 + 24));
  try
  {
    if ( !v4 )
      goto LABEL_60;
    Provider = GetProviderPointer<CCCM>(*((_QWORD *)this + 7), &IID_ICommandProperties);
    v33 = Provider;
    v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct tagDBPROPSET *))(*(_QWORD *)Provider + 32LL))(
           Provider,
           v4,
           v3);
    if ( (int)(v8 + 0x80000000) >= 0 && v8 != -2147217887 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(v8, L"<CCommandProperties::SetProperties|OLEDB|ERR> ", 0x55u);
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(v8, L"<CCommandProperties::SetProperties|OLEDB|ERR> ", 0x57u);
          if ( (bidGblFlags & 2) != 0 )
            v8 = bidTraceHR(off_1800C84B8[0], 89097, L"<CCommandProperties::SetProperties|Trace|HR> ", v8);
        }
      }
      pExceptionObject = v8;
      throw (long *)&pExceptionObject;
    }
    v27 = 0;
    v9 = v3;
    v32 = v3;
    v10 = 0;
    v28 = 0;
    v11 = *(_QWORD *)DBPROPSET_ROWSET.Data4;
    v12 = *(_QWORD *)&DBPROPSET_ROWSET.Data1;
    while ( v10 < v4 )
    {
      rgProperties = v9->rgProperties;
      p_guidPropertySet = &v9->guidPropertySet;
      v15 = *(_QWORD *)&v9->guidPropertySet.Data1 - v12;
      if ( !v15 )
        v15 = *(_QWORD *)v9->guidPropertySet.Data4 - v11;
      if ( !v15 )
      {
        v35 = 0;
        CSupportedPropDispenser::GetAllSupportedFoxProps(
          (CSupportedPropDispenser *)(v6 + 328),
          &v37,
          (const struct tagDBPROPSET **)&v35);
        for ( i = 0; ; ++i )
        {
          v9 = v32;
          if ( i >= v32->cProperties )
          {
            v11 = *(_QWORD *)DBPROPSET_ROWSET.Data4;
            v12 = *(_QWORD *)&DBPROPSET_ROWSET.Data1;
            goto LABEL_45;
          }
          CDBPROPContainer::SetProperty((CDBPROPContainer *)(v6 + 184), p_guidPropertySet, rgProperties, 1, 0);
          if ( rgProperties->dwStatus )
          {
            if ( FindProperty(v35, rgProperties->dwPropertyID, 0) == -1 && rgProperties->dwPropertyID != 260 )
              goto LABEL_35;
            v17 = ValidatePropertyValue(p_guidPropertySet, rgProperties);
            rgProperties->dwStatus = v17;
            if ( v17 )
              goto LABEL_35;
            if ( rgProperties->dwPropertyID == 260 && *((_BYTE *)v38 + 64) && rgProperties->vValue.iVal )
            {
              rgProperties->dwStatus = 6;
LABEL_35:
              ++HIDWORD(v27);
              goto LABEL_36;
            }
            LODWORD(v27) = v27 + 1;
            if ( rgProperties->vValue.vt )
            {
              CDBPROPContainer::SetProperty((CDBPROPContainer *)(v6 + 576), p_guidPropertySet, rgProperties, 0, 0);
              v18 = (CDBPROPContainer *)(v6 + 480);
              v19 = rgProperties;
LABEL_43:
              CDBPROPContainer::SetProperty(v18, p_guidPropertySet, v19, 0, 0);
              goto LABEL_36;
            }
            v41.dwPropertyID = rgProperties->dwPropertyID;
            if ( CDBPROPContainer::GetProperty(g_pcontAllProps, p_guidPropertySet, &v41) )
            {
              CDBPROPContainer::SetProperty((CDBPROPContainer *)(v6 + 480), p_guidPropertySet, &v41, 0, 0);
              if ( *(_BYTE *)(v6 + 672) )
              {
                if ( CDBPROPContainer::GetProperty((CDBPROPContainer *)(v6 + 680), p_guidPropertySet, &v41) )
                {
                  v18 = (CDBPROPContainer *)(v6 + 576);
                  v19 = &v41;
                  goto LABEL_43;
                }
              }
            }
          }
          else
          {
            if ( rgProperties->vValue.vt )
            {
              CDBPROPContainer::SetProperty((CDBPROPContainer *)(v6 + 576), p_guidPropertySet, rgProperties, 0, 0);
              CDBPROPContainer::SetProperty((CDBPROPContainer *)(v6 + 480), p_guidPropertySet, rgProperties, 0, 0);
            }
            else
            {
              v41.dwPropertyID = rgProperties->dwPropertyID;
              if ( CDBPROPContainer::GetProperty(g_pcontAllProps, p_guidPropertySet, &v41) )
              {
                CDBPROPContainer::SetProperty((CDBPROPContainer *)(v6 + 480), p_guidPropertySet, &v41, 0, 0);
                if ( *(_BYTE *)(v6 + 672) )
                {
                  if ( CDBPROPContainer::GetProperty((CDBPROPContainer *)(v6 + 680), p_guidPropertySet, &v41) )
                    CDBPROPContainer::SetProperty((CDBPROPContainer *)(v6 + 576), p_guidPropertySet, &v41, 0, 0);
                }
              }
            }
            LODWORD(v27) = v27 + 1;
          }
LABEL_36:
          ++rgProperties;
        }
      }
      v20 = 0;
      while ( v20 < v9->cProperties )
      {
        CDBPROPContainer::SetProperty((CDBPROPContainer *)(v6 + 184), p_guidPropertySet, rgProperties, 1, 0);
        if ( rgProperties->dwStatus )
        {
          ++HIDWORD(v27);
        }
        else
        {
          if ( rgProperties->vValue.vt )
          {
            CDBPROPContainer::SetProperty((CDBPROPContainer *)(v6 + 576), p_guidPropertySet, rgProperties, 0, 0);
            CDBPROPContainer::SetProperty((CDBPROPContainer *)(v6 + 480), p_guidPropertySet, rgProperties, 0, 0);
          }
          else
          {
            v41.dwPropertyID = rgProperties->dwPropertyID;
            if ( CDBPROPContainer::GetProperty(g_pcontAllProps, p_guidPropertySet, &v41) )
            {
              CDBPROPContainer::SetProperty((CDBPROPContainer *)(v6 + 480), p_guidPropertySet, &v41, 0, 0);
              if ( *(_BYTE *)(v6 + 672) )
              {
                if ( CDBPROPContainer::GetProperty((CDBPROPContainer *)(v6 + 680), p_guidPropertySet, &v41) )
                  CDBPROPContainer::SetProperty((CDBPROPContainer *)(v6 + 576), p_guidPropertySet, &v41, 0, 0);
              }
            }
          }
          LODWORD(v27) = v27 + 1;
        }
        ++v20;
        ++rgProperties;
        v11 = *(_QWORD *)DBPROPSET_ROWSET.Data4;
        v12 = *(_QWORD *)&DBPROPSET_ROWSET.Data1;
        v9 = v32;
      }
LABEL_45:
      v10 = ++v28;
      v32 = ++v9;
    }
    (*(void (__fastcall **)(__int64, __int64, struct tagDBPROPSET *))(*(_QWORD *)Provider + 16LL))(Provider, v12, v9);
    if ( HIDWORD(v27) )
    {
      v21 = (_DWORD)v27 != 0;
      LODWORD(v27) = -(int)v27;
      v22 = v21 ? 265946 : -2147217887;
    }
    else
    {
LABEL_60:
      v22 = 0;
    }
  }
  catch ( long v31 )
  {
    v24 = v31;
    if ( (bidGblFlags & 2) != 0 )
    {
      OLEDBTraceErr(v31, L"<CCommandProperties::SetProperties|OLEDB|ERR> ", 0xF1u);
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( off_1800C8C60[0] )
          bidTraceA(off_1800C84B8[0], 247808, off_1800C8C60[0], v24);
      }
    }
    if ( v33 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    LODWORD(v27) = v24;
    v3 = v36;
    v4 = a2;
    v22 = v24;
  }
  catch ( ... )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      OLEDBTraceErr(-2147418113, L"<CCommandProperties::SetProperties|OLEDB|ERR> ", 0xF8u);
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( off_1800C8C58[0] )
          bidTraceA(off_1800C84B8[0], 254976, off_1800C8C58[0], 0);
      }
    }
    if ( v33 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    LODWORD(v27) = -2147418113;
    v3 = v36;
    v4 = a2;
    v22 = -2147418113;
  }
  LeaveCriticalSection(lpCriticalSection);
  if ( (bidGblFlags & 0x80u) != 0 )
    BidTraceOLEDBPropertySets(v4, v3);
  if ( (bidGblFlags & 2) != 0 && off_1800C93E8[0] )
    bidTraceW(off_1800C84B8[0], 267264, off_1800C93E8[0], v22, v4, (_DWORD)v3, v27);
  if ( (bidGblFlags & 4) != 0 && v34 != -1 && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *, _DWORD, struct tagDBPROPSET *))off_1800BC0E8[0])(
      bidID,
      0,
      0,
      &v34,
      *(_DWORD *)v25,
      v26);
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned int)bidTraceHR(off_1800C84B8[0], 269321, L"<CCommandProperties::SetProperties|Trace|HR> ", v22);
  return v22;
}

```

## disassembly

```asm
0x180071370  push    rbx
0x180071372  push    rsi
0x180071373  push    rdi
0x180071374  push    r12
0x180071376  push    r13
0x180071378  push    r14
0x18007137a  push    r15
0x18007137c  sub     rsp, 100h
0x180071383  mov     rax, cs:__security_cookie
0x18007138a  xor     rax, rsp
0x18007138d  mov     [rsp+138h+var_48], rax
0x180071395  mov     r13, r8
0x180071398  mov     r12d, edx
0x18007139b  mov     rdi, rcx
0x18007139e  mov     [rsp+138h+var_B8], rcx
0x1800713a6  mov     [rsp+138h+var_F8], edx
0x1800713aa  mov     [rsp+138h+var_C8], r8
0x1800713af  xor     ebx, ebx
0x1800713b1  mov     [rsp+138h+var_E0], rbx
0x1800713b6  mov     rsi, [rcx+38h]
0x1800713ba  xor     edx, edx; Val
0x1800713bc  lea     r8d, [rbx+48h]; Size
0x1800713c0  lea     rcx, [rsp+138h+var_98]; void *
0x1800713c8  call    memset_0
0x1800713cd  mov     [rsp+138h+var_D8], 0FFFFFFFFFFFFFFFFh
0x1800713d6  test    byte ptr cs:_bidGblFlags, 4
0x1800713dd  jz      short loc_180071414
0x1800713df  mov     rax, cs:off_1800C9608; "<ICommandProperties::SetProperties|API|"...
0x1800713e6  test    rax, rax
0x1800713e9  jz      short loc_180071414
0x1800713eb  mov     rcx, rsi; this
0x1800713ee  call    ?GetBidID@CCCM@@QEAAHXZ; CCCM::GetBidID(void)
0x1800713f3  mov     rdx, cs:off_1800C9608; "<ICommandProperties::SetProperties|API|"...
0x1800713fa  mov     [rsp+138h+var_110], r13
0x1800713ff  mov     dword ptr [rsp+138h+var_118], r12d
0x180071404  mov     r9d, r12d
0x180071407  mov     r8d, eax
0x18007140a  lea     rcx, [rsp+138h+var_D8]
0x18007140f  call    _bidScopeEnterW
0x180071414  lea     rax, [rsi+18h]
0x180071418  mov     [rsp+138h+lpCriticalSection], rax
0x180071420  mov     rcx, rax; lpCriticalSection
0x180071423  call    cs:__imp_EnterCriticalSection
0x180071429  nop
0x18007142a  test    r12d, r12d
0x18007142d  jz      loc_1800718D9
0x180071433  lea     rdx, IID_ICommandProperties
0x18007143a  mov     rcx, [rdi+38h]
0x18007143e  call    ??$GetProviderPointer@VCCCM@@@@YAPEAXPEAV?$CComObject@VCCCM@@@ATL@@AEBU_GUID@@@Z; GetProviderPointer<CCCM>(ATL::CComObject<CCCM> *,_GUID const &)
0x180071443  mov     r14, rax
0x180071446  mov     [rsp+138h+var_B0], rax
0x18007144e  mov     [rsp+138h+var_E0], rax
0x180071453  mov     rax, [rax]
0x180071456  mov     r8, r13
0x180071459  mov     edx, r12d
0x18007145c  mov     rcx, r14
0x18007145f  mov     rax, [rax+20h]
0x180071463  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071468  mov     edi, eax
0x18007146a  mov     ecx, 80000000h
0x18007146f  add     eax, ecx
0x180071471  test    ecx, eax
0x180071473  jnz     loc_1800714FF
0x180071479  cmp     edi, 80040E21h
0x18007147f  jz      short loc_1800714FF
0x180071481  mov     eax, cs:_bidGblFlags
0x180071487  mov     sil, 2
0x18007148a  test    sil, al
0x18007148d  jz      short loc_1800714EA
0x18007148f  mov     r8d, 55h ; 'U'; unsigned int
0x180071495  lea     rdx, aCcommandproper_2; "<CCommandProperties::SetProperties|OLED"...
0x18007149c  mov     ecx, edi; int
0x18007149e  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800714a3  mov     eax, cs:_bidGblFlags
0x1800714a9  test    sil, al
0x1800714ac  jz      short loc_1800714EA
0x1800714ae  mov     r8d, 57h ; 'W'; unsigned int
0x1800714b4  lea     rdx, aCcommandproper_2; "<CCommandProperties::SetProperties|OLED"...
0x1800714bb  mov     ecx, edi; int
0x1800714bd  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800714c2  mov     eax, cs:_bidGblFlags
0x1800714c8  test    sil, al
0x1800714cb  jz      short loc_1800714EA
0x1800714cd  mov     r9d, edi
0x1800714d0  lea     r8, aCcommandproper_0; "<CCommandProperties::SetProperties|Trac"...
0x1800714d7  mov     edx, 15C09h
0x1800714dc  mov     rcx, cs:off_1800C84B8; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x1800714e3  call    _bidTraceHR
0x1800714e8  mov     edi, eax
0x1800714ea  mov     [rsp+138h+pExceptionObject], edi
0x1800714ee  lea     rdx, _TI1J; pThrowInfo
0x1800714f5  lea     rcx, [rsp+138h+pExceptionObject]; pExceptionObject
0x1800714fa  call    _CxxThrowException_0
0x1800714ff  mov     [rsp+138h+var_108], ebx
0x180071503  mov     [rsp+138h+var_104], ebx
0x180071507  mov     r8, r13
0x18007150a  mov     [rsp+138h+var_E8], r13
0x18007150f  mov     eax, ebx
0x180071511  mov     [rsp+138h+var_100], ebx
0x180071515  mov     rcx, qword ptr cs:DBPROPSET_ROWSET.Data4
0x18007151c  mov     rdx, qword ptr cs:DBPROPSET_ROWSET.Data1
0x180071523  cmp     eax, r12d
0x180071526  jnb     loc_1800718AB
0x18007152c  mov     rdi, [r8]
0x18007152f  lea     r14, [r8+0Ch]
0x180071533  mov     rax, [r14]
0x180071536  sub     rax, rdx
0x180071539  jnz     short loc_180071542
0x18007153b  mov     rax, [r14+8]
0x18007153f  sub     rax, rcx
0x180071542  test    rax, rax
0x180071545  jnz     loc_18007179A
0x18007154b  mov     [rsp+138h+var_D0], rbx
0x180071550  lea     rcx, [rsi+148h]; this
0x180071557  lea     r8, [rsp+138h+var_D0]; struct tagDBPROPSET **
0x18007155c  lea     rdx, [rsp+138h+var_C0]; unsigned int *
0x180071561  call    ?GetAllSupportedFoxProps@CSupportedPropDispenser@@QEAA_NPEAKPEAPEBUtagDBPROPSET@@@Z; CSupportedPropDispenser::GetAllSupportedFoxProps(ulong *,tagDBPROPSET const * *)
0x180071566  mov     r15d, ebx
0x180071569  mov     r8, [rsp+138h+var_E8]
0x18007156e  cmp     r15d, [r8+8]
0x180071572  jnb     loc_180071774
0x180071578  lea     rcx, [rsi+0B8h]; this
0x18007157f  mov     [rsp+138h+var_118], bl; bool
0x180071583  mov     r9b, 1; bool
0x180071586  mov     r8, rdi; struct tagDBPROP *
0x180071589  mov     rdx, r14; struct _GUID *
0x18007158c  call    ?SetProperty@CDBPROPContainer@@QEAAHAEBU_GUID@@AEAUtagDBPROP@@_N2@Z; CDBPROPContainer::SetProperty(_GUID const &,tagDBPROP &,bool,bool)
0x180071591  cmp     [rdi+8], ebx
0x180071594  jnz     loc_18007165D
0x18007159a  mov     rdx, r14; struct _GUID *
0x18007159d  cmp     [rdi+30h], bx
0x1800715a1  jz      short loc_1800715D7
0x1800715a3  lea     rcx, [rsi+240h]; this
0x1800715aa  mov     [rsp+138h+var_118], bl; bool
0x1800715ae  xor     r9d, r9d; bool
0x1800715b1  mov     r8, rdi; struct tagDBPROP *
0x1800715b4  call    ?SetProperty@CDBPROPContainer@@QEAAHAEBU_GUID@@AEAUtagDBPROP@@_N2@Z; CDBPROPContainer::SetProperty(_GUID const &,tagDBPROP &,bool,bool)
0x1800715b9  lea     rcx, [rsi+1E0h]; this
0x1800715c0  mov     [rsp+138h+var_118], bl; bool
0x1800715c4  xor     r9d, r9d; bool
0x1800715c7  mov     r8, rdi; struct tagDBPROP *
0x1800715ca  mov     rdx, r14; struct _GUID *
0x1800715cd  call    ?SetProperty@CDBPROPContainer@@QEAAHAEBU_GUID@@AEAUtagDBPROP@@_N2@Z; CDBPROPContainer::SetProperty(_GUID const &,tagDBPROP &,bool,bool)
0x1800715d2  jmp     loc_180071657
0x1800715d7  mov     eax, [rdi]
0x1800715d9  mov     [rsp+138h+var_98.dwPropertyID], eax
0x1800715e0  lea     r8, [rsp+138h+var_98]; struct tagDBPROP *
0x1800715e8  mov     rcx, cs:?g_pcontAllProps@@3PEAVCDBPROPContainer@@EA; this
0x1800715ef  call    ?GetProperty@CDBPROPContainer@@QEAA_NAEBU_GUID@@PEAUtagDBPROP@@@Z; CDBPROPContainer::GetProperty(_GUID const &,tagDBPROP *)
0x1800715f4  test    al, al
0x1800715f6  jz      short loc_180071657
0x1800715f8  lea     rcx, [rsi+1E0h]; this
0x1800715ff  mov     [rsp+138h+var_118], bl; bool
0x180071603  xor     r9d, r9d; bool
0x180071606  lea     r8, [rsp+138h+var_98]; struct tagDBPROP *
0x18007160e  mov     rdx, r14; struct _GUID *
0x180071611  call    ?SetProperty@CDBPROPContainer@@QEAAHAEBU_GUID@@AEAUtagDBPROP@@_N2@Z; CDBPROPContainer::SetProperty(_GUID const &,tagDBPROP &,bool,bool)
0x180071616  cmp     [rsi+2A0h], bl
0x18007161c  jz      short loc_180071657
0x18007161e  lea     rcx, [rsi+2A8h]; this
0x180071625  lea     r8, [rsp+138h+var_98]; struct tagDBPROP *
0x18007162d  mov     rdx, r14; struct _GUID *
0x180071630  call    ?GetProperty@CDBPROPContainer@@QEAA_NAEBU_GUID@@PEAUtagDBPROP@@@Z; CDBPROPContainer::GetProperty(_GUID const &,tagDBPROP *)
0x180071635  test    al, al
0x180071637  jz      short loc_180071657
0x180071639  lea     rcx, [rsi+240h]; this
0x180071640  mov     [rsp+138h+var_118], bl; bool
0x180071644  xor     r9d, r9d; bool
0x180071647  lea     r8, [rsp+138h+var_98]; struct tagDBPROP *
0x18007164f  mov     rdx, r14; struct _GUID *
0x180071652  call    ?SetProperty@CDBPROPContainer@@QEAAHAEBU_GUID@@AEAUtagDBPROP@@_N2@Z; CDBPROPContainer::SetProperty(_GUID const &,tagDBPROP &,bool,bool)
0x180071657  inc     [rsp+138h+var_108]
0x18007165b  jmp     short loc_1800716B2
0x18007165d  xor     r8d, r8d; struct tagDBPROP **
0x180071660  mov     edx, [rdi]; unsigned int
0x180071662  mov     rcx, [rsp+138h+var_D0]; struct tagDBPROPSET *
0x180071667  call    ?FindProperty@@YAKPEAUtagDBPROPSET@@KPEAPEAUtagDBPROP@@@Z; FindProperty(tagDBPROPSET *,ulong,tagDBPROP * *)
0x18007166c  cmp     eax, 0FFFFFFFFh
0x18007166f  jnz     short loc_180071679
0x180071671  cmp     dword ptr [rdi], 104h
0x180071677  jnz     short loc_1800716AE
0x180071679  mov     rdx, rdi; struct tagDBPROP *
0x18007167c  mov     rcx, r14; struct _GUID *
0x18007167f  call    ?ValidatePropertyValue@@YAKAEBU_GUID@@AEAUtagDBPROP@@@Z; ValidatePropertyValue(_GUID const &,tagDBPROP &)
0x180071684  mov     [rdi+8], eax
0x180071687  test    eax, eax
0x180071689  jnz     short loc_1800716AE
0x18007168b  mov     eax, [rdi]
0x18007168d  cmp     eax, 104h
0x180071692  jnz     short loc_1800716BE
0x180071694  mov     rcx, [rsp+138h+var_B8]
0x18007169c  cmp     [rcx+40h], bl
0x18007169f  jz      short loc_1800716BE
0x1800716a1  cmp     [rdi+38h], bx
0x1800716a5  jz      short loc_1800716BE
0x1800716a7  mov     dword ptr [rdi+8], 6
0x1800716ae  inc     [rsp+138h+var_104]
0x1800716b2  inc     r15d
0x1800716b5  add     rdi, 48h ; 'H'
0x1800716b9  jmp     loc_180071569
0x1800716be  inc     [rsp+138h+var_108]
0x1800716c2  mov     rdx, r14; struct _GUID *
0x1800716c5  cmp     [rdi+30h], bx
0x1800716c9  jz      short loc_1800716ED
0x1800716cb  lea     rcx, [rsi+240h]; this
0x1800716d2  mov     [rsp+138h+var_118], bl; bool
0x1800716d6  xor     r9d, r9d; bool
0x1800716d9  mov     r8, rdi; struct tagDBPROP *
0x1800716dc  call    ?SetProperty@CDBPROPContainer@@QEAAHAEBU_GUID@@AEAUtagDBPROP@@_N2@Z; CDBPROPContainer::SetProperty(_GUID const &,tagDBPROP &,bool,bool)
0x1800716e1  lea     rcx, [rsi+1E0h]
0x1800716e8  mov     r8, rdi
0x1800716eb  jmp     short loc_180071760
0x1800716ed  mov     [rsp+138h+var_98.dwPropertyID], eax
0x1800716f4  lea     r8, [rsp+138h+var_98]; struct tagDBPROP *
0x1800716fc  mov     rcx, cs:?g_pcontAllProps@@3PEAVCDBPROPContainer@@EA; this
0x180071703  call    ?GetProperty@CDBPROPContainer@@QEAA_NAEBU_GUID@@PEAUtagDBPROP@@@Z; CDBPROPContainer::GetProperty(_GUID const &,tagDBPROP *)
0x180071708  test    al, al
0x18007170a  jz      short loc_1800716B2
0x18007170c  lea     rcx, [rsi+1E0h]; this
0x180071713  mov     [rsp+138h+var_118], bl; bool
0x180071717  xor     r9d, r9d; bool
0x18007171a  lea     r8, [rsp+138h+var_98]; struct tagDBPROP *
0x180071722  mov     rdx, r14; struct _GUID *
0x180071725  call    ?SetProperty@CDBPROPContainer@@QEAAHAEBU_GUID@@AEAUtagDBPROP@@_N2@Z; CDBPROPContainer::SetProperty(_GUID const &,tagDBPROP &,bool,bool)
0x18007172a  cmp     [rsi+2A0h], bl
0x180071730  jz      short loc_1800716B2
0x180071732  lea     rcx, [rsi+2A8h]; this
0x180071739  lea     r8, [rsp+138h+var_98]; struct tagDBPROP *
0x180071741  mov     rdx, r14; struct _GUID *
0x180071744  call    ?GetProperty@CDBPROPContainer@@QEAA_NAEBU_GUID@@PEAUtagDBPROP@@@Z; CDBPROPContainer::GetProperty(_GUID const &,tagDBPROP *)
0x180071749  test    al, al
0x18007174b  jz      loc_1800716B2
0x180071751  lea     rcx, [rsi+240h]; this
0x180071758  lea     r8, [rsp+138h+var_98]; struct tagDBPROP *
0x180071760  xor     r9d, r9d; bool
0x180071763  mov     [rsp+138h+var_118], bl; bool
0x180071767  mov     rdx, r14; struct _GUID *
0x18007176a  call    ?SetProperty@CDBPROPContainer@@QEAAHAEBU_GUID@@AEAUtagDBPROP@@_N2@Z; CDBPROPContainer::SetProperty(_GUID const &,tagDBPROP &,bool,bool)
0x18007176f  jmp     loc_1800716B2
0x180071774  mov     rcx, qword ptr cs:DBPROPSET_ROWSET.Data4
0x18007177b  mov     rdx, qword ptr cs:DBPROPSET_ROWSET.Data1
0x180071782  mov     eax, [rsp+138h+var_100]
0x180071786  inc     eax
0x180071788  mov     [rsp+138h+var_100], eax
0x18007178c  add     r8, 20h ; ' '
0x180071790  mov     [rsp+138h+var_E8], r8
0x180071795  jmp     loc_180071523
0x18007179a  mov     r15d, ebx
0x18007179d  cmp     r15d, [r8+8]
0x1800717a1  jnb     short loc_180071782
0x1800717a3  lea     rcx, [rsi+0B8h]; this
0x1800717aa  mov     [rsp+138h+var_118], bl; bool
0x1800717ae  mov     r9b, 1; bool
0x1800717b1  mov     r8, rdi; struct tagDBPROP *
0x1800717b4  mov     rdx, r14; struct _GUID *
0x1800717b7  call    ?SetProperty@CDBPROPContainer@@QEAAHAEBU_GUID@@AEAUtagDBPROP@@_N2@Z; CDBPROPContainer::SetProperty(_GUID const &,tagDBPROP &,bool,bool)
0x1800717bc  cmp     [rdi+8], ebx
0x1800717bf  jnz     loc_180071888
0x1800717c5  mov     rdx, r14; struct _GUID *
0x1800717c8  cmp     [rdi+30h], bx
0x1800717cc  jz      short loc_180071802
0x1800717ce  lea     rcx, [rsi+240h]; this
0x1800717d5  mov     [rsp+138h+var_118], bl; bool
0x1800717d9  xor     r9d, r9d; bool
0x1800717dc  mov     r8, rdi; struct tagDBPROP *
0x1800717df  call    ?SetProperty@CDBPROPContainer@@QEAAHAEBU_GUID@@AEAUtagDBPROP@@_N2@Z; CDBPROPContainer::SetProperty(_GUID const &,tagDBPROP &,bool,bool)
0x1800717e4  lea     rcx, [rsi+1E0h]; this
0x1800717eb  mov     [rsp+138h+var_118], bl; bool
0x1800717ef  xor     r9d, r9d; bool
0x1800717f2  mov     r8, rdi; struct tagDBPROP *
0x1800717f5  mov     rdx, r14; struct _GUID *
0x1800717f8  call    ?SetProperty@CDBPROPContainer@@QEAAHAEBU_GUID@@AEAUtagDBPROP@@_N2@Z; CDBPROPContainer::SetProperty(_GUID const &,tagDBPROP &,bool,bool)
0x1800717fd  jmp     loc_180071882
0x180071802  mov     eax, [rdi]
0x180071804  mov     [rsp+138h+var_98.dwPropertyID], eax
0x18007180b  lea     r8, [rsp+138h+var_98]; struct tagDBPROP *
0x180071813  mov     rcx, cs:?g_pcontAllProps@@3PEAVCDBPROPContainer@@EA; this
0x18007181a  call    ?GetProperty@CDBPROPContainer@@QEAA_NAEBU_GUID@@PEAUtagDBPROP@@@Z; CDBPROPContainer::GetProperty(_GUID const &,tagDBPROP *)
0x18007181f  test    al, al
0x180071821  jz      short loc_180071882
0x180071823  lea     rcx, [rsi+1E0h]; this
0x18007182a  mov     [rsp+138h+var_118], bl; bool
0x18007182e  xor     r9d, r9d; bool
0x180071831  lea     r8, [rsp+138h+var_98]; struct tagDBPROP *
0x180071839  mov     rdx, r14; struct _GUID *
0x18007183c  call    ?SetProperty@CDBPROPContainer@@QEAAHAEBU_GUID@@AEAUtagDBPROP@@_N2@Z; CDBPROPContainer::SetProperty(_GUID const &,tagDBPROP &,bool,bool)
0x180071841  cmp     [rsi+2A0h], bl
0x180071847  jz      short loc_180071882
0x180071849  lea     rcx, [rsi+2A8h]; this
0x180071850  lea     r8, [rsp+138h+var_98]; struct tagDBPROP *
0x180071858  mov     rdx, r14; struct _GUID *
0x18007185b  call    ?GetProperty@CDBPROPContainer@@QEAA_NAEBU_GUID@@PEAUtagDBPROP@@@Z; CDBPROPContainer::GetProperty(_GUID const &,tagDBPROP *)
0x180071860  test    al, al
0x180071862  jz      short loc_180071882
0x180071864  lea     rcx, [rsi+240h]; this
0x18007186b  mov     [rsp+138h+var_118], bl; bool
0x18007186f  xor     r9d, r9d; bool
0x180071872  lea     r8, [rsp+138h+var_98]; struct tagDBPROP *
0x18007187a  mov     rdx, r14; struct _GUID *
0x18007187d  call    ?SetProperty@CDBPROPContainer@@QEAAHAEBU_GUID@@AEAUtagDBPROP@@_N2@Z; CDBPROPContainer::SetProperty(_GUID const &,tagDBPROP &,bool,bool)
  ... truncated ...
```
