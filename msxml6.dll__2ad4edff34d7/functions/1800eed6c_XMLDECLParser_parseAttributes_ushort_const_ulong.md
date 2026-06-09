# XMLDECLParser::parseAttributes(ushort const *,ulong)

- ea: `0x1800eed6c`
- end: `0x1800eeec3`
- name: `?parseAttributes@XMLDECLParser@@QEAAPEAVVector@@PEBGK@Z`
- size: `343`
- prototype: `Vector *__fastcall(XMLDECLParser *this, const wchar_t *wszAttrs, int ulLen)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x1800dd6c0`

## callees

- `0x180009490`
- `0x18000d688`
- `0x18000d7d0`
- `0x180034244`
- `0x18004af40`
- `0x1800770d8`
- `0x180077138`
- `0x18007d930`
- `0x1800bc3b0`
- `0x1800eed6c`
- `0x180188010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800eee68`
- `OLEAUT32!__imp_SysFreeString` at `0x1800eee68`

## string_xrefs

- `0x1800eedcd`: `<?xml `

## pseudocode

```c
Vector *__fastcall XMLDECLParser::parseAttributes(XMLDECLParser *this, const wchar_t *wszAttrs, int ulLen)
{
  _reference<Vector> *p_attrs; // r14
  Vector *v7; // rbx
  HRESULT v8; // ebx
  XMLParser *p; // rcx
  String *v10; // rdi
  Exception *v11; // rbx
  wchar_t *bstr; // [rsp+40h] [rbp-28h] BYREF
  _reference<String> s; // [rsp+70h] [rbp+8h] BYREF
  _reference<Exception> e; // [rsp+88h] [rbp+20h] BYREF

  p_attrs = &this->_attrs;
  v7 = Vector::newVector(6u, (int)wszAttrs);
  release(&p_attrs->_p);
  p_attrs->_p = v7;
  v8 = AttributeParser::parse(this, L"<?xml ", 6, wszAttrs, ulLen, L"?><e/>", 6, 0x800u);
  if ( v8 < 0 )
  {
    bstr = 0;
    p = this->_xmlParser._p;
    if ( p && p->GetErrorInfo(p, &bstr) >= 0 )
    {
      s._p = 0;
      e._p = 0;
      v10 = String::newString(bstr);
      release(&s._p);
      s._p = v10;
      v11 = Exception::newException(v8, v8, v10, 0);
      release(&e._p);
      e._p = v11;
      SysFreeString(bstr);
      Exception::storeThis(v11);
      if ( v10 )
        assign(&s._p, 0);
      if ( v11 )
        assign(&e._p, 0);
      Exception::throwStored();
      __debugbreak();
    }
    Exception::throwHR(v8);
  }
  return p_attrs->_p;
}

```

## disassembly

