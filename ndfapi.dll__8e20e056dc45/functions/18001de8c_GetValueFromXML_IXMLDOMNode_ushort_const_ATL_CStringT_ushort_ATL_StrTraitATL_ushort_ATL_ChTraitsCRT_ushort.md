# GetValueFromXML(IXMLDOMNode *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x18001de8c`
- end: `0x18001df7f`
- name: `?GetValueFromXML@@YAJPEAUIXMLDOMNode@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `243`
- prototype: `__int64 __fastcall(__int64, const OLECHAR *, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001d854`
- `0x18001df88`

## callees

- `0x18000eed8`
- `0x18000f350`
- `0x18001de8c`
- `0x180021010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001dea5`
- `OLEAUT32!__imp_SysAllocString` at `0x18001dea5`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ded6`
- `OLEAUT32!__imp_SysFreeString` at `0x18001df44`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ded6`
- `OLEAUT32!__imp_SysFreeString` at `0x18001df44`

## string_xrefs

- `0x18001df30`: `__CDATA_XML_CLOSE_SYMBOL__`

## pseudocode

```c
__int64 __fastcall GetValueFromXML(__int64 a1, const OLECHAR *a2, __int64 a3)
{
  OLECHAR *v5; // rdi
  int v6; // ebx
  __int64 v7; // r8
  _QWORD v9[7]; // [rsp+20h] [rbp-38h] BYREF
  BSTR bstrString; // [rsp+78h] [rbp+20h] BYREF

  v9[0] = 0;
  v5 = SysAllocString(a2);
  if ( v5 )
  {
    v6 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, _QWORD *))(*(_QWORD *)a1 + 296LL))(a1, v5, v9);
    SysFreeString(v5);
    if ( v6 )
    {
      if ( v6 == 1 )
        v6 = -2147024809;
    }
    else
    {
      bstrString = 0;
      v6 = (*(__int64 (__fastcall **)(_QWORD, BSTR *))(*(_QWORD *)v9[0] + 208LL))(v9[0], &bstrString);
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
  if ( v9[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v9[0] + 16LL))(v9[0]);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001de8c  push    rbx
0x18001de8e  push    rbp
0x18001de8f  push    rsi
0x18001de90  push    rdi
0x18001de91  sub     rsp, 38h
0x18001de95  mov     rsi, r8
0x18001de98  mov     rbx, rcx
0x18001de9b  xor     ebp, ebp
0x18001de9d  mov     [rsp+58h+var_38], rbp
0x18001dea2  mov     rcx, rdx; psz
0x18001dea5  call    cs:__imp_SysAllocString
0x18001deab  mov     rdi, rax
0x18001deae  test    rax, rax
0x18001deb1  jz      loc_18001DF58
0x18001deb7  mov     rdx, [rbx]
0x18001deba  mov     rax, [rdx+128h]
0x18001dec1  lea     r8, [rsp+58h+var_38]
0x18001dec6  mov     rdx, rdi
0x18001dec9  mov     rcx, rbx
0x18001decc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ded1  mov     ebx, eax
0x18001ded3  mov     rcx, rdi; bstrString
0x18001ded6  call    cs:__imp_SysFreeString
0x18001dedc  test    ebx, ebx
0x18001dede  jnz     short loc_18001DF4C
0x18001dee0  mov     [rsp+58h+bstrString], rbp
0x18001dee5  mov     rcx, [rsp+58h+var_38]
0x18001deea  mov     rax, [rcx]
0x18001deed  lea     rdx, [rsp+58h+bstrString]
0x18001def2  mov     rax, [rax+0D0h]
0x18001def9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001defe  mov     ebx, eax
0x18001df00  test    eax, eax
0x18001df02  js      short loc_18001DF5D
0x18001df04  mov     rdx, [rsp+58h+bstrString]
0x18001df09  test    rdx, rdx
0x18001df0c  jnz     short loc_18001DF13
0x18001df0e  mov     r8d, ebp
0x18001df11  jmp     short loc_18001DF21
0x18001df13  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001df17  inc     r8
0x18001df1a  cmp     [rdx+r8*2], bp
0x18001df1f  jnz     short loc_18001DF17
0x18001df21  mov     rcx, rsi
0x18001df24  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18001df29  lea     r8, asc_1800288A0; "]]>"
0x18001df30  lea     rdx, aCdataXmlCloseS; "__CDATA_XML_CLOSE_SYMBOL__"
0x18001df37  mov     rcx, rsi
0x18001df3a  call    ?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG0@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Replace(ushort const *,ushort const *)
0x18001df3f  mov     rcx, [rsp+58h+bstrString]; bstrString
0x18001df44  call    cs:__imp_SysFreeString
0x18001df4a  jmp     short loc_18001DF5D
0x18001df4c  cmp     ebx, 1
0x18001df4f  jnz     short loc_18001DF5D
0x18001df51  mov     ebx, 80070057h
0x18001df56  jmp     short loc_18001DF5D
0x18001df58  mov     ebx, 8007000Eh
0x18001df5d  mov     rcx, [rsp+58h+var_38]
0x18001df62  test    rcx, rcx
0x18001df65  jz      short loc_18001DF74
0x18001df67  mov     rax, [rcx]
0x18001df6a  mov     rax, [rax+10h]
0x18001df6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df73  nop
0x18001df74  mov     eax, ebx
0x18001df76  add     rsp, 38h
0x18001df7a  pop     rdi
0x18001df7b  pop     rsi
0x18001df7c  pop     rbp
0x18001df7d  pop     rbx
0x18001df7e  retn
```
