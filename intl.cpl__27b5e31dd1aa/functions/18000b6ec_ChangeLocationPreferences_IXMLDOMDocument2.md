# ChangeLocationPreferences(IXMLDOMDocument2 *)

- ea: `0x18000b6ec`
- end: `0x18000b8c0`
- name: `?ChangeLocationPreferences@@YAJPEAUIXMLDOMDocument2@@@Z`
- size: `468`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18000dce0`

## callees

- `0x18000aa10`
- `0x18000aa9c`
- `0x18000accc`
- `0x18000b6ec`
- `0x18000ce98`
- `0x18000d020`
- `0x18000da60`
- `0x18000f464`
- `0x18002b010`

## import_xrefs

- `msvcrt!_wtoi` at `0x18000b885`
- `msvcrt!_wtoi` at `0x18000b885`
- `api-ms-win-core-localization-l1-2-0!SetUserGeoID` at `0x18000b88d`
- `api-ms-win-core-localization-l1-2-0!SetUserGeoID` at `0x18000b88d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b8ad`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b8ad`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall ChangeLocationPreferences(struct IXMLDOMDocument2 *a1)
{
  wchar_t *v2; // rdi
  unsigned int Attribute; // ebx
  HRESULT (__stdcall *selectSingleNode)(IXMLDOMDocument2 *, BSTR, IXMLDOMNode **); // r14
  _bstr_t *v5; // rbx
  _bstr_t *v6; // rax
  _QWORD *v7; // rdx
  HRESULT (__stdcall *v8)(IXMLDOMNode *, BSTR, IXMLDOMNode **); // rsi
  _bstr_t *v9; // rbx
  _bstr_t *v10; // rax
  _QWORD *v11; // rdx
  _bstr_t *v12; // rax
  unsigned __int16 *v13; // rdx
  int v14; // eax
  GEOID v15; // eax
  _BYTE v17[8]; // [rsp+20h] [rbp-10h] BYREF
  _BYTE v18[8]; // [rsp+28h] [rbp-8h] BYREF
  struct IXMLDOMNode *v19; // [rsp+60h] [rbp+30h] BYREF
  wchar_t *String; // [rsp+68h] [rbp+38h] BYREF
  struct IXMLDOMNode *v21; // [rsp+70h] [rbp+40h] BYREF
  char v22; // [rsp+78h] [rbp+48h] BYREF

  v19 = 0;
  v21 = 0;
  v2 = 0;
  String = 0;
  if ( a1 )
  {
    selectSingleNode = a1->lpVtbl->selectSingleNode;
    v5 = _bstr_t::_bstr_t((_bstr_t *)v18, "//");
    v6 = _bstr_t::_bstr_t((_bstr_t *)v17, L"gs:LocationPreferences");
    v7 = *(_QWORD **)_bstr_t::operator+(v5, &v22, v6);
    if ( v7 )
      v7 = (_QWORD *)*v7;
    Attribute = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, _QWORD *, struct IXMLDOMNode **))selectSingleNode)(
                  a1,
                  v7,
                  &v19);
    _bstr_t::_Free((_bstr_t *)&v22);
    _bstr_t::_Free((_bstr_t *)v17);
    _bstr_t::_Free((_bstr_t *)v18);
    if ( Attribute == 1 )
    {
      Attribute = 0;
    }
    else if ( (unsigned int)CheckHR(Attribute) )
    {
      v8 = v19->lpVtbl->selectSingleNode;
      v9 = _bstr_t::_bstr_t((_bstr_t *)v17, "//");
      v10 = _bstr_t::_bstr_t((_bstr_t *)v18, L"gs:GeoID");
      v11 = *(_QWORD **)_bstr_t::operator+(v9, &v22, v10);
      if ( v11 )
        v11 = (_QWORD *)*v11;
      Attribute = ((__int64 (__fastcall *)(struct IXMLDOMNode *, _QWORD *, struct IXMLDOMNode **))v8)(v19, v11, &v21);
      _bstr_t::_Free((_bstr_t *)&v22);
      _bstr_t::_Free((_bstr_t *)v18);
      _bstr_t::_Free((_bstr_t *)v17);
      if ( (unsigned int)CheckHR(Attribute) )
      {
        v12 = _bstr_t::_bstr_t((_bstr_t *)&v22, VALUE_ATTR);
        v13 = *(_QWORD *)v12 ? **(unsigned __int16 ***)v12 : 0LL;
        Attribute = GetAttribute(v21, v13, &String);
        _bstr_t::_Free((_bstr_t *)&v22);
        v14 = CheckHR(Attribute);
        v2 = String;
        if ( v14 )
        {
          v15 = _wtoi(String);
          SetUserGeoID(v15);
        }
      }
    }
  }
  else
  {
    Attribute = -2147024809;
  }
  ReleaseDomNode(&v19);
  ReleaseDomNode(&v21);
  if ( v2 )
    SysFreeString(v2);
  return Attribute;
}

