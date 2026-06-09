# ChangeInputPreferences(IXMLDOMDocument2 *)

- ea: `0x18000b2a4`
- end: `0x18000b6e6`
- name: `?ChangeInputPreferences@@YAJPEAUIXMLDOMDocument2@@@Z`
- size: `1090`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18000dce0`

## callees

- `0x18000aa10`
- `0x18000aa9c`
- `0x18000accc`
- `0x18000b2a4`
- `0x18000ce98`
- `0x18000d020`
- `0x18000da60`
- `0x18000f464`
- `0x180012f10`
- `0x18001308c`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18000b544`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18000b601`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18000b544`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18000b601`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b63c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b651`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b665`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b692`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b6a0`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b6ae`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b63c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b651`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b665`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b692`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b6a0`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b6ae`
- `Bcp47Langs!SetInputMethodOverride` at `0x18000b60f`
- `Bcp47Langs!SetInputMethodOverride` at `0x18000b60f`

## string_xrefs

- `0x18000b528`: `Remove`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall ChangeInputPreferences(struct IXMLDOMDocument2 *a1)
{
  OLECHAR *v2; // r14
  unsigned __int16 *v3; // rsi
  OLECHAR *v4; // rdi
  unsigned int Attribute; // ebx
  HRESULT (__stdcall *selectSingleNode)(IXMLDOMDocument2 *, BSTR, IXMLDOMNode **); // r12
  _bstr_t *v7; // rbx
  _bstr_t *v8; // rax
  _QWORD *v9; // rdx
  HRESULT (__stdcall *selectNodes)(IXMLDOMNode *, BSTR, IXMLDOMNodeList **); // r15
  _bstr_t *v11; // rbx
  _bstr_t *v12; // rax
  _QWORD *v13; // rdx
  unsigned int v14; // r12d
  int v15; // r15d
  unsigned __int16 ***v16; // rax
  unsigned __int16 *v17; // rdx
  unsigned __int16 ***v18; // rax
  unsigned __int16 *v19; // rdx
  int v20; // eax
  int v21; // eax
  unsigned int v22; // ecx
  unsigned __int16 ***v23; // rax
  unsigned __int16 *v24; // rdx
  int v25; // eax
  unsigned int v26; // edx
  BSTR bstrString; // [rsp+50h] [rbp-30h] BYREF
  __int64 v29; // [rsp+58h] [rbp-28h] BYREF
  _BYTE v30[8]; // [rsp+60h] [rbp-20h] BYREF
  _BYTE v31[8]; // [rsp+68h] [rbp-18h] BYREF
  _BYTE v32[16]; // [rsp+70h] [rbp-10h] BYREF
  int v33; // [rsp+C0h] [rbp+40h] BYREF
  struct IXMLDOMNode *v34; // [rsp+C8h] [rbp+48h] BYREF
  LPCWCH v35; // [rsp+D0h] [rbp+50h] BYREF
  LPCWCH lpString1; // [rsp+D8h] [rbp+58h] BYREF

  v34 = 0;
  v29 = 0;
  v2 = 0;
  lpString1 = 0;
  v3 = 0;
  bstrString = 0;
  v4 = 0;
  v35 = 0;
  v33 = 0;
  if ( a1 )
  {
    selectSingleNode = a1->lpVtbl->selectSingleNode;
    v7 = _bstr_t::_bstr_t((_bstr_t *)v32, "//");
    v8 = _bstr_t::_bstr_t((_bstr_t *)v31, L"gs:InputPreferences");
    v9 = *(_QWORD **)_bstr_t::operator+(v7, v30, v8);
    if ( v9 )
      v9 = (_QWORD *)*v9;
    Attribute = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, _QWORD *, struct IXMLDOMNode **))selectSingleNode)(
                  a1,
                  v9,
                  &v34);
    _bstr_t::_Free((_bstr_t *)v30);
    _bstr_t::_Free((_bstr_t *)v31);
    _bstr_t::_Free((_bstr_t *)v32);
    if ( Attribute == 1 )
    {
      Attribute = 0;
    }
    else if ( (unsigned int)CheckHR(Attribute) )
    {
      selectNodes = v34->lpVtbl->selectNodes;
      v11 = _bstr_t::_bstr_t((_bstr_t *)v30, "//");
      v12 = _bstr_t::_bstr_t((_bstr_t *)v31, L"gs:InputLanguageID");
      v13 = *(_QWORD **)_bstr_t::operator+(v11, v32, v12);
      if ( v13 )
        v13 = (_QWORD *)*v13;
      Attribute = ((__int64 (__fastcall *)(struct IXMLDOMNode *, _QWORD *, __int64 *))selectNodes)(v34, v13, &v29);
      _bstr_t::_Free((_bstr_t *)v32);
      _bstr_t::_Free((_bstr_t *)v31);
      _bstr_t::_Free((_bstr_t *)v30);
      if ( (unsigned int)CheckHR(Attribute) )
      {
        ReleaseDomNode(&v34);
        Attribute = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v29 + 64LL))(v29, &v33);
        if ( (unsigned int)CheckHR(Attribute) )
        {
          v14 = 0;
          v15 = 0;
          if ( v33 > 0 )
          {
            do
            {
              Attribute = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IXMLDOMNode **))(*(_QWORD *)v29 + 56LL))(
                            v29,
                            (unsigned int)v15,
                            &v34);
              if ( !(unsigned int)CheckHR(Attribute) )
                break;
              v16 = (unsigned __int16 ***)_bstr_t::_bstr_t((_bstr_t *)v32, ACTION_ATTR);
              if ( *v16 )
                v17 = **v16;
              else
                v17 = 0;
              Attribute = GetAttribute(v34, v17, (unsigned __int16 **)&lpString1);
              _bstr_t::_Free((_bstr_t *)v32);
              if ( !(unsigned int)CheckHR(Attribute) )
              {
                v2 = (OLECHAR *)lpString1;
                break;
              }
              v18 = (unsigned __int16 ***)_bstr_t::_bstr_t((_bstr_t *)v31, ID_ATTR);
              if ( *v18 )
                v19 = **v18;
              else
                v19 = 0;
              Attribute = GetAttribute(v34, v19, &bstrString);
              _bstr_t::_Free((_bstr_t *)v31);
              v20 = CheckHR(Attribute);
              v2 = (OLECHAR *)lpString1;
              if ( !v20 )
              {
                v3 = bstrString;
                break;
              }
              v21 = CompareStringEx(&LocaleName, 0x10u, lpString1, -1, REMOVE_ATTR, -1, 0, 0, 0);
              Attribute = 1;
              v22 = v14 | 1;
              if ( v21 != 2 )
                v22 = v14;
              v14 = v22;
              v3 = bstrString;
              if ( (unsigned int)Input_InstallLayoutOrTip(bstrString, v22) )
              {
                v23 = (unsigned __int16 ***)_bstr_t::_bstr_t((_bstr_t *)v30, DEFAULT_ATTR);
                if ( *v23 )
                  v24 = **v23;
                else
                  v24 = 0;
                Attribute = GetAttribute(v34, v24, (unsigned __int16 **)&v35);
                _bstr_t::_Free((_bstr_t *)v30);
                v25 = CheckHR(Attribute);
                v4 = (OLECHAR *)v35;
                if ( !v25 )
                  break;
                if ( !Attribute && CompareStringEx(&LocaleName, 0x10u, v35, -1, TRUE_ATTR, -1, 0, 0, 0) == 2 )
                {
                  Attribute = SetInputMethodOverride(v3);
                  if ( !Attribute )
                    Attribute = Input_SetDefaultLayoutOrTip(v3, v26) == 0;
                }
              }
              ReleaseDomNode(&v34);
              if ( v2 )
              {
                SysFreeString(v2);
                v2 = 0;
                lpString1 = 0;
              }
              if ( v3 )
              {
                SysFreeString(v3);
                v3 = 0;
                bstrString = 0;
              }
              if ( v4 )
              {
                SysFreeString(v4);
                v4 = 0;
                v35 = 0;
              }
              ++v15;
            }
            while ( v15 < v33 );
            if ( v2 )
              SysFreeString(v2);
            if ( v3 )
              SysFreeString(v3);
            if ( v4 )
              SysFreeString(v4);
          }
        }
      }
    }
  }
  else
  {
    Attribute = -2147024809;
  }
  ReleaseDomNode(&v34);
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  return Attribute;
}

```

