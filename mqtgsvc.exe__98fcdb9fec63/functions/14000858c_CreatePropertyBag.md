# CreatePropertyBag

- ea: `0x14000858c`
- end: `0x140008b59`
- name: `CreatePropertyBag`
- size: `1485`
- prototype: `void __fastcall(__int64, __int64, IUnknown *, LPVOID *)`
- caller_count: `1`
- callee_count: `20`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140009238`

## callees

- `0x140001cc6`
- `0x1400030ac`
- `0x140003104`
- `0x1400031a0`
- `0x1400032a0`
- `0x140003378`
- `0x14000339c`
- `0x140003474`
- `0x140003530`
- `0x1400035a0`
- `0x140003630`
- `0x140003868`
- `0x140003dc8`
- `0x140007554`
- `0x140007f4c`
- `0x140008034`
- `0x1400083b0`
- `0x14000858c`
- `0x14000a3a8`
- `0x14000f8f4`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x140008872`
- `OLEAUT32!__imp_VariantInit` at `0x1400089d4`
- `OLEAUT32!__imp_VariantInit` at `0x140008a53`
- `OLEAUT32!__imp_VariantInit` at `0x140008872`
- `OLEAUT32!__imp_VariantInit` at `0x1400089d4`
- `OLEAUT32!__imp_VariantInit` at `0x140008a53`

## string_xrefs

- `0x140008912`: `QueueNamePathname`

## pseudocode

