# GetNameValuePairsFromXML(ushort const *,IXMLDOMElement *,std::multimap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>> &)

- ea: `0x18002bac4`
- end: `0x18002bc41`
- name: `?GetNameValuePairsFromXML@@YAJPEBGPEAUIXMLDOMElement@@AEAV?$multimap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@@std@@@Z`
- size: `381`
- prototype: `__int64 __fastcall(const OLECHAR *, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002be68`

## callees

- `0x18000579c`
- `0x180006d58`
- `0x180008c84`
- `0x18002b61c`
- `0x18002b8bc`
- `0x18002b9d0`
- `0x18002bac4`
- `0x18002bd7c`
- `0x18002c4a4`
- `0x18002f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002bade`
- `OLEAUT32!__imp_SysAllocString` at `0x18002bade`
- `OLEAUT32!__imp_SysFreeString` at `0x18002bb0e`
- `OLEAUT32!__imp_SysFreeString` at `0x18002bb0e`

## pseudocode

```c
__int64 __fastcall GetNameValuePairsFromXML(const OLECHAR *a1, __int64 a2, __int64 a3)
{
  OLECHAR *v5; // rdi
  int ValueFromXML; // ebx
  int NextNode; // eax
  __int64 v8; // rax
  __int64 v10; // [rsp+20h] [rbp-48h] BYREF
  __int64 v11; // [rsp+28h] [rbp-40h] BYREF
  struct IXMLDOMNodeList *v12; // [rsp+30h] [rbp-38h] BYREF
  __int64 v13; // [rsp+38h] [rbp-30h] BYREF
  _BYTE v14[8]; // [rsp+40h] [rbp-28h] BYREF
  _BYTE v15[32]; // [rsp+48h] [rbp-20h] BYREF
  struct IXMLDOMNode *v16; // [rsp+A8h] [rbp+40h] BYREF

  v13 = 0;
  v5 = SysAllocString(a1);
  if ( v5 )
  {
    ValueFromXML = (*(__int64 (__fastcall **)(__int64, OLECHAR *, __int64 *))(*(_QWORD *)a2 + 296LL))(a2, v5, &v13);
    SysFreeString(v5);
    if ( ValueFromXML )
    {
      if ( ValueFromXML == 1 )
        ValueFromXML = 0;
    }
    else
    {
      v12 = 0;
      ValueFromXML = (*(__int64 (__fastcall **)(__int64, struct IXMLDOMNodeList **))(*(_QWORD *)v13 + 96LL))(v13, &v12);
      while ( ValueFromXML >= 0 )
      {
        v16 = 0;
        NextNode = _XmlUtilGetNextNode(v12, &v16);
        ValueFromXML = NextNode;
        if ( NextNode == 1 )
        {
          ValueFromXML = 0;
          ATL::CComPtrBase<INDFHelperClass>::~CComPtrBase<INDFHelperClass>((__int64 *)&v16);
          break;
        }
        if ( NextNode >= 0 )
        {
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v11);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v10);
          ValueFromXML = GetValueFromXML(v16, L"Name", &v11);
          if ( ValueFromXML >= 0 )
          {
            ValueFromXML = GetValueFromXML(v16, L"Value", &v10);
            if ( ValueFromXML >= 0 )
            {
              v8 = std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>(
                     v15,
                     &v11,
                     &v10);
              std::multimap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::insert<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>(
                a3,
                v14,
                v8);
              std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::~pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>(v15);
            }
          }
          ATL::CStringData::Release((ATL::CStringData *)(v10 - 24));
          ATL::CStringData::Release((ATL::CStringData *)(v11 - 24));
        }
        ATL::CComPtrBase<INDFHelperClass>::~CComPtrBase<INDFHelperClass>((__int64 *)&v16);
      }
      ATL::CComPtrBase<INDFHelperClass>::~CComPtrBase<INDFHelperClass>((__int64 *)&v12);
    }
  }
  else
  {
    ValueFromXML = -2147024882;
  }
  ATL::CComPtrBase<INDFHelperClass>::~CComPtrBase<INDFHelperClass>(&v13);
  return (unsigned int)ValueFromXML;
}

```

## disassembly

