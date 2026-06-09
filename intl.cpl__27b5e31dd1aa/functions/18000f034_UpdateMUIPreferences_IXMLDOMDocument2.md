# UpdateMUIPreferences(IXMLDOMDocument2 *)

- ea: `0x18000f034`
- end: `0x18000f32a`
- name: `?UpdateMUIPreferences@@YAJPEAUIXMLDOMDocument2@@@Z`
- size: `758`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x18000dce0`

## callees

- `0x18000aa10`
- `0x18000aa9c`
- `0x18000accc`
- `0x18000b8c8`
- `0x18000ce98`
- `0x18000d020`
- `0x18000da60`
- `0x18000f034`
- `0x18000f464`
- `0x18002b010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000f208`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f317`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f208`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f317`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall UpdateMUIPreferences(struct IXMLDOMDocument2 *a1)
{
  OLECHAR *v2; // rdi
  unsigned int Attribute; // ebx
  HRESULT (__stdcall *selectSingleNode)(IXMLDOMDocument2 *, BSTR, IXMLDOMNode **); // r14
  _bstr_t *v5; // rbx
  _bstr_t *v6; // rax
  _QWORD *v7; // rdx
  HRESULT (__stdcall *v8)(IXMLDOMNode *, BSTR, IXMLDOMNode **); // rsi
  _bstr_t *v9; // rbx
  _bstr_t *v10; // rax
  _QWORD *v11; // rdx
  unsigned __int16 ***v12; // rax
  unsigned __int16 *v13; // rdx
  HRESULT (__stdcall *v14)(IXMLDOMNode *, BSTR, IXMLDOMNode **); // rsi
  _bstr_t *v15; // rbx
  _bstr_t *v16; // rax
  _QWORD *v17; // rdx
  unsigned __int16 ***v18; // rax
  unsigned __int16 *v19; // rdx
  _BYTE v21[8]; // [rsp+20h] [rbp-10h] BYREF
  _BYTE v22[8]; // [rsp+28h] [rbp-8h] BYREF
  struct IXMLDOMNode *v23; // [rsp+60h] [rbp+30h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp+38h] BYREF
  struct IXMLDOMNode *v25; // [rsp+70h] [rbp+40h] BYREF
  char v26; // [rsp+78h] [rbp+48h] BYREF

  v25 = 0;
  v23 = 0;
  v2 = 0;
  bstrString = 0;
  if ( !a1 )
  {
    Attribute = -2147024809;
    goto LABEL_31;
  }
  selectSingleNode = a1->lpVtbl->selectSingleNode;
  v5 = _bstr_t::_bstr_t((_bstr_t *)v22, "//");
  v6 = _bstr_t::_bstr_t((_bstr_t *)v21, L"gs:MUILanguagePreferences");
  v7 = *(_QWORD **)_bstr_t::operator+(v5, &v26, v6);
  if ( v7 )
    v7 = (_QWORD *)*v7;
  Attribute = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, _QWORD *, struct IXMLDOMNode **))selectSingleNode)(
                a1,
                v7,
                &v25);
  _bstr_t::_Free((_bstr_t *)&v26);
  _bstr_t::_Free((_bstr_t *)v21);
  _bstr_t::_Free((_bstr_t *)v22);
  if ( Attribute == 1 )
  {
    Attribute = 0;
    goto LABEL_31;
  }
  if ( (unsigned int)CheckHR(Attribute) )
  {
    v8 = v25->lpVtbl->selectSingleNode;
    v9 = _bstr_t::_bstr_t((_bstr_t *)v21, "//");
    v10 = _bstr_t::_bstr_t((_bstr_t *)v22, L"gs:MUILanguage");
    v11 = *(_QWORD **)_bstr_t::operator+(v9, &v26, v10);
    if ( v11 )
      v11 = (_QWORD *)*v11;
    Attribute = ((__int64 (__fastcall *)(struct IXMLDOMNode *, _QWORD *, struct IXMLDOMNode **))v8)(v25, v11, &v23);
    _bstr_t::_Free((_bstr_t *)&v26);
    _bstr_t::_Free((_bstr_t *)v22);
    _bstr_t::_Free((_bstr_t *)v21);
    if ( (unsigned int)CheckHR(Attribute) )
    {
      v12 = (unsigned __int16 ***)_bstr_t::_bstr_t((_bstr_t *)&v26, VALUE_ATTR);
      if ( *v12 )
        v13 = **v12;
      else
        v13 = 0;
      Attribute = GetAttribute(v23, v13, &bstrString);
      _bstr_t::_Free((_bstr_t *)&v26);
      if ( !(unsigned int)CheckHR(Attribute) )
        goto LABEL_30;
      v2 = bstrString;
      if ( !(unsigned int)ChangeMUIPreferences(bstrString, 1) )
      {
        Attribute = 1;
        goto LABEL_31;
      }
      ReleaseDomNode(&v23);
      v23 = 0;
      if ( v2 )
      {
        SysFreeString(v2);
        v2 = 0;
        bstrString = 0;
      }
      v14 = v25->lpVtbl->selectSingleNode;
      v15 = _bstr_t::_bstr_t((_bstr_t *)v21, "//");
      v16 = _bstr_t::_bstr_t((_bstr_t *)v22, L"gs:MUIFallback");
      v17 = *(_QWORD **)_bstr_t::operator+(v15, &v26, v16);
      if ( v17 )
        v17 = (_QWORD *)*v17;
      Attribute = ((__int64 (__fastcall *)(struct IXMLDOMNode *, _QWORD *, struct IXMLDOMNode **))v14)(v25, v17, &v23);
      _bstr_t::_Free((_bstr_t *)&v26);
      _bstr_t::_Free((_bstr_t *)v22);
      _bstr_t::_Free((_bstr_t *)v21);
      if ( Attribute != 1 && (unsigned int)CheckHR(Attribute) )
      {
        v18 = (unsigned __int16 ***)_bstr_t::_bstr_t((_bstr_t *)&v26, VALUE_ATTR);
        if ( *v18 )
          v19 = **v18;
        else
          v19 = 0;
        Attribute = GetAttribute(v23, v19, &bstrString);
        _bstr_t::_Free((_bstr_t *)&v26);
        if ( (unsigned int)CheckHR(Attribute) )
        {
          v2 = bstrString;
          if ( !(unsigned int)ChangeMUIPreferences(bstrString, 0) )
            Attribute = 1;
          goto LABEL_31;
        }
LABEL_30:
        v2 = bstrString;
      }
    }
  }
