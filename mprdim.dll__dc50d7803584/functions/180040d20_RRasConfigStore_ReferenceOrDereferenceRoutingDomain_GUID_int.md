# RRasConfigStore::ReferenceOrDereferenceRoutingDomain(_GUID *,int)

- ea: `0x180040d20`
- end: `0x180040ea8`
- name: `?ReferenceOrDereferenceRoutingDomain@RRasConfigStore@@QEAAKPEAU_GUID@@H@Z`
- size: `392`
- prototype: `unsigned int(RRasConfigStore *__hidden this, struct _GUID *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003748c`

## callees

- `0x180040d20`
- `0x180040eb0`
- `0x180043e34`
- `0x18004583c`
- `0x1800459e8`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180040e6c`
- `ntdll!RtlReleaseResource` at `0x180040e75`
- `ntdll!RtlReleaseResource` at `0x180040e6c`
- `ntdll!RtlReleaseResource` at `0x180040e75`
- `ntdll!RtlAcquireResourceExclusive` at `0x180040e54`
- `ntdll!RtlAcquireResourceExclusive` at `0x180040e54`
- `ntdll!RtlAcquireResourceShared` at `0x180040e18`
- `ntdll!RtlAcquireResourceShared` at `0x180040e18`

## string_xrefs

- `0x180040da3`: `RRasConfigStore::ReferenceOrDereferenceRoutingDomain`
- `0x180040dd8`: `RRasConfigStore::ReferenceOrDereferenceRoutingDomain`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RRasConfigStore::ReferenceOrDereferenceRoutingDomain(
        RRasConfigStore *this,
        struct _GUID *a2,
        int a3)
{
  void (*v6)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  __int64 v7; // rbx
  unsigned int v8; // ebx
  unsigned __int16 *v10; // [rsp+28h] [rbp-D8h]
  unsigned int v11; // [rsp+30h] [rbp-D0h]
  unsigned int v12; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v13; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v14; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v15; // [rsp+58h] [rbp-A8h]
  __int128 v16; // [rsp+68h] [rbp-98h]
  __int64 v17; // [rsp+78h] [rbp-88h]
  int v18; // [rsp+80h] [rbp-80h]
  int v19; // [rsp+84h] [rbp-7Ch]
  int v20; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v21[2044]; // [rsp+94h] [rbp-6Ch] BYREF

  v12 = 0;
  v20 = 0;
  memset_0(v21, 0, sizeof(v21));
  v15 = 0;
  v14 = 0;
  v16 = 0;
  v17 = 0;
  v18 = -1;
  v19 = 0;
  if ( *((_QWORD *)&xmmword_1800710A0 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v14,
      L"RRasConfigStore::ReferenceOrDereferenceRoutingDomain",
      &v12,
      v6,
      a2,
      v10,
      v11);
  if ( a2 )
  {
    RtlAcquireResourceShared((PRTL_RESOURCE)((char *)this + 112), 1u);
    std::_Hash<std::tr1::_Umap_traits<_GUID,RRasRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>,0>>::lower_bound(
      (char *)this + 16,
      &v13,
      a2);
    if ( v13 == *((_QWORD *)this + 3) )
    {
      v12 = 1168;
    }
    else
    {
      v7 = *(_QWORD *)(v13 + 32);
      RtlAcquireResourceExclusive((PRTL_RESOURCE)(v7 + 728), 1u);
      v12 = RRasRoutingDomainConfig::ReferenceOrDereferenceRoutingDomain((RRasRoutingDomainConfig *)v7, a3);
      RtlReleaseResource((PRTL_RESOURCE)(v7 + 728));
    }
    RtlReleaseResource((PRTL_RESOURCE)((char *)this + 112));
  }
  else
  {
    v12 = 87;
    if ( (_QWORD)xmmword_180071090 )
    {
      LOWORD(v20) = 0;
      FormatRRASErrorString(
        &v20,
        L"%hs(Line#%d): Invalid parameter.",
        "RRasConfigStore::ReferenceOrDereferenceRoutingDomain",
        1062);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180071090,
        &v20);
    }
  }
  v8 = v12;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v14);
  return v8;
}

```

## disassembly

