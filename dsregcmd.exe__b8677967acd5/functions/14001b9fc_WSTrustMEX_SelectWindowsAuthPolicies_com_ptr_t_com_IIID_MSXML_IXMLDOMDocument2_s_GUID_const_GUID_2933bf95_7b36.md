# WSTrustMEX::SelectWindowsAuthPolicies(_com_ptr_t<_com_IIID<MSXML::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> const &,ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,WSTrustMEX::PolicyInfo,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<WSTrustMEX::PolicyInfo>> &)

- ea: `0x14001b9fc`
- end: `0x14001bd52`
- name: `?SelectWindowsAuthPolicies@WSTrustMEX@@AEAAXAEBV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAV?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UPolicyInfo@WSTrustMEX@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@UPolicyInfo@WSTrustMEX@@@2@@ATL@@@Z`
- size: `854`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001a28c`

## callees

- `0x140005c58`
- `0x140007bf8`
- `0x140008c34`
- `0x14000f6b0`
- `0x140018d0c`
- `0x14001943c`
- `0x1400196f4`
- `0x140019cb4`
- `0x14001b9fc`
- `0x14001c1b8`
- `0x14002c070`
- `0x14002c084`
- `0x140030010`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall WSTrustMEX::SelectWindowsAuthPolicies(__int64 a1, struct IUnknown **a2, __int64 a3)
{
  struct IUnknown *v4; // rbx
  struct IUnknown *v5; // rdi
  int v6; // eax
  unsigned int v7; // r12d
  int i; // r13d
  int v9; // eax
  struct IUnknown *v10; // rbx
  int v11; // eax
  struct IUnknown *v12; // rsi
  int v13; // eax
  struct IUnknown *v14; // r14
  int v15; // eax
  _DWORD *v16; // rax
  unsigned __int16 *v17; // rsi
  unsigned __int16 *Node; // rax
  const char *v19; // r8
  _QWORD *v20; // rsi
  _QWORD *v21; // rdx
  _DWORD *v23; // [rsp+30h] [rbp-40h] BYREF
  struct IUnknown *v24; // [rsp+38h] [rbp-38h] BYREF
  _BYTE v25[8]; // [rsp+40h] [rbp-30h] BYREF
  struct IUnknown *v26; // [rsp+48h] [rbp-28h]
  struct IUnknown *v27; // [rsp+50h] [rbp-20h] BYREF
  unsigned __int16 *v28; // [rsp+58h] [rbp-18h] BYREF
  _QWORD v29[2]; // [rsp+60h] [rbp-10h] BYREF
  struct IUnknown *v31; // [rsp+B8h] [rbp+48h] BYREF
  struct IUnknown *v32; // [rsp+C8h] [rbp+58h] BYREF

  v4 = *a2;
  if ( !*a2 )
    _com_issue_error(-2147467261);
  _bstr_t::_bstr_t((_bstr_t *)v25, L"wsdl:definitions/wsp:Policy/wsp:ExactlyOne/wsp:All/http:NegotiateAuthentication");
  MSXML::IXMLDOMNode::selectNodes(v4);
  v5 = v26;
  if ( !v26 )
    _com_issue_error(-2147467261);
  LODWORD(v31) = 0;
  v6 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v26->lpVtbl[2].Release)(v26, &v31);
  if ( v6 < 0 )
    _com_issue_errorex(v6, v5, &GUID_2933bf82_7b36_11d2_b20e_00c04f983e60);
  v7 = 0;
  for ( i = (int)v31; (int)v7 < i; ++v7 )
  {
    v31 = 0;
    v9 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, struct IUnknown **))v5->lpVtbl[2].AddRef)(v5, v7, &v31);
    if ( v9 < 0 )
      _com_issue_errorex(v9, v5, &GUID_2933bf82_7b36_11d2_b20e_00c04f983e60);
    v10 = v31;
    v29[1] = v31;
    if ( !v31 )
      _com_issue_error(-2147467261);
    v31 = 0;
    v11 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v10->lpVtbl[3].Release)(v10, &v31);
    if ( v11 < 0 )
      _com_issue_errorex(v11, v10, &GUID_2933bf80_7b36_11d2_b20e_00c04f983e60);
    v12 = v31;
    v32 = v31;
    if ( !v31 )
      _com_issue_error(-2147467261);
    v31 = 0;
    v13 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v12->lpVtbl[3].Release)(v12, &v31);
    if ( v13 < 0 )
      _com_issue_errorex(v13, v12, &GUID_2933bf80_7b36_11d2_b20e_00c04f983e60);
    v14 = v31;
    if ( !v31 )
      _com_issue_error(-2147467261);
    v24 = 0;
    v15 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v31->lpVtbl[3].Release)(v31, &v24);
    if ( v15 < 0 )
      _com_issue_errorex(v15, v14, &GUID_2933bf80_7b36_11d2_b20e_00c04f983e60);
    v27 = v24;
    ((void (__fastcall *)(struct IUnknown *))v14->lpVtbl->Release)(v14);
    ((void (__fastcall *)(struct IUnknown *))v12->lpVtbl->Release)(v12);
    WSTrustMEX::CheckPolicy(a1, (void **)&v23, &v27);
    v16 = v23;
    if ( *(v23 - 4) )
    {
      v17 = *(unsigned __int16 **)ATL::operator+(v29, L"#", &v23);
      LODWORD(v32) = 0;
      LODWORD(v31) = 0;
      v28 = 0;
      Node = ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,TokenCache::Item,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<TokenCache::Item>>::GetNode(
               (__int64 *)a3,
               v17,
               &v32,
               (unsigned int *)&v31,
               &v28);
      if ( !Node )
      {
        if ( !*(_QWORD *)a3 )
        {
          LOBYTE(v19) = 1;
          if ( !ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,WSTrustMEX::PolicyInfo,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<WSTrustMEX::PolicyInfo>>::InitHashTable(
                  (void **)a3,
                  *(_DWORD *)(a3 + 16),
                  v19) )
            ATL::AtlThrowImpl(0x8007000E);
        }
        Node = (unsigned __int16 *)ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,WSTrustMEX::PolicyInfo,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<WSTrustMEX::PolicyInfo>>::NewNode(
                                     a3,
                                     v17,
                                     (unsigned int)v32,
                                     (unsigned int)v31);
      }
      v20 = Node + 4;
      v21 = (_QWORD *)(v29[0] - 24LL);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v29[0] - 24LL + 16), 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v21 + 8LL))(*v21);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
        v20,
        &v23);
      v20[2] = 1;
      v16 = v23;
    }
    if ( _InterlockedExchangeAdd(v16 - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v16 - 3) + 8LL))(*((_QWORD *)v16 - 3));
    if ( v24 )
      ((void (__fastcall *)(struct IUnknown *))v24->lpVtbl->Release)(v24);
    ((void (__fastcall *)(struct IUnknown *))v10->lpVtbl->Release)(v10);
  }
  return ((__int64 (__fastcall *)(struct IUnknown *))v5->lpVtbl->Release)(v5);
}

```

