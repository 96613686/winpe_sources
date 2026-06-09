# CComponentTypes::Load(IPropertyBag2 *,IErrorLog *)

- ea: `0x18002ebb0`
- end: `0x18002efab`
- name: `?Load@CComponentTypes@@UEAAJPEAUIPropertyBag2@@PEAUIErrorLog@@@Z`
- size: `1019`
- prototype: `__int64 __fastcall(CComponentTypes *__hidden this, struct IPropertyBag2 *, struct IErrorLog *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180004740`
- `0x180004b48`
- `0x1800054bc`
- `0x180006b38`
- `0x1800149b0`
- `0x18002ebb0`
- `0x180030cb4`
- `0x18003125c`
- `0x180032668`
- `0x1800f8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18002ed9e`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18002ed9e`
- `ole32!CoTaskMemFree` at `0x18002ef19`
- `ole32!CoTaskMemFree` at `0x18002ef19`
- `OLEAUT32!__imp_VariantClear` at `0x18002ef42`
- `OLEAUT32!__imp_VariantClear` at `0x18002ef42`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CComponentTypes::Load(CComponentTypes *this, struct IPropertyBag2 *a2, struct IErrorLog *a3)
{
  __int64 result; // rax
  unsigned __int64 v4; // rdx
  unsigned __int64 v5; // rdx
  __int64 v6; // rbx
  VARIANTARG *i; // rdi
  unsigned __int64 v8; // rdx
  unsigned __int64 v9; // rdx
  __int64 v10; // rbx
  VARIANTARG *j; // rdi
  unsigned __int64 v12; // rdx
  unsigned __int64 v13; // rdx
  __int64 v14; // rbx
  VARIANTARG *k; // rdi
  unsigned __int64 v16; // rdx
  unsigned __int64 v17; // rdx
  __int64 v18; // rbx
  VARIANTARG *m; // rdi
  _BYTE v20[32]; // [rsp+0h] [rbp-C8h] BYREF
  VARIANTARG *v21; // [rsp+40h] [rbp-88h]
  void *v22; // [rsp+48h] [rbp-80h]
  void *v23; // [rsp+50h] [rbp-78h]
  unsigned int v24; // [rsp+60h] [rbp-68h] BYREF
  ComException *v25; // [rsp+88h] [rbp-40h] BYREF
  std::bad_alloc *v26; // [rsp+90h] [rbp-38h] BYREF
  std::exception *v27; // [rsp+98h] [rbp-30h] BYREF
  unsigned int v28; // [rsp+E8h] [rbp+20h]

  if ( !a2 )
    return 2147500035LL;
  v22 = 0;
  v21 = 0;
  v23 = 0;
  v28 = 0;
  try
  {
    result = ((__int64 (*)(void))a2->lpVtbl->CountProperties)();
    if ( (int)result >= 0 )
      result = 0;
  }
  catch ( long v24 )
  {
    operator delete(v22, (unsigned __int64)v20);
    operator delete(v23, v4);
    v6 = 0;
    for ( i = v21; (unsigned int)v6 < v28; v6 = (unsigned int)(v6 + 1) )
      VariantClear(&i[v6]);
    operator delete(i, v5);
    return v24;
  }
  catch ( ComException *v25 )
  {
    operator delete(v22, (unsigned __int64)v20);
    operator delete(v23, v8);
    v10 = 0;
    for ( j = v21; (unsigned int)v10 < v28; v10 = (unsigned int)(v10 + 1) )
      VariantClear(&j[v10]);
    operator delete(j, v9);
    return *(unsigned int *)v25;
  }
  catch ( std::bad_alloc *v26 )
  {
    operator delete(v22, (unsigned __int64)v20);
    operator delete(v23, v12);
    v14 = 0;
    for ( k = v21; (unsigned int)v14 < v28; v14 = (unsigned int)(v14 + 1) )
      VariantClear(&k[v14]);
    operator delete(k, v13);
    return 2147942414LL;
  }
  catch ( std::exception *v27 )
  {
    operator delete(v22, (unsigned __int64)v20);
    operator delete(v23, v16);
    v18 = 0;
    for ( m = v21; (unsigned int)v18 < v28; v18 = (unsigned int)(v18 + 1) )
      VariantClear(&m[v18]);
    operator delete(m, v17);
    return 2147549183LL;
  }
  return result;
}

```

## disassembly

