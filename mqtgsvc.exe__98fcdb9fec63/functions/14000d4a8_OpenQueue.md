# OpenQueue

- ea: `0x14000d4a8`
- end: `0x14000d5a6`
- name: `OpenQueue`
- size: `254`
- prototype: `_QWORD *__fastcall(_QWORD *, const wchar_t *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000d648`

## callees

- `0x1400030ac`
- `0x140003868`
- `0x140003dc8`
- `0x140004eb4`
- `0x14000cf50`
- `0x14000d440`
- `0x14000d4a8`
- `0x14000ec24`
- `0x14001cf00`
- `0x140020010`

## import_xrefs

- `ole32!CLSIDFromProgID` at `0x14000d4ec`
- `ole32!CLSIDFromProgID` at `0x14000d4ec`

## pseudocode

```c
_QWORD *__fastcall OpenQueue(_QWORD *a1, const wchar_t *a2)
{
  HRESULT v4; // ecx
  IUnknown *v5; // r8
  __int64 v6; // rcx
  __int64 v7; // rdx
  struct IUnknown *v8; // rax
  LPVOID ppv[2]; // [rsp+20h] [rbp-30h] BYREF
  GUID clsid; // [rsp+30h] [rbp-20h] BYREF

  ppv[0] = 0;
  clsid = 0;
  v4 = CLSIDFromProgID(L"MSMQ.MSMQQueueInfo", &clsid);
  if ( v4 >= 0 )
    v4 = _com_ptr_t<_com_IIID<IMSMQQueueInfo4,&__s_GUID const _GUID_eba96b21_2168_11d3_898c_00e02c074f6b>>::CreateInstance(
           ppv,
           &clsid,
           v5,
           0x17u);
  if ( (int)(v4 + 0x80000000) >= 0 && v4 != -2147467262 )
    _com_issue_error(v4);
  _bstr_t::_bstr_t((_bstr_t *)&clsid, a2);
  v6 = _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->((__int64 *)ppv);
  if ( *(_QWORD *)&clsid.Data1 )
    v7 = **(_QWORD **)&clsid.Data1;
  else
    v7 = 0;
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 120LL))(v6, v7);
  v8 = (struct IUnknown *)_com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->((__int64 *)ppv);
  IMSMQQueueInfo4::Open(v8, a1);
  _bstr_t::_Free((_bstr_t *)&clsid);
  R<IObjectContext>::~R<IObjectContext>((__int64 *)ppv);
  return a1;
}

```

## disassembly

```asm
0x14000d4a8  mov     [rsp-8+arg_10], rbx
0x14000d4ad  mov     [rsp-8+arg_18], rdi
0x14000d4b2  push    rbp
0x14000d4b3  mov     rbp, rsp
0x14000d4b6  sub     rsp, 50h
0x14000d4ba  mov     rax, cs:__security_cookie
0x14000d4c1  xor     rax, rsp
0x14000d4c4  mov     [rbp+var_10], rax
0x14000d4c8  mov     rdi, rdx
0x14000d4cb  mov     rbx, rcx
0x14000d4ce  mov     qword ptr [rbp+clsid.Data1], rcx
0x14000d4d2  mov     [rbp+ppv], 0
0x14000d4da  xorps   xmm0, xmm0
0x14000d4dd  movups  xmmword ptr [rbp+clsid.Data1], xmm0
0x14000d4e1  lea     rdx, [rbp+clsid]; lpclsid
0x14000d4e5  lea     rcx, aMsmqMsmqqueuei; "MSMQ.MSMQQueueInfo"
0x14000d4ec  call    cs:__imp_CLSIDFromProgID
0x14000d4f2  mov     ecx, eax
0x14000d4f4  test    eax, eax
0x14000d4f6  js      short loc_14000D50D
0x14000d4f8  mov     r9d, 17h
0x14000d4fe  lea     rdx, [rbp+clsid]; rclsid
0x14000d502  lea     rcx, [rbp+ppv]; ppv
0x14000d506  call    ?CreateInstance@?$_com_ptr_t@V?$_com_IIID@UIMSMQQueueInfo4@@$1?_GUID_eba96b21_2168_11d3_898c_00e02c074f6b@@3U__s_GUID@@B@@@@QEAAJAEBU_GUID@@PEAUIUnknown@@K@Z; _com_ptr_t<_com_IIID<IMSMQQueueInfo4,&__s_GUID const _GUID_eba96b21_2168_11d3_898c_00e02c074f6b>>::CreateInstance(_GUID const &,IUnknown *,ulong)
0x14000d50b  mov     ecx, eax; int
0x14000d50d  mov     edx, 80000000h
0x14000d512  lea     eax, [rcx+rdx]
0x14000d515  test    edx, eax
0x14000d517  jnz     short loc_14000D527
0x14000d519  cmp     ecx, 80004002h
0x14000d51f  jz      short loc_14000D527
0x14000d521  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x14000d527  mov     rdx, rdi; wchar_t *
0x14000d52a  lea     rcx, [rbp+clsid]; this
0x14000d52e  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x14000d533  nop
0x14000d534  lea     rcx, [rbp+ppv]
0x14000d538  call    ??C?$_com_ptr_t@V?$_com_IIID@UIMSMQRuleHandler@@$1?_GUID_b0cdbf11_9774_11d2_8929_000000000000@@3U__s_GUID@@B@@@@QEBAPEAUIMSMQRuleHandler@@XZ; _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->(void)
0x14000d53d  mov     rcx, rax
0x14000d540  mov     rax, [rax]
0x14000d543  mov     r8, [rax+78h]
0x14000d547  mov     rax, qword ptr [rbp+clsid.Data1]
0x14000d54b  test    rax, rax
0x14000d54e  jz      short loc_14000D555
0x14000d550  mov     rdx, [rax]
0x14000d553  jmp     short loc_14000D557
0x14000d555  xor     edx, edx
0x14000d557  mov     rax, r8
0x14000d55a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d55f  lea     rcx, [rbp+ppv]
0x14000d563  call    ??C?$_com_ptr_t@V?$_com_IIID@UIMSMQRuleHandler@@$1?_GUID_b0cdbf11_9774_11d2_8929_000000000000@@3U__s_GUID@@B@@@@QEBAPEAUIMSMQRuleHandler@@XZ; _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->(void)
0x14000d568  mov     rdx, rbx
0x14000d56b  mov     rcx, rax; struct IUnknown *
0x14000d56e  call    ?Open@IMSMQQueueInfo4@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIMSMQQueue4@@$1?_GUID_eba96b20_2168_11d3_898c_00e02c074f6b@@3U__s_GUID@@B@@@@JJ@Z; IMSMQQueueInfo4::Open(long,long)
0x14000d573  nop
0x14000d574  lea     rcx, [rbp+clsid]; this
0x14000d578  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14000d57d  nop
0x14000d57e  lea     rcx, [rbp+ppv]
0x14000d582  call    ??1?$R@UIObjectContext@@@@QEAA@XZ; R<IObjectContext>::~R<IObjectContext>(void)
0x14000d587  mov     rax, rbx
0x14000d58a  mov     rcx, [rbp+var_10]
0x14000d58e  xor     rcx, rsp; StackCookie
0x14000d591  call    __security_check_cookie
0x14000d596  mov     rbx, [rsp+50h+arg_10]
0x14000d59b  mov     rdi, [rsp+50h+arg_18]
0x14000d5a0  add     rsp, 50h
0x14000d5a4  pop     rbp
0x14000d5a5  retn
```
