# CMSMQRuleHandler::EvaluateConditionToken(IMSMQPropertyBag *,_bstr_t,int *)

- ea: `0x180005df4`
- end: `0x180006a48`
- name: `?EvaluateConditionToken@CMSMQRuleHandler@@QEAAJPEAUIMSMQPropertyBag@@V_bstr_t@@PEAH@Z`
- size: `3156`
- prototype: `__int64 __fastcall(__int64, __int64, _bstr_t *, BOOL *)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800097c8`

## callees

- `0x180004d20`
- `0x1800053ac`
- `0x18000544c`
- `0x1800054a4`
- `0x1800056c8`
- `0x1800057c8`
- `0x180005df4`
- `0x180009ab0`
- `0x180009b3c`
- `0x180014d30`
- `0x1800157c8`
- `0x1800157fc`
- `0x180015888`
- `0x1800158cc`
- `0x180022010`

## import_xrefs

- `msvcrt!wcstoul` at `0x180006373`
- `msvcrt!wcstoul` at `0x180006373`
- `msvcrt!_wtol` at `0x1800064ce`
- `msvcrt!_wtol` at `0x1800064ce`
- `msvcrt!wcsstr` at `0x1800067c5`
- `msvcrt!wcsstr` at `0x180006950`
- `msvcrt!wcsstr` at `0x1800067c5`
- `msvcrt!wcsstr` at `0x180006950`
- `msvcrt!_wcsicmp` at `0x180005ed0`
- `msvcrt!_wcsicmp` at `0x180005ef1`
- `msvcrt!_wcsicmp` at `0x180005f12`
- `msvcrt!_wcsicmp` at `0x180005f33`
- `msvcrt!_wcsicmp` at `0x180005f54`
- `msvcrt!_wcsicmp` at `0x180005f75`
- `msvcrt!_wcsicmp` at `0x180005f96`
- `msvcrt!_wcsicmp` at `0x180005fb7`
- `msvcrt!_wcsicmp` at `0x180005fd8`
- `msvcrt!_wcsicmp` at `0x180005ff9`
- `msvcrt!_wcsicmp` at `0x18000601a`
- `msvcrt!_wcsicmp` at `0x18000603b`
- `msvcrt!_wcsicmp` at `0x18000605c`
- `msvcrt!_wcsicmp` at `0x18000607d`
- `msvcrt!_wcsicmp` at `0x18000623a`
- `msvcrt!_wcsicmp` at `0x180006256`
- `msvcrt!_wcsicmp` at `0x18000638f`
- `msvcrt!_wcsicmp` at `0x1800063b4`
- `msvcrt!_wcsicmp` at `0x1800063d9`
- `msvcrt!_wcsicmp` at `0x1800064ea`
- `msvcrt!_wcsicmp` at `0x18000650f`
- `msvcrt!_wcsicmp` at `0x180006534`
- `msvcrt!_wcsicmp` at `0x1800066ed`
- `msvcrt!_wcsicmp` at `0x1800067e1`
- `msvcrt!_wcsicmp` at `0x180006821`
- `msvcrt!_wcsicmp` at `0x18000696c`
- `msvcrt!_wcsicmp` at `0x180005ed0`
- `msvcrt!_wcsicmp` at `0x180005ef1`
- `msvcrt!_wcsicmp` at `0x180005f12`
- `msvcrt!_wcsicmp` at `0x180005f33`
- `msvcrt!_wcsicmp` at `0x180005f54`
- `msvcrt!_wcsicmp` at `0x180005f75`
- `msvcrt!_wcsicmp` at `0x180005f96`
- `msvcrt!_wcsicmp` at `0x180005fb7`
- `msvcrt!_wcsicmp` at `0x180005fd8`
- `msvcrt!_wcsicmp` at `0x180005ff9`
- `msvcrt!_wcsicmp` at `0x18000601a`
- `msvcrt!_wcsicmp` at `0x18000603b`
- `msvcrt!_wcsicmp` at `0x18000605c`
- `msvcrt!_wcsicmp` at `0x18000607d`
- `msvcrt!_wcsicmp` at `0x18000623a`
- `msvcrt!_wcsicmp` at `0x180006256`
- `msvcrt!_wcsicmp` at `0x18000638f`
- `msvcrt!_wcsicmp` at `0x1800063b4`
- `msvcrt!_wcsicmp` at `0x1800063d9`
- `msvcrt!_wcsicmp` at `0x1800064ea`
- `msvcrt!_wcsicmp` at `0x18000650f`
- `msvcrt!_wcsicmp` at `0x180006534`
- `msvcrt!_wcsicmp` at `0x1800066ed`
- `msvcrt!_wcsicmp` at `0x1800067e1`
- `msvcrt!_wcsicmp` at `0x180006821`
- `msvcrt!_wcsicmp` at `0x18000696c`
- `OLEAUT32!__imp_VariantInit` at `0x180005e80`
- `OLEAUT32!__imp_VariantInit` at `0x180005e80`
- `OLEAUT32!__imp_VariantClear` at `0x180006090`
- `OLEAUT32!__imp_VariantClear` at `0x180006279`
- `OLEAUT32!__imp_VariantClear` at `0x1800063fc`
- `OLEAUT32!__imp_VariantClear` at `0x180006557`
- `OLEAUT32!__imp_VariantClear` at `0x180006837`
- `OLEAUT32!__imp_VariantClear` at `0x18000698f`
- `OLEAUT32!__imp_VariantClear` at `0x180006090`
- `OLEAUT32!__imp_VariantClear` at `0x180006279`
- `OLEAUT32!__imp_VariantClear` at `0x1800063fc`
- `OLEAUT32!__imp_VariantClear` at `0x180006557`
- `OLEAUT32!__imp_VariantClear` at `0x180006837`
- `OLEAUT32!__imp_VariantClear` at `0x18000698f`

