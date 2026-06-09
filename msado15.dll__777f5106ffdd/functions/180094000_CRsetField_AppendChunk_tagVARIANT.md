# CRsetField::AppendChunk(tagVARIANT)

- ea: `0x180094000`
- end: `0x180094b1b`
- name: `?AppendChunk@CRsetField@@UEAAJUtagVARIANT@@@Z`
- size: `2843`
- prototype: `__int64 __fastcall(CRsetField *__hidden this, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `32`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180094b30`

## callees

- `0x180008340`
- `0x1800092d0`
- `0x18000b760`
- `0x180011088`
- `0x180018788`
- `0x18001a750`
- `0x18001a820`
- `0x180020da0`
- `0x180020e20`
- `0x180030ce0`
- `0x180031760`
- `0x180032710`
- `0x18003d270`
- `0x180049010`
- `0x1800497a0`
- `0x18004c5f0`
- `0x18004f1b0`
- `0x18004f2b0`
- `0x18004f370`
- `0x180054098`
- `0x180056e84`
- `0x180057bdc`
- `0x18005cd08`
- `0x18005d3b0`
- `0x18006a22c`
- `0x180094000`
- `0x1800ac9b4`
- `0x1800c8ebc`
- `0x1800c8f34`
- `0x1800cbc18`
- `0x1800cd4c4`
- `0x1800d0010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180094a59`
- `OLEAUT32!__imp_SysFreeString` at `0x180094a59`
- `OLEAUT32!__imp_VariantInit` at `0x180094804`
- `OLEAUT32!__imp_VariantInit` at `0x180094804`
- `OLEAUT32!__imp_VariantClear` at `0x180094855`
- `OLEAUT32!__imp_VariantClear` at `0x180094855`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180094794`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180094794`

## pseudocode

