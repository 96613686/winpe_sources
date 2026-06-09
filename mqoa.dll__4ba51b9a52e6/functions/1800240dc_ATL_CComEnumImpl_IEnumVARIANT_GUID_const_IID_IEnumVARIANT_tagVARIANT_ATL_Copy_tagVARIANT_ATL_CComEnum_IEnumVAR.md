# ATL::CComEnumImpl<IEnumVARIANT,&_GUID const IID_IEnumVARIANT,tagVARIANT,ATL::_Copy<tagVARIANT>,ATL::CComEnum<IEnumVARIANT,&_GUID const IID_IEnumVARIANT,tagVARIANT,ATL::_Copy<tagVARIANT>,ATL::CComSingleThreadModel>>::~CComEnumImpl<IEnumVARIANT,&_GUID const IID_IEnumVARIANT,tagVARIANT,ATL::_Copy<tagVARIANT>,ATL::CComEnum<IEnumVARIANT,&_GUID const IID_IEnumVARIANT,tagVARIANT,ATL::_Copy<tagVARIANT>,ATL::CComSingleThreadModel>>(void)

- ea: `0x1800240dc`
- end: `0x180024128`
- name: `??1?$CComEnumImpl@UIEnumVARIANT@@$1?IID_IEnumVARIANT@@3U_GUID@@BUtagVARIANT@@V?$_Copy@UtagVARIANT@@@ATL@@V?$CComEnum@UIEnumVARIANT@@$1?IID_IEnumVARIANT@@3U_GUID@@BUtagVARIANT@@V?$_Copy@UtagVARIANT@@@ATL@@VCComSingleThreadModel@6@@6@@ATL@@QEAA@XZ`
- size: `76`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180024130`

## callees

- `0x18000178c`
- `0x1800033ec`
- `0x1800240dc`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x1800240fc`
- `OLEAUT32!__imp_VariantClear` at `0x1800240fc`

## pseudocode

```c
__int64 __fastcall ATL::CComEnumImpl<IEnumVARIANT,&_GUID const IID_IEnumVARIANT,tagVARIANT,ATL::_Copy<tagVARIANT>,ATL::CComEnum<IEnumVARIANT,&_GUID const IID_IEnumVARIANT,tagVARIANT,ATL::_Copy<tagVARIANT>,ATL::CComSingleThreadModel>>::~CComEnumImpl<IEnumVARIANT,&_GUID const IID_IEnumVARIANT,tagVARIANT,ATL::_Copy<tagVARIANT>,ATL::CComEnum<IEnumVARIANT,&_GUID const IID_IEnumVARIANT,tagVARIANT,ATL::_Copy<tagVARIANT>,ATL::CComSingleThreadModel>>(
        __int64 a1)
{
  VARIANTARG *i; // rdi

  if ( (*(_BYTE *)(a1 + 40) & 2) != 0 )
  {
    for ( i = *(VARIANTARG **)(a1 + 16); i != *(VARIANTARG **)(a1 + 24); ++i )
      VariantClear(i);
    operator delete(*(void **)(a1 + 16));
  }
  return R<IADs>::~R<IADs>(a1 + 8);
}

```

## disassembly

```asm
0x1800240dc  mov     [rsp+arg_0], rbx
0x1800240e1  push    rdi
0x1800240e2  sub     rsp, 20h
0x1800240e6  mov     rbx, rcx
0x1800240e9  test    byte ptr [rcx+28h], 2
0x1800240ed  jz      short loc_180024115
0x1800240ef  mov     rdi, [rcx+10h]
0x1800240f3  cmp     rdi, [rcx+18h]
0x1800240f7  jz      short loc_18002410C
0x1800240f9  mov     rcx, rdi; pvarg
0x1800240fc  call    cs:__imp_VariantClear
0x180024102  add     rdi, 18h
0x180024106  cmp     rdi, [rbx+18h]
0x18002410a  jnz     short loc_1800240F9
0x18002410c  mov     rcx, [rbx+10h]; Block
0x180024110  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180024115  lea     rcx, [rbx+8]
0x180024119  mov     rbx, [rsp+28h+arg_0]
0x18002411e  add     rsp, 20h
0x180024122  pop     rdi
0x180024123  jmp     ??1?$R@UIADs@@@@QEAA@XZ; R<IADs>::~R<IADs>(void)
```
