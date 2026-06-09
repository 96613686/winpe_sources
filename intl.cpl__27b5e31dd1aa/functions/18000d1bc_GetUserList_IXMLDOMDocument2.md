# GetUserList(IXMLDOMDocument2 *)

- ea: `0x18000d1bc`
- end: `0x18000d499`
- name: `?GetUserList@@YAJPEAUIXMLDOMDocument2@@@Z`
- size: `733`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000dce0`

## callees

- `0x18000aa10`
- `0x18000aa9c`
- `0x18000accc`
- `0x18000ce98`
- `0x18000d020`
- `0x18000d1bc`
- `0x18000da60`
- `0x18000f464`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18000d3b5`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18000d442`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18000d3b5`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18000d442`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d474`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d482`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d474`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d482`

## string_xrefs

- `0x18000d3c7`: `CopySettingsToSystemAcct`
- `0x18000d328`: `CopySettingsToDefaultUserAcct`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall GetUserList(struct IXMLDOMDocument2 *a1)
{
  OLECHAR *v2; // rsi
  OLECHAR *v3; // rdi
  unsigned int Attribute; // ebx
  HRESULT (__stdcall *selectSingleNode)(IXMLDOMDocument2 *, BSTR, IXMLDOMNode **); // r15
  _bstr_t *v6; // rbx
  _bstr_t *v7; // rax
  _QWORD *v8; // rdx
  HRESULT (__stdcall *v9)(IXMLDOMNode *, BSTR, IXMLDOMNode **); // r14
  _bstr_t *v10; // rbx
  _bstr_t *v11; // rax
  _QWORD *v12; // rdx
  _bstr_t *v13; // rax
  unsigned __int16 *v14; // rdx
  int v15; // eax
  unsigned __int16 ***v16; // rax
  unsigned __int16 *v17; // rdx
  _BYTE v19[8]; // [rsp+50h] [rbp-20h] BYREF
  _BYTE v20[8]; // [rsp+58h] [rbp-18h] BYREF
  _BYTE v21[16]; // [rsp+60h] [rbp-10h] BYREF
  struct IXMLDOMNode *v22; // [rsp+B0h] [rbp+40h] BYREF
  struct IXMLDOMNode *v23; // [rsp+B8h] [rbp+48h] BYREF
  LPCWCH v24; // [rsp+C0h] [rbp+50h] BYREF
  LPCWCH lpString1; // [rsp+C8h] [rbp+58h] BYREF

  v22 = 0;
  v23 = 0;
  v2 = 0;
  lpString1 = 0;
  v3 = 0;
  v24 = 0;
  if ( a1 )
  {
    selectSingleNode = a1->lpVtbl->selectSingleNode;
    v6 = _bstr_t::_bstr_t((_bstr_t *)v21, "//");
    v7 = _bstr_t::_bstr_t((_bstr_t *)v20, L"gs:UserList");
    v8 = *(_QWORD **)_bstr_t::operator+(v6, v19, v7);
    if ( v8 )
      v8 = (_QWORD *)*v8;
    Attribute = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, _QWORD *, struct IXMLDOMNode **))selectSingleNode)(
                  a1,
                  v8,
                  &v22);
    _bstr_t::_Free((_bstr_t *)v19);
    _bstr_t::_Free((_bstr_t *)v20);
    _bstr_t::_Free((_bstr_t *)v21);
    if ( Attribute == 1 )
    {
      Attribute = 0;
    }
    else if ( (unsigned int)CheckHR(Attribute) )
    {
      v9 = v22->lpVtbl->selectSingleNode;
      v10 = _bstr_t::_bstr_t((_bstr_t *)v19, "//");
      v11 = _bstr_t::_bstr_t((_bstr_t *)v20, L"gs:User");
      v12 = *(_QWORD **)_bstr_t::operator+(v10, v21, v11);
      if ( v12 )
        v12 = (_QWORD *)*v12;
      Attribute = ((__int64 (__fastcall *)(struct IXMLDOMNode *, _QWORD *, struct IXMLDOMNode **))v9)(v22, v12, &v23);
      _bstr_t::_Free((_bstr_t *)v21);
      _bstr_t::_Free((_bstr_t *)v20);
      _bstr_t::_Free((_bstr_t *)v19);
      if ( Attribute != 1 && (unsigned int)CheckHR(Attribute) )
      {
        v13 = _bstr_t::_bstr_t((_bstr_t *)v21, DEFAULTUSERACCT_ATTR);
        v14 = *(_QWORD *)v13 ? **(unsigned __int16 ***)v13 : 0LL;
        Attribute = GetAttribute(v23, v14, (unsigned __int16 **)&lpString1);
        _bstr_t::_Free((_bstr_t *)v21);
        v15 = CheckHR(Attribute);
        v2 = (OLECHAR *)lpString1;
        if ( v15 )
        {
          if ( CompareStringEx(&LocaleName, 0x10u, lpString1, -1, TRUE_ATTR, -1, 0, 0, 0) == 2 )
            gCopySettingsToDefaultUserAcct = 1;
          v16 = (unsigned __int16 ***)_bstr_t::_bstr_t((_bstr_t *)&lpString1, SYSTEMACCT_ATTR);
          if ( *v16 )
            v17 = **v16;
          else
            v17 = 0;
          Attribute = GetAttribute(v23, v17, (unsigned __int16 **)&v24);
          _bstr_t::_Free((_bstr_t *)&lpString1);
          if ( (unsigned int)CheckHR(Attribute) )
          {
            v3 = (OLECHAR *)v24;
            if ( CompareStringEx(&LocaleName, 0x10u, v24, -1, TRUE_ATTR, -1, 0, 0, 0) == 2 )
              gCopySettingsToSystemAcct = 1;
          }
          else
          {
            v3 = (OLECHAR *)v24;
          }
        }
      }
    }
  }
  else
  {
    Attribute = -2147024809;
  }
  ReleaseDomNode(&v22);
  ReleaseDomNode(&v23);
  if ( v2 )
    SysFreeString(v2);
  if ( v3 )
    SysFreeString(v3);
  return Attribute;
}

```