```c
__int64 __fastcall CRsetField::AppendChunk(CRsetField *this, struct tagVARIANT *a2, __int64 a3, const char *a4)
{
  char *v4; // rsi
  struct CStdComObjectRoot *v7; // rbx
  unsigned int BidObjectID; // eax
  __int64 v9; // rdx
  __int64 v10; // r9
  __int64 v11; // rdx
  unsigned int v12; // ebx
  char *v13; // rcx
  bool v14; // zf
  OLECHAR *v15; // rsi
  CRecordset *v16; // r15
  unsigned int v17; // eax
  IRecordInfo *pRecInfo; // xmm1_8
  unsigned int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // r9
  __int64 v22; // rdx
  int v23; // edx
  __int16 v24; // ax
  int v25; // edx
  _WORD *v26; // rbx
  int v27; // edx
  __int16 v28; // ax
  CSysString *v29; // r14
  unsigned int v30; // eax
  __int64 v31; // rbx
  BSTR v32; // r14
  int v33; // edx
  unsigned int v34; // eax
  __int64 v35; // rdx
  __int64 v36; // r9
  __int64 v37; // rdx
  SAFEARRAY *v38; // rbx
  unsigned int v39; // eax
  unsigned int v40; // eax
  unsigned int v41; // ebx
  unsigned int v42; // eax
  __int64 v44; // [rsp+20h] [rbp-E0h]
  int v45; // [rsp+20h] [rbp-E0h]
  BSTR bstrString; // [rsp+30h] [rbp-D0h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v48; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v49[40]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v50; // [rsp+80h] [rbp-80h]
  struct tagVARIANT v51; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v52[2]; // [rsp+B0h] [rbp-50h] BYREF
  struct tagVARIANT v53; // [rsp+C0h] [rbp-40h]
  _QWORD v54[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int16 v55; // [rsp+F0h] [rbp-10h]
  CSysString *v56; // [rsp+108h] [rbp+8h]
  int Stream; // [rsp+150h] [rbp+50h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+160h] [rbp+60h] BYREF
  int EOF; // [rsp+168h] [rbp+68h] BYREF

  v4 = (char *)this + 8;
  v7 = (struct CStdComObjectRoot *)(((unsigned __int64)this + 8) & -(__int64)(this != 0));
  CXLockContext::CXLockContext((CXLockContext *)v49, v7, (struct CCriticalSection **)(*((_QWORD *)this + 8) + 8LL), a4);
  if ( (unsigned int)CContext::IsZombied((CContext *)v49, v7) )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312)) != -1 )
      {
        BidObjectID = CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312));
        v9 = 814089;
        v45 = 795;
LABEL_10:
        bidTraceW(off_18012A1F0[0], v9, L"<CRsetField::AppendChunk|ADO|ERR> %u#, line %d\n", BidObjectID, v45);
        goto LABEL_13;
      }
      v10 = 795;
      v11 = 814089;
      goto LABEL_12;
    }
    goto LABEL_13;
  }
  if ( (unsigned int)CContext::FailIfClosed((CContext *)v49, *((_QWORD *)this + 21) != 0) )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312)) != -1 )
      {
        BidObjectID = CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312));
        v9 = 815113;
        v45 = 796;
        goto LABEL_10;
      }
      v10 = 796;
      v11 = 815113;
LABEL_12:
      bidTraceW(off_18012A1F0[0], v11, L"<CRsetField::AppendChunk|ADO|ERR>  line %d\n", v10);
    }
LABEL_13:
    v12 = v50;
    goto LABEL_132;
  }
  CVar::CVar((CVar *)v54, a2, 4u, 0);
  v13 = (char *)*((_QWORD *)v4 + 4);
  v14 = v4 == v13;
  bstrString = 0;
  v15 = 0;
  *(_QWORD *)&pvarg.vt = 0;
  if ( v14 )
    v13 = 0;
  v48 = -1;
  v16 = (CRecordset *)((unsigned __int64)(v13 - 32) & -(__int64)(v13 != 0));
  if ( (bidGblFlags & 4) != 0 && off_18012AB68[0] )
  {
    v17 = CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312));
    pRecInfo = a2->pRecInfo;
    *(_OWORD *)&v51.vt = *(_OWORD *)&a2->vt;
    v51.pRecInfo = pRecInfo;
    bidScopeEnterW(&v48, off_18012AB68[0], v17, &v51, v44);
  }
  LOWORD(Stream) = 0;
  LOWORD(rgsabound.cElements) = 0;
  EOF = CRecordset::_get_EOF(v16, (__int16 *)&Stream);
  if ( (unsigned int)CContext::Failed((CContext *)v49, &EOF) )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312)) != -1 )
      {
        v19 = CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312));
        v20 = 828425;
        LODWORD(v44) = 809;
LABEL_58:
        bidTraceW(off_18012A1F0[0], v20, L"<CRsetField::AppendChunk|ADO|ERR> %u#, line %d\n", v19, v44);
        goto LABEL_124;
      }
      v21 = 809;
      v22 = 828425;
      goto LABEL_60;
    }
    goto LABEL_127;
  }
  EOF = CRecordset::_get_BOF(v16, (__int16 *)&rgsabound);
  if ( !(unsigned int)CContext::Failed((CContext *)v49, &EOF) )
  {
    if ( (_WORD)Stream || (v23 = 1, LOWORD(rgsabound.cElements)) )
      v23 = 0;
    if ( (unsigned int)CContext::RecordFailed((CContext *)v49, v23) )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312)) != -1 )
        {
          v19 = CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312));
          v20 = 830473;
          LODWORD(v44) = 811;
          goto LABEL_58;
        }
        v21 = 811;
        v22 = 830473;
        goto LABEL_60;
      }
      goto LABEL_127;
    }
    if ( (unsigned int)CContext::VariantFailed((CContext *)v49, (const struct CVar *)v54) )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312)) != -1 )
        {
          v19 = CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312));
          v20 = 833545;
          LODWORD(v44) = 814;
          goto LABEL_58;
        }
        v21 = 814;
        v22 = 833545;
        goto LABEL_60;
      }
      goto LABEL_127;
    }
    v24 = v55 & 0xBFFF;
    if ( (v55 & 0xBFFF) == 1 || v24 == 8 || (v25 = 0, v24 == 8209) )
      v25 = 1;
    if ( (unsigned int)CContext::ArgFailed((CContext *)v49, v25) )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312)) != -1 )
        {
          v19 = CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312));
          v20 = 838665;
          LODWORD(v44) = 819;
          goto LABEL_58;
        }
        v21 = 819;
        v22 = 838665;
        goto LABEL_60;
      }
      goto LABEL_127;
    }
    v26 = (_WORD *)((char *)this + 112);
    if ( *((char *)this + 132) >= 0 || (v27 = 1, (unsigned __int16)(*v26 - 128) > 2u) )
      v27 = 0;
    if ( (unsigned int)CContext::OpFailed((CContext *)v49, v27) )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312)) != -1 )
        {
          v19 = CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312));
          v20 = 843785;
          LODWORD(v44) = 824;
          goto LABEL_58;
        }
        v21 = 824;
        v22 = 843785;
        goto LABEL_60;
      }
LABEL_124:
      if ( (bidGblFlags & 2) != 0 && off_18012A600[0] )
      {
        v41 = v50;
        v42 = CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312));
        LODWORD(v44) = v41;
        bidTraceW(off_18012A1F0[0], 925696, off_18012A600[0], v42, v44);
      }
      goto LABEL_127;
    }
    Stream = CRsetOptionalInterface<IRowsetChange,&_GUID const IID_IRowsetChange>::HRCheck((char *)v16 + 408);
    if ( (unsigned int)CContext::FailedDescription((CContext *)v49, &Stream, 0x271Cu) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_124;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312)) != -1 )
      {
        v19 = CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312));
        v20 = 846857;
        LODWORD(v44) = 827;
        goto LABEL_58;
      }
      v21 = 827;
      v22 = 846857;
      goto LABEL_60;
    }
    v28 = v55 & 0xBFFF;
    if ( (v55 & 0xBFFF) == 8 )
    {
      v29 = v56;
      if ( *v26 == 129 )
      {
        Stream = CSysString::ToAnsiAlloc(v56, (char **)&bstrString);
        if ( (unsigned int)CContext::Failed((CContext *)v49, &Stream) )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312)) == -1 )
            {
              bidTraceW(off_18012A1F0[0], 856073, L"<CRsetField::AppendChunk|ADO|ERR>  line %d\n", 836);
            }
            else
            {
              v30 = CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312));
              LODWORD(v44) = 836;
              bidTraceW(off_18012A1F0[0], 856073, L"<CRsetField::AppendChunk|ADO|ERR> %u#, line %d\n", v30, v44);
            }
          }
          v15 = bstrString;
          goto LABEL_122;
        }
        v15 = bstrString;
        if ( bstrString )
        {
          v31 = -1;
          do
            ++v31;
          while ( *((_BYTE *)bstrString + v31) );
        }
        else
        {
          LODWORD(v31) = 0;
        }
        v32 = bstrString;
      }
      else
      {
        LODWORD(v31) = 2 * CSysString::GetLength(v56, 0);
        if ( (*((_BYTE *)v29 + 8) & 4) != 0 )
          v32 = *(BSTR *)v29;
        else
          v32 = 0;
      }
    }
    else
    {
      if ( v28 != 8209 )
      {
        if ( v28 == 1 )
        {
          if ( *v26 != 128 )
          {
            CSysString::CSysString((CSysString *)&pvarg, qword_1800F3508, 3u);
            if ( (unsigned int)CContext::StringFailed((CContext *)v49, (const struct CSysString *)&pvarg) )
            {
              if ( (bidGblFlags & 2) != 0 )
              {
                if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312)) == -1 )
                {
                  bidTraceW(off_18012A1F0[0], 900105, L"<CRsetField::AppendChunk|ADO|ERR>  line %d\n", 879);
                }
                else
                {
                  v39 = CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312));
                  LODWORD(v44) = 879;
                  bidTraceW(off_18012A1F0[0], 900105, L"<CRsetField::AppendChunk|ADO|ERR> %u#, line %d\n", v39, v44);
                }
              }
              CSysString::~CSysString((CSysString *)&pvarg);
            }
            else
            {
              CVar::CVar((CVar *)v52, (const struct CSysString *)&pvarg, 3u);
              if ( (unsigned int)CContext::VariantFailed((CContext *)v49, (const struct CVar *)v52) )
              {
                if ( (bidGblFlags & 2) != 0 )
                {
                  if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312)) == -1 )
                  {
                    bidTraceW(off_18012A1F0[0], 903177, L"<CRsetField::AppendChunk|ADO|ERR>  line %d\n", 882);
                  }
                  else
                  {
                    v40 = CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312));
                    LODWORD(v44) = 882;
                    bidTraceW(off_18012A1F0[0], 903177, L"<CRsetField::AppendChunk|ADO|ERR> %u#, line %d\n", v40, v44);
                  }
                }
              }
              else
              {
                CVar::UpdateVariant((CVar *)v52);
                v51 = v53;
                Stream = CRsetField::SetValue(this, &v51);
                CContext::Failed((CContext *)v49, &Stream);
              }
              v52[0] = &CVar::`vftable';
              CVar::Clear((CVar *)v52);
              CSysString::~CSysString((CSysString *)&pvarg);
            }
            goto LABEL_124;
          }
          rgsabound = 0;
          memset(&pvarg, 0, sizeof(pvarg));
          v38 = SafeArrayCreate(0x11u, 1u, &rgsabound);
          if ( !(unsigned int)CContext::MemFailed((CContext *)v49, v38) )
          {
            VariantInit(&pvarg);
            pvarg.llVal = (LONGLONG)v38;
            pvarg.vt = 8209;
            v51 = pvarg;
            Stream = CRsetField::SetValue(this, &v51);
            CContext::Failed((CContext *)v49, &Stream);
            VariantClear(&pvarg);
            goto LABEL_124;
          }
          if ( (bidGblFlags & 2) != 0 )
          {
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312)) != -1 )
            {
              v19 = CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312));
              v20 = 888841;
              LODWORD(v44) = 868;
              goto LABEL_58;
            }
            v21 = 868;
            v22 = 888841;
            goto LABEL_60;
          }
          goto LABEL_124;
        }
        CContext::ArgFailed((CContext *)v49, 0);
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_124;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312)) != -1 )
        {
          v19 = CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312));
          v20 = 912393;
          LODWORD(v44) = 891;
          goto LABEL_58;
        }
        v36 = 891;
        v37 = 912393;
        goto LABEL_121;
      }
      v31 = (__int64)v56;
      v32 = (BSTR)CSafeArray::Lock(v56);
      LODWORD(v31) = CSafeArray::cDim((CSafeArray *)v31, v33);
    }
    Stream = CRecordset::GetStream(v16, *((_QWORD *)this + 13), 1u, (struct ISequentialStream **)&pvarg);
    if ( (unsigned int)CContext::Failed((CContext *)v49, &Stream) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_122;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312)) != -1 )
      {
        v34 = CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312));
        v35 = 916489;
        LODWORD(v44) = 895;
