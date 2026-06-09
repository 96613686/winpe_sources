# ATL::CComObject<ATL::CComEnum<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComSingleThreadModel>>::`scalar deleting destructor'(uint)

- ea: `0x180009374`
- end: `0x180009393`
- name: `??_G?$CComObject@V?$CComEnum@UIEnumConnections@@$1?IID_IEnumConnections@@3U_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@VCComSingleThreadModel@6@@ATL@@@ATL@@QEAAPEAXI@Z`
- size: `31`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18000987c`
- `0x180009af0`
- `0x18000a4e0`

## callees

- `0x18000178c`
- `0x18000924c`

## pseudocode

```c
void *__fastcall ATL::CComObject<ATL::CComEnum<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComSingleThreadModel>>::`scalar deleting destructor'(
        void *Block)
{
  ATL::CComObject<ATL::CComEnum<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComSingleThreadModel>>::~CComObject<ATL::CComEnum<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComSingleThreadModel>>();
  operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180009374  push    rbx
0x180009376  sub     rsp, 20h
0x18000937a  mov     rbx, rcx
0x18000937d  call    ??1?$CComObject@V?$CComEnum@UIEnumConnections@@$1?IID_IEnumConnections@@3U_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@VCComSingleThreadModel@6@@ATL@@@ATL@@QEAA@XZ; ATL::CComObject<ATL::CComEnum<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComSingleThreadModel>>::~CComObject<ATL::CComEnum<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComSingleThreadModel>>(void)
0x180009382  mov     rcx, rbx; Block
0x180009385  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000938a  mov     rax, rbx
0x18000938d  add     rsp, 20h
0x180009391  pop     rbx
0x180009392  retn
```
