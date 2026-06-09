# ATL::CComEnumImpl<IEnumVARIANT,&_GUID const IID_IEnumVARIANT,tagVARIANT,ATL::_Copy<tagVARIANT>,ATL::CComEnum<IEnumVARIANT,&_GUID const IID_IEnumVARIANT,tagVARIANT,ATL::_Copy<tagVARIANT>,ATL::CComSingleThreadModel>>::Clone(IEnumVARIANT * *)

- ea: `0x18002443c`
- end: `0x18002453f`
- name: `?Clone@?$CComEnumImpl@UIEnumVARIANT@@$1?IID_IEnumVARIANT@@3U_GUID@@BUtagVARIANT@@V?$_Copy@UtagVARIANT@@@ATL@@V?$CComEnum@UIEnumVARIANT@@$1?IID_IEnumVARIANT@@3U_GUID@@BUtagVARIANT@@V?$_Copy@UtagVARIANT@@@ATL@@VCComSingleThreadModel@6@@6@@ATL@@UEAAJPEAPEAUIEnumVARIANT@@@Z`
- size: `259`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180024430`

## callees

- `0x1800033ec`
- `0x180009144`
- `0x180009174`
- `0x18000962c`
- `0x180024268`
- `0x18002443c`
- `0x180024548`
- `0x1800245e0`

## pseudocode

```c
__int64 __fastcall ATL::CComEnumImpl<IEnumVARIANT,&_GUID const IID_IEnumVARIANT,tagVARIANT,ATL::_Copy<tagVARIANT>,ATL::CComEnum<IEnumVARIANT,&_GUID const IID_IEnumVARIANT,tagVARIANT,ATL::_Copy<tagVARIANT>,ATL::CComSingleThreadModel>>::Clone(
        __int64 a1,
        void **a2)
{
  int Interface; // ebx
  int v5; // ebp
  struct IUnknown **v6; // rax
  int v7; // r15d
  _QWORD *v8; // rsi
  void *Block; // [rsp+68h] [rbp+10h] BYREF
  char v11; // [rsp+70h] [rbp+18h] BYREF
  char v12; // [rsp+78h] [rbp+20h] BYREF

  Interface = -2147467261;
  if ( a2 )
  {
    *a2 = 0;
    Block = 0;
    Interface = ATL::CComObject<ATL::CComEnum<IEnumVARIANT,&_GUID const IID_IEnumVARIANT,tagVARIANT,ATL::_Copy<tagVARIANT>,ATL::CComSingleThreadModel>>::CreateInstance(&Block);
    if ( Interface >= 0 )
    {
      v5 = 1;
      if ( (*(_BYTE *)(a1 + 40) & 1) != 0 )
      {
        v6 = (struct IUnknown **)ATL::CComPtr<IUnknown>::CComPtr<IUnknown>(&v12, a1);
        v7 = 0;
      }
      else
      {
        v6 = (struct IUnknown **)ATL::CComPtr<IUnknown>::CComPtr<IUnknown>(&v11, a1 + 8);
        v5 = 0;
        v7 = 2;
      }
      v8 = Block;
      Interface = ATL::CComEnumImpl<IEnumVARIANT,&_GUID const IID_IEnumVARIANT,tagVARIANT,ATL::_Copy<tagVARIANT>,ATL::CComEnum<IEnumVARIANT,&_GUID const IID_IEnumVARIANT,tagVARIANT,ATL::_Copy<tagVARIANT>,ATL::CComSingleThreadModel>>::Init(
                    (__int64)Block,
                    *(const VARIANTARG **)(a1 + 16),
                    *(_QWORD *)(a1 + 24),
                    *v6,
                    0);
      if ( v7 )
        R<IADs>::~R<IADs>(&v11);
      if ( v5 )
        R<IADs>::~R<IADs>(&v12);
      if ( Interface < 0
        || (v8[4] = *(_QWORD *)(a1 + 32),
            Interface = ATL::AtlInternalQueryInterface(
                          v8,
                          (const struct ATL::_ATL_INTMAP_ENTRY *)&`ATL::CComEnum<IEnumVARIANT,&_GUID const IID_IEnumVARIANT,tagVARIANT,ATL::_Copy<tagVARIANT>,ATL::CComSingleThreadModel>::_GetEntries'::`2'::_entries,
                          &IID_IEnumVARIANT,
                          a2),
            Interface < 0) )
      {
        if ( v8 )
          ATL::CComObject<ATL::CComEnum<IEnumVARIANT,&_GUID const IID_IEnumVARIANT,tagVARIANT,ATL::_Copy<tagVARIANT>,ATL::CComSingleThreadModel>>::`scalar deleting destructor'(v8);
      }
    }
  }
  return (unsigned int)Interface;
}

```

## disassembly

```asm
0x18002443c  mov     [rsp+arg_0], rbx
0x180024441  push    rbp
0x180024442  push    rsi
0x180024443  push    rdi
0x180024444  push    r14
0x180024446  push    r15
0x180024448  sub     rsp, 30h
0x18002444c  mov     r14, rdx
0x18002444f  mov     rdi, rcx
0x180024452  mov     ebx, 80004003h
0x180024457  test    rdx, rdx
0x18002445a  jz      loc_18002452C
0x180024460  lea     rcx, [rsp+58h+Block]
0x180024465  mov     qword ptr [rdx], 0
0x18002446c  mov     [rsp+58h+Block], 0
0x180024475  call    ?CreateInstance@?$CComObject@V?$CComEnum@UIEnumVARIANT@@$1?IID_IEnumVARIANT@@3U_GUID@@BUtagVARIANT@@V?$_Copy@UtagVARIANT@@@ATL@@VCComSingleThreadModel@6@@ATL@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<ATL::CComEnum<IEnumVARIANT,&_GUID const IID_IEnumVARIANT,tagVARIANT,ATL::_Copy<tagVARIANT>,ATL::CComSingleThreadModel>>::CreateInstance(ATL::CComObject<ATL::CComEnum<IEnumVARIANT,&_GUID const IID_IEnumVARIANT,tagVARIANT,ATL::_Copy<tagVARIANT>,ATL::CComSingleThreadModel>> * *)
0x18002447a  mov     ebx, eax
0x18002447c  test    eax, eax
0x18002447e  js      loc_18002452C
0x180024484  mov     ebp, 1
0x180024489  test    [rdi+28h], bpl
0x18002448d  jz      short loc_1800244A1
0x18002448f  mov     rdx, rdi
0x180024492  lea     rcx, [rsp+58h+arg_18]
0x180024497  call    ??0?$CComPtr@UIUnknown@@@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComPtr<IUnknown>::CComPtr<IUnknown>(IUnknown *)
0x18002449c  xor     r15d, r15d
0x18002449f  jmp     short loc_1800244B5
0x1800244a1  lea     rdx, [rdi+8]
0x1800244a5  lea     rcx, [rsp+58h+arg_10]
0x1800244aa  call    ??0?$CComPtr@UIUnknown@@@ATL@@QEAA@AEBV01@@Z; ATL::CComPtr<IUnknown>::CComPtr<IUnknown>(ATL::CComPtr<IUnknown> const &)
0x1800244af  xor     ebp, ebp
0x1800244b1  lea     r15d, [rbp+2]
0x1800244b5  mov     rsi, [rsp+58h+Block]
0x1800244ba  mov     r9, [rax]
0x1800244bd  mov     rcx, rsi
0x1800244c0  mov     r8, [rdi+18h]
0x1800244c4  mov     rdx, [rdi+10h]
0x1800244c8  mov     [rsp+58h+var_38], 0
0x1800244d0  call    ?Init@?$CComEnumImpl@UIEnumVARIANT@@$1?IID_IEnumVARIANT@@3U_GUID@@BUtagVARIANT@@V?$_Copy@UtagVARIANT@@@ATL@@V?$CComEnum@UIEnumVARIANT@@$1?IID_IEnumVARIANT@@3U_GUID@@BUtagVARIANT@@V?$_Copy@UtagVARIANT@@@ATL@@VCComSingleThreadModel@6@@6@@ATL@@QEAAJPEAUtagVARIANT@@0PEAUIUnknown@@W4CComEnumFlags@2@@Z; ATL::CComEnumImpl<IEnumVARIANT,&_GUID const IID_IEnumVARIANT,tagVARIANT,ATL::_Copy<tagVARIANT>,ATL::CComEnum<IEnumVARIANT,&_GUID const IID_IEnumVARIANT,tagVARIANT,ATL::_Copy<tagVARIANT>,ATL::CComSingleThreadModel>>::Init(tagVARIANT *,tagVARIANT *,IUnknown *,ATL::CComEnumFlags)
0x1800244d5  mov     ebx, eax
0x1800244d7  test    r15d, r15d
0x1800244da  jz      short loc_1800244E6
0x1800244dc  lea     rcx, [rsp+58h+arg_10]
0x1800244e1  call    ??1?$R@UIADs@@@@QEAA@XZ; R<IADs>::~R<IADs>(void)
0x1800244e6  test    ebp, ebp
0x1800244e8  jz      short loc_1800244F4
0x1800244ea  lea     rcx, [rsp+58h+arg_18]
0x1800244ef  call    ??1?$R@UIADs@@@@QEAA@XZ; R<IADs>::~R<IADs>(void)
0x1800244f4  test    ebx, ebx
0x1800244f6  js      short loc_18002451F
0x1800244f8  mov     rax, [rdi+20h]
0x1800244fc  lea     r8, IID_IEnumVARIANT; struct _GUID *
0x180024503  mov     r9, r14; void **
0x180024506  mov     [rsi+20h], rax
0x18002450a  lea     rdx, ?_entries@?1??_GetEntries@?$CComEnum@UIEnumVARIANT@@$1?IID_IEnumVARIANT@@3U_GUID@@BUtagVARIANT@@V?$_Copy@UtagVARIANT@@@ATL@@VCComSingleThreadModel@6@@ATL@@SAPEBU_ATL_INTMAP_ENTRY@3@XZ@4QBU43@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180024511  mov     rcx, rsi; void *
0x180024514  call    ?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z; ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180024519  mov     ebx, eax
0x18002451b  test    eax, eax
0x18002451d  jns     short loc_18002452C
0x18002451f  test    rsi, rsi
0x180024522  jz      short loc_18002452C
0x180024524  mov     rcx, rsi; Block
0x180024527  call    ??_G?$CComObject@V?$CComEnum@UIEnumVARIANT@@$1?IID_IEnumVARIANT@@3U_GUID@@BUtagVARIANT@@V?$_Copy@UtagVARIANT@@@ATL@@VCComSingleThreadModel@6@@ATL@@@ATL@@QEAAPEAXI@Z; ATL::CComObject<ATL::CComEnum<IEnumVARIANT,&_GUID const IID_IEnumVARIANT,tagVARIANT,ATL::_Copy<tagVARIANT>,ATL::CComSingleThreadModel>>::`scalar deleting destructor'(uint)
0x18002452c  mov     eax, ebx
0x18002452e  mov     rbx, [rsp+58h+arg_0]
0x180024533  add     rsp, 30h
0x180024537  pop     r15
0x180024539  pop     r14
0x18002453b  pop     rdi
0x18002453c  pop     rsi
0x18002453d  pop     rbp
0x18002453e  retn
```
