# RRasConfigStore::GetRoutingDomainConfiguration(_GUID *,_RRAS_RD_CONFIG_TYPE,int,ulong *,void *)

- ea: `0x18003d6bc`
- end: `0x18003d8bd`
- name: `?GetRoutingDomainConfiguration@RRasConfigStore@@QEAAKPEAU_GUID@@W4_RRAS_RD_CONFIG_TYPE@@HPEAKPEAX@Z`
- size: `513`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180035d10`

## callees

- `0x18003c810`
- `0x18003d6bc`
- `0x180043e34`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18003d7b9`
- `ntdll!RtlReleaseResource` at `0x18003d7c2`
- `ntdll!RtlReleaseResource` at `0x18003d7b9`
- `ntdll!RtlReleaseResource` at `0x18003d7c2`
- `ntdll!RtlAcquireResourceExclusive` at `0x18003d78e`
- `ntdll!RtlAcquireResourceExclusive` at `0x18003d78e`
- `ntdll!RtlAcquireResourceShared` at `0x18003d750`
- `ntdll!RtlAcquireResourceShared` at `0x18003d796`
- `ntdll!RtlAcquireResourceShared` at `0x18003d750`
- `ntdll!RtlAcquireResourceShared` at `0x18003d796`

## string_xrefs

- `0x18003d7ea`: `RRasConfigStore::GetRoutingDomainConfiguration`
- `0x18003d832`: `RRasConfigStore::GetRoutingDomainConfiguration`

## pseudocode

```c
__int64 __fastcall RRasConfigStore::GetRoutingDomainConfiguration(
        __int64 a1,
        const struct _GUID *a2,
        int a3,
        int a4,
        __int64 a5,
        char *a6)
{
  struct _RTL_RESOURCE *v10; // rsi
  unsigned int v11; // ebx
  __int64 v12; // rbx
  struct _RTL_RESOURCE *v13; // rcx
  unsigned int ConfigParam; // eax
  struct _RTL_RESOURCE *v15; // rcx
  const struct _GUID *v16; // r9
  __int64 v18; // [rsp+40h] [rbp-C0h] BYREF
  GUID v19; // [rsp+48h] [rbp-B8h] BYREF
  int v20; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v21; // [rsp+5Ch] [rbp-A4h]
  __int128 v22; // [rsp+6Ch] [rbp-94h]
  int v23; // [rsp+7Ch] [rbp-84h]
  int v24; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v25[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  *(_QWORD *)&v19.Data1 = a5;
  v24 = 0;
  memset_0(v25, 0, sizeof(v25));
  v20 = 0;
  v23 = 0;
  v21 = 0;
  v22 = 0;
  if ( a2 && a6 )
  {
    v10 = (struct _RTL_RESOURCE *)(a1 + 112);
    RtlAcquireResourceShared((PRTL_RESOURCE)(a1 + 112), 1u);
    std::_Hash<std::tr1::_Umap_traits<_GUID,RRasRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>,0>>::lower_bound(
      a1 + 16,
      &v18,
      a2);
    if ( v18 == *(_QWORD *)(a1 + 24) )
    {
      v11 = 1168;
    }
    else
    {
      v12 = *(_QWORD *)(v18 + 32);
      v13 = (struct _RTL_RESOURCE *)(v12 + 728);
      if ( a4 )
        RtlAcquireResourceExclusive(v13, 1u);
      else
        RtlAcquireResourceShared(v13, 1u);
      ConfigParam = RRasRoutingDomainConfig::GetConfigParam(v12, a3, a4, *(unsigned int **)&v19.Data1, a6);
      v15 = (struct _RTL_RESOURCE *)(v12 + 728);
      v11 = ConfigParam;
      RtlReleaseResource(v15);
    }
    RtlReleaseResource(v10);
    if ( !v11 )
      return v11;
  }
  else
  {
    v11 = 87;
    if ( (_QWORD)xmmword_180071090 )
    {
      LOWORD(v24) = 0;
      FormatRRASErrorString(
        &v24,
        L"%hs(Line#%d): Invalid parameter.",
        "RRasConfigStore::GetRoutingDomainConfiguration",
        949);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180071090,
        &v24);
    }
  }
  if ( (_QWORD)xmmword_1800710A0 )
  {
    LOWORD(v24) = 0;
    LOWORD(v20) = 0;
    v19 = GUID_NULL;
    FormatRRASErrorString(&v24, L"%s: failed: %d.", L"RRasConfigStore::GetRoutingDomainConfiguration", v11);
    v16 = &v19;
    if ( a2 )
      v16 = a2;
    gCfgStoreParamTemplateFunc(
      gCfgStoreEtwContext,
      (const struct _EVENT_DESCRIPTOR *)xmmword_1800710A0,
      (const unsigned __int16 *)&v24,
      v16,
      0,
      (const unsigned __int16 *)&v20);
  }
  return v11;
}

```

