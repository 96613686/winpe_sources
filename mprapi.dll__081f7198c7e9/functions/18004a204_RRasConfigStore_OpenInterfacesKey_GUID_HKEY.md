# RRasConfigStore::OpenInterfacesKey(_GUID *,HKEY__ * *)

- ea: `0x18004a204`
- end: `0x18004a35b`
- name: `?OpenInterfacesKey@RRasConfigStore@@QEAAKPEAU_GUID@@PEAPEAUHKEY__@@@Z`
- size: `343`
- prototype: `__int64 __fastcall(RRasConfigStore *this, struct _GUID *, HKEY *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004214c`

## callees

- `0x18004a204`
- `0x18004a364`
- `0x18004f0ec`
- `0x180050dbc`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18004a330`
- `ntdll!RtlReleaseResource` at `0x18004a330`
- `ntdll!RtlAcquireResourceExclusive` at `0x18004a2ab`
- `ntdll!RtlAcquireResourceExclusive` at `0x18004a2ab`

## string_xrefs

- `0x18004a2ed`: `%s: Routing domain not configured.`
- `0x18004a256`: `RRasConfigStore::OpenInterfacesKey`
- `0x18004a2de`: `RRasConfigStore::OpenInterfacesKey`

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
      (_QWORD *)this + 2,
      &v9,
      (__int64)a2);
    if ( v9 == *((_QWORD *)this + 3) )
    {
      v6 = 1168;
      if ( (_QWORD)xmmword_180078C50 )
      {
        LOWORD(v10) = 0;
        FormatRRASErrorString(&v10, L"%s: Routing domain not configured.", L"RRasConfigStore::OpenInterfacesKey", 1168);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
          gCfgStoreEtwContext,
          xmmword_180078C50,
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
    if ( (_QWORD)xmmword_180078C50 )
    {
      LOWORD(v10) = 0;
      FormatRRASErrorString(&v10, L"%hs(Line#%d): Invalid parameter.", "RRasConfigStore::OpenInterfacesKey", 599);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180078C50,
        &v10);
    }
    return 87;
  }
  return v6;
}

```

## disassembly

```asm
0x18004a204  mov     [rsp+arg_18], rbx
0x18004a209  push    rbp
0x18004a20a  push    rsi
0x18004a20b  push    rdi
0x18004a20c  sub     rsp, 840h
0x18004a213  mov     rax, cs:__security_cookie
0x18004a21a  xor     rax, rsp
0x18004a21d  mov     [rsp+858h+var_28], rax
0x18004a225  mov     rbp, r8
0x18004a228  mov     rsi, rdx
0x18004a22b  mov     rbx, rcx
0x18004a22e  xor     eax, eax
0x18004a230  xor     edx, edx; Val
0x18004a232  mov     [rsp+858h+var_828], eax
0x18004a236  mov     r8d, 7FCh; Size
0x18004a23c  lea     rcx, [rsp+858h+var_824]; void *
0x18004a241  call    memset_0
0x18004a246  test    rsi, rsi
0x18004a249  jnz     short loc_18004A2A2
0x18004a24b  cmp     qword ptr cs:xmmword_180078C50, rsi
0x18004a252  jz      short loc_18004A298
0x18004a254  xor     eax, eax
0x18004a256  lea     r8, aRrasconfigstor_15; "RRasConfigStore::OpenInterfacesKey"
0x18004a25d  mov     r9d, 257h
0x18004a263  mov     word ptr [rsp+858h+var_828], ax
0x18004a268  lea     rdx, aHsLineDInvalid; "%hs(Line#%d): Invalid parameter."
0x18004a26f  lea     rcx, [rsp+858h+var_828]
0x18004a274  call    FormatRRASErrorString
0x18004a279  mov     rdx, qword ptr cs:xmmword_180078C50
0x18004a280  lea     r8, [rsp+858h+var_828]
0x18004a285  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18004a28c  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004a293  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a298  mov     ebx, 57h ; 'W'
0x18004a29d  jmp     loc_18004A336
0x18004a2a2  lea     rdi, [rbx+70h]
0x18004a2a6  mov     dl, 1; Wait
0x18004a2a8  mov     rcx, rdi; Resource
0x18004a2ab  call    cs:__imp_RtlAcquireResourceExclusive
0x18004a2b1  lea     rcx, [rbx+10h]
0x18004a2b5  mov     r8, rsi
0x18004a2b8  lea     rdx, [rsp+858h+var_838]
0x18004a2bd  call    ?lower_bound@?$_Hash@V?$_Umap_traits@U_GUID@@PEAVRRasRoutingDomainConfig@@V?$_Hash_compare@U_GUID@@UGuidHash@@UGuidEquality@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@@4@$0A@@tr1@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@@2@@std@@@2@AEBU_GUID@@@Z; std::_Hash<std::tr1::_Umap_traits<_GUID,RRasRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>,0>>::lower_bound(_GUID const &)
0x18004a2c2  mov     rcx, [rsp+858h+var_838]
0x18004a2c7  cmp     rcx, [rbx+18h]
0x18004a2cb  jnz     short loc_18004A31F
0x18004a2cd  cmp     qword ptr cs:xmmword_180078C50, 0
0x18004a2d5  mov     ebx, 490h
0x18004a2da  jz      short loc_18004A32D
0x18004a2dc  xor     eax, eax
0x18004a2de  lea     r8, aRrasconfigstor; "RRasConfigStore::OpenInterfacesKey"
0x18004a2e5  mov     r9d, ebx
0x18004a2e8  mov     word ptr [rsp+858h+var_828], ax
0x18004a2ed  lea     rdx, aSRoutingDomain_1; "%s: Routing domain not configured."
0x18004a2f4  lea     rcx, [rsp+858h+var_828]
0x18004a2f9  call    FormatRRASErrorString
0x18004a2fe  mov     rdx, qword ptr cs:xmmword_180078C50
0x18004a305  lea     r8, [rsp+858h+var_828]
0x18004a30a  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18004a311  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004a318  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a31d  jmp     short loc_18004A32D
0x18004a31f  mov     rcx, [rcx+20h]; this
0x18004a323  mov     rdx, rbp; HKEY *
0x18004a326  call    ?OpenInterfacesKey@RRasRoutingDomainConfig@@QEAAKPEAPEAUHKEY__@@@Z; RRasRoutingDomainConfig::OpenInterfacesKey(HKEY__ * *)
0x18004a32b  mov     ebx, eax
0x18004a32d  mov     rcx, rdi; Resource
0x18004a330  call    cs:__imp_RtlReleaseResource
0x18004a336  mov     eax, ebx
0x18004a338  mov     rcx, [rsp+858h+var_28]
0x18004a340  xor     rcx, rsp; StackCookie
0x18004a343  call    __security_check_cookie
0x18004a348  mov     rbx, [rsp+858h+arg_18]
0x18004a350  add     rsp, 840h
0x18004a357  pop     rdi
0x18004a358  pop     rsi
0x18004a359  pop     rbp
0x18004a35a  retn
```