```asm
0x180040d20  push    rbp
0x180040d22  push    rbx
0x180040d23  push    rsi
0x180040d24  push    rdi
0x180040d25  push    r14
0x180040d27  lea     rbp, [rsp-7A0h]
0x180040d2f  sub     rsp, 8A0h
0x180040d36  mov     rax, cs:__security_cookie
0x180040d3d  xor     rax, rsp
0x180040d40  mov     [rbp+7C0h+var_30], rax
0x180040d47  mov     r14d, r8d
0x180040d4a  mov     rbx, rdx
0x180040d4d  mov     rdi, rcx
0x180040d50  xor     esi, esi
0x180040d52  mov     [rsp+8C0h+var_880], esi
0x180040d56  mov     [rbp+7C0h+var_830], esi
0x180040d59  xor     edx, edx; Val
0x180040d5b  mov     r8d, 7FCh; Size
0x180040d61  lea     rcx, [rbp+7C0h+var_82C]; void *
0x180040d65  call    memset_0
0x180040d6a  xorps   xmm0, xmm0
0x180040d6d  movdqu  [rsp+8C0h+var_868], xmm0
0x180040d73  mov     [rsp+8C0h+var_870], rsi
0x180040d78  xorps   xmm1, xmm1
0x180040d7b  movdqu  [rsp+8C0h+var_858], xmm1
0x180040d81  mov     [rsp+8C0h+var_848], rsi
0x180040d86  mov     [rbp+7C0h+var_840], 0FFFFFFFFh
0x180040d8d  mov     [rbp+7C0h+var_83C], esi
0x180040d90  cmp     qword ptr cs:xmmword_1800710A0+8, rsi
0x180040d97  jz      short loc_180040DB4
0x180040d99  mov     [rsp+8C0h+var_8A0], rbx; struct _GUID *
0x180040d9e  lea     r8, [rsp+8C0h+var_880]; unsigned int *
0x180040da3  lea     rdx, aRrasconfigstor_29; "RRasConfigStore::ReferenceOrDereference"...
0x180040daa  lea     rcx, [rsp+8C0h+var_870]; this
0x180040daf  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x180040db4  test    rbx, rbx
0x180040db7  jnz     short loc_180040E0F
0x180040db9  mov     [rsp+8C0h+var_880], 57h ; 'W'
0x180040dc1  cmp     qword ptr cs:xmmword_180071090, rsi
0x180040dc8  jz      loc_180040E7B
0x180040dce  mov     word ptr [rbp+7C0h+var_830], si
0x180040dd2  mov     r9d, 426h
0x180040dd8  lea     r8, aRrasconfigstor_5; "RRasConfigStore::ReferenceOrDereference"...
0x180040ddf  lea     rdx, aHsLineDInvalid; "%hs(Line#%d): Invalid parameter."
0x180040de6  lea     rcx, [rbp+7C0h+var_830]
0x180040dea  call    FormatRRASErrorString
0x180040def  lea     r8, [rbp+7C0h+var_830]
0x180040df3  mov     rdx, qword ptr cs:xmmword_180071090
0x180040dfa  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180040e01  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180040e08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040e0d  jmp     short loc_180040E7B
0x180040e0f  lea     rsi, [rdi+70h]
0x180040e13  mov     dl, 1; Wait
0x180040e15  mov     rcx, rsi; Resource
0x180040e18  call    cs:__imp_RtlAcquireResourceShared
0x180040e1e  lea     rcx, [rdi+10h]
0x180040e22  mov     r8, rbx
0x180040e25  lea     rdx, [rsp+8C0h+var_878]
0x180040e2a  call    ?lower_bound@?$_Hash@V?$_Umap_traits@U_GUID@@PEAVRRasRoutingDomainConfig@@V?$_Hash_compare@U_GUID@@UGuidHash@@UGuidEquality@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@@4@$0A@@tr1@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@@2@@std@@@2@AEBU_GUID@@@Z; std::_Hash<std::tr1::_Umap_traits<_GUID,RRasRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>,0>>::lower_bound(_GUID const &)
0x180040e2f  mov     rax, [rsp+8C0h+var_878]
0x180040e34  cmp     rax, [rdi+18h]
0x180040e38  jnz     short loc_180040E44
0x180040e3a  mov     [rsp+8C0h+var_880], 490h
0x180040e42  jmp     short loc_180040E72
0x180040e44  mov     rbx, [rax+20h]
0x180040e48  lea     rdi, [rbx+2D8h]
0x180040e4f  mov     dl, 1; Wait
0x180040e51  mov     rcx, rdi; Resource
0x180040e54  call    cs:__imp_RtlAcquireResourceExclusive
0x180040e5a  mov     edx, r14d; int
0x180040e5d  mov     rcx, rbx; this
0x180040e60  call    ?ReferenceOrDereferenceRoutingDomain@RRasRoutingDomainConfig@@QEAAKH@Z; RRasRoutingDomainConfig::ReferenceOrDereferenceRoutingDomain(int)
0x180040e65  mov     [rsp+8C0h+var_880], eax
0x180040e69  mov     rcx, rdi; Resource
0x180040e6c  call    cs:__imp_RtlReleaseResource
0x180040e72  mov     rcx, rsi; Resource
0x180040e75  call    cs:__imp_RtlReleaseResource
0x180040e7b  mov     ebx, [rsp+8C0h+var_880]
0x180040e7f  lea     rcx, [rsp+8C0h+var_870]; this
0x180040e84  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180040e89  mov     eax, ebx
0x180040e8b  mov     rcx, [rbp+7C0h+var_30]
0x180040e92  xor     rcx, rsp; StackCookie
0x180040e95  call    __security_check_cookie
0x180040e9a  add     rsp, 8A0h
0x180040ea1  pop     r14
0x180040ea3  pop     rdi
0x180040ea4  pop     rsi
0x180040ea5  pop     rbx
0x180040ea6  pop     rbp
0x180040ea7  retn
```
