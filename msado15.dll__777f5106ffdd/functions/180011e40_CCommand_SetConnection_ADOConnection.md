# CCommand::SetConnection(_ADOConnection *)

- ea: `0x180011e40`
- end: `0x18001281d`
- name: `?SetConnection@CCommand@@QEAAJPEAU_ADOConnection@@@Z`
- size: `2525`
- prototype: `__int64 __fastcall(CCommand *__hidden this, struct _ADOConnection *)`
- caller_count: `4`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180011b60`
- `0x1800337d0`
- `0x180042720`
- `0x18008712c`

## callees

- `0x180001514`
- `0x180011e40`
- `0x180012824`
- `0x1800139d0`
- `0x18001a750`
- `0x18001a820`
- `0x18001cc2c`
- `0x180020fc0`
- `0x180042a04`
- `0x18004f1b0`
- `0x18004f2b0`
- `0x18006a22c`
- `0x1800c8f34`
- `0x1800d0010`

## import_xrefs

- `MSDART!UMSEnterCSWraper` at `0x180011ee6`
- `MSDART!UMSEnterCSWraper` at `0x180011ee6`
- `MSDART!MpHeapAlloc` at `0x180012293`
- `MSDART!MpHeapAlloc` at `0x180012293`
- `MSDART!MpHeapFree` at `0x1800124e1`
- `MSDART!MpHeapFree` at `0x1800124e1`
- `KERNEL32!LeaveCriticalSection` at `0x180012790`
- `KERNEL32!LeaveCriticalSection` at `0x180012790`
- `KERNEL32!TlsSetValue` at `0x180011ecb`
- `KERNEL32!TlsSetValue` at `0x1800127ec`
- `KERNEL32!TlsSetValue` at `0x180011ecb`
- `KERNEL32!TlsSetValue` at `0x1800127ec`
- `KERNEL32!TlsGetValue` at `0x180011e87`
- `KERNEL32!TlsGetValue` at `0x180011e87`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800122da`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800122da`
- `OLEAUT32!__imp_SysStringLen` at `0x1800122c9`
- `OLEAUT32!__imp_SysStringLen` at `0x1800122c9`
- `OLEAUT32!__imp_VariantInit` at `0x180012240`
- `OLEAUT32!__imp_VariantInit` at `0x180012240`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800127b6`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800127b6`

## string_xrefs

- `0x180011f77`: `<CCommand::SetConnection|ADO|ERR> %u#, line %d\n`
- `0x180012002`: `<CCommand::SetConnection|ADO|ERR> %u#, line %d\n`
- `0x1800120a9`: `<CCommand::SetConnection|ADO|ERR> %u#, line %d\n`
- `0x18001212c`: `<CCommand::SetConnection|ADO|ERR> %u#, line %d\n`
- `0x1800121fa`: `<CCommand::SetConnection|ADO|ERR> %u#, line %d\n`
- `0x18001239c`: `<CCommand::SetConnection|ADO|ERR> %u#, line %d\n`
- `0x18001259e`: `<CCommand::SetConnection|ADO|ERR> %u#, line %d\n`
- `0x18001267e`: `<CCommand::SetConnection|ADO|ERR> %u#, line %d\n`
- `0x1800126e9`: `<CCommand::SetConnection|ADO|ERR> %u#, line %d\n`
- `0x18001214a`: `<CCommand::SetConnection|ADO|ERR>  line %d\n`
- `0x1800123b5`: `<CCommand::SetConnection|ADO|ERR>  line %d\n`
- `0x180012707`: `<CCommand::SetConnection|ADO|ERR>  line %d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CCommand::SetConnection(CCommand *this, struct _ADOConnection *a2)
{
  __int64 v4; // rdi
  char *v5; // r14
  OLECHAR *v6; // r12
  _DWORD *Value; // rax
  unsigned int BidObjectID; // eax
  __int64 v9; // r9
  __int64 v10; // rdx
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  __int64 v14; // r13
  __int64 v15; // rdx
  unsigned int v16; // eax
  __int64 v17; // r9
  __int64 v18; // rdx
  CSysString *v19; // rdi
  char v20; // si
  UINT v21; // eax
  char v22; // cl
  char v23; // si
  char v24; // al
  VARTYPE vt; // dx
  unsigned int v26; // eax
  __int64 (__fastcall *v27)(__int64, VARIANTARG *, GUID *, __int64 *); // r10
  LONGLONG v28; // rcx
  union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *llVal; // rax
  CSysString *v30; // rdi
  unsigned int v31; // eax
  int v32; // edi
  unsigned int v33; // eax
  unsigned int v34; // eax
  unsigned int v35; // eax
  __int64 v36; // rcx
  unsigned int v37; // ebx
  __int64 v38; // rcx
  _DWORD *v40; // rax
  IErrorInfo *v41; // rdx
  void **v43; // [rsp+30h] [rbp-79h] BYREF
  char v44; // [rsp+38h] [rbp-71h]
  VARIANTARG pvarg; // [rsp+40h] [rbp-69h] BYREF
  CSysString *v46; // [rsp+58h] [rbp-51h]
  _DWORD *TlsValue; // [rsp+60h] [rbp-49h] BYREF
  int v48; // [rsp+68h] [rbp-41h]
  __int64 v49; // [rsp+70h] [rbp-39h]
  int v50; // [rsp+78h] [rbp-31h]
  __int16 v51; // [rsp+7Ch] [rbp-2Dh]
  char v52; // [rsp+7Eh] [rbp-2Bh]
  char *v53; // [rsp+80h] [rbp-29h]
  int BoundQuery; // [rsp+88h] [rbp-21h]
  int v55; // [rsp+8Ch] [rbp-1Dh]
  __int64 *v56; // [rsp+90h] [rbp-19h]
  __int64 v57; // [rsp+98h] [rbp-11h] BYREF
  VARIANTARG v58; // [rsp+A0h] [rbp-9h] BYREF
  struct CQuery *v59; // [rsp+110h] [rbp+67h] BYREF
  __int64 v60; // [rsp+118h] [rbp+6Fh] BYREF
  __int64 v61; // [rsp+120h] [rbp+77h] BYREF
  __int64 v62; // [rsp+128h] [rbp+7Fh] BYREF

  v4 = *((_QWORD *)this + 14) + 8LL;
  v5 = (char *)this + 32;
  v6 = 0;
  if ( !this )
    v5 = 0;
  v53 = v5;
  v55 = 0;
  Value = TlsGetValue(*((_DWORD *)g_pStaticGlobals + 5));
  TlsValue = Value;
  BoundQuery = 0;
  if ( Value )
  {
    ++Value[2];
  }
  else
  {
    v48 = 1;
    v49 = 0;
    v50 = 0;
    v51 = 0;
    v52 = 0;
    TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), &TlsValue);
    TlsValue = &TlsValue;
  }
  v56 = 0;
  UMSEnterCSWraper(v4);
  v56 = (__int64 *)v4;
  v61 = 0;
  v57 = 0;
  if ( !a2 )
  {
    CCommand::Close(this);
    (*(void (__fastcall **)(char *, char *))(*((_QWORD *)this + 4) + 152LL))((char *)this + 32, v5);
    goto LABEL_108;
  }
  v60 = 0;
  v62 = 0;
  if ( (**(int (__fastcall ***)(struct _ADOConnection *, GUID *, __int64 *))a2)(a2, &IID_IADOSecurity, &v60) < 0
    && (unsigned int)CContext::ArgFailed((CContext *)&TlsValue, 0) )
  {
    if ( (bidGblFlags & 2) == 0 )
    {
LABEL_29:
      ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(&v60);
      goto LABEL_109;
    }
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
      bidTraceW(off_18012A1E0[0], 1094665, L"<CCommand::SetConnection|ADO|ERR> %u#, line %d\n", BidObjectID, 1069);
      goto LABEL_29;
    }
    v9 = 1069;
    v10 = 1094665;
LABEL_28:
    bidTraceW(off_18012A1E0[0], v10, L"<CCommand::SetConnection|ADO|ERR>  line %d\n", v9);
    goto LABEL_29;
  }
  BoundQuery = (**(__int64 (__fastcall ***)(struct _ADOConnection *, GUID *, __int64 *))a2)(a2, &IID_IADOClass, &v62);
  if ( BoundQuery < 0 )
  {
    CContext::PushError((CContext *)&TlsValue);
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_29;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144)) != -1 )
    {
      v11 = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
      bidTraceW(off_18012A1E0[0], 1097737, L"<CCommand::SetConnection|ADO|ERR> %u#, line %d\n", v11, 1072);
      goto LABEL_29;
    }
    v9 = 1072;
    v10 = 1097737;
    goto LABEL_28;
  }
  (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v62 + 24LL))(v62, &v61);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
  if ( *(_BYTE *)(v61 + 1041) )
  {
    LODWORD(v59) = -2146824575;
    CContext::FailedPushWarning((CContext *)&TlsValue, (const int *)&v59);
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_29;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144)) != -1 )
    {
      v12 = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
      bidTraceW(off_18012A1E0[0], 1104905, L"<CCommand::SetConnection|ADO|ERR> %u#, line %d\n", v12, 1079);
      goto LABEL_29;
    }
    v9 = 1079;
    v10 = 1104905;
    goto LABEL_28;
  }
  if ( !*(_QWORD *)(v61 + 976) )
  {
    LODWORD(v59) = -2146824579;
    CContext::FailedDescription((CContext *)&TlsValue, (const int *)&v59, 0x271Fu);
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_29;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144)) != -1 )
    {
      v13 = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
      bidTraceW(off_18012A1E0[0], 1110025, L"<CCommand::SetConnection|ADO|ERR> %u#, line %d\n", v13, 1084);
      goto LABEL_29;
    }
    v9 = 1084;
    v10 = 1110025;
    goto LABEL_28;
  }
  v14 = v61 + 544;
  CCommand::Close(this);
  v15 = v61 + 32;
  if ( !v61 )
    v15 = 0;
  (*(void (__fastcall **)(char *, __int64))(*((_QWORD *)this + 4) + 152LL))((char *)this + 32, v15);
  BoundQuery = CCommand::GetBoundQuery(this, &v59);
  if ( BoundQuery < 0 )
  {
    CContext::PushError((CContext *)&TlsValue);
    if ( (bidGblFlags & 2) == 0 )
    {
LABEL_104:
      ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(&v60);
      v36 = *((_QWORD *)this + 15);
      if ( v36 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 88LL))(v36);
        *((_QWORD *)this + 15) = 0;
      }
      (*(void (__fastcall **)(char *, char *))(*((_QWORD *)this + 4) + 152LL))((char *)this + 32, v5);
      goto LABEL_109;
    }
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144)) != -1 )
    {
      v16 = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
      bidTraceW(off_18012A1E0[0], 1117193, L"<CCommand::SetConnection|ADO|ERR> %u#, line %d\n", v16, 1091);
      goto LABEL_104;
    }
    v17 = 1091;
    v18 = 1117193;
LABEL_103:
    bidTraceW(off_18012A1E0[0], v18, L"<CCommand::SetConnection|ADO|ERR>  line %d\n", v17);
    goto LABEL_104;
  }
  v43 = &CVar::`vftable';
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v46 = 0;
  v44 = 4;
  pvarg.vt = 0;
  pvarg.lVal = 0;
  v19 = (CSysString *)MpHeapAlloc(g_hHeapHandle, 10485760, 16);
  if ( v19 )
  {
    v20 = v44;
    if ( (*((_BYTE *)this + 168) & 4) != 0 )
      v6 = (OLECHAR *)*((_QWORD *)this + 20);
    if ( (v44 & 1) != 0 && v6 )
    {
      v21 = SysStringLen(v6);
      v6 = SysAllocStringLen(v6, v21);
      v22 = v20 | 4;
      v23 = v20 & 0xFB;
      if ( v6 )
        v23 = v22;
    }
    else
    {
      v23 = v44 | 4;
    }
    *(_QWORD *)v19 = v6;
    *((_BYTE *)v19 + 8) = v23;
    v46 = v19;
    if ( (*((_BYTE *)v19 + 8) & 4) != 0 )
    {
      v24 = v44;
      goto LABEL_50;
    }
  }
  else
  {
    v19 = 0;
    v46 = 0;
  }
  v24 = v44 & 0xFB;
  v44 &= ~4u;
