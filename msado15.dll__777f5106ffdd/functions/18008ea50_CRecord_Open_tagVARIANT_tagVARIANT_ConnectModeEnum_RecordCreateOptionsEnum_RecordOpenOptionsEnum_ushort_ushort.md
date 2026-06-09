# CRecord::Open(tagVARIANT,tagVARIANT,ConnectModeEnum,RecordCreateOptionsEnum,RecordOpenOptionsEnum,ushort *,ushort *)

- ea: `0x18008ea50`
- end: `0x18009057f`
- name: `?Open@CRecord@@UEAAJUtagVARIANT@@0W4ConnectModeEnum@@W4RecordCreateOptionsEnum@@W4RecordOpenOptionsEnum@@PEAG4@Z`
- size: `6959`
- prototype: `__int64 __usercall@<rax>(CRecord *__hidden this@<rcx>, struct tagVARIANT *@<rdx>, struct tagVARIANT *@<r8>, enum ConnectModeEnum@<r9d>, enum RecordCreateOptionsEnum, enum RecordOpenOptionsEnum, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `31`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180090590`

## callees

- `0x18001a750`
- `0x18001a820`
- `0x180020da0`
- `0x180020e20`
- `0x180030ce0`
- `0x180031760`
- `0x180032710`
- `0x1800465a4`
- `0x18004c390`
- `0x18004f1b0`
- `0x18004f370`
- `0x180050b90`
- `0x180057938`
- `0x180059ccc`
- `0x180059d44`
- `0x18006a22c`
- `0x18008298c`
- `0x18008a060`
- `0x18008a800`
- `0x18008b550`
- `0x18008ea50`
- `0x1800907e4`
- `0x180090c6c`
- `0x180090f48`
- `0x1800c8ebc`
- `0x1800c8f34`
- `0x1800cbaf8`
- `0x1800ccb94`
- `0x1800ccd14`
- `0x1800ccd5c`
- `0x1800d0010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800900eb`
- `OLEAUT32!__imp_SysAllocString` at `0x1800900eb`
- `OLEAUT32!__imp_SysFreeString` at `0x18009043e`
- `OLEAUT32!__imp_SysFreeString` at `0x18009043e`
- `OLEAUT32!__imp_VariantInit` at `0x18008eb61`
- `OLEAUT32!__imp_VariantInit` at `0x18008eb61`
- `OLEAUT32!__imp_VariantClear` at `0x180090498`
- `OLEAUT32!__imp_VariantClear` at `0x180090498`

## string_xrefs

- `0x18008ebbc`: `<CRecord::Open|ADO|ERR> %u#, line %d\n`
- `0x18008f643`: `<CRecord::Open|ADO|ERR> %u#, line %d\n`
- `0x18008f6ec`: `<CRecord::Open|ADO|ERR> %u#, line %d\n`
- `0x18008ebdf`: `<CRecord::Open|ADO|ERR>  line %d\n`
- `0x18008f70f`: `<CRecord::Open|ADO|ERR>  line %d\n`
- `0x18008f8a0`: `<CRecord::Open|ADO|ERR>  line %d\n`

## pseudocode

