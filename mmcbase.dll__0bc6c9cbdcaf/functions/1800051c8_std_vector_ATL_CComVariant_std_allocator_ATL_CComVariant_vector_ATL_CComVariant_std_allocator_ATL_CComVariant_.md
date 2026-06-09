# std::vector<ATL::CComVariant,std::allocator<ATL::CComVariant>>::vector<ATL::CComVariant,std::allocator<ATL::CComVariant>>(std::vector<ATL::CComVariant,std::allocator<ATL::CComVariant>> const &)

- ea: `0x1800051c8`
- end: `0x180005289`
- name: `??0?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@QEAA@AEBV01@@Z`
- size: `193`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180004bf0`
- `0x180004e20`
- `0x180005170`

## callees

- `0x1800051c8`
- `0x1800056c4`
- `0x180009928`
- `0x180009950`

## import_xrefs

- `MFC42u!__imp_??2@YAPEAX_K@Z` at `0x180005255`
- `MFC42u!__imp_??2@YAPEAX_K@Z` at `0x180005255`

## pseudocode

```c
_QWORD *__fastcall std::vector<ATL::CComVariant>::vector<ATL::CComVariant>(_QWORD *a1, __int64 a2)
{
  unsigned __int64 v4; // rax
  unsigned __int64 v6; // rsi
  char *v7; // rax

  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  v4 = 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*(_QWORD *)(a2 + 8) - *(_QWORD *)a2) >> 3);
  if ( v4 )
  {
    if ( v4 > 0xAAAAAAAAAAAAAAALL )
      std::_Xlength_error("vector<T> too long");
    v6 = 8 * ((__int64)(*(_QWORD *)(a2 + 8) - *(_QWORD *)a2) >> 3);
    v7 = (char *)operator new(v6);
    if ( !v7 )
      std::_Xbad_alloc();
    *a1 = v7;
    a1[1] = v7;
    a1[2] = &v7[v6];
    try
    {
      a1[1] = std::_Uninit_copy<std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<ATL::CComVariant>>>,ATL::CComVariant *,std::allocator<ATL::CComVariant>>(*(struct tagVARIANT **)a2);
    }
    catch ( ... )
    {
      std::vector<ATL::CComVariant>::_Tidy(a1);
      throw;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x1800051c8  mov     [rsp+arg_8], rbx
0x1800051cd  mov     [rsp+arg_10], rsi
0x1800051d2  mov     [rsp+arg_0], rcx
0x1800051d7  push    rdi
0x1800051d8  sub     rsp, 30h
0x1800051dc  mov     rdi, rdx
0x1800051df  mov     rbx, rcx
0x1800051e2  mov     qword ptr [rcx], 0
0x1800051e9  mov     qword ptr [rcx+8], 0
0x1800051f1  mov     qword ptr [rcx+10h], 0
0x1800051f9  mov     rax, [rdx+8]
0x1800051fd  sub     rax, [rdx]
0x180005200  sar     rax, 3
0x180005204  mov     rcx, 0AAAAAAAAAAAAAAABh
0x18000520e  imul    rax, rcx
0x180005212  test    rax, rax
0x180005215  jnz     short loc_18000522A
0x180005217  mov     rax, rbx
0x18000521a  mov     rbx, [rsp+38h+arg_8]
0x18000521f  mov     rsi, [rsp+38h+arg_10]
0x180005224  add     rsp, 30h
0x180005228  pop     rdi
0x180005229  retn
0x18000522a  mov     rcx, 0AAAAAAAAAAAAAAAh
0x180005234  cmp     rax, rcx
0x180005237  jbe     short loc_180005246
0x180005239  lea     rcx, aVectorTTooLong; "vector<T> too long"
0x180005240  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180005246  lea     rax, [rax+rax*2]
0x18000524a  lea     rsi, ds:0[rax*8]
0x180005252  mov     rcx, rsi
0x180005255  call    cs:__imp_??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000525b  mov     r8, rax
0x18000525e  test    rax, rax
0x180005261  jnz     short loc_180005269
0x180005263  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180005269  mov     [rbx], r8
0x18000526c  mov     [rbx+8], r8
0x180005270  add     rax, rsi
0x180005273  mov     [rbx+10h], rax
0x180005277  mov     rdx, [rdi+8]
0x18000527b  mov     rcx, [rdi]; struct tagVARIANT *
0x18000527e  call    ??$_Uninit_copy@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@VCComVariant@ATL@@@std@@@std@@@std@@PEAVCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@2@@std@@YAPEAVCComVariant@ATL@@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@VCComVariant@ATL@@@std@@@std@@@0@0PEAV12@AEAU?$_Wrap_alloc@V?$allocator@VCComVariant@ATL@@@std@@@0@U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_copy<std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<ATL::CComVariant>>>,ATL::CComVariant *,std::allocator<ATL::CComVariant>>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<ATL::CComVariant>>>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<ATL::CComVariant>>>,ATL::CComVariant *,std::_Wrap_alloc<std::allocator<ATL::CComVariant>> &,std::_Nonscalar_ptr_iterator_tag)
0x180005283  mov     [rbx+8], rax
0x180005287  jmp     short loc_180005217
```