## pseudocode

```c
__int64 __fastcall CMSMQRuleHandler::EvaluateConditionToken(__int64 a1, __int64 a2, _bstr_t *a3, BOOL *a4)
{
  const wchar_t **v7; // rbx
  const wchar_t *v8; // rcx
  const wchar_t *v9; // rcx
  const wchar_t *v10; // rcx
  const wchar_t *v11; // rcx
  const wchar_t *v12; // rcx
  const wchar_t *v13; // rcx
  const wchar_t *v14; // rcx
  const wchar_t *v15; // rcx
  const wchar_t *v16; // rcx
  const wchar_t *v17; // rcx
  const wchar_t *v18; // rcx
  const wchar_t *v19; // rcx
  const wchar_t *v20; // rcx
  const wchar_t *v21; // rcx
  unsigned int v22; // eax
  __int64 *v24; // r14
  __int64 v25; // r15
  _bstr_t *v26; // rax
  __int64 v27; // rdx
  const wchar_t *v28; // rdx
  const wchar_t *v29; // rcx
  int v30; // r14d
  const wchar_t *v31; // rcx
  BOOL v32; // eax
  __int64 *v33; // r14
  __int64 v34; // r15
  _bstr_t *v35; // rax
  __int64 v36; // rdx
  unsigned int Lo; // r15d
  const wchar_t *v38; // rcx
  unsigned int v39; // r14d
  const wchar_t *v40; // rcx
  BOOL v41; // eax
  const wchar_t *v42; // rcx
  const wchar_t *v43; // rcx
  __int64 *v44; // r14
  __int64 v45; // r15
  _bstr_t *v46; // rax
  __int64 v47; // rdx
  LONG lVal; // r15d
  const wchar_t *v49; // rcx
  int v50; // r14d
  const wchar_t *v51; // rcx
  BOOL v52; // eax
  const wchar_t *v53; // rcx
  const wchar_t *v54; // rcx
  int v55; // r14d
  __int64 *v56; // r15
  __int64 v57; // r13
  _bstr_t *v58; // rax
  __int64 v59; // rdx
  __int64 *v60; // r15
  __int64 v61; // r13
  _bstr_t *v62; // rax
  __int64 v63; // rdx
  const wchar_t *v64; // rcx
  __int64 *v65; // r14
  __int64 v66; // r15
  _bstr_t *v67; // rax
  __int64 v68; // rdx
  wchar_t *v69; // r14
  const wchar_t *v70; // rdx
  const wchar_t *v71; // rcx
  const wchar_t *v72; // rcx
  BOOL v73; // eax
  const wchar_t *v74; // rcx
  __int64 *v75; // r14
  __int64 v76; // r15
  _bstr_t *v77; // rax
  __int64 v78; // rdx
  const wchar_t *v79; // rdx
  const wchar_t *v80; // rcx
  wchar_t *v81; // r14
  const wchar_t *v82; // rcx
  BOOL v83; // eax
  const wchar_t **v84; // [rsp+60h] [rbp-A8h] BYREF
  const wchar_t **v85; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v86; // [rsp+70h] [rbp-98h] BYREF
  VARIANTARG pvarg; // [rsp+78h] [rbp-90h] BYREF
  VARIANTARG pvargDest; // [rsp+90h] [rbp-78h] BYREF
  _BYTE v89[32]; // [rsp+A8h] [rbp-60h] BYREF
  _bstr_t *v90; // [rsp+C8h] [rbp-40h]
  const wchar_t **v91; // [rsp+118h] [rbp+10h] BYREF
  _bstr_t *v92; // [rsp+120h] [rbp+18h]
  wchar_t *EndPtr; // [rsp+128h] [rbp+20h] BYREF

  v92 = a3;
  v90 = a3;
  _bstr_t::_bstr_t((_bstr_t *)&v85, &psz);
  _bstr_t::_bstr_t((_bstr_t *)&v84, &psz);
  CStringTokens::CStringTokens((CStringTokens *)v89);
  v86 = a2;
  if ( a2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  *a4 = 0;
  CStringTokens::Parse((CStringTokens *)v89, a3, 0x3Du);
  CStringTokens::GetToken((CStringTokens *)v89, 0, (struct _bstr_t *)&v85);
  v7 = v85;
  if ( v85 )
    v8 = *v85;
  else
    v8 = 0;
  if ( !_wcsicmp(v8, L"$MSG_LABEL_CONTAINS")
    || (!v7 ? (v9 = 0) : (v9 = *v7), !_wcsicmp(v9, L"$MSG_LABEL_DOES_NOT_CONTAIN")) )
  {
    CStringTokens::GetToken((CStringTokens *)v89, 1u, (struct _bstr_t *)&v84);
    v75 = (__int64 *)_com_ptr_t<_com_IIID<IMSMQPropertyBag,&__s_GUID const _GUID_07f19951_ab28_11d2_8936_000000000000>>::operator->(&v86);
    v76 = *v75;
    v77 = _bstr_t::_bstr_t((_bstr_t *)&EndPtr, L"Label");
    if ( *(_QWORD *)v77 )
      v78 = **(_QWORD **)v77;
    else
      v78 = 0;
    (*(void (__fastcall **)(__int64 *, __int64, VARIANTARG *))(v76 + 64))(v75, v78, &pvarg);
    _bstr_t::_Free((_bstr_t *)&EndPtr);
    _variant_t::_variant_t(&pvargDest, &pvarg);
    _bstr_t::_bstr_t((_bstr_t *)&v91, (const struct _variant_t *)&pvargDest);
    _variant_t::~_variant_t((_variant_t *)&pvargDest);
    if ( v84 )
      v79 = *v84;
    else
      v79 = 0;
    if ( v91 )
      v80 = *v91;
    else
      v80 = 0;
    v81 = wcsstr(v80, v79);
    if ( v7 )
      v82 = *v7;
    else
      v82 = 0;
    if ( _wcsicmp(v82, L"$MSG_LABEL_CONTAINS") )
      v83 = v81 == 0;
    else
      v83 = v81 != 0;
    *a4 = v83;
    VariantClear(&pvarg);
    _bstr_t::_Free((_bstr_t *)&v91);
    if ( !a2 )
      goto LABEL_189;
    goto LABEL_188;
  }
  if ( v7 )
    v10 = *v7;
  else
    v10 = 0;
  if ( _wcsicmp(v10, L"$MSG_BODY_CONTAINS") )
  {
    v11 = v7 ? *v7 : 0LL;
    if ( _wcsicmp(v11, L"$MSG_BODY_DOES_NOT_CONTAIN") )
    {
      if ( v7 )
        v12 = *v7;
      else
        v12 = 0;
      if ( _wcsicmp(v12, L"$MSG_PRIORITY_GREATER_THAN")
        && (!v7 ? (v13 = 0) : (v13 = *v7),
            _wcsicmp(v13, L"$MSG_PRIORITY_LESS_THAN")
         && (!v7 ? (v14 = 0) : (v14 = *v7),
             _wcsicmp(v14, L"$MSG_PRIORITY_EQUALS")
          && (!v7 ? (v15 = 0) : (v15 = *v7), _wcsicmp(v15, L"$MSG_PRIORITY_NOT_EQUAL")))) )
      {
        if ( v7 )
          v16 = *v7;
        else
          v16 = 0;
        if ( _wcsicmp(v16, L"$MSG_APPSPECIFIC_GREATER_THAN")
          && (!v7 ? (v17 = 0) : (v17 = *v7),
              _wcsicmp(v17, L"$MSG_APPSPECIFIC_LESS_THAN")
           && (!v7 ? (v18 = 0) : (v18 = *v7),
               _wcsicmp(v18, L"$MSG_APPSPECIFIC_EQUALS")
            && (!v7 ? (v19 = 0) : (v19 = *v7), _wcsicmp(v19, L"$MSG_APPSPECIFIC_NOT_EQUAL")))) )
        {
          if ( v7 )
            v20 = *v7;
          else
            v20 = 0;
          if ( _wcsicmp(v20, L"$MSG_SRCMACHINEID_EQUALS") )
          {
            v21 = v7 ? *v7 : 0LL;
            if ( _wcsicmp(v21, L"$MSG_SRCMACHINEID_NOT_EQUAL") )
            {
              VariantClear(&pvarg);
              LOWORD(v91) = 70;
              LODWORD(EndPtr) = -1072820729;
              if ( g_pMSMQErrorLoggingTrace )
              {
                v22 = mqwcslen(L"trigobjs/rulehdlr");
                CMSMQTrace::MSMQTraceEvent(
                  g_pMSMQErrorLoggingTrace,
                  1,
                  1,
                  2LL * (v22 + 1),
                  L"trigobjs/rulehdlr",
                  2,
                  &v91,
                  4,
                  &EndPtr,
                  0,
                  0);
              }
              if ( a2 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 16LL))(a2);
              CStringTokens::~CStringTokens((CStringTokens *)v89);
              _bstr_t::_Free((_bstr_t *)&v84);
              _bstr_t::_Free((_bstr_t *)&v85);
              _bstr_t::_Free(a3);
              return 3222146567LL;
            }
          }
          CStringTokens::GetToken((CStringTokens *)v89, 1u, (struct _bstr_t *)&v84);
          v24 = (__int64 *)_com_ptr_t<_com_IIID<IMSMQPropertyBag,&__s_GUID const _GUID_07f19951_ab28_11d2_8936_000000000000>>::operator->(&v86);
          v25 = *v24;
          v26 = _bstr_t::_bstr_t((_bstr_t *)&EndPtr, L"SrcMachineId");
          if ( *(_QWORD *)v26 )
            v27 = **(_QWORD **)v26;
          else
            v27 = 0;
          (*(void (__fastcall **)(__int64 *, __int64, VARIANTARG *))(v25 + 64))(v24, v27, &pvarg);
          _bstr_t::_Free((_bstr_t *)&EndPtr);
          _variant_t::_variant_t(&pvargDest, &pvarg);
          _bstr_t::_bstr_t((_bstr_t *)&v91, (const struct _variant_t *)&pvargDest);
          _variant_t::~_variant_t((_variant_t *)&pvargDest);
          if ( v84 )
            v28 = *v84;
          else
            v28 = 0;
          if ( v91 )
            v29 = *v91;
          else
            v29 = 0;
          v30 = _wcsicmp(v29, v28);
          if ( v7 )
            v31 = *v7;
          else
            v31 = 0;
          if ( _wcsicmp(v31, L"$MSG_SRCMACHINEID_EQUALS") )
            v32 = v30 != 0;
          else
            v32 = v30 == 0;
          *a4 = v32;
          VariantClear(&pvarg);
          _bstr_t::_Free((_bstr_t *)&v91);
          if ( !a2 )
          {
LABEL_189:
            CStringTokens::~CStringTokens((CStringTokens *)v89);
            _bstr_t::_Free((_bstr_t *)&v84);
            _bstr_t::_Free((_bstr_t *)&v85);
            _bstr_t::_Free(a3);
            return 0;
          }
        }
        else
        {
          EndPtr = 0;
          CStringTokens::GetToken((CStringTokens *)v89, 1u, (struct _bstr_t *)&v84);
          v33 = (__int64 *)_com_ptr_t<_com_IIID<IMSMQPropertyBag,&__s_GUID const _GUID_07f19951_ab28_11d2_8936_000000000000>>::operator->(&v86);
          v34 = *v33;
          v35 = _bstr_t::_bstr_t((_bstr_t *)&v91, L"AppSpecific");
          if ( *(_QWORD *)v35 )
            v36 = **(_QWORD **)v35;
          else
            v36 = 0;
          (*(void (__fastcall **)(__int64 *, __int64, VARIANTARG *))(v34 + 64))(v33, v36, &pvarg);
          _bstr_t::_Free((_bstr_t *)&v91);
          Lo = pvarg.cyVal.Lo;
          if ( v84 )
            v38 = *v84;
          else
            v38 = 0;
          v39 = wcstoul(v38, &EndPtr, 10);
          if ( v7 )
            v40 = *v7;
          else
            v40 = 0;
          if ( _wcsicmp(v40, L"$MSG_APPSPECIFIC_EQUALS") )
          {
            if ( v7 )
              v42 = *v7;
            else
              v42 = 0;
            if ( _wcsicmp(v42, L"$MSG_APPSPECIFIC_NOT_EQUAL") )
            {
              if ( v7 )
                v43 = *v7;
              else
                v43 = 0;
              if ( _wcsicmp(v43, L"$MSG_APPSPECIFIC_GREATER_THAN") )
                v41 = v39 > Lo;
              else
                v41 = v39 < Lo;
            }
            else
            {
              v41 = v39 != Lo;
            }
          }
          else
          {
            v41 = v39 == Lo;
          }
          *a4 = v41;
          VariantClear(&pvarg);
          if ( !a2 )
            goto LABEL_189;
        }
      }
      else
      {
        CStringTokens::GetToken((CStringTokens *)v89, 1u, (struct _bstr_t *)&v84);
        v44 = (__int64 *)_com_ptr_t<_com_IIID<IMSMQPropertyBag,&__s_GUID const _GUID_07f19951_ab28_11d2_8936_000000000000>>::operator->(&v86);
        v45 = *v44;
        v46 = _bstr_t::_bstr_t((_bstr_t *)&v91, L"MessagePriority");
        if ( *(_QWORD *)v46 )
          v47 = **(_QWORD **)v46;
        else
          v47 = 0;
        (*(void (__fastcall **)(__int64 *, __int64, VARIANTARG *))(v45 + 64))(v44, v47, &pvarg);
        _bstr_t::_Free((_bstr_t *)&v91);
        lVal = pvarg.lVal;
        if ( v84 )
          v49 = *v84;
        else
          v49 = 0;
        v50 = _wtol(v49);
        if ( v7 )
          v51 = *v7;
        else
          v51 = 0;
        if ( _wcsicmp(v51, L"$MSG_PRIORITY_EQUALS") )
        {
          if ( v7 )
            v53 = *v7;
          else
            v53 = 0;
          if ( _wcsicmp(v53, L"$MSG_PRIORITY_NOT_EQUAL") )
          {
            if ( v7 )
              v54 = *v7;
            else
              v54 = 0;
            if ( _wcsicmp(v54, L"$MSG_PRIORITY_GREATER_THAN") )
              v52 = v50 > lVal;
            else
              v52 = v50 < lVal;
          }
          else
          {
            v52 = v50 != lVal;
          }
        }
        else
        {
          v52 = v50 == lVal;
        }
        *a4 = v52;
        VariantClear(&pvarg);
        if ( !a2 )
          goto LABEL_189;
      }
LABEL_188:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 16LL))(a2);
      goto LABEL_189;
    }
  }
  v55 = 1;
  CStringTokens::GetToken((CStringTokens *)v89, 1u, (struct _bstr_t *)&v84);
  v56 = (__int64 *)_com_ptr_t<_com_IIID<IMSMQPropertyBag,&__s_GUID const _GUID_07f19951_ab28_11d2_8936_000000000000>>::operator->(&v86);
  v57 = *v56;
  v58 = _bstr_t::_bstr_t((_bstr_t *)&v91, L"MessageBodyType");
  if ( *(_QWORD *)v58 )
    v59 = **(_QWORD **)v58;
  else
    v59 = 0;
  (*(void (__fastcall **)(__int64 *, __int64, VARIANTARG *))(v57 + 64))(v56, v59, &pvarg);
  _bstr_t::_Free((_bstr_t *)&v91);
  switch ( pvarg.lVal )
  {
    case 0:
      if ( v7 )
        v74 = *v7;
      else
        v74 = 0;
      *a4 = _wcsicmp(v74, L"$MSG_BODY_DOES_NOT_CONTAIN") == 0;
      break;
    case 8:
    case 0x1F:
      v65 = (__int64 *)_com_ptr_t<_com_IIID<IMSMQPropertyBag,&__s_GUID const _GUID_07f19951_ab28_11d2_8936_000000000000>>::operator->(&v86);
      v66 = *v65;
      v67 = _bstr_t::_bstr_t((_bstr_t *)&EndPtr, L"MessageBody");
      if ( *(_QWORD *)v67 )
        v68 = **(_QWORD **)v67;
      else
        v68 = 0;
      (*(void (__fastcall **)(__int64 *, __int64, VARIANTARG *))(v66 + 64))(v65, v68, &pvarg);
      _bstr_t::_Free((_bstr_t *)&EndPtr);
      _variant_t::_variant_t(&pvargDest, &pvarg);
      _bstr_t::_bstr_t((_bstr_t *)&v91, (const struct _variant_t *)&pvargDest);
      _variant_t::~_variant_t((_variant_t *)&pvargDest);
      v69 = 0;
      if ( _bstr_t::length((_bstr_t *)&v91) )
      {
        if ( v84 )
          v70 = *v84;
        else
          v70 = 0;
        if ( v91 )
          v71 = *v91;
        else
          v71 = 0;
        v69 = wcsstr(v71, v70);
      }
      if ( v7 )
        v72 = *v7;
      else
        v72 = 0;
      if ( _wcsicmp(v72, L"$MSG_BODY_CONTAINS") )
        v73 = v69 == 0;
      else
        v73 = v69 != 0;
      *a4 = v73;
      goto LABEL_164;
    case 0x2011:
      v60 = (__int64 *)_com_ptr_t<_com_IIID<IMSMQPropertyBag,&__s_GUID const _GUID_07f19951_ab28_11d2_8936_000000000000>>::operator->(&v86);
      v61 = *v60;
      v62 = _bstr_t::_bstr_t((_bstr_t *)&EndPtr, L"MessageBody");
      if ( *(_QWORD *)v62 )
        v63 = **(_QWORD **)v62;
      else
        v63 = 0;
      (*(void (__fastcall **)(__int64 *, __int64, VARIANTARG *))(v61 + 64))(v60, v63, &pvarg);
      _bstr_t::_Free((_bstr_t *)&EndPtr);
      _variant_t::_variant_t(&pvargDest, &pvarg);
      _bstr_t::_bstr_t((_bstr_t *)&v91, (const struct _variant_t *)&pvargDest);
      _variant_t::~_variant_t((_variant_t *)&pvargDest);
      if ( _bstr_t::length((_bstr_t *)&v91)
        || (!v7 ? (v64 = 0) : (v64 = *v7), _wcsicmp(v64, L"$MSG_BODY_DOES_NOT_CONTAIN")) )
      {
        v55 = 0;
      }
      *a4 = v55;
LABEL_164:
      _bstr_t::_Free((_bstr_t *)&v91);
      break;
  }
  VariantClear(&pvarg);
  if ( a2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 16LL))(a2);
  CStringTokens::~CStringTokens((CStringTokens *)v89);
  _bstr_t::_Free((_bstr_t *)&v84);
  _bstr_t::_Free((_bstr_t *)&v85);
  _bstr_t::_Free(v90);
  return 0;
}

```