```asm
0x18002ebb0  mov     [rsp+arg_0], rbx
0x18002ebb5  push    rsi
0x18002ebb6  push    rdi
0x18002ebb7  push    r13
0x18002ebb9  push    r14
0x18002ebbb  push    r15
0x18002ebbd  sub     rsp, 0A0h
0x18002ebc4  mov     r15, r8
0x18002ebc7  mov     rdi, rdx
0x18002ebca  mov     r13, rcx
0x18002ebcd  test    rdx, rdx
0x18002ebd0  jnz     short loc_18002EBDC
0x18002ebd2  mov     eax, 80004003h
0x18002ebd7  jmp     loc_18002EF92
0x18002ebdc  mov     [rsp+0C8h+var_80], 0
0x18002ebe5  mov     [rsp+0C8h+var_88], 0
0x18002ebee  mov     [rsp+0C8h+var_78], 0
0x18002ebf7  mov     [rsp+0C8h+arg_18], 0
0x18002ec02  mov     [rsp+0C8h+arg_8], 0
0x18002ec0d  mov     rax, [rdx]
0x18002ec10  lea     rdx, [rsp+0C8h+arg_8]
0x18002ec18  mov     rcx, rdi
0x18002ec1b  mov     rax, [rax+28h]
0x18002ec1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec24  test    eax, eax
0x18002ec26  js      loc_18002EF92
0x18002ec2c  mov     eax, [rsp+0C8h+arg_8]
0x18002ec33  test    eax, eax
0x18002ec35  jz      loc_18002EF92
0x18002ec3b  mov     rcx, rax
0x18002ec3e  mov     eax, 28h ; '('
0x18002ec43  mul     rcx
0x18002ec46  mov     r14, 0FFFFFFFFFFFFFFFFh
0x18002ec4d  cmovb   rax, r14
0x18002ec51  mov     rcx, rax; unsigned __int64
0x18002ec54  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002ec59  mov     rbx, rax
0x18002ec5c  mov     [rsp+0C8h+var_80], rax
0x18002ec61  mov     rax, [rdi]
0x18002ec64  lea     rcx, [rsp+0C8h+arg_18]
0x18002ec6c  mov     [rsp+0C8h+var_A8], rcx
0x18002ec71  mov     r9, rbx
0x18002ec74  mov     r8d, [rsp+0C8h+arg_8]
0x18002ec7c  xor     edx, edx
0x18002ec7e  mov     rcx, rdi
0x18002ec81  mov     rax, [rax+30h]
0x18002ec85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec8a  mov     esi, eax
0x18002ec8c  test    eax, eax
0x18002ec8e  jns     short loc_18002EC9F
0x18002ec90  mov     rcx, rbx; void *
0x18002ec93  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002ec98  mov     eax, esi
0x18002ec9a  jmp     loc_18002EF92
0x18002ec9f  mov     eax, [rsp+0C8h+arg_18]
0x18002eca6  cmp     [rsp+0C8h+arg_8], eax
0x18002ecad  jz      short loc_18002ECC1
0x18002ecaf  mov     rcx, rbx; void *
0x18002ecb2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002ecb7  mov     eax, 8000FFFFh
0x18002ecbc  jmp     loc_18002EF92
0x18002ecc1  mov     rcx, rax
0x18002ecc4  mov     eax, 4
0x18002ecc9  mul     rcx
0x18002eccc  cmovb   rax, r14
0x18002ecd0  mov     rcx, rax; unsigned __int64
0x18002ecd3  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002ecd8  mov     r14, rax
0x18002ecdb  mov     [rsp+0C8h+var_78], rax
0x18002ece0  mov     ecx, [rsp+0C8h+arg_18]
0x18002ece7  mov     eax, 18h
0x18002ecec  mul     rcx
0x18002ecef  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002ecf6  cmovb   rax, rcx
0x18002ecfa  mov     rcx, rax; unsigned __int64
0x18002ecfd  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002ed02  mov     rsi, rax
0x18002ed05  mov     [rsp+0C8h+var_88], rax
0x18002ed0a  mov     eax, [rsp+0C8h+arg_18]
0x18002ed11  lea     r8, [rax+rax*2]
0x18002ed15  shl     r8, 3; Size
0x18002ed19  xor     edx, edx; Val
0x18002ed1b  mov     rcx, rsi; void *
0x18002ed1e  call    memset_0
0x18002ed23  mov     rax, [rdi]
0x18002ed26  mov     [rsp+0C8h+var_A0], r14
0x18002ed2b  mov     [rsp+0C8h+var_A8], rsi
0x18002ed30  mov     r9, r15
0x18002ed33  mov     r8, rbx
0x18002ed36  mov     edx, [rsp+0C8h+arg_18]
0x18002ed3d  mov     rcx, rdi
0x18002ed40  mov     rax, [rax+18h]
0x18002ed44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ed49  mov     edi, eax
0x18002ed4b  test    eax, eax
0x18002ed4d  jns     short loc_18002ED6E
0x18002ed4f  mov     rcx, rbx; void *
0x18002ed52  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002ed57  mov     rcx, r14; void *
0x18002ed5a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002ed5f  mov     rcx, rsi; void *
0x18002ed62  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002ed67  mov     eax, edi
0x18002ed69  jmp     loc_18002EF92
0x18002ed6e  xor     r8d, r8d
0x18002ed71  xor     eax, eax
0x18002ed73  mov     [rsp+0C8h+arg_8], r8d
0x18002ed7b  cmp     eax, [rsp+0C8h+arg_18]
0x18002ed82  jnb     loc_18002EF5B
0x18002ed88  mov     ecx, eax
0x18002ed8a  cmp     dword ptr [r14+rcx*4], 0
0x18002ed8f  jl      loc_18002EF0D
0x18002ed95  lea     rcx, [rcx+rcx*4]
0x18002ed99  mov     rcx, [rbx+rcx*8+10h]
0x18002ed9e  call    cs:__imp__o__wtoi
0x18002eda4  mov     r9d, eax
0x18002eda7  mov     r8d, [rsp+0C8h+arg_8]
0x18002edaf  lea     rdx, [r8+r8*4]
0x18002edb3  cmp     word ptr [rbx+rdx*8+4], 9
0x18002edb9  jz      loc_18002EE69
0x18002edbf  cmp     word ptr [rbx+rdx*8+4], 0Dh
0x18002edc5  jnz     loc_18002EF0D
0x18002edcb  lea     rdi, [r13+48h]
0x18002edcf  mov     r15d, r9d
0x18002edd2  mov     rax, [rdi+8]
0x18002edd6  sub     rax, [rdi]
0x18002edd9  sar     rax, 3
0x18002eddd  cmp     r9, rax
0x18002ede0  jb      short loc_18002EE45
0x18002ede2  lea     edx, [r9+1]
0x18002ede6  mov     rcx, rdi
0x18002ede9  call    ?reserve@?$vector@V?$CComQIPtr@UIComponentType@@$1?_GUID_6a340dc0_0311_11d3_9d8e_00c04f72d980@@3U__s_GUID@@B@ATL@@V?$allocator@V?$CComQIPtr@UIComponentType@@$1?_GUID_6a340dc0_0311_11d3_9d8e_00c04f72d980@@3U__s_GUID@@B@ATL@@@std@@@std@@QEAAX_K@Z; std::vector<ATL::CComQIPtr<IComponentType,&__s_GUID const _GUID_6a340dc0_0311_11d3_9d8e_00c04f72d980>>::reserve(unsigned __int64)
0x18002edee  mov     [rsp+0C8h+var_70], 0
0x18002edf7  lea     rdx, [rsp+0C8h+var_60]
0x18002edfc  mov     rcx, rdi
0x18002edff  call    ?end@?$vector@VCComBSTR@ATL@@V?$allocator@VCComBSTR@ATL@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VCComBSTR@ATL@@@std@@@std@@@2@XZ; std::vector<ATL::CComBSTR>::end(void)
0x18002ee04  mov     rcx, [rdi+8]
0x18002ee08  sub     rcx, [rdi]
0x18002ee0b  sar     rcx, 3
0x18002ee0f  mov     r9d, r15d
0x18002ee12  sub     r9, rcx
0x18002ee15  inc     r9
0x18002ee18  lea     rcx, [rsp+0C8h+var_70]
0x18002ee1d  mov     [rsp+0C8h+var_A8], rcx
0x18002ee22  mov     r8, [rax]
0x18002ee25  lea     rdx, [rsp+0C8h+var_58]
0x18002ee2a  mov     rcx, rdi
0x18002ee2d  call    ?insert@?$vector@V?$CComQIPtr@UIComponentType@@$1?_GUID_6a340dc0_0311_11d3_9d8e_00c04f72d980@@3U__s_GUID@@B@ATL@@V?$allocator@V?$CComQIPtr@UIComponentType@@$1?_GUID_6a340dc0_0311_11d3_9d8e_00c04f72d980@@3U__s_GUID@@B@ATL@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$CComQIPtr@UIComponentType@@$1?_GUID_6a340dc0_0311_11d3_9d8e_00c04f72d980@@3U__s_GUID@@B@ATL@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$CComQIPtr@UIComponentType@@$1?_GUID_6a340dc0_0311_11d3_9d8e_00c04f72d980@@3U__s_GUID@@B@ATL@@@std@@@std@@@2@_KAEBV?$CComQIPtr@UIComponentType@@$1?_GUID_6a340dc0_0311_11d3_9d8e_00c04f72d980@@3U__s_GUID@@B@ATL@@@Z; std::vector<ATL::CComQIPtr<IComponentType,&__s_GUID const _GUID_6a340dc0_0311_11d3_9d8e_00c04f72d980>>::insert(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<ATL::CComQIPtr<IComponentType,&__s_GUID const _GUID_6a340dc0_0311_11d3_9d8e_00c04f72d980>>>>,unsigned __int64,ATL::CComQIPtr<IComponentType,&__s_GUID const _GUID_6a340dc0_0311_11d3_9d8e_00c04f72d980> const &)
0x18002ee32  nop
0x18002ee33  lea     rcx, [rsp+0C8h+var_70]
0x18002ee38  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18002ee3d  mov     r8d, [rsp+0C8h+arg_8]
0x18002ee45  mov     eax, r8d
0x18002ee48  lea     rdx, [rax+rax*2]
0x18002ee4c  mov     rax, [rdi]
0x18002ee4f  lea     rcx, [rax+r15*8]; struct IUnknown **
0x18002ee53  lea     r8, _GUID_6a340dc0_0311_11d3_9d8e_00c04f72d980; struct _GUID *
0x18002ee5a  mov     rdx, [rsi+rdx*8+8]; struct IUnknown *
0x18002ee5f  call    ?AtlComQIPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@AEBU_GUID@@@Z; ATL::AtlComQIPtrAssign(IUnknown * *,IUnknown *,_GUID const &)
0x18002ee64  jmp     loc_18002EF05
0x18002ee69  lea     rdi, [r13+48h]
0x18002ee6d  mov     r15, r9
0x18002ee70  mov     rax, [rdi+8]
0x18002ee74  sub     rax, [rdi]
0x18002ee77  sar     rax, 3
0x18002ee7b  cmp     r9, rax
0x18002ee7e  jb      short loc_18002EEE6
0x18002ee80  lea     edx, [r9+1]
0x18002ee84  mov     rcx, rdi
0x18002ee87  call    ?reserve@?$vector@V?$CComQIPtr@UIComponentType@@$1?_GUID_6a340dc0_0311_11d3_9d8e_00c04f72d980@@3U__s_GUID@@B@ATL@@V?$allocator@V?$CComQIPtr@UIComponentType@@$1?_GUID_6a340dc0_0311_11d3_9d8e_00c04f72d980@@3U__s_GUID@@B@ATL@@@std@@@std@@QEAAX_K@Z; std::vector<ATL::CComQIPtr<IComponentType,&__s_GUID const _GUID_6a340dc0_0311_11d3_9d8e_00c04f72d980>>::reserve(unsigned __int64)
0x18002ee8c  mov     [rsp+0C8h+var_70], 0
0x18002ee95  lea     rdx, [rsp+0C8h+var_50]
0x18002ee9a  mov     rcx, rdi
0x18002ee9d  call    ?end@?$vector@VCComBSTR@ATL@@V?$allocator@VCComBSTR@ATL@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VCComBSTR@ATL@@@std@@@std@@@2@XZ; std::vector<ATL::CComBSTR>::end(void)
0x18002eea2  mov     rcx, [rdi+8]
0x18002eea6  sub     rcx, [rdi]
0x18002eea9  sar     rcx, 3
0x18002eead  mov     r9, r15
0x18002eeb0  sub     r9, rcx
0x18002eeb3  inc     r9
0x18002eeb6  lea     rcx, [rsp+0C8h+var_70]
0x18002eebb  mov     [rsp+0C8h+var_A8], rcx
0x18002eec0  mov     r8, [rax]
0x18002eec3  lea     rdx, [rsp+0C8h+var_48]
0x18002eecb  mov     rcx, rdi
0x18002eece  call    ?insert@?$vector@V?$CComQIPtr@UIComponentType@@$1?_GUID_6a340dc0_0311_11d3_9d8e_00c04f72d980@@3U__s_GUID@@B@ATL@@V?$allocator@V?$CComQIPtr@UIComponentType@@$1?_GUID_6a340dc0_0311_11d3_9d8e_00c04f72d980@@3U__s_GUID@@B@ATL@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$CComQIPtr@UIComponentType@@$1?_GUID_6a340dc0_0311_11d3_9d8e_00c04f72d980@@3U__s_GUID@@B@ATL@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$CComQIPtr@UIComponentType@@$1?_GUID_6a340dc0_0311_11d3_9d8e_00c04f72d980@@3U__s_GUID@@B@ATL@@@std@@@std@@@2@_KAEBV?$CComQIPtr@UIComponentType@@$1?_GUID_6a340dc0_0311_11d3_9d8e_00c04f72d980@@3U__s_GUID@@B@ATL@@@Z; std::vector<ATL::CComQIPtr<IComponentType,&__s_GUID const _GUID_6a340dc0_0311_11d3_9d8e_00c04f72d980>>::insert(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<ATL::CComQIPtr<IComponentType,&__s_GUID const _GUID_6a340dc0_0311_11d3_9d8e_00c04f72d980>>>>,unsigned __int64,ATL::CComQIPtr<IComponentType,&__s_GUID const _GUID_6a340dc0_0311_11d3_9d8e_00c04f72d980> const &)
0x18002eed3  nop
0x18002eed4  lea     rcx, [rsp+0C8h+var_70]
0x18002eed9  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18002eede  mov     r8d, [rsp+0C8h+arg_8]
0x18002eee6  mov     eax, r8d
0x18002eee9  lea     rdx, [rax+rax*2]
0x18002eeed  mov     rax, [rdi]
0x18002eef0  lea     rcx, [rax+r15*8]; struct IUnknown **
0x18002eef4  lea     r8, _GUID_6a340dc0_0311_11d3_9d8e_00c04f72d980; struct _GUID *
0x18002eefb  mov     rdx, [rsi+rdx*8+8]; struct IUnknown *
0x18002ef00  call    ?AtlComQIPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@AEBU_GUID@@@Z; ATL::AtlComQIPtrAssign(IUnknown * *,IUnknown *,_GUID const &)
0x18002ef05  mov     r8d, [rsp+0C8h+arg_8]
0x18002ef0d  mov     eax, r8d
0x18002ef10  lea     rcx, [rax+rax*4]
0x18002ef14  mov     rcx, [rbx+rcx*8+10h]; pv
0x18002ef19  call    cs:__imp_CoTaskMemFree
0x18002ef1f  mov     eax, [rsp+0C8h+arg_8]
0x18002ef26  lea     rcx, [rax+rax*4]
0x18002ef2a  mov     qword ptr [rbx+rcx*8+10h], 0
0x18002ef33  mov     eax, [rsp+0C8h+arg_8]
0x18002ef3a  lea     rcx, [rax+rax*2]
0x18002ef3e  lea     rcx, [rsi+rcx*8]; pvarg
0x18002ef42  call    cs:__imp_VariantClear
0x18002ef48  mov     r8d, [rsp+0C8h+arg_8]
0x18002ef50  inc     r8d
0x18002ef53  mov     eax, r8d
0x18002ef56  jmp     loc_18002ED73
0x18002ef5b  mov     rcx, rbx; void *
0x18002ef5e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002ef63  mov     rcx, r14; void *
0x18002ef66  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002ef6b  mov     rcx, rsi; void *
0x18002ef6e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002ef73  xor     eax, eax
0x18002ef75  jmp     short loc_18002EF92
0x18002ef77  mov     eax, [rsp+0C8h+var_68]
0x18002ef7b  jmp     short loc_18002EF92
0x18002ef7d  mov     eax, [rsp+0C8h+arg_8]
0x18002ef84  jmp     short loc_18002EF92
0x18002ef86  mov     eax, 8007000Eh
0x18002ef8b  jmp     short loc_18002EF92
0x18002ef8d  mov     eax, 8000FFFFh
0x18002ef92  mov     rbx, [rsp+0C8h+arg_0]
0x18002ef9a  add     rsp, 0A0h
0x18002efa1  pop     r15
0x18002efa3  pop     r14
0x18002efa5  pop     r13
0x18002efa7  pop     rdi
0x18002efa8  pop     rsi
0x18002efa9  retn
```
