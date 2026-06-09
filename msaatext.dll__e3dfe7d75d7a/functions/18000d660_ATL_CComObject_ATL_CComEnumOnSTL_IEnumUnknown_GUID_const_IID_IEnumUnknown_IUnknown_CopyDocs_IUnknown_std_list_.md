# ATL::CComObject<ATL::CComEnumOnSTL<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,CopyDocs<IUnknown>,std::list<DocInfo *,std::allocator<DocInfo *>>,ATL::CComSingleThreadModel>>::AddRef(void)

- ea: `0x18000d660`
- end: `0x18000d673`
- name: `?AddRef@?$CComObject@V?$CComEnumOnSTL@UIEnumUnknown@@$1?IID_IEnumUnknown@@3U_GUID@@BPEAUIUnknown@@V?$CopyDocs@UIUnknown@@@@V?$list@PEAUDocInfo@@V?$allocator@PEAUDocInfo@@@std@@@std@@VCComSingleThreadModel@ATL@@@ATL@@@ATL@@UEAAKXZ`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000d660`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<ATL::CComEnumOnSTL<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,CopyDocs<IUnknown>,std::list<DocInfo *>,ATL::CComSingleThreadModel>>::AddRef(
        __int64 a1)
{
  int v1; // edx
  __int64 result; // rax

  v1 = *(_DWORD *)(a1 + 32);
  result = 0x7FFFFFFF;
  if ( v1 != 0x7FFFFFFF )
  {
    result = (unsigned int)(v1 + 1);
    *(_DWORD *)(a1 + 32) = result;
  }
  return result;
}

```

## disassembly

```asm
0x18000d660  mov     edx, [rcx+20h]
0x18000d663  mov     eax, 7FFFFFFFh
0x18000d668  cmp     edx, eax
0x18000d66a  jz      short locret_18000D672
0x18000d66c  lea     eax, [rdx+1]
0x18000d66f  mov     [rcx+20h], eax
0x18000d672  retn
```
