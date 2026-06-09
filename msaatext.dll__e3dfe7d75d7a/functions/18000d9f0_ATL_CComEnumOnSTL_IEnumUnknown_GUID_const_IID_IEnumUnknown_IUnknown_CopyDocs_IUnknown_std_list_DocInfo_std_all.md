# ATL::CComEnumOnSTL<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,CopyDocs<IUnknown>,std::list<DocInfo *,std::allocator<DocInfo *>>,ATL::CComSingleThreadModel>::Next(ulong,IUnknown * *,ulong *)

- ea: `0x18000d9f0`
- end: `0x18000d9f5`
- name: `?Next@?$CComEnumOnSTL@UIEnumUnknown@@$1?IID_IEnumUnknown@@3U_GUID@@BPEAUIUnknown@@V?$CopyDocs@UIUnknown@@@@V?$list@PEAUDocInfo@@V?$allocator@PEAUDocInfo@@@std@@@std@@VCComSingleThreadModel@ATL@@@ATL@@UEAAJKPEAPEAUIUnknown@@PEAK@Z`
- size: `5`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000d9fc`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall ATL::CComEnumOnSTL<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,CopyDocs<IUnknown>,std::list<DocInfo *>,ATL::CComSingleThreadModel>::Next(
        __int64 a1,
        unsigned int a2,
        _QWORD *a3,
        unsigned int *a4)
{
  return ATL::IEnumOnSTLImpl<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,CopyDocs<IUnknown>,std::list<DocInfo *>,ATL::CComEnumOnSTL<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,CopyDocs<IUnknown>,std::list<DocInfo *>,ATL::CComSingleThreadModel>>::Next(
           a1,
           a2,
           a3,
           a4);
}

```

## disassembly

```asm
0x18000d9f0  jmp     ?Next@?$IEnumOnSTLImpl@UIEnumUnknown@@$1?IID_IEnumUnknown@@3U_GUID@@BPEAUIUnknown@@V?$CopyDocs@UIUnknown@@@@V?$list@PEAUDocInfo@@V?$allocator@PEAUDocInfo@@@std@@@std@@V?$CComEnumOnSTL@UIEnumUnknown@@$1?IID_IEnumUnknown@@3U_GUID@@BPEAUIUnknown@@V?$CopyDocs@UIUnknown@@@@V?$list@PEAUDocInfo@@V?$allocator@PEAUDocInfo@@@std@@@std@@VCComSingleThreadModel@ATL@@@ATL@@@ATL@@UEAAJKPEAPEAUIUnknown@@PEAK@Z; ATL::IEnumOnSTLImpl<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,CopyDocs<IUnknown>,std::list<DocInfo *>,ATL::CComEnumOnSTL<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,CopyDocs<IUnknown>,std::list<DocInfo *>,ATL::CComSingleThreadModel>>::Next(ulong,IUnknown * *,ulong *)
```
