# CMSMQCollection::Item(tagVARIANT *,tagVARIANT *)

- ea: `0x180024770`
- end: `0x18002480f`
- name: `?Item@CMSMQCollection@@UEAAJPEAUtagVARIANT@@0@Z`
- size: `159`
- prototype: `int(CMSMQCollection *__hidden this, struct tagVARIANT *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000cb34`
- `0x180024770`
- `0x180025354`
- `0x180026d98`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800247af`
- `OLEAUT32!__imp_SysAllocString` at `0x1800247af`
- `OLEAUT32!__imp_SysFreeString` at `0x1800247d6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800247d6`
- `OLEAUT32!__imp_VariantInit` at `0x1800247ed`
- `OLEAUT32!__imp_VariantInit` at `0x1800247ed`
- `OLEAUT32!__imp_VariantCopy` at `0x1800247fa`
- `OLEAUT32!__imp_VariantCopy` at `0x1800247fa`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMSMQCollection::Item(CMSMQCollection *this, struct tagVARIANT *a2, struct tagVARIANT *a3)
{
  HRESULT TrueBstr; // eax
  __int64 v6; // rcx
  OLECHAR *v8; // rbx
  __int64 v9; // rsi
  _BYTE v10[56]; // [rsp+20h] [rbp-38h] BYREF
  OLECHAR *psz; // [rsp+78h] [rbp+20h] BYREF

  psz = 0;
  TrueBstr = GetTrueBstr(a2, &psz);
  if ( TrueBstr < 0 )
    goto LABEL_2;
  v8 = SysAllocString(psz);
  psz = v8;
  v9 = *(_QWORD *)std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::find(
                    (char *)this + 112,
                    v10,
                    &psz);
  SysFreeString(v8);
  if ( v9 == *((_QWORD *)this + 15) )
  {
    v6 = 3222142982LL;
    return CreateErrorHelper(v6, 12);
  }
  VariantInit(a3);
  TrueBstr = VariantCopy(a3, (const VARIANTARG *)(v9 + 32));
  if ( TrueBstr < 0 )
  {
LABEL_2:
    v6 = (unsigned int)TrueBstr;
    return CreateErrorHelper(v6, 12);
  }
  return 0;
}

```

## disassembly

```asm
0x180024770  push    rbx
0x180024772  push    rbp
0x180024773  push    rsi
0x180024774  push    rdi
0x180024775  sub     rsp, 38h
0x180024779  mov     rdi, r8
0x18002477c  mov     rax, rdx
0x18002477f  mov     rbp, rcx
0x180024782  mov     [rsp+58h+psz], 0
0x18002478b  lea     rdx, [rsp+58h+psz]; wchar_t **
0x180024790  mov     rcx, rax; struct tagVARIANT *
0x180024793  call    ?GetTrueBstr@@YAJPEAUtagVARIANT@@PEAPEA_W@Z; GetTrueBstr(tagVARIANT *,wchar_t * *)
0x180024798  test    eax, eax
0x18002479a  jns     short loc_1800247AA
0x18002479c  mov     ecx, eax
0x18002479e  mov     edx, 0Ch
0x1800247a3  call    ?CreateErrorHelper@@YAJJW4MsmqObjType@@@Z; CreateErrorHelper(long,MsmqObjType)
0x1800247a8  jmp     short loc_180024806
0x1800247aa  mov     rcx, [rsp+58h+psz]; psz
0x1800247af  call    cs:__imp_SysAllocString
0x1800247b5  mov     rbx, rax
0x1800247b8  mov     [rsp+58h+psz], rax
0x1800247bd  lea     rcx, [rbp+70h]
0x1800247c1  lea     r8, [rsp+58h+psz]
0x1800247c6  lea     rdx, [rsp+58h+var_38]
0x1800247cb  call    ?find@?$_Tree@V?$_Tmap_traits@VCComBSTR@ATL@@VCComVariant@2@U?$less@VCComBSTR@ATL@@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@VCComVariant@2@@std@@@5@$0A@@std@@@std@@QEAA?AViterator@12@AEBVCComBSTR@ATL@@@Z; std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::find(ATL::CComBSTR const &)
0x1800247d0  mov     rsi, [rax]
0x1800247d3  mov     rcx, rbx; bstrString
0x1800247d6  call    cs:__imp_SysFreeString
0x1800247dc  nop
0x1800247dd  cmp     rsi, [rbp+78h]
0x1800247e1  jnz     short loc_1800247EA
0x1800247e3  mov     ecx, 0C00E0006h
0x1800247e8  jmp     short loc_18002479E
0x1800247ea  mov     rcx, rdi; pvarg
0x1800247ed  call    cs:__imp_VariantInit
0x1800247f3  lea     rdx, [rsi+20h]; pvargSrc
0x1800247f7  mov     rcx, rdi; pvargDest
0x1800247fa  call    cs:__imp_VariantCopy
0x180024800  test    eax, eax
0x180024802  js      short loc_18002479C
0x180024804  xor     eax, eax
0x180024806  add     rsp, 38h
0x18002480a  pop     rdi
0x18002480b  pop     rsi
0x18002480c  pop     rbp
0x18002480d  pop     rbx
0x18002480e  retn
```
