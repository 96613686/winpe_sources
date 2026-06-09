# WSTrustResponse::GetErrorCode(void)

- ea: `0x140027d80`
- end: `0x140027efc`
- name: `?GetErrorCode@WSTrustResponse@@QEBA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ`
- size: `380`
- prototype: `void **__fastcall(const unsigned __int16 **, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140016a04`

## callees

- `0x140005c80`
- `0x1400061dc`
- `0x140008308`
- `0x140018d0c`
- `0x1400193b4`
- `0x140019a5c`
- `0x14001c244`
- `0x140027d80`
- `0x140028040`
- `0x14002c070`
- `0x140030010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x140027e87`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x140027e87`

## string_xrefs

- `0x140027df7`: `xmlns:S='http://www.w3.org/2003/05/soap-envelope' `

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void **__fastcall WSTrustResponse::GetErrorCode(const unsigned __int16 **a1, void **a2)
{
  struct IUnknown *v4; // rbx
  __int64 v5; // rbx
  __int64 v6; // rdx
  __int64 v7; // r8
  wchar_t *v8; // rax
  __int64 v9; // rax
  _BYTE v11[8]; // [rsp+28h] [rbp-18h] BYREF
  __int64 v12; // [rsp+30h] [rbp-10h]
  __int64 *v13; // [rsp+70h] [rbp+30h] BYREF
  struct IUnknown *v14; // [rsp+78h] [rbp+38h] BYREF

  *a2 = (void *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          a2,
          (__int64)L"Unknown") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(a2, L"Unknown", 7);
  if ( *((_DWORD *)*a1 - 4) )
  {
    MSXML::Create(&v14, *a1, L"xmlns:S='http://www.w3.org/2003/05/soap-envelope' ");
    v4 = v14;
    if ( !v14 )
      _com_issue_error(-2147467261);
    _bstr_t::_bstr_t((_bstr_t *)v11, L"S:Envelope/S:Body/S:Fault/S:Code/S:Subcode/S:Value");
    MSXML::IXMLDOMNode::selectSingleNode(v4);
    v5 = v12;
    if ( !v12 )
      goto LABEL_18;
    MSXML::IXMLDOMNode::Gettext(v12, &v13);
    if ( v13 )
    {
      v6 = *v13;
      if ( *v13 )
      {
        v7 = -1;
        do
          ++v7;
        while ( *(_WORD *)(v6 + 2 * v7) );
        goto LABEL_13;
      }
    }
    else
    {
      v6 = 0;
    }
    v7 = 0;
LABEL_13:
    ATL::CSimpleStringT<unsigned short,0>::SetString(a2, v6, v7);
    if ( *((int *)*a2 - 4) > 0 )
    {
      v8 = wcschr((const wchar_t *)*a2, 0x3Au);
      if ( v8 )
      {
        v9 = ((char *)v8 - (_BYTE *)*a2) >> 1;
        if ( (int)v9 > 0 )
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Delete(
            (__int64 *)a2,
            0,
            v9 + 1);
      }
    }
    _bstr_t::~_bstr_t((_bstr_t *)&v13);
LABEL_18:
    if ( v5 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    if ( v14 )
      ((void (__fastcall *)(struct IUnknown *))v14->lpVtbl->Release)(v14);
  }
  return a2;
}

```

## disassembly

