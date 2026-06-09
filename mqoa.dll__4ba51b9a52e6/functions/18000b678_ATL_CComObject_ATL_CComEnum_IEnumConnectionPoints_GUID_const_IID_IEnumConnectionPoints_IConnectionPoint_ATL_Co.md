# ATL::CComObject<ATL::CComEnum<IEnumConnectionPoints,&_GUID const IID_IEnumConnectionPoints,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComSingleThreadModel>>::`scalar deleting destructor'(uint)

- ea: `0x18000b678`
- end: `0x18000b697`
- name: `??_G?$CComObject@V?$CComEnum@UIEnumConnectionPoints@@$1?IID_IEnumConnectionPoints@@3U_GUID@@BPEAUIConnectionPoint@@V?$_CopyInterface@UIConnectionPoint@@@ATL@@VCComSingleThreadModel@6@@ATL@@@ATL@@QEAAPEAXI@Z`
- size: `31`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18000c9fc`
- `0x180012110`

## callees

- `0x18000178c`
- `0x18000ad6c`

## pseudocode

```c
void *__fastcall ATL::CComObject<ATL::CComEnum<IEnumConnectionPoints,&_GUID const IID_IEnumConnectionPoints,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComSingleThreadModel>>::`scalar deleting destructor'(
        void *Block)
{
  ATL::CComObject<ATL::CComEnum<IEnumConnectionPoints,&_GUID const IID_IEnumConnectionPoints,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComSingleThreadModel>>::~CComObject<ATL::CComEnum<IEnumConnectionPoints,&_GUID const IID_IEnumConnectionPoints,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComSingleThreadModel>>();
  operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x18000b678  push    rbx
0x18000b67a  sub     rsp, 20h
0x18000b67e  mov     rbx, rcx
0x18000b681  call    ??1?$CComObject@V?$CComEnum@UIEnumConnectionPoints@@$1?IID_IEnumConnectionPoints@@3U_GUID@@BPEAUIConnectionPoint@@V?$_CopyInterface@UIConnectionPoint@@@ATL@@VCComSingleThreadModel@6@@ATL@@@ATL@@QEAA@XZ; ATL::CComObject<ATL::CComEnum<IEnumConnectionPoints,&_GUID const IID_IEnumConnectionPoints,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComSingleThreadModel>>::~CComObject<ATL::CComEnum<IEnumConnectionPoints,&_GUID const IID_IEnumConnectionPoints,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComSingleThreadModel>>(void)
0x18000b686  mov     rcx, rbx; Block
0x18000b689  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b68e  mov     rax, rbx
0x18000b691  add     rsp, 20h
0x18000b695  pop     rbx
0x18000b696  retn
```
