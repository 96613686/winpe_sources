# RRasConfigStore::AcquireRoutingDomainHandle(_GUID *,ulong,void * *)

- ea: `0x180038be8`
- end: `0x180038db9`
- name: `?AcquireRoutingDomainHandle@RRasConfigStore@@QEAAKPEAU_GUID@@KPEAPEAX@Z`
- size: `465`
- prototype: `__int64 __fastcall(RRasConfigStore *this, struct _GUID *, char, void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180034cf0`

## callees

- `0x180038be8`
- `0x180043e34`
- `0x18004583c`
- `0x1800459e8`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180038d7d`
- `ntdll!RtlReleaseResource` at `0x180038d7d`
- `ntdll!RtlAcquireResourceExclusive` at `0x180038d43`
- `ntdll!RtlAcquireResourceExclusive` at `0x180038d43`
- `ntdll!RtlAcquireResourceShared` at `0x180038d0e`
- `ntdll!RtlAcquireResourceShared` at `0x180038d5b`
- `ntdll!RtlAcquireResourceShared` at `0x180038d0e`
- `ntdll!RtlAcquireResourceShared` at `0x180038d5b`

## string_xrefs

- `0x180038c84`: `RRasConfigStore::AcquireRoutingDomainHandle`
- `0x180038cc2`: `RRasConfigStore::AcquireRoutingDomainHandle`

## pseudocode

```c
__int64 __fastcall RRasConfigStore::AcquireRoutingDomainHandle(
        RRasConfigStore *this,
        struct _GUID *a2,
        char a3,
        void **a4)
{
  void (*v8)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  int v9; // edi
  __int64 v10; // rsi
  unsigned int v11; // ebx
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
  int v23; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v24[2044]; // [rsp+94h] [rbp-6Ch] BYREF

  v15 = 0;
  v23 = 0;
  memset_0(v24, 0, sizeof(v24));
  v18 = 0;
  v17 = 0;
  v19 = 0;
  v20 = 0;
  v21 = -1;
  v22 = 0;
  if ( *((_QWORD *)&xmmword_1800710A0 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v17,
      L"RRasConfigStore::AcquireRoutingDomainHandle",
      &v15,
      v8,
      a2,
      v13,
      v14);
  if ( a4 || a2 || (a3 & 3) != 0 )
  {
    *a4 = 0;
    v9 = 1;
    RtlAcquireResourceShared((PRTL_RESOURCE)((char *)this + 112), 1u);
    std::_Hash<std::tr1::_Umap_traits<_GUID,RRasRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>,0>>::lower_bound(
      (char *)this + 16,
      &v16,
      a2);
    if ( v16 == *((_QWORD *)this + 3) )
    {
      v15 = 1168;
    }
    else
    {
      v10 = *(_QWORD *)(v16 + 32);
      if ( (a3 & 1) != 0 )
      {
        RtlAcquireResourceExclusive((PRTL_RESOURCE)(v10 + 728), 1u);
      }
      else if ( (a3 & 2) != 0 )
      {
        RtlAcquireResourceShared((PRTL_RESOURCE)(v10 + 728), 1u);
      }
      *a4 = (void *)v10;
    }
  }
  else
  {
    v15 = 87;
    if ( (_QWORD)xmmword_180071090 )
    {
      LOWORD(v23) = 0;
      FormatRRASErrorString(
        &v23,
        L"%hs(Line#%d): Invalid parameter.",
        "RRasConfigStore::AcquireRoutingDomainHandle",
        854);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180071090,
        &v23);
    }
    v9 = 0;
  }
  if ( v15 && v9 )
    RtlReleaseResource((PRTL_RESOURCE)((char *)this + 112));
  v11 = v15;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v17);
  return v11;
}

