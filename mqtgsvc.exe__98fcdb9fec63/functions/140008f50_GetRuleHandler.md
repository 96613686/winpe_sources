# GetRuleHandler

- ea: `0x140008f50`
- end: `0x14000912b`
- name: `GetRuleHandler`
- size: `475`
- prototype: `LPVOID *__fastcall(LPVOID *, _QWORD *)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400082d4`
- `0x140008b60`

## callees

- `0x140001cc6`
- `0x140003dc8`
- `0x1400046bc`
- `0x140004eb4`
- `0x140006458`
- `0x140007594`
- `0x140007dbc`
- `0x140008034`
- `0x140008520`
- `0x140008f50`
- `0x140009180`
- `0x140017cf4`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x140008fba`
- `KERNEL32!LeaveCriticalSection` at `0x14000911b`
- `KERNEL32!LeaveCriticalSection` at `0x140008fba`
- `KERNEL32!LeaveCriticalSection` at `0x14000911b`
- `ATL!__imp_AtlComPtrAssign` at `0x1400090f0`
- `ATL!__imp_AtlComPtrAssign` at `0x1400090f0`

## pseudocode

```c
LPVOID *__fastcall GetRuleHandler(LPVOID *a1, _QWORD *a2)
{
  _QWORD *v4; // r14
  struct _RTL_CRITICAL_SECTION *v6; // rbx
  HRESULT v7; // r15d
  __int64 v8; // r10
  int v9; // edx
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // [rsp+38h] [rbp-70h] BYREF
  _QWORD v14[2]; // [rsp+40h] [rbp-68h] BYREF
  const _com_error *v15; // [rsp+50h] [rbp-58h] BYREF
  _BYTE pExceptionObject[80]; // [rsp+58h] [rbp-50h] BYREF
  LPVOID ppv; // [rsp+C0h] [rbp+18h] BYREF
  __int64 v19; // [rsp+C8h] [rbp+20h] BYREF

  v4 = a2 + 135;
  if ( a2[135] )
  {
    _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::_com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>(
      a1,
      a2 + 135);
    return a1;
  }
  v6 = (struct _RTL_CRITICAL_SECTION *)(a2 + 136);
  v14[1] = a2 + 136;
  CCriticalSection::Lock((CCriticalSection *)(a2 + 136));
  if ( *v4 )
  {
    _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::_com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>(
      a1,
      v4);
    LeaveCriticalSection(v6);
    return a1;
  }
  ppv = 0;
  v7 = _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::CreateInstance(&ppv);
  if ( v7 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), v7);
    if ( !byte_14002AB1C )
      EvReportWithError(0xC000089F, v7, 2u, a2[1], *a2);
    bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, v7);
    throw (bad_hresult *)pExceptionObject;
  }
  try
  {
    v8 = _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->(&ppv);
    v9 = *((unsigned __int8 *)a2 + 1072);
    v10 = a2[4];
    v19 = v10;
    if ( v10 )
      _InterlockedIncrement((volatile signed __int32 *)(v10 + 16));
    v11 = a2[5];
    v13 = v11;
    if ( v11 )
      _InterlockedIncrement((volatile signed __int32 *)(v11 + 16));
    v12 = *a2;
    v14[0] = v12;
    if ( v12 )
      _InterlockedIncrement((volatile signed __int32 *)(v12 + 16));
    IMSMQRuleHandler::Init(v8, v14, &v13, &v19, v9);
    AtlComPtrAssign(v4, ppv);
    *a1 = ppv;
    _com_ptr_t<_com_IIID<IMSMQTriggersConfig,&__s_GUID const _GUID_7c55d6a1_f584_11d2_89b2_000000000000>>::_AddRef(a1);
  }
  catch ( const _com_error *v15 )
  {
    if ( (unsigned __int8)CSafeSet<_bstr_t>::insert(qword_14002AE28, a2) )
      EvReportWithError(0xC00008A0, *((_DWORD *)v15 + 2), 2u, a2[1], *a2);
    throw;
  }
  v8 = _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->(&ppv);
  v9 = *((unsigned __int8 *)a2 + 1072);
  v10 = a2[4];
}

