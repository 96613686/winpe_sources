# RRasConfigStore::GetRoutingDomainConfigObject(_GUID *,ulong,ulong,int,_MPRI_ROUTING_DOMAIN_CONFIG_EX * *)

- ea: `0x18003d3f4`
- end: `0x18003d6b6`
- name: `?GetRoutingDomainConfigObject@RRasConfigStore@@QEAAKPEAU_GUID@@KKHPEAPEAU_MPRI_ROUTING_DOMAIN_CONFIG_EX@@@Z`
- size: `706`
- prototype: `unsigned int __fastcall(RRasConfigStore *__hidden this, struct _GUID *, unsigned int, unsigned int, int, struct _MPRI_ROUTING_DOMAIN_CONFIG_EX **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180035b0c`

## callees

- `0x18003c608`
- `0x18003d3f4`
- `0x180043e34`
- `0x180044144`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18003d577`
- `ntdll!RtlReleaseResource` at `0x18003d5a8`
- `ntdll!RtlReleaseResource` at `0x18003d63c`
- `ntdll!RtlReleaseResource` at `0x18003d577`
- `ntdll!RtlReleaseResource` at `0x18003d5a8`
- `ntdll!RtlReleaseResource` at `0x18003d63c`
- `ntdll!RtlAcquireResourceShared` at `0x18003d489`
- `ntdll!RtlAcquireResourceShared` at `0x18003d4c5`
- `ntdll!RtlAcquireResourceShared` at `0x18003d489`
- `ntdll!RtlAcquireResourceShared` at `0x18003d4c5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003d4f9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003d4f9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003d4de`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003d4de`
- `KERNEL32!GetProcessHeap` at `0x18003d4e6`
- `KERNEL32!GetProcessHeap` at `0x18003d4e6`

## string_xrefs

- `0x18003d65c`: `RRasConfigStore::GetRoutingDomainConfigObject`
- `0x18003d51c`: `RRasConfigStore::GetRoutingDomainConfigObject`
- `0x18003d5c9`: `RRasConfigStore::GetRoutingDomainConfigObject`
- `0x18003d5d4`: `%s: pRdObject->GetConfig failed: %d.`

## pseudocode