```c
__int64 __fastcall CRecord::Open(
        CRecord *this,
        struct tagVARIANT *a2,
        struct tagVARIANT *a3,
        unsigned int a4,
        enum RecordCreateOptionsEnum a5,
        enum RecordOpenOptionsEnum a6,
        unsigned __int16 *a7,
        unsigned __int16 *a8)
{
  enum RecordOpenOptionsEnum v8; // ebx
  unsigned int BidObjectID; // eax
  __int64 v14; // r8
  const char *v15; // r9
  unsigned int v16; // r13d
  char v17; // bl
  unsigned int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // r9
  __int64 v21; // rdx
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // r9
  __int64 v25; // rdx
  __int64 v26; // r8
  char *v27; // r9
  __int64 v28; // rax
  __int64 v29; // r9
  const struct CVar *v30; // rax
  __int64 v31; // rax
  __int64 v32; // r9
  const struct CVar *v33; // rax
  const struct CVar *v34; // rax
  __int64 *v35; // rax
  __int64 v36; // rcx
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // r9
  __int64 v40; // rdx
  __int64 v41; // r8
  __int64 v42; // r9
  __int64 (__fastcall ***v43)(_QWORD, GUID *, __int64 *); // rax
  __int64 v44; // rdx
  __int64 v45; // r8
  __int64 v46; // r9
  struct IUnknown *v47; // rax
  __int64 v48; // rdx
  __int64 v49; // r9
  char *v50; // r8
  __int64 v51; // rax
  __int64 v52; // r8
  const struct CVar *v53; // rax
  __int64 v54; // rax
  __int64 v55; // r8
  const struct CVar *v56; // rax
  const struct CVar *v57; // rax
  __int64 v58; // r8
  __int64 v59; // r9
  _QWORD *v60; // rsi
  __int64 v61; // rdx
  __int64 v62; // rdx
  __int64 v63; // rcx
  __int64 v64; // r8
  __int64 v65; // r9
  __int64 (__fastcall ***v66)(_QWORD, GUID *, struct IUnknown **); // rax
  unsigned int v67; // eax
  __int64 v68; // rdx
  const struct CVar *v69; // rax
  unsigned int v70; // eax
  __int64 v71; // rdx
  __int64 v72; // r9
  __int64 v73; // rdx
  const struct CSysString *v74; // rax
  const struct CVar *v75; // rax
  __int64 v76; // r9
  __int64 v77; // rdx
  bool v78; // sf
  struct IUnknownVtbl *lpVtbl; // rax
  struct CVar *v80; // rdx
  __int16 v81; // bx
  unsigned __int16 *v82; // r14
  unsigned __int16 *v83; // r12
  _QWORD *v84; // rbx
  int v85; // ebx
  unsigned int v86; // eax
  _QWORD *v87; // rbx
  __int64 *v88; // rax
  __int64 v89; // rdx
  const struct CVar *v90; // rax
  __int64 (__fastcall ***v91)(_QWORD, GUID *, __int64 *); // rax
  BSTR v92; // rbx
  BSTR v93; // rdx
  __int64 v94; // rdx
  unsigned int v95; // r13d
  __int64 v96; // rax
  __int64 (__fastcall ***v97)(_QWORD, GUID *, __int64 *); // rcx
  int v98; // eax
  __int64 v99; // rcx
  int v100; // ebx
  unsigned int v101; // eax
  unsigned int v102; // ebx
  __int64 v104; // [rsp+20h] [rbp-E0h]
  unsigned int v105; // [rsp+28h] [rbp-D8h]
  enum RecordCreateOptionsEnum v106; // [rsp+30h] [rbp-D0h]
  enum RecordOpenOptionsEnum v107; // [rsp+38h] [rbp-C8h]
  struct IUnknown *v108; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v109[40]; // [rsp+48h] [rbp-B8h] BYREF
  int v110; // [rsp+70h] [rbp-90h]
  __int64 v111; // [rsp+80h] [rbp-80h] BYREF
  __int64 v112; // [rsp+88h] [rbp-78h] BYREF
  char v113; // [rsp+90h] [rbp-70h]
  _QWORD *v114; // [rsp+98h] [rbp-68h] BYREF
  struct IUnknown *v115; // [rsp+A0h] [rbp-60h] BYREF
  struct _ADOConnection *v116; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v117; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v118; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v119; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v120; // [rsp+C8h] [rbp-38h] BYREF
  BSTR bstrString; // [rsp+D0h] [rbp-30h]
  VARIANTARG pvarg; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v123[2]; // [rsp+F0h] [rbp-10h] BYREF
  int v124; // [rsp+100h] [rbp+0h]
  _QWORD v125[2]; // [rsp+120h] [rbp+20h] BYREF
  unsigned int v126; // [rsp+130h] [rbp+30h]
  __int64 v127; // [rsp+1A0h] [rbp+A0h] BYREF

  v8 = a6;
  v119 = -1;
  if ( (bidGblFlags & 4) != 0 && off_18012AB20[0] )
  {
    BidObjectID = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
    v107 = v8;
    v106 = a5;
    v105 = a4;
    bidScopeEnterW(&v119, off_18012AB20[0], BidObjectID, a2, (_DWORD)a3);
  }
  memset(&pvarg, 0, sizeof(pvarg));
  CVar::CVar((CVar *)v125, a2, 4u, 1);
  CVar::CVar((CVar *)v123, a3, 4u, 1);
  v14 = *((_QWORD *)this + 18);
  v116 = 0;
  v118 = 0;
  CXLockContext::CXLockContext(
    (CXLockContext *)v109,
    (struct CStdComObjectRoot *)(((unsigned __int64)this + 32)
                               & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)),
    (struct CCriticalSection **)(v14 + 8),
    v15);
  bstrString = 0;
  v16 = 0;
  v117 = 0;
  if ( v8 != adOpenRecordUnspecified )
    v16 = v8;
  v114 = 0;
  v17 = 0;
  v115 = 0;
  LOBYTE(a6) = 0;
  VariantInit(&pvarg);
  if ( (unsigned int)CContext::VariantFailed((CContext *)v109, (const struct CVar *)v125) )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_293;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
    {
      v18 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
      v19 = 926729;
      LODWORD(v104) = 905;
LABEL_10:
      bidTraceW(off_18012A1E8[0], v19, L"<CRecord::Open|ADO|ERR> %u#, line %d\n", v18, v104, v105, v106, v107);
LABEL_13:
      v17 = 0;
      goto LABEL_293;
    }
    v20 = 905;
    v21 = 926729;
    goto LABEL_12;
  }
  if ( !(unsigned int)CContext::VariantFailed((CContext *)v109, (const struct CVar *)v123) )
  {
    if ( *((_QWORD *)this + 34) )
    {
      LODWORD(v127) = -2146824583;
      if ( (unsigned int)CContext::Failed((CContext *)v109, (const int *)&v127) )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
          {
            v18 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
            v19 = 931849;
            LODWORD(v104) = 910;
            goto LABEL_10;
          }
          v20 = 910;
          v21 = 931849;
          goto LABEL_12;
        }
        goto LABEL_293;
      }
    }
    v22 = *((_QWORD *)this + 72);
    if ( v22 )
    {
      if ( *(_BYTE *)(v22 + 544) )
      {
        LODWORD(v127) = -2146824577;
        if ( (unsigned int)CContext::Failed((CContext *)v109, (const int *)&v127) )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
            {
              v18 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
              v19 = 936969;
              LODWORD(v104) = 915;
              goto LABEL_10;
            }
            v20 = 915;
            v21 = 936969;
            goto LABEL_12;
          }
          goto LABEL_293;
        }
      }
    }
    if ( (unsigned int)CVar::Exists((CVar *)v125) )
    {
      if ( (v126 & 0xBFFF) == 8 )
      {
        v34 = (const struct CVar *)CVar::operator=((CRecord *)((char *)this + 216));
        if ( (unsigned int)CContext::VariantFailed((CContext *)v109, v34) )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_13;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
          {
            v18 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
            v19 = 946185;
            LODWORD(v104) = 924;
            goto LABEL_10;
          }
          v20 = 924;
          v21 = 946185;
          goto LABEL_12;
        }
        v35 = (__int64 *)*((_QWORD *)this + 32);
        if ( (v35[1] & 4) != 0 )
          v36 = *v35;
        else
          v36 = 0;
        if ( (unsigned int)CContext::ArgFailed((CContext *)v109, v36 != 0) )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_13;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
          {
            v18 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
            v19 = 947209;
            LODWORD(v104) = 925;
            goto LABEL_10;
          }
          v20 = 925;
          v21 = 947209;
          goto LABEL_12;
        }
      }
      else if ( (v126 & 0xBFFF) == 9 || (v126 & 0xBFFF) == 0xD )
      {
        if ( CVar::operator IUnknown *(v125, v23, v126, v24) )
        {
          LOWORD(v26) = v26 & 0xBFFF;
          v27 = (char *)this + 216;
          if ( (_WORD)v26 == 13 )
          {
            v28 = CVar::operator IUnknown *(v125, v25, v26, v27);
            v30 = (const struct CVar *)CVar::operator=(v29, v28);
            if ( (unsigned int)CContext::VariantFailed((CContext *)v109, v30) )
            {
              if ( (bidGblFlags & 2) == 0 )
                goto LABEL_13;
              if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
              {
                v18 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
                v19 = 954377;
                LODWORD(v104) = 932;
                goto LABEL_10;
              }
              v20 = 932;
              v21 = 954377;
              goto LABEL_12;
            }
          }
          else
          {
            v31 = CVar::operator IUnknown *(v125, v25, v26, v27);
            v33 = (const struct CVar *)CVar::operator=(v32, v31);
            if ( (unsigned int)CContext::VariantFailed((CContext *)v109, v33) )
            {
              if ( (bidGblFlags & 2) == 0 )
                goto LABEL_13;
              if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
              {
                v18 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
                v19 = 956425;
                LODWORD(v104) = 934;
                goto LABEL_10;
              }
              v20 = 934;
              v21 = 956425;
              goto LABEL_12;
            }
          }
        }
        else
        {
          LODWORD(v127) = -2146825287;
          if ( (unsigned int)CContext::Failed((CContext *)v109, (const int *)&v127) )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_13;
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
            {
              v18 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
              v19 = 959497;
              LODWORD(v104) = 937;
              goto LABEL_10;
            }
            v20 = 937;
            v21 = 959497;
            goto LABEL_12;
          }
        }
      }
      else
      {
        LODWORD(v127) = -2146825287;
        if ( (unsigned int)CContext::Failed((CContext *)v109, (const int *)&v127) )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_13;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
          {
            v18 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
            v19 = 962569;
            LODWORD(v104) = 940;
            goto LABEL_10;
          }
          v20 = 940;
          v21 = 962569;
          goto LABEL_12;
        }
      }
    }
    if ( (unsigned int)CVar::Exists((CVar *)v123) )
    {
      if ( (v124 & 0xBFFF) == 8 )
      {
        LODWORD(v127) = CRecord::Disconnect(this);
        if ( (unsigned int)CContext::Failed((CContext *)v109, (const int *)&v127) )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_13;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
          {
            v18 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
            v19 = 973833;
            LODWORD(v104) = 951;
            goto LABEL_10;
          }
          v20 = 951;
          v21 = 973833;
          goto LABEL_12;
        }
        v57 = (const struct CVar *)CVar::operator=((CRecord *)((char *)this + 168));
        if ( (unsigned int)CContext::VariantFailed((CContext *)v109, v57) )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_13;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
          {
            v18 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
            v19 = 974857;
            LODWORD(v104) = 952;
            goto LABEL_10;
          }
          v20 = 952;
          v21 = 974857;
          goto LABEL_12;
        }
      }
      else if ( (v124 & 0xBFFF) == 9 || (v124 & 0xBFFF) == 0xD )
      {
        if ( CVar::operator IUnknown *(v123, v37, v38, v39) )
        {
          v111 = 0;
          v43 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))CVar::operator IUnknown *(v123, v40, v41, v42);
          LODWORD(v127) = (**v43)(v43, &IID_IADOConnection, &v111);
          if ( (unsigned int)CContext::Failed((CContext *)v109, (const int *)&v127) )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_13;
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
            {
              v18 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
              v19 = 982025;
              LODWORD(v104) = 959;
              goto LABEL_10;
            }
            v20 = 959;
            v21 = 982025;
            goto LABEL_12;
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v111 + 16LL))(v111);
          LODWORD(v127) = CRecord::Disconnect(this);
          if ( (unsigned int)CContext::Failed((CContext *)v109, (const int *)&v127) )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_13;
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
            {
              v18 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
              v19 = 984073;
              LODWORD(v104) = 961;
              goto LABEL_10;
            }
            v20 = 961;
            v21 = 984073;
            goto LABEL_12;
          }
          v47 = (struct IUnknown *)CVar::operator IUnknown *(v123, v44, v45, v46);
          LODWORD(v127) = CRecord::Connect(this, v47);
          if ( (unsigned int)CContext::Failed((CContext *)v109, (const int *)&v127) )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_13;
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
            {
              v18 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
              v19 = 985097;
              LODWORD(v104) = 962;
              goto LABEL_10;
            }
            v20 = 962;
            v21 = 985097;
            goto LABEL_12;
          }
          v50 = (char *)this + 168;
          if ( (v124 & 0xBFFF) == 0xD )
          {
            v51 = CVar::operator IUnknown *(v123, v48, v50, v49);
            v53 = (const struct CVar *)CVar::operator=(v52, v51);
            if ( (unsigned int)CContext::VariantFailed((CContext *)v109, v53) )
            {
              if ( (bidGblFlags & 2) == 0 )
                goto LABEL_13;
              if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
              {
                v18 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
                v19 = 987145;
                LODWORD(v104) = 964;
                goto LABEL_10;
              }
              v20 = 964;
              v21 = 987145;
              goto LABEL_12;
            }
          }
          else
          {
            v54 = CVar::operator IUnknown *(v123, v48, v50, v49);
            v56 = (const struct CVar *)CVar::operator=(v55, v54);
            if ( (unsigned int)CContext::VariantFailed((CContext *)v109, v56) )
            {
              if ( (bidGblFlags & 2) == 0 )
                goto LABEL_13;
              if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
              {
                v18 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
                v19 = 989193;
                LODWORD(v104) = 966;
                goto LABEL_10;
              }
              v20 = 966;
              v21 = 989193;
              goto LABEL_12;
            }
          }
        }
        else
        {
          LODWORD(v127) = -2146825287;
          if ( (unsigned int)CContext::Failed((CContext *)v109, (const int *)&v127) )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_13;
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
            {
              v18 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
              v19 = 993289;
              LODWORD(v104) = 970;
              goto LABEL_10;
            }
            v20 = 970;
            v21 = 993289;
            goto LABEL_12;
          }
        }
      }
      else
      {
        LODWORD(v127) = -2146825287;
        if ( (unsigned int)CContext::Failed((CContext *)v109, (const int *)&v127) )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_13;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
          {
            v18 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
            v19 = 997385;
            LODWORD(v104) = 974;
            goto LABEL_10;
          }
          v20 = 974;
          v21 = 997385;
          goto LABEL_12;
        }
      }
    }
    if ( a4 )
    {
      LODWORD(v127) = (*(__int64 (__fastcall **)(CRecord *, _QWORD))(*(_QWORD *)this + 128LL))(this, a4);
      if ( (unsigned int)CContext::Failed((CContext *)v109, (const int *)&v127) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_13;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
        {
          v18 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
          v19 = 1004553;
          LODWORD(v104) = 981;
          goto LABEL_10;
        }
        v20 = 981;
        v21 = 1004553;
        goto LABEL_12;
      }
    }
    if ( !*((_DWORD *)this + 76) )
      *((_DWORD *)this + 76) = 1;
    if ( (unsigned int)CVar::HasValue((CRecord *)((char *)this + 168)) )
    {
      if ( (*((_WORD *)this + 92) & 0xBFFF) != 8 )
      {
        v61 = 8;
        goto LABEL_134;
      }
      v60 = (_QWORD *)((char *)this + 208);
      if ( !(unsigned int)CSysString::IsEmpty(*((CSysString **)this + 26)) )
      {
LABEL_133:
        v61 = 8;
        goto LABEL_134;
      }
    }
    else
    {
      v60 = (_QWORD *)((char *)this + 208);
    }
    v61 = 8;
    if ( (*((_WORD *)this + 116) & 0xBFFF) == 8 )
    {
      if ( (unsigned int)CSysString::IsEmpty(*((CSysString **)this + 32)) )
        goto LABEL_133;
      v112 = 0;
      v113 = 7;
      v69 = (const struct CVar *)CVar::operator=((CRecord *)((char *)this + 168));
      if ( (unsigned int)CContext::VariantFailed((CContext *)v109, v69) )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
          {
            v70 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
            v71 = 1017865;
            LODWORD(v104) = 994;
LABEL_148:
            bidTraceW(off_18012A1E8[0], v71, L"<CRecord::Open|ADO|ERR> %u#, line %d\n", v70, v104, v105, v106, v107);
            goto LABEL_151;
          }
          v72 = 994;
          v73 = 1017865;
          goto LABEL_150;
        }
      }
      else
      {
        LODWORD(v127) = CSysString::Set((CSysString *)&v112, L"URL=", 4u);
        if ( (unsigned int)CContext::Failed((CContext *)v109, (const int *)&v127) )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_151;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
          {
            v70 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
            v71 = 1018889;
            LODWORD(v104) = 995;
            goto LABEL_148;
          }
          v72 = 995;
          v73 = 1018889;
LABEL_150:
          bidTraceW(off_18012A1E8[0], v73, L"<CRecord::Open|ADO|ERR>  line %d\n", v72);
          goto LABEL_151;
        }
        v74 = (const struct CSysString *)CSysString::operator+=(&v112, *v60);
        if ( (unsigned int)CContext::StringFailed((CContext *)v109, v74) )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_151;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
          {
            v70 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
            v71 = 1019913;
            LODWORD(v104) = 996;
            goto LABEL_148;
          }
          v72 = 996;
          v73 = 1019913;
          goto LABEL_150;
        }
        v75 = (const struct CVar *)CVar::operator=((CRecord *)((char *)this + 168));
        if ( !(unsigned int)CContext::VariantFailed((CContext *)v109, v75) )
        {
          LOBYTE(a6) = 1;
          CSysString::~CSysString((CSysString *)&v112);
          goto LABEL_133;
        }
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
          {
            v70 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
            v71 = 1020937;
            LODWORD(v104) = 997;
            goto LABEL_148;
          }
          v72 = 997;
          v73 = 1020937;
          goto LABEL_150;
        }
      }
LABEL_151:
      CSysString::~CSysString((CSysString *)&v112);
      goto LABEL_13;
    }
LABEL_134:
    if ( (((*((_WORD *)this + 116) & 0xBFFF) - 9) & 0xFFFB) != 0 )
    {
      v81 = *((_WORD *)this + 92) & 0xBFFF;
      v82 = a8;
      v83 = a7;
      if ( v81 == 8 )
      {
        LODWORD(v127) = ATL::CComObject<CConnection>::CreateInstance(&v114);
        if ( (unsigned int)CContext::Failed((CContext *)v109, (const int *)&v127) )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_292;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
          {
            v67 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
            v68 = 1079305;
            LODWORD(v104) = 1054;
            goto LABEL_140;
          }
          v76 = 1054;
          v77 = 1079305;
          goto LABEL_170;
        }
        v84 = v114;
        (*(void (__fastcall **)(_QWORD *))(*v114 + 8LL))(v114);
        if ( (bidGblFlags & 2) != 0 && off_18012A588[0] )
        {
          v85 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(v84 + 32));
          v86 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
          LODWORD(v104) = v85;
          bidTraceW(off_18012A1E8[0], 1081344, off_18012A588[0], v86, v104);
          v84 = v114;
        }
        (*(void (__fastcall **)(char *, GUID *, __int64 *))(*((_QWORD *)this + 13) + 32LL))(
          (char *)this + 104,
          &IID_IUnknown,
          &v117);
        if ( v117 )
          (*(void (__fastcall **)(_QWORD *))(v84[26] + 24LL))(v84 + 26);
        (*(void (__fastcall **)(_QWORD *, _QWORD))(v84[27] + 32LL))(v84 + 27, *((unsigned int *)this + 34));
        if ( *((_QWORD *)this + 16) )
          (*(void (__fastcall **)(_QWORD *))(v84[27] + 24LL))(v84 + 27);
        v87 = v114;
        LODWORD(v127) = (*(__int64 (__fastcall **)(_QWORD *, _QWORD))(*v114 + 248LL))(
                          v114,
                          *((unsigned int *)this + 76));
        if ( (unsigned int)CContext::Failed((CContext *)v109, (const int *)&v127) )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_292;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
          {
            v67 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
            v68 = 1099785;
            LODWORD(v104) = 1074;
            goto LABEL_140;
          }
          v76 = 1074;
          v77 = 1099785;
          goto LABEL_170;
        }
        v88 = (__int64 *)*((_QWORD *)this + 26);
        if ( (v88[1] & 4) != 0 )
          v89 = *v88;
        else
          v89 = 0;
        LODWORD(v127) = (*(__int64 (__fastcall **)(_QWORD *, __int64, unsigned __int16 *, unsigned __int16 *, int, unsigned int, enum RecordCreateOptionsEnum, enum RecordOpenOptionsEnum))(*v87 + 160LL))(
                          v87,
                          v89,
                          v83,
                          v82,
                          -1,
                          v105,
                          v106,
                          v107);
        if ( (unsigned int)CContext::Failed((CContext *)v109, (const int *)&v127) )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_292;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
          {
            v67 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
            v68 = 1100809;
            LODWORD(v104) = 1075;
            goto LABEL_140;
          }
          v76 = 1075;
          v77 = 1100809;
          goto LABEL_170;
        }
        LODWORD(v127) = (*(__int64 (__fastcall **)(_QWORD *, GUID *, struct IUnknown **))*v87)(
                          v87,
                          &IID_IDispatch,
                          &v115);
        if ( (unsigned int)CContext::Failed((CContext *)v109, (const int *)&v127) )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_292;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
          {
            v67 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
            v68 = 1101833;
            LODWORD(v104) = 1076;
            goto LABEL_140;
          }
          v76 = 1076;
          v77 = 1101833;
          goto LABEL_170;
        }
        LODWORD(v127) = CRecord::Connect(this, v115);
        if ( (unsigned int)CContext::Failed((CContext *)v109, (const int *)&v127) )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_292;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
          {
            v67 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
            v68 = 1102857;
            LODWORD(v104) = 1077;
            goto LABEL_140;
          }
          v76 = 1077;
          v77 = 1102857;
          goto LABEL_170;
        }
        v90 = (const struct CVar *)CVar::operator=((char *)this + 168, v115);
        if ( (unsigned int)CContext::VariantFailed((CContext *)v109, v90) )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_292;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
          {
            v67 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
            v68 = 1103881;
            LODWORD(v104) = 1078;
            goto LABEL_140;
          }
          v76 = 1078;
          v77 = 1103881;
          goto LABEL_170;
        }
      }
      else if ( ((v81 - 9) & 0xFFFB) != 0 )
      {
        LODWORD(v127) = -2146824579;
        if ( (unsigned int)CContext::Failed((CContext *)v109, (const int *)&v127) )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_292;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
          {
            v67 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
            v68 = 1107977;
            LODWORD(v104) = 1082;
            goto LABEL_140;
          }
          v76 = 1082;
          v77 = 1107977;
          goto LABEL_170;
        }
      }
      v91 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))CVar::operator IUnknown *(
                                                                   (char *)this + 168,
                                                                   v61,
                                                                   v58,
                                                                   v59);
      LODWORD(v127) = (**v91)(v91, &IID_IADOClass, &v118);
      if ( (unsigned int)CContext::Failed((CContext *)v109, (const int *)&v127) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_292;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
        {
          v67 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
          v68 = 1111049;
          LODWORD(v104) = 1085;
          goto LABEL_140;
        }
        v76 = 1085;
        v77 = 1111049;
        goto LABEL_170;
      }
      (*(void (__fastcall **)(__int64, struct _ADOConnection **))(*(_QWORD *)v118 + 24LL))(v118, &v116);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v118 + 16LL))(v118);
      if ( (unsigned int)CVar::HasValue((CRecord *)((char *)this + 216)) )
      {
        v94 = *((_QWORD *)this + 32);
        if ( (*(_BYTE *)(v94 + 8) & 4) != 0 )
          v93 = *(BSTR *)v94;
        else
          v93 = 0;
      }
      else
      {
        bstrString = SysAllocString(&WindowName);
        v92 = bstrString;
        if ( !bstrString )
        {
          LODWORD(v127) = -2147024882;
          if ( (unsigned int)CContext::Failed((CContext *)v109, (const int *)&v127) )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_292;
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
            {
              v67 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
              v68 = 1121289;
              LODWORD(v104) = 1095;
              goto LABEL_140;
            }
            v76 = 1095;
            v77 = 1121289;
            goto LABEL_170;
          }
        }
        v93 = v92;
      }
      if ( (v16 & 0x10000) != 0 )
      {
        LODWORD(v127) = CRecord::OpenFromNewCommand(this, v116, v16);
        if ( (unsigned int)CContext::Failed((CContext *)v109, (const int *)&v127) )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_292;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
          {
            v67 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
            v68 = 1134601;
            LODWORD(v104) = 1108;
            goto LABEL_140;
          }
          v76 = 1108;
          v77 = 1134601;
          goto LABEL_170;
        }
      }
      else
      {
        v95 = *((_DWORD *)this + 76) | v16;
        v96 = *(_QWORD *)v116;
        if ( a5 == adFailIfNotExists )
        {
          LODWORD(v127) = (*(__int64 (__fastcall **)(struct _ADOConnection *, BSTR, _QWORD, __int64, unsigned __int16 *, unsigned __int16 *, VARIANTARG *))(v96 + 400))(
                            v116,
                            v93,
                            v95,
                            1,
                            v83,
                            v82,
                            &pvarg);
          if ( (unsigned int)CContext::Failed((CContext *)v109, (const int *)&v127) )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_292;
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
            {
              v67 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
              v68 = 1141769;
              LODWORD(v104) = 1115;
              goto LABEL_140;
            }
            v76 = 1115;
            v77 = 1141769;
            goto LABEL_170;
          }
        }
        else
        {
          LODWORD(v127) = (*(__int64 (__fastcall **)(struct _ADOConnection *, BSTR, _QWORD, unsigned __int16 *, unsigned __int16 *, VARIANTARG *))(v96 + 408))(
                            v116,
                            v93,
                            a5 | v95,
                            v83,
                            v82,
                            &pvarg);
          if ( (unsigned int)CContext::Failed((CContext *)v109, (const int *)&v127) )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_292;
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
            {
              v67 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
              v68 = 1146889;
              LODWORD(v104) = 1120;
              goto LABEL_140;
            }
            v76 = 1120;
            v77 = 1146889;
            goto LABEL_170;
          }
        }
        LODWORD(v127) = (**(__int64 (__fastcall ***)(LONGLONG, GUID *, char *))pvarg.llVal)(
                          pvarg.llVal,
                          &IID_IRow,
                          (char *)this + 272);
        if ( (unsigned int)CContext::Failed((CContext *)v109, (const int *)&v127) )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_292;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
          {
            v67 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
            v68 = 1149961;
            LODWORD(v104) = 1123;
            goto LABEL_140;
          }
          v76 = 1123;
          v77 = 1149961;
          goto LABEL_170;
        }
      }
    }
    else
    {
      v108 = 0;
      v120 = 0;
      v112 = 0;
      v111 = 0;
      if ( CVar::operator IUnknown *((char *)this + 216, 8, v58, v59) )
      {
        v66 = (__int64 (__fastcall ***)(_QWORD, GUID *, struct IUnknown **))CVar::operator IUnknown *(
                                                                              v63,
                                                                              v62,
                                                                              v64,
                                                                              v65);
        LODWORD(v127) = (**v66)(v66, &IID_IUnknown, &v108);
        if ( (unsigned int)CContext::Failed((CContext *)v109, (const int *)&v127) )
        {
          if ( (bidGblFlags & 2) == 0 )
          {
LABEL_292:
            v17 = a6;
            goto LABEL_293;
          }
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
          {
            v67 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
            v68 = 1037321;
            LODWORD(v104) = 1013;
LABEL_140:
            bidTraceW(off_18012A1E8[0], v68, L"<CRecord::Open|ADO|ERR> %u#, line %d\n", v67, v104);
            goto LABEL_292;
          }
          v76 = 1013;
          v77 = 1037321;
          goto LABEL_170;
        }
      }
      else
      {
        LODWORD(v127) = -2146825287;
        if ( (unsigned int)CContext::Failed((CContext *)v109, (const int *)&v127) )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_292;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
          {
            v67 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
            v68 = 1040393;
            LODWORD(v104) = 1016;
            goto LABEL_140;
          }
          v76 = 1016;
          v77 = 1040393;
LABEL_170:
          bidTraceW(off_18012A1E8[0], v77, L"<CRecord::Open|ADO|ERR>  line %d\n", v76);
          goto LABEL_292;
        }
      }
      v78 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))v108->lpVtbl->QueryInterface)(
              v108,
              &IID_IADORecordset,
              &v120) < 0;
      lpVtbl = v108->lpVtbl;
      if ( v78 )
      {
        if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))lpVtbl->QueryInterface)(
               v108,
               &IID_IADORecord,
               &v112) < 0 )
        {
          if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))v108->lpVtbl->QueryInterface)(
                 v108,
                 &IID_IADOCommand,
                 &v111) < 0 )
          {
            ((void (__fastcall *)(struct IUnknown *))v108->lpVtbl->Release)(v108);
            LODWORD(v127) = -2146825287;
            if ( (unsigned int)CContext::Failed((CContext *)v109, (const int *)&v127) )
            {
              if ( (bidGblFlags & 2) == 0 )
                goto LABEL_292;
              if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
              {
                v67 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
                v68 = 1072137;
                LODWORD(v104) = 1047;
                goto LABEL_140;
              }
              v76 = 1047;
              v77 = 1072137;
              goto LABEL_170;
            }
          }
          else
          {
            if ( v111 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v111 + 16LL))(v111);
              v111 = 0;
            }
            LODWORD(v127) = CRecord::OpenFromCommand(this, v108);
            CContext::Failed((CContext *)v109, (const int *)&v127);
            ((void (__fastcall *)(struct IUnknown *))v108->lpVtbl->Release)(v108);
            if ( v110 < 0 )
            {
              if ( (bidGblFlags & 2) == 0 )
                goto LABEL_292;
              if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
              {
                v67 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
                v68 = 1065993;
                LODWORD(v104) = 1041;
                goto LABEL_140;
              }
              v76 = 1041;
              v77 = 1065993;
              goto LABEL_170;
            }
          }
        }
        else
        {
          LODWORD(v127) = CRecord::Clone(this, v108);
          CContext::Failed((CContext *)v109, (const int *)&v127);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v112 + 16LL))(v112);
          ((void (__fastcall *)(struct IUnknown *))v108->lpVtbl->Release)(v108);
          if ( v110 < 0 )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_292;
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
            {
              v67 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
              v68 = 1057801;
              LODWORD(v104) = 1033;
              goto LABEL_140;
            }
            v76 = 1033;
            v77 = 1057801;
            goto LABEL_170;
          }
        }
      }
      else
      {
        ((void (*)(void))lpVtbl->Release)();
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v120 + 16LL))(v120);
        LODWORD(v127) = CRecord::OpenFromRecordset(this, v80);
        if ( (unsigned int)CContext::Failed((CContext *)v109, (const int *)&v127) )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_292;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
          {
            v67 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
            v68 = 1047561;
            LODWORD(v104) = 1023;
            goto LABEL_140;
          }
          v76 = 1023;
          v77 = 1047561;
          goto LABEL_170;
        }
      }
    }
    if ( (*((_BYTE *)this + 304) & 2) != 0 )
    {
      v97 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 34);
      if ( v97 )
      {
        if ( (v127 = 0, v98 = (**v97)(v97, &IID_IRowChange, &v127), v99 = v127, v98 >= 0) && v127
          || (*((_DWORD *)this + 76) = *((_DWORD *)this + 76) & 0xFFFFFFFC | 1, v99) )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v99 + 16LL))(v99);
        }
      }
    }
    goto LABEL_292;
  }
  if ( (bidGblFlags & 2) != 0 )
  {
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
    {
      v18 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
      v19 = 927753;
      LODWORD(v104) = 906;
      goto LABEL_10;
    }
    v20 = 906;
    v21 = 927753;
LABEL_12:
    bidTraceW(off_18012A1E8[0], v21, L"<CRecord::Open|ADO|ERR>  line %d\n", v20);
    goto LABEL_13;
  }
LABEL_293:
  SysFreeString(bstrString);
  if ( v114 )
    (*(void (__fastcall **)(_QWORD *))(*v114 + 16LL))(v114);
  if ( v115 )
  {
    ((void (__fastcall *)(struct IUnknown *))v115->lpVtbl->Release)(v115);
    v115 = 0;
  }
  if ( v117 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v117 + 16LL))(v117);
    v117 = 0;
  }
  VariantClear(&pvarg);
  if ( v110 < 0 && v17 )
  {
    CRecord::Disconnect(this);
    CVar::Clear((CRecord *)((char *)this + 168));
  }
  if ( (bidGblFlags & 2) != 0 && off_18012A570[0] )
  {
    v100 = v110;
    v101 = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
    LODWORD(v104) = v100;
    bidTraceW(off_18012A1E8[0], 1184768, off_18012A570[0], v101, v104);
  }
  if ( (bidGblFlags & 4) != 0 && v119 != -1 && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *))off_180121248[0])(bidID, 0, 0, &v119);
  v102 = v110;
  CXLockContext::~CXLockContext((CXLockContext *)v109);
  v123[0] = &CVar::`vftable';
  CVar::Clear((CVar *)v123);
  v125[0] = &CVar::`vftable';
  CVar::Clear((CVar *)v125);
  return v102;
}

```