```

## disassembly

```asm
0x180038be8  mov     [rsp-8+arg_10], rbx
0x180038bed  push    rbp
0x180038bee  push    rsi
0x180038bef  push    rdi
0x180038bf0  push    r14
0x180038bf2  push    r15
0x180038bf4  lea     rbp, [rsp-7A0h]
0x180038bfc  sub     rsp, 8A0h
0x180038c03  mov     rax, cs:__security_cookie
0x180038c0a  xor     rax, rsp
0x180038c0d  mov     [rbp+7C0h+var_30], rax
0x180038c14  mov     r15, r9
0x180038c17  mov     r14d, r8d
0x180038c1a  mov     rsi, rdx
0x180038c1d  mov     rbx, rcx
0x180038c20  mov     [rsp+8C0h+var_880], 0
0x180038c28  xor     eax, eax
0x180038c2a  mov     [rbp+7C0h+var_830], eax
0x180038c2d  xor     edx, edx; Val
0x180038c2f  mov     r8d, 7FCh; Size
0x180038c35  lea     rcx, [rbp+7C0h+var_82C]; void *
0x180038c39  call    memset_0
0x180038c3e  xorps   xmm0, xmm0
0x180038c41  movdqu  [rsp+8C0h+var_868], xmm0
0x180038c47  mov     [rsp+8C0h+var_870], 0
0x180038c50  xorps   xmm1, xmm1
0x180038c53  movdqu  [rsp+8C0h+var_858], xmm1
0x180038c59  mov     [rsp+8C0h+var_848], 0
0x180038c62  mov     [rbp+7C0h+var_840], 0FFFFFFFFh
0x180038c69  mov     [rbp+7C0h+var_83C], 0
0x180038c70  cmp     qword ptr cs:xmmword_1800710A0+8, 0
0x180038c78  jz      short loc_180038C95
0x180038c7a  mov     [rsp+8C0h+var_8A0], rsi; struct _GUID *
0x180038c7f  lea     r8, [rsp+8C0h+var_880]; unsigned int *
0x180038c84  lea     rdx, aRrasconfigstor_23; "RRasConfigStore::AcquireRoutingDomainHa"...
0x180038c8b  lea     rcx, [rsp+8C0h+var_870]; this
0x180038c90  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x180038c95  test    r15, r15
0x180038c98  jnz     short loc_180038CFB
0x180038c9a  test    rsi, rsi
0x180038c9d  jnz     short loc_180038CFB
0x180038c9f  test    r14b, 3
0x180038ca3  jnz     short loc_180038CFB
0x180038ca5  mov     [rsp+8C0h+var_880], 57h ; 'W'
0x180038cad  cmp     qword ptr cs:xmmword_180071090, rsi
0x180038cb4  jz      short loc_180038CF7
0x180038cb6  xor     eax, eax
0x180038cb8  mov     word ptr [rbp+7C0h+var_830], ax
0x180038cbc  mov     r9d, 356h
0x180038cc2  lea     r8, aRrasconfigstor_35; "RRasConfigStore::AcquireRoutingDomainHa"...
0x180038cc9  lea     rdx, aHsLineDInvalid; "%hs(Line#%d): Invalid parameter."
0x180038cd0  lea     rcx, [rbp+7C0h+var_830]
0x180038cd4  call    FormatRRASErrorString
0x180038cd9  lea     r8, [rbp+7C0h+var_830]
0x180038cdd  mov     rdx, qword ptr cs:xmmword_180071090
0x180038ce4  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180038ceb  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180038cf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038cf7  xor     edi, edi
0x180038cf9  jmp     short loc_180038D6E
0x180038cfb  mov     qword ptr [r15], 0
0x180038d02  lea     rcx, [rbx+70h]; Resource
0x180038d06  mov     edi, 1
0x180038d0b  mov     dl, dil; Wait
0x180038d0e  call    cs:__imp_RtlAcquireResourceShared
0x180038d14  lea     rcx, [rbx+10h]
0x180038d18  mov     r8, rsi
0x180038d1b  lea     rdx, [rsp+8C0h+var_878]
0x180038d20  call    ?lower_bound@?$_Hash@V?$_Umap_traits@U_GUID@@PEAVRRasRoutingDomainConfig@@V?$_Hash_compare@U_GUID@@UGuidHash@@UGuidEquality@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@@4@$0A@@tr1@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@@2@@std@@@2@AEBU_GUID@@@Z; std::_Hash<std::tr1::_Umap_traits<_GUID,RRasRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>,0>>::lower_bound(_GUID const &)
0x180038d25  mov     rax, [rsp+8C0h+var_878]
0x180038d2a  cmp     rax, [rbx+18h]
0x180038d2e  jz      short loc_180038D66
0x180038d30  mov     rsi, [rax+20h]
0x180038d34  test    dil, r14b
0x180038d37  jz      short loc_180038D4B
0x180038d39  lea     rcx, [rsi+2D8h]; Resource
0x180038d40  mov     dl, dil; Wait
0x180038d43  call    cs:__imp_RtlAcquireResourceExclusive
0x180038d49  jmp     short loc_180038D61
0x180038d4b  test    r14b, 2
0x180038d4f  jz      short loc_180038D61
0x180038d51  lea     rcx, [rsi+2D8h]; Resource
0x180038d58  mov     dl, dil; Wait
0x180038d5b  call    cs:__imp_RtlAcquireResourceShared
0x180038d61  mov     [r15], rsi
0x180038d64  jmp     short loc_180038D6E
0x180038d66  mov     [rsp+8C0h+var_880], 490h
0x180038d6e  cmp     [rsp+8C0h+var_880], 0
0x180038d73  jz      short loc_180038D83
0x180038d75  test    edi, edi
0x180038d77  jz      short loc_180038D83
0x180038d79  lea     rcx, [rbx+70h]; Resource
0x180038d7d  call    cs:__imp_RtlReleaseResource
0x180038d83  mov     ebx, [rsp+8C0h+var_880]
0x180038d87  lea     rcx, [rsp+8C0h+var_870]; this
0x180038d8c  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180038d91  mov     eax, ebx
0x180038d93  mov     rcx, [rbp+7C0h+var_30]
0x180038d9a  xor     rcx, rsp; StackCookie
0x180038d9d  call    __security_check_cookie
0x180038da2  mov     rbx, [rsp+8C0h+arg_10]
0x180038daa  add     rsp, 8A0h
0x180038db1  pop     r15
0x180038db3  pop     r14
0x180038db5  pop     rdi
0x180038db6  pop     rsi
0x180038db7  pop     rbp
0x180038db8  retn
```
