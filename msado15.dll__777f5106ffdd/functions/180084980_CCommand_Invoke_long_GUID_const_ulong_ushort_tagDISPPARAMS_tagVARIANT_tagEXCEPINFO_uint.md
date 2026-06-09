# CCommand::Invoke(long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x180084980`
- end: `0x180085da1`
- name: `?Invoke@CCommand@@UEAAJJAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `5153`
- prototype: `int(CCommand *__hidden this, int, const struct _GUID *, unsigned int, unsigned __int16, struct tagDISPPARAMS *, struct tagVARIANT *, struct tagEXCEPINFO *, unsigned int *)`
- caller_count: `2`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180085db0`
- `0x180085dc0`

## callees

- `0x180009240`
- `0x180020e50`
- `0x180023090`
- `0x180023180`
- `0x180027790`
- `0x18004f1b0`
- `0x180053098`
- `0x18006a22c`
- `0x18007f6d0`
- `0x1800848e0`
- `0x180084980`
- `0x180087eb0`
- `0x1800c8f34`
- `0x1800cb55c`
- `0x1800cdb20`
- `0x1800d0010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180085902`
- `OLEAUT32!__imp_VariantInit` at `0x180085902`

## string_xrefs

- `0x180084a4e`: `<CCommand::Invoke|ADO|ERR> %u#, line %d\n`
- `0x180084bc2`: `<CCommand::Invoke|ADO|ERR> %u#, line %d\n`
- `0x18008521f`: `<CCommand::Invoke|ADO|ERR> %u#, line %d\n`
- `0x180084a76`: `<CCommand::Invoke|ADO|ERR>  line %d\n`
- `0x180085175`: `<CCommand::Invoke|ADO|ERR>  line %d\n`
- `0x180085245`: `<CCommand::Invoke|ADO|ERR>  line %d\n`

## pseudocode

