# GetValueFromXML(IXMLDOMNode *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x18002bd7c`
- end: `0x18002be62`
- name: `?GetValueFromXML@@YAJPEAUIXMLDOMNode@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `230`
- prototype: `__int64 __fastcall(__int64, const OLECHAR *, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002bac4`
- `0x18002be68`

## callees

- `0x180006f04`
- `0x180008c84`
- `0x18002bd7c`
- `0x18002c0c0`
- `0x18002f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002bd95`
- `OLEAUT32!__imp_SysAllocString` at `0x18002bd95`
- `OLEAUT32!__imp_SysFreeString` at `0x18002bdc6`
- `OLEAUT32!__imp_SysFreeString` at `0x18002be34`
- `OLEAUT32!__imp_SysFreeString` at `0x18002bdc6`
- `OLEAUT32!__imp_SysFreeString` at `0x18002be34`

## string_xrefs

- `0x18002be20`: `__CDATA_XML_CLOSE_SYMBOL__`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetValueFromXML(__int64 a1, const OLECHAR *a2, __int64 a3)
{
  OLECHAR *v5; // rdi
  int v6; // ebx
  __int64 v7; // r8
  __int64 v9[7]; // [rsp+20h] [rbp-38h] BYREF
  BSTR bstrString; // [rsp+78h] [rbp+20h] BYREF

  v9[0] = 0;
  v5 = SysAllocString(a2);
  if ( v5 )
  {
    v6 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, __int64 *))(*(_QWORD *)a1 + 296LL))(a1, v5, v9);
    SysFreeString(v5);
    if ( v6 )
    {
      if ( v6 == 1 )
        v6 = -2147024809;
    }
    else
    {
      bstrString = 0;
      v6 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v9[0] + 208LL))(v9[0], &bstrString);
      if ( v6 >= 0 )
      {
        if ( bstrString )
        {
          v7 = -1;
          do
            ++v7;
          while ( bstrString[v7] );
        }
        else
        {
          v7 = 0;
        }
        ATL::CSimpleStringT<unsigned short,0>::SetString(a3, bstrString, v7);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Replace(
          a3,
          L"__CDATA_XML_CLOSE_SYMBOL__",
          L"]]>");
        SysFreeString(bstrString);
      }
    }
  }
  else
  {
    v6 = -2147024882;
  }
  ATL::CComPtrBase<INDFHelperClass>::~CComPtrBase<INDFHelperClass>(v9);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002bd7c  push    rbx
0x18002bd7e  push    rbp
0x18002bd7f  push    rsi
0x18002bd80  push    rdi
0x18002bd81  sub     rsp, 38h
0x18002bd85  mov     rsi, r8
0x18002bd88  mov     rbx, rcx
0x18002bd8b  xor     ebp, ebp
0x18002bd8d  mov     [rsp+58h+var_38], rbp
0x18002bd92  mov     rcx, rdx; psz
0x18002bd95  call    cs:__imp_SysAllocString
0x18002bd9b  mov     rdi, rax
0x18002bd9e  test    rax, rax
0x18002bda1  jz      loc_18002BE48
0x18002bda7  mov     rdx, [rbx]
0x18002bdaa  mov     rax, [rdx+128h]
0x18002bdb1  lea     r8, [rsp+58h+var_38]
0x18002bdb6  mov     rdx, rdi
0x18002bdb9  mov     rcx, rbx
0x18002bdbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bdc1  mov     ebx, eax
0x18002bdc3  mov     rcx, rdi; bstrString
0x18002bdc6  call    cs:__imp_SysFreeString
0x18002bdcc  test    ebx, ebx
0x18002bdce  jnz     short loc_18002BE3C
0x18002bdd0  mov     [rsp+58h+bstrString], rbp
0x18002bdd5  mov     rcx, [rsp+58h+var_38]
0x18002bdda  mov     rax, [rcx]
0x18002bddd  lea     rdx, [rsp+58h+bstrString]
0x18002bde2  mov     rax, [rax+0D0h]
0x18002bde9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bdee  mov     ebx, eax
0x18002bdf0  test    eax, eax
0x18002bdf2  js      short loc_18002BE4D
0x18002bdf4  mov     rdx, [rsp+58h+bstrString]
0x18002bdf9  test    rdx, rdx
0x18002bdfc  jnz     short loc_18002BE03
0x18002bdfe  mov     r8d, ebp
0x18002be01  jmp     short loc_18002BE11
0x18002be03  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002be07  inc     r8
0x18002be0a  cmp     [rdx+r8*2], bp
0x18002be0f  jnz     short loc_18002BE07
0x18002be11  mov     rcx, rsi
0x18002be14  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18002be19  lea     r8, asc_180039418; "]]>"
0x18002be20  lea     rdx, aCdataXmlCloseS; "__CDATA_XML_CLOSE_SYMBOL__"
0x18002be27  mov     rcx, rsi
0x18002be2a  call    ?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG0@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Replace(ushort const *,ushort const *)
0x18002be2f  mov     rcx, [rsp+58h+bstrString]; bstrString
0x18002be34  call    cs:__imp_SysFreeString
0x18002be3a  jmp     short loc_18002BE4D
0x18002be3c  cmp     ebx, 1
0x18002be3f  jnz     short loc_18002BE4D
0x18002be41  mov     ebx, 80070057h
0x18002be46  jmp     short loc_18002BE4D
0x18002be48  mov     ebx, 8007000Eh
0x18002be4d  lea     rcx, [rsp+58h+var_38]
0x18002be52  call    ??1?$CComPtrBase@UINDFHelperClass@@@ATL@@QEAA@XZ; ATL::CComPtrBase<INDFHelperClass>::~CComPtrBase<INDFHelperClass>(void)
0x18002be57  mov     eax, ebx
0x18002be59  add     rsp, 38h
0x18002be5d  pop     rdi
0x18002be5e  pop     rsi
0x18002be5f  pop     rbp
0x18002be60  pop     rbx
0x18002be61  retn
```