```c
__int64 __fastcall RRasConfigStore::GetRoutingDomainConfigObject(
        RRasConfigStore *this,
        struct _GUID *a2,
        int a3,
        unsigned int a4,
        int a5,
        struct _MPRI_ROUTING_DOMAIN_CONFIG_EX **a6)
{
  struct _RTL_RESOURCE *v9; // r12
  unsigned int Config; // ebx
  __int64 v11; // r13
  struct _MPRI_ROUTING_DOMAIN_CONFIG_EX *v12; // rax
  HANDLE ProcessHeap; // rax
  struct _MPRI_ROUTING_DOMAIN_CONFIG_EX *v14; // rdi
  _OWORD v19[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v20; // [rsp+70h] [rbp-90h] BYREF
  __int128 v21; // [rsp+74h] [rbp-8Ch]
  __int128 v22; // [rsp+84h] [rbp-7Ch]
  int v23; // [rsp+94h] [rbp-6Ch]
  int v24; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v25[2044]; // [rsp+A4h] [rbp-5Ch] BYREF

  v24 = 0;
  memset_0(v25, 0, sizeof(v25));
  v20 = 0;
  v23 = 0;
  v21 = 0;
  v22 = 0;
  if ( a2 && a6 )
  {
    v9 = (struct _RTL_RESOURCE *)((char *)this + 112);
    *a6 = 0;
    RtlAcquireResourceShared((PRTL_RESOURCE)((char *)this + 112), 1u);
    std::_Hash<std::tr1::_Umap_traits<_GUID,RRasRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>,0>>::lower_bound(
      (char *)this + 16,
      v19,
      a2);
    if ( *(_QWORD *)&v19[0] == *((_QWORD *)this + 3) )
    {
      Config = 1168;
    }
    else
    {
      v11 = *(_QWORD *)(*(_QWORD *)&v19[0] + 32LL);
      RtlAcquireResourceShared((PRTL_RESOURCE)(v11 + 728), 1u);
      Config = 8;
      if ( a3 >= 0 )
      {
        ProcessHeap = GetProcessHeap();
        v12 = (struct _MPRI_ROUTING_DOMAIN_CONFIG_EX *)HeapAlloc(ProcessHeap, 8u, 0x368u);
      }
      else
      {
        v12 = (struct _MPRI_ROUTING_DOMAIN_CONFIG_EX *)LocalAlloc(0x40u, 0x368u);
      }
      *(_QWORD *)&v19[0] = v12;
      v14 = v12;
      if ( v12 )
      {
        memset_0(v12, 0, 0x368u);
        Config = RRasRoutingDomainConfig::GetConfig((RRasRoutingDomainConfig *)v11, a3, a4, v14);
        RtlReleaseResource((PRTL_RESOURCE)(v11 + 728));
        if ( Config )
        {
          if ( (_QWORD)xmmword_1800710A0 )
          {
            LOWORD(v24) = 0;
            LOWORD(v20) = 0;
            v19[1] = GUID_NULL;
            FormatRRASErrorString(
              &v24,
              L"%s: pRdObject->GetConfig failed: %d.",
              L"RRasConfigStore::GetRoutingDomainConfigObject",
              Config);
            ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, struct _GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
              gCfgStoreEtwContext,
              xmmword_1800710A0,
              &v24,
              a2,
              0,
              &v20);
          }
          FreeRoutingDomainConfigObject(v19);
        }
        else
        {
          *a6 = v14;
        }
      }
      else
      {
        if ( (_QWORD)xmmword_1800710A0 )
        {
          LOWORD(v24) = 0;
          LOWORD(v20) = 0;
          v19[0] = GUID_NULL;
          FormatRRASErrorString(&v24, L"%s: Malloc failed.", L"RRasConfigStore::GetRoutingDomainConfigObject");
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, struct _GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
            gCfgStoreEtwContext,
            xmmword_1800710A0,
            &v24,
            a2,
            0,
            &v20);
        }
        RtlReleaseResource((PRTL_RESOURCE)(v11 + 728));
      }
    }
    RtlReleaseResource(v9);
  }
  else
  {
    Config = 87;
    if ( (_QWORD)xmmword_180071090 )
    {
      LOWORD(v24) = 0;
      FormatRRASErrorString(
        &v24,
        L"%hs(Line#%d): Invalid parameter.",
        "RRasConfigStore::GetRoutingDomainConfigObject",
        1129);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180071090,
        &v24);
    }
  }
  return Config;
}

```

## disassembly

