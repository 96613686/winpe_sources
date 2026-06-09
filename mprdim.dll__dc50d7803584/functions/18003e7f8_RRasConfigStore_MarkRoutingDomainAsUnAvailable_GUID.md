# RRasConfigStore::MarkRoutingDomainAsUnAvailable(_GUID *)

- ea: `0x18003e7f8`
- end: `0x18003e97b`
- name: `?MarkRoutingDomainAsUnAvailable@RRasConfigStore@@QEAAKPEAU_GUID@@@Z`
- size: `387`
- prototype: `unsigned int(RRasConfigStore *__hidden this, struct _GUID *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180036730`

## callees

- `0x18003e7f8`
- `0x180043e34`
- `0x18004583c`
- `0x1800459e8`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18003e93a`
- `ntdll!RtlReleaseResource` at `0x18003e943`
- `ntdll!RtlReleaseResource` at `0x18003e93a`
- `ntdll!RtlReleaseResource` at `0x18003e943`
- `ntdll!RtlAcquireResourceExclusive` at `0x18003e92a`
- `ntdll!RtlAcquireResourceExclusive` at `0x18003e92a`
- `ntdll!RtlAcquireResourceShared` at `0x18003e8ee`
- `ntdll!RtlAcquireResourceShared` at `0x18003e8ee`

## string_xrefs

- `0x18003e879`: `RRasConfigStore::MarkRoutingDomainAsUnAvailable`
- `0x18003e8ae`: `RRasConfigStore::MarkRoutingDomainAsUnAvailable`

## pseudocode

```c
__int64 __fastcall RRasConfigStore::MarkRoutingDomainAsUnAvailable(RRasConfigStore *this, struct _GUID *a2)
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
      L"RRasConfigStore::MarkRoutingDomainAsUnAvailable",
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
      *(_DWORD *)(v5 + 532) &= ~1u;
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
        "RRasConfigStore::MarkRoutingDomainAsUnAvailable",
        1327);
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
0x18003e7f8  mov     [rsp-8+arg_10], rbx
0x18003e7fd  push    rbp
0x18003e7fe  push    rsi
0x18003e7ff  push    rdi
0x18003e800  lea     rbp, [rsp-7A0h]
0x18003e808  sub     rsp, 8A0h
0x18003e80f  mov     rax, cs:__security_cookie
0x18003e816  xor     rax, rsp
0x18003e819  mov     [rbp+7B0h+var_20], rax
0x18003e820  mov     rbx, rdx
0x18003e823  mov     rdi, rcx
0x18003e826  xor     esi, esi
0x18003e828  mov     [rsp+8B0h+var_870], esi
0x18003e82c  mov     [rbp+7B0h+var_820], esi
0x18003e82f  xor     edx, edx; Val
0x18003e831  mov     r8d, 7FCh; Size
0x18003e837  lea     rcx, [rbp+7B0h+var_81C]; void *
0x18003e83b  call    memset_0
0x18003e840  xorps   xmm0, xmm0
0x18003e843  movdqu  [rsp+8B0h+var_858], xmm0
0x18003e849  mov     [rsp+8B0h+var_860], rsi
0x18003e84e  xorps   xmm1, xmm1
0x18003e851  movdqu  [rsp+8B0h+var_848], xmm1
0x18003e857  mov     [rsp+8B0h+var_838], rsi
0x18003e85c  mov     [rbp+7B0h+var_830], 0FFFFFFFFh
0x18003e863  mov     [rbp+7B0h+var_82C], esi
0x18003e866  cmp     qword ptr cs:xmmword_1800710A0+8, rsi
0x18003e86d  jz      short loc_18003E88A
0x18003e86f  mov     [rsp+8B0h+var_890], rbx; struct _GUID *
0x18003e874  lea     r8, [rsp+8B0h+var_870]; unsigned int *
0x18003e879  lea     rdx, aRrasconfigstor_11; "RRasConfigStore::MarkRoutingDomainAsUnA"...
0x18003e880  lea     rcx, [rsp+8B0h+var_860]; this
0x18003e885  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x18003e88a  test    rbx, rbx
0x18003e88d  jnz     short loc_18003E8E5
0x18003e88f  mov     [rsp+8B0h+var_870], 57h ; 'W'
0x18003e897  cmp     qword ptr cs:xmmword_180071090, rsi
0x18003e89e  jz      loc_18003E949
0x18003e8a4  mov     word ptr [rbp+7B0h+var_820], si
0x18003e8a8  mov     r9d, 52Fh
0x18003e8ae  lea     r8, aRrasconfigstor_9; "RRasConfigStore::MarkRoutingDomainAsUnA"...
0x18003e8b5  lea     rdx, aHsLineDInvalid; "%hs(Line#%d): Invalid parameter."
0x18003e8bc  lea     rcx, [rbp+7B0h+var_820]
0x18003e8c0  call    FormatRRASErrorString
0x18003e8c5  lea     r8, [rbp+7B0h+var_820]
0x18003e8c9  mov     rdx, qword ptr cs:xmmword_180071090
0x18003e8d0  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003e8d7  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18003e8de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e8e3  jmp     short loc_18003E949
0x18003e8e5  lea     rsi, [rdi+70h]
0x18003e8e9  mov     dl, 1; Wait
0x18003e8eb  mov     rcx, rsi; Resource
0x18003e8ee  call    cs:__imp_RtlAcquireResourceShared
0x18003e8f4  lea     rcx, [rdi+10h]
0x18003e8f8  mov     r8, rbx
0x18003e8fb  lea     rdx, [rsp+8B0h+var_868]
0x18003e900  call    ?lower_bound@?$_Hash@V?$_Umap_traits@U_GUID@@PEAVRRasRoutingDomainConfig@@V?$_Hash_compare@U_GUID@@UGuidHash@@UGuidEquality@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@@4@$0A@@tr1@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@@2@@std@@@2@AEBU_GUID@@@Z; std::_Hash<std::tr1::_Umap_traits<_GUID,RRasRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>,0>>::lower_bound(_GUID const &)
0x18003e905  mov     rax, [rsp+8B0h+var_868]
0x18003e90a  cmp     rax, [rdi+18h]
0x18003e90e  jnz     short loc_18003E91A
0x18003e910  mov     [rsp+8B0h+var_870], 490h
0x18003e918  jmp     short loc_18003E940
0x18003e91a  mov     rbx, [rax+20h]
0x18003e91e  lea     rdi, [rbx+2D8h]
0x18003e925  mov     dl, 1; Wait
0x18003e927  mov     rcx, rdi; Resource
0x18003e92a  call    cs:__imp_RtlAcquireResourceExclusive
0x18003e930  and     dword ptr [rbx+214h], 0FFFFFFFEh
0x18003e937  mov     rcx, rdi; Resource
0x18003e93a  call    cs:__imp_RtlReleaseResource
0x18003e940  mov     rcx, rsi; Resource
0x18003e943  call    cs:__imp_RtlReleaseResource
0x18003e949  mov     ebx, [rsp+8B0h+var_870]
0x18003e94d  lea     rcx, [rsp+8B0h+var_860]; this
0x18003e952  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18003e957  mov     eax, ebx
0x18003e959  mov     rcx, [rbp+7B0h+var_20]
0x18003e960  xor     rcx, rsp; StackCookie
0x18003e963  call    __security_check_cookie
0x18003e968  mov     rbx, [rsp+8B0h+arg_10]
0x18003e970  add     rsp, 8A0h
0x18003e977  pop     rdi
0x18003e978  pop     rsi
0x18003e979  pop     rbp
0x18003e97a  retn
```
