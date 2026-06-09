# ATL::CComEnumOnSTL<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,CopyDocs<IUnknown>,std::list<DocInfo *,std::allocator<DocInfo *>>,ATL::CComSingleThreadModel>::Reset(void)

- ea: `0x18000deb0`
- end: `0x18000decf`
- name: `?Reset@?$CComEnumOnSTL@UIEnumUnknown@@$1?IID_IEnumUnknown@@3U_GUID@@BPEAUIUnknown@@V?$CopyDocs@UIUnknown@@@@V?$list@PEAUDocInfo@@V?$allocator@PEAUDocInfo@@@std@@@std@@VCComSingleThreadModel@ATL@@@ATL@@UEAAJXZ`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000deb0`

## pseudocode

```c
__int64 __fastcall ATL::CComEnumOnSTL<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,CopyDocs<IUnknown>,std::list<DocInfo *>,ATL::CComSingleThreadModel>::Reset(
        __int64 a1)
{
  __int64 **v1; // rax
  __int64 result; // rax
  __int64 v4; // rcx

  v1 = *(__int64 ***)(a1 + 16);
  if ( !v1 )
    return 2147500037LL;
  v4 = **v1;
  result = 0;
  *(_QWORD *)(a1 + 24) = v4;
  return result;
}

```

## disassembly

```asm
0x18000deb0  mov     rax, [rcx+10h]
0x18000deb4  mov     rdx, rcx
0x18000deb7  test    rax, rax
0x18000deba  jnz     short loc_18000DEC2
0x18000debc  mov     eax, 80004005h
0x18000dec1  retn
0x18000dec2  mov     rax, [rax]
0x18000dec5  mov     rcx, [rax]
0x18000dec8  xor     eax, eax
0x18000deca  mov     [rdx+18h], rcx
0x18000dece  retn
```
