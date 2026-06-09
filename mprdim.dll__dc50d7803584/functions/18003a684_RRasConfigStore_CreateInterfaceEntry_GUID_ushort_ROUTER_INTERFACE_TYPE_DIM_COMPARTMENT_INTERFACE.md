# RRasConfigStore::CreateInterfaceEntry(_GUID *,ushort *,_ROUTER_INTERFACE_TYPE,_DIM_COMPARTMENT_INTERFACE *)

- ea: `0x18003a684`
- end: `0x18003a86d`
- name: `?CreateInterfaceEntry@RRasConfigStore@@QEAAKPEAU_GUID@@PEAGW4_ROUTER_INTERFACE_TYPE@@PEAU_DIM_COMPARTMENT_INTERFACE@@@Z`
- size: `489`
- prototype: `__int64 __fastcall(RRasConfigStore *this, struct _GUID *, BYTE *, enum _ROUTER_INTERFACE_TYPE, struct _DIM_COMPARTMENT_INTERFACE *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180035244`

## callees

- `0x18003a684`
- `0x18003a874`
- `0x180043e34`
- `0x18004583c`
- `0x180045ad4`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18003a831`
- `ntdll!RtlReleaseResource` at `0x18003a831`
- `ntdll!RtlAcquireResourceExclusive` at `0x18003a79d`
- `ntdll!RtlAcquireResourceExclusive` at `0x18003a79d`

## string_xrefs

- `0x18003a7e2`: `%s: Routing domain not configured.`
- `0x18003a723`: `RRasConfigStore::CreateInterfaceEntry`
- `0x18003a7db`: `RRasConfigStore::CreateInterfaceEntry`
- `0x18003a75b`: `RRasConfigStore::CreateInterfaceEntry`

## pseudocode

```c
__int64 __fastcall RRasConfigStore::CreateInterfaceEntry(
        RRasConfigStore *this,
        struct _GUID *a2,
        BYTE *a3,
        enum _ROUTER_INTERFACE_TYPE a4,
        struct _DIM_COMPARTMENT_INTERFACE *a5)
{
  void (*v8)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  unsigned int v9; // ebx
  unsigned int InterfaceEntry; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v12; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v13; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v14; // [rsp+38h] [rbp-C8h]
  __int128 v15; // [rsp+48h] [rbp-B8h]
  __int64 v16; // [rsp+58h] [rbp-A8h]
  int v17; // [rsp+60h] [rbp-A0h]
  int v18; // [rsp+64h] [rbp-9Ch]
  int v19; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v20[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  InterfaceEntry = 0;
  v19 = 0;
  memset_0(v20, 0, sizeof(v20));
  v14 = 0;
  v13 = 0;
  v15 = 0;
  v16 = 0;
  v17 = -1;
  v18 = 0;
  if ( *((_QWORD *)&xmmword_180071090 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v13,
      L"RRasConfigStore::CreateInterfaceEntry",
      &InterfaceEntry,
      v8);
  if ( a2 )
  {
    RtlAcquireResourceExclusive((PRTL_RESOURCE)((char *)this + 112), 1u);
    std::_Hash<std::tr1::_Umap_traits<_GUID,RRasRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>,0>>::lower_bound(
      (char *)this + 16,
      &v12,
      a2);
    if ( v12 == *((_QWORD *)this + 3) )
    {
      InterfaceEntry = 1168;
      if ( (_QWORD)xmmword_180071090 )
      {
        LOWORD(v19) = 0;
        FormatRRASErrorString(&v19, L"%s: Routing domain not configured.", L"RRasConfigStore::CreateInterfaceEntry");
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
          gCfgStoreEtwContext,
          xmmword_180071090,
          &v19);
      }
    }
    else
    {
      InterfaceEntry = RRasRoutingDomainConfig::CreateInterfaceEntry(
                         *(RRasRoutingDomainConfig **)(v12 + 32),
                         a3,
                         ROUTER_IF_TYPE_DEDICATED,
                         a5);
    }
    RtlReleaseResource((PRTL_RESOURCE)((char *)this + 112));
  }
  else
  {
    InterfaceEntry = 87;
    if ( (_QWORD)xmmword_180071090 )
    {
      LOWORD(v19) = 0;
      FormatRRASErrorString(&v19, L"%hs(Line#%d): Invalid parameter.", "RRasConfigStore::CreateInterfaceEntry", 639);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180071090,
        &v19);
    }
  }
  v9 = InterfaceEntry;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v13);
  return v9;
}

