# ATL::CComObject<ATL::CComEnum<IEnumVARIANT,&_GUID const IID_IEnumVARIANT,tagVARIANT,ATL::_Copy<tagVARIANT>,ATL::CComSingleThreadModel>>::`scalar deleting destructor'(uint)

- ea: `0x180024268`
- end: `0x180024287`
- name: `??_G?$CComObject@V?$CComEnum@UIEnumVARIANT@@$1?IID_IEnumVARIANT@@3U_GUID@@BUtagVARIANT@@V?$_Copy@UtagVARIANT@@@ATL@@VCComSingleThreadModel@6@@ATL@@@ATL@@QEAAPEAXI@Z`
- size: `31`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18002443c`
- `0x180024970`
- `0x180024f10`

## callees

- `0x18000178c`
- `0x180024130`

## pseudocode

```c
void *__fastcall ATL::CComObject<ATL::CComEnum<IEnumVARIANT,&_GUID const IID_IEnumVARIANT,tagVARIANT,ATL::_Copy<tagVARIANT>,ATL::CComSingleThreadModel>>::`scalar deleting destructor'(
        void *Block)
{
  ATL::CComObject<ATL::CComEnum<IEnumVARIANT,&_GUID const IID_IEnumVARIANT,tagVARIANT,ATL::_Copy<tagVARIANT>,ATL::CComSingleThreadModel>>::~CComObject<ATL::CComEnum<IEnumVARIANT,&_GUID const IID_IEnumVARIANT,tagVARIANT,ATL::_Copy<tagVARIANT>,ATL::CComSingleThreadModel>>();
  operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180024268  push    rbx
0x18002426a  sub     rsp, 20h
0x18002426e  mov     rbx, rcx
0x180024271  call    ??1?$CComObject@V?$CComEnum@UIEnumVARIANT@@$1?IID_IEnumVARIANT@@3U_GUID@@BUtagVARIANT@@V?$_Copy@UtagVARIANT@@@ATL@@VCComSingleThreadModel@6@@ATL@@@ATL@@QEAA@XZ; ATL::CComObject<ATL::CComEnum<IEnumVARIANT,&_GUID const IID_IEnumVARIANT,tagVARIANT,ATL::_Copy<tagVARIANT>,ATL::CComSingleThreadModel>>::~CComObject<ATL::CComEnum<IEnumVARIANT,&_GUID const IID_IEnumVARIANT,tagVARIANT,ATL::_Copy<tagVARIANT>,ATL::CComSingleThreadModel>>(void)
0x180024276  mov     rcx, rbx; Block
0x180024279  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002427e  mov     rax, rbx
0x180024281  add     rsp, 20h
0x180024285  pop     rbx
0x180024286  retn
```