```c
void __fastcall CreatePropertyBag(__int64 a1, __int64 a2, IUnknown *a3, LPVOID *a4)
{
  int Instance; // ebx
  struct IUnknown *v9; // rdi
  __int128 *Label; // rbx
  _bstr_t *v11; // rax
  struct IUnknown *v12; // rdi
  __int128 *MessageID; // rbx
  _bstr_t *v14; // rax
  struct IUnknown *v15; // rdi
  __int128 *MsgBody; // rbx
  _bstr_t *v17; // rax
  struct IUnknown *v18; // rbx
  LONG v19; // ecx
  _bstr_t *v20; // rax
  struct IUnknown *v21; // rdi
  __int128 *CorrelationID; // rbx
  _bstr_t *v23; // rax
  struct IUnknown *v24; // rdi
  __int128 *Priority; // rbx
  _bstr_t *v26; // rax
  struct IUnknown *v27; // rbx
  _bstr_t *v28; // rax
  struct IUnknown *v29; // rbx
  _bstr_t *v30; // rax
  struct IUnknown *v31; // rbx
  _bstr_t *v32; // rax
  struct IUnknown *v33; // rbx
  _bstr_t *v34; // rax
  struct IUnknown *v35; // rbx
  _bstr_t *v36; // rax
  struct IUnknown *v37; // rbx
  _bstr_t *v38; // rax
  struct IUnknown *v39; // rbx
  _bstr_t *v40; // rax
  struct IUnknown *v41; // rbx
  _bstr_t *v42; // rax
  struct IUnknown *v43; // rbx
  _bstr_t *v44; // rax
  struct IUnknown *v45; // rdi
  __int128 *SrcMachineId; // rbx
  _bstr_t *v47; // rax
  struct IUnknown *v48; // rdi
  __int128 *MsgLookupID; // rbx
  _bstr_t *v50; // rax
  _BYTE v51[8]; // [rsp+20h] [rbp-49h] BYREF
  _BYTE v52[8]; // [rsp+28h] [rbp-41h] BYREF
  VARIANTARG pvarg; // [rsp+30h] [rbp-39h] BYREF
  VARIANTARG pExceptionObject; // [rsp+50h] [rbp-19h] BYREF
  VARIANTARG pvargSrc; // [rsp+70h] [rbp+7h] BYREF

  Instance = _com_ptr_t<_com_IIID<IMSMQPropertyBag,&__s_GUID const _GUID_07f19951_ab28_11d2_8936_000000000000>>::CreateInstance(
               a4,
               a2,
               a3,
               0x17u);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_1833f040ae3e358d840c1ed912348424_Traceguids);
    bad_win32_error::bad_win32_error((bad_win32_error *)&pExceptionObject, Instance);
    throw (bad_hresult *)&pExceptionObject;
  }
  v9 = (struct IUnknown *)_com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->((__int64 *)a4);
  Label = (__int128 *)CMsgProperties::GetLabel(a1, &pExceptionObject);
  v11 = _bstr_t::_bstr_t((_bstr_t *)v52, L"Label");
  IMSMQPropertyBag::Write(v9, v11, Label);
  _variant_t::~_variant_t(&pExceptionObject);
  v12 = (struct IUnknown *)_com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->((__int64 *)a4);
  MessageID = (__int128 *)CMsgProperties::GetMessageID(a1, &pExceptionObject);
  v14 = _bstr_t::_bstr_t((_bstr_t *)v52, L"MessageID");
  IMSMQPropertyBag::Write(v12, v14, MessageID);
  _variant_t::~_variant_t(&pExceptionObject);
  v15 = (struct IUnknown *)_com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->((__int64 *)a4);
  MsgBody = (__int128 *)CMsgProperties::GetMsgBody(a1, &pExceptionObject);
  v17 = _bstr_t::_bstr_t((_bstr_t *)v52, L"MessageBody");
  IMSMQPropertyBag::Write(v15, v17, MsgBody);
  _variant_t::~_variant_t(&pExceptionObject);
  v18 = (struct IUnknown *)_com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->((__int64 *)a4);
  v19 = *(_DWORD *)(a1 + 400);
  pvarg.vt = 3;
  pvarg.lVal = v19;
  v20 = _bstr_t::_bstr_t((_bstr_t *)v52, L"MessageBodyType");
  IMSMQPropertyBag::Write(v18, v20, (__int128 *)&pvarg);
  _variant_t::~_variant_t(&pvarg);
  v21 = (struct IUnknown *)_com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->((__int64 *)a4);
  CorrelationID = (__int128 *)CMsgProperties::GetCorrelationID(a1, &pExceptionObject);
  v23 = _bstr_t::_bstr_t((_bstr_t *)v52, L"CorrelationID");
  IMSMQPropertyBag::Write(v21, v23, CorrelationID);
  _variant_t::~_variant_t(&pExceptionObject);
  v24 = (struct IUnknown *)_com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->((__int64 *)a4);
  Priority = (__int128 *)CMsgProperties::GetPriority(a1, &pExceptionObject);
  v26 = _bstr_t::_bstr_t((_bstr_t *)v52, L"MessagePriority");
  IMSMQPropertyBag::Write(v24, v26, Priority);
  _variant_t::~_variant_t(&pExceptionObject);
  v27 = (struct IUnknown *)_com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->((__int64 *)a4);
  _bstr_t::_bstr_t((_bstr_t *)v52, *(const wchar_t **)(a1 + 256));
  _variant_t::_variant_t((_variant_t *)&pvarg, (const struct _bstr_t *)v52);
  v28 = _bstr_t::_bstr_t((_bstr_t *)v51, L"ResponseQueueName");
  IMSMQPropertyBag::Write(v27, v28, (__int128 *)&pvarg);
  _variant_t::~_variant_t(&pvarg);
  _bstr_t::_Free((_bstr_t *)v52);
  v29 = (struct IUnknown *)_com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->((__int64 *)a4);
  _bstr_t::_bstr_t((_bstr_t *)v52, *(const wchar_t **)(a1 + 304));
  _variant_t::_variant_t((_variant_t *)&pvarg, (const struct _bstr_t *)v52);
  v30 = _bstr_t::_bstr_t((_bstr_t *)v51, L"AdminQueueName");
  IMSMQPropertyBag::Write(v29, v30, (__int128 *)&pvarg);
  _variant_t::~_variant_t(&pvarg);
  _bstr_t::_Free((_bstr_t *)v52);
  v31 = (struct IUnknown *)_com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->((__int64 *)a4);
  VariantInit(&pvarg);
  pvarg.vt = 19;
  pvarg.lVal = *(_DWORD *)(a1 + 208);
  v32 = _bstr_t::_bstr_t((_bstr_t *)v51, L"AppSpecific");
  IMSMQPropertyBag::Write(v31, v32, (__int128 *)&pvarg);
  _variant_t::~_variant_t(&pvarg);
  v33 = (struct IUnknown *)_com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->((__int64 *)a4);
  _variant_t::_variant_t((_variant_t *)&pvarg, (const struct _bstr_t *)a3);
  v34 = _bstr_t::_bstr_t((_bstr_t *)v51, L"QueueNameFormatname");
  IMSMQPropertyBag::Write(v33, v34, (__int128 *)&pvarg);
  _variant_t::~_variant_t(&pvarg);
  v35 = (struct IUnknown *)_com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->((__int64 *)a4);
  _variant_t::_variant_t((_variant_t *)&pvarg, (const struct _bstr_t *)(a2 + 2096));
  v36 = _bstr_t::_bstr_t((_bstr_t *)v51, L"QueueNamePathname");
  IMSMQPropertyBag::Write(v35, v36, (__int128 *)&pvarg);
  _variant_t::~_variant_t(&pvarg);
  v37 = (struct IUnknown *)_com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->((__int64 *)a4);
  _variant_t::_variant_t((_variant_t *)&pvarg, (const struct _bstr_t *)(a2 + 2088));
  v38 = _bstr_t::_bstr_t((_bstr_t *)v51, L"TriggerName");
  IMSMQPropertyBag::Write(v37, v38, (__int128 *)&pvarg);
  _variant_t::~_variant_t(&pvarg);
  v39 = (struct IUnknown *)_com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->((__int64 *)a4);
  _variant_t::_variant_t((_variant_t *)&pvarg, (const struct _bstr_t *)(a2 + 2080));
  v40 = _bstr_t::_bstr_t((_bstr_t *)v51, L"TriggerID");
  IMSMQPropertyBag::Write(v39, v40, (__int128 *)&pvarg);
  _variant_t::~_variant_t(&pvarg);
  v41 = (struct IUnknown *)_com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->((__int64 *)a4);
  VariantInit(&pvarg);
  GetVariantTimeOfTime(*(unsigned int *)(a1 + 352), &pvarg);
  pvargSrc = pvarg;
  pvarg.vt = 0;
  _variant_t::_variant_t(&pExceptionObject, &pvargSrc);
  _variant_t::~_variant_t(&pvarg);
  v42 = _bstr_t::_bstr_t((_bstr_t *)v51, L"SentTime");
  IMSMQPropertyBag::Write(v41, v42, (__int128 *)&pExceptionObject);
  _variant_t::~_variant_t(&pExceptionObject);
  v43 = (struct IUnknown *)_com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->((__int64 *)a4);
  VariantInit(&pvarg);
  GetVariantTimeOfTime(*(unsigned int *)(a1 + 328), &pvarg);
  pExceptionObject = pvarg;
  pvarg.vt = 0;
  _variant_t::_variant_t(&pvargSrc, &pExceptionObject);
  _variant_t::~_variant_t(&pvarg);
  v44 = _bstr_t::_bstr_t((_bstr_t *)v51, L"ArrivedTime");
  IMSMQPropertyBag::Write(v43, v44, (__int128 *)&pvargSrc);
  _variant_t::~_variant_t(&pvargSrc);
  v45 = (struct IUnknown *)_com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->((__int64 *)a4);
  SrcMachineId = (__int128 *)CMsgProperties::GetSrcMachineId(a1, &pExceptionObject);
  v47 = _bstr_t::_bstr_t((_bstr_t *)v51, L"SrcMachineId");
  IMSMQPropertyBag::Write(v45, v47, SrcMachineId);
  _variant_t::~_variant_t(&pExceptionObject);
  v48 = (struct IUnknown *)_com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->((__int64 *)a4);
  MsgLookupID = (__int128 *)CMsgProperties::GetMsgLookupID(a1, &pExceptionObject);
  v50 = _bstr_t::_bstr_t((_bstr_t *)v51, L"LookupId");
  IMSMQPropertyBag::Write(v48, v50, MsgLookupID);
  _variant_t::~_variant_t(&pExceptionObject);
}

```