```

## disassembly

```asm
0x140008f50  mov     [rsp+arg_8], rdx
0x140008f55  push    rbx
0x140008f56  push    rsi
0x140008f57  push    rdi
0x140008f58  push    r14
0x140008f5a  push    r15
0x140008f5c  sub     rsp, 80h
0x140008f63  mov     rsi, rdx
0x140008f66  mov     rdi, rcx
0x140008f69  lea     r14, [rdx+438h]
0x140008f70  cmp     qword ptr [r14], 0
0x140008f74  jz      short loc_140008F90
0x140008f76  mov     rdx, r14
0x140008f79  call    ??$?0V?$CComPtr@UIUnknown@@@ATL@@@?$_com_ptr_t@V?$_com_IIID@UIMSMQRuleHandler@@$1?_GUID_b0cdbf11_9774_11d2_8929_000000000000@@3U__s_GUID@@B@@@@QEAA@AEBV?$CComPtr@UIUnknown@@@ATL@@@Z; _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::_com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>(ATL::CComPtr<IUnknown> const &)
0x140008f7e  mov     rax, rdi
0x140008f81  add     rsp, 80h
0x140008f88  pop     r15
0x140008f8a  pop     r14
0x140008f8c  pop     rdi
0x140008f8d  pop     rsi
0x140008f8e  pop     rbx
0x140008f8f  retn
0x140008f90  lea     rbx, [rdx+440h]
0x140008f97  mov     [rsp+0A8h+var_60], rbx
0x140008f9c  mov     rcx, rbx; this
0x140008f9f  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x140008fa4  nop
0x140008fa5  cmp     qword ptr [r14], 0
0x140008fa9  jz      short loc_140008FC3
0x140008fab  mov     rdx, r14
0x140008fae  mov     rcx, rdi
0x140008fb1  call    ??$?0V?$CComPtr@UIUnknown@@@ATL@@@?$_com_ptr_t@V?$_com_IIID@UIMSMQRuleHandler@@$1?_GUID_b0cdbf11_9774_11d2_8929_000000000000@@3U__s_GUID@@B@@@@QEAA@AEBV?$CComPtr@UIUnknown@@@ATL@@@Z; _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::_com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>(ATL::CComPtr<IUnknown> const &)
0x140008fb6  nop
0x140008fb7  mov     rcx, rbx; lpCriticalSection
0x140008fba  call    cs:__imp_LeaveCriticalSection
0x140008fc0  nop
0x140008fc1  jmp     short loc_140008F7E
0x140008fc3  mov     [rsp+0A8h+ppv], 0
0x140008fcf  mov     r9d, 17h
0x140008fd5  lea     rcx, [rsp+0A8h+ppv]; ppv
0x140008fdd  call    ?CreateInstance@?$_com_ptr_t@V?$_com_IIID@UIMSMQRuleHandler@@$1?_GUID_b0cdbf11_9774_11d2_8929_000000000000@@3U__s_GUID@@B@@@@QEAAJPEB_WPEAUIUnknown@@K@Z; _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::CreateInstance(wchar_t const *,IUnknown *,ulong)
0x140008fe2  mov     r15d, eax
0x140008fe5  test    eax, eax
0x140008fe7  jns     loc_140009078
0x140008fed  lea     rax, WPP_GLOBAL_Control
0x140008ff4  mov     rcx, cs:WPP_GLOBAL_Control
0x140008ffb  cmp     rcx, rax
0x140008ffe  jz      short loc_140009031
0x140009000  test    byte ptr [rcx+1Ch], 1
0x140009004  jz      short loc_140009031
0x140009006  mov     rax, [rsi+8]
0x14000900a  test    rax, rax
0x14000900d  jz      short loc_140009014
0x14000900f  mov     r9, [rax]
0x140009012  jmp     short loc_140009017
0x140009014  xor     r9d, r9d
0x140009017  mov     edx, 21h ; '!'
0x14000901c  mov     dword ptr [rsp+0A8h+var_88], r15d; char
0x140009021  lea     r8, WPP_1833f040ae3e358d840c1ed912348424_Traceguids
0x140009028  mov     rcx, [rcx+10h]; LoggerHandle
0x14000902c  call    WPP_SF_Sd
0x140009031  cmp     cs:byte_14002AB1C, 0
0x140009038  jnz     short loc_140009059
0x14000903a  mov     r8d, 2; unsigned __int16
0x140009040  mov     rax, [rsi]
0x140009043  mov     qword ptr [rsp+0A8h+var_88], rax
0x140009048  mov     r9, [rsi+8]
0x14000904c  mov     edx, r15d; dwMessageId
0x14000904f  mov     ecx, 0C000089Fh; unsigned int
0x140009054  call    ?EvReportWithError@@YAXKJGZZ; EvReportWithError(ulong,long,ushort,...)
0x140009059  mov     edx, r15d; unsigned int
0x14000905c  lea     rcx, [rsp+0A8h+pExceptionObject]; this
0x140009061  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x140009066  lea     rdx, _TI3?AVbad_hresult@@; pThrowInfo
0x14000906d  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x140009072  call    _CxxThrowException_0
0x140009078  lea     rcx, [rsp+0A8h+ppv]
0x140009080  call    ??C?$_com_ptr_t@V?$_com_IIID@UIMSMQRuleHandler@@$1?_GUID_b0cdbf11_9774_11d2_8929_000000000000@@3U__s_GUID@@B@@@@QEBAPEAUIMSMQRuleHandler@@XZ; _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->(void)
0x140009085  mov     r10, rax
0x140009088  movzx   edx, byte ptr [rsi+430h]
0x14000908f  mov     rcx, [rsi+20h]
0x140009093  mov     [rsp+0A8h+arg_18], rcx
0x14000909b  test    rcx, rcx
0x14000909e  jz      short loc_1400090A4
0x1400090a0  lock inc dword ptr [rcx+10h]
0x1400090a4  mov     rax, [rsi+28h]
0x1400090a8  mov     [rsp+0A8h+var_70], rax
0x1400090ad  test    rax, rax
0x1400090b0  jz      short loc_1400090B6
0x1400090b2  lock inc dword ptr [rax+10h]
0x1400090b6  mov     rax, [rsi]
0x1400090b9  mov     [rsp+0A8h+var_68], rax
0x1400090be  test    rax, rax
0x1400090c1  jz      short loc_1400090C7
0x1400090c3  lock inc dword ptr [rax+10h]
0x1400090c7  mov     dword ptr [rsp+0A8h+var_88], edx
0x1400090cb  lea     r9, [rsp+0A8h+arg_18]
0x1400090d3  lea     r8, [rsp+0A8h+var_70]
0x1400090d8  lea     rdx, [rsp+0A8h+var_68]
0x1400090dd  mov     rcx, r10
0x1400090e0  call    ?Init@IMSMQRuleHandler@@QEAAJV_bstr_t@@00J@Z; IMSMQRuleHandler::Init(_bstr_t,_bstr_t,_bstr_t,long)
0x1400090e5  mov     rdx, [rsp+0A8h+ppv]
0x1400090ed  mov     rcx, r14
0x1400090f0  call    cs:__imp_AtlComPtrAssign
0x1400090f6  mov     rax, [rsp+0A8h+ppv]
0x1400090fe  mov     [rdi], rax
0x140009101  mov     rcx, rdi
0x140009104  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIMSMQTriggersConfig@@$1?_GUID_7c55d6a1_f584_11d2_89b2_000000000000@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IMSMQTriggersConfig,&__s_GUID const _GUID_7c55d6a1_f584_11d2_89b2_000000000000>>::_AddRef(void)
0x140009109  nop
0x14000910a  lea     rcx, [rsp+0A8h+ppv]
0x140009112  call    ??1?$R@UIObjectContext@@@@QEAA@XZ; R<IObjectContext>::~R<IObjectContext>(void)
0x140009117  nop
0x140009118  mov     rcx, rbx; lpCriticalSection
0x14000911b  call    cs:__imp_LeaveCriticalSection
0x140009121  nop
0x140009122  mov     rax, rdi
0x140009125  jmp     loc_140008F81
```