```asm
0x18003d3f4  push    rbp
0x18003d3f6  push    rbx
0x18003d3f7  push    rsi
0x18003d3f8  push    rdi
0x18003d3f9  push    r12
0x18003d3fb  push    r13
0x18003d3fd  push    r14
0x18003d3ff  push    r15
0x18003d401  lea     rbp, [rsp-7B8h]
0x18003d409  sub     rsp, 8B8h
0x18003d410  mov     rax, cs:__security_cookie
0x18003d417  xor     rax, rsp
0x18003d41a  mov     [rbp+7F0h+var_50], rax
0x18003d421  mov     r14, [rbp+7F0h+arg_28]
0x18003d428  mov     esi, r8d
0x18003d42b  mov     [rsp+8F0h+var_8AC], r8d
0x18003d430  mov     rdi, rdx
0x18003d433  mov     [rsp+8F0h+var_8A8], rdx
0x18003d438  mov     rbx, rcx
0x18003d43b  xor     eax, eax
0x18003d43d  mov     [rsp+8F0h+var_8B0], r9d
0x18003d442  xor     edx, edx; Val
0x18003d444  mov     [rbp+7F0h+var_850], eax
0x18003d447  mov     r8d, 7FCh; Size
0x18003d44d  lea     rcx, [rbp+7F0h+var_84C]; void *
0x18003d451  call    memset_0
0x18003d456  xor     eax, eax
0x18003d458  xorps   xmm0, xmm0
0x18003d45b  mov     [rsp+8F0h+var_880], eax
0x18003d45f  mov     [rbp+7F0h+var_85C], eax
0x18003d462  movups  [rsp+8F0h+var_87C], xmm0
0x18003d467  movups  [rbp+7F0h+var_86C], xmm0
0x18003d46b  test    rdi, rdi
0x18003d46e  jz      loc_18003D644
0x18003d474  test    r14, r14
0x18003d477  jz      loc_18003D644
0x18003d47d  lea     r12, [rbx+70h]
0x18003d481  mov     [r14], rax
0x18003d484  mov     rcx, r12; Resource
0x18003d487  mov     dl, 1; Wait
0x18003d489  call    cs:__imp_RtlAcquireResourceShared
0x18003d48f  lea     rcx, [rbx+10h]
0x18003d493  mov     r8, rdi
0x18003d496  lea     rdx, [rsp+8F0h+var_8A0]
0x18003d49b  call    ?lower_bound@?$_Hash@V?$_Umap_traits@U_GUID@@PEAVRRasRoutingDomainConfig@@V?$_Hash_compare@U_GUID@@UGuidHash@@UGuidEquality@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@@4@$0A@@tr1@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@@2@@std@@@2@AEBU_GUID@@@Z; std::_Hash<std::tr1::_Umap_traits<_GUID,RRasRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>,0>>::lower_bound(_GUID const &)
0x18003d4a0  mov     rax, qword ptr [rsp+8F0h+var_8A0]
0x18003d4a5  cmp     rax, [rbx+18h]
0x18003d4a9  jnz     short loc_18003D4B5
0x18003d4ab  mov     ebx, 490h
0x18003d4b0  jmp     loc_18003D639
0x18003d4b5  mov     r13, [rax+20h]
0x18003d4b9  mov     dl, 1; Wait
0x18003d4bb  lea     r15, [r13+2D8h]
0x18003d4c2  mov     rcx, r15; Resource
0x18003d4c5  call    cs:__imp_RtlAcquireResourceShared
0x18003d4cb  mov     ebx, 8
0x18003d4d0  test    esi, esi
0x18003d4d2  jns     short loc_18003D4E6
0x18003d4d4  mov     esi, 368h
0x18003d4d9  lea     ecx, [rbx+38h]; uFlags
0x18003d4dc  mov     edx, esi; uBytes
0x18003d4de  call    cs:__imp_LocalAlloc
0x18003d4e4  jmp     short loc_18003D4FF
0x18003d4e6  call    cs:__imp_GetProcessHeap
0x18003d4ec  mov     esi, 368h
0x18003d4f1  mov     edx, ebx; dwFlags
0x18003d4f3  mov     rcx, rax; hHeap
0x18003d4f6  mov     r8d, esi; dwBytes
0x18003d4f9  call    cs:__imp_HeapAlloc
0x18003d4ff  mov     qword ptr [rsp+8F0h+var_8A0], rax
0x18003d504  mov     rdi, rax
0x18003d507  test    rax, rax
0x18003d50a  jnz     short loc_18003D582
0x18003d50c  cmp     qword ptr cs:xmmword_1800710A0, rax
0x18003d513  jz      short loc_18003D574
0x18003d515  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18003d51c  lea     r8, aRrasconfigstor_28; "RRasConfigStore::GetRoutingDomainConfig"...
0x18003d523  mov     word ptr [rbp+7F0h+var_850], ax
0x18003d527  lea     rdx, aSMallocFailed; "%s: Malloc failed."
0x18003d52e  mov     word ptr [rsp+8F0h+var_880], ax
0x18003d533  lea     rcx, [rbp+7F0h+var_850]
0x18003d537  movdqu  [rsp+8F0h+var_8A0], xmm0
0x18003d53d  call    FormatRRASErrorString
0x18003d542  mov     r9, [rsp+8F0h+var_8A8]
0x18003d547  lea     rax, [rsp+8F0h+var_880]
0x18003d54c  mov     rdx, qword ptr cs:xmmword_1800710A0
0x18003d553  lea     r8, [rbp+7F0h+var_850]
0x18003d557  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003d55e  mov     [rsp+8F0h+var_8C8], rax
0x18003d563  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18003d56a  mov     [rsp+8F0h+var_8D0], rdi
0x18003d56f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d574  mov     rcx, r15; Resource
0x18003d577  call    cs:__imp_RtlReleaseResource
0x18003d57d  jmp     loc_18003D639
0x18003d582  mov     r8, rsi; Size
0x18003d585  xor     edx, edx; Val
0x18003d587  mov     rcx, rdi; void *
0x18003d58a  call    memset_0
0x18003d58f  mov     r8d, [rsp+8F0h+var_8B0]; unsigned int
0x18003d594  mov     r9, rdi; struct _MPRI_ROUTING_DOMAIN_CONFIG_EX *
0x18003d597  mov     edx, [rsp+8F0h+var_8AC]; unsigned int
0x18003d59b  mov     rcx, r13; this
0x18003d59e  call    ?GetConfig@RRasRoutingDomainConfig@@QEAAKKKPEAU_MPRI_ROUTING_DOMAIN_CONFIG_EX@@@Z; RRasRoutingDomainConfig::GetConfig(ulong,ulong,_MPRI_ROUTING_DOMAIN_CONFIG_EX *)
0x18003d5a3  mov     rcx, r15; Resource
0x18003d5a6  mov     ebx, eax
0x18003d5a8  call    cs:__imp_RtlReleaseResource
0x18003d5ae  test    ebx, ebx
0x18003d5b0  jz      loc_18003D636
0x18003d5b6  cmp     qword ptr cs:xmmword_1800710A0, 0
0x18003d5be  jz      short loc_18003D62A
0x18003d5c0  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18003d5c7  xor     ecx, ecx
0x18003d5c9  lea     r8, aRrasconfigstor_28; "RRasConfigStore::GetRoutingDomainConfig"...
0x18003d5d0  mov     word ptr [rbp+7F0h+var_850], cx
0x18003d5d4  lea     rdx, aSPrdobjectGetc; "%s: pRdObject->GetConfig failed: %d."
0x18003d5db  xor     eax, eax
0x18003d5dd  lea     rcx, [rbp+7F0h+var_850]
0x18003d5e1  mov     r9d, ebx
0x18003d5e4  mov     word ptr [rsp+8F0h+var_880], ax
0x18003d5e9  movdqu  [rsp+8F0h+var_890], xmm0
0x18003d5ef  call    FormatRRASErrorString
0x18003d5f4  mov     r9, [rsp+8F0h+var_8A8]
0x18003d5f9  lea     rax, [rsp+8F0h+var_880]
0x18003d5fe  mov     rdx, qword ptr cs:xmmword_1800710A0
0x18003d605  lea     r8, [rbp+7F0h+var_850]
0x18003d609  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003d610  mov     [rsp+8F0h+var_8C8], rax
0x18003d615  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18003d61c  mov     [rsp+8F0h+var_8D0], 0
0x18003d625  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d62a  lea     rcx, [rsp+8F0h+var_8A0]
0x18003d62f  call    FreeRoutingDomainConfigObject
0x18003d634  jmp     short loc_18003D639
0x18003d636  mov     [r14], rdi
0x18003d639  mov     rcx, r12; Resource
0x18003d63c  call    cs:__imp_RtlReleaseResource
0x18003d642  jmp     short loc_18003D691
0x18003d644  cmp     qword ptr cs:xmmword_180071090, rax
0x18003d64b  mov     ebx, 57h ; 'W'
0x18003d650  jz      short loc_18003D691
0x18003d652  mov     r9d, 469h
0x18003d658  mov     word ptr [rbp+7F0h+var_850], ax
0x18003d65c  lea     r8, aRrasconfigstor_0; "RRasConfigStore::GetRoutingDomainConfig"...
0x18003d663  lea     rdx, aHsLineDInvalid; "%hs(Line#%d): Invalid parameter."
0x18003d66a  lea     rcx, [rbp+7F0h+var_850]
0x18003d66e  call    FormatRRASErrorString
0x18003d673  mov     rdx, qword ptr cs:xmmword_180071090
0x18003d67a  lea     r8, [rbp+7F0h+var_850]
0x18003d67e  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003d685  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18003d68c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d691  mov     eax, ebx
0x18003d693  mov     rcx, [rbp+7F0h+var_50]
0x18003d69a  xor     rcx, rsp; StackCookie
0x18003d69d  call    __security_check_cookie
0x18003d6a2  add     rsp, 8B8h
0x18003d6a9  pop     r15
0x18003d6ab  pop     r14
0x18003d6ad  pop     r13
0x18003d6af  pop     r12
0x18003d6b1  pop     rdi
0x18003d6b2  pop     rsi
0x18003d6b3  pop     rbx
0x18003d6b4  pop     rbp
0x18003d6b5  retn
```
