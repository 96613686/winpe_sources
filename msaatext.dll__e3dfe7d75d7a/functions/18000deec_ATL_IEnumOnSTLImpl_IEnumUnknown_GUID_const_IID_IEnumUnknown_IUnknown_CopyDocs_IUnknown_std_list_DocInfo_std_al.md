# ATL::IEnumOnSTLImpl<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,CopyDocs<IUnknown>,std::list<DocInfo *,std::allocator<DocInfo *>>,ATL::CComEnumOnSTL<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,CopyDocs<IUnknown>,std::list<DocInfo *,std::allocator<DocInfo *>>,ATL::CComSingleThreadModel>>::Skip(ulong)

- ea: `0x18000deec`
- end: `0x18000df18`
- name: `?Skip@?$IEnumOnSTLImpl@UIEnumUnknown@@$1?IID_IEnumUnknown@@3U_GUID@@BPEAUIUnknown@@V?$CopyDocs@UIUnknown@@@@V?$list@PEAUDocInfo@@V?$allocator@PEAUDocInfo@@@std@@@std@@V?$CComEnumOnSTL@UIEnumUnknown@@$1?IID_IEnumUnknown@@3U_GUID@@BPEAUIUnknown@@V?$CopyDocs@UIUnknown@@@@V?$list@PEAUDocInfo@@V?$allocator@PEAUDocInfo@@@std@@@std@@VCComSingleThreadModel@ATL@@@ATL@@@ATL@@UEAAJK@Z`
- size: `44`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000dee0`

## callees

- `0x18000deec`

## pseudocode

```c
__int64 __fastcall ATL::IEnumOnSTLImpl<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,CopyDocs<IUnknown>,std::list<DocInfo *>,ATL::CComEnumOnSTL<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,CopyDocs<IUnknown>,std::list<DocInfo *>,ATL::CComSingleThreadModel>>::Skip(
        __int64 a1,
        int a2)
{
  unsigned int v2; // r8d
  _QWORD *v3; // r9

  v2 = 0;
  if ( a2 )
  {
    while ( 1 )
    {
      v3 = *(_QWORD **)(a1 + 24);
      if ( v3 == **(_QWORD ***)(a1 + 16) )
        break;
      *(_QWORD *)(a1 + 24) = *v3;
      if ( !--a2 )
        return v2;
    }
    return 1;
  }
  return v2;
}

```

## disassembly

```asm
0x18000deec  xor     r8d, r8d
0x18000deef  test    edx, edx
0x18000def1  jz      short loc_18000DF14
0x18000def3  mov     rax, [rcx+10h]
0x18000def7  mov     r9, [rcx+18h]
0x18000defb  cmp     r9, [rax]
0x18000defe  jz      short loc_18000DF0E
0x18000df00  mov     rax, [r9]
0x18000df03  mov     [rcx+18h], rax
0x18000df07  add     edx, 0FFFFFFFFh
0x18000df0a  jnz     short loc_18000DEF3
0x18000df0c  jmp     short loc_18000DF14
0x18000df0e  mov     r8d, 1
0x18000df14  mov     eax, r8d
0x18000df17  retn
```