## disassembly

```asm
0x14000858c  push    rbp
0x14000858e  push    rbx
0x14000858f  push    rsi
0x140008590  push    rdi
0x140008591  push    r12
0x140008593  push    r14
0x140008595  push    r15
0x140008597  lea     rbp, [rsp-27h]
0x14000859c  sub     rsp, 90h
0x1400085a3  mov     rsi, r9
0x1400085a6  mov     r12, r8
0x1400085a9  mov     r15, rdx
0x1400085ac  mov     r14, rcx
0x1400085af  mov     r9d, 17h
0x1400085b5  mov     rcx, rsi; ppv
0x1400085b8  call    ?CreateInstance@?$_com_ptr_t@V?$_com_IIID@UIMSMQPropertyBag@@$1?_GUID_07f19951_ab28_11d2_8936_000000000000@@3U__s_GUID@@B@@@@QEAAJAEBU_GUID@@PEAUIUnknown@@K@Z; _com_ptr_t<_com_IIID<IMSMQPropertyBag,&__s_GUID const _GUID_07f19951_ab28_11d2_8936_000000000000>>::CreateInstance(_GUID const &,IUnknown *,ulong)
0x1400085bd  mov     ebx, eax
0x1400085bf  test    eax, eax
0x1400085c1  jns     short loc_140008610
0x1400085c3  lea     rax, WPP_GLOBAL_Control
0x1400085ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1400085d1  cmp     rcx, rax
0x1400085d4  jz      short loc_1400085F4
0x1400085d6  test    byte ptr [rcx+1Ch], 1
0x1400085da  jz      short loc_1400085F4
0x1400085dc  mov     edx, 20h ; ' '
0x1400085e1  mov     r9d, ebx
0x1400085e4  lea     r8, WPP_1833f040ae3e358d840c1ed912348424_Traceguids
0x1400085eb  mov     rcx, [rcx+10h]
0x1400085ef  call    WPP_SF_d
0x1400085f4  mov     edx, ebx; unsigned int
0x1400085f6  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1400085fa  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x1400085ff  lea     rdx, _TI3?AVbad_hresult@@; pThrowInfo
0x140008606  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14000860a  call    _CxxThrowException_0
0x140008610  mov     rcx, rsi
0x140008613  call    ??C?$_com_ptr_t@V?$_com_IIID@UIMSMQRuleHandler@@$1?_GUID_b0cdbf11_9774_11d2_8929_000000000000@@3U__s_GUID@@B@@@@QEBAPEAUIMSMQRuleHandler@@XZ; _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->(void)
0x140008618  mov     rdi, rax
0x14000861b  lea     rdx, [rbp+57h+pExceptionObject]
0x14000861f  mov     rcx, r14
0x140008622  call    ?GetLabel@CMsgProperties@@QEBA?AV_variant_t@@XZ; CMsgProperties::GetLabel(void)
0x140008627  mov     rbx, rax
0x14000862a  lea     rdx, aLabel; "Label"
0x140008631  lea     rcx, [rbp+57h+var_98]; this
0x140008635  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x14000863a  mov     r8, rbx
0x14000863d  mov     rdx, rax
0x140008640  mov     rcx, rdi
0x140008643  call    ?Write@IMSMQPropertyBag@@QEAAJV_bstr_t@@AEBV_variant_t@@@Z; IMSMQPropertyBag::Write(_bstr_t,_variant_t const &)
0x140008648  nop
0x140008649  lea     rcx, [rbp+57h+pExceptionObject]; this
0x14000864d  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x140008652  mov     rcx, rsi
0x140008655  call    ??C?$_com_ptr_t@V?$_com_IIID@UIMSMQRuleHandler@@$1?_GUID_b0cdbf11_9774_11d2_8929_000000000000@@3U__s_GUID@@B@@@@QEBAPEAUIMSMQRuleHandler@@XZ; _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->(void)
0x14000865a  mov     rdi, rax
0x14000865d  lea     rdx, [rbp+57h+pExceptionObject]
0x140008661  mov     rcx, r14
0x140008664  call    ?GetMessageID@CMsgProperties@@QEBA?AV_variant_t@@XZ; CMsgProperties::GetMessageID(void)
0x140008669  mov     rbx, rax
0x14000866c  lea     rdx, aMessageid; "MessageID"
0x140008673  lea     rcx, [rbp+57h+var_98]; this
0x140008677  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x14000867c  mov     r8, rbx
0x14000867f  mov     rdx, rax
0x140008682  mov     rcx, rdi
0x140008685  call    ?Write@IMSMQPropertyBag@@QEAAJV_bstr_t@@AEBV_variant_t@@@Z; IMSMQPropertyBag::Write(_bstr_t,_variant_t const &)
0x14000868a  nop
0x14000868b  lea     rcx, [rbp+57h+pExceptionObject]; this
0x14000868f  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x140008694  mov     rcx, rsi
0x140008697  call    ??C?$_com_ptr_t@V?$_com_IIID@UIMSMQRuleHandler@@$1?_GUID_b0cdbf11_9774_11d2_8929_000000000000@@3U__s_GUID@@B@@@@QEBAPEAUIMSMQRuleHandler@@XZ; _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->(void)
0x14000869c  mov     rdi, rax
0x14000869f  lea     rdx, [rbp+57h+pExceptionObject]
0x1400086a3  mov     rcx, r14
0x1400086a6  call    ?GetMsgBody@CMsgProperties@@QEBA?AV_variant_t@@XZ; CMsgProperties::GetMsgBody(void)
0x1400086ab  mov     rbx, rax
0x1400086ae  lea     rdx, aMessagebody; "MessageBody"
0x1400086b5  lea     rcx, [rbp+57h+var_98]; this
0x1400086b9  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x1400086be  mov     r8, rbx
0x1400086c1  mov     rdx, rax
0x1400086c4  mov     rcx, rdi
0x1400086c7  call    ?Write@IMSMQPropertyBag@@QEAAJV_bstr_t@@AEBV_variant_t@@@Z; IMSMQPropertyBag::Write(_bstr_t,_variant_t const &)
0x1400086cc  nop
0x1400086cd  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1400086d1  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1400086d6  mov     rcx, rsi
0x1400086d9  call    ??C?$_com_ptr_t@V?$_com_IIID@UIMSMQRuleHandler@@$1?_GUID_b0cdbf11_9774_11d2_8929_000000000000@@3U__s_GUID@@B@@@@QEBAPEAUIMSMQRuleHandler@@XZ; _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->(void)
0x1400086de  mov     rbx, rax
0x1400086e1  mov     ecx, [r14+190h]
0x1400086e8  mov     eax, 3
0x1400086ed  mov     word ptr [rbp+57h+pvarg], ax
0x1400086f1  mov     word ptr [rbp+57h+pvarg+8], cx
0x1400086f5  sar     ecx, 10h
0x1400086f8  mov     word ptr [rbp+57h+pvarg+0Ah], cx
0x1400086fc  lea     rdx, aMessagebodytyp; "MessageBodyType"
0x140008703  lea     rcx, [rbp+57h+var_98]; this
0x140008707  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x14000870c  lea     r8, [rbp+57h+pvarg]
0x140008710  mov     rdx, rax
0x140008713  mov     rcx, rbx
0x140008716  call    ?Write@IMSMQPropertyBag@@QEAAJV_bstr_t@@AEBV_variant_t@@@Z; IMSMQPropertyBag::Write(_bstr_t,_variant_t const &)
0x14000871b  nop
0x14000871c  lea     rcx, [rbp+57h+pvarg]; this
0x140008720  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x140008725  mov     rcx, rsi
0x140008728  call    ??C?$_com_ptr_t@V?$_com_IIID@UIMSMQRuleHandler@@$1?_GUID_b0cdbf11_9774_11d2_8929_000000000000@@3U__s_GUID@@B@@@@QEBAPEAUIMSMQRuleHandler@@XZ; _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->(void)
0x14000872d  mov     rdi, rax
0x140008730  lea     rdx, [rbp+57h+pExceptionObject]
0x140008734  mov     rcx, r14
0x140008737  call    ?GetCorrelationID@CMsgProperties@@QEBA?AV_variant_t@@XZ; CMsgProperties::GetCorrelationID(void)
0x14000873c  mov     rbx, rax
0x14000873f  lea     rdx, aCorrelationid; "CorrelationID"
0x140008746  lea     rcx, [rbp+57h+var_98]; this
0x14000874a  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x14000874f  mov     r8, rbx
0x140008752  mov     rdx, rax
0x140008755  mov     rcx, rdi
0x140008758  call    ?Write@IMSMQPropertyBag@@QEAAJV_bstr_t@@AEBV_variant_t@@@Z; IMSMQPropertyBag::Write(_bstr_t,_variant_t const &)
0x14000875d  nop
0x14000875e  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140008762  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x140008767  mov     rcx, rsi
0x14000876a  call    ??C?$_com_ptr_t@V?$_com_IIID@UIMSMQRuleHandler@@$1?_GUID_b0cdbf11_9774_11d2_8929_000000000000@@3U__s_GUID@@B@@@@QEBAPEAUIMSMQRuleHandler@@XZ; _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->(void)
0x14000876f  mov     rdi, rax
0x140008772  lea     rdx, [rbp+57h+pExceptionObject]
0x140008776  mov     rcx, r14
0x140008779  call    ?GetPriority@CMsgProperties@@QEBA?AV_variant_t@@XZ; CMsgProperties::GetPriority(void)
0x14000877e  mov     rbx, rax
0x140008781  lea     rdx, aMessagepriorit; "MessagePriority"
0x140008788  lea     rcx, [rbp+57h+var_98]; this
0x14000878c  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x140008791  mov     r8, rbx
0x140008794  mov     rdx, rax
0x140008797  mov     rcx, rdi
0x14000879a  call    ?Write@IMSMQPropertyBag@@QEAAJV_bstr_t@@AEBV_variant_t@@@Z; IMSMQPropertyBag::Write(_bstr_t,_variant_t const &)
0x14000879f  nop
0x1400087a0  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1400087a4  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1400087a9  mov     rcx, rsi
0x1400087ac  call    ??C?$_com_ptr_t@V?$_com_IIID@UIMSMQRuleHandler@@$1?_GUID_b0cdbf11_9774_11d2_8929_000000000000@@3U__s_GUID@@B@@@@QEBAPEAUIMSMQRuleHandler@@XZ; _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->(void)
0x1400087b1  mov     rbx, rax
0x1400087b4  mov     rdx, [r14+100h]; wchar_t *
0x1400087bb  lea     rcx, [rbp+57h+var_98]; this
0x1400087bf  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x1400087c4  nop
0x1400087c5  lea     rdx, [rbp+57h+var_98]; struct _bstr_t *
0x1400087c9  lea     rcx, [rbp+57h+pvarg]; this
0x1400087cd  call    ??0_variant_t@@QEAA@AEBV_bstr_t@@@Z; _variant_t::_variant_t(_bstr_t const &)
0x1400087d2  nop
0x1400087d3  lea     rdx, aResponsequeuen; "ResponseQueueName"
0x1400087da  lea     rcx, [rbp+57h+var_A0]; this
0x1400087de  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x1400087e3  lea     r8, [rbp+57h+pvarg]
0x1400087e7  mov     rdx, rax
0x1400087ea  mov     rcx, rbx
0x1400087ed  call    ?Write@IMSMQPropertyBag@@QEAAJV_bstr_t@@AEBV_variant_t@@@Z; IMSMQPropertyBag::Write(_bstr_t,_variant_t const &)
0x1400087f2  nop
0x1400087f3  lea     rcx, [rbp+57h+pvarg]; this
0x1400087f7  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1400087fc  nop
0x1400087fd  lea     rcx, [rbp+57h+var_98]; this
0x140008801  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x140008806  mov     rcx, rsi
0x140008809  call    ??C?$_com_ptr_t@V?$_com_IIID@UIMSMQRuleHandler@@$1?_GUID_b0cdbf11_9774_11d2_8929_000000000000@@3U__s_GUID@@B@@@@QEBAPEAUIMSMQRuleHandler@@XZ; _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->(void)
0x14000880e  mov     rbx, rax
0x140008811  mov     rdx, [r14+130h]; wchar_t *
0x140008818  lea     rcx, [rbp+57h+var_98]; this
0x14000881c  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x140008821  nop
0x140008822  lea     rdx, [rbp+57h+var_98]; struct _bstr_t *
0x140008826  lea     rcx, [rbp+57h+pvarg]; this
0x14000882a  call    ??0_variant_t@@QEAA@AEBV_bstr_t@@@Z; _variant_t::_variant_t(_bstr_t const &)
0x14000882f  nop
0x140008830  lea     rdx, aAdminqueuename; "AdminQueueName"
0x140008837  lea     rcx, [rbp+57h+var_A0]; this
0x14000883b  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x140008840  lea     r8, [rbp+57h+pvarg]
0x140008844  mov     rdx, rax
0x140008847  mov     rcx, rbx
0x14000884a  call    ?Write@IMSMQPropertyBag@@QEAAJV_bstr_t@@AEBV_variant_t@@@Z; IMSMQPropertyBag::Write(_bstr_t,_variant_t const &)
0x14000884f  nop
0x140008850  lea     rcx, [rbp+57h+pvarg]; this
0x140008854  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x140008859  nop
0x14000885a  lea     rcx, [rbp+57h+var_98]; this
0x14000885e  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x140008863  mov     rcx, rsi
0x140008866  call    ??C?$_com_ptr_t@V?$_com_IIID@UIMSMQRuleHandler@@$1?_GUID_b0cdbf11_9774_11d2_8929_000000000000@@3U__s_GUID@@B@@@@QEBAPEAUIMSMQRuleHandler@@XZ; _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->(void)
0x14000886b  mov     rbx, rax
0x14000886e  lea     rcx, [rbp+57h+pvarg]; pvarg
0x140008872  call    cs:__imp_VariantInit
0x140008878  nop
0x140008879  mov     eax, 13h
0x14000887e  mov     word ptr [rbp+57h+pvarg], ax
0x140008882  mov     ecx, [r14+0D0h]
0x140008889  mov     dword ptr [rbp+57h+pvarg+8], ecx
0x14000888c  lea     rdx, aAppspecific; "AppSpecific"
0x140008893  lea     rcx, [rbp+57h+var_A0]; this
0x140008897  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x14000889c  lea     r8, [rbp+57h+pvarg]
0x1400088a0  mov     rdx, rax
0x1400088a3  mov     rcx, rbx
0x1400088a6  call    ?Write@IMSMQPropertyBag@@QEAAJV_bstr_t@@AEBV_variant_t@@@Z; IMSMQPropertyBag::Write(_bstr_t,_variant_t const &)
0x1400088ab  nop
0x1400088ac  lea     rcx, [rbp+57h+pvarg]; this
0x1400088b0  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1400088b5  mov     rcx, rsi
0x1400088b8  call    ??C?$_com_ptr_t@V?$_com_IIID@UIMSMQRuleHandler@@$1?_GUID_b0cdbf11_9774_11d2_8929_000000000000@@3U__s_GUID@@B@@@@QEBAPEAUIMSMQRuleHandler@@XZ; _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->(void)
0x1400088bd  mov     rbx, rax
0x1400088c0  mov     rdx, r12; struct _bstr_t *
0x1400088c3  lea     rcx, [rbp+57h+pvarg]; this
0x1400088c7  call    ??0_variant_t@@QEAA@AEBV_bstr_t@@@Z; _variant_t::_variant_t(_bstr_t const &)
0x1400088cc  nop
0x1400088cd  lea     rdx, aQueuenameforma; "QueueNameFormatname"
0x1400088d4  lea     rcx, [rbp+57h+var_A0]; this
0x1400088d8  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x1400088dd  lea     r8, [rbp+57h+pvarg]
0x1400088e1  mov     rdx, rax
0x1400088e4  mov     rcx, rbx
0x1400088e7  call    ?Write@IMSMQPropertyBag@@QEAAJV_bstr_t@@AEBV_variant_t@@@Z; IMSMQPropertyBag::Write(_bstr_t,_variant_t const &)
0x1400088ec  nop
0x1400088ed  lea     rcx, [rbp+57h+pvarg]; this
0x1400088f1  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1400088f6  mov     rcx, rsi
0x1400088f9  call    ??C?$_com_ptr_t@V?$_com_IIID@UIMSMQRuleHandler@@$1?_GUID_b0cdbf11_9774_11d2_8929_000000000000@@3U__s_GUID@@B@@@@QEBAPEAUIMSMQRuleHandler@@XZ; _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->(void)
0x1400088fe  mov     rbx, rax
0x140008901  lea     rdx, [r15+830h]; struct _bstr_t *
0x140008908  lea     rcx, [rbp+57h+pvarg]; this
0x14000890c  call    ??0_variant_t@@QEAA@AEBV_bstr_t@@@Z; _variant_t::_variant_t(_bstr_t const &)
0x140008911  nop
0x140008912  lea     rdx, aQueuenamepathn; "QueueNamePathname"
0x140008919  lea     rcx, [rbp+57h+var_A0]; this
0x14000891d  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x140008922  lea     r8, [rbp+57h+pvarg]
0x140008926  mov     rdx, rax
0x140008929  mov     rcx, rbx
0x14000892c  call    ?Write@IMSMQPropertyBag@@QEAAJV_bstr_t@@AEBV_variant_t@@@Z; IMSMQPropertyBag::Write(_bstr_t,_variant_t const &)
0x140008931  nop
0x140008932  lea     rcx, [rbp+57h+pvarg]; this
0x140008936  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x14000893b  mov     rcx, rsi
0x14000893e  call    ??C?$_com_ptr_t@V?$_com_IIID@UIMSMQRuleHandler@@$1?_GUID_b0cdbf11_9774_11d2_8929_000000000000@@3U__s_GUID@@B@@@@QEBAPEAUIMSMQRuleHandler@@XZ; _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->(void)
0x140008943  mov     rbx, rax
0x140008946  lea     rdx, [r15+828h]; struct _bstr_t *
0x14000894d  lea     rcx, [rbp+57h+pvarg]; this
0x140008951  call    ??0_variant_t@@QEAA@AEBV_bstr_t@@@Z; _variant_t::_variant_t(_bstr_t const &)
0x140008956  nop
0x140008957  lea     rdx, aTriggername; "TriggerName"
0x14000895e  lea     rcx, [rbp+57h+var_A0]; this
0x140008962  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x140008967  lea     r8, [rbp+57h+pvarg]
0x14000896b  mov     rdx, rax
0x14000896e  mov     rcx, rbx
0x140008971  call    ?Write@IMSMQPropertyBag@@QEAAJV_bstr_t@@AEBV_variant_t@@@Z; IMSMQPropertyBag::Write(_bstr_t,_variant_t const &)
0x140008976  nop
0x140008977  lea     rcx, [rbp+57h+pvarg]; this
0x14000897b  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x140008980  mov     rcx, rsi
0x140008983  call    ??C?$_com_ptr_t@V?$_com_IIID@UIMSMQRuleHandler@@$1?_GUID_b0cdbf11_9774_11d2_8929_000000000000@@3U__s_GUID@@B@@@@QEBAPEAUIMSMQRuleHandler@@XZ; _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->(void)
0x140008988  mov     rbx, rax
0x14000898b  lea     rdx, [r15+820h]; struct _bstr_t *
0x140008992  lea     rcx, [rbp+57h+pvarg]; this
0x140008996  call    ??0_variant_t@@QEAA@AEBV_bstr_t@@@Z; _variant_t::_variant_t(_bstr_t const &)
0x14000899b  nop
0x14000899c  lea     rdx, aTriggerid; "TriggerID"
0x1400089a3  lea     rcx, [rbp+57h+var_A0]; this
0x1400089a7  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x1400089ac  lea     r8, [rbp+57h+pvarg]
0x1400089b0  mov     rdx, rax
0x1400089b3  mov     rcx, rbx
0x1400089b6  call    ?Write@IMSMQPropertyBag@@QEAAJV_bstr_t@@AEBV_variant_t@@@Z; IMSMQPropertyBag::Write(_bstr_t,_variant_t const &)
0x1400089bb  nop
0x1400089bc  lea     rcx, [rbp+57h+pvarg]; this
0x1400089c0  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1400089c5  mov     rcx, rsi
0x1400089c8  call    ??C?$_com_ptr_t@V?$_com_IIID@UIMSMQRuleHandler@@$1?_GUID_b0cdbf11_9774_11d2_8929_000000000000@@3U__s_GUID@@B@@@@QEBAPEAUIMSMQRuleHandler@@XZ; _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->(void)
0x1400089cd  mov     rbx, rax
0x1400089d0  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1400089d4  call    cs:__imp_VariantInit
0x1400089da  nop
0x1400089db  mov     ecx, [r14+160h]; __int64
0x1400089e2  lea     rdx, [rbp+57h+pvarg]; struct tagVARIANT *
0x1400089e6  call    ?GetVariantTimeOfTime@@YAJ_JPEAUtagVARIANT@@@Z; GetVariantTimeOfTime(__int64,tagVARIANT *)
0x1400089eb  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x1400089ef  movups  xmmword ptr [rbp+57h+pvargSrc], xmm0
0x1400089f3  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x1400089f8  movsd   qword ptr [rbp+57h+pvargSrc+10h], xmm1
0x1400089fd  xor     eax, eax
0x1400089ff  mov     word ptr [rbp+57h+pvarg], ax
0x140008a03  lea     rdx, [rbp+57h+pvargSrc]; pvargSrc
0x140008a07  lea     rcx, [rbp+57h+pExceptionObject]; pvargDest
0x140008a0b  call    ??0_variant_t@@QEAA@AEBV0@@Z; _variant_t::_variant_t(_variant_t const &)
0x140008a10  nop
0x140008a11  lea     rcx, [rbp+57h+pvarg]; this
0x140008a15  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x140008a1a  nop
0x140008a1b  lea     rdx, aSenttime; "SentTime"
0x140008a22  lea     rcx, [rbp+57h+var_A0]; this
  ... truncated ...
```
