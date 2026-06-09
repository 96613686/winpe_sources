# ATL::CComSafeArray<tagVARIANT,12>::SetAt(long,tagVARIANT const &,int)

- ea: `0x18001ad58`
- end: `0x18001adad`
- name: `?SetAt@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAAJJAEBUtagVARIANT@@H@Z`
- size: `85`
- prototype: `HRESULT __fastcall(SAFEARRAY **, LONG, const VARIANTARG *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001a610`
- `0x18001a91c`

## callees

- `0x18001a8dc`
- `0x18001ac60`
- `0x18001ad58`

## import_xrefs

- `OLEAUT32!__imp_VariantCopyInd` at `0x18001ad97`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18001ad97`

## pseudocode

```c
HRESULT __fastcall ATL::CComSafeArray<tagVARIANT,12>::SetAt(SAFEARRAY **a1, LONG a2, const VARIANTARG *a3)
{
  LONG v6; // edx
  int LowerBound; // esi

  LowerBound = ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(a1, a2);
  if ( a2 < LowerBound || a2 > (int)ATL::CComSafeArray<tagVARIANT,12>::GetUpperBound(a1, v6) )
    return -2147024809;
  else
    return VariantCopyInd((VARIANT *)(*a1)->pvData + a2 - LowerBound, a3);
}

```

## disassembly

```asm
0x18001ad58  push    rbx
0x18001ad5a  push    rbp
0x18001ad5b  push    rsi
0x18001ad5c  push    rdi
0x18001ad5d  sub     rsp, 28h
0x18001ad61  mov     rbp, r8
0x18001ad64  mov     ebx, edx
0x18001ad66  mov     rdi, rcx
0x18001ad69  call    ?GetLowerBound@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEBAJI@Z; ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(uint)
0x18001ad6e  mov     esi, eax
0x18001ad70  cmp     ebx, eax
0x18001ad72  jl      short loc_18001AD9F
0x18001ad74  mov     rcx, rdi
0x18001ad77  call    ?GetUpperBound@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEBAJI@Z; ATL::CComSafeArray<tagVARIANT,12>::GetUpperBound(uint)
0x18001ad7c  cmp     ebx, eax
0x18001ad7e  jg      short loc_18001AD9F
0x18001ad80  sub     ebx, esi
0x18001ad82  movsxd  rax, ebx
0x18001ad85  lea     rdx, [rax+rax*2]
0x18001ad89  mov     rax, [rdi]
0x18001ad8c  mov     rcx, [rax+10h]
0x18001ad90  lea     rcx, [rcx+rdx*8]; pvarDest
0x18001ad94  mov     rdx, rbp; pvargSrc
0x18001ad97  call    cs:__imp_VariantCopyInd
0x18001ad9d  jmp     short loc_18001ADA4
0x18001ad9f  mov     eax, 80070057h
0x18001ada4  add     rsp, 28h
0x18001ada8  pop     rdi
0x18001ada9  pop     rsi
0x18001adaa  pop     rbp
0x18001adab  pop     rbx
0x18001adac  retn
```