```asm
0x18002bac4  push    rbp
0x18002bac6  push    rbx
0x18002bac7  push    rsi
0x18002bac8  push    rdi
0x18002bac9  mov     rbp, rsp
0x18002bacc  sub     rsp, 68h
0x18002bad0  mov     rsi, r8
0x18002bad3  mov     rbx, rdx
0x18002bad6  mov     [rbp+var_30], 0
0x18002bade  call    cs:__imp_SysAllocString
0x18002bae4  mov     rdi, rax
0x18002bae7  test    rax, rax
0x18002baea  jz      loc_18002BC28
0x18002baf0  mov     rcx, [rbx]
0x18002baf3  mov     rax, [rcx+128h]
0x18002bafa  lea     r8, [rbp+var_30]
0x18002bafe  mov     rdx, rdi
0x18002bb01  mov     rcx, rbx
0x18002bb04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb09  mov     ebx, eax
0x18002bb0b  mov     rcx, rdi; bstrString
0x18002bb0e  call    cs:__imp_SysFreeString
0x18002bb14  test    ebx, ebx
0x18002bb16  jnz     loc_18002BC1F
0x18002bb1c  mov     [rbp+var_38], 0
0x18002bb24  mov     rcx, [rbp+var_30]
0x18002bb28  mov     rax, [rcx]
0x18002bb2b  lea     rdx, [rbp+var_38]
0x18002bb2f  mov     rax, [rax+60h]
0x18002bb33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb38  mov     ebx, eax
0x18002bb3a  test    ebx, ebx
0x18002bb3c  js      loc_18002BC14
0x18002bb42  mov     [rbp+arg_18], 0
0x18002bb4a  lea     rdx, [rbp+arg_18]; struct IXMLDOMNode **
0x18002bb4e  mov     rcx, [rbp+var_38]; struct IXMLDOMNodeList *
0x18002bb52  call    ?_XmlUtilGetNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; _XmlUtilGetNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x18002bb57  mov     ebx, eax
0x18002bb59  cmp     eax, 1
0x18002bb5c  jz      loc_18002BC08
0x18002bb62  test    eax, eax
0x18002bb64  js      loc_18002BBFA
0x18002bb6a  lea     rcx, [rbp+var_40]
0x18002bb6e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18002bb73  nop
0x18002bb74  lea     rcx, [rbp+var_48]
0x18002bb78  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18002bb7d  nop
0x18002bb7e  lea     r8, [rbp+var_40]
0x18002bb82  lea     rdx, aName; "Name"
0x18002bb89  mov     rcx, [rbp+arg_18]
0x18002bb8d  call    ?GetValueFromXML@@YAJPEAUIXMLDOMNode@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; GetValueFromXML(IXMLDOMNode *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18002bb92  mov     ebx, eax
0x18002bb94  test    eax, eax
0x18002bb96  js      short loc_18002BBDE
0x18002bb98  lea     r8, [rbp+var_48]
0x18002bb9c  lea     rdx, aValue; "Value"
0x18002bba3  mov     rcx, [rbp+arg_18]
0x18002bba7  call    ?GetValueFromXML@@YAJPEAUIXMLDOMNode@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; GetValueFromXML(IXMLDOMNode *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18002bbac  mov     ebx, eax
0x18002bbae  test    eax, eax
0x18002bbb0  js      short loc_18002BBDE
0x18002bbb2  lea     r8, [rbp+var_48]
0x18002bbb6  lea     rdx, [rbp+var_40]
0x18002bbba  lea     rcx, [rbp+var_20]
0x18002bbbe  call    ??$?0AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV01@@?$pair@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@QEAA@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAPEAX@Z; std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,void * *)
0x18002bbc3  nop
0x18002bbc4  mov     r8, rax
0x18002bbc7  lea     rdx, [rbp+var_28]
0x18002bbcb  mov     rcx, rsi
0x18002bbce  call    ??$insert@U?$pair@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@?$multimap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@std@@@std@@@1@$$QEAU?$pair@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@1@@Z; std::multimap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::insert<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>(std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>> &&)
0x18002bbd3  nop
0x18002bbd4  lea     rcx, [rbp+var_20]
0x18002bbd8  call    ??1?$pair@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@QEAA@XZ; std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::~pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>(void)
0x18002bbdd  nop
0x18002bbde  mov     rcx, [rbp+var_48]
0x18002bbe2  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002bbe6  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002bbeb  nop
0x18002bbec  mov     rcx, [rbp+var_40]
0x18002bbf0  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002bbf4  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002bbf9  nop
0x18002bbfa  lea     rcx, [rbp+arg_18]
0x18002bbfe  call    ??1?$CComPtrBase@UINDFHelperClass@@@ATL@@QEAA@XZ; ATL::CComPtrBase<INDFHelperClass>::~CComPtrBase<INDFHelperClass>(void)
0x18002bc03  jmp     loc_18002BB3A
0x18002bc08  xor     ebx, ebx
0x18002bc0a  lea     rcx, [rbp+arg_18]
0x18002bc0e  call    ??1?$CComPtrBase@UINDFHelperClass@@@ATL@@QEAA@XZ; ATL::CComPtrBase<INDFHelperClass>::~CComPtrBase<INDFHelperClass>(void)
0x18002bc13  nop
0x18002bc14  lea     rcx, [rbp+var_38]
0x18002bc18  call    ??1?$CComPtrBase@UINDFHelperClass@@@ATL@@QEAA@XZ; ATL::CComPtrBase<INDFHelperClass>::~CComPtrBase<INDFHelperClass>(void)
0x18002bc1d  jmp     short loc_18002BC2D
0x18002bc1f  cmp     ebx, 1
0x18002bc22  jnz     short loc_18002BC2D
0x18002bc24  xor     ebx, ebx
0x18002bc26  jmp     short loc_18002BC2D
0x18002bc28  mov     ebx, 8007000Eh
0x18002bc2d  lea     rcx, [rbp+var_30]
0x18002bc31  call    ??1?$CComPtrBase@UINDFHelperClass@@@ATL@@QEAA@XZ; ATL::CComPtrBase<INDFHelperClass>::~CComPtrBase<INDFHelperClass>(void)
0x18002bc36  mov     eax, ebx
0x18002bc38  add     rsp, 68h
0x18002bc3c  pop     rdi
0x18002bc3d  pop     rsi
0x18002bc3e  pop     rbx
0x18002bc3f  pop     rbp
0x18002bc40  retn
```
