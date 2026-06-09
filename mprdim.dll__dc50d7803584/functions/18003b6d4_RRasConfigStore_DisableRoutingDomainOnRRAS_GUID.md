# RRasConfigStore::DisableRoutingDomainOnRRAS(_GUID *)

- ea: `0x18003b6d4`
- end: `0x18003b928`
- name: `?DisableRoutingDomainOnRRAS@RRasConfigStore@@QEAAKPEAU_GUID@@@Z`
- size: `596`
- prototype: `__int64 __fastcall(RRasConfigStore *this, struct _GUID *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800353e0`

## callees

- `0x180038bc0`
- `0x18003b6d4`
- `0x180041210`
- `0x180043c28`
- `0x180043ca0`
- `0x180043d5c`
- `0x180043e34`
- `0x18004583c`
- `0x1800459e8`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18003b8cf`
- `ntdll!RtlReleaseResource` at `0x18003b8cf`
- `ntdll!RtlAcquireResourceExclusive` at `0x18003b7e9`
- `ntdll!RtlAcquireResourceExclusive` at `0x18003b7e9`

## string_xrefs

- `0x18003b76f`: `RRasConfigStore::DisableRoutingDomainOnRRAS`
- `0x18003b83d`: `RRasConfigStore::DisableRoutingDomainOnRRAS`
- `0x18003b7a6`: `RRasConfigStore::DisableRoutingDomainOnRRAS`
- `0x18003b844`: `%s: Routing domain not configured.`

## pseudocode

```c
__int64 __fastcall RRasConfigStore::DisableRoutingDomainOnRRAS(RRasConfigStore *this, struct _GUID *a2)
{
  void (*v4)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  struct _RTL_RESOURCE *v5; // r14
  char *v6; // rdi
  RRasRoutingDomainConfig *v7; // rsi
  unsigned int v8; // edx
  _QWORD *v9; // rbx
  unsigned int v10; // ebx
  _QWORD *v12; // r8
  unsigned __int16 *v13; // [rsp+28h] [rbp-D8h]
  unsigned int v14; // [rsp+30h] [rbp-D0h]
  unsigned int v15; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v16; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v17; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v18; // [rsp+58h] [rbp-A8h]
  __int128 v19; // [rsp+68h] [rbp-98h]
  __int64 v20; // [rsp+78h] [rbp-88h]
  int v21; // [rsp+80h] [rbp-80h]
  int v22; // [rsp+84h] [rbp-7Ch]
  GUID v23; // [rsp+88h] [rbp-78h] BYREF
  int v24; // [rsp+98h] [rbp-68h] BYREF
  __int128 v25; // [rsp+9Ch] [rbp-64h]
  __int128 v26; // [rsp+ACh] [rbp-54h]
  int v27; // [rsp+BCh] [rbp-44h]
  int v28; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v29[2044]; // [rsp+C4h] [rbp-3Ch] BYREF

  v15 = 0;
  v28 = 0;
  memset_0(v29, 0, sizeof(v29));
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v18 = 0;
  v17 = 0;
  v19 = 0;
  v20 = 0;
  v21 = -1;
  v22 = 0;
  if ( *((_QWORD *)&xmmword_1800710A0 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v17,
      L"RRasConfigStore::DisableRoutingDomainOnRRAS",
      &v15,
      v4,
      a2,
      v13,
      v14);
  if ( a2 )
  {
    v5 = (struct _RTL_RESOURCE *)((char *)this + 112);
    RtlAcquireResourceExclusive((PRTL_RESOURCE)((char *)this + 112), 1u);
    v6 = (char *)this + 16;
    std::_Hash<std::tr1::_Umap_traits<_GUID,RRasRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>,0>>::lower_bound(
      (char *)this + 16,
      &v16,
      a2);
    if ( v16 == *((_QWORD *)this + 3) )
    {
      v15 = 1168;
      if ( (_QWORD)xmmword_1800710A0 )
      {
        LOWORD(v28) = 0;
        v23 = GUID_NULL;
        LOWORD(v24) = 0;
        FormatRRASErrorString(
          &v28,
          L"%s: Routing domain not configured.",
          L"RRasConfigStore::DisableRoutingDomainOnRRAS");
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, struct _GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
          gCfgStoreEtwContext,
          xmmword_1800710A0,
          &v28,
          a2,
          0,
          &v24);
      }
    }
    else
    {
      v7 = *(RRasRoutingDomainConfig **)(v16 + 32);
      RRasRoutingDomainConfig::RemoveConfigurationFromRegistry(v7);
      std::_Hash<std::tr1::_Umap_traits<_GUID,RRasRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>,0>>::equal_range(
        v6,
        &v23,
        a2);
      v9 = *(_QWORD **)&v23.Data1;
      if ( *(_OWORD *)&v23 == __PAIR128__(*((_QWORD *)v6 + 1), **((_QWORD **)v6 + 1)) )
      {
        std::_Hash<std::tr1::_Umap_traits<_GUID,RRasRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>,0>>::clear(v6);
      }
      else
      {
        while ( v9 != *(_QWORD **)v23.Data4 )
        {
          v12 = v9;
          v9 = (_QWORD *)*v9;
          std::_Hash<std::tr1::_Umap_traits<_GUID,RRasRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>,0>>::erase(
            v6,
            &v16,
            v12);
        }
      }
      if ( v7 )
        RRasRoutingDomainConfig::`scalar deleting destructor'(v7, v8);
    }
    RtlReleaseResource(v5);
  }
  else
  {
    v15 = 87;
    if ( (_QWORD)xmmword_180071090 )
    {
      LOWORD(v28) = 0;
      FormatRRASErrorString(
        &v28,
        L"%hs(Line#%d): Invalid parameter.",
        "RRasConfigStore::DisableRoutingDomainOnRRAS",
        556);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180071090,
        &v28);
    }
  }
  v10 = v15;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v17);
  return v10;
}

```

## disassembly

```asm
0x18003b6d4  mov     [rsp-8+arg_10], rbx
0x18003b6d9  mov     [rsp-8+arg_18], rsi
0x18003b6de  push    rbp
0x18003b6df  push    rdi
0x18003b6e0  push    r14
0x18003b6e2  lea     rbp, [rsp-7D0h]
0x18003b6ea  sub     rsp, 8D0h
0x18003b6f1  mov     rax, cs:__security_cookie
0x18003b6f8  xor     rax, rsp
0x18003b6fb  mov     [rbp+7E0h+var_20], rax
0x18003b702  mov     rbx, rdx
0x18003b705  mov     rsi, rcx
0x18003b708  mov     [rsp+8E0h+var_8A0], 0
0x18003b710  xor     eax, eax
0x18003b712  mov     [rbp+7E0h+var_820], eax
0x18003b715  xor     edx, edx; Val
0x18003b717  mov     r8d, 7FCh; Size
0x18003b71d  lea     rcx, [rbp+7E0h+var_81C]; void *
0x18003b721  call    memset_0
0x18003b726  xor     eax, eax
0x18003b728  mov     [rbp+7E0h+var_848], eax
0x18003b72b  xorps   xmm0, xmm0
0x18003b72e  movups  [rbp+7E0h+var_844], xmm0
0x18003b732  movups  [rbp+7E0h+var_834], xmm0
0x18003b736  mov     [rbp+7E0h+var_824], eax
0x18003b739  movdqu  [rsp+8E0h+var_888], xmm0
0x18003b73f  mov     [rsp+8E0h+var_890], rax
0x18003b744  xorps   xmm1, xmm1
0x18003b747  movdqu  [rsp+8E0h+var_878], xmm1
0x18003b74d  mov     [rsp+8E0h+var_868], rax
0x18003b752  mov     [rbp+7E0h+var_860], 0FFFFFFFFh
0x18003b759  mov     [rbp+7E0h+var_85C], eax
0x18003b75c  cmp     qword ptr cs:xmmword_1800710A0+8, rax
0x18003b763  jz      short loc_18003B780
0x18003b765  mov     [rsp+8E0h+var_8C0], rbx; struct _GUID *
0x18003b76a  lea     r8, [rsp+8E0h+var_8A0]; unsigned int *
0x18003b76f  lea     rdx, aRrasconfigstor_12; "RRasConfigStore::DisableRoutingDomainOn"...
0x18003b776  lea     rcx, [rsp+8E0h+var_890]; this
0x18003b77b  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x18003b780  test    rbx, rbx
0x18003b783  jnz     short loc_18003B7E0
0x18003b785  mov     [rsp+8E0h+var_8A0], 57h ; 'W'
0x18003b78d  cmp     qword ptr cs:xmmword_180071090, rbx
0x18003b794  jz      loc_18003B8D5
0x18003b79a  xor     eax, eax
0x18003b79c  mov     word ptr [rbp+7E0h+var_820], ax
0x18003b7a0  mov     r9d, 22Ch
0x18003b7a6  lea     r8, aRrasconfigstor_31; "RRasConfigStore::DisableRoutingDomainOn"...
0x18003b7ad  lea     rdx, aHsLineDInvalid; "%hs(Line#%d): Invalid parameter."
0x18003b7b4  lea     rcx, [rbp+7E0h+var_820]
0x18003b7b8  call    FormatRRASErrorString
0x18003b7bd  lea     r8, [rbp+7E0h+var_820]
0x18003b7c1  mov     rdx, qword ptr cs:xmmword_180071090
0x18003b7c8  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003b7cf  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18003b7d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b7db  jmp     loc_18003B8D5
0x18003b7e0  lea     r14, [rsi+70h]
0x18003b7e4  mov     dl, 1; Wait
0x18003b7e6  mov     rcx, r14; Resource
0x18003b7e9  call    cs:__imp_RtlAcquireResourceExclusive
0x18003b7ef  lea     rdi, [rsi+10h]
0x18003b7f3  mov     r8, rbx
0x18003b7f6  lea     rdx, [rsp+8E0h+var_898]
0x18003b7fb  mov     rcx, rdi
0x18003b7fe  call    ?lower_bound@?$_Hash@V?$_Umap_traits@U_GUID@@PEAVRRasRoutingDomainConfig@@V?$_Hash_compare@U_GUID@@UGuidHash@@UGuidEquality@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@@4@$0A@@tr1@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@@2@@std@@@2@AEBU_GUID@@@Z; std::_Hash<std::tr1::_Umap_traits<_GUID,RRasRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>,0>>::lower_bound(_GUID const &)
0x18003b803  mov     rax, [rsp+8E0h+var_898]
0x18003b808  cmp     rax, [rsi+18h]
0x18003b80c  jnz     short loc_18003B889
0x18003b80e  mov     r9d, 490h
0x18003b814  mov     [rsp+8E0h+var_8A0], r9d
0x18003b819  cmp     qword ptr cs:xmmword_1800710A0, 0
0x18003b821  jz      loc_18003B8CC
0x18003b827  xor     eax, eax
0x18003b829  mov     word ptr [rbp+7E0h+var_820], ax
0x18003b82d  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18003b834  movdqu  [rbp+7E0h+var_858], xmm0
0x18003b839  mov     word ptr [rbp+7E0h+var_848], ax
0x18003b83d  lea     r8, aRrasconfigstor_12; "RRasConfigStore::DisableRoutingDomainOn"...
0x18003b844  lea     rdx, aSRoutingDomain_1; "%s: Routing domain not configured."
0x18003b84b  lea     rcx, [rbp+7E0h+var_820]
0x18003b84f  call    FormatRRASErrorString
0x18003b854  lea     rax, [rbp+7E0h+var_848]
0x18003b858  mov     [rsp+8E0h+var_8B8], rax
0x18003b85d  mov     [rsp+8E0h+var_8C0], 0
0x18003b866  mov     r9, rbx
0x18003b869  lea     r8, [rbp+7E0h+var_820]
0x18003b86d  mov     rdx, qword ptr cs:xmmword_1800710A0
0x18003b874  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003b87b  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18003b882  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b887  jmp     short loc_18003B8CC
0x18003b889  mov     rsi, [rax+20h]
0x18003b88d  mov     rcx, rsi; this
0x18003b890  call    ?RemoveConfigurationFromRegistry@RRasRoutingDomainConfig@@QEAAKXZ; RRasRoutingDomainConfig::RemoveConfigurationFromRegistry(void)
0x18003b895  mov     r8, rbx
0x18003b898  lea     rdx, [rbp+7E0h+var_858]
0x18003b89c  mov     rcx, rdi
0x18003b89f  call    ?equal_range@?$_Hash@V?$_Umap_traits@U_GUID@@PEAVRRasRoutingDomainConfig@@V?$_Hash_compare@U_GUID@@UGuidHash@@UGuidEquality@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@@4@$0A@@tr1@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@@2@@std@@@std@@V12@@2@AEBU_GUID@@@Z; std::_Hash<std::tr1::_Umap_traits<_GUID,RRasRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>,0>>::equal_range(_GUID const &)
0x18003b8a4  mov     rbx, qword ptr [rbp+7E0h+var_858]
0x18003b8a8  mov     rax, [rdi+8]
0x18003b8ac  cmp     rbx, [rax]
0x18003b8af  jnz     short loc_18003B90C
0x18003b8b1  cmp     qword ptr [rbp+7E0h+var_858+8], rax
0x18003b8b5  jnz     short loc_18003B90C
0x18003b8b7  mov     rcx, rdi
0x18003b8ba  call    ?clear@?$_Hash@V?$_Umap_traits@U_GUID@@PEAVRRasRoutingDomainConfig@@V?$_Hash_compare@U_GUID@@UGuidHash@@UGuidEquality@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@@4@$0A@@tr1@std@@@std@@QEAAXXZ; std::_Hash<std::tr1::_Umap_traits<_GUID,RRasRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>,0>>::clear(void)
0x18003b8bf  test    rsi, rsi
0x18003b8c2  jz      short loc_18003B8CC
0x18003b8c4  mov     rcx, rsi; this
0x18003b8c7  call    ??_GRRasRoutingDomainConfig@@QEAAPEAXI@Z; RRasRoutingDomainConfig::`scalar deleting destructor'(uint)
0x18003b8cc  mov     rcx, r14; Resource
0x18003b8cf  call    cs:__imp_RtlReleaseResource
0x18003b8d5  mov     ebx, [rsp+8E0h+var_8A0]
0x18003b8d9  lea     rcx, [rsp+8E0h+var_890]; this
0x18003b8de  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18003b8e3  mov     eax, ebx
0x18003b8e5  mov     rcx, [rbp+7E0h+var_20]
0x18003b8ec  xor     rcx, rsp; StackCookie
0x18003b8ef  call    __security_check_cookie
0x18003b8f4  lea     r11, [rsp+8E0h+var_10]
0x18003b8fc  mov     rbx, [r11+30h]
0x18003b900  mov     rsi, [r11+38h]
0x18003b904  mov     rsp, r11
0x18003b907  pop     r14
0x18003b909  pop     rdi
0x18003b90a  pop     rbp
0x18003b90b  retn
0x18003b90c  cmp     rbx, qword ptr [rbp+7E0h+var_858+8]
0x18003b910  jz      short loc_18003B8BF
0x18003b912  mov     r8, rbx
0x18003b915  mov     rbx, [rbx]
0x18003b918  lea     rdx, [rsp+8E0h+var_898]
0x18003b91d  mov     rcx, rdi
0x18003b920  call    ?erase@?$_Hash@V?$_Umap_traits@U_GUID@@PEAVRRasRoutingDomainConfig@@V?$_Hash_compare@U_GUID@@UGuidHash@@UGuidEquality@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@@4@$0A@@tr1@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@@2@@std@@@2@V?$_List_const_iterator@V?$_List_val@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@@2@@std@@@2@@Z; std::_Hash<std::tr1::_Umap_traits<_GUID,RRasRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>,0>>::erase(std::_List_const_iterator<std::_List_val<std::pair<_GUID const,RRasRoutingDomainConfig *>>>)
0x18003b925  jmp     short loc_18003B90C
```
