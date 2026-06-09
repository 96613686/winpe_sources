# _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::_com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>(ATL::CComPtr<IUnknown> const &)

- ea: `0x140007dbc`
- end: `0x140007dfb`
- name: `??$?0V?$CComPtr@UIUnknown@@@ATL@@@?$_com_ptr_t@V?$_com_IIID@UIMSMQRuleHandler@@$1?_GUID_b0cdbf11_9774_11d2_8929_000000000000@@3U__s_GUID@@B@@@@QEAA@AEBV?$CComPtr@UIUnknown@@@ATL@@@Z`
- size: `63`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140008f50`

## callees

- `0x140007dbc`
- `0x140007e04`
- `0x14000ec24`

## pseudocode

```c
_QWORD *__fastcall _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::_com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>(
        _QWORD *a1,
        _QWORD *a2)
{
  int v3; // eax

  *a1 = 0;
  if ( *a2 )
  {
    v3 = _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::_QueryInterface<ATL::CComPtr<IUnknown>>(
           a1,
           a2);
    if ( (int)(v3 + 0x80000000) >= 0 && v3 != -2147467262 )
      _com_issue_error(v3);
  }
  return a1;
}

```

## disassembly

```asm
0x140007dbc  push    rbx
0x140007dbe  sub     rsp, 20h
0x140007dc2  mov     qword ptr [rcx], 0
0x140007dc9  mov     rbx, rcx
0x140007dcc  cmp     qword ptr [rdx], 0
0x140007dd0  jz      short loc_140007DF2
0x140007dd2  call    ??$_QueryInterface@V?$CComPtr@UIUnknown@@@ATL@@@?$_com_ptr_t@V?$_com_IIID@UIMSMQRuleHandler@@$1?_GUID_b0cdbf11_9774_11d2_8929_000000000000@@3U__s_GUID@@B@@@@AEAAJAEBV?$CComPtr@UIUnknown@@@ATL@@@Z; _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::_QueryInterface<ATL::CComPtr<IUnknown>>(ATL::CComPtr<IUnknown> const &)
0x140007dd7  mov     ecx, 80000000h
0x140007ddc  lea     edx, [rax+rcx]
0x140007ddf  test    ecx, edx
0x140007de1  jnz     short loc_140007DF2
0x140007de3  cmp     eax, 80004002h
0x140007de8  jz      short loc_140007DF2
0x140007dea  mov     ecx, eax; int
0x140007dec  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x140007df2  mov     rax, rbx
0x140007df5  add     rsp, 20h
0x140007df9  pop     rbx
0x140007dfa  retn
```
