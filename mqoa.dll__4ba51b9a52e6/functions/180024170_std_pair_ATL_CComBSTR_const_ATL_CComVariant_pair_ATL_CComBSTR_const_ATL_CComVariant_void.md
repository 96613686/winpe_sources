# std::pair<ATL::CComBSTR const,ATL::CComVariant>::~pair<ATL::CComBSTR const,ATL::CComVariant>(void)

- ea: `0x180024170`
- end: `0x1800241a3`
- name: `??1?$pair@$$CBVCComBSTR@ATL@@VCComVariant@2@@std@@QEAA@XZ`
- size: `51`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180024308`
- `0x180026308`
- `0x180026450`
- `0x180028204`

## callees

- `0x180024170`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180024196`
- `OLEAUT32!__imp_SysFreeString` at `0x180024196`
- `OLEAUT32!__imp_VariantClear` at `0x18002418c`
- `OLEAUT32!__imp_VariantClear` at `0x18002418c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall std::pair<ATL::CComBSTR const,ATL::CComVariant>::~pair<ATL::CComBSTR const,ATL::CComVariant>(BSTR *a1)
{
  VARIANTARG *v2; // rcx

  v2 = (VARIANTARG *)(a1 + 1);
  if ( v2->vt == 4095 )
    v2->vt = 8;
  VariantClear(v2);
  SysFreeString(*a1);
}

```

## disassembly

```asm
0x180024170  push    rbx
0x180024172  sub     rsp, 20h
0x180024176  mov     rbx, rcx
0x180024179  add     rcx, 8; pvarg
0x18002417d  mov     eax, 0FFFh
0x180024182  cmp     [rcx], ax
0x180024185  jnz     short loc_18002418C
0x180024187  mov     word ptr [rcx], 8
0x18002418c  call    cs:__imp_VariantClear
0x180024192  nop
0x180024193  mov     rcx, [rbx]; bstrString
0x180024196  call    cs:__imp_SysFreeString
0x18002419c  nop
0x18002419d  add     rsp, 20h
0x1800241a1  pop     rbx
0x1800241a2  retn
```