LABEL_89:
        bidTraceW(off_18012A1F0[0], v35, L"<CRsetField::AppendChunk|ADO|ERR> %u#, line %d\n", v34, v44);
        goto LABEL_122;
      }
      v36 = 895;
      v37 = 916489;
    }
    else
    {
      Stream = (*(__int64 (__fastcall **)(_QWORD, BSTR, _QWORD, _QWORD))(**(_QWORD **)&pvarg.vt + 32LL))(
                 *(_QWORD *)&pvarg.vt,
                 v32,
                 (unsigned int)v31,
                 0);
      if ( !(unsigned int)CContext::Failed((CContext *)v49, &Stream) || (bidGblFlags & 2) == 0 )
      {
LABEL_122:
        if ( v15 )
          SysFreeString(v15);
        goto LABEL_124;
      }
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312)) != -1 )
      {
        v34 = CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312));
        v35 = 919561;
        LODWORD(v44) = 898;
        goto LABEL_89;
      }
      v36 = 898;
      v37 = 919561;
    }
LABEL_121:
    bidTraceW(off_18012A1F0[0], v37, L"<CRsetField::AppendChunk|ADO|ERR>  line %d\n", v36);
    goto LABEL_122;
  }
  if ( (bidGblFlags & 2) != 0 )
  {
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312)) != -1 )
    {
      v19 = CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312));
      v20 = 829449;
      LODWORD(v44) = 810;
      goto LABEL_58;
    }
    v21 = 810;
    v22 = 829449;