```

## disassembly

```asm
0x18000b6ec  push    rbp
0x18000b6ee  push    rbx
0x18000b6ef  push    rsi
0x18000b6f0  push    rdi
0x18000b6f1  push    r14
0x18000b6f3  mov     rbp, rsp
0x18000b6f6  sub     rsp, 30h
0x18000b6fa  mov     rsi, rcx
0x18000b6fd  mov     [rbp+arg_0], 0
0x18000b705  mov     [rbp+arg_10], 0
0x18000b70d  xor     edi, edi
0x18000b70f  mov     [rbp+String], rdi
0x18000b713  test    rcx, rcx
0x18000b716  jnz     short loc_18000B722
0x18000b718  mov     ebx, 80070057h
0x18000b71d  jmp     loc_18000B893
0x18000b722  mov     rax, [rcx]
0x18000b725  mov     r14, [rax+128h]
0x18000b72c  lea     rdx, asc_180030760; "//"
0x18000b733  lea     rcx, [rbp+var_8]; this
0x18000b737  call    ??0_bstr_t@@QEAA@PEBD@Z; _bstr_t::_bstr_t(char const *)
0x18000b73c  mov     rbx, rax
0x18000b73f  lea     rdx, aGsLocationpref; "gs:LocationPreferences"
0x18000b746  lea     rcx, [rbp+var_10]; this
0x18000b74a  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000b74f  nop
0x18000b750  mov     r8, rax
0x18000b753  lea     rdx, [rbp+arg_18]
0x18000b757  mov     rcx, rbx
0x18000b75a  call    ??H_bstr_t@@QEBA?AV0@AEBV0@@Z; _bstr_t::operator+(_bstr_t const &)
0x18000b75f  nop
0x18000b760  mov     rdx, [rax]
0x18000b763  test    rdx, rdx
0x18000b766  jz      short loc_18000B76B
0x18000b768  mov     rdx, [rdx]
0x18000b76b  lea     r8, [rbp+arg_0]
0x18000b76f  mov     rcx, rsi
0x18000b772  mov     rax, r14
0x18000b775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b77a  mov     ebx, eax
0x18000b77c  lea     rcx, [rbp+arg_18]; this
0x18000b780  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000b785  nop
0x18000b786  lea     rcx, [rbp+var_10]; this
0x18000b78a  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000b78f  nop
0x18000b790  lea     rcx, [rbp+var_8]; this
0x18000b794  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000b799  cmp     ebx, 1
0x18000b79c  jnz     short loc_18000B7A5
0x18000b79e  xor     ebx, ebx
0x18000b7a0  jmp     loc_18000B893
0x18000b7a5  mov     ecx, ebx; int
0x18000b7a7  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000b7ac  test    eax, eax
0x18000b7ae  jz      loc_18000B893
0x18000b7b4  mov     rax, [rbp+arg_0]
0x18000b7b8  mov     rcx, [rax]
0x18000b7bb  mov     rsi, [rcx+128h]
0x18000b7c2  lea     rdx, asc_180030760; "//"
0x18000b7c9  lea     rcx, [rbp+var_10]; this
0x18000b7cd  call    ??0_bstr_t@@QEAA@PEBD@Z; _bstr_t::_bstr_t(char const *)
0x18000b7d2  mov     rbx, rax
0x18000b7d5  lea     rdx, aGsGeoid; "gs:GeoID"
0x18000b7dc  lea     rcx, [rbp+var_8]; this
0x18000b7e0  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000b7e5  nop
0x18000b7e6  mov     r8, rax
0x18000b7e9  lea     rdx, [rbp+arg_18]
0x18000b7ed  mov     rcx, rbx
0x18000b7f0  call    ??H_bstr_t@@QEBA?AV0@AEBV0@@Z; _bstr_t::operator+(_bstr_t const &)
0x18000b7f5  nop
0x18000b7f6  mov     rdx, [rax]
0x18000b7f9  test    rdx, rdx
0x18000b7fc  jz      short loc_18000B801
0x18000b7fe  mov     rdx, [rdx]
0x18000b801  lea     r8, [rbp+arg_10]
0x18000b805  mov     rcx, [rbp+arg_0]
0x18000b809  mov     rax, rsi
0x18000b80c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b811  mov     ebx, eax
0x18000b813  lea     rcx, [rbp+arg_18]; this
0x18000b817  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000b81c  nop
0x18000b81d  lea     rcx, [rbp+var_8]; this
0x18000b821  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000b826  nop
0x18000b827  lea     rcx, [rbp+var_10]; this
0x18000b82b  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000b830  mov     ecx, ebx; int
0x18000b832  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000b837  test    eax, eax
0x18000b839  jz      short loc_18000B893
0x18000b83b  lea     rdx, ?VALUE_ATTR@@3PAGA; "Value"
0x18000b842  lea     rcx, [rbp+arg_18]; this
0x18000b846  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000b84b  nop
0x18000b84c  mov     rcx, [rax]
0x18000b84f  test    rcx, rcx
0x18000b852  jz      short loc_18000B859
0x18000b854  mov     rdx, [rcx]
0x18000b857  jmp     short loc_18000B85B
0x18000b859  xor     edx, edx; unsigned __int16 *
0x18000b85b  lea     r8, [rbp+String]; unsigned __int16 **
0x18000b85f  mov     rcx, [rbp+arg_10]; struct IXMLDOMNode *
0x18000b863  call    ?GetAttribute@@YAJPEAUIXMLDOMNode@@PEAGPEAPEAG@Z; GetAttribute(IXMLDOMNode *,ushort *,ushort * *)
0x18000b868  mov     ebx, eax
0x18000b86a  lea     rcx, [rbp+arg_18]; this
0x18000b86e  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000b873  mov     ecx, ebx; int
0x18000b875  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000b87a  mov     rdi, [rbp+String]
0x18000b87e  test    eax, eax
0x18000b880  jz      short loc_18000B893
0x18000b882  mov     rcx, rdi; String
0x18000b885  call    cs:__imp__wtoi
0x18000b88b  mov     ecx, eax; GeoId
0x18000b88d  call    cs:__imp_SetUserGeoID
0x18000b893  lea     rcx, [rbp+arg_0]; struct IXMLDOMNode **
0x18000b897  call    ?ReleaseDomNode@@YAXPEAPEAUIXMLDOMNode@@@Z; ReleaseDomNode(IXMLDOMNode * *)
0x18000b89c  lea     rcx, [rbp+arg_10]; struct IXMLDOMNode **
0x18000b8a0  call    ?ReleaseDomNode@@YAXPEAPEAUIXMLDOMNode@@@Z; ReleaseDomNode(IXMLDOMNode * *)
0x18000b8a5  test    rdi, rdi
0x18000b8a8  jz      short loc_18000B8B3
0x18000b8aa  mov     rcx, rdi; bstrString
0x18000b8ad  call    cs:__imp_SysFreeString
0x18000b8b3  mov     eax, ebx
0x18000b8b5  add     rsp, 30h
0x18000b8b9  pop     r14
0x18000b8bb  pop     rdi
0x18000b8bc  pop     rsi
0x18000b8bd  pop     rbx
0x18000b8be  pop     rbp
0x18000b8bf  retn
```
