# XMLDECLParser::parseAttributes(ushort const *,ulong)

- ea: `0x100a5a33`
- end: `0x100a5b45`
- name: `?parseAttributes@XMLDECLParser@@QAEPAVVector@@PBGK@Z`
- size: `274`
- prototype: `Vector *__thiscall(XMLDECLParser *this, const wchar_t *wszAttrs, unsigned int ulLen)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x1008c6c2`

## callees

- `0x1003fb13`
- `0x10040b56`
- `0x10040bb4`
- `0x1005710a`
- `0x10064c51`
- `0x10064d7d`
- `0x10064e17`
- `0x10064f26`
- `0x10067b20`
- `0x1006bff0`
- `0x100a5910`
- `0x100a5a33`

## import_xrefs

- `OLEAUT32!__imp__SysFreeString@4` at `0x100a5ae9`
- `OLEAUT32!__imp__SysFreeString@4` at `0x100a5ae9`

## string_xrefs

- `0x100a5a6e`: `<?xml `

## pseudocode

```c
Vector *__thiscall XMLDECLParser::parseAttributes(XMLDECLParser *this, const wchar_t *wszAttrs, unsigned int ulLen)
{
  _reference<Vector> *p_attrs; // edi
  struct Vector *v5; // esi
  HRESULT v6; // ebx
  unsigned int refs; // ecx
  String *p; // edi
  Exception *v9; // esi
  wchar_t *bstr; // [esp+10h] [ebp-24h] BYREF
  _reference<Exception> e; // [esp+14h] [ebp-20h] BYREF
  _reference<String> s; // [esp+18h] [ebp-1Ch] BYREF
  CPPEH_RECORD ms_exc; // [esp+1Ch] [ebp-18h]

  e._p = (Exception *)this;
  p_attrs = &this->_attrs;
  v5 = Vector::newVector();
  release(&p_attrs->_p);
  p_attrs->_p = v5;
  v6 = AttributeParser::parse(this, L"<?xml ", 6, wszAttrs, ulLen, L"?><e/>", 6, 0x800u);
  if ( v6 < 0 )
  {
    p_attrs = 0;
    bstr = 0;
    refs = e._p->_refs;
    if ( refs
      && (*(int (__thiscall **)(_DWORD, unsigned int, wchar_t **))(*(_DWORD *)refs + 44))(
           *(_DWORD *)(*(_DWORD *)refs + 44),
           refs,
           &bstr) >= 0 )
    {
      s._p = 0;
      e._p = 0;
      ms_exc.registration.TryLevel = 0;
      p = String::newString(bstr);
      release(&s._p);
      s._p = p;
      v9 = Exception::newException(v6, v6, p, 0);
      release(&e._p);
      e._p = v9;
      SysFreeString(bstr);
      Exception::storeThis(v9);
      ms_exc.registration.TryLevel = -2;
      while ( 1 )
      {
        if ( p )
          assign(&s._p, 0);
        if ( v9 )
          assign(&e._p, 0);
        Exception::throwStored();
        p = s._p;
        v9 = e._p;
      }
    }
    Exception::throwHR(v6);
  }
  return p_attrs->_p;
}

```

## disassembly

