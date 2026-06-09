# CMSMQRuleHandler::GetArgumentValue(IMSMQPropertyBag *,_bstr_t,tagVARIANT *)

- ea: `0x180006ef0`
- end: `0x1800082b2`
- name: `?GetArgumentValue@CMSMQRuleHandler@@QEAAJPEAUIMSMQPropertyBag@@V_bstr_t@@PEAUtagVARIANT@@@Z`
- size: `5058`
- prototype: `__int64 __fastcall(__int64, __int64, const wchar_t ***, VARIANTARG *)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008d68`
- `0x180009420`

## callees

- `0x180004d20`
- `0x180004dfc`
- `0x18000544c`
- `0x1800057c8`
- `0x180005c10`
- `0x180006ef0`
- `0x180008d14`
- `0x180009ab0`
- `0x180014d30`
- `0x180015e5c`
- `0x180022010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180006f50`
- `msvcrt!_wcsicmp` at `0x180007055`
- `msvcrt!_wcsicmp` at `0x18000715a`
- `msvcrt!_wcsicmp` at `0x18000725f`
- `msvcrt!_wcsicmp` at `0x18000740d`
- `msvcrt!_wcsicmp` at `0x180007512`
- `msvcrt!_wcsicmp` at `0x180007617`
- `msvcrt!_wcsicmp` at `0x18000771c`
- `msvcrt!_wcsicmp` at `0x180007821`
- `msvcrt!_wcsicmp` at `0x180007926`
- `msvcrt!_wcsicmp` at `0x180007a2b`
- `msvcrt!_wcsicmp` at `0x180007b30`
- `msvcrt!_wcsicmp` at `0x180007c35`
- `msvcrt!_wcsicmp` at `0x180007d3a`
- `msvcrt!_wcsicmp` at `0x180007e3f`
- `msvcrt!_wcsicmp` at `0x180007f44`
- `msvcrt!_wcsicmp` at `0x180008049`
- `msvcrt!_wcsicmp` at `0x180006f50`
- `msvcrt!_wcsicmp` at `0x180007055`
- `msvcrt!_wcsicmp` at `0x18000715a`
- `msvcrt!_wcsicmp` at `0x18000725f`
- `msvcrt!_wcsicmp` at `0x18000740d`
- `msvcrt!_wcsicmp` at `0x180007512`
- `msvcrt!_wcsicmp` at `0x180007617`
- `msvcrt!_wcsicmp` at `0x18000771c`
- `msvcrt!_wcsicmp` at `0x180007821`
- `msvcrt!_wcsicmp` at `0x180007926`
- `msvcrt!_wcsicmp` at `0x180007a2b`
- `msvcrt!_wcsicmp` at `0x180007b30`
- `msvcrt!_wcsicmp` at `0x180007c35`
- `msvcrt!_wcsicmp` at `0x180007d3a`
- `msvcrt!_wcsicmp` at `0x180007e3f`
- `msvcrt!_wcsicmp` at `0x180007f44`
- `msvcrt!_wcsicmp` at `0x180008049`
- `OLEAUT32!__imp_VariantInit` at `0x18000817a`
- `OLEAUT32!__imp_VariantInit` at `0x18000817a`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800081ad`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800081ad`

## string_xrefs

- `0x180007638`: `QueueNamePathname`
- `0x180007610`: `$MSG_QUEUE_PATHNAME`

## pseudocode

