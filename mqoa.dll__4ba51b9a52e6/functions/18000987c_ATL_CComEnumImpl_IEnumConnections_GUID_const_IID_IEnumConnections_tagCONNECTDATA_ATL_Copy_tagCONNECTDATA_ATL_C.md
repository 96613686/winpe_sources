# ATL::CComEnumImpl<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComEnum<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComSingleThreadModel>>::Clone(IEnumConnections * *)

- ea: `0x18000987c`
- end: `0x18000997f`
- name: `?Clone@?$CComEnumImpl@UIEnumConnections@@$1?IID_IEnumConnections@@3U_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@V?$CComEnum@UIEnumConnections@@$1?IID_IEnumConnections@@3U_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@VCComSingleThreadModel@6@@6@@ATL@@UEAAJPEAPEAUIEnumConnections@@@Z`
- size: `259`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180009870`

## callees

- `0x1800033ec`
- `0x180009144`
- `0x180009174`
- `0x180009374`
- `0x18000962c`
- `0x18000987c`
- `0x180009a54`
- `0x18000a1a8`

## pseudocode

```c
__int64 __fastcall ATL::CComEnumImpl<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComEnum<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComSingleThreadModel>>::Clone(
        __int64 a1,
        void **a2)
{
  int Interface; // ebx
  int v5; // ebp
  _QWORD *v6; // rax
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
    Interface = ATL::CComObject<ATL::CComEnum<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComSingleThreadModel>>::CreateInstance(&Block);
    if ( Interface >= 0 )
    {
      v5 = 1;
      if ( (*(_BYTE *)(a1 + 40) & 1) != 0 )
      {
        v6 = (_QWORD *)ATL::CComPtr<IUnknown>::CComPtr<IUnknown>(&v12, a1);
        v7 = 0;
      }
      else
      {
        v6 = (_QWORD *)ATL::CComPtr<IUnknown>::CComPtr<IUnknown>(&v11, a1 + 8);
        v5 = 0;
        v7 = 2;
      }
      v8 = Block;
      Interface = ATL::CComEnumImpl<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComEnum<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComSingleThreadModel>>::Init(
                    Block,
                    *(_QWORD *)(a1 + 16),
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
                          (const struct ATL::_ATL_INTMAP_ENTRY *)&`ATL::CComEnum<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComSingleThreadModel>::_GetEntries'::`2'::_entries,
                          &IID_IEnumConnections,
                          a2),
            Interface < 0) )
      {
        if ( v8 )
          ATL::CComObject<ATL::CComEnum<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComSingleThreadModel>>::`scalar deleting destructor'(v8);
      }
    }
  }
  return (unsigned int)Interface;
}

```

## disassembly

```asm
0x18000987c  mov     [rsp+arg_0], rbx
0x180009881  push    rbp
0x180009882  push    rsi
0x180009883  push    rdi
0x180009884  push    r14
0x180009886  push    r15
0x180009888  sub     rsp, 30h
0x18000988c  mov     r14, rdx
0x18000988f  mov     rdi, rcx
0x180009892  mov     ebx, 80004003h
0x180009897  test    rdx, rdx
0x18000989a  jz      loc_18000996C
0x1800098a0  lea     rcx, [rsp+58h+Block]
0x1800098a5  mov     qword ptr [rdx], 0
0x1800098ac  mov     [rsp+58h+Block], 0
0x1800098b5  call    ?CreateInstance@?$CComObject@V?$CComEnum@UIEnumConnections@@$1?IID_IEnumConnections@@3U_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@VCComSingleThreadModel@6@@ATL@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<ATL::CComEnum<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComSingleThreadModel>>::CreateInstance(ATL::CComObject<ATL::CComEnum<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComSingleThreadModel>> * *)
0x1800098ba  mov     ebx, eax
0x1800098bc  test    eax, eax
0x1800098be  js      loc_18000996C
0x1800098c4  mov     ebp, 1
0x1800098c9  test    [rdi+28h], bpl
0x1800098cd  jz      short loc_1800098E1
0x1800098cf  mov     rdx, rdi
0x1800098d2  lea     rcx, [rsp+58h+arg_18]
0x1800098d7  call    ??0?$CComPtr@UIUnknown@@@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComPtr<IUnknown>::CComPtr<IUnknown>(IUnknown *)
0x1800098dc  xor     r15d, r15d
0x1800098df  jmp     short loc_1800098F5
0x1800098e1  lea     rdx, [rdi+8]
0x1800098e5  lea     rcx, [rsp+58h+arg_10]
0x1800098ea  call    ??0?$CComPtr@UIUnknown@@@ATL@@QEAA@AEBV01@@Z; ATL::CComPtr<IUnknown>::CComPtr<IUnknown>(ATL::CComPtr<IUnknown> const &)
0x1800098ef  xor     ebp, ebp
0x1800098f1  lea     r15d, [rbp+2]
0x1800098f5  mov     rsi, [rsp+58h+Block]
0x1800098fa  mov     r9, [rax]
0x1800098fd  mov     rcx, rsi
0x180009900  mov     r8, [rdi+18h]
0x180009904  mov     rdx, [rdi+10h]
0x180009908  mov     [rsp+58h+var_38], 0
0x180009910  call    ?Init@?$CComEnumImpl@UIEnumConnections@@$1?IID_IEnumConnections@@3U_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@V?$CComEnum@UIEnumConnections@@$1?IID_IEnumConnections@@3U_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@VCComSingleThreadModel@6@@6@@ATL@@QEAAJPEAUtagCONNECTDATA@@0PEAUIUnknown@@W4CComEnumFlags@2@@Z; ATL::CComEnumImpl<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComEnum<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComSingleThreadModel>>::Init(tagCONNECTDATA *,tagCONNECTDATA *,IUnknown *,ATL::CComEnumFlags)
0x180009915  mov     ebx, eax
0x180009917  test    r15d, r15d
0x18000991a  jz      short loc_180009926
0x18000991c  lea     rcx, [rsp+58h+arg_10]
0x180009921  call    ??1?$R@UIADs@@@@QEAA@XZ; R<IADs>::~R<IADs>(void)
0x180009926  test    ebp, ebp
0x180009928  jz      short loc_180009934
0x18000992a  lea     rcx, [rsp+58h+arg_18]
0x18000992f  call    ??1?$R@UIADs@@@@QEAA@XZ; R<IADs>::~R<IADs>(void)
0x180009934  test    ebx, ebx
0x180009936  js      short loc_18000995F
0x180009938  mov     rax, [rdi+20h]
0x18000993c  lea     r8, IID_IEnumConnections; struct _GUID *
0x180009943  mov     r9, r14; void **
0x180009946  mov     [rsi+20h], rax
0x18000994a  lea     rdx, ?_entries@?1??_GetEntries@?$CComEnum@UIEnumConnections@@$1?IID_IEnumConnections@@3U_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@VCComSingleThreadModel@6@@ATL@@SAPEBU_ATL_INTMAP_ENTRY@3@XZ@4QBU43@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180009951  mov     rcx, rsi; void *
0x180009954  call    ?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z; ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180009959  mov     ebx, eax
0x18000995b  test    eax, eax
0x18000995d  jns     short loc_18000996C
0x18000995f  test    rsi, rsi
0x180009962  jz      short loc_18000996C
0x180009964  mov     rcx, rsi; Block
0x180009967  call    ??_G?$CComObject@V?$CComEnum@UIEnumConnections@@$1?IID_IEnumConnections@@3U_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@VCComSingleThreadModel@6@@ATL@@@ATL@@QEAAPEAXI@Z; ATL::CComObject<ATL::CComEnum<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComSingleThreadModel>>::`scalar deleting destructor'(uint)
0x18000996c  mov     eax, ebx
0x18000996e  mov     rbx, [rsp+58h+arg_0]
0x180009973  add     rsp, 30h
0x180009977  pop     r15
0x180009979  pop     r14
0x18000997b  pop     rdi
0x18000997c  pop     rsi
0x18000997d  pop     rbp
0x18000997e  retn
```