```asm
0x100a5a33  push    14h
0x100a5a35  push    offset stru_101765F8
0x100a5a3a  call    __SEH_prolog4
0x100a5a3f  mov     ebx, this
0x100a5a41  mov     [ebp+e._p], ebx
0x100a5a44  lea     edi, [ebx+8]
0x100a5a47  push    6
0x100a5a49  pop     this; initialCapacity
0x100a5a4a  call    ?newVector@Vector@@SGPAV1@HH@Z; Vector::newVector(int,int)
0x100a5a4f  mov     esi, eax
0x100a5a51  mov     this, edi; ppref
0x100a5a53  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x100a5a58  mov     [edi], esi
0x100a5a5a  push    800h; ulFlag
0x100a5a5f  push    6; cchsuffix
0x100a5a61  push    offset aE; "?><e/>"
0x100a5a66  push    [ebp+ulLen]; cchattr
0x100a5a69  push    [ebp+wszAttrs]; attrs
0x100a5a6c  push    6; cchprefix
0x100a5a6e  push    offset aXml_0; "<?xml "
0x100a5a73  mov     this, ebx; this
0x100a5a75  call    ?parse@AttributeParser@@IAEJPBGH0H0HK@Z; AttributeParser::parse(ushort const *,int,ushort const *,int,ushort const *,int,ulong)
0x100a5a7a  mov     ebx, eax
0x100a5a7c  test    ebx, ebx
0x100a5a7e  jns     loc_100A5B31
0x100a5a84  xor     edi, edi
0x100a5a86  mov     [ebp+bstr], edi
0x100a5a89  mov     this, [ebp+e._p]
0x100a5a8c  mov     this, [this+4]
0x100a5a8f  test    this, this
0x100a5a91  jz      loc_100A5B2A
0x100a5a97  mov     eax, [this]
0x100a5a99  mov     esi, [eax+2Ch]
0x100a5a9c  lea     eax, [ebp+bstr]
0x100a5a9f  push    eax
0x100a5aa0  push    this
0x100a5aa1  mov     this, esi; this
0x100a5aa3  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100a5aa9  call    esi
0x100a5aab  test    eax, eax
0x100a5aad  js      short loc_100A5B2A
0x100a5aaf  mov     [ebp+s._p], edi
0x100a5ab2  mov     [ebp+e._p], edi
0x100a5ab5  mov     [ebp+ms_exc.registration.TryLevel], edi
0x100a5ab8  mov     this, [ebp+bstr]; c
0x100a5abb  call    ?newString@String@@SGPAV1@PBG@Z; String::newString(ushort const *)
0x100a5ac0  mov     edi, eax
0x100a5ac2  lea     this, [ebp+s]; ppref
0x100a5ac5  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x100a5aca  mov     [ebp+s._p], edi
0x100a5acd  push    0; p
0x100a5acf  push    edi; s
0x100a5ad0  mov     edx, ebx; resid
0x100a5ad2  mov     this, ebx; hresult
0x100a5ad4  call    ?newException@Exception@@SGPAV1@JJPAVString@@PAV?$_array@V?$_reference@VString@@@@@@@Z; Exception::newException(long,long,String *,_array<_reference<String>> *)
0x100a5ad9  mov     esi, eax
0x100a5adb  lea     this, [ebp+e]; ppref
0x100a5ade  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x100a5ae3  mov     [ebp+e._p], esi
0x100a5ae6  push    [ebp+bstr]; bstrString
0x100a5ae9  call    ds:__imp__SysFreeString@4; SysFreeString(x)
0x100a5aef  mov     this, esi; this
0x100a5af1  call    ?storeThis@Exception@@QAEXXZ; Exception::storeThis(void)
0x100a5af6  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x100a5afd  call    $LN18_45
0x100a5b02  call    ?throwStored@Exception@@SGXXZ; Exception::throwStored(void)
0x100a5b07  mov     edi, [ebp+s._p]
0x100a5b0a  mov     esi, [ebp+e._p]
0x100a5b0d  test    edi, edi
0x100a5b0f  jz      short loc_100A5B1B
0x100a5b11  xor     edx, edx; pref
0x100a5b13  lea     this, [ebp+s]; ppref
0x100a5b16  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x100a5b1b  test    esi, esi
0x100a5b1d  jz      short $LN17_40
0x100a5b1f  xor     edx, edx; pref
0x100a5b21  lea     this, [ebp+e]; ppref
0x100a5b24  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x100a5b29  retn
0x100a5b2a  mov     this, ebx; hr
0x100a5b2c  call    ?throwHR@Exception@@SGXJ@Z; Exception::throwHR(long)
0x100a5b31  mov     eax, [edi]
0x100a5b33  mov     this, [ebp+ms_exc.registration.Next]
0x100a5b36  mov     large fs:0, this
0x100a5b3d  pop     this
0x100a5b3e  pop     edi
0x100a5b3f  pop     esi
0x100a5b40  pop     ebx
0x100a5b41  leave
0x100a5b42  retn    8
```
