# XMLDECLParser::parseAttributes(ushort const *,ulong)

- ea: `0x100a5923`
- end: `0x100a5a35`
- name: `?parseAttributes@XMLDECLParser@@QAEPAVVector@@PBGK@Z`
- size: `274`
- prototype: `Vector *__thiscall(XMLDECLParser *this, const wchar_t *wszAttrs, unsigned int ulLen)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x1008c682`

## callees

- `0x1003fba3`
- `0x10040be6`
- `0x10040c44`
- `0x1005719a`
- `0x10064cf1`
- `0x10064e1d`
- `0x10064eb7`
- `0x10064fc6`
- `0x10067bc0`
- `0x1006c080`
- `0x100a5800`
- `0x100a5923`

## import_xrefs

- `OLEAUT32!__imp__SysFreeString@4` at `0x100a59d9`
- `OLEAUT32!__imp__SysFreeString@4` at `0x100a59d9`

## string_xrefs

- `0x100a595e`: `<?xml `

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
0x100a5923  push    14h
0x100a5925  push    offset stru_10176508
0x100a592a  call    __SEH_prolog4
0x100a592f  mov     ebx, this
0x100a5931  mov     [ebp+e._p], ebx
0x100a5934  lea     edi, [ebx+8]
0x100a5937  push    6
0x100a5939  pop     this; initialCapacity
0x100a593a  call    ?newVector@Vector@@SGPAV1@HH@Z; Vector::newVector(int,int)
0x100a593f  mov     esi, eax
0x100a5941  mov     this, edi; ppref
0x100a5943  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x100a5948  mov     [edi], esi
0x100a594a  push    800h; ulFlag
0x100a594f  push    6; cchsuffix
0x100a5951  push    offset aE; "?><e/>"
0x100a5956  push    [ebp+ulLen]; cchattr
0x100a5959  push    [ebp+wszAttrs]; attrs
0x100a595c  push    6; cchprefix
0x100a595e  push    offset aXml_0; "<?xml "
0x100a5963  mov     this, ebx; this
0x100a5965  call    ?parse@AttributeParser@@IAEJPBGH0H0HK@Z; AttributeParser::parse(ushort const *,int,ushort const *,int,ushort const *,int,ulong)
0x100a596a  mov     ebx, eax
0x100a596c  test    ebx, ebx
0x100a596e  jns     loc_100A5A21
0x100a5974  xor     edi, edi
0x100a5976  mov     [ebp+bstr], edi
0x100a5979  mov     this, [ebp+e._p]
0x100a597c  mov     this, [this+4]
0x100a597f  test    this, this
0x100a5981  jz      loc_100A5A1A
0x100a5987  mov     eax, [this]
0x100a5989  mov     esi, [eax+2Ch]
0x100a598c  lea     eax, [ebp+bstr]
0x100a598f  push    eax
0x100a5990  push    this
0x100a5991  mov     this, esi; this
0x100a5993  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100a5999  call    esi
0x100a599b  test    eax, eax
0x100a599d  js      short loc_100A5A1A
0x100a599f  mov     [ebp+s._p], edi
0x100a59a2  mov     [ebp+e._p], edi
0x100a59a5  mov     [ebp+ms_exc.registration.TryLevel], edi
0x100a59a8  mov     this, [ebp+bstr]; c
0x100a59ab  call    ?newString@String@@SGPAV1@PBG@Z; String::newString(ushort const *)
0x100a59b0  mov     edi, eax
0x100a59b2  lea     this, [ebp+s]; ppref
0x100a59b5  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x100a59ba  mov     [ebp+s._p], edi
0x100a59bd  push    0; p
0x100a59bf  push    edi; s
0x100a59c0  mov     edx, ebx; resid
0x100a59c2  mov     this, ebx; hresult
0x100a59c4  call    ?newException@Exception@@SGPAV1@JJPAVString@@PAV?$_array@V?$_reference@VString@@@@@@@Z; Exception::newException(long,long,String *,_array<_reference<String>> *)
0x100a59c9  mov     esi, eax
0x100a59cb  lea     this, [ebp+e]; ppref
0x100a59ce  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x100a59d3  mov     [ebp+e._p], esi
0x100a59d6  push    [ebp+bstr]; bstrString
0x100a59d9  call    ds:__imp__SysFreeString@4; SysFreeString(x)
0x100a59df  mov     this, esi; this
0x100a59e1  call    ?storeThis@Exception@@QAEXXZ; Exception::storeThis(void)
0x100a59e6  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x100a59ed  call    $LN18_45
0x100a59f2  call    ?throwStored@Exception@@SGXXZ; Exception::throwStored(void)
0x100a59f7  mov     edi, [ebp+s._p]
0x100a59fa  mov     esi, [ebp+e._p]
0x100a59fd  test    edi, edi
0x100a59ff  jz      short loc_100A5A0B
0x100a5a01  xor     edx, edx; pref
0x100a5a03  lea     this, [ebp+s]; ppref
0x100a5a06  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x100a5a0b  test    esi, esi
0x100a5a0d  jz      short $LN17_40
0x100a5a0f  xor     edx, edx; pref
0x100a5a11  lea     this, [ebp+e]; ppref
0x100a5a14  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x100a5a19  retn
0x100a5a1a  mov     this, ebx; hr
0x100a5a1c  call    ?throwHR@Exception@@SGXJ@Z; Exception::throwHR(long)
0x100a5a21  mov     eax, [edi]
0x100a5a23  mov     this, [ebp+ms_exc.registration.Next]
0x100a5a26  mov     large fs:0, this
0x100a5a2d  pop     this
0x100a5a2e  pop     edi
0x100a5a2f  pop     esi
0x100a5a30  pop     ebx
0x100a5a31  leave
0x100a5a32  retn    8
```