## disassembly

```asm
0x180005df4  mov     rax, rsp
0x180005df7  mov     [rax+18h], r8
0x180005dfb  mov     [rax+8], rcx
0x180005dff  push    rbx
0x180005e00  push    rdi
0x180005e01  push    r12
0x180005e03  push    r13
0x180005e05  push    r14
0x180005e07  push    r15
0x180005e09  sub     rsp, 0D8h
0x180005e10  mov     r12, r9
0x180005e13  mov     r13, r8
0x180005e16  mov     [rax-40h], r8
0x180005e1a  mov     rdi, rdx
0x180005e1d  lea     rdx, psz; wchar_t *
0x180005e24  lea     rcx, [rsp+108h+var_A0]; this
0x180005e29  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x180005e2e  nop
0x180005e2f  lea     rdx, psz; wchar_t *
0x180005e36  lea     rcx, [rsp+108h+var_A8]; this
0x180005e3b  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x180005e40  nop
0x180005e41  lea     rcx, [rsp+108h+var_60]; this
0x180005e49  call    ??0CStringTokens@@QEAA@XZ; CStringTokens::CStringTokens(void)
0x180005e4e  nop
0x180005e4f  mov     [rsp+108h+var_98], rdi
0x180005e54  test    rdi, rdi
0x180005e57  jz      short loc_180005E69
0x180005e59  mov     rax, [rdi]
0x180005e5c  mov     rcx, rdi
0x180005e5f  mov     rax, [rax+8]
0x180005e63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e68  nop
0x180005e69  xorps   xmm0, xmm0
0x180005e6c  xor     eax, eax
0x180005e6e  movups  xmmword ptr [rsp+108h+pvarg], xmm0
0x180005e73  mov     qword ptr [rsp+108h+pvarg+10h], rax
0x180005e7b  lea     rcx, [rsp+108h+pvarg]; pvarg
0x180005e80  call    cs:__imp_VariantInit
0x180005e86  mov     dword ptr [r12], 0
0x180005e8e  mov     r8d, 3Dh ; '='; wchar_t
0x180005e94  mov     rdx, r13; struct _bstr_t *
0x180005e97  lea     rcx, [rsp+108h+var_60]; this
0x180005e9f  call    ?Parse@CStringTokens@@QEAAXAEBV_bstr_t@@_W@Z; CStringTokens::Parse(_bstr_t const &,wchar_t)
0x180005ea4  lea     r8, [rsp+108h+var_A0]; struct _bstr_t *
0x180005ea9  xor     edx, edx; unsigned int
0x180005eab  lea     rcx, [rsp+108h+var_60]; this
0x180005eb3  call    ?GetToken@CStringTokens@@QEAAXKAEAV_bstr_t@@@Z; CStringTokens::GetToken(ulong,_bstr_t &)
0x180005eb8  mov     rbx, [rsp+108h+var_A0]
0x180005ebd  test    rbx, rbx
0x180005ec0  jz      short loc_180005EC7
0x180005ec2  mov     rcx, [rbx]
0x180005ec5  jmp     short loc_180005EC9
0x180005ec7  xor     ecx, ecx; String1
0x180005ec9  lea     rdx, aMsgLabelContai; "$MSG_LABEL_CONTAINS"
0x180005ed0  call    cs:__imp__wcsicmp
0x180005ed6  test    eax, eax
0x180005ed8  jz      loc_18000688B
0x180005ede  test    rbx, rbx
0x180005ee1  jz      short loc_180005EE8
0x180005ee3  mov     rcx, [rbx]
0x180005ee6  jmp     short loc_180005EEA
0x180005ee8  xor     ecx, ecx; String1
0x180005eea  lea     rdx, aMsgLabelDoesNo; "$MSG_LABEL_DOES_NOT_CONTAIN"
0x180005ef1  call    cs:__imp__wcsicmp
0x180005ef7  test    eax, eax
0x180005ef9  jz      loc_18000688B
0x180005eff  test    rbx, rbx
0x180005f02  jz      short loc_180005F09
0x180005f04  mov     rcx, [rbx]
0x180005f07  jmp     short loc_180005F0B
0x180005f09  xor     ecx, ecx; String1
0x180005f0b  lea     rdx, aMsgBodyContain; "$MSG_BODY_CONTAINS"
0x180005f12  call    cs:__imp__wcsicmp
0x180005f18  test    eax, eax
0x180005f1a  jz      loc_1800065A6
0x180005f20  test    rbx, rbx
0x180005f23  jz      short loc_180005F2A
0x180005f25  mov     rcx, [rbx]
0x180005f28  jmp     short loc_180005F2C
0x180005f2a  xor     ecx, ecx; String1
0x180005f2c  lea     rdx, aMsgBodyDoesNot; "$MSG_BODY_DOES_NOT_CONTAIN"
0x180005f33  call    cs:__imp__wcsicmp
0x180005f39  test    eax, eax
0x180005f3b  jz      loc_1800065A6
0x180005f41  test    rbx, rbx
0x180005f44  jz      short loc_180005F4B
0x180005f46  mov     rcx, [rbx]
0x180005f49  jmp     short loc_180005F4D
0x180005f4b  xor     ecx, ecx; String1
0x180005f4d  lea     rdx, aMsgPriorityGre; "$MSG_PRIORITY_GREATER_THAN"
0x180005f54  call    cs:__imp__wcsicmp
0x180005f5a  test    eax, eax
0x180005f5c  jz      loc_18000644B
0x180005f62  test    rbx, rbx
0x180005f65  jz      short loc_180005F6C
0x180005f67  mov     rcx, [rbx]
0x180005f6a  jmp     short loc_180005F6E
0x180005f6c  xor     ecx, ecx; String1
0x180005f6e  lea     rdx, aMsgPriorityLes; "$MSG_PRIORITY_LESS_THAN"
0x180005f75  call    cs:__imp__wcsicmp
0x180005f7b  test    eax, eax
0x180005f7d  jz      loc_18000644B
0x180005f83  test    rbx, rbx
0x180005f86  jz      short loc_180005F8D
0x180005f88  mov     rcx, [rbx]
0x180005f8b  jmp     short loc_180005F8F
0x180005f8d  xor     ecx, ecx; String1
0x180005f8f  lea     rdx, aMsgPriorityEqu; "$MSG_PRIORITY_EQUALS"
0x180005f96  call    cs:__imp__wcsicmp
0x180005f9c  test    eax, eax
0x180005f9e  jz      loc_18000644B
0x180005fa4  test    rbx, rbx
0x180005fa7  jz      short loc_180005FAE
0x180005fa9  mov     rcx, [rbx]
0x180005fac  jmp     short loc_180005FB0
0x180005fae  xor     ecx, ecx; String1
0x180005fb0  lea     rdx, aMsgPriorityNot; "$MSG_PRIORITY_NOT_EQUAL"
0x180005fb7  call    cs:__imp__wcsicmp
0x180005fbd  test    eax, eax
0x180005fbf  jz      loc_18000644B
0x180005fc5  test    rbx, rbx
0x180005fc8  jz      short loc_180005FCF
0x180005fca  mov     rcx, [rbx]
0x180005fcd  jmp     short loc_180005FD1
0x180005fcf  xor     ecx, ecx; String1
0x180005fd1  lea     rdx, aMsgAppspecific_1; "$MSG_APPSPECIFIC_GREATER_THAN"
0x180005fd8  call    cs:__imp__wcsicmp
0x180005fde  test    eax, eax
0x180005fe0  jz      loc_1800062D6
0x180005fe6  test    rbx, rbx
0x180005fe9  jz      short loc_180005FF0
0x180005feb  mov     rcx, [rbx]
0x180005fee  jmp     short loc_180005FF2
0x180005ff0  xor     ecx, ecx; String1
0x180005ff2  lea     rdx, aMsgAppspecific; "$MSG_APPSPECIFIC_LESS_THAN"
0x180005ff9  call    cs:__imp__wcsicmp
0x180005fff  test    eax, eax
0x180006001  jz      loc_1800062D6
0x180006007  test    rbx, rbx
0x18000600a  jz      short loc_180006011
0x18000600c  mov     rcx, [rbx]
0x18000600f  jmp     short loc_180006013
0x180006011  xor     ecx, ecx; String1
0x180006013  lea     rdx, aMsgAppspecific_2; "$MSG_APPSPECIFIC_EQUALS"
0x18000601a  call    cs:__imp__wcsicmp
0x180006020  test    eax, eax
0x180006022  jz      loc_1800062D6
0x180006028  test    rbx, rbx
0x18000602b  jz      short loc_180006032
0x18000602d  mov     rcx, [rbx]
0x180006030  jmp     short loc_180006034
0x180006032  xor     ecx, ecx; String1
0x180006034  lea     rdx, aMsgAppspecific_3; "$MSG_APPSPECIFIC_NOT_EQUAL"
0x18000603b  call    cs:__imp__wcsicmp
0x180006041  test    eax, eax
0x180006043  jz      loc_1800062D6
0x180006049  test    rbx, rbx
0x18000604c  jz      short loc_180006053
0x18000604e  mov     rcx, [rbx]
0x180006051  jmp     short loc_180006055
0x180006053  xor     ecx, ecx; String1
0x180006055  lea     rdx, aMsgSrcmachinei; "$MSG_SRCMACHINEID_EQUALS"
0x18000605c  call    cs:__imp__wcsicmp
0x180006062  test    eax, eax
0x180006064  jz      loc_180006175
0x18000606a  test    rbx, rbx
0x18000606d  jz      short loc_180006074
0x18000606f  mov     rcx, [rbx]
0x180006072  jmp     short loc_180006076
0x180006074  xor     ecx, ecx; String1
0x180006076  lea     rdx, aMsgSrcmachinei_1; "$MSG_SRCMACHINEID_NOT_EQUAL"
0x18000607d  call    cs:__imp__wcsicmp
0x180006083  test    eax, eax
0x180006085  jz      loc_180006175
0x18000608b  lea     rcx, [rsp+108h+pvarg]; pvarg
0x180006090  call    cs:__imp_VariantClear
0x180006096  mov     eax, 46h ; 'F'
0x18000609b  mov     word ptr [rsp+108h+arg_8], ax
0x1800060a3  mov     dword ptr [rsp+108h+EndPtr], 0C00E0E07h
0x1800060ae  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, 0; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x1800060b6  jz      short loc_18000612A
0x1800060b8  lea     rbx, aTrigobjsRulehd; "trigobjs/rulehdlr"
0x1800060bf  mov     rcx, rbx; wchar_t *
0x1800060c2  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x1800060c7  lea     r9d, [rax+1]
0x1800060cb  add     r9, r9
0x1800060ce  mov     [rsp+108h+var_B8], 0
0x1800060d7  mov     [rsp+108h+var_C0], 0
0x1800060e0  lea     rax, [rsp+108h+EndPtr]
0x1800060e8  mov     [rsp+108h+var_C8], rax
0x1800060ed  mov     [rsp+108h+var_D0], 4
0x1800060f6  lea     rax, [rsp+108h+arg_8]
0x1800060fe  mov     [rsp+108h+var_D8], rax
0x180006103  mov     [rsp+108h+var_E0], 2
0x18000610c  mov     [rsp+108h+var_E8], rbx
0x180006111  mov     r14d, 1
0x180006117  mov     r8d, r14d
0x18000611a  mov     edx, r14d
0x18000611d  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180006124  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x180006129  nop
0x18000612a  test    rdi, rdi
0x18000612d  jz      short loc_18000613F
0x18000612f  mov     rax, [rdi]
0x180006132  mov     rcx, rdi
0x180006135  mov     rax, [rax+10h]
0x180006139  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000613e  nop
0x18000613f  lea     rcx, [rsp+108h+var_60]; this
0x180006147  call    ??1CStringTokens@@UEAA@XZ; CStringTokens::~CStringTokens(void)
0x18000614c  nop
0x18000614d  lea     rcx, [rsp+108h+var_A8]; this
0x180006152  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180006157  nop
0x180006158  lea     rcx, [rsp+108h+var_A0]; this
0x18000615d  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180006162  nop
0x180006163  mov     rcx, r13; this
0x180006166  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000616b  mov     eax, 0C00E0E07h
0x180006170  jmp     loc_180006A36
0x180006175  lea     r8, [rsp+108h+var_A8]; struct _bstr_t *
0x18000617a  mov     edx, 1; unsigned int
0x18000617f  lea     rcx, [rsp+108h+var_60]; this
0x180006187  call    ?GetToken@CStringTokens@@QEAAXKAEAV_bstr_t@@@Z; CStringTokens::GetToken(ulong,_bstr_t &)
0x18000618c  lea     rcx, [rsp+108h+var_98]
0x180006191  call    ??C?$_com_ptr_t@V?$_com_IIID@UIMSMQPropertyBag@@$1?_GUID_07f19951_ab28_11d2_8936_000000000000@@3U__s_GUID@@B@@@@QEBAPEAUIMSMQPropertyBag@@XZ; _com_ptr_t<_com_IIID<IMSMQPropertyBag,&__s_GUID const _GUID_07f19951_ab28_11d2_8936_000000000000>>::operator->(void)
0x180006196  mov     r14, rax
0x180006199  mov     r15, [rax]
0x18000619c  lea     rdx, aSrcmachineid; "SrcMachineId"
0x1800061a3  lea     rcx, [rsp+108h+EndPtr]; this
0x1800061ab  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x1800061b0  nop
0x1800061b1  mov     rcx, [rax]
0x1800061b4  test    rcx, rcx
0x1800061b7  jz      short loc_1800061BE
0x1800061b9  mov     rdx, [rcx]
0x1800061bc  jmp     short loc_1800061C0
0x1800061be  xor     edx, edx
0x1800061c0  lea     r8, [rsp+108h+pvarg]
0x1800061c5  mov     rcx, r14
0x1800061c8  mov     rax, [r15+40h]
0x1800061cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061d1  nop
0x1800061d2  lea     rcx, [rsp+108h+EndPtr]; this
0x1800061da  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800061df  lea     rdx, [rsp+108h+pvarg]; pvargSrc
0x1800061e4  lea     rcx, [rsp+108h+pvargDest]; pvargDest
0x1800061ec  call    ??0_variant_t@@QEAA@AEBUtagVARIANT@@@Z; _variant_t::_variant_t(tagVARIANT const &)
0x1800061f1  nop
0x1800061f2  lea     rdx, [rsp+108h+pvargDest]; struct _variant_t *
0x1800061fa  lea     rcx, [rsp+108h+arg_8]; this
0x180006202  call    ??0_bstr_t@@QEAA@AEBV_variant_t@@@Z; _bstr_t::_bstr_t(_variant_t const &)
0x180006207  nop
0x180006208  lea     rcx, [rsp+108h+pvargDest]; this
0x180006210  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180006215  mov     rax, [rsp+108h+var_A8]
0x18000621a  test    rax, rax
0x18000621d  jz      short loc_180006224
0x18000621f  mov     rdx, [rax]
0x180006222  jmp     short loc_180006226
0x180006224  xor     edx, edx; String2
0x180006226  mov     rax, [rsp+108h+arg_8]
0x18000622e  test    rax, rax
0x180006231  jz      short loc_180006238
0x180006233  mov     rcx, [rax]
0x180006236  jmp     short loc_18000623A
0x180006238  xor     ecx, ecx; String1
0x18000623a  call    cs:__imp__wcsicmp
0x180006240  mov     r14d, eax
0x180006243  test    rbx, rbx
0x180006246  jz      short loc_18000624D
0x180006248  mov     rcx, [rbx]
0x18000624b  jmp     short loc_18000624F
0x18000624d  xor     ecx, ecx; String1
0x18000624f  lea     rdx, aMsgSrcmachinei; "$MSG_SRCMACHINEID_EQUALS"
0x180006256  call    cs:__imp__wcsicmp
0x18000625c  test    eax, eax
0x18000625e  jnz     short loc_180006268
0x180006260  test    r14d, r14d
0x180006263  setz    al
0x180006266  jmp     short loc_180006270
0x180006268  xor     eax, eax
0x18000626a  test    r14d, r14d
0x18000626d  setnz   al
0x180006270  mov     [r12], eax
0x180006274  lea     rcx, [rsp+108h+pvarg]; pvarg
0x180006279  call    cs:__imp_VariantClear
0x18000627f  nop
0x180006280  lea     rcx, [rsp+108h+arg_8]; this
0x180006288  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000628d  nop
0x18000628e  test    rdi, rdi
0x180006291  jz      short loc_1800062A3
0x180006293  mov     rax, [rdi]
0x180006296  mov     rcx, rdi
0x180006299  mov     rax, [rax+10h]
0x18000629d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062a2  nop
  ... truncated ...
```