## disassembly

```asm
0x18000b2a4  push    rbp
0x18000b2a6  push    rbx
0x18000b2a7  push    rsi
0x18000b2a8  push    rdi
0x18000b2a9  push    r12
0x18000b2ab  push    r14
0x18000b2ad  push    r15
0x18000b2af  mov     rbp, rsp
0x18000b2b2  sub     rsp, 80h
0x18000b2b9  mov     r15, rcx
0x18000b2bc  mov     [rbp+arg_8], 0
0x18000b2c4  mov     [rbp+var_28], 0
0x18000b2cc  xor     r14d, r14d
0x18000b2cf  mov     [rbp+lpString1], r14
0x18000b2d3  xor     esi, esi
0x18000b2d5  mov     [rbp+bstrString], rsi
0x18000b2d9  xor     edi, edi
0x18000b2db  mov     [rbp+arg_10], rdi
0x18000b2df  mov     [rbp+arg_0], esi
0x18000b2e2  test    rcx, rcx
0x18000b2e5  jnz     short loc_18000B2F1
0x18000b2e7  mov     ebx, 80070057h
0x18000b2ec  jmp     loc_18000B6B4
0x18000b2f1  mov     rax, [rcx]
0x18000b2f4  mov     r12, [rax+128h]
0x18000b2fb  lea     rdx, asc_180030760; "//"
0x18000b302  lea     rcx, [rbp+var_10]; this
0x18000b306  call    ??0_bstr_t@@QEAA@PEBD@Z; _bstr_t::_bstr_t(char const *)
0x18000b30b  mov     rbx, rax
0x18000b30e  lea     rdx, aGsInputprefere; "gs:InputPreferences"
0x18000b315  lea     rcx, [rbp+var_18]; this
0x18000b319  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000b31e  nop
0x18000b31f  mov     r8, rax
0x18000b322  lea     rdx, [rbp+var_20]
0x18000b326  mov     rcx, rbx
0x18000b329  call    ??H_bstr_t@@QEBA?AV0@AEBV0@@Z; _bstr_t::operator+(_bstr_t const &)
0x18000b32e  nop
0x18000b32f  mov     rdx, [rax]
0x18000b332  test    rdx, rdx
0x18000b335  jz      short loc_18000B33A
0x18000b337  mov     rdx, [rdx]
0x18000b33a  lea     r8, [rbp+arg_8]
0x18000b33e  mov     rcx, r15
0x18000b341  mov     rax, r12
0x18000b344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b349  mov     ebx, eax
0x18000b34b  lea     rcx, [rbp+var_20]; this
0x18000b34f  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000b354  nop
0x18000b355  lea     rcx, [rbp+var_18]; this
0x18000b359  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000b35e  nop
0x18000b35f  lea     rcx, [rbp+var_10]; this
0x18000b363  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000b368  cmp     ebx, 1
0x18000b36b  jnz     short loc_18000B374
0x18000b36d  xor     ebx, ebx
0x18000b36f  jmp     loc_18000B6B4
0x18000b374  mov     ecx, ebx; int
0x18000b376  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000b37b  test    eax, eax
0x18000b37d  jz      loc_18000B6B4
0x18000b383  mov     rax, [rbp+arg_8]
0x18000b387  mov     rcx, [rax]
0x18000b38a  mov     r15, [rcx+120h]
0x18000b391  lea     rdx, asc_180030760; "//"
0x18000b398  lea     rcx, [rbp+var_20]; this
0x18000b39c  call    ??0_bstr_t@@QEAA@PEBD@Z; _bstr_t::_bstr_t(char const *)
0x18000b3a1  mov     rbx, rax
0x18000b3a4  lea     rdx, aGsInputlanguag; "gs:InputLanguageID"
0x18000b3ab  lea     rcx, [rbp+var_18]; this
0x18000b3af  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000b3b4  nop
0x18000b3b5  mov     r8, rax
0x18000b3b8  lea     rdx, [rbp+var_10]
0x18000b3bc  mov     rcx, rbx
0x18000b3bf  call    ??H_bstr_t@@QEBA?AV0@AEBV0@@Z; _bstr_t::operator+(_bstr_t const &)
0x18000b3c4  nop
0x18000b3c5  mov     rdx, [rax]
0x18000b3c8  test    rdx, rdx
0x18000b3cb  jz      short loc_18000B3D0
0x18000b3cd  mov     rdx, [rdx]
0x18000b3d0  lea     r8, [rbp+var_28]
0x18000b3d4  mov     rcx, [rbp+arg_8]
0x18000b3d8  mov     rax, r15
0x18000b3db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3e0  mov     ebx, eax
0x18000b3e2  lea     rcx, [rbp+var_10]; this
0x18000b3e6  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000b3eb  nop
0x18000b3ec  lea     rcx, [rbp+var_18]; this
0x18000b3f0  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000b3f5  nop
0x18000b3f6  lea     rcx, [rbp+var_20]; this
0x18000b3fa  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000b3ff  mov     ecx, ebx; int
0x18000b401  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000b406  test    eax, eax
0x18000b408  jz      loc_18000B6B4
0x18000b40e  lea     rcx, [rbp+arg_8]; struct IXMLDOMNode **
0x18000b412  call    ?ReleaseDomNode@@YAXPEAPEAUIXMLDOMNode@@@Z; ReleaseDomNode(IXMLDOMNode * *)
0x18000b417  mov     rcx, [rbp+var_28]
0x18000b41b  mov     rax, [rcx]
0x18000b41e  lea     rdx, [rbp+arg_0]
0x18000b422  mov     rax, [rax+40h]
0x18000b426  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b42b  mov     ebx, eax
0x18000b42d  mov     ecx, eax; int
0x18000b42f  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000b434  test    eax, eax
0x18000b436  jz      loc_18000B6B4
0x18000b43c  xor     r12d, r12d
0x18000b43f  xor     r15d, r15d
0x18000b442  cmp     [rbp+arg_0], r12d
0x18000b446  jle     loc_18000B6B4
0x18000b44c  mov     rcx, [rbp+var_28]
0x18000b450  mov     rax, [rcx]
0x18000b453  lea     r8, [rbp+arg_8]
0x18000b457  mov     edx, r15d
0x18000b45a  mov     rax, [rax+38h]
0x18000b45e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b463  mov     ebx, eax
0x18000b465  mov     ecx, eax; int
0x18000b467  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000b46c  test    eax, eax
0x18000b46e  jz      loc_18000B68A
0x18000b474  lea     rdx, ?ACTION_ATTR@@3PAGA; "Action"
0x18000b47b  lea     rcx, [rbp+var_10]; this
0x18000b47f  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000b484  nop
0x18000b485  mov     rcx, [rax]
0x18000b488  test    rcx, rcx
0x18000b48b  jz      short loc_18000B492
0x18000b48d  mov     rdx, [rcx]
0x18000b490  jmp     short loc_18000B494
0x18000b492  xor     edx, edx; unsigned __int16 *
0x18000b494  lea     r8, [rbp+lpString1]; unsigned __int16 **
0x18000b498  mov     rcx, [rbp+arg_8]; struct IXMLDOMNode *
0x18000b49c  call    ?GetAttribute@@YAJPEAUIXMLDOMNode@@PEAGPEAPEAG@Z; GetAttribute(IXMLDOMNode *,ushort *,ushort * *)
0x18000b4a1  mov     ebx, eax
0x18000b4a3  lea     rcx, [rbp+var_10]; this
0x18000b4a7  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000b4ac  mov     ecx, ebx; int
0x18000b4ae  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000b4b3  test    eax, eax
0x18000b4b5  jz      loc_18000B686
0x18000b4bb  lea     rdx, ?ID_ATTR@@3PAGA; "ID"
0x18000b4c2  lea     rcx, [rbp+var_18]; this
0x18000b4c6  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000b4cb  nop
0x18000b4cc  mov     rcx, [rax]
0x18000b4cf  test    rcx, rcx
0x18000b4d2  jz      short loc_18000B4D9
0x18000b4d4  mov     rdx, [rcx]
0x18000b4d7  jmp     short loc_18000B4DB
0x18000b4d9  xor     edx, edx; unsigned __int16 *
0x18000b4db  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x18000b4df  mov     rcx, [rbp+arg_8]; struct IXMLDOMNode *
0x18000b4e3  call    ?GetAttribute@@YAJPEAUIXMLDOMNode@@PEAGPEAPEAG@Z; GetAttribute(IXMLDOMNode *,ushort *,ushort * *)
0x18000b4e8  mov     ebx, eax
0x18000b4ea  lea     rcx, [rbp+var_18]; this
0x18000b4ee  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000b4f3  mov     ecx, ebx; int
0x18000b4f5  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000b4fa  mov     r14, [rbp+lpString1]
0x18000b4fe  test    eax, eax
0x18000b500  jz      loc_18000B680
0x18000b506  mov     [rsp+80h+lParam], 0; lParam
0x18000b50f  mov     [rsp+80h+lpReserved], 0; lpReserved
0x18000b518  mov     [rsp+80h+lpVersionInformation], 0; lpVersionInformation
0x18000b521  or      ecx, 0FFFFFFFFh
0x18000b524  mov     [rsp+80h+cchCount2], ecx; cchCount2
0x18000b528  lea     rax, ?REMOVE_ATTR@@3PAGA; "Remove"
0x18000b52f  mov     [rsp+80h+lpString2], rax; lpString2
0x18000b534  mov     r9d, ecx; cchCount1
0x18000b537  mov     r8, r14; lpString1
0x18000b53a  lea     edx, [rcx+11h]; dwCmpFlags
0x18000b53d  lea     rcx, LocaleName; lpLocaleName
0x18000b544  call    cs:__imp_CompareStringEx
0x18000b54a  mov     ecx, r12d
0x18000b54d  mov     ebx, 1
0x18000b552  or      ecx, ebx
0x18000b554  cmp     eax, 2
0x18000b557  cmovnz  ecx, r12d
0x18000b55b  mov     r12d, ecx
0x18000b55e  mov     edx, ecx; unsigned int
0x18000b560  mov     rsi, [rbp+bstrString]
0x18000b564  mov     rcx, rsi; unsigned __int16 *
0x18000b567  call    ?Input_InstallLayoutOrTip@@YAHPEBGK@Z; Input_InstallLayoutOrTip(ushort const *,ulong)
0x18000b56c  test    eax, eax
0x18000b56e  jz      loc_18000B62B
0x18000b574  lea     rdx, ?DEFAULT_ATTR@@3PAGA; "Default"
0x18000b57b  lea     rcx, [rbp+var_20]; this
0x18000b57f  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000b584  nop
0x18000b585  mov     rcx, [rax]
0x18000b588  test    rcx, rcx
0x18000b58b  jz      short loc_18000B592
0x18000b58d  mov     rdx, [rcx]
0x18000b590  jmp     short loc_18000B594
0x18000b592  xor     edx, edx; unsigned __int16 *
0x18000b594  lea     r8, [rbp+arg_10]; unsigned __int16 **
0x18000b598  mov     rcx, [rbp+arg_8]; struct IXMLDOMNode *
0x18000b59c  call    ?GetAttribute@@YAJPEAUIXMLDOMNode@@PEAGPEAPEAG@Z; GetAttribute(IXMLDOMNode *,ushort *,ushort * *)
0x18000b5a1  mov     ebx, eax
0x18000b5a3  lea     rcx, [rbp+var_20]; this
0x18000b5a7  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000b5ac  mov     ecx, ebx; int
0x18000b5ae  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000b5b3  mov     rdi, [rbp+arg_10]
0x18000b5b7  test    eax, eax
0x18000b5b9  jz      loc_18000B68A
0x18000b5bf  test    ebx, ebx
0x18000b5c1  jnz     short loc_18000B62B
0x18000b5c3  mov     [rsp+80h+lParam], 0; lParam
0x18000b5cc  mov     [rsp+80h+lpReserved], 0; lpReserved
0x18000b5d5  mov     [rsp+80h+lpVersionInformation], 0; lpVersionInformation
0x18000b5de  or      ecx, 0FFFFFFFFh
0x18000b5e1  mov     [rsp+80h+cchCount2], ecx; cchCount2
0x18000b5e5  lea     rax, ?TRUE_ATTR@@3PAGA; "true"
0x18000b5ec  mov     [rsp+80h+lpString2], rax; lpString2
0x18000b5f1  mov     r9d, ecx; cchCount1
0x18000b5f4  mov     r8, rdi; lpString1
0x18000b5f7  lea     edx, [rbx+10h]; dwCmpFlags
0x18000b5fa  lea     rcx, LocaleName; lpLocaleName
0x18000b601  call    cs:__imp_CompareStringEx
0x18000b607  cmp     eax, 2
0x18000b60a  jnz     short loc_18000B62B
0x18000b60c  mov     rcx, rsi
0x18000b60f  call    cs:__imp_SetInputMethodOverride
0x18000b615  mov     ebx, eax
0x18000b617  test    eax, eax
0x18000b619  jnz     short loc_18000B62B
0x18000b61b  mov     rcx, rsi; unsigned __int16 *
0x18000b61e  call    ?Input_SetDefaultLayoutOrTip@@YAHPEBGK@Z; Input_SetDefaultLayoutOrTip(ushort const *,ulong)
0x18000b623  test    eax, eax
0x18000b625  lea     eax, [rbx+1]
0x18000b628  cmovz   ebx, eax
0x18000b62b  lea     rcx, [rbp+arg_8]; struct IXMLDOMNode **
0x18000b62f  call    ?ReleaseDomNode@@YAXPEAPEAUIXMLDOMNode@@@Z; ReleaseDomNode(IXMLDOMNode * *)
0x18000b634  test    r14, r14
0x18000b637  jz      short loc_18000B649
0x18000b639  mov     rcx, r14; bstrString
0x18000b63c  call    cs:__imp_SysFreeString
0x18000b642  xor     r14d, r14d
0x18000b645  mov     [rbp+lpString1], r14
0x18000b649  test    rsi, rsi
0x18000b64c  jz      short loc_18000B65D
0x18000b64e  mov     rcx, rsi; bstrString
0x18000b651  call    cs:__imp_SysFreeString
0x18000b657  xor     esi, esi
0x18000b659  mov     [rbp+bstrString], rsi
0x18000b65d  test    rdi, rdi
0x18000b660  jz      short loc_18000B671
0x18000b662  mov     rcx, rdi; bstrString
0x18000b665  call    cs:__imp_SysFreeString
0x18000b66b  xor     edi, edi
0x18000b66d  mov     [rbp+arg_10], rdi
0x18000b671  inc     r15d
0x18000b674  cmp     r15d, [rbp+arg_0]
0x18000b678  jl      loc_18000B44C
0x18000b67e  jmp     short loc_18000B68A
0x18000b680  mov     rsi, [rbp+bstrString]
0x18000b684  jmp     short loc_18000B68A
0x18000b686  mov     r14, [rbp+lpString1]
0x18000b68a  test    r14, r14
0x18000b68d  jz      short loc_18000B698
0x18000b68f  mov     rcx, r14; bstrString
0x18000b692  call    cs:__imp_SysFreeString
0x18000b698  test    rsi, rsi
0x18000b69b  jz      short loc_18000B6A6
0x18000b69d  mov     rcx, rsi; bstrString
0x18000b6a0  call    cs:__imp_SysFreeString
0x18000b6a6  test    rdi, rdi
0x18000b6a9  jz      short loc_18000B6B4
0x18000b6ab  mov     rcx, rdi; bstrString
0x18000b6ae  call    cs:__imp_SysFreeString
0x18000b6b4  lea     rcx, [rbp+arg_8]; struct IXMLDOMNode **
0x18000b6b8  call    ?ReleaseDomNode@@YAXPEAPEAUIXMLDOMNode@@@Z; ReleaseDomNode(IXMLDOMNode * *)
0x18000b6bd  mov     rcx, [rbp+var_28]
0x18000b6c1  test    rcx, rcx
0x18000b6c4  jz      short loc_18000B6D2
0x18000b6c6  mov     rax, [rcx]
0x18000b6c9  mov     rax, [rax+10h]
0x18000b6cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6d2  mov     eax, ebx
0x18000b6d4  add     rsp, 80h
0x18000b6db  pop     r15
0x18000b6dd  pop     r14
0x18000b6df  pop     r12
0x18000b6e1  pop     rdi
0x18000b6e2  pop     rsi
0x18000b6e3  pop     rbx
0x18000b6e4  pop     rbp
0x18000b6e5  retn
```