```asm
0x1800eed6c  mov     [rsp+arg_8], rbx
0x1800eed71  mov     [rsp+arg_10], rsi
0x1800eed76  push    rdi
0x1800eed77  push    r14
0x1800eed79  push    r15
0x1800eed7b  sub     rsp, 50h
0x1800eed7f  mov     edi, ulLen
0x1800eed82  mov     rsi, wszAttrs
0x1800eed85  mov     r15, this
0x1800eed88  lea     r14, [this+10h]
0x1800eed8c  mov     ecx, 6; initialCapacity
0x1800eed91  call    ?newVector@Vector@@SAPEAV1@HH@Z; Vector::newVector(int,int)
0x1800eed96  mov     rbx, rax
0x1800eed99  mov     this, r14; ppref
0x1800eed9c  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1800eeda1  mov     [r14], rbx
0x1800eeda4  mov     [rsp+68h+ulFlag], 800h; ulFlag
0x1800eedac  mov     [rsp+68h+cchsuffix], 6; cchsuffix
0x1800eedb4  lea     rax, aE; "?><e/>"
0x1800eedbb  mov     [rsp+68h+suffix], rax; suffix
0x1800eedc0  mov     [rsp+68h+cchattr], edi; cchattr
0x1800eedc4  mov     r9, rsi; attrs
0x1800eedc7  mov     ulLen, 6; cchprefix
0x1800eedcd  lea     wszAttrs, aXml_0; "<?xml "
0x1800eedd4  mov     this, r15; this
0x1800eedd7  call    ?parse@AttributeParser@@IEAAJPEBGH0H0HK@Z; AttributeParser::parse(ushort const *,int,ushort const *,int,ushort const *,int,ulong)
0x1800eeddc  mov     ebx, eax
0x1800eedde  xor     esi, esi
0x1800eede0  test    eax, eax
0x1800eede2  jns     loc_1800EEEAA
0x1800eede8  mov     [rsp+68h+bstr], rsi
0x1800eeded  mov     this, [r15+8]
0x1800eedf1  test    this, this
0x1800eedf4  jz      loc_1800EEEA2
0x1800eedfa  mov     rax, [this]
0x1800eedfd  lea     wszAttrs, [rsp+68h+bstr]
0x1800eee02  mov     rax, [rax+58h]
0x1800eee06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eee0b  test    eax, eax
0x1800eee0d  js      loc_1800EEEA2
0x1800eee13  mov     [rsp+68h+s._p], rsi
0x1800eee18  mov     [rsp+68h+e._p], rsi
0x1800eee20  mov     this, [rsp+68h+bstr]; c
0x1800eee25  call    ?newString@String@@SAPEAV1@PEBG@Z; String::newString(ushort const *)
0x1800eee2a  mov     rdi, rax
0x1800eee2d  lea     this, [rsp+68h+s]; ppref
0x1800eee32  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1800eee37  mov     [rsp+68h+s._p], rdi
0x1800eee3c  xor     r9d, r9d; p
0x1800eee3f  mov     r8, rdi; s
0x1800eee42  mov     edx, ebx; resid
0x1800eee44  mov     ecx, ebx; hresult
0x1800eee46  call    ?newException@Exception@@SAPEAV1@JJPEAVString@@PEAV?$_array@V?$_reference@VString@@@@@@@Z; Exception::newException(long,long,String *,_array<_reference<String>> *)
0x1800eee4b  mov     rbx, rax
0x1800eee4e  lea     this, [rsp+68h+e]; ppref
0x1800eee56  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1800eee5b  mov     [rsp+68h+e._p], rbx
0x1800eee63  mov     this, [rsp+68h+bstr]; bstrString
0x1800eee68  call    cs:__imp_SysFreeString
0x1800eee6e  mov     this, rbx; this
0x1800eee71  call    ?storeThis@Exception@@QEAAXXZ; Exception::storeThis(void)
0x1800eee76  nop
0x1800eee77  test    rdi, rdi
0x1800eee7a  jz      short loc_1800EEE88
0x1800eee7c  xor     edx, edx; pref
0x1800eee7e  lea     this, [rsp+68h+s]; ppref
0x1800eee83  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800eee88  test    rbx, rbx
0x1800eee8b  jz      short loc_1800EEE9C
0x1800eee8d  xor     edx, edx; pref
0x1800eee8f  lea     this, [rsp+68h+e]; ppref
0x1800eee97  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800eee9c  call    ?throwStored@Exception@@SAXXZ; Exception::throwStored(void)
0x1800eeea1  int     3; Trap to Debugger
0x1800eeea2  mov     ecx, ebx; hr
0x1800eeea4  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x1800eeeaa  mov     rax, [r14]
0x1800eeead  lea     r11, [rsp+68h+var_18]
0x1800eeeb2  mov     rbx, [r11+28h]
0x1800eeeb6  mov     rsi, [r11+30h]
0x1800eeeba  mov     rsp, r11
0x1800eeebd  pop     r15
0x1800eeebf  pop     r14
0x1800eeec1  pop     rdi
0x1800eeec2  retn
0x18017f239  push    rbp
0x18017f23b  sub     rsp, 40h
0x18017f23f  mov     rbp, rdx
0x18017f242  cmp     qword ptr [rbp+70h], 0
0x18017f247  jz      short loc_18017F255
0x18017f249  xor     edx, edx; pref
0x18017f24b  lea     rcx, [rbp+70h]; ppref
0x18017f24f  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x18017f254  nop
0x18017f255  cmp     qword ptr [rbp+88h], 0
0x18017f25d  jz      short loc_18017F26E
0x18017f25f  xor     edx, edx; pref
0x18017f261  lea     rcx, [rbp+88h]; ppref
0x18017f268  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x18017f26d  nop
0x18017f26e  add     rsp, 40h
0x18017f272  pop     rbp
0x18017f273  retn
```
