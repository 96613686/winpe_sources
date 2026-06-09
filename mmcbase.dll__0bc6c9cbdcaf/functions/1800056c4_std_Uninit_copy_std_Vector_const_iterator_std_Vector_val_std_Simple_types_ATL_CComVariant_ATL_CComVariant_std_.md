# std::_Uninit_copy<std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<ATL::CComVariant>>>,ATL::CComVariant *,std::allocator<ATL::CComVariant>>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<ATL::CComVariant>>>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<ATL::CComVariant>>>,ATL::CComVariant *,std::_Wrap_alloc<std::allocator<ATL::CComVariant>> &,std::_Nonscalar_ptr_iterator_tag)

- ea: `0x1800056c4`
- end: `0x180005721`
- name: `??$_Uninit_copy@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@VCComVariant@ATL@@@std@@@std@@@std@@PEAVCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@2@@std@@YAPEAVCComVariant@ATL@@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@VCComVariant@ATL@@@std@@@std@@@0@0PEAV12@AEAU?$_Wrap_alloc@V?$allocator@VCComVariant@ATL@@@std@@@0@U_Nonscalar_ptr_iterator_tag@0@@Z`
- size: `93`
- prototype: `__int64 __fastcall(struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800051c8`

## callees

- `0x1800056c4`
- `0x180005728`

## pseudocode

```c
VARIANTARG *__fastcall std::_Uninit_copy<std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<ATL::CComVariant>>>,ATL::CComVariant *,std::allocator<ATL::CComVariant>>(
        struct tagVARIANT *a1,
        struct tagVARIANT *a2,
        VARIANTARG *a3)
{
  while ( a1 != a2 )
  {
    a3->vt = 0;
    ATL::CComVariant::InternalCopy(a3++, a1++);
  }
  return a3;
}

```

## disassembly

```asm
0x1800056c4  mov     rax, rsp
0x1800056c7  mov     [rax+8], rbx
0x1800056cb  mov     [rax+10h], rsi
0x1800056cf  mov     [rax+20h], r9
0x1800056d3  mov     [rax+18h], r8
0x1800056d7  push    rdi
0x1800056d8  sub     rsp, 20h
0x1800056dc  mov     rsi, r8
0x1800056df  mov     rdi, rdx
0x1800056e2  mov     rbx, rcx
0x1800056e5  mov     [rsp+28h+arg_18], r8
0x1800056ea  cmp     rbx, rdi
0x1800056ed  jz      short loc_18000570E
0x1800056ef  xor     eax, eax
0x1800056f1  mov     [rsi], ax
0x1800056f4  mov     rdx, rbx; struct tagVARIANT *
0x1800056f7  mov     rcx, rsi; this
0x1800056fa  call    ?InternalCopy@CComVariant@ATL@@QEAAXPEBUtagVARIANT@@@Z; ATL::CComVariant::InternalCopy(tagVARIANT const *)
0x1800056ff  add     rsi, 18h
0x180005703  mov     [rsp+28h+arg_10], rsi
0x180005708  add     rbx, 18h
0x18000570c  jmp     short loc_1800056EA
0x18000570e  mov     rax, rsi
0x180005711  mov     rbx, [rsp+28h+arg_0]
0x180005716  mov     rsi, [rsp+28h+arg_8]
0x18000571b  add     rsp, 20h
0x18000571f  pop     rdi
0x180005720  retn
```