```

## disassembly

```asm
0x18003a684  mov     [rsp-8+arg_18], rbx
0x18003a689  push    rbp
0x18003a68a  push    rsi
0x18003a68b  push    rdi
0x18003a68c  push    r14
0x18003a68e  push    r15
0x18003a690  lea     rbp, [rsp-780h]
0x18003a698  sub     rsp, 880h
0x18003a69f  mov     rax, cs:__security_cookie
0x18003a6a6  xor     rax, rsp
0x18003a6a9  mov     [rbp+7A0h+var_30], rax
0x18003a6b0  mov     r14, r8
0x18003a6b3  mov     rsi, rdx
0x18003a6b6  mov     rdi, rcx
0x18003a6b9  mov     r15, [rbp+7A0h+arg_20]
0x18003a6c0  mov     [rsp+8A0h+var_880], 0
0x18003a6c8  xor     eax, eax
0x18003a6ca  mov     [rsp+8A0h+var_830], eax
0x18003a6ce  xor     edx, edx; Val
0x18003a6d0  mov     r8d, 7FCh; Size
0x18003a6d6  lea     rcx, [rsp+8A0h+var_82C]; void *
0x18003a6db  call    memset_0
0x18003a6e0  xorps   xmm0, xmm0
0x18003a6e3  movdqu  [rsp+8A0h+var_868], xmm0
0x18003a6e9  mov     [rsp+8A0h+var_870], 0
0x18003a6f2  xorps   xmm1, xmm1
0x18003a6f5  movdqu  [rsp+8A0h+var_858], xmm1
0x18003a6fb  mov     [rsp+8A0h+var_848], 0
0x18003a704  mov     [rsp+8A0h+var_840], 0FFFFFFFFh
0x18003a70c  mov     [rsp+8A0h+var_83C], 0
0x18003a714  cmp     qword ptr cs:xmmword_180071090+8, 0
0x18003a71c  jz      short loc_18003A734
0x18003a71e  lea     r8, [rsp+8A0h+var_880]; unsigned int *
0x18003a723  lea     rdx, aRrasconfigstor_18; "RRasConfigStore::CreateInterfaceEntry"
0x18003a72a  lea     rcx, [rsp+8A0h+var_870]; this
0x18003a72f  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x18003a734  test    rsi, rsi
0x18003a737  jnz     short loc_18003A797
0x18003a739  mov     [rsp+8A0h+var_880], 57h ; 'W'
0x18003a741  cmp     qword ptr cs:xmmword_180071090, rsi
0x18003a748  jz      loc_18003A837
0x18003a74e  xor     eax, eax
0x18003a750  mov     word ptr [rsp+8A0h+var_830], ax
0x18003a755  mov     r9d, 27Fh
0x18003a75b  lea     r8, aRrasconfigstor_36; "RRasConfigStore::CreateInterfaceEntry"
0x18003a762  lea     rdx, aHsLineDInvalid; "%hs(Line#%d): Invalid parameter."
0x18003a769  lea     rcx, [rsp+8A0h+var_830]
0x18003a76e  call    FormatRRASErrorString
0x18003a773  lea     r8, [rsp+8A0h+var_830]
0x18003a778  mov     rdx, qword ptr cs:xmmword_180071090
0x18003a77f  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003a786  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18003a78d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a792  jmp     loc_18003A837
0x18003a797  mov     dl, 1; Wait
0x18003a799  lea     rcx, [rdi+70h]; Resource
0x18003a79d  call    cs:__imp_RtlAcquireResourceExclusive
0x18003a7a3  lea     rcx, [rdi+10h]
0x18003a7a7  mov     r8, rsi
0x18003a7aa  lea     rdx, [rsp+8A0h+var_878]
0x18003a7af  call    ?lower_bound@?$_Hash@V?$_Umap_traits@U_GUID@@PEAVRRasRoutingDomainConfig@@V?$_Hash_compare@U_GUID@@UGuidHash@@UGuidEquality@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@@4@$0A@@tr1@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@@2@@std@@@2@AEBU_GUID@@@Z; std::_Hash<std::tr1::_Umap_traits<_GUID,RRasRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>,0>>::lower_bound(_GUID const &)
0x18003a7b4  mov     rcx, [rsp+8A0h+var_878]
0x18003a7b9  cmp     rcx, [rdi+18h]
0x18003a7bd  jnz     short loc_18003A814
0x18003a7bf  mov     r9d, 490h
0x18003a7c5  mov     [rsp+8A0h+var_880], r9d
0x18003a7ca  cmp     qword ptr cs:xmmword_180071090, 0
0x18003a7d2  jz      short loc_18003A82D
0x18003a7d4  xor     eax, eax
0x18003a7d6  mov     word ptr [rsp+8A0h+var_830], ax
0x18003a7db  lea     r8, aRrasconfigstor_18; "RRasConfigStore::CreateInterfaceEntry"
0x18003a7e2  lea     rdx, aSRoutingDomain_1; "%s: Routing domain not configured."
0x18003a7e9  lea     rcx, [rsp+8A0h+var_830]
0x18003a7ee  call    FormatRRASErrorString
0x18003a7f3  lea     r8, [rsp+8A0h+var_830]
0x18003a7f8  mov     rdx, qword ptr cs:xmmword_180071090
0x18003a7ff  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003a806  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18003a80d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a812  jmp     short loc_18003A82D
0x18003a814  mov     r9, r15; struct _DIM_COMPARTMENT_INTERFACE *
0x18003a817  mov     r8d, 3; enum _ROUTER_INTERFACE_TYPE
0x18003a81d  mov     rdx, r14; lpData
0x18003a820  mov     rcx, [rcx+20h]; this
0x18003a824  call    ?CreateInterfaceEntry@RRasRoutingDomainConfig@@QEAAKPEAGW4_ROUTER_INTERFACE_TYPE@@PEAU_DIM_COMPARTMENT_INTERFACE@@@Z; RRasRoutingDomainConfig::CreateInterfaceEntry(ushort *,_ROUTER_INTERFACE_TYPE,_DIM_COMPARTMENT_INTERFACE *)
0x18003a829  mov     [rsp+8A0h+var_880], eax
0x18003a82d  lea     rcx, [rdi+70h]; Resource
0x18003a831  call    cs:__imp_RtlReleaseResource
0x18003a837  mov     ebx, [rsp+8A0h+var_880]
0x18003a83b  lea     rcx, [rsp+8A0h+var_870]; this
0x18003a840  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18003a845  mov     eax, ebx
0x18003a847  mov     rcx, [rbp+7A0h+var_30]
0x18003a84e  xor     rcx, rsp; StackCookie
0x18003a851  call    __security_check_cookie
0x18003a856  mov     rbx, [rsp+8A0h+arg_18]
0x18003a85e  add     rsp, 880h
0x18003a865  pop     r15
0x18003a867  pop     r14
0x18003a869  pop     rdi
0x18003a86a  pop     rsi
0x18003a86b  pop     rbp
0x18003a86c  retn
```