## disassembly

```asm
0x18008ea50  push    rbp
0x18008ea52  push    rbx
0x18008ea53  push    rsi
0x18008ea54  push    rdi
0x18008ea55  push    r12
0x18008ea57  push    r13
0x18008ea59  push    r14
0x18008ea5b  push    r15
0x18008ea5d  lea     rbp, [rsp-58h]
0x18008ea62  sub     rsp, 158h
0x18008ea69  mov     ebx, [rbp+90h+arg_28]
0x18008ea6f  xor     r12d, r12d
0x18008ea72  test    byte ptr cs:_bidGblFlags, 4
0x18008ea79  mov     r15d, r9d
0x18008ea7c  mov     rsi, r8
0x18008ea7f  mov     [rbp+90h+var_D0], 0FFFFFFFFFFFFFFFFh
0x18008ea87  mov     r14, rdx
0x18008ea8a  mov     rdi, rcx
0x18008ea8d  jz      short loc_18008EAD5
0x18008ea8f  mov     rax, cs:off_18012AB20; "<CRecord::Open|API|ADO> %u#, vSrc: %p{V"...
0x18008ea96  test    rax, rax
0x18008ea99  jz      short loc_18008EAD5
0x18008ea9b  add     rcx, 98h; this
0x18008eaa2  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008eaa7  mov     ecx, [rbp+90h+arg_20]
0x18008eaad  mov     r9, r14
0x18008eab0  mov     rdx, cs:off_18012AB20; "<CRecord::Open|API|ADO> %u#, vSrc: %p{V"...
0x18008eab7  mov     r8d, eax
0x18008eaba  mov     [rsp+190h+var_158], ebx
0x18008eabe  mov     dword ptr [rsp+190h+var_160], ecx
0x18008eac2  lea     rcx, [rbp+90h+var_D0]
0x18008eac6  mov     dword ptr [rsp+190h+var_168], r15d
0x18008eacb  mov     [rsp+190h+var_170], rsi
0x18008ead0  call    _bidScopeEnterW
0x18008ead5  xor     eax, eax
0x18008ead7  lea     rcx, [rbp+90h+var_70]; this
0x18008eadb  xorps   xmm0, xmm0
0x18008eade  mov     qword ptr [rbp+90h+pvarg+10h], rax
0x18008eae2  mov     r8b, 4; unsigned __int8
0x18008eae5  mov     rdx, r14; struct tagVARIANT *
0x18008eae8  movups  xmmword ptr [rbp+90h+pvarg], xmm0
0x18008eaec  lea     r13d, [rax+1]
0x18008eaf0  mov     r9d, r13d; int
0x18008eaf3  call    ??0CVar@@QEAA@AEBUtagVARIANT@@EH@Z; CVar::CVar(tagVARIANT const &,uchar,int)
0x18008eaf8  mov     r9d, r13d; int
0x18008eafb  lea     rcx, [rbp+90h+var_A0]; this
0x18008eaff  mov     r8b, 4; unsigned __int8
0x18008eb02  mov     rdx, rsi; struct tagVARIANT *
0x18008eb05  call    ??0CVar@@QEAA@AEBUtagVARIANT@@EH@Z; CVar::CVar(tagVARIANT const &,uchar,int)
0x18008eb0a  mov     r8, [rdi+90h]
0x18008eb11  lea     rcx, [rdi+20h]
0x18008eb15  lea     esi, [r13+7]
0x18008eb19  mov     [rbp+90h+var_E8], r12
0x18008eb1d  add     r8, rsi; struct CCriticalSection **
0x18008eb20  mov     [rbp+90h+var_D8], r12
0x18008eb24  mov     rax, rdi
0x18008eb27  neg     rax
0x18008eb2a  sbb     rdx, rdx
0x18008eb2d  and     rdx, rcx; struct CStdComObjectRoot *
0x18008eb30  lea     rcx, [rsp+190h+var_148]; this
0x18008eb35  call    ??0CXLockContext@@QEAA@PEAVCStdComObjectRoot@@PEAPEAVCCriticalSection@@PEBD@Z; CXLockContext::CXLockContext(CStdComObjectRoot *,CCriticalSection * *,char const *)
0x18008eb3a  cmp     ebx, 0FFFFFFFFh
0x18008eb3d  mov     [rbp+90h+bstrString], r12
0x18008eb41  mov     r13d, r12d
0x18008eb44  mov     [rbp+90h+var_E0], r12
0x18008eb48  cmovnz  r13d, ebx
0x18008eb4c  mov     [rbp+90h+var_F8], r12
0x18008eb50  mov     bl, r12b
0x18008eb53  mov     [rbp+90h+var_F0], r12
0x18008eb57  lea     rcx, [rbp+90h+pvarg]; pvarg
0x18008eb5b  mov     byte ptr [rbp+90h+arg_28], bl
0x18008eb61  call    cs:__imp_VariantInit
0x18008eb68  nop     dword ptr [rax+rax+00h]
0x18008eb6d  lea     rdx, [rbp+90h+var_70]; struct CVar *
0x18008eb71  lea     rcx, [rsp+190h+var_148]; this
0x18008eb76  call    ?VariantFailed@CContext@@QEAAHAEBVCVar@@@Z; CContext::VariantFailed(CVar const &)
0x18008eb7b  test    eax, eax
0x18008eb7d  jz      short loc_18008EBF3
0x18008eb7f  test    byte ptr cs:_bidGblFlags, 2
0x18008eb86  jz      loc_18009043A
0x18008eb8c  lea     rbx, [rdi+98h]
0x18008eb93  mov     rcx, rbx; this
0x18008eb96  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008eb9b  cmp     eax, 0FFFFFFFFh
0x18008eb9e  jz      short loc_18008EBCD
0x18008eba0  mov     rcx, rbx; this
0x18008eba3  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008eba8  mov     edx, 0E2409h
0x18008ebad  mov     dword ptr [rsp+190h+var_170], 389h
0x18008ebb5  mov     rcx, cs:off_18012A1E8; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18008ebbc  lea     r8, aCrecordOpenAdo_0; "<CRecord::Open|ADO|ERR> %u#, line %d\n"
0x18008ebc3  mov     r9d, eax
0x18008ebc6  call    _bidTraceW
0x18008ebcb  jmp     short loc_18008EBEB
0x18008ebcd  mov     r9d, 389h
0x18008ebd3  mov     edx, 0E2409h
0x18008ebd8  mov     rcx, cs:off_18012A1E8; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18008ebdf  lea     r8, aCrecordOpenAdo; "<CRecord::Open|ADO|ERR>  line %d\n"
0x18008ebe6  call    _bidTraceW
0x18008ebeb  mov     bl, r12b
0x18008ebee  jmp     loc_18009043A
0x18008ebf3  lea     rdx, [rbp+90h+var_A0]; struct CVar *
0x18008ebf7  lea     rcx, [rsp+190h+var_148]; this
0x18008ebfc  call    ?VariantFailed@CContext@@QEAAHAEBVCVar@@@Z; CContext::VariantFailed(CVar const &)
0x18008ec01  test    eax, eax
0x18008ec03  jz      short loc_18008EC4D
0x18008ec05  test    byte ptr cs:_bidGblFlags, 2
0x18008ec0c  jz      loc_18009043A
0x18008ec12  lea     rbx, [rdi+98h]
0x18008ec19  mov     rcx, rbx; this
0x18008ec1c  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008ec21  cmp     eax, 0FFFFFFFFh
0x18008ec24  jz      short loc_18008EC40
0x18008ec26  mov     rcx, rbx; this
0x18008ec29  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008ec2e  mov     edx, 0E2809h
0x18008ec33  mov     dword ptr [rsp+190h+var_170], 38Ah
0x18008ec3b  jmp     loc_18008EBB5
0x18008ec40  mov     r9d, 38Ah
0x18008ec46  mov     edx, 0E2809h
0x18008ec4b  jmp     short loc_18008EBD8
0x18008ec4d  cmp     [rdi+110h], r12
0x18008ec54  jz      short loc_18008ECC0
0x18008ec56  lea     rdx, [rbp+90h+arg_0]; int *
0x18008ec5d  mov     dword ptr [rbp+90h+arg_0], 800A0E79h
0x18008ec67  lea     rcx, [rsp+190h+var_148]; this
0x18008ec6c  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18008ec71  test    eax, eax
0x18008ec73  jz      short loc_18008ECC0
0x18008ec75  test    byte ptr cs:_bidGblFlags, 2
0x18008ec7c  jz      loc_18009043A
0x18008ec82  lea     rbx, [rdi+98h]
0x18008ec89  mov     rcx, rbx; this
0x18008ec8c  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008ec91  cmp     eax, 0FFFFFFFFh
0x18008ec94  jz      short loc_18008ECB0
0x18008ec96  mov     rcx, rbx; this
0x18008ec99  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008ec9e  mov     edx, 0E3809h
0x18008eca3  mov     dword ptr [rsp+190h+var_170], 38Eh
0x18008ecab  jmp     loc_18008EBB5
0x18008ecb0  mov     r9d, 38Eh
0x18008ecb6  mov     edx, 0E3809h
0x18008ecbb  jmp     loc_18008EBD8
0x18008ecc0  mov     rax, [rdi+240h]
0x18008ecc7  test    rax, rax
0x18008ecca  jz      short loc_18008ED3F
0x18008eccc  cmp     [rax+220h], r12b
0x18008ecd3  jz      short loc_18008ED3F
0x18008ecd5  lea     rdx, [rbp+90h+arg_0]; int *
0x18008ecdc  mov     dword ptr [rbp+90h+arg_0], 800A0E7Fh
0x18008ece6  lea     rcx, [rsp+190h+var_148]; this
0x18008eceb  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18008ecf0  test    eax, eax
0x18008ecf2  jz      short loc_18008ED3F
0x18008ecf4  test    byte ptr cs:_bidGblFlags, 2
0x18008ecfb  jz      loc_18009043A
0x18008ed01  lea     rbx, [rdi+98h]
0x18008ed08  mov     rcx, rbx; this
0x18008ed0b  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008ed10  cmp     eax, 0FFFFFFFFh
0x18008ed13  jz      short loc_18008ED2F
0x18008ed15  mov     rcx, rbx; this
0x18008ed18  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008ed1d  mov     edx, 0E4C09h
0x18008ed22  mov     dword ptr [rsp+190h+var_170], 393h
0x18008ed2a  jmp     loc_18008EBB5
0x18008ed2f  mov     r9d, 393h
0x18008ed35  mov     edx, 0E4C09h
0x18008ed3a  jmp     loc_18008EBD8
0x18008ed3f  lea     rcx, [rbp+90h+var_70]; this
0x18008ed43  call    ?Exists@CVar@@QEBAHXZ; CVar::Exists(void)
0x18008ed48  mov     ebx, 0BFFFh
0x18008ed4d  test    eax, eax
0x18008ed4f  jz      loc_18008F037
0x18008ed55  mov     r8d, [rbp+90h+var_60]
0x18008ed59  mov     ecx, r8d
0x18008ed5c  and     ecx, ebx
0x18008ed5e  sub     ecx, esi
0x18008ed60  jz      loc_18008EF54
0x18008ed66  sub     ecx, 1
0x18008ed69  jz      short loc_18008EDDE
0x18008ed6b  cmp     ecx, 4
0x18008ed6e  jz      short loc_18008EDDE
0x18008ed70  lea     rdx, [rbp+90h+arg_0]; int *
0x18008ed77  mov     dword ptr [rbp+90h+arg_0], 800A0BB9h
0x18008ed81  lea     rcx, [rsp+190h+var_148]; this
0x18008ed86  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18008ed8b  test    eax, eax
0x18008ed8d  jz      loc_18008F037
0x18008ed93  test    byte ptr cs:_bidGblFlags, 2
0x18008ed9a  jz      loc_18008EBEB
0x18008eda0  lea     rbx, [rdi+98h]
0x18008eda7  mov     rcx, rbx; this
0x18008edaa  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008edaf  cmp     eax, 0FFFFFFFFh
0x18008edb2  jz      short loc_18008EDCE
0x18008edb4  mov     rcx, rbx; this
0x18008edb7  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008edbc  mov     edx, 0EB009h
0x18008edc1  mov     dword ptr [rsp+190h+var_170], 3ACh
0x18008edc9  jmp     loc_18008EBB5
0x18008edce  mov     r9d, 3ACh
0x18008edd4  mov     edx, 0EB009h
0x18008edd9  jmp     loc_18008EBD8
0x18008edde  lea     rcx, [rbp+90h+var_70]
0x18008ede2  call    ??BCVar@@QEAAPEAUIUnknown@@XZ; CVar::operator IUnknown *(void)
0x18008ede7  test    rax, rax
0x18008edea  jz      loc_18008EEE6
0x18008edf0  and     r8w, bx
0x18008edf4  lea     r9, [rdi+0D8h]
0x18008edfb  lea     rcx, [rbp+90h+var_70]
0x18008edff  cmp     r8w, 0Dh
0x18008ee04  jnz     short loc_18008EE76
0x18008ee06  call    ??BCVar@@QEAAPEAUIUnknown@@XZ; CVar::operator IUnknown *(void)
0x18008ee0b  mov     rdx, rax
0x18008ee0e  mov     rcx, r9
0x18008ee11  call    ??4CVar@@QEAAAEBV0@QEAUIUnknown@@@Z; CVar::operator=(IUnknown * const)
0x18008ee16  mov     rdx, rax; struct CVar *
0x18008ee19  lea     rcx, [rsp+190h+var_148]; this
0x18008ee1e  call    ?VariantFailed@CContext@@QEAAHAEBVCVar@@@Z; CContext::VariantFailed(CVar const &)
0x18008ee23  test    eax, eax
0x18008ee25  jz      loc_18008F037
0x18008ee2b  test    byte ptr cs:_bidGblFlags, 2
0x18008ee32  jz      loc_18008EBEB
0x18008ee38  lea     rbx, [rdi+98h]
0x18008ee3f  mov     rcx, rbx; this
0x18008ee42  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008ee47  cmp     eax, 0FFFFFFFFh
0x18008ee4a  jz      short loc_18008EE66
0x18008ee4c  mov     rcx, rbx; this
0x18008ee4f  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008ee54  mov     edx, 0E9009h
0x18008ee59  mov     dword ptr [rsp+190h+var_170], 3A4h
0x18008ee61  jmp     loc_18008EBB5
0x18008ee66  mov     r9d, 3A4h
0x18008ee6c  mov     edx, 0E9009h
0x18008ee71  jmp     loc_18008EBD8
0x18008ee76  call    ??BCVar@@QEAAPEAUIUnknown@@XZ; CVar::operator IUnknown *(void)
0x18008ee7b  mov     rdx, rax
0x18008ee7e  mov     rcx, r9
0x18008ee81  call    ??4CVar@@QEAAAEBV0@QEAUIDispatch@@@Z; CVar::operator=(IDispatch * const)
0x18008ee86  mov     rdx, rax; struct CVar *
0x18008ee89  lea     rcx, [rsp+190h+var_148]; this
0x18008ee8e  call    ?VariantFailed@CContext@@QEAAHAEBVCVar@@@Z; CContext::VariantFailed(CVar const &)
0x18008ee93  test    eax, eax
0x18008ee95  jz      loc_18008F037
0x18008ee9b  test    byte ptr cs:_bidGblFlags, 2
0x18008eea2  jz      loc_18008EBEB
0x18008eea8  lea     rbx, [rdi+98h]
0x18008eeaf  mov     rcx, rbx; this
0x18008eeb2  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008eeb7  cmp     eax, 0FFFFFFFFh
0x18008eeba  jz      short loc_18008EED6
0x18008eebc  mov     rcx, rbx; this
0x18008eebf  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008eec4  mov     edx, 0E9809h
0x18008eec9  mov     dword ptr [rsp+190h+var_170], 3A6h
0x18008eed1  jmp     loc_18008EBB5
0x18008eed6  mov     r9d, 3A6h
0x18008eedc  mov     edx, 0E9809h
0x18008eee1  jmp     loc_18008EBD8
0x18008eee6  lea     rdx, [rbp+90h+arg_0]; int *
0x18008eeed  mov     dword ptr [rbp+90h+arg_0], 800A0BB9h
0x18008eef7  lea     rcx, [rsp+190h+var_148]; this
0x18008eefc  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18008ef01  test    eax, eax
0x18008ef03  jz      loc_18008F037
0x18008ef09  test    byte ptr cs:_bidGblFlags, 2
0x18008ef10  jz      loc_18008EBEB
0x18008ef16  lea     rbx, [rdi+98h]
0x18008ef1d  mov     rcx, rbx; this
0x18008ef20  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008ef25  cmp     eax, 0FFFFFFFFh
0x18008ef28  jz      short loc_18008EF44
0x18008ef2a  mov     rcx, rbx; this
0x18008ef2d  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008ef32  mov     edx, 0EA409h
0x18008ef37  mov     dword ptr [rsp+190h+var_170], 3A9h
0x18008ef3f  jmp     loc_18008EBB5
0x18008ef44  mov     r9d, 3A9h
0x18008ef4a  mov     edx, 0EA409h
0x18008ef4f  jmp     loc_18008EBD8
0x18008ef54  lea     rcx, [rdi+0D8h]; this
0x18008ef5b  lea     rdx, [rbp+90h+var_70]
0x18008ef5f  call    ??4CVar@@QEAAAEBV0@AEBV0@@Z; CVar::operator=(CVar const &)
0x18008ef64  mov     rdx, rax; struct CVar *
0x18008ef67  lea     rcx, [rsp+190h+var_148]; this
0x18008ef6c  call    ?VariantFailed@CContext@@QEAAHAEBVCVar@@@Z; CContext::VariantFailed(CVar const &)
0x18008ef71  test    eax, eax
0x18008ef73  jz      short loc_18008EFC0
0x18008ef75  test    byte ptr cs:_bidGblFlags, 2
0x18008ef7c  jz      loc_18008EBEB
0x18008ef82  lea     rbx, [rdi+98h]
0x18008ef89  mov     rcx, rbx; this
0x18008ef8c  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008ef91  cmp     eax, 0FFFFFFFFh
0x18008ef94  jz      short loc_18008EFB0
0x18008ef96  mov     rcx, rbx; this
0x18008ef99  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
  ... truncated ...
```
