# ATL::CComEnumImpl<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComEnum<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComSingleThreadModel>>::~CComEnumImpl<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComEnum<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComSingleThreadModel>>(void)

- ea: `0x1800091f8`
- end: `0x180009243`
- name: `??1?$CComEnumImpl@UIEnumConnections@@$1?IID_IEnumConnections@@3U_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@V?$CComEnum@UIEnumConnections@@$1?IID_IEnumConnections@@3U_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@VCComSingleThreadModel@6@@6@@ATL@@QEAA@XZ`
- size: `75`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18000924c`

## callees

- `0x18000178c`
- `0x1800033ec`
- `0x1800091f8`
- `0x18000a6cc`

## pseudocode

```c
__int64 __fastcall ATL::CComEnumImpl<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComEnum<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComSingleThreadModel>>::~CComEnumImpl<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComEnum<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComSingleThreadModel>>(
        __int64 a1)
{
  __int64 *i; // rdi

  if ( (*(_BYTE *)(a1 + 40) & 2) != 0 )
  {
    for ( i = *(__int64 **)(a1 + 16); i != *(__int64 **)(a1 + 24); i += 2 )
      ATL::_CopyInterface<IConnectionPoint>::destroy(i);
    operator delete(*(void **)(a1 + 16));
  }
  return R<IADs>::~R<IADs>(a1 + 8);
}

```

## disassembly

```asm
0x1800091f8  mov     [rsp+arg_0], rbx
0x1800091fd  push    rdi
0x1800091fe  sub     rsp, 20h
0x180009202  mov     rbx, rcx
0x180009205  test    byte ptr [rcx+28h], 2
0x180009209  jz      short loc_180009230
0x18000920b  mov     rdi, [rcx+10h]
0x18000920f  cmp     rdi, [rcx+18h]
0x180009213  jz      short loc_180009227
0x180009215  mov     rcx, rdi
0x180009218  call    ?destroy@?$_CopyInterface@UIConnectionPoint@@@ATL@@SAXPEAPEAUIConnectionPoint@@@Z; ATL::_CopyInterface<IConnectionPoint>::destroy(IConnectionPoint * *)
0x18000921d  add     rdi, 10h
0x180009221  cmp     rdi, [rbx+18h]
0x180009225  jnz     short loc_180009215
0x180009227  mov     rcx, [rbx+10h]; Block
0x18000922b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009230  lea     rcx, [rbx+8]
0x180009234  mov     rbx, [rsp+28h+arg_0]
0x180009239  add     rsp, 20h
0x18000923d  pop     rdi
0x18000923e  jmp     ??1?$R@UIADs@@@@QEAA@XZ; R<IADs>::~R<IADs>(void)
```
