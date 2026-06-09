# RRasConfigStore::MarkRoutingDomainAsAvailable(_GUID *)

- ea: `0x18003e66c`
- end: `0x18003e7ef`
- name: `?MarkRoutingDomainAsAvailable@RRasConfigStore@@QEAAKPEAU_GUID@@@Z`
- size: `387`
- prototype: `unsigned int(RRasConfigStore *__hidden this, struct _GUID *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003653c`

## callees

- `0x18003e66c`
- `0x180043e34`
- `0x18004583c`
- `0x1800459e8`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18003e7ae`
- `ntdll!RtlReleaseResource` at `0x18003e7b7`
- `ntdll!RtlReleaseResource` at `0x18003e7ae`
- `ntdll!RtlReleaseResource` at `0x18003e7b7`
- `ntdll!RtlAcquireResourceExclusive` at `0x18003e79e`
- `ntdll!RtlAcquireResourceExclusive` at `0x18003e79e`
- `ntdll!RtlAcquireResourceShared` at `0x18003e762`
- `ntdll!RtlAcquireResourceShared` at `0x18003e762`

## string_xrefs

- `0x18003e6ed`: `RRasConfigStore::MarkRoutingDomainAsAvailable`
- `0x18003e722`: `RRasConfigStore::MarkRoutingDomainAsAvailable`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RRasConfigStore::MarkRoutingDomainAsAvailable(RRasConfigStore *this, struct _GUID *a2)
{
  void (*v4)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  __int64 v5; // rbx
  unsigned int v6; // ebx
  unsigned __int16 *v8; // [rsp+28h] [rbp-D8h]
  unsigned int v9; // [rsp+30h] [rbp-D0h]
  unsigned int v10; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v11; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v12; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v13; // [rsp+58h] [rbp-A8h]
  __int128 v14; // [rsp+68h] [rbp-98h]
  __int64 v15; // [rsp+78h] [rbp-88h]
  int v16; // [rsp+80h] [rbp-80h]
  int v17; // [rsp+84h] [rbp-7Ch]
  int v18; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v19[2044]; // [rsp+94h] [rbp-6Ch] BYREF

  v10 = 0;
  v18 = 0;
  memset_0(v19, 0, sizeof(v19));
  v13 = 0;
  v12 = 0;
  v14 = 0;
  v15 = 0;
  v16 = -1;
  v17 = 0;
  if ( *((_QWORD *)&xmmword_1800710A0 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v12,
      L"RRasConfigStore::MarkRoutingDomainAsAvailable",
      &v10,
      v4,
      a2,
      v8,
      v9);
  if ( a2 )
  {
    RtlAcquireResourceShared((PRTL_RESOURCE)((char *)this + 112), 1u);
    std::_Hash<std::tr1::_Umap_traits<_GUID,RRasRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>,0>>::lower_bound(
      (char *)this + 16,
      &v11,
      a2);
    if ( v11 == *((_QWORD *)this + 3) )
    {
      v10 = 1168;
    }
    else
    {
      v5 = *(_QWORD *)(v11 + 32);
      RtlAcquireResourceExclusive((PRTL_RESOURCE)(v5 + 728), 1u);
      *(_DWORD *)(v5 + 532) |= 1u;
      RtlReleaseResource((PRTL_RESOURCE)(v5 + 728));
    }
    RtlReleaseResource((PRTL_RESOURCE)((char *)this + 112));
  }
  else
  {
    v10 = 87;
    if ( (_QWORD)xmmword_180071090 )
    {
      LOWORD(v18) = 0;
      FormatRRASErrorString(
        &v18,
        L"%hs(Line#%d): Invalid parameter.",
        "RRasConfigStore::MarkRoutingDomainAsAvailable",
        1285);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180071090,
        &v18);
    }
  }
  v6 = v10;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v12);
  return v6;
}

```

## disassembly

