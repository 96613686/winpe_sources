# WSTrustMEX::ProcessPolicyNodes(_com_ptr_t<_com_IIID<MSXML::IXMLDOMNodeList,&__s_GUID const _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60>>,ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,WSTrustMEX::PolicyInfo,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<WSTrustMEX::PolicyInfo>> &)

- ea: `0x14001b3f0`
- end: `0x14001b8cd`
- name: `?ProcessPolicyNodes@WSTrustMEX@@AEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNodeList@MSXML@@$1?_GUID_2933bf82_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAV?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UPolicyInfo@WSTrustMEX@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@UPolicyInfo@WSTrustMEX@@@2@@ATL@@@Z`
- size: `1245`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001a28c`

## callees

- `0x140005c58`
- `0x140007bf8`
- `0x140008c34`
- `0x14000f6b0`
- `0x14001943c`
- `0x1400196f4`
- `0x140019cb4`
- `0x14001b3f0`
- `0x14002c070`
- `0x14002c084`
- `0x140030010`

## pseudocode

```c
// Hidden C++ exception states: #wind=33
__int64 __fastcall WSTrustMEX::ProcessPolicyNodes(__int64 a1, struct IUnknown **a2, __int64 a3)
{
  __int64 result; // rax
  struct IUnknown **v4; // rdi
  struct IUnknown *v5; // rbx
  int v6; // eax
  unsigned int v7; // ecx
  struct IUnknown *v8; // rbx
  int v9; // eax
  struct IUnknown *v10; // rbx
  int v11; // eax
  struct IUnknown *v12; // rdi
  int v13; // eax
  struct IUnknown *v14; // r14
  int v15; // eax
  struct IUnknown *v16; // rsi
  int v17; // eax
  struct IUnknown *v18; // r15
  int v19; // eax
  struct IUnknown *v20; // r13
  int v21; // eax
  struct IUnknown *v22; // r12
  int v23; // eax
  struct IUnknown *v24; // r12
  _DWORD *v25; // rax
  unsigned __int16 *v26; // rdi
  unsigned __int16 *Node; // rax
  const char *v28; // r8
  _QWORD *v29; // rdi
  _QWORD *v30; // rdx
  unsigned int v31; // [rsp+38h] [rbp-49h]
  _DWORD *v32; // [rsp+40h] [rbp-41h] BYREF
  struct IUnknown *v33; // [rsp+48h] [rbp-39h] BYREF
  struct IUnknown *v34; // [rsp+50h] [rbp-31h] BYREF
  int i; // [rsp+58h] [rbp-29h]
  struct IUnknown *v36; // [rsp+60h] [rbp-21h] BYREF
  struct IUnknown *v37; // [rsp+68h] [rbp-19h] BYREF
  _QWORD v38[13]; // [rsp+70h] [rbp-11h] BYREF
  _UNKNOWN *retaddr; // [rsp+E0h] [rbp+5Fh] BYREF
  struct IUnknown *v43; // [rsp+100h] [rbp+7Fh] BYREF

  result = (__int64)&retaddr;
  v4 = a2;
  v5 = *a2;
  if ( *a2 )
  {
    LODWORD(v43) = 0;
    v6 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v5->lpVtbl[2].Release)(v5, &v43);
    if ( v6 < 0 )
      _com_issue_errorex(v6, v5, &GUID_2933bf82_7b36_11d2_b20e_00c04f983e60);
    v7 = 0;
    v31 = 0;
    result = (unsigned int)v43;
    for ( i = (int)v43; (int)v7 < i; v4 = a2 )
    {
      v8 = *v4;
      if ( !*v4 )
        _com_issue_error(-2147467261);
      v43 = 0;
      v9 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, struct IUnknown **))v8->lpVtbl[2].AddRef)(v8, v7, &v43);
      if ( v9 < 0 )
        _com_issue_errorex(v9, v8, &GUID_2933bf82_7b36_11d2_b20e_00c04f983e60);
      v10 = v43;
      v38[1] = v43;
      if ( !v43 )
        _com_issue_error(-2147467261);
      v43 = 0;
      v11 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v10->lpVtbl[3].Release)(v10, &v43);
      if ( v11 < 0 )
        _com_issue_errorex(v11, v10, &GUID_2933bf80_7b36_11d2_b20e_00c04f983e60);
      v12 = v43;
      v37 = v43;
      if ( !v43 )
        _com_issue_error(-2147467261);
      v43 = 0;
      v13 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v12->lpVtbl[3].Release)(v12, &v43);
      if ( v13 < 0 )
        _com_issue_errorex(v13, v12, &GUID_2933bf80_7b36_11d2_b20e_00c04f983e60);
      v14 = v43;
      v34 = v43;
      if ( !v43 )
        _com_issue_error(-2147467261);
      v43 = 0;
      v15 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v14->lpVtbl[3].Release)(v14, &v43);
      if ( v15 < 0 )
        _com_issue_errorex(v15, v14, &GUID_2933bf80_7b36_11d2_b20e_00c04f983e60);
      v16 = v43;
      v38[2] = v43;
      if ( !v43 )
        _com_issue_error(-2147467261);
      v43 = 0;
      v17 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v16->lpVtbl[3].Release)(v16, &v43);
      if ( v17 < 0 )
        _com_issue_errorex(v17, v16, &GUID_2933bf80_7b36_11d2_b20e_00c04f983e60);
      v18 = v43;
      v38[3] = v43;
      if ( !v43 )
        _com_issue_error(-2147467261);
      v43 = 0;
      v19 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v18->lpVtbl[3].Release)(v18, &v43);
      if ( v19 < 0 )
        _com_issue_errorex(v19, v18, &GUID_2933bf80_7b36_11d2_b20e_00c04f983e60);
      v20 = v43;
      v38[4] = v43;
      if ( !v43 )
        _com_issue_error(-2147467261);
      v43 = 0;
      v21 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v20->lpVtbl[3].Release)(v20, &v43);
      if ( v21 < 0 )
        _com_issue_errorex(v21, v20, &GUID_2933bf80_7b36_11d2_b20e_00c04f983e60);
      v22 = v43;
      v36 = v43;
      if ( !v43 )
        _com_issue_error(-2147467261);
      v33 = 0;
      v23 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v43->lpVtbl[3].Release)(v43, &v33);
      if ( v23 < 0 )
        _com_issue_errorex(v23, v22, &GUID_2933bf80_7b36_11d2_b20e_00c04f983e60);
      v24 = v33;
      v36 = v33;
      ((void (__fastcall *)(struct IUnknown *))v43->lpVtbl->Release)(v43);
      ((void (__fastcall *)(struct IUnknown *))v20->lpVtbl->Release)(v20);
      if ( v18 )
        ((void (__fastcall *)(struct IUnknown *))v18->lpVtbl->Release)(v18);
      if ( v16 )
        ((void (__fastcall *)(struct IUnknown *))v16->lpVtbl->Release)(v16);
      if ( v14 )
        ((void (__fastcall *)(struct IUnknown *))v14->lpVtbl->Release)(v14);
      if ( v12 )
        ((void (__fastcall *)(struct IUnknown *))v12->lpVtbl->Release)(v12);
      if ( v24 )
      {
        WSTrustMEX::CheckPolicy(a1, (void **)&v32, &v36);
        v25 = v32;
        if ( *(v32 - 4) )
        {
          v26 = *(unsigned __int16 **)ATL::operator+(v38, L"#", &v32);
          LODWORD(v34) = 0;
          LODWORD(v43) = 0;
          v37 = 0;
          Node = ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,TokenCache::Item,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<TokenCache::Item>>::GetNode(
                   (__int64 *)a3,
                   v26,
                   &v34,
                   (unsigned int *)&v43,
                   (unsigned __int16 **)&v37);
          if ( !Node )
          {
            if ( !*(_QWORD *)a3 )
            {
              LOBYTE(v28) = 1;
              if ( !ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,WSTrustMEX::PolicyInfo,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<WSTrustMEX::PolicyInfo>>::InitHashTable(
                      (void **)a3,
                      *(_DWORD *)(a3 + 16),
                      v28) )
                ATL::AtlThrowImpl(0x8007000E);
            }
            Node = (unsigned __int16 *)ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,WSTrustMEX::PolicyInfo,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<WSTrustMEX::PolicyInfo>>::NewNode(
                                         a3,
                                         v26,
                                         (unsigned int)v34,
                                         (unsigned int)v43);
          }
          v29 = Node + 4;
          v30 = (_QWORD *)(v38[0] - 24LL);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v38[0] - 24LL + 16), 0xFFFFFFFF) <= 1 )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v30 + 8LL))(*v30);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
            v29,
            &v32);
          v29[2] = 0;
          v25 = v32;
        }
        if ( _InterlockedExchangeAdd(v25 - 2, 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v25 - 3) + 8LL))(*((_QWORD *)v25 - 3));
        v24 = v33;
      }
      if ( v24 )
        ((void (__fastcall *)(struct IUnknown *))v24->lpVtbl->Release)(v24);
      result = ((__int64 (__fastcall *)(struct IUnknown *))v10->lpVtbl->Release)(v10);
      v7 = v31 + 1;
      v31 = v7;
    }
    if ( *v4 )
      return ((__int64 (__fastcall *)(struct IUnknown *))(*v4)->lpVtbl->Release)(*v4);
  }
  return result;
}