LABEL_50:
  vt = 8;
  pvarg.vt = 8;
  if ( (v24 & 4) != 0 )
    goto LABEL_59;
  BoundQuery = -2147024882;
  if ( !(unsigned int)CContext::PushError((CContext *)&TlsValue) || !BoundQuery )
  {
    v19 = v46;
    vt = pvarg.vt;
LABEL_59:
    v27 = *(__int64 (__fastcall **)(__int64, VARIANTARG *, GUID *, __int64 *))(*(_QWORD *)v14 + 256LL);
    if ( (vt & 0xBFFF) == 8 )
    {
      if ( (*((_BYTE *)v19 + 8) & 4) != 0 )
        v28 = *(_QWORD *)v19;
      else
        v28 = 0;
      if ( (vt & 0x4000) != 0 )
        llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)pvarg.llVal;
      else
        llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&pvarg.llVal;
    }
    else
    {
      if ( (vt & 0x2000) == 0 )
        goto LABEL_70;
      v28 = *((_QWORD *)v19 + 2);
      llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&pvarg.llVal;
      if ( (vt & 0x4000) != 0 )
        llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)pvarg.llVal;
    }
    llVal->llVal = v28;
LABEL_70:
    v58 = pvarg;
    BoundQuery = v27(v14, &v58, &IID_IADOCommand, &v57);
    if ( v57 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
      v57 = 0;
    }
    v43 = &CVar::`vftable';
    v44 |= 4u;
    if ( (pvarg.vt & 0xBFFF) == 0 )
      goto LABEL_82;
    if ( (pvarg.vt & 0xBFFF) == 8 )
    {
      v30 = v46;
      if ( v46 )
      {
        CSysString::~CSysString(v46);
        MpHeapFree(g_hHeapHandle, v30);
      }
    }
    else
    {
      if ( (pvarg.vt & 0x2000) == 0 )
        goto LABEL_80;
      if ( v46 )
        (**(void (__fastcall ***)(CSysString *, __int64))v46)(v46, 1);
    }
    v46 = 0;
    pvarg.llVal = 0;
LABEL_80:
    if ( (v44 & 2) != 0 )
      CVar::Empty((CVar *)&v43);
LABEL_82:
    if ( BoundQuery >= 0 )
    {
      BoundQuery = -2146824921;
      CContext::PushError((CContext *)&TlsValue);
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_104;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144)) != -1 )
      {
        v35 = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
        bidTraceW(off_18012A1E0[0], 1149961, L"<CCommand::SetConnection|ADO|ERR> %u#, line %d\n", v35, 1123);
        goto LABEL_104;
      }
      v17 = 1123;
      v18 = 1149961;
      goto LABEL_103;
    }
    if ( BoundQuery != -2146825023 )
    {
      LODWORD(v59) = BoundQuery;
      CContext::FailedPushWarning((CContext *)&TlsValue, (const int *)&v59);
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_104;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144)) != -1 )
      {
        v34 = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
        bidTraceW(off_18012A1E0[0], 1144841, L"<CCommand::SetConnection|ADO|ERR> %u#, line %d\n", v34, 1118);
        goto LABEL_104;
      }
      v17 = 1118;
      v18 = 1144841;
      goto LABEL_103;
    }
    BoundQuery = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v14 + 264LL))(v14, v5);
    if ( BoundQuery < 0 )
    {
      CContext::PushError((CContext *)&TlsValue);
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_104;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144)) != -1 )
      {
        v31 = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
        bidTraceW(off_18012A1E0[0], 1139721, L"<CCommand::SetConnection|ADO|ERR> %u#, line %d\n", v31, 1113);
        goto LABEL_104;
      }
      v17 = 1113;
      v18 = 1139721;
      goto LABEL_103;
    }
    if ( (bidGblFlags & 2) != 0 && off_18012A508[0] )
    {
      v32 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(v61 + 256));
      v33 = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
      bidTraceW(off_18012A1E0[0], 1155072, off_18012A508[0], v33, v32);
    }
    if ( v60 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
LABEL_108:
    *((_DWORD *)this + 83) = 1;
    goto LABEL_109;
  }
  if ( (bidGblFlags & 2) != 0 )
  {
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144)) == -1 )
    {
      bidTraceW(off_18012A1E0[0], 1129481, L"<CCommand::SetConnection|ADO|ERR>  line %d\n", 1103);
    }
    else
    {
      v26 = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
      bidTraceW(off_18012A1E0[0], 1129481, L"<CCommand::SetConnection|ADO|ERR> %u#, line %d\n", v26, 1103);
    }
  }
  v43 = &CVar::`vftable';
  CVar::Clear((CVar *)&v43);
  ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(&v60);
