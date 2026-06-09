# RRasConfigStore::OpenInterfacesKey(_GUID *,HKEY__ * *)

- ea: `0x18003ec48`
- end: `0x18003ed9f`
- name: `?OpenInterfacesKey@RRasConfigStore@@QEAAKPEAU_GUID@@PEAPEAUHKEY__@@@Z`
- size: `343`
- prototype: `unsigned int(RRasConfigStore *__hidden this, struct _GUID *, HKEY *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180036924`

## callees

- `0x18003ec48`
- `0x18003eda8`
- `0x180043e34`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18003ed74`
- `ntdll!RtlReleaseResource` at `0x18003ed74`
- `ntdll!RtlAcquireResourceExclusive` at `0x18003ecef`
- `ntdll!RtlAcquireResourceExclusive` at `0x18003ecef`

## string_xrefs

- `0x18003ed31`: `%s: Routing domain not configured.`
- `0x18003ec9a`: `RRasConfigStore::OpenInterfacesKey`
- `0x18003ed22`: `RRasConfigStore::OpenInterfacesKey`

## pseudocode

```c
__int64 __fastcall RRasConfigStore::OpenInterfacesKey(RRasConfigStore *this, struct _GUID *a2, HKEY *a3)
{
  unsigned int v6; // ebx
  struct _RTL_RESOURCE *v7; // rdi
  __int64 v9; // [rsp+20h] [rbp-838h] BYREF
  int v10; // [rsp+30h] [rbp-828h] BYREF
  _BYTE v11[2044]; // [rsp+34h] [rbp-824h] BYREF

  v10 = 0;
  memset_0(v11, 0, sizeof(v11));
  if ( a2 )
  {
    v7 = (struct _RTL_RESOURCE *)((char *)this + 112);
    RtlAcquireResourceExclusive((PRTL_RESOURCE)((char *)this + 112), 1u);
    std::_Hash<std::tr1::_Umap_traits<_GUID,RRasRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>,0>>::lower_bound(
      (char *)this + 16,
      &v9,
      a2);
    if ( v9 == *((_QWORD *)this + 3) )
    {
      v6 = 1168;
      if ( (_QWORD)xmmword_180071090 )
      {
        LOWORD(v10) = 0;
        FormatRRASErrorString(&v10, L"%s: Routing domain not configured.", L"RRasConfigStore::OpenInterfacesKey", 1168);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
          gCfgStoreEtwContext,
          xmmword_180071090,
          &v10);
      }
    }
    else
    {
      v6 = RRasRoutingDomainConfig::OpenInterfacesKey(*(RRasRoutingDomainConfig **)(v9 + 32), a3);
    }
    RtlReleaseResource(v7);
  }
  else
  {
    if ( (_QWORD)xmmword_180071090 )
    {
      LOWORD(v10) = 0;
      FormatRRASErrorString(&v10, L"%hs(Line#%d): Invalid parameter.", "RRasConfigStore::OpenInterfacesKey", 599);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180071090,
        &v10);
    }
    return 87;
  }
  return v6;
}