```c
__int64 __fastcall CCommand::Invoke(
        CCommand *this,
        int a2,
        const struct _GUID *a3,
        unsigned int a4,
        unsigned __int16 a5,
        struct tagDISPPARAMS *a6,
        struct tagVARIANT *pvarg,
        struct tagEXCEPINFO *a8,
        unsigned int *a9)
{
  int v13; // eax
  __int64 v14; // rcx
  bool v15; // r9
  unsigned int BidObjectID; // eax
  __int64 v17; // rdx
  __int64 v18; // rcx
  CStdComObjectRoot *v19; // rcx
  CStdComObjectRoot *v20; // rcx
  unsigned int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // r9
  __int64 v24; // rdx
  __int64 (__fastcall *v25)(CCommand *, LONGLONG, __int64, _QWORD, int, struct tagVARIANT *, ULONG *); // r11
  int v26; // r9d
  int *v27; // rax
  unsigned int v28; // ecx
  unsigned int *v29; // rax
  __int64 Lo; // r8
  CY *p_cyVal; // rax
  LONGLONG llVal; // rdx
  union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *p_llVal; // rax
  int Item; // eax
  const int *p_scode; // rdx
  __int64 v36; // r9
  unsigned int *v37; // rax
  struct tagVARIANT *v38; // r8
  LONGLONG v39; // rdx
  int v40; // eax
  struct tagVARIANT *v41; // rdx
  __int64 (__fastcall *v42)(CCommand *, ULONG *); // rax
  __int64 (__fastcall *v43)(CCommand *, _QWORD); // rax
  USHORT *p_uiVal; // rdx
  int v45; // eax
  __int64 (__fastcall *v46)(CCommand *, _QWORD); // rax
  CY *pcyVal; // rdx
  __int64 (__fastcall *v48)(CCommand *, LONGLONG); // rax
  union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *v49; // rdx
  unsigned int v50; // eax
  __int64 v51; // rdx
  __int64 v52; // r9
  __int64 v53; // rdx
  int v54; // eax
  CStdComObjectRoot *v55; // rcx
  CContext *v56; // rcx
  unsigned int v57; // ebx
  unsigned int *v59; // [rsp+20h] [rbp-E0h]
  unsigned int *v60; // [rsp+20h] [rbp-E0h]
  unsigned __int16 v61[4]; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v62; // [rsp+58h] [rbp-A8h]
  unsigned int v63; // [rsp+60h] [rbp-A0h] BYREF
  struct tagVARIANT *v64; // [rsp+68h] [rbp-98h] BYREF
  struct tagVARIANT v65; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v66[32]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v67; // [rsp+B0h] [rbp-50h]
  unsigned int v68; // [rsp+B8h] [rbp-48h]
  struct tagVARIANT v69; // [rsp+C0h] [rbp-40h] BYREF
  char v70; // [rsp+D9h] [rbp-27h]
  struct tagVARIANT v71; // [rsp+E0h] [rbp-20h] BYREF
  char v72; // [rsp+F9h] [rbp-7h]
  __int16 v73; // [rsp+100h] [rbp+0h]
  _QWORD v74[2]; // [rsp+108h] [rbp+8h] BYREF
  char v75; // [rsp+119h] [rbp+19h]
  __int16 v76; // [rsp+120h] [rbp+20h]
  int *v77; // [rsp+128h] [rbp+28h] BYREF
  char v78; // [rsp+139h] [rbp+39h]
  struct tagVARIANT v79; // [rsp+140h] [rbp+40h]

  *(_QWORD *)v61 = a9;
  v64 = pvarg;
  v67 = ((unsigned __int64)this + 32) & -(__int64)(this != 0);
  CContext::Init((CContext *)v66);
  v63 = 0;
  v13 = CContext::ArgFailed((CContext *)v66, a6 != 0);
  v15 = 0;
  if ( v13 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144)) == -1 )
      {
        bidTraceW(off_18012A1E0[0], 274441, L"<CCommand::Invoke|ADO|ERR>  line %d\n", 268);
      }
      else
      {
        BidObjectID = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
        bidTraceW(off_18012A1E0[0], 274441, L"<CCommand::Invoke|ADO|ERR> %u#, line %d\n", BidObjectID, 268);
      }
    }
    goto LABEL_227;
  }
  v17 = a5;
  if ( a6->cNamedArgs && (a5 & 4) == 0 || a2 > 500 )
    goto LABEL_218;
  if ( a2 == 500 )
  {
    if ( (a5 & 2) != 0 )
    {
      if ( !a6->cArgs )
      {
        *(_DWORD *)v61 = CStdComObjectRoot::PrepareInvokeArgsAndResult(
                           (CStdComObjectRoot *)v14,
                           a6,
                           (struct CStdComObjectRoot::INVOKE_ARG *)&v69,
                           0,
                           &v63,
                           &v64,
                           9u);
        if ( CContext::FailedInvoke((CContext *)v66, (const int *)v61, a8, 0) )
          goto LABEL_225;
        v41 = v64;
        v42 = *(__int64 (__fastcall **)(CCommand *, ULONG *))(*(_QWORD *)this + 56LL);
        goto LABEL_69;
      }
      v14 = 1;
      if ( a6->cArgs == 1 )
      {
        v61[0] = 12;
        v63 = 1;
        *(_DWORD *)v61 = CStdComObjectRoot::PrepareInvokeArgsAndResult(
                           (CStdComObjectRoot *)1,
                           a6,
                           (struct CStdComObjectRoot::INVOKE_ARG *)&v69,
                           v61,
                           &v63,
                           &v64,
                           9u);
        if ( CContext::FailedInvoke((CContext *)v66, (const int *)v61, a8, 0) )
          goto LABEL_225;
        v65 = v69;
        Item = CQdefProperties::get_Item((CCommand *)((char *)this + 232), &v65, (struct ADOProperty **)&v64->llVal);
        goto LABEL_46;
      }
    }
    if ( (a5 & 4) == 0 || a6->cArgs != 2 )
      goto LABEL_79;
    *(_DWORD *)v61 = 786444;
    v63 = 2;
    *(_DWORD *)v61 = CStdComObjectRoot::PrepareInvokeArgs(
                       (CStdComObjectRoot *)v14,
                       a6,
                       (struct CStdComObjectRoot::INVOKE_ARG *)&v69,
                       v61,
                       2u);
    if ( CContext::FailedInvoke((CContext *)v66, (const int *)v61, a8, 0) )
      goto LABEL_226;
    v65 = v69;
    v64 = 0;
    *(_DWORD *)v61 = CQdefProperties::get_Item((CCommand *)((char *)this + 232), &v65, (struct ADOProperty **)&v64);
    if ( CContext::FailedInvoke((CContext *)v66, (const int *)v61, a8, 0) )
      goto LABEL_226;
    v65 = v71;
    v54 = (*(__int64 (__fastcall **)(struct tagVARIANT *, struct tagVARIANT *))(*(_QWORD *)&v64->vt + 64LL))(v64, &v65);
    goto LABEL_134;
  }
  if ( a2 <= 7 )
  {
    if ( a2 == 7 )
    {
      if ( (a5 & 2) != 0 && !a6->cArgs )
      {
        *(_DWORD *)v61 = CStdComObjectRoot::PrepareInvokeArgsAndResult(
                           (CStdComObjectRoot *)v14,
                           a6,
                           (struct CStdComObjectRoot::INVOKE_ARG *)&v69,
                           0,
                           &v63,
                           &v64,
                           3u);
        if ( !CContext::FailedInvoke((CContext *)v66, (const int *)v61, a8, 0) )
        {
          v41 = v64;
          if ( v64 )
          {
            v42 = *(__int64 (__fastcall **)(CCommand *, ULONG *))(*(_QWORD *)this + 168LL);
            goto LABEL_69;
          }
        }
        goto LABEL_225;
      }
      if ( (a5 & 0xC) == 0 || a6->cArgs != 1 )
        goto LABEL_79;
      v63 = 1;
      v61[0] = 3;
      *(_DWORD *)v61 = CStdComObjectRoot::PrepareInvokeArgs(
                         (CStdComObjectRoot *)1,
                         a6,
                         (struct CStdComObjectRoot::INVOKE_ARG *)&v69,
                         v61,
                         1u);
      if ( CContext::FailedInvoke((CContext *)v66, (const int *)v61, a8, 0) )
        goto LABEL_226;
      v46 = *(__int64 (__fastcall **)(CCommand *, _QWORD))(*(_QWORD *)this + 160LL);
      goto LABEL_89;
    }
    v18 = (unsigned int)a2;
    if ( a2 )
    {
      if ( a2 != 1 )
      {
        if ( a2 != 2 )
        {
          if ( a2 != 3 )
          {
            if ( a2 != 4 )
            {
              v19 = (CStdComObjectRoot *)(unsigned int)(a2 - 5);
              if ( a2 != 5 )
              {
                if ( a2 == 6 )
                {
                  v62 = 2060;
                  *(_DWORD *)v61 = 134416392;
                  *(_DWORD *)&v61[2] = 134416387;
                  v63 = 5;
                  *(_DWORD *)v61 = CStdComObjectRoot::PrepareInvokeArgsAndResult(
                                     v19,
                                     a6,
                                     (struct CStdComObjectRoot::INVOKE_ARG *)&v69,
                                     v61,
                                     &v63,
                                     &v64,
                                     9u);
                  if ( CContext::FailedInvoke((CContext *)v66, (const int *)v61, a8, 0) )
                  {
                    if ( (bidGblFlags & 2) == 0 )
                      goto LABEL_225;
                    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144)) != -1 )
                    {
                      v21 = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
                      v22 = 364553;
                      LODWORD(v59) = 356;
LABEL_23:
                      bidTraceW(off_18012A1E0[0], v22, L"<CCommand::Invoke|ADO|ERR> %u#, line %d\n", v21, v59);
                      goto LABEL_225;
                    }
                    v23 = 356;
                    v24 = 364553;
                    goto LABEL_111;
                  }
                  v25 = *(__int64 (__fastcall **)(CCommand *, LONGLONG, __int64, _QWORD, int, struct tagVARIANT *, ULONG *))(*(_QWORD *)this + 144LL);
                  if ( v78 )
                  {
                    v26 = 0;
                  }
                  else
                  {
                    v27 = (int *)&v77;
                    if ( (v76 & 0x4000) != 0 )
                      v27 = v77;
                    v26 = *v27;
                  }
                  if ( v75 )
                  {
                    v28 = 1;
                  }
                  else
                  {
                    v29 = (unsigned int *)v74;
                    if ( (v73 & 0x4000) != 0 )
                      v29 = (unsigned int *)v74[0];
                    v28 = *v29;
                  }
                  if ( v72 )
                  {
                    Lo = 0;
                  }
                  else
                  {
                    p_cyVal = &v71.cyVal;
                    if ( (v71.vt & 0x4000) != 0 )
                      p_cyVal = v71.pcyVal;
                    Lo = p_cyVal->Lo;
                  }
                  if ( v70 )
                  {
                    llVal = 0;
                  }
                  else
                  {
                    p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&v69.llVal;
                    if ( (v69.vt & 0x4000) != 0 )
                      p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)v69.llVal;
                    llVal = p_llVal->llVal;
                  }
                  v65 = v79;
                  Item = v25(this, llVal, Lo, v28, v26, &v65, (ULONG *)&v64->cyVal);
                  goto LABEL_46;
                }
                goto LABEL_218;
              }
              v61[2] = 2051;
              *(_DWORD *)v61 = 135022604;
              v63 = 3;
              *(_DWORD *)v61 = CStdComObjectRoot::PrepareInvokeArgsAndResult(
                                 v19,
                                 a6,
                                 (struct CStdComObjectRoot::INVOKE_ARG *)&v69,
                                 v61,
                                 &v63,
                                 &v64,
                                 9u);
              if ( CContext::FailedInvoke((CContext *)v66, (const int *)v61, a8, 0) )
              {
                if ( (bidGblFlags & 2) == 0 )
                  goto LABEL_225;
                if ( (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144)) != -1 )
                {
                  v21 = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
                  v22 = 394249;
                  LODWORD(v59) = 385;
                  goto LABEL_23;
                }
                v23 = 385;
                v24 = 394249;
                goto LABEL_111;
              }
              if ( v75 )
              {
                v36 = 0xFFFFFFFFLL;
              }
              else
              {
                v37 = (unsigned int *)v74;
                if ( (v73 & 0x4000) != 0 )
                  v37 = (unsigned int *)v74[0];
                v36 = *v37;
              }
              v38 = &v71;
              v39 = v69.llVal;
              if ( v72 )
                v38 = 0;
              if ( v70 )
                v39 = 0;
              v40 = (*(__int64 (__fastcall **)(CCommand *, LONGLONG, struct tagVARIANT *, __int64, CY *))(*(_QWORD *)this + 136LL))(
                      this,
                      v39,
                      v38,
                      v36,
                      &v64->cyVal);
              goto LABEL_62;
            }
            if ( (a5 & 2) != 0 && !a6->cArgs )
            {
              *(_DWORD *)v61 = CStdComObjectRoot::PrepareInvokeArgsAndResult(
                                 (CStdComObjectRoot *)(unsigned int)(a2 - 4),
                                 a6,
                                 (struct CStdComObjectRoot::INVOKE_ARG *)&v69,
                                 0,
                                 &v63,
                                 &v64,
                                 0xBu);
              if ( !CContext::FailedInvoke((CContext *)v66, (const int *)v61, a8, 0) )
              {
                v41 = v64;
                if ( v64 )
                {
                  v42 = *(__int64 (__fastcall **)(CCommand *, ULONG *))(*(_QWORD *)this + 120LL);
LABEL_69:
                  Item = v42(this, (ULONG *)&v41->cyVal);
                  goto LABEL_46;
                }
              }
              goto LABEL_225;
            }
            if ( (a5 & 0xC) != 0 && a6->cArgs == 1 )
            {
              v63 = 1;
              v61[0] = 11;
              *(_DWORD *)v61 = CStdComObjectRoot::PrepareInvokeArgs(
                                 (CStdComObjectRoot *)1,
                                 a6,
                                 (struct CStdComObjectRoot::INVOKE_ARG *)&v69,
                                 v61,
                                 1u);
              if ( CContext::FailedInvoke((CContext *)v66, (const int *)v61, a8, 0) )
                goto LABEL_226;
              v43 = *(__int64 (__fastcall **)(CCommand *, _QWORD))(*(_QWORD *)this + 128LL);
              goto LABEL_75;
            }
            goto LABEL_79;
          }
          if ( (a5 & 2) != 0 && !a6->cArgs )
          {
            *(_DWORD *)v61 = CStdComObjectRoot::PrepareInvokeArgsAndResult(
                               (CStdComObjectRoot *)(unsigned int)(a2 - 3),
                               a6,
                               (struct CStdComObjectRoot::INVOKE_ARG *)&v69,
                               0,
                               &v63,
                               &v64,
                               3u);
            if ( !CContext::FailedInvoke((CContext *)v66, (const int *)v61, a8, 0) )
            {
              v41 = v64;
              if ( v64 )
              {
                v42 = *(__int64 (__fastcall **)(CCommand *, ULONG *))(*(_QWORD *)this + 104LL);
                goto LABEL_69;
              }
            }
LABEL_225:
            if ( !v63 )
              goto LABEL_227;
LABEL_226:
            CStdComObjectRoot::ClearInvokeArgs(v20, (struct CStdComObjectRoot::INVOKE_ARG *)&v69, v63);
            goto LABEL_227;
          }
          if ( (a5 & 0xC) == 0 || a6->cArgs != 1 )
            goto LABEL_79;
          v63 = 1;
          v61[0] = 3;
          *(_DWORD *)v61 = CStdComObjectRoot::PrepareInvokeArgs(
                             (CStdComObjectRoot *)1,
                             a6,
                             (struct CStdComObjectRoot::INVOKE_ARG *)&v69,
                             v61,
                             1u);
          if ( CContext::FailedInvoke((CContext *)v66, (const int *)v61, a8, 0) )
            goto LABEL_226;
          v46 = *(__int64 (__fastcall **)(CCommand *, _QWORD))(*(_QWORD *)this + 112LL);
LABEL_89:
          pcyVal = &v69.cyVal;
          if ( (v69.vt & 0x4000) != 0 )
            pcyVal = v69.pcyVal;
          v45 = v46(this, pcyVal->Lo);
          goto LABEL_78;
        }
        if ( (a5 & 2) != 0 && !a6->cArgs )
        {
          *(_DWORD *)v61 = CStdComObjectRoot::PrepareInvokeArgsAndResult(
                             (CStdComObjectRoot *)(unsigned int)(a2 - 2),
                             a6,
                             (struct CStdComObjectRoot::INVOKE_ARG *)&v69,
                             0,
                             &v63,
                             &v64,
                             8u);
          if ( !CContext::FailedInvoke((CContext *)v66, (const int *)v61, a8, 0) )
          {
            v41 = v64;
            if ( v64 )
            {
              v42 = *(__int64 (__fastcall **)(CCommand *, ULONG *))(*(_QWORD *)this + 88LL);
              goto LABEL_69;
            }
          }
          goto LABEL_225;
        }
        if ( (a5 & 0xC) == 0 || a6->cArgs != 1 )
          goto LABEL_79;
        v63 = 1;
        v61[0] = 8;
        *(_DWORD *)v61 = CStdComObjectRoot::PrepareInvokeArgs(
                           (CStdComObjectRoot *)1,
                           a6,
                           (struct CStdComObjectRoot::INVOKE_ARG *)&v69,
                           v61,
                           1u);
        if ( CContext::FailedInvoke((CContext *)v66, (const int *)v61, a8, 0) )
          goto LABEL_226;
        v48 = *(__int64 (__fastcall **)(CCommand *, LONGLONG))(*(_QWORD *)this + 96LL);
LABEL_101:
        v49 = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&v69.llVal;
        if ( (v69.vt & 0x4000) != 0 )
          v49 = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)v69.llVal;
        v45 = v48(this, v49->llVal);
        goto LABEL_78;
      }
      if ( (a5 & 2) != 0 )
      {
        *(_DWORD *)v61 = CStdComObjectRoot::PrepareInvokeArgsAndResult(
                           (CStdComObjectRoot *)(unsigned int)(a2 - 1),
                           a6,
                           (struct CStdComObjectRoot::INVOKE_ARG *)&v69,
                           0,
                           &v63,
                           &v64,
                           9u);
        if ( CContext::FailedInvoke((CContext *)v66, (const int *)v61, a8, 0) )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_225;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144)) != -1 )
          {
            v21 = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
            v22 = 286729;
            LODWORD(v59) = 280;
            goto LABEL_23;
          }
          v23 = 280;
          v24 = 286729;
          goto LABEL_111;
        }
        v41 = v64;
        v42 = *(__int64 (__fastcall **)(CCommand *, ULONG *))(*(_QWORD *)this + 64LL);
        goto LABEL_69;
      }
      if ( (a5 & 0xC) == 0 )
        goto LABEL_79;
      v61[0] = 12;
      v63 = 1;
      *(_DWORD *)v61 = CStdComObjectRoot::PrepareInvokeArgs(
                         (CStdComObjectRoot *)1,
                         a6,
                         (struct CStdComObjectRoot::INVOKE_ARG *)&v69,
                         v61,
                         1u);
      if ( CContext::FailedInvoke((CContext *)v66, (const int *)v61, a8, 0) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_226;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144)) != -1 )
        {
          v50 = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
          v51 = 297993;
          LODWORD(v60) = 291;
LABEL_118:
          bidTraceW(off_18012A1E0[0], v51, L"<CCommand::Invoke|ADO|ERR> %u#, line %d\n", v50, v60);
          goto LABEL_226;
        }
        v52 = 291;
        v53 = 297993;
        goto LABEL_120;
      }
      v65 = v69;
      v45 = (*(__int64 (__fastcall **)(CCommand *, struct tagVARIANT *))(*(_QWORD *)this + 80LL))(this, &v65);
      goto LABEL_78;
    }
    if ( (a5 & 2) != 0 )
    {
      if ( !a6->cArgs )
      {
        *(_DWORD *)v61 = CStdComObjectRoot::PrepareInvokeArgsAndResult(
                           (CStdComObjectRoot *)(unsigned int)a2,
                           a6,
                           (struct CStdComObjectRoot::INVOKE_ARG *)&v69,
                           0,
                           &v63,
                           &v64,
                           9u);
        if ( CContext::FailedInvoke((CContext *)v66, (const int *)v61, a8, 0) )
          goto LABEL_225;
        v41 = v64;
        v42 = *(__int64 (__fastcall **)(CCommand *, ULONG *))(*(_QWORD *)this + 152LL);
        goto LABEL_69;
      }
      v18 = 1;
      if ( a6->cArgs == 1 )
      {
        v61[0] = 12;
        v63 = 1;
        *(_DWORD *)v61 = CStdComObjectRoot::PrepareInvokeArgsAndResult(
                           (CStdComObjectRoot *)1,
                           a6,
                           (struct CStdComObjectRoot::INVOKE_ARG *)&v69,
                           v61,
                           &v63,
                           &v64,
                           9u);
        if ( CContext::FailedInvoke((CContext *)v66, (const int *)v61, a8, 0) )
          goto LABEL_225;
        v65 = v69;
        Item = CParameters::get_Item((CCommand *)((char *)this + 368), &v65, (struct _ADOParameter **)&v64->llVal);
        goto LABEL_46;
      }
    }
    if ( (a5 & 4) == 0 || a6->cArgs != 2 )
      goto LABEL_79;
    *(_DWORD *)v61 = 786444;
    v63 = 2;
    *(_DWORD *)v61 = CStdComObjectRoot::PrepareInvokeArgs(
                       (CStdComObjectRoot *)v18,
                       a6,
                       (struct CStdComObjectRoot::INVOKE_ARG *)&v69,
                       v61,
                       2u);
    if ( CContext::FailedInvoke((CContext *)v66, (const int *)v61, a8, 0) )
      goto LABEL_226;
    v65 = v69;
    v64 = 0;
    *(_DWORD *)v61 = CParameters::get_Item((CCommand *)((char *)this + 368), &v65, (struct _ADOParameter **)&v64);
    if ( CContext::FailedInvoke((CContext *)v66, (const int *)v61, a8, 0) )
      goto LABEL_226;
    v65 = v71;
    v54 = (*(__int64 (__fastcall **)(struct tagVARIANT *, struct tagVARIANT *))(*(_QWORD *)&v64->vt + 88LL))(v64, &v65);
LABEL_134:
    *(_DWORD *)v61 = v54;
    CContext::FailedInvoke((CContext *)v66, (const int *)v61, a8, 0);
    (*(void (__fastcall **)(struct tagVARIANT *))(*(_QWORD *)&v64->vt + 16LL))(v64);
    goto LABEL_226;
  }
  switch ( a2 )
  {
    case 8:
      if ( (a5 & 2) != 0 && !a6->cArgs )
      {
        *(_DWORD *)v61 = CStdComObjectRoot::PrepareInvokeArgsAndResult(
                           (CStdComObjectRoot *)(unsigned int)(a2 - 8),
                           a6,
                           (struct CStdComObjectRoot::INVOKE_ARG *)&v69,
                           0,
                           &v63,
                           &v64,
                           8u);
        if ( !CContext::FailedInvoke((CContext *)v66, (const int *)v61, a8, 0) )
        {
          v41 = v64;
          if ( v64 )
          {
            v42 = *(__int64 (__fastcall **)(CCommand *, ULONG *))(*(_QWORD *)this + 176LL);
            goto LABEL_69;
          }
        }
        goto LABEL_225;
      }
      if ( (a5 & 0xC) == 0 || a6->cArgs != 1 )
        goto LABEL_79;
      v61[0] = 8;
      v63 = 1;
      *(_DWORD *)v61 = CStdComObjectRoot::PrepareInvokeArgs(
                         (CStdComObjectRoot *)1,
                         a6,
                         (struct CStdComObjectRoot::INVOKE_ARG *)&v69,
                         v61,
                         1u);
      if ( CContext::FailedInvoke((CContext *)v66, (const int *)v61, a8, 0) )
        goto LABEL_226;
      v48 = *(__int64 (__fastcall **)(CCommand *, LONGLONG))(*(_QWORD *)this + 184LL);
      goto LABEL_101;
    case 9:
      if ( (a5 & 2) == 0 || a6->cArgs )
        goto LABEL_79;
      *(_DWORD *)v61 = CStdComObjectRoot::PrepareInvokeArgsAndResult(
                         (CStdComObjectRoot *)(unsigned int)(a2 - 9),
                         a6,
                         (struct CStdComObjectRoot::INVOKE_ARG *)&v69,
                         0,
                         &v63,
                         &v64,
                         3u);
      if ( !CContext::FailedInvoke((CContext *)v66, (const int *)v61, a8, 0) )
      {
        v40 = (*(__int64 (__fastcall **)(CCommand *, CY *))(*(_QWORD *)this + 192LL))(this, &v64->cyVal);
LABEL_62:
        *(_DWORD *)v61 = v40;
        v15 = 1;
LABEL_63:
        p_scode = (const int *)v61;
LABEL_224:
        CContext::FailedInvoke((CContext *)v66, p_scode, a8, v15);
        goto LABEL_225;
      }
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_225;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144)) != -1 )
      {
        v21 = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
        v22 = 431113;
        LODWORD(v59) = 421;
        goto LABEL_23;
      }
      v23 = 421;
      v24 = 431113;
      goto LABEL_111;
    case 10:
      if ( pvarg )
        VariantInit(pvarg);
      if ( a6->cArgs )
        v63 = -2147352562;
      else
        v63 = (*(__int64 (__fastcall **)(CCommand *, __int64))(*(_QWORD *)this + 200LL))(this, v17);
      CContext::FailedInvoke((CContext *)v66, (const int *)&v63, a8, 0);
      goto LABEL_227;
    case 11:
      if ( (a5 & 2) == 0 )
      {
        if ( (a5 & 0xC) == 0 || a6->cArgs != 1 )
          goto LABEL_79;
        v63 = 1;
        v61[0] = 13;
        *(_DWORD *)v61 = CStdComObjectRoot::PrepareInvokeArgs(
                           (CStdComObjectRoot *)1,
                           a6,
                           (struct CStdComObjectRoot::INVOKE_ARG *)&v69,
                           v61,
                           1u);
        if ( CContext::FailedInvoke((CContext *)v66, (const int *)v61, a8, 0) )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_226;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144)) != -1 )
          {
            v50 = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
            v51 = 332809;
            LODWORD(v60) = 325;
            goto LABEL_118;
          }
          v52 = 325;
          v53 = 332809;
LABEL_120:
          bidTraceW(off_18012A1E0[0], v53, L"<CCommand::Invoke|ADO|ERR>  line %d\n", v52);
          goto LABEL_226;
        }
        v45 = (*(__int64 (__fastcall **)(CCommand *, LONGLONG))(*(_QWORD *)this + 208LL))(this, v69.llVal);
LABEL_78:
        *(_DWORD *)v61 = v45;
        CContext::FailedInvoke((CContext *)v66, (const int *)v61, a8, 0);
        goto LABEL_226;
      }
      *(_DWORD *)v61 = CStdComObjectRoot::PrepareInvokeArgsAndResult(
                         (CStdComObjectRoot *)(unsigned int)(a2 - 11),
                         a6,
                         (struct CStdComObjectRoot::INVOKE_ARG *)&v69,
                         0,
                         &v63,
                         &v64,
                         0);
      if ( !CContext::FailedInvoke((CContext *)v66, (const int *)v61, a8, 0) )
      {
        Item = (*(__int64 (__fastcall **)(CCommand *, struct tagVARIANT *))(*(_QWORD *)this + 216LL))(this, v64);
LABEL_46:
        *(_DWORD *)v61 = Item;
        p_scode = (const int *)v61;
LABEL_223:
        v15 = 0;
        goto LABEL_224;
      }
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_225;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144)) != -1 )
      {
        v21 = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
        v22 = 322569;
        LODWORD(v59) = 315;
        goto LABEL_23;
      }
      v23 = 315;
      v24 = 322569;
LABEL_111:
      bidTraceW(off_18012A1E0[0], v24, L"<CCommand::Invoke|ADO|ERR>  line %d\n", v23);
      goto LABEL_225;
  }
  v55 = (CStdComObjectRoot *)(unsigned int)(a2 - 12);
  if ( a2 == 12 )
  {
    if ( (a5 & 2) != 0 && !a6->cArgs )
    {
      *(_DWORD *)v61 = CStdComObjectRoot::PrepareInvokeArgsAndResult(
                         v55,
                         a6,
                         (struct CStdComObjectRoot::INVOKE_ARG *)&v69,
                         0,
                         &v63,
                         &v64,
                         8u);
      if ( !CContext::FailedInvoke((CContext *)v66, (const int *)v61, a8, 0) )
      {
        v41 = v64;
        if ( v64 )
        {
          v42 = *(__int64 (__fastcall **)(CCommand *, ULONG *))(*(_QWORD *)this + 232LL);
          goto LABEL_69;
        }
      }
      goto LABEL_225;
    }
    if ( (a5 & 0xC) == 0 || a6->cArgs != 1 )
      goto LABEL_79;
    v61[0] = 8;
    v63 = 1;
    *(_DWORD *)v61 = CStdComObjectRoot::PrepareInvokeArgs(
                       (CStdComObjectRoot *)1,
                       a6,
                       (struct CStdComObjectRoot::INVOKE_ARG *)&v69,
                       v61,
                       1u);
    if ( CContext::FailedInvoke((CContext *)v66, (const int *)v61, a8, 0) )
      goto LABEL_226;
    v48 = *(__int64 (__fastcall **)(CCommand *, LONGLONG))(*(_QWORD *)this + 224LL);
    goto LABEL_101;
  }
  if ( a2 == 13 )
  {
    if ( (a5 & 2) != 0 && !a6->cArgs )
    {
      *(_DWORD *)v61 = CStdComObjectRoot::PrepareInvokeArgsAndResult(
                         v55,
                         a6,
                         (struct CStdComObjectRoot::INVOKE_ARG *)&v69,
                         0,
                         &v63,
                         &v64,
                         0xBu);
      if ( !CContext::FailedInvoke((CContext *)v66, (const int *)v61, a8, 0) )
      {
        v41 = v64;
        if ( v64 )
        {
          v42 = *(__int64 (__fastcall **)(CCommand *, ULONG *))(*(_QWORD *)this + 248LL);
          goto LABEL_69;
        }
      }
      goto LABEL_225;
    }
    if ( (a5 & 0xC) != 0 && a6->cArgs == 1 )
    {
      v63 = 1;
      v61[0] = 11;
      *(_DWORD *)v61 = CStdComObjectRoot::PrepareInvokeArgs(
                         (CStdComObjectRoot *)1,
                         a6,
                         (struct CStdComObjectRoot::INVOKE_ARG *)&v69,
                         v61,
                         1u);
      if ( CContext::FailedInvoke((CContext *)v66, (const int *)v61, a8, 0) )
        goto LABEL_226;
      v43 = *(__int64 (__fastcall **)(CCommand *, _QWORD))(*(_QWORD *)this + 240LL);
LABEL_75:
      p_uiVal = &v69.uiVal;
      if ( (v69.vt & 0x4000) != 0 )
        p_uiVal = v69.bstrVal;
      v45 = v43(this, *p_uiVal);
      goto LABEL_78;
    }
LABEL_79:
    *(_DWORD *)v61 = -2147352562;
    goto LABEL_63;
  }
LABEL_218:
  if ( a8 )
    a8->scode = 0;
  v68 = ADOIDispatchImpl<_ADOCommand>::Invoke(this, (unsigned int)a2, a3, a4, a5, a6, pvarg, a8, *(_QWORD *)v61);
  if ( a8 && a8->scode )
  {
    CContext::FreeExcepBSTRs(v56, a8);
    p_scode = &a8->scode;
    goto LABEL_223;
  }
LABEL_227:
  v57 = v68;
  CContext::~CContext((CContext *)v66);
  return v57;
}

```