## disassembly

```asm
0x18000d1bc  push    rbp
0x18000d1be  push    rbx
0x18000d1bf  push    rsi
0x18000d1c0  push    rdi
0x18000d1c1  push    r13
0x18000d1c3  push    r14
0x18000d1c5  push    r15
0x18000d1c7  mov     rbp, rsp
0x18000d1ca  sub     rsp, 70h
0x18000d1ce  mov     r14, rcx
0x18000d1d1  mov     [rbp+arg_0], 0
0x18000d1d9  mov     [rbp+arg_8], 0
0x18000d1e1  xor     esi, esi
0x18000d1e3  mov     [rbp+lpString1], rsi
0x18000d1e7  xor     edi, edi
0x18000d1e9  mov     [rbp+arg_10], rdi
0x18000d1ed  test    rcx, rcx
0x18000d1f0  jnz     short loc_18000D1FC
0x18000d1f2  mov     ebx, 80070057h
0x18000d1f7  jmp     loc_18000D45A
0x18000d1fc  mov     rax, [rcx]
0x18000d1ff  mov     r15, [rax+128h]
0x18000d206  lea     rdx, asc_180030760; "//"
0x18000d20d  lea     rcx, [rbp+var_10]; this
0x18000d211  call    ??0_bstr_t@@QEAA@PEBD@Z; _bstr_t::_bstr_t(char const *)
0x18000d216  mov     rbx, rax
0x18000d219  lea     rdx, aGsUserlist; "gs:UserList"
0x18000d220  lea     rcx, [rbp+var_18]; this
0x18000d224  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000d229  nop
0x18000d22a  mov     r8, rax
0x18000d22d  lea     rdx, [rbp+var_20]
0x18000d231  mov     rcx, rbx
0x18000d234  call    ??H_bstr_t@@QEBA?AV0@AEBV0@@Z; _bstr_t::operator+(_bstr_t const &)
0x18000d239  nop
0x18000d23a  mov     rdx, [rax]
0x18000d23d  test    rdx, rdx
0x18000d240  jz      short loc_18000D245
0x18000d242  mov     rdx, [rdx]
0x18000d245  lea     r8, [rbp+arg_0]
0x18000d249  mov     rcx, r14
0x18000d24c  mov     rax, r15
0x18000d24f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d254  mov     ebx, eax
0x18000d256  lea     rcx, [rbp+var_20]; this
0x18000d25a  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000d25f  nop
0x18000d260  lea     rcx, [rbp+var_18]; this
0x18000d264  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000d269  nop
0x18000d26a  lea     rcx, [rbp+var_10]; this
0x18000d26e  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000d273  mov     r15d, 1
0x18000d279  cmp     ebx, r15d
0x18000d27c  jnz     short loc_18000D285
0x18000d27e  xor     ebx, ebx
0x18000d280  jmp     loc_18000D45A
0x18000d285  mov     ecx, ebx; int
0x18000d287  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000d28c  test    eax, eax
0x18000d28e  jz      loc_18000D45A
0x18000d294  mov     rax, [rbp+arg_0]
0x18000d298  mov     rcx, [rax]
0x18000d29b  mov     r14, [rcx+128h]
0x18000d2a2  lea     rdx, asc_180030760; "//"
0x18000d2a9  lea     rcx, [rbp+var_20]; this
0x18000d2ad  call    ??0_bstr_t@@QEAA@PEBD@Z; _bstr_t::_bstr_t(char const *)
0x18000d2b2  mov     rbx, rax
0x18000d2b5  lea     rdx, aGsUser; "gs:User"
0x18000d2bc  lea     rcx, [rbp+var_18]; this
0x18000d2c0  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000d2c5  nop
0x18000d2c6  mov     r8, rax
0x18000d2c9  lea     rdx, [rbp+var_10]
0x18000d2cd  mov     rcx, rbx
0x18000d2d0  call    ??H_bstr_t@@QEBA?AV0@AEBV0@@Z; _bstr_t::operator+(_bstr_t const &)
0x18000d2d5  nop
0x18000d2d6  mov     rdx, [rax]
0x18000d2d9  test    rdx, rdx
0x18000d2dc  jz      short loc_18000D2E1
0x18000d2de  mov     rdx, [rdx]
0x18000d2e1  lea     r8, [rbp+arg_8]
0x18000d2e5  mov     rcx, [rbp+arg_0]
0x18000d2e9  mov     rax, r14
0x18000d2ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d2f1  mov     ebx, eax
0x18000d2f3  lea     rcx, [rbp+var_10]; this
0x18000d2f7  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000d2fc  nop
0x18000d2fd  lea     rcx, [rbp+var_18]; this
0x18000d301  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000d306  nop
0x18000d307  lea     rcx, [rbp+var_20]; this
0x18000d30b  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000d310  cmp     ebx, r15d
0x18000d313  jz      loc_18000D45A
0x18000d319  mov     ecx, ebx; int
0x18000d31b  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000d320  test    eax, eax
0x18000d322  jz      loc_18000D45A
0x18000d328  lea     rdx, ?DEFAULTUSERACCT_ATTR@@3PAGA; "CopySettingsToDefaultUserAcct"
0x18000d32f  lea     rcx, [rbp+var_10]; this
0x18000d333  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000d338  nop
0x18000d339  mov     rcx, [rax]
0x18000d33c  test    rcx, rcx
0x18000d33f  jz      short loc_18000D346
0x18000d341  mov     rdx, [rcx]
0x18000d344  jmp     short loc_18000D348
0x18000d346  xor     edx, edx; unsigned __int16 *
0x18000d348  lea     r8, [rbp+lpString1]; unsigned __int16 **
0x18000d34c  mov     rcx, [rbp+arg_8]; struct IXMLDOMNode *
0x18000d350  call    ?GetAttribute@@YAJPEAUIXMLDOMNode@@PEAGPEAPEAG@Z; GetAttribute(IXMLDOMNode *,ushort *,ushort * *)
0x18000d355  mov     ebx, eax
0x18000d357  lea     rcx, [rbp+var_10]; this
0x18000d35b  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000d360  mov     ecx, ebx; int
0x18000d362  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000d367  mov     rsi, [rbp+lpString1]
0x18000d36b  test    eax, eax
0x18000d36d  jz      loc_18000D45A
0x18000d373  mov     [rsp+70h+lParam], 0; lParam
0x18000d37c  mov     [rsp+70h+lpReserved], 0; lpReserved
0x18000d385  mov     [rsp+70h+lpVersionInformation], 0; lpVersionInformation
0x18000d38e  or      edi, 0FFFFFFFFh
0x18000d391  mov     [rsp+70h+cchCount2], edi; cchCount2
0x18000d395  lea     r13, ?TRUE_ATTR@@3PAGA; "true"
0x18000d39c  mov     [rsp+70h+lpString2], r13; lpString2
0x18000d3a1  mov     r9d, edi; cchCount1
0x18000d3a4  mov     r8, rsi; lpString1
0x18000d3a7  lea     r14d, [rdi+11h]
0x18000d3ab  mov     edx, r14d; dwCmpFlags
0x18000d3ae  lea     rcx, LocaleName; lpLocaleName
0x18000d3b5  call    cs:__imp_CompareStringEx
0x18000d3bb  cmp     eax, 2
0x18000d3be  jnz     short loc_18000D3C7
0x18000d3c0  mov     cs:?gCopySettingsToDefaultUserAcct@@3HA, r15d; int gCopySettingsToDefaultUserAcct
0x18000d3c7  lea     rdx, ?SYSTEMACCT_ATTR@@3PAGA; "CopySettingsToSystemAcct"
0x18000d3ce  lea     rcx, [rbp+lpString1]; this
0x18000d3d2  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000d3d7  nop
0x18000d3d8  mov     rcx, [rax]
0x18000d3db  test    rcx, rcx
0x18000d3de  jz      short loc_18000D3E5
0x18000d3e0  mov     rdx, [rcx]
0x18000d3e3  jmp     short loc_18000D3E7
0x18000d3e5  xor     edx, edx; unsigned __int16 *
0x18000d3e7  lea     r8, [rbp+arg_10]; unsigned __int16 **
0x18000d3eb  mov     rcx, [rbp+arg_8]; struct IXMLDOMNode *
0x18000d3ef  call    ?GetAttribute@@YAJPEAUIXMLDOMNode@@PEAGPEAPEAG@Z; GetAttribute(IXMLDOMNode *,ushort *,ushort * *)
0x18000d3f4  mov     ebx, eax
0x18000d3f6  lea     rcx, [rbp+lpString1]; this
0x18000d3fa  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000d3ff  mov     ecx, ebx; int
0x18000d401  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000d406  test    eax, eax
0x18000d408  jz      short loc_18000D456
0x18000d40a  mov     [rsp+70h+lParam], 0; lParam
0x18000d413  mov     [rsp+70h+lpReserved], 0; lpReserved
0x18000d41c  mov     [rsp+70h+lpVersionInformation], 0; lpVersionInformation
0x18000d425  mov     [rsp+70h+cchCount2], edi; cchCount2
0x18000d429  mov     [rsp+70h+lpString2], r13; lpString2
0x18000d42e  mov     r9d, edi; cchCount1
0x18000d431  mov     rdi, [rbp+arg_10]
0x18000d435  mov     r8, rdi; lpString1
0x18000d438  mov     edx, r14d; dwCmpFlags
0x18000d43b  lea     rcx, LocaleName; lpLocaleName
0x18000d442  call    cs:__imp_CompareStringEx
0x18000d448  cmp     eax, 2
0x18000d44b  jnz     short loc_18000D45A
0x18000d44d  mov     cs:?gCopySettingsToSystemAcct@@3HA, r15d; int gCopySettingsToSystemAcct
0x18000d454  jmp     short loc_18000D45A
0x18000d456  mov     rdi, [rbp+arg_10]
0x18000d45a  lea     rcx, [rbp+arg_0]; struct IXMLDOMNode **
0x18000d45e  call    ?ReleaseDomNode@@YAXPEAPEAUIXMLDOMNode@@@Z; ReleaseDomNode(IXMLDOMNode * *)
0x18000d463  lea     rcx, [rbp+arg_8]; struct IXMLDOMNode **
0x18000d467  call    ?ReleaseDomNode@@YAXPEAPEAUIXMLDOMNode@@@Z; ReleaseDomNode(IXMLDOMNode * *)
0x18000d46c  test    rsi, rsi
0x18000d46f  jz      short loc_18000D47A
0x18000d471  mov     rcx, rsi; bstrString
0x18000d474  call    cs:__imp_SysFreeString
0x18000d47a  test    rdi, rdi
0x18000d47d  jz      short loc_18000D488
0x18000d47f  mov     rcx, rdi; bstrString
0x18000d482  call    cs:__imp_SysFreeString
0x18000d488  mov     eax, ebx
0x18000d48a  add     rsp, 70h
0x18000d48e  pop     r15
0x18000d490  pop     r14
0x18000d492  pop     r13
0x18000d494  pop     rdi
0x18000d495  pop     rsi
0x18000d496  pop     rbx
0x18000d497  pop     rbp
0x18000d498  retn
```