```

## disassembly

```asm
0x18003ec48  mov     [rsp+arg_18], rbx
0x18003ec4d  push    rbp
0x18003ec4e  push    rsi
0x18003ec4f  push    rdi
0x18003ec50  sub     rsp, 840h
0x18003ec57  mov     rax, cs:__security_cookie
0x18003ec5e  xor     rax, rsp
0x18003ec61  mov     [rsp+858h+var_28], rax
0x18003ec69  mov     rbp, r8
0x18003ec6c  mov     rsi, rdx
0x18003ec6f  mov     rbx, rcx
0x18003ec72  xor     eax, eax
0x18003ec74  xor     edx, edx; Val
0x18003ec76  mov     [rsp+858h+var_828], eax
0x18003ec7a  mov     r8d, 7FCh; Size
0x18003ec80  lea     rcx, [rsp+858h+var_824]; void *
0x18003ec85  call    memset_0
0x18003ec8a  test    rsi, rsi
0x18003ec8d  jnz     short loc_18003ECE6
0x18003ec8f  cmp     qword ptr cs:xmmword_180071090, rsi
0x18003ec96  jz      short loc_18003ECDC
0x18003ec98  xor     eax, eax
0x18003ec9a  lea     r8, aRrasconfigstor_19; "RRasConfigStore::OpenInterfacesKey"
0x18003eca1  mov     r9d, 257h
0x18003eca7  mov     word ptr [rsp+858h+var_828], ax
0x18003ecac  lea     rdx, aHsLineDInvalid; "%hs(Line#%d): Invalid parameter."
0x18003ecb3  lea     rcx, [rsp+858h+var_828]
0x18003ecb8  call    FormatRRASErrorString
0x18003ecbd  mov     rdx, qword ptr cs:xmmword_180071090
0x18003ecc4  lea     r8, [rsp+858h+var_828]
0x18003ecc9  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003ecd0  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18003ecd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ecdc  mov     ebx, 57h ; 'W'
0x18003ece1  jmp     loc_18003ED7A
0x18003ece6  lea     rdi, [rbx+70h]
0x18003ecea  mov     dl, 1; Wait
0x18003ecec  mov     rcx, rdi; Resource
0x18003ecef  call    cs:__imp_RtlAcquireResourceExclusive
0x18003ecf5  lea     rcx, [rbx+10h]
0x18003ecf9  mov     r8, rsi
0x18003ecfc  lea     rdx, [rsp+858h+var_838]
0x18003ed01  call    ?lower_bound@?$_Hash@V?$_Umap_traits@U_GUID@@PEAVRRasRoutingDomainConfig@@V?$_Hash_compare@U_GUID@@UGuidHash@@UGuidEquality@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@@4@$0A@@tr1@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@@2@@std@@@2@AEBU_GUID@@@Z; std::_Hash<std::tr1::_Umap_traits<_GUID,RRasRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>,0>>::lower_bound(_GUID const &)
0x18003ed06  mov     rcx, [rsp+858h+var_838]
0x18003ed0b  cmp     rcx, [rbx+18h]
0x18003ed0f  jnz     short loc_18003ED63
0x18003ed11  cmp     qword ptr cs:xmmword_180071090, 0
0x18003ed19  mov     ebx, 490h
0x18003ed1e  jz      short loc_18003ED71
0x18003ed20  xor     eax, eax
0x18003ed22  lea     r8, aRrasconfigstor; "RRasConfigStore::OpenInterfacesKey"
0x18003ed29  mov     r9d, ebx
0x18003ed2c  mov     word ptr [rsp+858h+var_828], ax
0x18003ed31  lea     rdx, aSRoutingDomain_1; "%s: Routing domain not configured."
0x18003ed38  lea     rcx, [rsp+858h+var_828]
0x18003ed3d  call    FormatRRASErrorString
0x18003ed42  mov     rdx, qword ptr cs:xmmword_180071090
0x18003ed49  lea     r8, [rsp+858h+var_828]
0x18003ed4e  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003ed55  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18003ed5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ed61  jmp     short loc_18003ED71
0x18003ed63  mov     rcx, [rcx+20h]; this
0x18003ed67  mov     rdx, rbp; HKEY *
0x18003ed6a  call    ?OpenInterfacesKey@RRasRoutingDomainConfig@@QEAAKPEAPEAUHKEY__@@@Z; RRasRoutingDomainConfig::OpenInterfacesKey(HKEY__ * *)
0x18003ed6f  mov     ebx, eax
0x18003ed71  mov     rcx, rdi; Resource
0x18003ed74  call    cs:__imp_RtlReleaseResource
0x18003ed7a  mov     eax, ebx
0x18003ed7c  mov     rcx, [rsp+858h+var_28]
0x18003ed84  xor     rcx, rsp; StackCookie
0x18003ed87  call    __security_check_cookie
0x18003ed8c  mov     rbx, [rsp+858h+arg_18]
0x18003ed94  add     rsp, 840h
0x18003ed9b  pop     rdi
0x18003ed9c  pop     rsi
0x18003ed9d  pop     rbp
0x18003ed9e  retn
```