LABEL_60:
    bidTraceW(off_18012A1F0[0], v22, L"<CRsetField::AppendChunk|ADO|ERR>  line %d\n", v21);
    goto LABEL_124;
  }
LABEL_127:
  if ( (bidGblFlags & 4) != 0 && v48 != -1 && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *))off_180121248[0])(bidID, 0, 0, &v48);
  v12 = v50;
  v54[0] = &CVar::`vftable';
  CVar::Clear((CVar *)v54);
LABEL_132:
  CXLockContext::~CXLockContext((CXLockContext *)v49);
  return v12;
}

```

## disassembly

```asm
0x180094000  mov     [rsp-8+arg_8], rbx
0x180094005  push    rbp
0x180094006  push    rsi
0x180094007  push    rdi
0x180094008  push    r12
0x18009400a  push    r13
0x18009400c  push    r14
0x18009400e  push    r15
0x180094010  lea     rbp, [rsp-10h]
0x180094015  sub     rsp, 110h
0x18009401c  mov     r8, [rcx+40h]
0x180094020  lea     rsi, [rcx+8]
0x180094024  mov     rax, rcx
0x180094027  mov     r14, rdx
0x18009402a  neg     rax
0x18009402d  mov     rdi, rcx
0x180094030  lea     rcx, [rsp+140h+var_E8]; this
0x180094035  sbb     rbx, rbx
0x180094038  add     r8, 8; struct CCriticalSection **
0x18009403c  and     rbx, rsi
0x18009403f  mov     rdx, rbx; struct CStdComObjectRoot *
0x180094042  call    ??0CXLockContext@@QEAA@PEAVCStdComObjectRoot@@PEAPEAVCCriticalSection@@PEBD@Z; CXLockContext::CXLockContext(CStdComObjectRoot *,CCriticalSection * *,char const *)
0x180094047  mov     rdx, rbx; struct CStdComObjectRoot *
0x18009404a  lea     rcx, [rsp+140h+var_E8]; this
0x18009404f  call    ?IsZombied@CContext@@QEAAHPEAVCStdComObjectRoot@@@Z; CContext::IsZombied(CStdComObjectRoot *)
0x180094054  xor     r12d, r12d
0x180094057  test    eax, eax
0x180094059  jz      short loc_1800940A1
0x18009405b  test    byte ptr cs:_bidGblFlags, 2
0x180094062  jz      loc_180094125
0x180094068  lea     rcx, [rdi+138h]; this
0x18009406f  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180094074  cmp     eax, 0FFFFFFFFh
0x180094077  jz      short loc_180094094
0x180094079  lea     rcx, [rdi+138h]; this
0x180094080  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180094085  mov     edx, 0C6C09h
0x18009408a  mov     [rsp+140h+var_120], 31Bh
0x180094092  jmp     short loc_1800940EF
0x180094094  mov     r9d, 31Bh
0x18009409a  mov     edx, 0C6C09h
0x18009409f  jmp     short loc_180094112
0x1800940a1  cmp     [rdi+0A8h], r12
0x1800940a8  lea     rcx, [rsp+140h+var_E8]; this
0x1800940ad  mov     edx, r12d
0x1800940b0  setnz   dl; int
0x1800940b3  call    ?FailIfClosed@CContext@@QEAAHH@Z; CContext::FailIfClosed(int)
0x1800940b8  test    eax, eax
0x1800940ba  jz      short loc_18009412D
0x1800940bc  test    byte ptr cs:_bidGblFlags, 2
0x1800940c3  jz      short loc_180094125
0x1800940c5  lea     rcx, [rdi+138h]; this
0x1800940cc  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800940d1  cmp     eax, 0FFFFFFFFh
0x1800940d4  jz      short loc_180094107
0x1800940d6  lea     rcx, [rdi+138h]; this
0x1800940dd  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800940e2  mov     edx, 0C7009h
0x1800940e7  mov     [rsp+140h+var_120], 31Ch
0x1800940ef  mov     rcx, cs:off_18012A1F0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800940f6  lea     r8, aCrsetfieldAppe_0; "<CRsetField::AppendChunk|ADO|ERR> %u#, "...
0x1800940fd  mov     r9d, eax
0x180094100  call    _bidTraceW
0x180094105  jmp     short loc_180094125
0x180094107  mov     r9d, 31Ch
0x18009410d  mov     edx, 0C7009h
0x180094112  mov     rcx, cs:off_18012A1F0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180094119  lea     r8, aCrsetfieldAppe; "<CRsetField::AppendChunk|ADO|ERR>  line"...
0x180094120  call    _bidTraceW
0x180094125  mov     ebx, [rbp+40h+var_C0]
0x180094128  jmp     loc_180094AF3
0x18009412d  xor     r9d, r9d; int
0x180094130  lea     rcx, [rbp+40h+var_60]; this
0x180094134  mov     r8b, 4; unsigned __int8
0x180094137  mov     rdx, r14; struct tagVARIANT *
0x18009413a  call    ??0CVar@@QEAA@AEBUtagVARIANT@@EH@Z; CVar::CVar(tagVARIANT const &,uchar,int)
0x18009413f  mov     rcx, [rsi+20h]
0x180094143  cmp     rsi, rcx
0x180094146  mov     [rsp+140h+bstrString], r12
0x18009414b  mov     rsi, r12
0x18009414e  mov     qword ptr [rsp+140h+pvarg], r12
0x180094153  cmovz   rcx, r12
0x180094157  mov     [rsp+140h+var_F0], 0FFFFFFFFFFFFFFFFh
0x180094160  lea     rax, [rcx-20h]
0x180094164  neg     rcx
0x180094167  sbb     r15, r15
0x18009416a  and     r15, rax
0x18009416d  test    byte ptr cs:_bidGblFlags, 4
0x180094174  jz      short loc_1800941B9
0x180094176  mov     rax, cs:off_18012AB68; "<CRsetField::AppendChunk|API|ADO> %u#, "...
0x18009417d  test    rax, rax
0x180094180  jz      short loc_1800941B9
0x180094182  lea     rcx, [rdi+138h]; this
0x180094189  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18009418e  movups  xmm0, xmmword ptr [r14]
0x180094192  lea     r9, [rbp+40h+var_B0]
0x180094196  mov     rdx, cs:off_18012AB68; "<CRsetField::AppendChunk|API|ADO> %u#, "...
0x18009419d  movsd   xmm1, qword ptr [r14+10h]
0x1800941a3  lea     rcx, [rsp+140h+var_F0]
0x1800941a8  mov     r8d, eax
0x1800941ab  movaps  xmmword ptr [rbp+40h+var_B0], xmm0
0x1800941af  movsd   qword ptr [rbp+40h+var_B0+10h], xmm1
0x1800941b4  call    _bidScopeEnterW
0x1800941b9  lea     rdx, [rbp+40h+arg_0]; __int16 *
0x1800941bd  mov     word ptr [rbp+40h+arg_0], r12w
0x1800941c2  mov     rcx, r15; this
0x1800941c5  mov     word ptr [rbp+40h+rgsabound.cElements], r12w
0x1800941ca  call    ?_get_EOF@CRecordset@@QEAAJPEAF@Z; CRecordset::_get_EOF(short *)
0x1800941cf  lea     rdx, [rbp+40h+arg_18]; int *
0x1800941d3  mov     [rbp+40h+arg_18], eax
0x1800941d6  lea     rcx, [rsp+140h+var_E8]; this
0x1800941db  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800941e0  lea     r14, ??_7CVar@@6B@; const CVar::`vftable'
0x1800941e7  test    eax, eax
0x1800941e9  jz      short loc_18009425F
0x1800941eb  test    byte ptr cs:_bidGblFlags, 2
0x1800941f2  jz      loc_180094AAF
0x1800941f8  lea     rbx, [rdi+138h]
0x1800941ff  mov     rcx, rbx; this
0x180094202  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180094207  cmp     eax, 0FFFFFFFFh
0x18009420a  jz      short loc_18009423C
0x18009420c  mov     rcx, rbx; this
0x18009420f  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180094214  mov     edx, 0CA409h
0x180094219  mov     [rsp+140h+var_120], 329h
0x180094221  mov     rcx, cs:off_18012A1F0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180094228  lea     r8, aCrsetfieldAppe_0; "<CRsetField::AppendChunk|ADO|ERR> %u#, "...
0x18009422f  mov     r9d, eax
0x180094232  call    _bidTraceW
0x180094237  jmp     loc_180094A6C
0x18009423c  mov     r9d, 329h
0x180094242  mov     edx, 0CA409h
0x180094247  mov     rcx, cs:off_18012A1F0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18009424e  lea     r8, aCrsetfieldAppe; "<CRsetField::AppendChunk|ADO|ERR>  line"...
0x180094255  call    _bidTraceW
0x18009425a  jmp     loc_180094A6C
0x18009425f  lea     rdx, [rbp+40h+rgsabound]; __int16 *
0x180094263  mov     rcx, r15; this
0x180094266  call    ?_get_BOF@CRecordset@@QEAAJPEAF@Z; CRecordset::_get_BOF(short *)
0x18009426b  lea     rdx, [rbp+40h+arg_18]; int *
0x18009426f  mov     [rbp+40h+arg_18], eax
0x180094272  lea     rcx, [rsp+140h+var_E8]; this
0x180094277  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18009427c  test    eax, eax
0x18009427e  jz      short loc_1800942CB
0x180094280  test    byte ptr cs:_bidGblFlags, 2
0x180094287  jz      loc_180094AAF
0x18009428d  lea     rbx, [rdi+138h]
0x180094294  mov     rcx, rbx; this
0x180094297  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18009429c  cmp     eax, 0FFFFFFFFh
0x18009429f  jz      short loc_1800942BB
0x1800942a1  mov     rcx, rbx; this
0x1800942a4  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800942a9  mov     edx, 0CA809h
0x1800942ae  mov     [rsp+140h+var_120], 32Ah
0x1800942b6  jmp     loc_180094221
0x1800942bb  mov     r9d, 32Ah
0x1800942c1  mov     edx, 0CA809h
0x1800942c6  jmp     loc_180094247
0x1800942cb  mov     r13d, 1
0x1800942d1  cmp     word ptr [rbp+40h+arg_0], r12w
0x1800942d6  jnz     short loc_1800942E2
0x1800942d8  mov     edx, r13d
0x1800942db  cmp     word ptr [rbp+40h+rgsabound.cElements], r12w
0x1800942e0  jz      short loc_1800942E5
0x1800942e2  mov     edx, r12d; int
0x1800942e5  lea     rcx, [rsp+140h+var_E8]; this
0x1800942ea  call    ?RecordFailed@CContext@@QEAAHH@Z; CContext::RecordFailed(int)
0x1800942ef  test    eax, eax
0x1800942f1  jz      short loc_18009433E
0x1800942f3  test    byte ptr cs:_bidGblFlags, 2
0x1800942fa  jz      loc_180094AAF
0x180094300  lea     rbx, [rdi+138h]
0x180094307  mov     rcx, rbx; this
0x18009430a  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18009430f  cmp     eax, 0FFFFFFFFh
0x180094312  jz      short loc_18009432E
0x180094314  mov     rcx, rbx; this
0x180094317  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18009431c  mov     edx, 0CAC09h
0x180094321  mov     [rsp+140h+var_120], 32Bh
0x180094329  jmp     loc_180094221
0x18009432e  mov     r9d, 32Bh
0x180094334  mov     edx, 0CAC09h
0x180094339  jmp     loc_180094247
0x18009433e  lea     rdx, [rbp+40h+var_60]; struct CVar *
0x180094342  lea     rcx, [rsp+140h+var_E8]; this
0x180094347  call    ?VariantFailed@CContext@@QEAAHAEBVCVar@@@Z; CContext::VariantFailed(CVar const &)
0x18009434c  test    eax, eax
0x18009434e  jz      short loc_18009439B
0x180094350  test    byte ptr cs:_bidGblFlags, 2
0x180094357  jz      loc_180094AAF
0x18009435d  lea     rbx, [rdi+138h]
0x180094364  mov     rcx, rbx; this
0x180094367  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18009436c  cmp     eax, 0FFFFFFFFh
0x18009436f  jz      short loc_18009438B
0x180094371  mov     rcx, rbx; this
0x180094374  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180094379  mov     edx, 0CB809h
0x18009437e  mov     [rsp+140h+var_120], 32Eh
0x180094386  jmp     loc_180094221
0x18009438b  mov     r9d, 32Eh
0x180094391  mov     edx, 0CB809h
0x180094396  jmp     loc_180094247
0x18009439b  movzx   eax, [rbp+40h+var_50]
0x18009439f  mov     ecx, 0BFFFh
0x1800943a4  and     ax, cx
0x1800943a7  mov     ecx, 2011h
0x1800943ac  cmp     ax, r13w
0x1800943b0  jz      short loc_1800943C4
0x1800943b2  mov     edx, 8
0x1800943b7  cmp     ax, dx
0x1800943ba  jz      short loc_1800943C4
0x1800943bc  mov     edx, r12d
0x1800943bf  cmp     ax, cx
0x1800943c2  jnz     short loc_1800943C7
0x1800943c4  mov     edx, r13d; int
0x1800943c7  lea     rcx, [rsp+140h+var_E8]; this
0x1800943cc  call    ?ArgFailed@CContext@@QEAAHH@Z; CContext::ArgFailed(int)
0x1800943d1  test    eax, eax
0x1800943d3  jz      short loc_180094420
0x1800943d5  test    byte ptr cs:_bidGblFlags, 2
0x1800943dc  jz      loc_180094AAF
0x1800943e2  lea     rbx, [rdi+138h]
0x1800943e9  mov     rcx, rbx; this
0x1800943ec  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800943f1  cmp     eax, 0FFFFFFFFh
0x1800943f4  jz      short loc_180094410
0x1800943f6  mov     rcx, rbx; this
0x1800943f9  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800943fe  mov     edx, 0CCC09h
0x180094403  mov     [rsp+140h+var_120], 333h
0x18009440b  jmp     loc_180094221
0x180094410  mov     r9d, 333h
0x180094416  mov     edx, 0CCC09h
0x18009441b  jmp     loc_180094247
0x180094420  mov     r14d, 80h
0x180094426  lea     rbx, [rdi+70h]
0x18009442a  test    [rdi+84h], r14b
0x180094431  jz      short loc_180094443
0x180094433  movzx   eax, word ptr [rbx]
0x180094436  mov     edx, r13d
0x180094439  sub     ax, r14w
0x18009443d  cmp     ax, 2
0x180094441  jbe     short loc_180094446
0x180094443  mov     edx, r12d; int
0x180094446  lea     rcx, [rsp+140h+var_E8]; this
0x18009444b  call    ?OpFailed@CContext@@QEAAHH@Z; CContext::OpFailed(int)
0x180094450  test    eax, eax
0x180094452  jz      short loc_1800944C8
0x180094454  test    byte ptr cs:_bidGblFlags, 2
0x18009445b  jz      loc_180094A65
0x180094461  lea     rbx, [rdi+138h]
0x180094468  mov     rcx, rbx; this
0x18009446b  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180094470  cmp     eax, 0FFFFFFFFh
0x180094473  jz      short loc_1800944A5
0x180094475  mov     rcx, rbx; this
0x180094478  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18009447d  mov     edx, 0CE009h
0x180094482  mov     [rsp+140h+var_120], 338h
0x18009448a  mov     rcx, cs:off_18012A1F0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180094491  lea     r8, aCrsetfieldAppe_0; "<CRsetField::AppendChunk|ADO|ERR> %u#, "...
0x180094498  mov     r9d, eax
0x18009449b  call    _bidTraceW
0x1800944a0  jmp     loc_180094A65
0x1800944a5  mov     r9d, 338h
0x1800944ab  mov     edx, 0CE009h
0x1800944b0  mov     rcx, cs:off_18012A1F0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800944b7  lea     r8, aCrsetfieldAppe; "<CRsetField::AppendChunk|ADO|ERR>  line"...
0x1800944be  call    _bidTraceW
0x1800944c3  jmp     loc_180094A65
0x1800944c8  lea     rcx, [r15+198h]
0x1800944cf  call    ?HRCheck@?$CRsetOptionalInterface@UIRowsetChange@@$1?IID_IRowsetChange@@3U_GUID@@B@@QEAAJXZ; CRsetOptionalInterface<IRowsetChange,&_GUID const IID_IRowsetChange>::HRCheck(void)
0x1800944d4  mov     r8d, 271Ch; unsigned int
0x1800944da  mov     [rbp+40h+arg_0], eax
0x1800944dd  lea     rdx, [rbp+40h+arg_0]; int *
0x1800944e1  lea     rcx, [rsp+140h+var_E8]; this
0x1800944e6  call    ?FailedDescription@CContext@@QEAAHAEBJK@Z; CContext::FailedDescription(long const &,ulong)
0x1800944eb  test    eax, eax
0x1800944ed  jz      short loc_18009453A
0x1800944ef  test    byte ptr cs:_bidGblFlags, 2
0x1800944f6  jz      loc_180094A65
0x1800944fc  lea     rbx, [rdi+138h]
0x180094503  mov     rcx, rbx; this
0x180094506  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18009450b  cmp     eax, 0FFFFFFFFh
0x18009450e  jz      short loc_18009452A
0x180094510  mov     rcx, rbx; this
0x180094513  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180094518  mov     edx, 0CEC09h
0x18009451d  mov     [rsp+140h+var_120], 33Bh
0x180094525  jmp     loc_18009448A
0x18009452a  mov     r9d, 33Bh
0x180094530  mov     edx, 0CEC09h
0x180094535  jmp     loc_1800944B0
0x18009453a  movzx   eax, [rbp+40h+var_50]
  ... truncated ...
```
