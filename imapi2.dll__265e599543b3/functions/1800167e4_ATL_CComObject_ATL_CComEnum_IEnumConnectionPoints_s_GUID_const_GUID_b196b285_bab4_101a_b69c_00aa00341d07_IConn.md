# ATL::CComObject<ATL::CComEnum<IEnumConnectionPoints,&__s_GUID const _GUID_b196b285_bab4_101a_b69c_00aa00341d07,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComMultiThreadModel>>::CComObject<ATL::CComEnum<IEnumConnectionPoints,&__s_GUID const _GUID_b196b285_bab4_101a_b69c_00aa00341d07,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComMultiThreadModel>>(void *)

- ea: `0x1800167e4`
- end: `0x18001683c`
- name: `??0?$CComObject@V?$CComEnum@UIEnumConnectionPoints@@$1?_GUID_b196b285_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BPEAUIConnectionPoint@@V?$_CopyInterface@UIConnectionPoint@@@ATL@@VCComMultiThreadModel@6@@ATL@@@ATL@@QEAA@PEAX@Z`
- size: `88`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180017708`
- `0x1800185a0`
- `0x1800251a0`
- `0x180028310`
- `0x18002e020`
- `0x180032900`
- `0x180037b30`

## callees

- `0x1800167c4`
- `0x1800168d4`
- `0x18004a010`

## pseudocode

```c
_QWORD *__fastcall ATL::CComObject<ATL::CComEnum<IEnumConnectionPoints,&__s_GUID const _GUID_b196b285_bab4_101a_b69c_00aa00341d07,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComMultiThreadModel>>::CComObject<ATL::CComEnum<IEnumConnectionPoints,&__s_GUID const _GUID_b196b285_bab4_101a_b69c_00aa00341d07,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComMultiThreadModel>>(
        _QWORD *a1)
{
  __int64 v2; // rcx
  struct ATL::CAtlModule *v3; // rcx

  ATL::CComEnumImpl<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>>::CComEnumImpl<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>>();
  *(_DWORD *)(v2 + 48) = 0;
  *(_OWORD *)(v2 + 56) = 0;
  *(_OWORD *)(v2 + 72) = 0;
  *(_QWORD *)(v2 + 88) = 0;
  *(_BYTE *)(v2 + 96) = 0;
  ATL::CComAutoCriticalSection::CComAutoCriticalSection((ATL::CComAutoCriticalSection *)(v2 + 104));
  v3 = ATL::_pAtlModule;
  *a1 = &ATL::CComObject<ATL::CComEnum<IEnumConnectionPoints,&__s_GUID const _GUID_b196b285_bab4_101a_b69c_00aa00341d07,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComMultiThreadModel>>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v3 + 8LL))(v3);
  return a1;
}

```

## disassembly

```asm
0x1800167e4  push    rbx
0x1800167e6  sub     rsp, 20h
0x1800167ea  mov     rbx, rcx
0x1800167ed  call    ??0?$CComEnumImpl@UIEnumConnections@@$1?_GUID_b196b287_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@@ATL@@QEAA@XZ; ATL::CComEnumImpl<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>>::CComEnumImpl<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>>(void)
0x1800167f2  mov     dword ptr [rcx+30h], 0
0x1800167f9  xorps   xmm0, xmm0
0x1800167fc  movups  xmmword ptr [rcx+38h], xmm0
0x180016800  xor     eax, eax
0x180016802  movups  xmmword ptr [rcx+48h], xmm0
0x180016806  mov     [rcx+58h], rax
0x18001680a  mov     [rcx+60h], al
0x18001680d  add     rcx, 68h ; 'h'; this
0x180016811  call    ??0CComAutoCriticalSection@ATL@@QEAA@XZ; ATL::CComAutoCriticalSection::CComAutoCriticalSection(void)
0x180016816  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001681d  lea     rax, ??_7?$CComObject@V?$CComEnum@UIEnumConnectionPoints@@$1?_GUID_b196b285_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BPEAUIConnectionPoint@@V?$_CopyInterface@UIConnectionPoint@@@ATL@@VCComMultiThreadModel@6@@ATL@@@ATL@@6B@; const ATL::CComObject<ATL::CComEnum<IEnumConnectionPoints,&__s_GUID const _GUID_b196b285_bab4_101a_b69c_00aa00341d07,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComMultiThreadModel>>::`vftable'
0x180016824  mov     [rbx], rax
0x180016827  mov     rax, [rcx]
0x18001682a  mov     rax, [rax+8]
0x18001682e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016833  mov     rax, rbx
0x180016836  add     rsp, 20h
0x18001683a  pop     rbx
0x18001683b  retn
```