## disassembly

```asm
0x180084980  mov     [rsp-8+arg_10], rbx
0x180084985  push    rbp
0x180084986  push    rsi
0x180084987  push    rdi
0x180084988  push    r12
0x18008498a  push    r13
0x18008498c  push    r14
0x18008498e  push    r15
0x180084990  lea     rbp, [rsp-110h]
0x180084998  sub     rsp, 210h
0x18008499f  mov     rax, cs:__security_cookie
0x1800849a6  xor     rax, rsp
0x1800849a9  mov     [rbp+140h+var_40], rax
0x1800849b0  mov     rax, [rbp+140h+arg_40]
0x1800849b7  mov     rsi, rcx
0x1800849ba  mov     r15, [rbp+140h+pvarg]
0x1800849c1  mov     r14d, edx
0x1800849c4  mov     rdi, [rbp+140h+arg_28]
0x1800849cb  lea     rdx, [rcx+20h]
0x1800849cf  mov     rbx, [rbp+140h+arg_38]
0x1800849d6  mov     r13d, r9d
0x1800849d9  mov     qword ptr [rsp+240h+var_1F0], rax
0x1800849de  mov     r12, r8
0x1800849e1  mov     rax, rcx
0x1800849e4  mov     [rsp+240h+var_1D8], r15
0x1800849e9  neg     rax
0x1800849ec  sbb     rcx, rcx
0x1800849ef  and     rcx, rdx
0x1800849f2  mov     [rbp+140h+var_190], rcx
0x1800849f6  lea     rcx, [rbp+140h+var_1B0]; this
0x1800849fa  call    ?Init@CContext@@QEAAXXZ; CContext::Init(void)
0x1800849ff  xor     eax, eax
0x180084a01  lea     rcx, [rbp+140h+var_1B0]; this
0x180084a05  mov     edx, eax
0x180084a07  mov     [rsp+240h+var_1E0], eax
0x180084a0b  test    rdi, rdi
0x180084a0e  setnz   dl; int
0x180084a11  call    ?ArgFailed@CContext@@QEAAHH@Z; CContext::ArgFailed(int)
0x180084a16  xor     r9d, r9d; unsigned __int16 *
0x180084a19  test    eax, eax
0x180084a1b  jz      short loc_180084A92
0x180084a1d  test    byte ptr cs:_bidGblFlags, 2
0x180084a24  jz      loc_180085D68
0x180084a2a  lea     rcx, [rsi+90h]; this
0x180084a31  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180084a36  cmp     eax, 0FFFFFFFFh
0x180084a39  jz      short loc_180084A6F
0x180084a3b  lea     rcx, [rsi+90h]; this
0x180084a42  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180084a47  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180084a4e  lea     r8, aCcommandInvoke_0; "<CCommand::Invoke|ADO|ERR> %u#, line %d"...
0x180084a55  mov     r9d, eax
0x180084a58  mov     dword ptr [rsp+240h+var_220], 10Ch
0x180084a60  mov     edx, 43009h
0x180084a65  call    _bidTraceW
0x180084a6a  jmp     loc_180085D68
0x180084a6f  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180084a76  lea     r8, aCcommandInvoke; "<CCommand::Invoke|ADO|ERR>  line %d\n"
0x180084a7d  mov     r9d, 10Ch
0x180084a83  mov     edx, 43009h
0x180084a88  call    _bidTraceW
0x180084a8d  jmp     loc_180085D68
0x180084a92  movzx   edx, [rbp+140h+arg_20]
0x180084a99  cmp     [rdi+14h], r9d
0x180084a9d  jz      short loc_180084AA8
0x180084a9f  test    dl, 4
0x180084aa2  jz      loc_180085CF2
0x180084aa8  mov     eax, 1F4h
0x180084aad  cmp     r14d, eax
0x180084ab0  jg      loc_180085CF2
0x180084ab6  jz      loc_180085AED
0x180084abc  cmp     r14d, 7
0x180084ac0  jg      loc_1800855A8
0x180084ac6  jz      loc_1800854CD
0x180084acc  movzx   r8d, dx
0x180084ad0  mov     ecx, r14d; this
0x180084ad3  and     r8w, 4
0x180084ad8  test    r14d, r14d
0x180084adb  jz      loc_180085291
0x180084ae1  sub     ecx, 1; this
0x180084ae4  jz      loc_1800850DB
0x180084aea  sub     ecx, 1; this
0x180084aed  jz      loc_180084FE7
0x180084af3  sub     ecx, 1; this
0x180084af6  jz      loc_180084EF6
0x180084afc  sub     ecx, 1; this
0x180084aff  jz      loc_180084DD0
0x180084b05  sub     ecx, 1; this
0x180084b08  jz      loc_180084CAE
0x180084b0e  cmp     ecx, 1
0x180084b11  jnz     loc_180085CF2
0x180084b17  mov     eax, 80Ch
0x180084b1c  mov     [rsp+240h+var_210], 9; unsigned __int16
0x180084b23  mov     [rsp+240h+var_1E8], ax
0x180084b28  lea     r9, [rsp+240h+var_1F0]; unsigned __int16 *
0x180084b2d  lea     rax, [rsp+240h+var_1D8]
0x180084b32  mov     dword ptr [rsp+240h+var_1F0], 8030808h
0x180084b3a  mov     [rsp+240h+var_218], rax; struct tagVARIANT **
0x180084b3f  lea     r8, [rbp+140h+var_180]; struct CStdComObjectRoot::INVOKE_ARG *
0x180084b43  lea     rax, [rsp+240h+var_1E0]
0x180084b48  mov     dword ptr [rsp+240h+var_1F0+4], 8030803h
0x180084b50  mov     rdx, rdi; struct tagDISPPARAMS *
0x180084b53  mov     [rsp+240h+var_220], rax; unsigned int *
0x180084b58  mov     [rsp+240h+var_1E0], 5
0x180084b60  call    ?PrepareInvokeArgsAndResult@CStdComObjectRoot@@QEAAJPEAUtagDISPPARAMS@@PEAUINVOKE_ARG@1@PEAGAEAIAEAPEAUtagVARIANT@@G@Z; CStdComObjectRoot::PrepareInvokeArgsAndResult(tagDISPPARAMS *,CStdComObjectRoot::INVOKE_ARG *,ushort *,uint &,tagVARIANT * &,ushort)
0x180084b65  xor     r9d, r9d; bool
0x180084b68  mov     dword ptr [rsp+240h+var_1F0], eax
0x180084b6c  mov     r8, rbx; struct tagEXCEPINFO *
0x180084b6f  lea     rdx, [rsp+240h+var_1F0]; int *
0x180084b74  lea     rcx, [rbp+140h+var_1B0]; this
0x180084b78  call    ?FailedInvoke@CContext@@QEAA_NAEBJPEAUtagEXCEPINFO@@_N@Z; CContext::FailedInvoke(long const &,tagEXCEPINFO *,bool)
0x180084b7d  xor     r14d, r14d
0x180084b80  test    al, al
0x180084b82  jz      short loc_180084BE6
0x180084b84  test    byte ptr cs:_bidGblFlags, 2
0x180084b8b  jz      loc_180085D53
0x180084b91  lea     rcx, [rsi+90h]; this
0x180084b98  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180084b9d  cmp     eax, 0FFFFFFFFh
0x180084ba0  jz      short loc_180084BD6
0x180084ba2  lea     rcx, [rsi+90h]; this
0x180084ba9  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180084bae  mov     edx, 59009h
0x180084bb3  mov     dword ptr [rsp+240h+var_220], 164h
0x180084bbb  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180084bc2  lea     r8, aCcommandInvoke_0; "<CCommand::Invoke|ADO|ERR> %u#, line %d"...
0x180084bc9  mov     r9d, eax
0x180084bcc  call    _bidTraceW
0x180084bd1  jmp     loc_180085D53
0x180084bd6  mov     r9d, 164h
0x180084bdc  mov     edx, 59009h
0x180084be1  jmp     loc_18008516E
0x180084be6  mov     rax, [rsi]
0x180084be9  mov     edx, 4000h
0x180084bee  mov     r10, [rsp+240h+var_1D8]
0x180084bf3  movaps  xmm0, [rbp+140h+var_100]
0x180084bf7  add     r10, 8
0x180084bfb  movsd   xmm1, [rbp+140h+var_F0]
0x180084c00  mov     r11, [rax+90h]
0x180084c07  cmp     [rbp+140h+var_107], r14b
0x180084c0b  jz      short loc_180084C12
0x180084c0d  mov     r9d, r14d
0x180084c10  jmp     short loc_180084C22
0x180084c12  test    [rbp+140h+var_120], dx
0x180084c16  lea     rax, [rbp+140h+var_118]
0x180084c1a  cmovnz  rax, [rbp+140h+var_118]
0x180084c1f  mov     r9d, [rax]
0x180084c22  cmp     [rbp+140h+var_127], r14b
0x180084c26  jz      short loc_180084C2F
0x180084c28  mov     ecx, 1
0x180084c2d  jmp     short loc_180084C3E
0x180084c2f  test    [rbp+140h+var_140], dx
0x180084c33  lea     rax, [rbp+140h+var_138]
0x180084c37  cmovnz  rax, [rbp+140h+var_138]
0x180084c3c  mov     ecx, [rax]
0x180084c3e  cmp     [rbp+140h+var_147], r14b
0x180084c42  jz      short loc_180084C49
0x180084c44  mov     r8d, r14d
0x180084c47  jmp     short loc_180084C59
0x180084c49  test    word ptr [rbp+140h+var_160], dx
0x180084c4d  lea     rax, [rbp+140h+var_160+8]
0x180084c51  cmovnz  rax, qword ptr [rbp+140h+var_160+8]
0x180084c56  mov     r8d, [rax]
0x180084c59  cmp     [rbp+140h+var_167], r14b
0x180084c5d  jz      short loc_180084C64
0x180084c5f  mov     rdx, r14
0x180084c62  jmp     short loc_180084C74
0x180084c64  test    [rbp+140h+var_180], dx
0x180084c68  lea     rax, [rbp+140h+var_178]
0x180084c6c  cmovnz  rax, qword ptr [rbp+140h+var_178]
0x180084c71  mov     rdx, [rax]
0x180084c74  mov     qword ptr [rsp+240h+var_210], r10
0x180084c79  lea     rax, [rsp+240h+var_1D0]
0x180084c7e  mov     [rsp+240h+var_218], rax
0x180084c83  mov     rax, r11
0x180084c86  mov     dword ptr [rsp+240h+var_220], r9d
0x180084c8b  mov     r9d, ecx
0x180084c8e  mov     rcx, rsi
0x180084c91  movaps  xmmword ptr [rsp+240h+var_1D0], xmm0
0x180084c96  movsd   qword ptr [rbp+140h+var_1D0+10h], xmm1
0x180084c9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084ca0  mov     dword ptr [rsp+240h+var_1F0], eax
0x180084ca4  lea     rdx, [rsp+240h+var_1F0]
0x180084ca9  jmp     loc_180085D44
0x180084cae  mov     eax, 803h
0x180084cb3  mov     [rsp+240h+var_210], 9; unsigned __int16
0x180084cba  mov     [rsp+240h+var_1F0+4], ax
0x180084cbf  lea     r9, [rsp+240h+var_1F0]; unsigned __int16 *
0x180084cc4  mov     eax, 3
0x180084cc9  mov     dword ptr [rsp+240h+var_1F0], 80C480Ch
0x180084cd1  mov     [rsp+240h+var_1E0], eax
0x180084cd5  lea     r8, [rbp+140h+var_180]; struct CStdComObjectRoot::INVOKE_ARG *
0x180084cd9  lea     rax, [rsp+240h+var_1D8]
0x180084cde  mov     rdx, rdi; struct tagDISPPARAMS *
0x180084ce1  mov     [rsp+240h+var_218], rax; struct tagVARIANT **
0x180084ce6  lea     rax, [rsp+240h+var_1E0]
0x180084ceb  mov     [rsp+240h+var_220], rax; unsigned int *
0x180084cf0  call    ?PrepareInvokeArgsAndResult@CStdComObjectRoot@@QEAAJPEAUtagDISPPARAMS@@PEAUINVOKE_ARG@1@PEAGAEAIAEAPEAUtagVARIANT@@G@Z; CStdComObjectRoot::PrepareInvokeArgsAndResult(tagDISPPARAMS *,CStdComObjectRoot::INVOKE_ARG *,ushort *,uint &,tagVARIANT * &,ushort)
0x180084cf5  xor     r9d, r9d; bool
0x180084cf8  mov     dword ptr [rsp+240h+var_1F0], eax
0x180084cfc  mov     r8, rbx; struct tagEXCEPINFO *
0x180084cff  lea     rdx, [rsp+240h+var_1F0]; int *
0x180084d04  lea     rcx, [rbp+140h+var_1B0]; this
0x180084d08  call    ?FailedInvoke@CContext@@QEAA_NAEBJPEAUtagEXCEPINFO@@_N@Z; CContext::FailedInvoke(long const &,tagEXCEPINFO *,bool)
0x180084d0d  xor     r14d, r14d
0x180084d10  test    al, al
0x180084d12  jz      short loc_180084D60
0x180084d14  test    byte ptr cs:_bidGblFlags, 2
0x180084d1b  jz      loc_180085D53
0x180084d21  lea     rcx, [rsi+90h]; this
0x180084d28  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180084d2d  cmp     eax, 0FFFFFFFFh
0x180084d30  jz      short loc_180084D50
0x180084d32  lea     rcx, [rsi+90h]; this
0x180084d39  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180084d3e  mov     edx, 60409h
0x180084d43  mov     dword ptr [rsp+240h+var_220], 181h
0x180084d4b  jmp     loc_180084BBB
0x180084d50  mov     r9d, 181h
0x180084d56  mov     edx, 60409h
0x180084d5b  jmp     loc_18008516E
0x180084d60  mov     rax, [rsi]
0x180084d63  mov     r10, [rsp+240h+var_1D8]
0x180084d68  add     r10, 8
0x180084d6c  mov     r11, [rax+88h]
0x180084d73  cmp     [rbp+140h+var_127], r14b
0x180084d77  jz      short loc_180084D7F
0x180084d79  or      r9d, 0FFFFFFFFh
0x180084d7d  jmp     short loc_180084D94
0x180084d7f  mov     edx, 4000h
0x180084d84  lea     rax, [rbp+140h+var_138]
0x180084d88  test    [rbp+140h+var_140], dx
0x180084d8c  cmovnz  rax, [rbp+140h+var_138]
0x180084d91  mov     r9d, [rax]
0x180084d94  cmp     [rbp+140h+var_147], r14b
0x180084d98  lea     r8, [rbp+140h+var_160]
0x180084d9c  mov     rdx, qword ptr [rbp+140h+var_178]
0x180084da0  mov     rcx, rsi
0x180084da3  cmovnz  r8, r14
0x180084da7  mov     [rsp+240h+var_220], r10
0x180084dac  cmp     [rbp+140h+var_167], r14b
0x180084db0  mov     rax, r11
0x180084db3  cmovnz  rdx, r14
0x180084db7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084dbc  mov     dword ptr [rsp+240h+var_1F0], eax
0x180084dc0  mov     r9d, 1
0x180084dc6  lea     rdx, [rsp+240h+var_1F0]
0x180084dcb  jmp     loc_180085D47
0x180084dd0  test    dl, 2
0x180084dd3  jz      short loc_180084E4B
0x180084dd5  xor     r14d, r14d
0x180084dd8  cmp     [rdi+10h], r14d
0x180084ddc  jnz     short loc_180084E4B
0x180084dde  lea     rax, [rsp+240h+var_1D8]
0x180084de3  mov     [rsp+240h+var_210], 0Bh; unsigned __int16
0x180084dea  mov     [rsp+240h+var_218], rax; struct tagVARIANT **
0x180084def  lea     r8, [rbp+140h+var_180]; struct CStdComObjectRoot::INVOKE_ARG *
0x180084df3  lea     rax, [rsp+240h+var_1E0]
0x180084df8  mov     rdx, rdi; struct tagDISPPARAMS *
0x180084dfb  mov     [rsp+240h+var_220], rax; unsigned int *
0x180084e00  call    ?PrepareInvokeArgsAndResult@CStdComObjectRoot@@QEAAJPEAUtagDISPPARAMS@@PEAUINVOKE_ARG@1@PEAGAEAIAEAPEAUtagVARIANT@@G@Z; CStdComObjectRoot::PrepareInvokeArgsAndResult(tagDISPPARAMS *,CStdComObjectRoot::INVOKE_ARG *,ushort *,uint &,tagVARIANT * &,ushort)
0x180084e05  xor     r9d, r9d; bool
0x180084e08  mov     dword ptr [rsp+240h+var_1F0], eax
0x180084e0c  mov     r8, rbx; struct tagEXCEPINFO *
0x180084e0f  lea     rdx, [rsp+240h+var_1F0]; int *
0x180084e14  lea     rcx, [rbp+140h+var_1B0]; this
0x180084e18  call    ?FailedInvoke@CContext@@QEAA_NAEBJPEAUtagEXCEPINFO@@_N@Z; CContext::FailedInvoke(long const &,tagEXCEPINFO *,bool)
0x180084e1d  test    al, al
0x180084e1f  jnz     loc_180085D53
0x180084e25  mov     rdx, [rsp+240h+var_1D8]
0x180084e2a  test    rdx, rdx
0x180084e2d  jz      loc_180085D53
0x180084e33  mov     rax, [rsi]
0x180084e36  mov     rax, [rax+78h]
0x180084e3a  add     rdx, 8
0x180084e3e  mov     rcx, rsi
0x180084e41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084e46  jmp     loc_180084CA0
0x180084e4b  mov     eax, 0Ch
0x180084e50  test    al, dl
0x180084e52  jz      loc_180084EE9
0x180084e58  lea     ecx, [rax-0Bh]; this
0x180084e5b  cmp     [rdi+10h], ecx
0x180084e5e  jnz     loc_180084EE9
0x180084e64  lea     eax, [rcx+0Ah]
0x180084e67  mov     [rsp+240h+var_1E0], ecx
0x180084e6b  lea     r9, [rsp+240h+var_1F0]; unsigned __int16 *
0x180084e70  mov     [rsp+240h+var_1F0], ax
0x180084e75  lea     r8, [rbp+140h+var_180]; struct CStdComObjectRoot::INVOKE_ARG *
0x180084e79  mov     dword ptr [rsp+240h+var_220], ecx; unsigned int
0x180084e7d  mov     rdx, rdi; struct tagDISPPARAMS *
0x180084e80  call    ?PrepareInvokeArgs@CStdComObjectRoot@@QEAAJPEAUtagDISPPARAMS@@PEAUINVOKE_ARG@1@PEAGI@Z; CStdComObjectRoot::PrepareInvokeArgs(tagDISPPARAMS *,CStdComObjectRoot::INVOKE_ARG *,ushort *,uint)
0x180084e85  xor     r9d, r9d; bool
0x180084e88  mov     dword ptr [rsp+240h+var_1F0], eax
0x180084e8c  mov     r8, rbx; struct tagEXCEPINFO *
0x180084e8f  lea     rdx, [rsp+240h+var_1F0]; int *
0x180084e94  lea     rcx, [rbp+140h+var_1B0]; this
0x180084e98  call    ?FailedInvoke@CContext@@QEAA_NAEBJPEAUtagEXCEPINFO@@_N@Z; CContext::FailedInvoke(long const &,tagEXCEPINFO *,bool)
0x180084e9d  test    al, al
0x180084e9f  jnz     loc_180085D5A
  ... truncated ...
```