```c
__int64 __fastcall CMSMQRuleHandler::GetArgumentValue(__int64 a1, __int64 a2, const wchar_t ***a3, VARIANTARG *a4)
{
  int v7; // r12d
  const wchar_t *v8; // rcx
  __int64 v9; // rsi
  __int64 (__fastcall *v10)(__int64, __int64, VARIANTARG *); // r14
  _bstr_t *v11; // rax
  __int64 v12; // rdx
  HRESULT v13; // edi
  unsigned int v14; // eax
  const wchar_t *v15; // rcx
  __int64 v16; // rsi
  __int64 (__fastcall *v17)(__int64, __int64, VARIANTARG *); // r14
  _bstr_t *v18; // rax
  __int64 v19; // rdx
  unsigned int v20; // eax
  const wchar_t *v21; // rcx
  __int64 v22; // rsi
  __int64 (__fastcall *v23)(__int64, __int64, VARIANTARG *); // r14
  _bstr_t *v24; // rax
  __int64 v25; // rdx
  unsigned int v26; // eax
  const wchar_t *v27; // rcx
  __int64 v28; // rsi
  __int64 (__fastcall *v29)(__int64, __int64, VARIANTARG *); // r14
  _bstr_t *v30; // rax
  __int64 v31; // rdx
  unsigned int v32; // eax
  unsigned int v33; // eax
  const wchar_t *v34; // rcx
  __int64 v35; // rsi
  __int64 (__fastcall *v36)(__int64, __int64, VARIANTARG *); // r14
  _bstr_t *v37; // rax
  __int64 v38; // rdx
  unsigned int v39; // eax
  const wchar_t *v40; // rcx
  __int64 v41; // rsi
  __int64 (__fastcall *v42)(__int64, __int64, VARIANTARG *); // r14
  _bstr_t *v43; // rax
  __int64 v44; // rdx
  unsigned int v45; // eax
  const wchar_t *v46; // rcx
  __int64 v47; // rsi
  __int64 (__fastcall *v48)(__int64, __int64, VARIANTARG *); // r14
  _bstr_t *v49; // rax
  __int64 v50; // rdx
  unsigned int v51; // eax
  const wchar_t *v52; // rcx
  __int64 v53; // rsi
  __int64 (__fastcall *v54)(__int64, __int64, VARIANTARG *); // r14
  _bstr_t *v55; // rax
  __int64 v56; // rdx
  unsigned int v57; // eax
  const wchar_t *v58; // rcx
  __int64 v59; // rsi
  __int64 (__fastcall *v60)(__int64, __int64, VARIANTARG *); // r14
  _bstr_t *v61; // rax
  __int64 v62; // rdx
  unsigned int v63; // eax
  const wchar_t *v64; // rcx
  __int64 v65; // rsi
  __int64 (__fastcall *v66)(__int64, __int64, VARIANTARG *); // r14
  _bstr_t *v67; // rax
  __int64 v68; // rdx
  unsigned int v69; // eax
  const wchar_t *v70; // rcx
  __int64 v71; // rsi
  __int64 (__fastcall *v72)(__int64, __int64, VARIANTARG *); // r14
  _bstr_t *v73; // rax
  __int64 v74; // rdx
  unsigned int v75; // eax
  const wchar_t *v76; // rcx
  __int64 v77; // rsi
  __int64 (__fastcall *v78)(__int64, __int64, VARIANTARG *); // r14
  _bstr_t *v79; // rax
  __int64 v80; // rdx
  unsigned int v81; // eax
  const wchar_t *v82; // rcx
  __int64 v83; // rsi
  __int64 (__fastcall *v84)(__int64, __int64, VARIANTARG *); // r14
  _bstr_t *v85; // rax
  __int64 v86; // rdx
  unsigned int v87; // eax
  const wchar_t *v88; // rcx
  __int64 v89; // rsi
  __int64 (__fastcall *v90)(__int64, __int64, VARIANTARG *); // r14
  _bstr_t *v91; // rax
  __int64 v92; // rdx
  unsigned int v93; // eax
  const wchar_t *v94; // rcx
  __int64 v95; // rsi
  __int64 (__fastcall *v96)(__int64, __int64, VARIANTARG *); // r14
  _bstr_t *v97; // rax
  __int64 v98; // rdx
  unsigned int v99; // eax
  const wchar_t *v100; // rcx
  __int64 v101; // rsi
  __int64 (__fastcall *v102)(__int64, __int64, VARIANTARG *); // r14
  _bstr_t *v103; // rax
  __int64 v104; // rdx
  unsigned int v105; // eax
  const wchar_t *v106; // rcx
  CMSMQRuleHandler *v107; // rcx
  __int64 v108; // rsi
  __int64 (__fastcall *v109)(__int64, __int64, VARIANTARG *); // r14
  _bstr_t *v110; // rax
  __int64 v111; // rdx
  unsigned int v112; // eax
  CMSMQRuleHandler *v113; // rcx
  LONGLONG v114; // rax
  unsigned int v115; // eax
  HRESULT v117; // [rsp+60h] [rbp-9h] BYREF
  __int64 v118; // [rsp+68h] [rbp-1h] BYREF
  VARIANTARG pvarg; // [rsp+70h] [rbp+7h] BYREF
  __int16 v120; // [rsp+D8h] [rbp+6Fh] BYREF
  const wchar_t ***v121; // [rsp+E0h] [rbp+77h]

  v121 = a3;
  v118 = a2;
  v7 = 0;
  if ( a2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
  if ( *a3 )
    v8 = **a3;
  else
    v8 = 0;
  if ( !_wcsicmp(v8, L"$MSG_ID") )
  {
    v9 = _com_ptr_t<_com_IIID<IMSMQPropertyBag,&__s_GUID const _GUID_07f19951_ab28_11d2_8936_000000000000>>::operator->(&v118);
    v10 = *(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v9 + 64LL);
    v11 = _bstr_t::_bstr_t((_bstr_t *)&v120, L"MessageID");
    if ( *(_QWORD *)v11 )
      v12 = **(_QWORD **)v11;
    else
      v12 = 0;
    v13 = v10(v9, v12, a4);
    _bstr_t::_Free((_bstr_t *)&v120);
    if ( v13 < 0 )
    {
      v120 = 400;
      v117 = v13;
      if ( g_pMSMQErrorLoggingTrace )
      {
        v14 = mqwcslen(L"trigobjs/rulehdlr");
        CMSMQTrace::MSMQTraceEvent(
          g_pMSMQErrorLoggingTrace,
          1,
          1,
          2LL * (v14 + 1),
          L"trigobjs/rulehdlr",
          2,
          &v120,
          4,
          &v117,
          0,
          0);
      }
    }
    if ( a2 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 16LL))(a2);
    goto LABEL_245;
  }
  if ( *a3 )
    v15 = **a3;
  else
    v15 = 0;
  if ( !_wcsicmp(v15, L"$MSG_LABEL") )
  {
    v16 = _com_ptr_t<_com_IIID<IMSMQPropertyBag,&__s_GUID const _GUID_07f19951_ab28_11d2_8936_000000000000>>::operator->(&v118);
    v17 = *(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v16 + 64LL);
    v18 = _bstr_t::_bstr_t((_bstr_t *)&v120, L"Label");
    if ( *(_QWORD *)v18 )
      v19 = **(_QWORD **)v18;
    else
      v19 = 0;
    v13 = v17(v16, v19, a4);
    _bstr_t::_Free((_bstr_t *)&v120);
    if ( v13 < 0 )
    {
      v120 = 410;
      v117 = v13;
      if ( g_pMSMQErrorLoggingTrace )
      {
        v20 = mqwcslen(L"trigobjs/rulehdlr");
        CMSMQTrace::MSMQTraceEvent(
          g_pMSMQErrorLoggingTrace,
          1,
          1,
          2LL * (v20 + 1),
          L"trigobjs/rulehdlr",
          2,
          &v120,
          4,
          &v117,
          0,
          0);
      }
    }
    if ( a2 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 16LL))(a2);
    goto LABEL_245;
  }
  if ( *a3 )
    v21 = **a3;
  else
    v21 = 0;
  if ( !_wcsicmp(v21, L"$MSG_BODY") )
  {
    v22 = _com_ptr_t<_com_IIID<IMSMQPropertyBag,&__s_GUID const _GUID_07f19951_ab28_11d2_8936_000000000000>>::operator->(&v118);
    v23 = *(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v22 + 64LL);
    v24 = _bstr_t::_bstr_t((_bstr_t *)&v120, L"MessageBody");
    if ( *(_QWORD *)v24 )
      v25 = **(_QWORD **)v24;
    else
      v25 = 0;
    v13 = v23(v22, v25, a4);
    _bstr_t::_Free((_bstr_t *)&v120);
    if ( v13 < 0 )
    {
      v120 = 420;
      v117 = v13;
      if ( g_pMSMQErrorLoggingTrace )
      {
        v26 = mqwcslen(L"trigobjs/rulehdlr");
        CMSMQTrace::MSMQTraceEvent(
          g_pMSMQErrorLoggingTrace,
          1,
          1,
          2LL * (v26 + 1),
          L"trigobjs/rulehdlr",
          2,
          &v120,
          4,
          &v117,
          0,
          0);
      }
    }
    if ( a2 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 16LL))(a2);
    goto LABEL_245;
  }
  if ( *a3 )
    v27 = **a3;
  else
    v27 = 0;
  if ( _wcsicmp(v27, L"$MSG_BODY_AS_STRING") )
  {
    if ( *a3 )
      v34 = **a3;
    else
      v34 = 0;
    if ( _wcsicmp(v34, L"$MSG_PRIORITY") )
    {
      if ( *a3 )
        v40 = **a3;
      else
        v40 = 0;
      if ( _wcsicmp(v40, L"$MSG_CORRELATION_ID") )
      {
        if ( *a3 )
          v46 = **a3;
        else
          v46 = 0;
        if ( _wcsicmp(v46, L"$MSG_QUEUE_PATHNAME") )
        {
          if ( *a3 )
            v52 = **a3;
          else
            v52 = 0;
          if ( _wcsicmp(v52, L"$MSG_QUEUE_FORMATNAME") )
          {
            if ( *a3 )
              v58 = **a3;
            else
              v58 = 0;
            if ( _wcsicmp(v58, L"$MSG_APPSPECIFIC") )
            {
              if ( *a3 )
                v64 = **a3;
              else
                v64 = 0;
              if ( _wcsicmp(v64, L"$MSG_RESPONSE_QUEUE_FORMATNAME") )
              {
                if ( *a3 )
                  v70 = **a3;
                else
                  v70 = 0;
                if ( _wcsicmp(v70, L"$MSG_ADMIN_QUEUE_FORMATNAME") )
                {
                  if ( *a3 )
                    v76 = **a3;
                  else
                    v76 = 0;
                  if ( _wcsicmp(v76, L"$MSG_ARRIVEDTIME") )
                  {
                    if ( *a3 )
                      v82 = **a3;
                    else
                      v82 = 0;
                    if ( _wcsicmp(v82, L"$MSG_SENTTIME") )
                    {
                      if ( *a3 )
                        v88 = **a3;
                      else
                        v88 = 0;
                      if ( _wcsicmp(v88, L"$MSG_SRCMACHINEID") )
                      {
                        if ( *a3 )
                          v94 = **a3;
                        else
                          v94 = 0;
                        if ( _wcsicmp(v94, L"$MSG_LOOKUP_ID") )
                        {
                          if ( *a3 )
                            v100 = **a3;
                          else
                            v100 = 0;
                          if ( _wcsicmp(v100, L"$TRIGGER_NAME") )
                          {
                            if ( *a3 )
                              v106 = **a3;
                            else
                              v106 = 0;
                            if ( _wcsicmp(v106, L"$TRIGGER_ID") )
                            {
                              if ( CMSMQRuleHandler::IsEnclosedInQuotes(v107, (const struct _bstr_t *)a3) )
                              {
                                CMSMQRuleHandler::ConvertToUnquotedVariant(v113, (const struct _bstr_t *)a3, a4);
                                if ( a2 )
                                  (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 16LL))(a2);
                                goto LABEL_54;
                              }
                              memset(&pvarg, 0, sizeof(pvarg));
                              VariantInit(&pvarg);
                              pvarg.vt = 8;
                              if ( *a3 )
                                v114 = (LONGLONG)**a3;
                              else
                                v114 = 0;
                              pvarg.llVal = v114;
                              v13 = VariantChangeType(a4, &pvarg, 0, 3u);
                              if ( v13 < 0 )
                              {
                                v120 = 570;
                                v117 = v13;
                                if ( g_pMSMQErrorLoggingTrace )
                                {
                                  v115 = mqwcslen(L"trigobjs/rulehdlr");
                                  CMSMQTrace::MSMQTraceEvent(
                                    g_pMSMQErrorLoggingTrace,
                                    1,
                                    1,
                                    2LL * (v115 + 1),
                                    L"trigobjs/rulehdlr",
                                    2,
                                    &v120,
                                    4,
                                    &v117,
                                    0,
                                    0);
                                }
                                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                                {
                                  WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13);
                                }
                              }
                              if ( a2 )
                                (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 16LL))(a2);
                            }
                            else
                            {
                              v108 = _com_ptr_t<_com_IIID<IMSMQPropertyBag,&__s_GUID const _GUID_07f19951_ab28_11d2_8936_000000000000>>::operator->(&v118);
                              v109 = *(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v108 + 64LL);
                              v110 = _bstr_t::_bstr_t((_bstr_t *)&v120, L"TriggerID");
                              if ( *(_QWORD *)v110 )
                                v111 = **(_QWORD **)v110;
                              else
                                v111 = 0;
                              v13 = v109(v108, v111, a4);
                              _bstr_t::_Free((_bstr_t *)&v120);
                              if ( v13 < 0 )
                              {
                                v120 = 560;
                                v117 = v13;
                                if ( g_pMSMQErrorLoggingTrace )
                                {
                                  v112 = mqwcslen(L"trigobjs/rulehdlr");
                                  CMSMQTrace::MSMQTraceEvent(
                                    g_pMSMQErrorLoggingTrace,
                                    1,
                                    1,
                                    2LL * (v112 + 1),
                                    L"trigobjs/rulehdlr",
                                    2,
                                    &v120,
                                    4,
                                    &v117,
                                    0,
                                    0);
                                }
                              }
                              if ( a2 )
                                (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 16LL))(a2);
                            }
                          }
                          else
                          {
                            v101 = _com_ptr_t<_com_IIID<IMSMQPropertyBag,&__s_GUID const _GUID_07f19951_ab28_11d2_8936_000000000000>>::operator->(&v118);
                            v102 = *(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v101 + 64LL);
                            v103 = _bstr_t::_bstr_t((_bstr_t *)&v120, L"TriggerName");
                            if ( *(_QWORD *)v103 )
                              v104 = **(_QWORD **)v103;
                            else
                              v104 = 0;
                            v13 = v102(v101, v104, a4);
                            _bstr_t::_Free((_bstr_t *)&v120);
                            if ( v13 < 0 )
                            {
                              v120 = 550;
                              v117 = v13;
                              if ( g_pMSMQErrorLoggingTrace )
                              {
                                v105 = mqwcslen(L"trigobjs/rulehdlr");
                                CMSMQTrace::MSMQTraceEvent(
                                  g_pMSMQErrorLoggingTrace,
                                  1,
                                  1,
                                  2LL * (v105 + 1),
                                  L"trigobjs/rulehdlr",
                                  2,
                                  &v120,
                                  4,
                                  &v117,
                                  0,
                                  0);
                              }
                            }
                            if ( a2 )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 16LL))(a2);
                          }
                        }
                        else
                        {
                          v95 = _com_ptr_t<_com_IIID<IMSMQPropertyBag,&__s_GUID const _GUID_07f19951_ab28_11d2_8936_000000000000>>::operator->(&v118);
                          v96 = *(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v95 + 64LL);
                          v97 = _bstr_t::_bstr_t((_bstr_t *)&v120, L"LookupId");
                          if ( *(_QWORD *)v97 )
                            v98 = **(_QWORD **)v97;
                          else
                            v98 = 0;
                          v13 = v96(v95, v98, a4);
                          _bstr_t::_Free((_bstr_t *)&v120);
                          if ( v13 < 0 )
                          {
                            v120 = 540;
                            v117 = v13;
                            if ( g_pMSMQErrorLoggingTrace )
                            {
                              v99 = mqwcslen(L"trigobjs/rulehdlr");
                              CMSMQTrace::MSMQTraceEvent(
                                g_pMSMQErrorLoggingTrace,
                                1,
                                1,
                                2LL * (v99 + 1),
                                L"trigobjs/rulehdlr",
                                2,
                                &v120,
                                4,
                                &v117,
                                0,
                                0);
                            }
                          }
                          if ( a2 )
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 16LL))(a2);
                        }
                      }
                      else
                      {
                        v89 = _com_ptr_t<_com_IIID<IMSMQPropertyBag,&__s_GUID const _GUID_07f19951_ab28_11d2_8936_000000000000>>::operator->(&v118);
                        v90 = *(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v89 + 64LL);
                        v91 = _bstr_t::_bstr_t((_bstr_t *)&v120, L"SrcMachineId");
                        if ( *(_QWORD *)v91 )
                          v92 = **(_QWORD **)v91;
                        else
                          v92 = 0;
                        v13 = v90(v89, v92, a4);
                        _bstr_t::_Free((_bstr_t *)&v120);
                        if ( v13 < 0 )
                        {
                          v120 = 530;
                          v117 = v13;
                          if ( g_pMSMQErrorLoggingTrace )
                          {
                            v93 = mqwcslen(L"trigobjs/rulehdlr");
                            CMSMQTrace::MSMQTraceEvent(
                              g_pMSMQErrorLoggingTrace,
                              1,
                              1,
                              2LL * (v93 + 1),
                              L"trigobjs/rulehdlr",
                              2,
                              &v120,
                              4,
                              &v117,
                              0,
                              0);
                          }
                        }
                        if ( a2 )
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 16LL))(a2);
                      }
                    }
                    else
                    {
                      v83 = _com_ptr_t<_com_IIID<IMSMQPropertyBag,&__s_GUID const _GUID_07f19951_ab28_11d2_8936_000000000000>>::operator->(&v118);
                      v84 = *(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v83 + 64LL);
                      v85 = _bstr_t::_bstr_t((_bstr_t *)&v120, L"SentTime");
                      if ( *(_QWORD *)v85 )
                        v86 = **(_QWORD **)v85;
                      else
                        v86 = 0;
                      v13 = v84(v83, v86, a4);
                      _bstr_t::_Free((_bstr_t *)&v120);
                      if ( v13 < 0 )
                      {
                        v120 = 520;
                        v117 = v13;
                        if ( g_pMSMQErrorLoggingTrace )
                        {
                          v87 = mqwcslen(L"trigobjs/rulehdlr");
                          CMSMQTrace::MSMQTraceEvent(
                            g_pMSMQErrorLoggingTrace,
                            1,
                            1,
                            2LL * (v87 + 1),
                            L"trigobjs/rulehdlr",
                            2,
                            &v120,
                            4,
                            &v117,
                            0,
                            0);
                        }
                      }
                      if ( a2 )
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 16LL))(a2);
                    }
                  }
                  else
                  {
                    v77 = _com_ptr_t<_com_IIID<IMSMQPropertyBag,&__s_GUID const _GUID_07f19951_ab28_11d2_8936_000000000000>>::operator->(&v118);
                    v78 = *(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v77 + 64LL);
                    v79 = _bstr_t::_bstr_t((_bstr_t *)&v120, L"ArrivedTime");
                    if ( *(_QWORD *)v79 )
                      v80 = **(_QWORD **)v79;
                    else
                      v80 = 0;
                    v13 = v78(v77, v80, a4);
                    _bstr_t::_Free((_bstr_t *)&v120);
                    if ( v13 < 0 )
                    {
                      v120 = 510;
                      v117 = v13;
                      if ( g_pMSMQErrorLoggingTrace )
                      {
                        v81 = mqwcslen(L"trigobjs/rulehdlr");
                        CMSMQTrace::MSMQTraceEvent(
                          g_pMSMQErrorLoggingTrace,
                          1,
                          1,
                          2LL * (v81 + 1),
                          L"trigobjs/rulehdlr",
                          2,
                          &v120,
                          4,
                          &v117,
                          0,
                          0);
                      }
                    }
                    if ( a2 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 16LL))(a2);
                  }
                }
                else
                {
                  v71 = _com_ptr_t<_com_IIID<IMSMQPropertyBag,&__s_GUID const _GUID_07f19951_ab28_11d2_8936_000000000000>>::operator->(&v118);
                  v72 = *(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v71 + 64LL);
                  v73 = _bstr_t::_bstr_t((_bstr_t *)&v120, L"AdminQueueName");
                  if ( *(_QWORD *)v73 )
                    v74 = **(_QWORD **)v73;
                  else
                    v74 = 0;
                  v13 = v72(v71, v74, a4);
                  _bstr_t::_Free((_bstr_t *)&v120);
                  if ( v13 < 0 )
                  {
                    v120 = 500;
                    v117 = v13;
                    if ( g_pMSMQErrorLoggingTrace )
                    {
                      v75 = mqwcslen(L"trigobjs/rulehdlr");
                      CMSMQTrace::MSMQTraceEvent(
                        g_pMSMQErrorLoggingTrace,
                        1,
                        1,
                        2LL * (v75 + 1),
                        L"trigobjs/rulehdlr",
                        2,
                        &v120,
                        4,
                        &v117,
                        0,
                        0);
                    }
                  }
                  if ( a2 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 16LL))(a2);
                }
              }
              else
              {
                v65 = _com_ptr_t<_com_IIID<IMSMQPropertyBag,&__s_GUID const _GUID_07f19951_ab28_11d2_8936_000000000000>>::operator->(&v118);
                v66 = *(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v65 + 64LL);
                v67 = _bstr_t::_bstr_t((_bstr_t *)&v120, L"ResponseQueueName");
                if ( *(_QWORD *)v67 )
                  v68 = **(_QWORD **)v67;
                else
                  v68 = 0;
                v13 = v66(v65, v68, a4);
                _bstr_t::_Free((_bstr_t *)&v120);
                if ( v13 < 0 )
                {
                  v120 = 490;
                  v117 = v13;
                  if ( g_pMSMQErrorLoggingTrace )
                  {
                    v69 = mqwcslen(L"trigobjs/rulehdlr");
                    CMSMQTrace::MSMQTraceEvent(
                      g_pMSMQErrorLoggingTrace,
                      1,
                      1,
                      2LL * (v69 + 1),
                      L"trigobjs/rulehdlr",
                      2,
                      &v120,
                      4,
                      &v117,
                      0,
                      0);
                  }
                }
                if ( a2 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 16LL))(a2);
              }
            }
            else
            {
              v59 = _com_ptr_t<_com_IIID<IMSMQPropertyBag,&__s_GUID const _GUID_07f19951_ab28_11d2_8936_000000000000>>::operator->(&v118);
              v60 = *(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v59 + 64LL);
              v61 = _bstr_t::_bstr_t((_bstr_t *)&v120, L"AppSpecific");
              if ( *(_QWORD *)v61 )
                v62 = **(_QWORD **)v61;
              else
                v62 = 0;
              v13 = v60(v59, v62, a4);
              _bstr_t::_Free((_bstr_t *)&v120);
              if ( v13 < 0 )
              {
                v120 = 480;
                v117 = v13;
                if ( g_pMSMQErrorLoggingTrace )
                {
                  v63 = mqwcslen(L"trigobjs/rulehdlr");
                  CMSMQTrace::MSMQTraceEvent(
                    g_pMSMQErrorLoggingTrace,
                    1,
                    1,
                    2LL * (v63 + 1),
                    L"trigobjs/rulehdlr",
                    2,
                    &v120,
                    4,
                    &v117,
                    0,
                    0);
                }
              }
              if ( a2 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 16LL))(a2);
            }
          }
          else
          {
            v53 = _com_ptr_t<_com_IIID<IMSMQPropertyBag,&__s_GUID const _GUID_07f19951_ab28_11d2_8936_000000000000>>::operator->(&v118);
            v54 = *(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v53 + 64LL);
            v55 = _bstr_t::_bstr_t((_bstr_t *)&v120, L"QueueNameFormatname");
            if ( *(_QWORD *)v55 )
              v56 = **(_QWORD **)v55;
            else
              v56 = 0;
            v13 = v54(v53, v56, a4);
            _bstr_t::_Free((_bstr_t *)&v120);
            if ( v13 < 0 )
            {
              v120 = 470;
              v117 = v13;
              if ( g_pMSMQErrorLoggingTrace )
              {
                v57 = mqwcslen(L"trigobjs/rulehdlr");
                CMSMQTrace::MSMQTraceEvent(
                  g_pMSMQErrorLoggingTrace,
                  1,
                  1,
                  2LL * (v57 + 1),
                  L"trigobjs/rulehdlr",
                  2,
                  &v120,
                  4,
                  &v117,
                  0,
                  0);
              }
            }
            if ( a2 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 16LL))(a2);
          }
        }
        else
        {
          v47 = _com_ptr_t<_com_IIID<IMSMQPropertyBag,&__s_GUID const _GUID_07f19951_ab28_11d2_8936_000000000000>>::operator->(&v118);
          v48 = *(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v47 + 64LL);
          v49 = _bstr_t::_bstr_t((_bstr_t *)&v120, L"QueueNamePathname");
          if ( *(_QWORD *)v49 )
            v50 = **(_QWORD **)v49;
          else
            v50 = 0;
          v13 = v48(v47, v50, a4);
          _bstr_t::_Free((_bstr_t *)&v120);
          if ( v13 < 0 )
          {
            v120 = 460;
            v117 = v13;
            if ( g_pMSMQErrorLoggingTrace )
            {
              v51 = mqwcslen(L"trigobjs/rulehdlr");
              CMSMQTrace::MSMQTraceEvent(
                g_pMSMQErrorLoggingTrace,
                1,
                1,
                2LL * (v51 + 1),
                L"trigobjs/rulehdlr",
                2,
                &v120,
                4,
                &v117,
                0,
                0);
            }
          }
          if ( a2 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 16LL))(a2);
        }
      }
      else
      {
        v41 = _com_ptr_t<_com_IIID<IMSMQPropertyBag,&__s_GUID const _GUID_07f19951_ab28_11d2_8936_000000000000>>::operator->(&v118);
        v42 = *(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v41 + 64LL);
        v43 = _bstr_t::_bstr_t((_bstr_t *)&v120, L"CorrelationID");
        if ( *(_QWORD *)v43 )
          v44 = **(_QWORD **)v43;
        else
          v44 = 0;
        v13 = v42(v41, v44, a4);
        _bstr_t::_Free((_bstr_t *)&v120);
        if ( v13 < 0 )
        {
          v120 = 450;
          v117 = v13;
          if ( g_pMSMQErrorLoggingTrace )
          {
            v45 = mqwcslen(L"trigobjs/rulehdlr");
            CMSMQTrace::MSMQTraceEvent(
              g_pMSMQErrorLoggingTrace,
              1,
              1,
              2LL * (v45 + 1),
              L"trigobjs/rulehdlr",
              2,
              &v120,
              4,
              &v117,
              0,
              0);
          }
        }
        if ( a2 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 16LL))(a2);
      }
    }
    else
    {
      v35 = _com_ptr_t<_com_IIID<IMSMQPropertyBag,&__s_GUID const _GUID_07f19951_ab28_11d2_8936_000000000000>>::operator->(&v118);
      v36 = *(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v35 + 64LL);
      v37 = _bstr_t::_bstr_t((_bstr_t *)&v120, L"MessagePriority");
      if ( *(_QWORD *)v37 )
        v38 = **(_QWORD **)v37;
      else
        v38 = 0;
      v13 = v36(v35, v38, a4);
      _bstr_t::_Free((_bstr_t *)&v120);
      if ( v13 < 0 )
      {
        v120 = 440;
        v117 = v13;
        if ( g_pMSMQErrorLoggingTrace )
        {
          v39 = mqwcslen(L"trigobjs/rulehdlr");
          CMSMQTrace::MSMQTraceEvent(
            g_pMSMQErrorLoggingTrace,
            1,
            1,
            2LL * (v39 + 1),
            L"trigobjs/rulehdlr",
            2,
            &v120,
            4,
            &v117,
            0,
            0);
        }
      }
      if ( a2 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 16LL))(a2);
    }
  }
  else
  {
    v28 = _com_ptr_t<_com_IIID<IMSMQPropertyBag,&__s_GUID const _GUID_07f19951_ab28_11d2_8936_000000000000>>::operator->(&v118);
    v29 = *(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v28 + 64LL);
    v30 = _bstr_t::_bstr_t((_bstr_t *)&v120, L"MessageBody");
    if ( *(_QWORD *)v30 )
      v31 = **(_QWORD **)v30;
    else
      v31 = 0;
    v7 = v29(v28, v31, a4);
    _bstr_t::_Free((_bstr_t *)&v120);
    if ( v7 < 0 )
    {
      v120 = 600;
      v117 = v7;
      if ( g_pMSMQErrorLoggingTrace )
      {
        v32 = mqwcslen(L"trigobjs/rulehdlr");
        CMSMQTrace::MSMQTraceEvent(
          g_pMSMQErrorLoggingTrace,
          1,
          1,
          2LL * (v32 + 1),
          L"trigobjs/rulehdlr",
          2,
          &v120,
          4,
          &v117,
          0,
          0);
      }
      if ( a2 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 16LL))(a2);
LABEL_54:
      v13 = v7;
      goto LABEL_245;
    }
    v13 = ConvertFromByteArrayToString(a4);
    if ( v13 < 0 )
    {
      v120 = 430;
      v117 = v13;
      if ( g_pMSMQErrorLoggingTrace )
      {
        v33 = mqwcslen(L"trigobjs/rulehdlr");
        CMSMQTrace::MSMQTraceEvent(
          g_pMSMQErrorLoggingTrace,
          1,
          1,
          2LL * (v33 + 1),
          L"trigobjs/rulehdlr",
          2,
          &v120,
          4,
          &v117,
          0,
          0);
      }
    }
    if ( a2 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 16LL))(a2);
  }
LABEL_245:
  _bstr_t::_Free((_bstr_t *)a3);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180006ef0  mov     [rsp-8+arg_0], rbx
0x180006ef5  mov     [rsp-8+arg_10], r8
0x180006efa  push    rbp
0x180006efb  push    rsi
0x180006efc  push    rdi
0x180006efd  push    r12
0x180006eff  push    r13
0x180006f01  push    r14
0x180006f03  push    r15
0x180006f05  lea     rbp, [rsp-27h]
0x180006f0a  sub     rsp, 90h
0x180006f11  mov     rdi, r9
0x180006f14  mov     r15, r8
0x180006f17  mov     rbx, rdx
0x180006f1a  mov     r13, rcx
0x180006f1d  mov     [rbp+57h+var_58], rdx
0x180006f21  xor     r12d, r12d
0x180006f24  test    rdx, rdx
0x180006f27  jz      short loc_180006F39
0x180006f29  mov     rax, [rdx]
0x180006f2c  mov     rcx, rdx
0x180006f2f  mov     rax, [rax+8]
0x180006f33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f38  nop
0x180006f39  mov     rax, [r15]
0x180006f3c  test    rax, rax
0x180006f3f  jz      short loc_180006F46
0x180006f41  mov     rcx, [rax]
0x180006f44  jmp     short loc_180006F49
0x180006f46  mov     rcx, r12; String1
0x180006f49  lea     rdx, aMsgId; "$MSG_ID"
0x180006f50  call    cs:__imp__wcsicmp
0x180006f56  test    eax, eax
0x180006f58  jnz     loc_18000703E
0x180006f5e  lea     rcx, [rbp+57h+var_58]
0x180006f62  call    ??C?$_com_ptr_t@V?$_com_IIID@UIMSMQPropertyBag@@$1?_GUID_07f19951_ab28_11d2_8936_000000000000@@3U__s_GUID@@B@@@@QEBAPEAUIMSMQPropertyBag@@XZ; _com_ptr_t<_com_IIID<IMSMQPropertyBag,&__s_GUID const _GUID_07f19951_ab28_11d2_8936_000000000000>>::operator->(void)
0x180006f67  mov     rsi, rax
0x180006f6a  mov     rcx, [rax]
0x180006f6d  mov     r14, [rcx+40h]
0x180006f71  lea     rdx, aMessageid; "MessageID"
0x180006f78  lea     rcx, [rbp+57h+arg_8]; this
0x180006f7c  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x180006f81  nop
0x180006f82  mov     rdx, [rax]
0x180006f85  test    rdx, rdx
0x180006f88  jz      short loc_180006F8F
0x180006f8a  mov     rdx, [rdx]
0x180006f8d  jmp     short loc_180006F92
0x180006f8f  mov     rdx, r12
0x180006f92  mov     r8, rdi
0x180006f95  mov     rcx, rsi
0x180006f98  mov     rax, r14
0x180006f9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fa0  mov     edi, eax
0x180006fa2  lea     rcx, [rbp+57h+arg_8]; this
0x180006fa6  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180006fab  test    edi, edi
0x180006fad  jns     short loc_180007024
0x180006faf  mov     eax, 190h
0x180006fb4  mov     [rbp+57h+arg_8], ax
0x180006fb8  mov     [rbp+57h+var_60], edi
0x180006fbb  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, r12; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180006fc2  jz      short loc_180007024
0x180006fc4  lea     r14, aTrigobjsRulehd; "trigobjs/rulehdlr"
0x180006fcb  mov     rcx, r14; wchar_t *
0x180006fce  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x180006fd3  mov     esi, 1
0x180006fd8  lea     r9d, [rsi+rax]
0x180006fdc  add     r9, r9
0x180006fdf  mov     [rsp+0C0h+var_70], r12
0x180006fe4  mov     [rsp+0C0h+var_78], r12
0x180006fe9  lea     rax, [rbp+57h+var_60]
0x180006fed  mov     [rsp+0C0h+var_80], rax
0x180006ff2  mov     [rsp+0C0h+var_88], 4
0x180006ffb  lea     rax, [rbp+57h+arg_8]
0x180006fff  mov     [rsp+0C0h+var_90], rax
0x180007004  mov     [rsp+0C0h+var_98], 2
0x18000700d  mov     qword ptr [rsp+0C0h+var_A0], r14
0x180007012  mov     r8d, esi
0x180007015  mov     edx, esi
0x180007017  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18000701e  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x180007023  nop
0x180007024  test    rbx, rbx
0x180007027  jz      short loc_180007039
0x180007029  mov     rax, [rbx]
0x18000702c  mov     rcx, rbx
0x18000702f  mov     rax, [rax+10h]
0x180007033  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007038  nop
0x180007039  jmp     loc_18000828D
0x18000703e  mov     rax, [r15]
0x180007041  test    rax, rax
0x180007044  jz      short loc_18000704B
0x180007046  mov     rcx, [rax]
0x180007049  jmp     short loc_18000704E
0x18000704b  mov     rcx, r12; String1
0x18000704e  lea     rdx, aMsgLabel; "$MSG_LABEL"
0x180007055  call    cs:__imp__wcsicmp
0x18000705b  test    eax, eax
0x18000705d  jnz     loc_180007143
0x180007063  lea     rcx, [rbp+57h+var_58]
0x180007067  call    ??C?$_com_ptr_t@V?$_com_IIID@UIMSMQPropertyBag@@$1?_GUID_07f19951_ab28_11d2_8936_000000000000@@3U__s_GUID@@B@@@@QEBAPEAUIMSMQPropertyBag@@XZ; _com_ptr_t<_com_IIID<IMSMQPropertyBag,&__s_GUID const _GUID_07f19951_ab28_11d2_8936_000000000000>>::operator->(void)
0x18000706c  mov     rsi, rax
0x18000706f  mov     rcx, [rax]
0x180007072  mov     r14, [rcx+40h]
0x180007076  lea     rdx, aLabel; "Label"
0x18000707d  lea     rcx, [rbp+57h+arg_8]; this
0x180007081  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x180007086  nop
0x180007087  mov     rdx, [rax]
0x18000708a  test    rdx, rdx
0x18000708d  jz      short loc_180007094
0x18000708f  mov     rdx, [rdx]
0x180007092  jmp     short loc_180007097
0x180007094  mov     rdx, r12
0x180007097  mov     r8, rdi
0x18000709a  mov     rcx, rsi
0x18000709d  mov     rax, r14
0x1800070a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070a5  mov     edi, eax
0x1800070a7  lea     rcx, [rbp+57h+arg_8]; this
0x1800070ab  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800070b0  test    edi, edi
0x1800070b2  jns     short loc_180007129
0x1800070b4  mov     eax, 19Ah
0x1800070b9  mov     [rbp+57h+arg_8], ax
0x1800070bd  mov     [rbp+57h+var_60], edi
0x1800070c0  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, r12; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x1800070c7  jz      short loc_180007129
0x1800070c9  lea     r14, aTrigobjsRulehd; "trigobjs/rulehdlr"
0x1800070d0  mov     rcx, r14; wchar_t *
0x1800070d3  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x1800070d8  mov     esi, 1
0x1800070dd  lea     r9d, [rsi+rax]
0x1800070e1  add     r9, r9
0x1800070e4  mov     [rsp+0C0h+var_70], r12
0x1800070e9  mov     [rsp+0C0h+var_78], r12
0x1800070ee  lea     rax, [rbp+57h+var_60]
0x1800070f2  mov     [rsp+0C0h+var_80], rax
0x1800070f7  mov     [rsp+0C0h+var_88], 4
0x180007100  lea     rax, [rbp+57h+arg_8]
0x180007104  mov     [rsp+0C0h+var_90], rax
0x180007109  mov     [rsp+0C0h+var_98], 2
0x180007112  mov     qword ptr [rsp+0C0h+var_A0], r14
0x180007117  mov     r8d, esi
0x18000711a  mov     edx, esi
0x18000711c  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180007123  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x180007128  nop
0x180007129  test    rbx, rbx
0x18000712c  jz      short loc_18000713E
0x18000712e  mov     rax, [rbx]
0x180007131  mov     rcx, rbx
0x180007134  mov     rax, [rax+10h]
0x180007138  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000713d  nop
0x18000713e  jmp     loc_18000828D
0x180007143  mov     rax, [r15]
0x180007146  test    rax, rax
0x180007149  jz      short loc_180007150
0x18000714b  mov     rcx, [rax]
0x18000714e  jmp     short loc_180007153
0x180007150  mov     rcx, r12; String1
0x180007153  lea     rdx, aMsgBody; "$MSG_BODY"
0x18000715a  call    cs:__imp__wcsicmp
0x180007160  test    eax, eax
0x180007162  jnz     loc_180007248
0x180007168  lea     rcx, [rbp+57h+var_58]
0x18000716c  call    ??C?$_com_ptr_t@V?$_com_IIID@UIMSMQPropertyBag@@$1?_GUID_07f19951_ab28_11d2_8936_000000000000@@3U__s_GUID@@B@@@@QEBAPEAUIMSMQPropertyBag@@XZ; _com_ptr_t<_com_IIID<IMSMQPropertyBag,&__s_GUID const _GUID_07f19951_ab28_11d2_8936_000000000000>>::operator->(void)
0x180007171  mov     rsi, rax
0x180007174  mov     rcx, [rax]
0x180007177  mov     r14, [rcx+40h]
0x18000717b  lea     rdx, aMessagebody; "MessageBody"
0x180007182  lea     rcx, [rbp+57h+arg_8]; this
0x180007186  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x18000718b  nop
0x18000718c  mov     rdx, [rax]
0x18000718f  test    rdx, rdx
0x180007192  jz      short loc_180007199
0x180007194  mov     rdx, [rdx]
0x180007197  jmp     short loc_18000719C
0x180007199  mov     rdx, r12
0x18000719c  mov     r8, rdi
0x18000719f  mov     rcx, rsi
0x1800071a2  mov     rax, r14
0x1800071a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071aa  mov     edi, eax
0x1800071ac  lea     rcx, [rbp+57h+arg_8]; this
0x1800071b0  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800071b5  test    edi, edi
0x1800071b7  jns     short loc_18000722E
0x1800071b9  mov     eax, 1A4h
0x1800071be  mov     [rbp+57h+arg_8], ax
0x1800071c2  mov     [rbp+57h+var_60], edi
0x1800071c5  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, r12; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x1800071cc  jz      short loc_18000722E
0x1800071ce  lea     r14, aTrigobjsRulehd; "trigobjs/rulehdlr"
0x1800071d5  mov     rcx, r14; wchar_t *
0x1800071d8  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x1800071dd  mov     esi, 1
0x1800071e2  lea     r9d, [rsi+rax]
0x1800071e6  add     r9, r9
0x1800071e9  mov     [rsp+0C0h+var_70], r12
0x1800071ee  mov     [rsp+0C0h+var_78], r12
0x1800071f3  lea     rax, [rbp+57h+var_60]
0x1800071f7  mov     [rsp+0C0h+var_80], rax
0x1800071fc  mov     [rsp+0C0h+var_88], 4
0x180007205  lea     rax, [rbp+57h+arg_8]
0x180007209  mov     [rsp+0C0h+var_90], rax
0x18000720e  mov     [rsp+0C0h+var_98], 2
0x180007217  mov     qword ptr [rsp+0C0h+var_A0], r14
0x18000721c  mov     r8d, esi
0x18000721f  mov     edx, esi
0x180007221  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180007228  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x18000722d  nop
0x18000722e  test    rbx, rbx
0x180007231  jz      short loc_180007243
0x180007233  mov     rax, [rbx]
0x180007236  mov     rcx, rbx
0x180007239  mov     rax, [rax+10h]
0x18000723d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007242  nop
0x180007243  jmp     loc_18000828D
0x180007248  mov     rax, [r15]
0x18000724b  test    rax, rax
0x18000724e  jz      short loc_180007255
0x180007250  mov     rcx, [rax]
0x180007253  jmp     short loc_180007258
0x180007255  mov     rcx, r12; String1
0x180007258  lea     rdx, aMsgBodyAsStrin; "$MSG_BODY_AS_STRING"
0x18000725f  call    cs:__imp__wcsicmp
0x180007265  test    eax, eax
0x180007267  jnz     loc_1800073F6
0x18000726d  lea     rcx, [rbp+57h+var_58]
0x180007271  call    ??C?$_com_ptr_t@V?$_com_IIID@UIMSMQPropertyBag@@$1?_GUID_07f19951_ab28_11d2_8936_000000000000@@3U__s_GUID@@B@@@@QEBAPEAUIMSMQPropertyBag@@XZ; _com_ptr_t<_com_IIID<IMSMQPropertyBag,&__s_GUID const _GUID_07f19951_ab28_11d2_8936_000000000000>>::operator->(void)
0x180007276  mov     rsi, rax
0x180007279  mov     rcx, [rax]
0x18000727c  mov     r14, [rcx+40h]
0x180007280  lea     rdx, aMessagebody; "MessageBody"
0x180007287  lea     rcx, [rbp+57h+arg_8]; this
0x18000728b  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x180007290  nop
0x180007291  mov     rdx, [rax]
0x180007294  test    rdx, rdx
0x180007297  jz      short loc_18000729E
0x180007299  mov     rdx, [rdx]
0x18000729c  jmp     short loc_1800072A1
0x18000729e  mov     rdx, r12
0x1800072a1  mov     r8, rdi
0x1800072a4  mov     rcx, rsi
0x1800072a7  mov     rax, r14
0x1800072aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072af  mov     r12d, eax
0x1800072b2  lea     rcx, [rbp+57h+arg_8]; this
0x1800072b6  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800072bb  xor     r13d, r13d
0x1800072be  test    r12d, r12d
0x1800072c1  jns     loc_180007359
0x1800072c7  mov     eax, 258h
0x1800072cc  mov     [rbp+57h+arg_8], ax
0x1800072d0  mov     [rbp+57h+var_60], r12d
0x1800072d4  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, r13; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x1800072db  jz      short loc_18000733C
0x1800072dd  lea     r14, aTrigobjsRulehd; "trigobjs/rulehdlr"
0x1800072e4  mov     rcx, r14; wchar_t *
0x1800072e7  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x1800072ec  lea     esi, [r13+1]
0x1800072f0  lea     r9d, [rsi+rax]
0x1800072f4  add     r9, r9
0x1800072f7  mov     [rsp+0C0h+var_70], r13
0x1800072fc  mov     [rsp+0C0h+var_78], r13
0x180007301  lea     rax, [rbp+57h+var_60]
0x180007305  mov     [rsp+0C0h+var_80], rax
0x18000730a  mov     [rsp+0C0h+var_88], 4
0x180007313  lea     rax, [rbp+57h+arg_8]
0x180007317  mov     [rsp+0C0h+var_90], rax
0x18000731c  mov     [rsp+0C0h+var_98], 2
0x180007325  mov     qword ptr [rsp+0C0h+var_A0], r14
0x18000732a  mov     r8d, esi
0x18000732d  mov     edx, esi
0x18000732f  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180007336  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x18000733b  nop
0x18000733c  test    rbx, rbx
0x18000733f  jz      short loc_180007351
0x180007341  mov     rax, [rbx]
0x180007344  mov     rcx, rbx
0x180007347  mov     rax, [rax+10h]
0x18000734b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007350  nop
0x180007351  mov     edi, r12d
0x180007354  jmp     loc_18000828D
0x180007359  mov     rcx, rdi; pvarg
0x18000735c  call    ?ConvertFromByteArrayToString@@YAJPEAUtagVARIANT@@@Z; ConvertFromByteArrayToString(tagVARIANT *)
0x180007361  mov     edi, eax
0x180007363  test    eax, eax
0x180007365  jns     short loc_1800073DC
0x180007367  mov     eax, 1AEh
  ... truncated ...
```
