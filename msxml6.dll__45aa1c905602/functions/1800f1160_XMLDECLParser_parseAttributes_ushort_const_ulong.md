# XMLDECLParser::parseAttributes(ushort const *,ulong)

- ea: `0x1800f1160`
- end: `0x1800f12be`
- name: `?parseAttributes@XMLDECLParser@@QEAAPEAVVector@@PEBGK@Z`
- size: `350`
- prototype: `Vector *__fastcall(XMLDECLParser *this, const wchar_t *wszAttrs, unsigned int ulLen)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x1800df6d4`

## callees

- `0x18000e120`
- `0x180015a80`
- `0x180019cd0`
- `0x180019e20`
- `0x18002ca20`
- `0x18007c900`
- `0x18008a388`
- `0x18009e8e8`
- `0x1800bda08`
- `0x1800f1160`
- `0x18018c010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800f125c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f125c`

## string_xrefs

- `0x1800f11c1`: `<?xml `

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
  v7 = Vector::newVector(6, (int)wszAttrs);
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
0x1800f1160  mov     [rsp+arg_8], rbx
0x1800f1165  mov     [rsp+arg_10], rsi
0x1800f116a  push    rdi
0x1800f116b  push    r14
0x1800f116d  push    r15
0x1800f116f  sub     rsp, 50h
0x1800f1173  mov     edi, ulLen
0x1800f1176  mov     rsi, wszAttrs
0x1800f1179  mov     r15, this
0x1800f117c  lea     r14, [this+10h]
0x1800f1180  mov     ecx, 6; initialCapacity
0x1800f1185  call    ?newVector@Vector@@SAPEAV1@HH@Z; Vector::newVector(int,int)
0x1800f118a  mov     rbx, rax
0x1800f118d  mov     this, r14; ppref
0x1800f1190  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1800f1195  mov     [r14], rbx
0x1800f1198  mov     [rsp+68h+ulFlag], 800h; ulFlag
0x1800f11a0  mov     [rsp+68h+cchsuffix], 6; cchsuffix
0x1800f11a8  lea     rax, aE; "?><e/>"
0x1800f11af  mov     [rsp+68h+suffix], rax; suffix
0x1800f11b4  mov     [rsp+68h+cchattr], edi; cchattr
0x1800f11b8  mov     r9, rsi; attrs
0x1800f11bb  mov     ulLen, 6; cchprefix
0x1800f11c1  lea     wszAttrs, aXml_0; "<?xml "
0x1800f11c8  mov     this, r15; this
0x1800f11cb  call    ?parse@AttributeParser@@IEAAJPEBGH0H0HK@Z; AttributeParser::parse(ushort const *,int,ushort const *,int,ushort const *,int,ulong)
0x1800f11d0  mov     ebx, eax
0x1800f11d2  xor     esi, esi
0x1800f11d4  test    eax, eax
0x1800f11d6  jns     loc_1800F12A4
0x1800f11dc  mov     [rsp+68h+bstr], rsi
0x1800f11e1  mov     this, [r15+8]
0x1800f11e5  test    this, this
0x1800f11e8  jz      loc_1800F129C
0x1800f11ee  mov     rax, [this]
0x1800f11f1  lea     wszAttrs, [rsp+68h+bstr]
0x1800f11f6  mov     rax, [rax+58h]
0x1800f11fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f11ff  test    eax, eax
0x1800f1201  js      loc_1800F129C
0x1800f1207  mov     [rsp+68h+s._p], rsi
0x1800f120c  mov     [rsp+68h+e._p], rsi
0x1800f1214  mov     this, [rsp+68h+bstr]; c
0x1800f1219  call    ?newString@String@@SAPEAV1@PEBG@Z; String::newString(ushort const *)
0x1800f121e  mov     rdi, rax
0x1800f1221  lea     this, [rsp+68h+s]; ppref
0x1800f1226  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1800f122b  mov     [rsp+68h+s._p], rdi
0x1800f1230  xor     r9d, r9d; p
0x1800f1233  mov     r8, rdi; s
0x1800f1236  mov     edx, ebx; resid
0x1800f1238  mov     ecx, ebx; hresult
0x1800f123a  call    ?newException@Exception@@SAPEAV1@JJPEAVString@@PEAV?$_array@V?$_reference@VString@@@@@@@Z; Exception::newException(long,long,String *,_array<_reference<String>> *)
0x1800f123f  mov     rbx, rax
0x1800f1242  lea     this, [rsp+68h+e]; ppref
0x1800f124a  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1800f124f  mov     [rsp+68h+e._p], rbx
0x1800f1257  mov     this, [rsp+68h+bstr]; bstrString
0x1800f125c  call    cs:__imp_SysFreeString
0x1800f1263  nop     dword ptr [rax+rax+00h]
0x1800f1268  mov     this, rbx; this
0x1800f126b  call    ?storeThis@Exception@@QEAAXXZ; Exception::storeThis(void)
0x1800f1270  nop
0x1800f1271  test    rdi, rdi
0x1800f1274  jz      short loc_1800F1282
0x1800f1276  xor     edx, edx; pref
0x1800f1278  lea     this, [rsp+68h+s]; ppref
0x1800f127d  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800f1282  test    rbx, rbx
0x1800f1285  jz      short loc_1800F1296
0x1800f1287  xor     edx, edx; pref
0x1800f1289  lea     this, [rsp+68h+e]; ppref
0x1800f1291  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800f1296  call    ?throwStored@Exception@@SAXXZ; Exception::throwStored(void)
0x1800f129b  int     3; Trap to Debugger
0x1800f129c  mov     ecx, ebx; hr
0x1800f129e  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x1800f12a4  mov     rax, [r14]
0x1800f12a7  lea     r11, [rsp+68h+var_18]
0x1800f12ac  mov     rbx, [r11+28h]
0x1800f12b0  mov     rsi, [r11+30h]
0x1800f12b4  mov     rsp, r11
0x1800f12b7  pop     r15
0x1800f12b9  pop     r14
0x1800f12bb  pop     rdi
0x1800f12bc  retn
0x180182ef7  push    rbp
0x180182ef9  sub     rsp, 40h
0x180182efd  mov     rbp, rdx
0x180182f00  cmp     qword ptr [rbp+70h], 0
0x180182f05  jz      short loc_180182F13
0x180182f07  xor     edx, edx; pref
0x180182f09  lea     rcx, [rbp+70h]; ppref
0x180182f0d  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180182f12  nop
0x180182f13  cmp     qword ptr [rbp+88h], 0
0x180182f1b  jz      short loc_180182F2C
0x180182f1d  xor     edx, edx; pref
0x180182f1f  lea     rcx, [rbp+88h]; ppref
0x180182f26  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180182f2b  nop
0x180182f2c  add     rsp, 40h
0x180182f30  pop     rbp
0x180182f31  retn
```