```asm
0x140027d80  mov     [rsp-18h+arg_0], rbx
0x140027d85  mov     [rsp-18h+arg_8], rdx
0x140027d8a  push    rbp
0x140027d8b  push    rsi
0x140027d8c  push    rdi
0x140027d8d  mov     rbp, rsp
0x140027d90  sub     rsp, 40h
0x140027d94  mov     rdi, rdx
0x140027d97  mov     rbx, rcx
0x140027d9a  xor     esi, esi
0x140027d9c  mov     [rbp+var_20], esi
0x140027d9f  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140027da6  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140027dad  mov     rax, [rax+18h]
0x140027db1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027db6  add     rax, 18h
0x140027dba  mov     [rdi], rax
0x140027dbd  lea     rdx, aUnknown_0; "Unknown"
0x140027dc4  mov     rcx, rdi
0x140027dc7  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x140027dcc  test    al, al
0x140027dce  jnz     short loc_140027DE4
0x140027dd0  lea     r8d, [rsi+7]
0x140027dd4  lea     rdx, aUnknown_0; "Unknown"
0x140027ddb  mov     rcx, rdi
0x140027dde  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x140027de3  nop
0x140027de4  mov     [rbp+var_20], 1
0x140027deb  mov     rdx, [rbx]
0x140027dee  cmp     [rdx-10h], esi
0x140027df1  jz      loc_140027EE1
0x140027df7  lea     r8, aXmlnsSHttpWwwW_0; "xmlns:S='http://www.w3.org/2003/05/soap"...
0x140027dfe  lea     rcx, [rbp+arg_18]
0x140027e02  call    ?Create@MSXML@@YA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@PEBG0@Z; MSXML::Create(ushort const *,ushort const *)
0x140027e07  nop
0x140027e08  mov     rbx, [rbp+arg_18]
0x140027e0c  test    rbx, rbx
0x140027e0f  jz      loc_140027EF1
0x140027e15  lea     rdx, aSEnvelopeSBody_0; "S:Envelope/S:Body/S:Fault/S:Code/S:Subc"...
0x140027e1c  lea     rcx, [rbp+var_18]; this
0x140027e20  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x140027e25  mov     r8, rax
0x140027e28  lea     rdx, [rbp+var_10]
0x140027e2c  mov     rcx, rbx; struct IUnknown *
0x140027e2f  call    ?selectSingleNode@IXMLDOMNode@MSXML@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML::IXMLDOMNode::selectSingleNode(_bstr_t)
0x140027e34  nop
0x140027e35  mov     rbx, [rbp+var_10]
0x140027e39  test    rbx, rbx
0x140027e3c  jz      short loc_140027EB6
0x140027e3e  lea     rdx, [rbp+arg_10]
0x140027e42  mov     rcx, rbx
0x140027e45  call    ?Gettext@IXMLDOMNode@MSXML@@QEAA?AV_bstr_t@@XZ; MSXML::IXMLDOMNode::Gettext(void)
0x140027e4a  nop
0x140027e4b  mov     rax, [rbp+arg_10]
0x140027e4f  test    rax, rax
0x140027e52  jz      short loc_140027E6C
0x140027e54  mov     rdx, [rax]
0x140027e57  test    rdx, rdx
0x140027e5a  jz      short loc_140027E6F
0x140027e5c  or      r8, 0FFFFFFFFFFFFFFFFh
0x140027e60  inc     r8
0x140027e63  cmp     [rdx+r8*2], si
0x140027e68  jnz     short loc_140027E60
0x140027e6a  jmp     short loc_140027E72
0x140027e6c  mov     rdx, rsi
0x140027e6f  mov     r8d, esi
0x140027e72  mov     rcx, rdi
0x140027e75  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x140027e7a  mov     rcx, [rdi]; Str
0x140027e7d  cmp     [rcx-10h], esi
0x140027e80  jle     short loc_140027EAC
0x140027e82  mov     edx, 3Ah ; ':'; Ch
0x140027e87  call    cs:__imp_wcschr
0x140027e8d  nop
0x140027e8e  test    rax, rax
0x140027e91  jz      short loc_140027EAC
0x140027e93  sub     rax, [rdi]
0x140027e96  sar     rax, 1
0x140027e99  test    eax, eax
0x140027e9b  jle     short loc_140027EAC
0x140027e9d  lea     r8d, [rax+1]
0x140027ea1  xor     edx, edx
0x140027ea3  mov     rcx, rdi
0x140027ea6  call    ?Delete@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHHH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Delete(int,int)
0x140027eab  nop
0x140027eac  lea     rcx, [rbp+arg_10]; this
0x140027eb0  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x140027eb5  nop
0x140027eb6  test    rbx, rbx
0x140027eb9  jz      short loc_140027ECB
0x140027ebb  mov     rax, [rbx]
0x140027ebe  mov     rcx, rbx
0x140027ec1  mov     rax, [rax+10h]
0x140027ec5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027eca  nop
0x140027ecb  mov     rcx, [rbp+arg_18]
0x140027ecf  test    rcx, rcx
0x140027ed2  jz      short loc_140027EE1
0x140027ed4  mov     rax, [rcx]
0x140027ed7  mov     rax, [rax+10h]
0x140027edb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027ee0  nop
0x140027ee1  mov     rax, rdi
0x140027ee4  mov     rbx, [rsp+40h+arg_0]
0x140027ee9  add     rsp, 40h
0x140027eed  pop     rdi
0x140027eee  pop     rsi
0x140027eef  pop     rbp
0x140027ef0  retn
0x140027ef1  mov     ecx, 80004003h; int
0x140027ef6  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