## disassembly

```asm
0x14001b9fc  mov     [rsp-38h+arg_10], rbx
0x14001ba01  mov     [rsp-38h+arg_0], rcx
0x14001ba06  push    rbp
0x14001ba07  push    rsi
0x14001ba08  push    rdi
0x14001ba09  push    r12
0x14001ba0b  push    r13
0x14001ba0d  push    r14
0x14001ba0f  push    r15
0x14001ba11  mov     rbp, rsp
0x14001ba14  sub     rsp, 70h
0x14001ba18  mov     r15, r8
0x14001ba1b  xor     r14d, r14d
0x14001ba1e  mov     rbx, [rdx]
0x14001ba21  test    rbx, rbx
0x14001ba24  jz      loc_14001BCC1
0x14001ba2a  lea     rdx, aWsdlDefinition_0; "wsdl:definitions/wsp:Policy/wsp:Exactly"...
0x14001ba31  lea     rcx, [rbp+var_30]; this
0x14001ba35  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14001ba3a  mov     r8, rax
0x14001ba3d  lea     rdx, [rbp+var_28]
0x14001ba41  mov     rcx, rbx; struct IUnknown *
0x14001ba44  call    ?selectNodes@IXMLDOMNode@MSXML@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNodeList@MSXML@@$1?_GUID_2933bf82_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML::IXMLDOMNode::selectNodes(_bstr_t)
0x14001ba49  nop
0x14001ba4a  mov     rdi, [rbp+var_28]
0x14001ba4e  test    rdi, rdi
0x14001ba51  jz      loc_14001BCB6
0x14001ba57  mov     dword ptr [rbp+arg_8], r14d
0x14001ba5b  mov     rax, [rdi]
0x14001ba5e  lea     rdx, [rbp+arg_8]
0x14001ba62  mov     rcx, rdi
0x14001ba65  mov     rax, [rax+40h]
0x14001ba69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ba6e  test    eax, eax
0x14001ba70  js      loc_14001BCCC
0x14001ba76  mov     r12d, r14d
0x14001ba79  mov     r13d, dword ptr [rbp+arg_8]
0x14001ba7d  test    r13d, r13d
0x14001ba80  jle     loc_14001BC8E
0x14001ba86  mov     [rbp+arg_8], r14
0x14001ba8a  mov     rax, [rdi]
0x14001ba8d  lea     r8, [rbp+arg_8]
0x14001ba91  mov     edx, r12d
0x14001ba94  mov     rcx, rdi
0x14001ba97  mov     rax, [rax+38h]
0x14001ba9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001baa0  test    eax, eax
0x14001baa2  js      loc_14001BD40
0x14001baa8  mov     rbx, [rbp+arg_8]
0x14001baac  mov     [rbp+var_8], rbx
0x14001bab0  test    rbx, rbx
0x14001bab3  jz      loc_14001BD35
0x14001bab9  mov     [rbp+arg_8], r14
0x14001babd  mov     rax, [rbx]
0x14001bac0  lea     rdx, [rbp+arg_8]
0x14001bac4  mov     rcx, rbx
0x14001bac7  mov     rax, [rax+58h]
0x14001bacb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001bad0  test    eax, eax
0x14001bad2  js      loc_14001BD23
0x14001bad8  mov     rsi, [rbp+arg_8]
0x14001badc  mov     [rbp+arg_18], rsi
0x14001bae0  test    rsi, rsi
0x14001bae3  jz      loc_14001BD18
0x14001bae9  mov     [rbp+arg_8], r14
0x14001baed  mov     rax, [rsi]
0x14001baf0  lea     rdx, [rbp+arg_8]
0x14001baf4  mov     rcx, rsi
0x14001baf7  mov     rax, [rax+58h]
0x14001bafb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001bb00  test    eax, eax
0x14001bb02  js      loc_14001BD06
0x14001bb08  mov     r14, [rbp+arg_8]
0x14001bb0c  mov     [rbp+arg_8], r14
0x14001bb10  test    r14, r14
0x14001bb13  jz      loc_14001BCFB
0x14001bb19  mov     [rbp+var_38], 0
0x14001bb21  mov     rax, [r14]
0x14001bb24  lea     rdx, [rbp+var_38]
0x14001bb28  mov     rcx, r14
0x14001bb2b  mov     rax, [rax+58h]
0x14001bb2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001bb34  test    eax, eax
0x14001bb36  js      loc_14001BCE9
0x14001bb3c  mov     rax, [rbp+var_38]
0x14001bb40  mov     [rbp+var_20], rax
0x14001bb44  mov     rax, [r14]
0x14001bb47  mov     rcx, r14
0x14001bb4a  mov     rax, [rax+10h]
0x14001bb4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001bb53  nop
0x14001bb54  mov     rax, [rsi]
0x14001bb57  mov     rcx, rsi
0x14001bb5a  mov     rax, [rax+10h]
0x14001bb5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001bb63  nop
0x14001bb64  lea     r8, [rbp+var_20]
0x14001bb68  lea     rdx, [rbp+var_40]
0x14001bb6c  mov     rcx, [rbp+arg_0]
0x14001bb70  call    ?CheckPolicy@WSTrustMEX@@AEAA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z; WSTrustMEX::CheckPolicy(_com_ptr_t<_com_IIID<MSXML::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> const &)
0x14001bb75  nop
0x14001bb76  mov     rax, [rbp+var_40]
0x14001bb7a  xor     r14d, r14d
0x14001bb7d  cmp     [rax-10h], r14d
0x14001bb81  jz      loc_14001BC3B
0x14001bb87  lea     r8, [rbp+var_40]
0x14001bb8b  lea     rdx, asc_140037470; "#"
0x14001bb92  lea     rcx, [rbp+var_10]
0x14001bb96  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@PEBGAEBV10@@Z; ATL::operator+(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14001bb9b  nop
0x14001bb9c  mov     rsi, [rax]
0x14001bb9f  mov     dword ptr [rbp+arg_18], r14d
0x14001bba3  mov     dword ptr [rbp+arg_8], r14d
0x14001bba7  mov     [rbp+var_18], r14
0x14001bbab  lea     rax, [rbp+var_18]
0x14001bbaf  mov     [rsp+70h+var_50], rax
0x14001bbb4  lea     r9, [rbp+arg_8]
0x14001bbb8  lea     r8, [rbp+arg_18]
0x14001bbbc  mov     rdx, rsi
0x14001bbbf  mov     rcx, r15
0x14001bbc2  call    ?GetNode@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VItem@TokenCache@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@VItem@TokenCache@@@2@@ATL@@AEBAPEAVCNode@12@PEBGAEAI1AEAPEAV312@@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,TokenCache::Item,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<TokenCache::Item>>::GetNode(ushort const *,uint &,uint &,ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,TokenCache::Item,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<TokenCache::Item>>::CNode * &)
0x14001bbc7  test    rax, rax
0x14001bbca  jnz     short loc_14001BBFB
0x14001bbcc  cmp     [r15], r14
0x14001bbcf  jnz     short loc_14001BBE8
0x14001bbd1  mov     r8b, 1
0x14001bbd4  mov     edx, [r15+10h]
0x14001bbd8  mov     rcx, r15
0x14001bbdb  call    ?InitHashTable@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UPolicyInfo@WSTrustMEX@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@UPolicyInfo@WSTrustMEX@@@2@@ATL@@QEAA_NI_N@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,WSTrustMEX::PolicyInfo,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<WSTrustMEX::PolicyInfo>>::InitHashTable(uint,bool)
0x14001bbe0  test    al, al
0x14001bbe2  jz      loc_14001BCDE
0x14001bbe8  mov     r9d, dword ptr [rbp+arg_8]
0x14001bbec  mov     r8d, dword ptr [rbp+arg_18]
0x14001bbf0  mov     rdx, rsi
0x14001bbf3  mov     rcx, r15
0x14001bbf6  call    ?NewNode@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UPolicyInfo@WSTrustMEX@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@UPolicyInfo@WSTrustMEX@@@2@@ATL@@AEAAPEAVCNode@12@PEBGII@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,WSTrustMEX::PolicyInfo,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<WSTrustMEX::PolicyInfo>>::NewNode(ushort const *,uint,uint)
0x14001bbfb  lea     rsi, [rax+8]
0x14001bbff  mov     rdx, [rbp+var_10]
0x14001bc03  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001bc07  or      eax, 0FFFFFFFFh
0x14001bc0a  lock xadd [rdx+10h], eax
0x14001bc0f  sub     eax, 1
0x14001bc12  jg      short loc_14001BC23
0x14001bc14  mov     rcx, [rdx]
0x14001bc17  mov     rax, [rcx]
0x14001bc1a  mov     rax, [rax+8]
0x14001bc1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001bc23  lea     rdx, [rbp+var_40]
0x14001bc27  mov     rcx, rsi
0x14001bc2a  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14001bc2f  mov     qword ptr [rsi+10h], 1
0x14001bc37  mov     rax, [rbp+var_40]
0x14001bc3b  lea     rdx, [rax-18h]
0x14001bc3f  or      eax, 0FFFFFFFFh
0x14001bc42  lock xadd [rdx+10h], eax
0x14001bc47  sub     eax, 1
0x14001bc4a  jg      short loc_14001BC5C
0x14001bc4c  mov     rcx, [rdx]
0x14001bc4f  mov     rax, [rcx]
0x14001bc52  mov     rax, [rax+8]
0x14001bc56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001bc5b  nop
0x14001bc5c  mov     rcx, [rbp+var_38]
0x14001bc60  test    rcx, rcx
0x14001bc63  jz      short loc_14001BC72
0x14001bc65  mov     rax, [rcx]
0x14001bc68  mov     rax, [rax+10h]
0x14001bc6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001bc71  nop
0x14001bc72  mov     rax, [rbx]
0x14001bc75  mov     rcx, rbx
0x14001bc78  mov     rax, [rax+10h]
0x14001bc7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001bc81  nop
0x14001bc82  inc     r12d
0x14001bc85  cmp     r12d, r13d
0x14001bc88  jl      loc_14001BA86
0x14001bc8e  mov     rax, [rdi]
0x14001bc91  mov     rcx, rdi
0x14001bc94  mov     rax, [rax+10h]
0x14001bc98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001bc9d  nop
0x14001bc9e  mov     rbx, [rsp+70h+arg_10]
0x14001bca6  add     rsp, 70h
0x14001bcaa  pop     r15
0x14001bcac  pop     r14
0x14001bcae  pop     r13
0x14001bcb0  pop     r12
0x14001bcb2  pop     rdi
0x14001bcb3  pop     rsi
0x14001bcb4  pop     rbp
0x14001bcb5  retn
0x14001bcb6  mov     ecx, 80004003h; int
0x14001bcbb  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x14001bcc1  mov     ecx, 80004003h; int
0x14001bcc6  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x14001bccc  lea     r8, _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60; struct _GUID *
0x14001bcd3  mov     rdx, rdi; struct IUnknown *
0x14001bcd6  mov     ecx, eax; int
0x14001bcd8  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x14001bcde  mov     ecx, 8007000Eh; unsigned int
0x14001bce3  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14001bce9  lea     r8, _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60; struct _GUID *
0x14001bcf0  mov     rdx, r14; struct IUnknown *
0x14001bcf3  mov     ecx, eax; int
0x14001bcf5  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x14001bcfb  mov     ecx, 80004003h; int
0x14001bd00  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x14001bd06  lea     r8, _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60; struct _GUID *
0x14001bd0d  mov     rdx, rsi; struct IUnknown *
0x14001bd10  mov     ecx, eax; int
0x14001bd12  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x14001bd18  mov     ecx, 80004003h; int
0x14001bd1d  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x14001bd23  lea     r8, _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60; struct _GUID *
0x14001bd2a  mov     rdx, rbx; struct IUnknown *
0x14001bd2d  mov     ecx, eax; int
0x14001bd2f  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x14001bd35  mov     ecx, 80004003h; int
0x14001bd3a  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x14001bd40  lea     r8, _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60; struct _GUID *
0x14001bd47  mov     rdx, rdi; struct IUnknown *
0x14001bd4a  mov     ecx, eax; int
0x14001bd4c  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
```