LABEL_109:
  v37 = BoundQuery;
  v38 = *v56;
  --*(_DWORD *)(v38 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v38 + 8));
  if ( TlsValue[2]-- == 1 )
  {
    v40 = TlsValue;
    v41 = (IErrorInfo *)*((_QWORD *)TlsValue + 2);
    if ( v41 )
    {
      SetErrorInfo(0, v41);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)TlsValue + 2) + 16LL))(*((_QWORD *)TlsValue + 2));
      v40 = TlsValue;
    }
    if ( *((_BYTE *)v40 + 30) )
    {
      *((_QWORD *)v40 + 2) = 0;
      TlsValue[6] = 0;
    }
    else
    {
      TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), 0);
    }
  }
  return v37;
}

```

## disassembly

```asm
0x180011e40  push    rbp
0x180011e42  push    rbx
0x180011e43  push    rsi
0x180011e44  push    rdi
0x180011e45  push    r12
0x180011e47  push    r13
0x180011e49  push    r14
0x180011e4b  push    r15
0x180011e4d  lea     rbp, [rsp-1Fh]
0x180011e52  sub     rsp, 0C8h
0x180011e59  mov     rsi, rdx
0x180011e5c  mov     rbx, rcx
0x180011e5f  mov     rdi, [rcx+70h]
0x180011e63  add     rdi, 8
0x180011e67  lea     r14, [rcx+20h]
0x180011e6b  xor     r12d, r12d
0x180011e6e  test    rcx, rcx
0x180011e71  cmovz   r14, r12
0x180011e75  mov     [rbp+57h+var_80], r14
0x180011e79  mov     [rbp+57h+var_74], r12d
0x180011e7d  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x180011e84  mov     ecx, [rcx+14h]; dwTlsIndex
0x180011e87  call    cs:__imp_TlsGetValue
0x180011e8e  nop     dword ptr [rax+rax+00h]
0x180011e93  mov     [rbp+57h+TlsValue], rax
0x180011e97  mov     [rbp+57h+var_78], r12d
0x180011e9b  test    rax, rax
0x180011e9e  jz      short loc_180011EA5
0x180011ea0  inc     dword ptr [rax+8]
0x180011ea3  jmp     short loc_180011EDF
0x180011ea5  mov     [rbp+57h+var_98], 1
0x180011eac  mov     [rbp+57h+var_90], r12
0x180011eb0  mov     [rbp+57h+var_88], r12d
0x180011eb4  mov     [rbp+57h+var_84], r12w
0x180011eb9  mov     [rbp+57h+var_82], r12b
0x180011ebd  lea     rdx, [rbp+57h+TlsValue]; lpTlsValue
0x180011ec1  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x180011ec8  mov     ecx, [rcx+14h]; dwTlsIndex
0x180011ecb  call    cs:__imp_TlsSetValue
0x180011ed2  nop     dword ptr [rax+rax+00h]
0x180011ed7  lea     rax, [rbp+57h+TlsValue]
0x180011edb  mov     [rbp+57h+TlsValue], rax
0x180011edf  mov     [rbp+57h+var_70], r12
0x180011ee3  mov     rcx, rdi
0x180011ee6  call    cs:__imp_UMSEnterCSWraper
0x180011eed  nop     dword ptr [rax+rax+00h]
0x180011ef2  mov     [rbp+57h+var_70], rdi
0x180011ef6  mov     [rbp+57h+arg_10], r12
0x180011efa  mov     [rbp+57h+var_68], r12
0x180011efe  test    rsi, rsi
0x180011f01  jz      loc_180012756
0x180011f07  mov     [rbp+57h+arg_8], r12
0x180011f0b  mov     [rbp+57h+arg_18], r12
0x180011f0f  mov     rax, [rsi]
0x180011f12  lea     r8, [rbp+57h+arg_8]
0x180011f16  lea     rdx, IID_IADOSecurity
0x180011f1d  mov     rcx, rsi
0x180011f20  mov     rax, [rax]
0x180011f23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f28  test    eax, eax
0x180011f2a  jns     short loc_180011F9D
0x180011f2c  xor     edx, edx; int
0x180011f2e  lea     rcx, [rbp+57h+TlsValue]; this
0x180011f32  call    ?ArgFailed@CContext@@QEAAHH@Z; CContext::ArgFailed(int)
0x180011f37  test    eax, eax
0x180011f39  jz      short loc_180011F9D
0x180011f3b  test    byte ptr cs:_bidGblFlags, 2
0x180011f42  jz      loc_18001215E
0x180011f48  lea     rcx, [rbx+90h]; this
0x180011f4f  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180011f54  cmp     eax, 0FFFFFFFFh
0x180011f57  jz      short loc_180011F8D
0x180011f59  lea     rcx, [rbx+90h]; this
0x180011f60  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180011f65  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180011f6c  mov     [rsp+100h+var_E0], 42Dh
0x180011f74  mov     r9d, eax
0x180011f77  lea     r8, aCcommandSetcon_1; "<CCommand::SetConnection|ADO|ERR> %u#, "...
0x180011f7e  mov     edx, 10B409h
0x180011f83  call    _bidTraceW
0x180011f88  jmp     loc_18001215E
0x180011f8d  mov     r9d, 42Dh
0x180011f93  mov     edx, 10B409h
0x180011f98  jmp     loc_18001214A
0x180011f9d  mov     rax, [rsi]
0x180011fa0  lea     r8, [rbp+57h+arg_18]
0x180011fa4  lea     rdx, IID_IADOClass
0x180011fab  mov     rcx, rsi
0x180011fae  mov     rax, [rax]
0x180011fb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011fb6  mov     [rbp+57h+var_78], eax
0x180011fb9  test    eax, eax
0x180011fbb  jns     short loc_180012028
0x180011fbd  lea     rcx, [rbp+57h+TlsValue]; this
0x180011fc1  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x180011fc6  test    byte ptr cs:_bidGblFlags, 2
0x180011fcd  jz      loc_18001215E
0x180011fd3  lea     rcx, [rbx+90h]; this
0x180011fda  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180011fdf  cmp     eax, 0FFFFFFFFh
0x180011fe2  jz      short loc_180012018
0x180011fe4  lea     rcx, [rbx+90h]; this
0x180011feb  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180011ff0  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180011ff7  mov     [rsp+100h+var_E0], 430h
0x180011fff  mov     r9d, eax
0x180012002  lea     r8, aCcommandSetcon_1; "<CCommand::SetConnection|ADO|ERR> %u#, "...
0x180012009  mov     edx, 10C009h
0x18001200e  call    _bidTraceW
0x180012013  jmp     loc_18001215E
0x180012018  mov     r9d, 430h
0x18001201e  mov     edx, 10C009h
0x180012023  jmp     loc_18001214A
0x180012028  mov     rcx, [rbp+57h+arg_18]
0x18001202c  mov     rax, [rcx]
0x18001202f  lea     rdx, [rbp+57h+arg_10]
0x180012033  mov     rax, [rax+18h]
0x180012037  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001203c  mov     rcx, [rbp+57h+arg_18]
0x180012040  mov     rax, [rcx]
0x180012043  mov     rax, [rax+10h]
0x180012047  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001204c  mov     rax, [rbp+57h+arg_10]
0x180012050  cmp     byte ptr [rax+411h], 0
0x180012057  jz      short loc_1800120CC
0x180012059  mov     dword ptr [rbp+57h+arg_0], 800A0E81h
0x180012060  lea     rdx, [rbp+57h+arg_0]; int *
0x180012064  lea     rcx, [rbp+57h+TlsValue]; this
0x180012068  call    ?FailedPushWarning@CContext@@QEAAHAEBJ@Z; CContext::FailedPushWarning(long const &)
0x18001206d  test    byte ptr cs:_bidGblFlags, 2
0x180012074  jz      loc_18001215E
0x18001207a  lea     rcx, [rbx+90h]; this
0x180012081  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180012086  cmp     eax, 0FFFFFFFFh
0x180012089  jz      short loc_1800120BF
0x18001208b  lea     rcx, [rbx+90h]; this
0x180012092  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180012097  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18001209e  mov     [rsp+100h+var_E0], 437h
0x1800120a6  mov     r9d, eax
0x1800120a9  lea     r8, aCcommandSetcon_1; "<CCommand::SetConnection|ADO|ERR> %u#, "...
0x1800120b0  mov     edx, 10DC09h
0x1800120b5  call    _bidTraceW
0x1800120ba  jmp     loc_18001215E
0x1800120bf  mov     r9d, 437h
0x1800120c5  mov     edx, 10DC09h
0x1800120ca  jmp     short loc_18001214A
0x1800120cc  cmp     qword ptr [rax+3D0h], 0
0x1800120d4  jnz     loc_18001216C
0x1800120da  mov     dword ptr [rbp+57h+arg_0], 800A0E7Dh
0x1800120e1  mov     r8d, 271Fh; unsigned int
0x1800120e7  lea     rdx, [rbp+57h+arg_0]; int *
0x1800120eb  lea     rcx, [rbp+57h+TlsValue]; this
0x1800120ef  call    ?FailedDescription@CContext@@QEAAHAEBJK@Z; CContext::FailedDescription(long const &,ulong)
0x1800120f4  test    byte ptr cs:_bidGblFlags, 2
0x1800120fb  jz      short loc_18001215E
0x1800120fd  lea     rcx, [rbx+90h]; this
0x180012104  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180012109  cmp     eax, 0FFFFFFFFh
0x18001210c  jz      short loc_18001213F
0x18001210e  lea     rcx, [rbx+90h]; this
0x180012115  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18001211a  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180012121  mov     [rsp+100h+var_E0], 43Ch
0x180012129  mov     r9d, eax
0x18001212c  lea     r8, aCcommandSetcon_1; "<CCommand::SetConnection|ADO|ERR> %u#, "...
0x180012133  mov     edx, 10F009h
0x180012138  call    _bidTraceW
0x18001213d  jmp     short loc_18001215E
0x18001213f  mov     r9d, 43Ch
0x180012145  mov     edx, 10F009h
0x18001214a  lea     r8, aCcommandSetcon; "<CCommand::SetConnection|ADO|ERR>  line"...
0x180012151  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180012158  call    _bidTraceW
0x18001215d  nop
0x18001215e  lea     rcx, [rbp+57h+arg_8]
0x180012162  call    ??1?$CComPtr@UIDBCreateSession@@@ATL@@QEAA@XZ; ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(void)
0x180012167  jmp     loc_18001277F
0x18001216c  lea     r13, [rax+220h]
0x180012173  mov     rcx, rbx; this
0x180012176  call    ?Close@CCommand@@QEAAJXZ; CCommand::Close(void)
0x18001217b  mov     rax, [rbx+20h]
0x18001217f  mov     r8, [rax+98h]
0x180012186  mov     rax, [rbp+57h+arg_10]
0x18001218a  test    rax, rax
0x18001218d  lea     rdx, [rax+20h]
0x180012191  jnz     short loc_180012196
0x180012193  mov     rdx, r12
0x180012196  lea     rcx, [rbx+20h]
0x18001219a  mov     rax, r8
0x18001219d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800121a2  lea     rdx, [rbp+57h+arg_0]; struct CQuery **
0x1800121a6  mov     rcx, rbx; this
0x1800121a9  call    ?GetBoundQuery@CCommand@@QEAAJPEAPEAVCQuery@@@Z; CCommand::GetBoundQuery(CQuery * *)
0x1800121ae  mov     [rbp+57h+var_78], eax
0x1800121b1  test    eax, eax
0x1800121b3  jns     short loc_180012220
0x1800121b5  lea     rcx, [rbp+57h+TlsValue]; this
0x1800121b9  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x1800121be  test    byte ptr cs:_bidGblFlags, 2
0x1800121c5  jz      loc_18001271B
0x1800121cb  lea     rcx, [rbx+90h]; this
0x1800121d2  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800121d7  cmp     eax, 0FFFFFFFFh
0x1800121da  jz      short loc_180012210
0x1800121dc  lea     rcx, [rbx+90h]; this
0x1800121e3  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800121e8  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800121ef  mov     [rsp+100h+var_E0], 443h
0x1800121f7  mov     r9d, eax
0x1800121fa  lea     r8, aCcommandSetcon_1; "<CCommand::SetConnection|ADO|ERR> %u#, "...
0x180012201  mov     edx, 110C09h
0x180012206  call    _bidTraceW
0x18001220b  jmp     loc_18001271B
0x180012210  mov     r9d, 443h
0x180012216  mov     edx, 110C09h
0x18001221b  jmp     loc_180012707
0x180012220  lea     rax, ??_7CVar@@6B@; const CVar::`vftable'
0x180012227  mov     [rbp+57h+var_D0], rax
0x18001222b  mov     [rbp+57h+var_C8], 4
0x18001222f  xorps   xmm0, xmm0
0x180012232  xor     eax, eax
0x180012234  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180012238  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18001223c  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180012240  call    cs:__imp_VariantInit
0x180012247  nop     dword ptr [rax+rax+00h]
0x18001224c  mov     eax, 0Ah
0x180012251  mov     word ptr [rbp+57h+pvarg], ax
0x180012255  mov     dword ptr [rbp+57h+pvarg+8], 80020004h
0x18001225c  mov     [rbp+57h+var_A8], r12
0x180012260  movzx   eax, [rbp+57h+var_C8]
0x180012264  or      al, 4
0x180012266  mov     [rbp+57h+var_C8], al
0x180012269  test    al, 2
0x18001226b  jz      short loc_180012278
0x18001226d  lea     rcx, [rbp+57h+var_D0]; this
0x180012271  call    ?Empty@CVar@@QEAAXXZ; CVar::Empty(void)
0x180012276  jmp     short loc_180012281
0x180012278  mov     word ptr [rbp+57h+pvarg], r12w
0x18001227d  mov     dword ptr [rbp+57h+pvarg+8], r12d
0x180012281  mov     edx, 0A00000h
0x180012286  mov     r8d, 10h
0x18001228c  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x180012293  call    cs:__imp_MpHeapAlloc
0x18001229a  nop     dword ptr [rax+rax+00h]
0x18001229f  mov     rdi, rax
0x1800122a2  test    rax, rax
0x1800122a5  jz      short loc_180012321
0x1800122a7  movzx   esi, [rbp+57h+var_C8]
0x1800122ab  test    byte ptr [rbx+0A8h], 4
0x1800122b2  jz      short loc_1800122BB
0x1800122b4  mov     r12, [rbx+0A0h]
0x1800122bb  test    sil, 1
0x1800122bf  jz      short loc_180012303
0x1800122c1  test    r12, r12
0x1800122c4  jz      short loc_180012303
0x1800122c6  mov     rcx, r12; pbstr
0x1800122c9  call    cs:__imp_SysStringLen
0x1800122d0  nop     dword ptr [rax+rax+00h]
0x1800122d5  mov     edx, eax; ui
0x1800122d7  mov     rcx, r12; strIn
0x1800122da  call    cs:__imp_SysAllocStringLen
0x1800122e1  nop     dword ptr [rax+rax+00h]
0x1800122e6  mov     r12, rax
0x1800122e9  movzx   ecx, sil
0x1800122ed  or      cl, 4
0x1800122f0  and     sil, 0FBh
0x1800122f4  movzx   esi, sil
0x1800122f8  movzx   ecx, cl
0x1800122fb  test    rax, rax
0x1800122fe  cmovnz  esi, ecx
0x180012301  jmp     short loc_180012307
0x180012303  or      sil, 4
0x180012307  mov     rcx, rdi
0x18001230a  mov     [rcx], r12
0x18001230d  mov     [rdi+8], sil
0x180012311  mov     [rbp+57h+var_A8], rdi
0x180012315  test    byte ptr [rdi+8], 4
0x180012319  jz      short loc_180012328
0x18001231b  movzx   eax, [rbp+57h+var_C8]
0x18001231f  jmp     short loc_180012331
0x180012321  mov     rdi, r12
0x180012324  mov     [rbp+57h+var_A8], r12
0x180012328  movzx   eax, [rbp+57h+var_C8]
0x18001232c  and     al, 0FBh
0x18001232e  mov     [rbp+57h+var_C8], al
0x180012331  mov     edx, 8
0x180012336  mov     word ptr [rbp+57h+pvarg], dx
0x18001233a  test    al, 4
0x18001233c  jnz     loc_1800123FC
0x180012342  mov     [rbp+57h+var_78], 8007000Eh
0x180012349  lea     rcx, [rbp+57h+TlsValue]; this
0x18001234d  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x180012352  test    eax, eax
0x180012354  jz      loc_1800123F4
0x18001235a  cmp     [rbp+57h+var_78], 0
0x18001235e  jz      loc_1800123F4
0x180012364  test    byte ptr cs:_bidGblFlags, 2
0x18001236b  jz      short loc_1800123CE
  ... truncated ...
```
