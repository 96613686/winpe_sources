# WSTrustResponse::ExtractErrorMessage(void)

- ea: `0x140027410`
- end: `0x14002752b`
- name: `?ExtractErrorMessage@WSTrustResponse@@AEBA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ`
- size: `283`
- prototype: `_QWORD *__fastcall(const unsigned __int16 **, _QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140026f30`

## callees

- `0x1400061dc`
- `0x140018d0c`
- `0x1400193b4`
- `0x140019a5c`
- `0x14001c244`
- `0x140027410`
- `0x140028040`
- `0x14002c070`
- `0x140030010`

## string_xrefs

- `0x140027454`: `xmlns:S='http://www.w3.org/2003/05/soap-envelope' `

## pseudocode

```c
_QWORD *__fastcall WSTrustResponse::ExtractErrorMessage(const unsigned __int16 **a1, _QWORD *a2)
{
  struct IUnknown *v4; // rbx
  __int64 v5; // rbx
  __int64 v6; // rdx
  __int64 v7; // r8
  _BYTE v9[8]; // [rsp+28h] [rbp-18h] BYREF
  __int64 v10; // [rsp+30h] [rbp-10h]
  __int64 *v11; // [rsp+70h] [rbp+30h] BYREF
  struct IUnknown *v12; // [rsp+78h] [rbp+38h] BYREF

  *a2 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  MSXML::Create(&v12, *a1, L"xmlns:S='http://www.w3.org/2003/05/soap-envelope' ");
  v4 = v12;
  if ( !v12 )
    _com_issue_error(-2147467261);
  _bstr_t::_bstr_t((_bstr_t *)v9, L"S:Envelope/S:Body/S:Fault/S:Reason");
  MSXML::IXMLDOMNode::selectSingleNode(v4);
  v5 = v10;
  if ( v10 )
  {
    MSXML::IXMLDOMNode::Gettext(v10, &v11);
    if ( v11 )
    {
      v6 = *v11;
      if ( *v11 )
      {
        v7 = -1;
        do
          ++v7;
        while ( *(_WORD *)(v6 + 2 * v7) );
        goto LABEL_10;
      }
    }
    else
    {
      v6 = 0;
    }
    v7 = 0;
LABEL_10:
    ATL::CSimpleStringT<unsigned short,0>::SetString(a2, v6, v7);
    _bstr_t::~_bstr_t((_bstr_t *)&v11);
  }
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  if ( v12 )
    ((void (__fastcall *)(struct IUnknown *))v12->lpVtbl->Release)(v12);
  return a2;
}

```

## disassembly

```asm
0x140027410  mov     [rsp-18h+arg_0], rbx
0x140027415  mov     [rsp-18h+arg_8], rdx
0x14002741a  push    rbp
0x14002741b  push    rsi
0x14002741c  push    rdi
0x14002741d  mov     rbp, rsp
0x140027420  sub     rsp, 40h
0x140027424  mov     rdi, rdx
0x140027427  mov     rbx, rcx
0x14002742a  xor     esi, esi
0x14002742c  mov     [rbp+var_20], esi
0x14002742f  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140027436  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14002743d  mov     rax, [rax+18h]
0x140027441  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027446  add     rax, 18h
0x14002744a  mov     [rdi], rax
0x14002744d  mov     [rbp+var_20], 1
0x140027454  lea     r8, aXmlnsSHttpWwwW_0; "xmlns:S='http://www.w3.org/2003/05/soap"...
0x14002745b  mov     rdx, [rbx]
0x14002745e  lea     rcx, [rbp+arg_18]
0x140027462  call    ?Create@MSXML@@YA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@PEBG0@Z; MSXML::Create(ushort const *,ushort const *)
0x140027467  nop
0x140027468  mov     rbx, [rbp+arg_18]
0x14002746c  test    rbx, rbx
0x14002746f  jz      loc_140027520
0x140027475  lea     rdx, aSEnvelopeSBody; "S:Envelope/S:Body/S:Fault/S:Reason"
0x14002747c  lea     rcx, [rbp+var_18]; this
0x140027480  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x140027485  mov     r8, rax
0x140027488  lea     rdx, [rbp+var_10]
0x14002748c  mov     rcx, rbx; struct IUnknown *
0x14002748f  call    ?selectSingleNode@IXMLDOMNode@MSXML@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML::IXMLDOMNode::selectSingleNode(_bstr_t)
0x140027494  nop
0x140027495  mov     rbx, [rbp+var_10]
0x140027499  test    rbx, rbx
0x14002749c  jz      short loc_1400274E5
0x14002749e  lea     rdx, [rbp+arg_10]
0x1400274a2  mov     rcx, rbx
0x1400274a5  call    ?Gettext@IXMLDOMNode@MSXML@@QEAA?AV_bstr_t@@XZ; MSXML::IXMLDOMNode::Gettext(void)
0x1400274aa  nop
0x1400274ab  mov     rax, [rbp+arg_10]
0x1400274af  test    rax, rax
0x1400274b2  jz      short loc_1400274CC
0x1400274b4  mov     rdx, [rax]
0x1400274b7  test    rdx, rdx
0x1400274ba  jz      short loc_1400274CF
0x1400274bc  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400274c0  inc     r8
0x1400274c3  cmp     [rdx+r8*2], si
0x1400274c8  jnz     short loc_1400274C0
0x1400274ca  jmp     short loc_1400274D2
0x1400274cc  mov     rdx, rsi
0x1400274cf  mov     r8d, esi
0x1400274d2  mov     rcx, rdi
0x1400274d5  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1400274da  nop
0x1400274db  lea     rcx, [rbp+arg_10]; this
0x1400274df  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1400274e4  nop
0x1400274e5  test    rbx, rbx
0x1400274e8  jz      short loc_1400274FA
0x1400274ea  mov     rax, [rbx]
0x1400274ed  mov     rcx, rbx
0x1400274f0  mov     rax, [rax+10h]
0x1400274f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400274f9  nop
0x1400274fa  mov     rcx, [rbp+arg_18]
0x1400274fe  test    rcx, rcx
0x140027501  jz      short loc_140027510
0x140027503  mov     rax, [rcx]
0x140027506  mov     rax, [rax+10h]
0x14002750a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002750f  nop
0x140027510  mov     rax, rdi
0x140027513  mov     rbx, [rsp+40h+arg_0]
0x140027518  add     rsp, 40h
0x14002751c  pop     rdi
0x14002751d  pop     rsi
0x14002751e  pop     rbp
0x14002751f  retn
0x140027520  mov     ecx, 80004003h; int
0x140027525  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