LABEL_31:
  ReleaseDomNode(&v23);
  ReleaseDomNode(&v25);
  if ( v2 )
    SysFreeString(v2);
  return Attribute;
}

```

## disassembly

```asm
0x18000f034  push    rbp
0x18000f036  push    rbx
0x18000f037  push    rsi
0x18000f038  push    rdi
0x18000f039  push    r14
0x18000f03b  mov     rbp, rsp
0x18000f03e  sub     rsp, 30h
0x18000f042  mov     rsi, rcx
0x18000f045  mov     [rbp+arg_10], 0
0x18000f04d  mov     [rbp+arg_0], 0
0x18000f055  xor     edi, edi
0x18000f057  mov     [rbp+bstrString], rdi
0x18000f05b  test    rcx, rcx
0x18000f05e  jnz     short loc_18000F06A
0x18000f060  mov     ebx, 80070057h
0x18000f065  jmp     loc_18000F2FD
0x18000f06a  mov     rax, [rcx]
0x18000f06d  mov     r14, [rax+128h]
0x18000f074  lea     rdx, asc_180030760; "//"
0x18000f07b  lea     rcx, [rbp+var_8]; this
0x18000f07f  call    ??0_bstr_t@@QEAA@PEBD@Z; _bstr_t::_bstr_t(char const *)
0x18000f084  mov     rbx, rax
0x18000f087  lea     rdx, aGsMuilanguagep; "gs:MUILanguagePreferences"
0x18000f08e  lea     rcx, [rbp+var_10]; this
0x18000f092  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000f097  nop
0x18000f098  mov     r8, rax
0x18000f09b  lea     rdx, [rbp+arg_18]
0x18000f09f  mov     rcx, rbx
0x18000f0a2  call    ??H_bstr_t@@QEBA?AV0@AEBV0@@Z; _bstr_t::operator+(_bstr_t const &)
0x18000f0a7  nop
0x18000f0a8  mov     rdx, [rax]
0x18000f0ab  test    rdx, rdx
0x18000f0ae  jz      short loc_18000F0B3
0x18000f0b0  mov     rdx, [rdx]
0x18000f0b3  lea     r8, [rbp+arg_10]
0x18000f0b7  mov     rcx, rsi
0x18000f0ba  mov     rax, r14
0x18000f0bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0c2  mov     ebx, eax
0x18000f0c4  lea     rcx, [rbp+arg_18]; this
0x18000f0c8  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000f0cd  nop
0x18000f0ce  lea     rcx, [rbp+var_10]; this
0x18000f0d2  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000f0d7  nop
0x18000f0d8  lea     rcx, [rbp+var_8]; this
0x18000f0dc  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000f0e1  mov     r14d, 1
0x18000f0e7  cmp     ebx, r14d
0x18000f0ea  jnz     short loc_18000F0F3
0x18000f0ec  xor     ebx, ebx
0x18000f0ee  jmp     loc_18000F2FD
0x18000f0f3  mov     ecx, ebx; int
0x18000f0f5  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000f0fa  test    eax, eax
0x18000f0fc  jz      loc_18000F2FD
0x18000f102  mov     rax, [rbp+arg_10]
0x18000f106  mov     rcx, [rax]
0x18000f109  mov     rsi, [rcx+128h]
0x18000f110  lea     rdx, asc_180030760; "//"
0x18000f117  lea     rcx, [rbp+var_10]; this
0x18000f11b  call    ??0_bstr_t@@QEAA@PEBD@Z; _bstr_t::_bstr_t(char const *)
0x18000f120  mov     rbx, rax
0x18000f123  lea     rdx, aGsMuilanguage; "gs:MUILanguage"
0x18000f12a  lea     rcx, [rbp+var_8]; this
0x18000f12e  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000f133  nop
0x18000f134  mov     r8, rax
0x18000f137  lea     rdx, [rbp+arg_18]
0x18000f13b  mov     rcx, rbx
0x18000f13e  call    ??H_bstr_t@@QEBA?AV0@AEBV0@@Z; _bstr_t::operator+(_bstr_t const &)
0x18000f143  nop
0x18000f144  mov     rdx, [rax]
0x18000f147  test    rdx, rdx
0x18000f14a  jz      short loc_18000F14F
0x18000f14c  mov     rdx, [rdx]
0x18000f14f  lea     r8, [rbp+arg_0]
0x18000f153  mov     rcx, [rbp+arg_10]
0x18000f157  mov     rax, rsi
0x18000f15a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f15f  mov     ebx, eax
0x18000f161  lea     rcx, [rbp+arg_18]; this
0x18000f165  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000f16a  nop
0x18000f16b  lea     rcx, [rbp+var_8]; this
0x18000f16f  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000f174  nop
0x18000f175  lea     rcx, [rbp+var_10]; this
0x18000f179  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000f17e  mov     ecx, ebx; int
0x18000f180  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000f185  test    eax, eax
0x18000f187  jz      loc_18000F2FD
0x18000f18d  lea     rdx, ?VALUE_ATTR@@3PAGA; "Value"
0x18000f194  lea     rcx, [rbp+arg_18]; this
0x18000f198  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000f19d  nop
0x18000f19e  mov     rcx, [rax]
0x18000f1a1  test    rcx, rcx
0x18000f1a4  jz      short loc_18000F1AB
0x18000f1a6  mov     rdx, [rcx]
0x18000f1a9  jmp     short loc_18000F1AD
0x18000f1ab  xor     edx, edx; unsigned __int16 *
0x18000f1ad  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x18000f1b1  mov     rcx, [rbp+arg_0]; struct IXMLDOMNode *
0x18000f1b5  call    ?GetAttribute@@YAJPEAUIXMLDOMNode@@PEAGPEAPEAG@Z; GetAttribute(IXMLDOMNode *,ushort *,ushort * *)
0x18000f1ba  mov     ebx, eax
0x18000f1bc  lea     rcx, [rbp+arg_18]; this
0x18000f1c0  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000f1c5  mov     ecx, ebx; int
0x18000f1c7  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000f1cc  test    eax, eax
0x18000f1ce  jz      loc_18000F2F9
0x18000f1d4  mov     edx, r14d; int
0x18000f1d7  mov     rdi, [rbp+bstrString]
0x18000f1db  mov     rcx, rdi; unsigned __int16 *
0x18000f1de  call    ?ChangeMUIPreferences@@YAHPEAGH@Z; ChangeMUIPreferences(ushort *,int)
0x18000f1e3  test    eax, eax
0x18000f1e5  jnz     short loc_18000F1EF
0x18000f1e7  mov     ebx, r14d
0x18000f1ea  jmp     loc_18000F2FD
0x18000f1ef  lea     rcx, [rbp+arg_0]; struct IXMLDOMNode **
0x18000f1f3  call    ?ReleaseDomNode@@YAXPEAPEAUIXMLDOMNode@@@Z; ReleaseDomNode(IXMLDOMNode * *)
0x18000f1f8  mov     [rbp+arg_0], 0
0x18000f200  test    rdi, rdi
0x18000f203  jz      short loc_18000F214
0x18000f205  mov     rcx, rdi; bstrString
0x18000f208  call    cs:__imp_SysFreeString
0x18000f20e  xor     edi, edi
0x18000f210  mov     [rbp+bstrString], rdi
0x18000f214  mov     rax, [rbp+arg_10]
0x18000f218  mov     rcx, [rax]
0x18000f21b  mov     rsi, [rcx+128h]
0x18000f222  lea     rdx, asc_180030760; "//"
0x18000f229  lea     rcx, [rbp+var_10]; this
0x18000f22d  call    ??0_bstr_t@@QEAA@PEBD@Z; _bstr_t::_bstr_t(char const *)
0x18000f232  mov     rbx, rax
0x18000f235  lea     rdx, aGsMuifallback; "gs:MUIFallback"
0x18000f23c  lea     rcx, [rbp+var_8]; this
0x18000f240  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000f245  nop
0x18000f246  mov     r8, rax
0x18000f249  lea     rdx, [rbp+arg_18]
0x18000f24d  mov     rcx, rbx
0x18000f250  call    ??H_bstr_t@@QEBA?AV0@AEBV0@@Z; _bstr_t::operator+(_bstr_t const &)
0x18000f255  nop
0x18000f256  mov     rdx, [rax]
0x18000f259  test    rdx, rdx
0x18000f25c  jz      short loc_18000F261
0x18000f25e  mov     rdx, [rdx]
0x18000f261  lea     r8, [rbp+arg_0]
0x18000f265  mov     rcx, [rbp+arg_10]
0x18000f269  mov     rax, rsi
0x18000f26c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f271  mov     ebx, eax
0x18000f273  lea     rcx, [rbp+arg_18]; this
0x18000f277  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000f27c  nop
0x18000f27d  lea     rcx, [rbp+var_8]; this
0x18000f281  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000f286  nop
0x18000f287  lea     rcx, [rbp+var_10]; this
0x18000f28b  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000f290  cmp     ebx, r14d
0x18000f293  jz      short loc_18000F2FD
0x18000f295  mov     ecx, ebx; int
0x18000f297  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000f29c  test    eax, eax
0x18000f29e  jz      short loc_18000F2FD
0x18000f2a0  lea     rdx, ?VALUE_ATTR@@3PAGA; "Value"
0x18000f2a7  lea     rcx, [rbp+arg_18]; this
0x18000f2ab  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000f2b0  nop
0x18000f2b1  mov     rcx, [rax]
0x18000f2b4  test    rcx, rcx
0x18000f2b7  jz      short loc_18000F2BE
0x18000f2b9  mov     rdx, [rcx]
0x18000f2bc  jmp     short loc_18000F2C0
0x18000f2be  xor     edx, edx; unsigned __int16 *
0x18000f2c0  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x18000f2c4  mov     rcx, [rbp+arg_0]; struct IXMLDOMNode *
0x18000f2c8  call    ?GetAttribute@@YAJPEAUIXMLDOMNode@@PEAGPEAPEAG@Z; GetAttribute(IXMLDOMNode *,ushort *,ushort * *)
0x18000f2cd  mov     ebx, eax
0x18000f2cf  lea     rcx, [rbp+arg_18]; this
0x18000f2d3  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000f2d8  mov     ecx, ebx; int
0x18000f2da  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000f2df  test    eax, eax
0x18000f2e1  jz      short loc_18000F2F9
0x18000f2e3  xor     edx, edx; int
0x18000f2e5  mov     rdi, [rbp+bstrString]
0x18000f2e9  mov     rcx, rdi; unsigned __int16 *
0x18000f2ec  call    ?ChangeMUIPreferences@@YAHPEAGH@Z; ChangeMUIPreferences(ushort *,int)
0x18000f2f1  test    eax, eax
0x18000f2f3  cmovz   ebx, r14d
0x18000f2f7  jmp     short loc_18000F2FD
0x18000f2f9  mov     rdi, [rbp+bstrString]
0x18000f2fd  lea     rcx, [rbp+arg_0]; struct IXMLDOMNode **
0x18000f301  call    ?ReleaseDomNode@@YAXPEAPEAUIXMLDOMNode@@@Z; ReleaseDomNode(IXMLDOMNode * *)
0x18000f306  lea     rcx, [rbp+arg_10]; struct IXMLDOMNode **
0x18000f30a  call    ?ReleaseDomNode@@YAXPEAPEAUIXMLDOMNode@@@Z; ReleaseDomNode(IXMLDOMNode * *)
0x18000f30f  test    rdi, rdi
0x18000f312  jz      short loc_18000F31D
0x18000f314  mov     rcx, rdi; bstrString
0x18000f317  call    cs:__imp_SysFreeString
0x18000f31d  mov     eax, ebx
0x18000f31f  add     rsp, 30h
0x18000f323  pop     r14
0x18000f325  pop     rdi
0x18000f326  pop     rsi
0x18000f327  pop     rbx
0x18000f328  pop     rbp
0x18000f329  retn
```