## disassembly

```asm
0x18003d6bc  push    rbp
0x18003d6be  push    rbx
0x18003d6bf  push    rsi
0x18003d6c0  push    rdi
0x18003d6c1  push    r12
0x18003d6c3  push    r13
0x18003d6c5  push    r14
0x18003d6c7  push    r15
0x18003d6c9  lea     rbp, [rsp-798h]
0x18003d6d1  sub     rsp, 898h
0x18003d6d8  mov     rax, cs:__security_cookie
0x18003d6df  xor     rax, rsp
0x18003d6e2  mov     [rbp+7D0h+var_50], rax
0x18003d6e9  mov     rax, [rbp+7D0h+arg_20]
0x18003d6f0  mov     r13d, r8d
0x18003d6f3  mov     r14, [rbp+7D0h+arg_28]
0x18003d6fa  mov     r12, rdx
0x18003d6fd  mov     qword ptr [rsp+8D0h+var_888], rax
0x18003d702  mov     rbx, rcx
0x18003d705  xor     eax, eax
0x18003d707  lea     rcx, [rbp+7D0h+var_84C]; void *
0x18003d70b  xor     edx, edx; Val
0x18003d70d  mov     [rbp+7D0h+var_850], eax
0x18003d710  mov     r8d, 7FCh; Size
0x18003d716  mov     r15d, r9d
0x18003d719  call    memset_0
0x18003d71e  xor     eax, eax
0x18003d720  xorps   xmm0, xmm0
0x18003d723  mov     [rsp+8D0h+var_878], eax
0x18003d727  mov     [rsp+8D0h+var_854], eax
0x18003d72b  movups  [rsp+8D0h+var_874], xmm0
0x18003d730  movups  [rsp+8D0h+var_864], xmm0
0x18003d735  test    r12, r12
0x18003d738  jz      loc_18003D7D2
0x18003d73e  test    r14, r14
0x18003d741  jz      loc_18003D7D2
0x18003d747  lea     rsi, [rbx+70h]
0x18003d74b  mov     dl, 1; Wait
0x18003d74d  mov     rcx, rsi; Resource
0x18003d750  call    cs:__imp_RtlAcquireResourceShared
0x18003d756  lea     rcx, [rbx+10h]
0x18003d75a  mov     r8, r12
0x18003d75d  lea     rdx, [rsp+8D0h+var_890]
0x18003d762  call    ?lower_bound@?$_Hash@V?$_Umap_traits@U_GUID@@PEAVRRasRoutingDomainConfig@@V?$_Hash_compare@U_GUID@@UGuidHash@@UGuidEquality@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@@4@$0A@@tr1@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@@2@@std@@@2@AEBU_GUID@@@Z; std::_Hash<std::tr1::_Umap_traits<_GUID,RRasRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>,0>>::lower_bound(_GUID const &)
0x18003d767  mov     rax, [rsp+8D0h+var_890]
0x18003d76c  cmp     rax, [rbx+18h]
0x18003d770  jnz     short loc_18003D779
0x18003d772  mov     ebx, 490h
0x18003d777  jmp     short loc_18003D7BF
0x18003d779  mov     rbx, [rax+20h]
0x18003d77d  mov     dl, 1; Wait
0x18003d77f  lea     rdi, [rbx+2D8h]
0x18003d786  mov     rcx, rdi; Resource
0x18003d789  test    r15d, r15d
0x18003d78c  jz      short loc_18003D796
0x18003d78e  call    cs:__imp_RtlAcquireResourceExclusive
0x18003d794  jmp     short loc_18003D79C
0x18003d796  call    cs:__imp_RtlAcquireResourceShared
0x18003d79c  mov     r9, qword ptr [rsp+8D0h+var_888]
0x18003d7a1  mov     r8d, r15d
0x18003d7a4  mov     edx, r13d
0x18003d7a7  mov     [rsp+8D0h+var_8B0], r14
0x18003d7ac  mov     rcx, rbx
0x18003d7af  call    ?GetConfigParam@RRasRoutingDomainConfig@@QEAAKW4_RRAS_RD_CONFIG_TYPE@@HPEAKPEAX@Z; RRasRoutingDomainConfig::GetConfigParam(_RRAS_RD_CONFIG_TYPE,int,ulong *,void *)
0x18003d7b4  mov     rcx, rdi; Resource
0x18003d7b7  mov     ebx, eax
0x18003d7b9  call    cs:__imp_RtlReleaseResource
0x18003d7bf  mov     rcx, rsi; Resource
0x18003d7c2  call    cs:__imp_RtlReleaseResource
0x18003d7c8  test    ebx, ebx
0x18003d7ca  jz      loc_18003D898
0x18003d7d0  jmp     short loc_18003D81F
0x18003d7d2  cmp     qword ptr cs:xmmword_180071090, rax
0x18003d7d9  mov     ebx, 57h ; 'W'
0x18003d7de  jz      short loc_18003D81F
0x18003d7e0  mov     r9d, 3B5h
0x18003d7e6  mov     word ptr [rbp+7D0h+var_850], ax
0x18003d7ea  lea     r8, aRrasconfigstor_4; "RRasConfigStore::GetRoutingDomainConfig"...
0x18003d7f1  lea     rdx, aHsLineDInvalid; "%hs(Line#%d): Invalid parameter."
0x18003d7f8  lea     rcx, [rbp+7D0h+var_850]
0x18003d7fc  call    FormatRRASErrorString
0x18003d801  mov     rdx, qword ptr cs:xmmword_180071090
0x18003d808  lea     r8, [rbp+7D0h+var_850]
0x18003d80c  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003d813  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18003d81a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d81f  cmp     qword ptr cs:xmmword_1800710A0, 0
0x18003d827  jz      short loc_18003D898
0x18003d829  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18003d830  xor     eax, eax
0x18003d832  lea     r8, aRrasconfigstor_7; "RRasConfigStore::GetRoutingDomainConfig"...
0x18003d839  mov     r9d, ebx
0x18003d83c  mov     word ptr [rbp+7D0h+var_850], ax
0x18003d840  lea     rdx, aSFailedD; "%s: failed: %d."
0x18003d847  mov     word ptr [rsp+8D0h+var_878], ax
0x18003d84c  lea     rcx, [rbp+7D0h+var_850]
0x18003d850  movdqu  [rsp+8D0h+var_888], xmm0
0x18003d856  call    FormatRRASErrorString
0x18003d85b  mov     rdx, qword ptr cs:xmmword_1800710A0
0x18003d862  lea     rax, [rsp+8D0h+var_878]
0x18003d867  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003d86e  lea     r9, [rsp+8D0h+var_888]
0x18003d873  mov     [rsp+8D0h+var_8A8], rax
0x18003d878  lea     r8, [rbp+7D0h+var_850]
0x18003d87c  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18003d883  test    r12, r12
0x18003d886  mov     [rsp+8D0h+var_8B0], 0
0x18003d88f  cmovnz  r9, r12
0x18003d893  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d898  mov     eax, ebx
0x18003d89a  mov     rcx, [rbp+7D0h+var_50]
0x18003d8a1  xor     rcx, rsp; StackCookie
0x18003d8a4  call    __security_check_cookie
0x18003d8a9  add     rsp, 898h
0x18003d8b0  pop     r15
0x18003d8b2  pop     r14
0x18003d8b4  pop     r13
0x18003d8b6  pop     r12
0x18003d8b8  pop     rdi
0x18003d8b9  pop     rsi
0x18003d8ba  pop     rbx
0x18003d8bb  pop     rbp
0x18003d8bc  retn
```