```

## disassembly

```asm
0x14001b3f0  mov     rax, rsp
0x14001b3f3  mov     [rax+18h], r8
0x14001b3f7  mov     [rax+10h], rdx
0x14001b3fb  mov     [rax+8], rcx
0x14001b3ff  push    rbp
0x14001b400  push    rbx
0x14001b401  push    rsi
0x14001b402  push    rdi
0x14001b403  push    r12
0x14001b405  push    r13
0x14001b407  push    r14
0x14001b409  push    r15
0x14001b40b  lea     rbp, [rax-5Fh]
0x14001b40f  sub     rsp, 98h
0x14001b416  mov     rdi, rdx
0x14001b419  xor     r13d, r13d
0x14001b41c  mov     rbx, [rdx]
0x14001b41f  test    rbx, rbx
0x14001b422  jnz     short loc_14001B429
0x14001b424  jmp     loc_14001B7B4
0x14001b429  mov     dword ptr [rbp+57h+arg_18], r13d
0x14001b42d  mov     rax, [rbx]
0x14001b430  lea     rdx, [rbp+57h+arg_18]
0x14001b434  mov     rcx, rbx
0x14001b437  mov     rax, [rax+40h]
0x14001b43b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b440  test    eax, eax
0x14001b442  js      loc_14001B7E5
0x14001b448  mov     ecx, r13d
0x14001b44b  mov     [rbp+57h+var_A0], ecx
0x14001b44e  mov     eax, dword ptr [rbp+57h+arg_18]
0x14001b451  mov     [rbp+57h+var_80], eax
0x14001b454  test    eax, eax
0x14001b456  jle     loc_14001B79F
0x14001b45c  mov     rbx, [rdi]
0x14001b45f  test    rbx, rbx
0x14001b462  jz      loc_14001B7DA
0x14001b468  mov     [rbp+57h+arg_18], r13
0x14001b46c  mov     rax, [rbx]
0x14001b46f  lea     r8, [rbp+57h+arg_18]
0x14001b473  mov     edx, ecx
0x14001b475  mov     rcx, rbx
0x14001b478  mov     rax, [rax+38h]
0x14001b47c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b481  test    eax, eax
0x14001b483  js      loc_14001B7C8
0x14001b489  mov     rbx, [rbp+57h+arg_18]
0x14001b48d  mov     [rbp+57h+var_60], rbx
0x14001b491  test    rbx, rbx
0x14001b494  jz      loc_14001B8C2
0x14001b49a  mov     [rbp+57h+arg_18], r13
0x14001b49e  mov     rax, [rbx]
0x14001b4a1  lea     rdx, [rbp+57h+arg_18]
0x14001b4a5  mov     rcx, rbx
0x14001b4a8  mov     rax, [rax+58h]
0x14001b4ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b4b1  test    eax, eax
0x14001b4b3  js      loc_14001B8B0
0x14001b4b9  mov     rdi, [rbp+57h+arg_18]
0x14001b4bd  mov     [rbp+57h+var_70], rdi
0x14001b4c1  test    rdi, rdi
0x14001b4c4  jz      loc_14001B8A5
0x14001b4ca  mov     [rbp+57h+arg_18], r13
0x14001b4ce  mov     rax, [rdi]
0x14001b4d1  lea     rdx, [rbp+57h+arg_18]
0x14001b4d5  mov     rcx, rdi
0x14001b4d8  mov     rax, [rax+58h]
0x14001b4dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b4e1  test    eax, eax
0x14001b4e3  js      loc_14001B893
0x14001b4e9  mov     r14, [rbp+57h+arg_18]
0x14001b4ed  mov     [rbp+57h+var_88], r14
0x14001b4f1  test    r14, r14
0x14001b4f4  jz      loc_14001B888
0x14001b4fa  mov     [rbp+57h+arg_18], r13
0x14001b4fe  mov     rax, [r14]
0x14001b501  lea     rdx, [rbp+57h+arg_18]
0x14001b505  mov     rcx, r14
0x14001b508  mov     rax, [rax+58h]
0x14001b50c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b511  test    eax, eax
0x14001b513  js      loc_14001B876
0x14001b519  mov     rsi, [rbp+57h+arg_18]
0x14001b51d  mov     [rbp+57h+var_58], rsi
0x14001b521  test    rsi, rsi
0x14001b524  jz      loc_14001B86B
0x14001b52a  mov     [rbp+57h+arg_18], r13
0x14001b52e  mov     rax, [rsi]
0x14001b531  lea     rdx, [rbp+57h+arg_18]
0x14001b535  mov     rcx, rsi
0x14001b538  mov     rax, [rax+58h]
0x14001b53c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b541  test    eax, eax
0x14001b543  js      loc_14001B859
0x14001b549  mov     r15, [rbp+57h+arg_18]
0x14001b54d  mov     [rbp+57h+var_50], r15
0x14001b551  test    r15, r15
0x14001b554  jz      loc_14001B84E
0x14001b55a  mov     [rbp+57h+arg_18], r13
0x14001b55e  mov     rax, [r15]
0x14001b561  lea     rdx, [rbp+57h+arg_18]
0x14001b565  mov     rcx, r15
0x14001b568  mov     rax, [rax+58h]
0x14001b56c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b571  test    eax, eax
0x14001b573  js      loc_14001B83C
0x14001b579  mov     r13, [rbp+57h+arg_18]
0x14001b57d  mov     [rbp+57h+var_48], r13
0x14001b581  test    r13, r13
0x14001b584  jz      loc_14001B831
0x14001b58a  mov     [rbp+57h+arg_18], 0
0x14001b592  mov     rax, [r13+0]
0x14001b596  lea     rdx, [rbp+57h+arg_18]
0x14001b59a  mov     rcx, r13
0x14001b59d  mov     rax, [rax+58h]
0x14001b5a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b5a6  test    eax, eax
0x14001b5a8  js      loc_14001B81F
0x14001b5ae  mov     r12, [rbp+57h+arg_18]
0x14001b5b2  mov     [rbp+57h+var_78], r12
0x14001b5b6  test    r12, r12
0x14001b5b9  jz      loc_14001B814
0x14001b5bf  mov     [rbp+57h+var_90], 0
0x14001b5c7  mov     rax, [r12]
0x14001b5cb  lea     rdx, [rbp+57h+var_90]
0x14001b5cf  mov     rcx, r12
0x14001b5d2  mov     rax, [rax+58h]
0x14001b5d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b5db  test    eax, eax
0x14001b5dd  js      loc_14001B802
0x14001b5e3  mov     r12, [rbp+57h+var_90]
0x14001b5e7  mov     [rbp+57h+var_78], r12
0x14001b5eb  mov     rcx, [rbp+57h+arg_18]
0x14001b5ef  mov     rax, [rcx]
0x14001b5f2  mov     rax, [rax+10h]
0x14001b5f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b5fb  nop
0x14001b5fc  mov     rax, [r13+0]
0x14001b600  mov     rcx, r13
0x14001b603  mov     rax, [rax+10h]
0x14001b607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b60c  nop
0x14001b60d  xor     r13d, r13d
0x14001b610  test    r15, r15
0x14001b613  jz      short loc_14001B625
0x14001b615  mov     rax, [r15]
0x14001b618  mov     rcx, r15
0x14001b61b  mov     rax, [rax+10h]
0x14001b61f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b624  nop
0x14001b625  test    rsi, rsi
0x14001b628  jz      short loc_14001B63A
0x14001b62a  mov     rax, [rsi]
0x14001b62d  mov     rcx, rsi
0x14001b630  mov     rax, [rax+10h]
0x14001b634  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b639  nop
0x14001b63a  test    r14, r14
0x14001b63d  jz      short loc_14001B64F
0x14001b63f  mov     rax, [r14]
0x14001b642  mov     rcx, r14
0x14001b645  mov     rax, [rax+10h]
0x14001b649  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b64e  nop
0x14001b64f  test    rdi, rdi
0x14001b652  jz      short loc_14001B664
0x14001b654  mov     rax, [rdi]
0x14001b657  mov     rcx, rdi
0x14001b65a  mov     rax, [rax+10h]
0x14001b65e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b663  nop
0x14001b664  test    r12, r12
0x14001b667  jz      loc_14001B764
0x14001b66d  lea     r8, [rbp+57h+var_78]
0x14001b671  lea     rdx, [rbp+57h+var_98]
0x14001b675  mov     rcx, [rbp+57h+arg_0]
0x14001b679  call    ?CheckPolicy@WSTrustMEX@@AEAA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z; WSTrustMEX::CheckPolicy(_com_ptr_t<_com_IIID<MSXML::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> const &)
0x14001b67e  nop
0x14001b67f  mov     rax, [rbp+57h+var_98]
0x14001b683  cmp     [rax-10h], r13d
0x14001b687  jz      loc_14001B740
0x14001b68d  lea     r8, [rbp+57h+var_98]
0x14001b691  lea     rdx, asc_140037470; "#"
0x14001b698  lea     rcx, [rbp+57h+var_68]
0x14001b69c  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@PEBGAEBV10@@Z; ATL::operator+(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14001b6a1  nop
0x14001b6a2  mov     rdi, [rax]
0x14001b6a5  mov     dword ptr [rbp+57h+var_88], r13d
0x14001b6a9  mov     dword ptr [rbp+57h+arg_18], r13d
0x14001b6ad  mov     [rbp+57h+var_70], r13
0x14001b6b1  lea     rax, [rbp+57h+var_70]
0x14001b6b5  mov     [rsp+20h], rax
0x14001b6ba  lea     r9, [rbp+57h+arg_18]
0x14001b6be  lea     r8, [rbp+57h+var_88]
0x14001b6c2  mov     rdx, rdi
0x14001b6c5  mov     rsi, [rbp+57h+arg_10]
0x14001b6c9  mov     rcx, rsi
0x14001b6cc  call    ?GetNode@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VItem@TokenCache@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@VItem@TokenCache@@@2@@ATL@@AEBAPEAVCNode@12@PEBGAEAI1AEAPEAV312@@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,TokenCache::Item,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<TokenCache::Item>>::GetNode(ushort const *,uint &,uint &,ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,TokenCache::Item,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<TokenCache::Item>>::CNode * &)
0x14001b6d1  test    rax, rax
0x14001b6d4  jnz     short loc_14001B704
0x14001b6d6  cmp     [rsi], r13
0x14001b6d9  jnz     short loc_14001B6F1
0x14001b6db  mov     r8b, 1
0x14001b6de  mov     edx, [rsi+10h]
0x14001b6e1  mov     rcx, rsi
0x14001b6e4  call    ?InitHashTable@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UPolicyInfo@WSTrustMEX@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@UPolicyInfo@WSTrustMEX@@@2@@ATL@@QEAA_NI_N@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,WSTrustMEX::PolicyInfo,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<WSTrustMEX::PolicyInfo>>::InitHashTable(uint,bool)
0x14001b6e9  test    al, al
0x14001b6eb  jz      loc_14001B7F7
0x14001b6f1  mov     r9d, dword ptr [rbp+57h+arg_18]
0x14001b6f5  mov     r8d, dword ptr [rbp+57h+var_88]
0x14001b6f9  mov     rdx, rdi
0x14001b6fc  mov     rcx, rsi
0x14001b6ff  call    ?NewNode@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UPolicyInfo@WSTrustMEX@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@UPolicyInfo@WSTrustMEX@@@2@@ATL@@AEAAPEAVCNode@12@PEBGII@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,WSTrustMEX::PolicyInfo,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<WSTrustMEX::PolicyInfo>>::NewNode(ushort const *,uint,uint)
0x14001b704  lea     rdi, [rax+8]
0x14001b708  mov     rdx, [rbp+57h+var_68]
0x14001b70c  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001b710  or      eax, 0FFFFFFFFh
0x14001b713  lock xadd [rdx+10h], eax
0x14001b718  sub     eax, 1
0x14001b71b  jg      short loc_14001B72C
0x14001b71d  mov     rcx, [rdx]
0x14001b720  mov     rax, [rcx]
0x14001b723  mov     rax, [rax+8]
0x14001b727  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b72c  lea     rdx, [rbp+57h+var_98]
0x14001b730  mov     rcx, rdi
0x14001b733  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14001b738  mov     [rdi+10h], r13
0x14001b73c  mov     rax, [rbp+57h+var_98]
0x14001b740  lea     rdx, [rax-18h]
0x14001b744  or      eax, 0FFFFFFFFh
0x14001b747  lock xadd [rdx+10h], eax
0x14001b74c  sub     eax, 1
0x14001b74f  jg      short loc_14001B760
0x14001b751  mov     rcx, [rdx]
0x14001b754  mov     rax, [rcx]
0x14001b757  mov     rax, [rax+8]
0x14001b75b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b760  mov     r12, [rbp+57h+var_90]
0x14001b764  test    r12, r12
0x14001b767  jz      short loc_14001B77A
0x14001b769  mov     rax, [r12]
0x14001b76d  mov     rcx, r12
0x14001b770  mov     rax, [rax+10h]
0x14001b774  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b779  nop
0x14001b77a  mov     rax, [rbx]
0x14001b77d  mov     rcx, rbx
0x14001b780  mov     rax, [rax+10h]
0x14001b784  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b789  nop
0x14001b78a  mov     ecx, [rbp+57h+var_A0]
0x14001b78d  inc     ecx
0x14001b78f  mov     [rbp+57h+var_A0], ecx
0x14001b792  mov     rdi, [rbp+57h+arg_8]
0x14001b796  cmp     ecx, [rbp+57h+var_80]
0x14001b799  jl      loc_14001B45C
0x14001b79f  mov     rcx, [rdi]
0x14001b7a2  test    rcx, rcx
0x14001b7a5  jz      short loc_14001B7B4
0x14001b7a7  mov     rax, [rcx]
0x14001b7aa  mov     rax, [rax+10h]
0x14001b7ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b7b3  nop
0x14001b7b4  add     rsp, 98h
0x14001b7bb  pop     r15
0x14001b7bd  pop     r14
0x14001b7bf  pop     r13
0x14001b7c1  pop     r12
0x14001b7c3  pop     rdi
0x14001b7c4  pop     rsi
0x14001b7c5  pop     rbx
0x14001b7c6  pop     rbp
0x14001b7c7  retn
0x14001b7c8  lea     r8, _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60; struct _GUID *
0x14001b7cf  mov     rdx, rbx; struct IUnknown *
0x14001b7d2  mov     ecx, eax; int
0x14001b7d4  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x14001b7da  mov     ecx, 80004003h; int
0x14001b7df  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x14001b7e5  lea     r8, _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60; struct _GUID *
0x14001b7ec  mov     rdx, rbx; struct IUnknown *
0x14001b7ef  mov     ecx, eax; int
0x14001b7f1  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x14001b7f7  mov     ecx, 8007000Eh; unsigned int
0x14001b7fc  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14001b802  lea     r8, _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60; struct _GUID *
0x14001b809  mov     rdx, r12; struct IUnknown *
0x14001b80c  mov     ecx, eax; int
0x14001b80e  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x14001b814  mov     ecx, 80004003h; int
0x14001b819  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x14001b81f  lea     r8, _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60; struct _GUID *
0x14001b826  mov     rdx, r13; struct IUnknown *
0x14001b829  mov     ecx, eax; int
0x14001b82b  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x14001b831  mov     ecx, 80004003h; int
0x14001b836  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x14001b83c  lea     r8, _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60; struct _GUID *
0x14001b843  mov     rdx, r15; struct IUnknown *
  ... truncated ...
```