```asm
0x18003e66c  mov     [rsp-8+arg_10], rbx
0x18003e671  push    rbp
0x18003e672  push    rsi
0x18003e673  push    rdi
0x18003e674  lea     rbp, [rsp-7A0h]
0x18003e67c  sub     rsp, 8A0h
0x18003e683  mov     rax, cs:__security_cookie
0x18003e68a  xor     rax, rsp
0x18003e68d  mov     [rbp+7B0h+var_20], rax
0x18003e694  mov     rbx, rdx
0x18003e697  mov     rdi, rcx
0x18003e69a  xor     esi, esi
0x18003e69c  mov     [rsp+8B0h+var_870], esi
0x18003e6a0  mov     [rbp+7B0h+var_820], esi
0x18003e6a3  xor     edx, edx; Val
0x18003e6a5  mov     r8d, 7FCh; Size
0x18003e6ab  lea     rcx, [rbp+7B0h+var_81C]; void *
0x18003e6af  call    memset_0
0x18003e6b4  xorps   xmm0, xmm0
0x18003e6b7  movdqu  [rsp+8B0h+var_858], xmm0
0x18003e6bd  mov     [rsp+8B0h+var_860], rsi
0x18003e6c2  xorps   xmm1, xmm1
0x18003e6c5  movdqu  [rsp+8B0h+var_848], xmm1
0x18003e6cb  mov     [rsp+8B0h+var_838], rsi
0x18003e6d0  mov     [rbp+7B0h+var_830], 0FFFFFFFFh
0x18003e6d7  mov     [rbp+7B0h+var_82C], esi
0x18003e6da  cmp     qword ptr cs:xmmword_1800710A0+8, rsi
0x18003e6e1  jz      short loc_18003E6FE
0x18003e6e3  mov     [rsp+8B0h+var_890], rbx; struct _GUID *
0x18003e6e8  lea     r8, [rsp+8B0h+var_870]; unsigned int *
0x18003e6ed  lea     rdx, aRrasconfigstor_22; "RRasConfigStore::MarkRoutingDomainAsAva"...
0x18003e6f4  lea     rcx, [rsp+8B0h+var_860]; this
0x18003e6f9  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x18003e6fe  test    rbx, rbx
0x18003e701  jnz     short loc_18003E759
0x18003e703  mov     [rsp+8B0h+var_870], 57h ; 'W'
0x18003e70b  cmp     qword ptr cs:xmmword_180071090, rsi
0x18003e712  jz      loc_18003E7BD
0x18003e718  mov     word ptr [rbp+7B0h+var_820], si
0x18003e71c  mov     r9d, 505h
0x18003e722  lea     r8, aRrasconfigstor_3; "RRasConfigStore::MarkRoutingDomainAsAva"...
0x18003e729  lea     rdx, aHsLineDInvalid; "%hs(Line#%d): Invalid parameter."
0x18003e730  lea     rcx, [rbp+7B0h+var_820]
0x18003e734  call    FormatRRASErrorString
0x18003e739  lea     r8, [rbp+7B0h+var_820]
0x18003e73d  mov     rdx, qword ptr cs:xmmword_180071090
0x18003e744  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003e74b  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18003e752  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e757  jmp     short loc_18003E7BD
0x18003e759  lea     rsi, [rdi+70h]
0x18003e75d  mov     dl, 1; Wait
0x18003e75f  mov     rcx, rsi; Resource
0x18003e762  call    cs:__imp_RtlAcquireResourceShared
0x18003e768  lea     rcx, [rdi+10h]
0x18003e76c  mov     r8, rbx
0x18003e76f  lea     rdx, [rsp+8B0h+var_868]
0x18003e774  call    ?lower_bound@?$_Hash@V?$_Umap_traits@U_GUID@@PEAVRRasRoutingDomainConfig@@V?$_Hash_compare@U_GUID@@UGuidHash@@UGuidEquality@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@@4@$0A@@tr1@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@@2@@std@@@2@AEBU_GUID@@@Z; std::_Hash<std::tr1::_Umap_traits<_GUID,RRasRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>,0>>::lower_bound(_GUID const &)
0x18003e779  mov     rax, [rsp+8B0h+var_868]
0x18003e77e  cmp     rax, [rdi+18h]
0x18003e782  jnz     short loc_18003E78E
0x18003e784  mov     [rsp+8B0h+var_870], 490h
0x18003e78c  jmp     short loc_18003E7B4
0x18003e78e  mov     rbx, [rax+20h]
0x18003e792  lea     rdi, [rbx+2D8h]
0x18003e799  mov     dl, 1; Wait
0x18003e79b  mov     rcx, rdi; Resource
0x18003e79e  call    cs:__imp_RtlAcquireResourceExclusive
0x18003e7a4  or      dword ptr [rbx+214h], 1
0x18003e7ab  mov     rcx, rdi; Resource
0x18003e7ae  call    cs:__imp_RtlReleaseResource
0x18003e7b4  mov     rcx, rsi; Resource
0x18003e7b7  call    cs:__imp_RtlReleaseResource
0x18003e7bd  mov     ebx, [rsp+8B0h+var_870]
0x18003e7c1  lea     rcx, [rsp+8B0h+var_860]; this
0x18003e7c6  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18003e7cb  mov     eax, ebx
0x18003e7cd  mov     rcx, [rbp+7B0h+var_20]
0x18003e7d4  xor     rcx, rsp; StackCookie
0x18003e7d7  call    __security_check_cookie
0x18003e7dc  mov     rbx, [rsp+8B0h+arg_10]
0x18003e7e4  add     rsp, 8A0h
0x18003e7eb  pop     rdi
0x18003e7ec  pop     rsi
0x18003e7ed  pop     rbp
0x18003e7ee  retn
```
