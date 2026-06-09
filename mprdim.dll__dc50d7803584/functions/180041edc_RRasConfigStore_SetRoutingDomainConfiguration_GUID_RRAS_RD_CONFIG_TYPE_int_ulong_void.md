# RRasConfigStore::SetRoutingDomainConfiguration(_GUID *,_RRAS_RD_CONFIG_TYPE,int,ulong,void *)

- ea: `0x180041edc`
- end: `0x18004208a`
- name: `?SetRoutingDomainConfiguration@RRasConfigStore@@QEAAKPEAU_GUID@@W4_RRAS_RD_CONFIG_TYPE@@HKPEAX@Z`
- size: `430`
- prototype: `unsigned int __high(struct _GUID *, enum _RRAS_RD_CONFIG_TYPE, int, unsigned int, void *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800379b0`

## callees

- `0x1800416fc`
- `0x180041edc`
- `0x180043e34`
- `0x18004583c`
- `0x1800459e8`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180041ff8`
- `ntdll!RtlReleaseResource` at `0x180042001`
- `ntdll!RtlReleaseResource` at `0x180041ff8`
- `ntdll!RtlReleaseResource` at `0x180042001`
- `ntdll!RtlAcquireResourceExclusive` at `0x180041fd1`
- `ntdll!RtlAcquireResourceExclusive` at `0x180041fd1`
- `ntdll!RtlAcquireResourceShared` at `0x180041f95`
- `ntdll!RtlAcquireResourceShared` at `0x180041f95`

## string_xrefs

- `0x180041f6d`: `RRasConfigStore::SetRoutingDomainConfiguration`
- `0x180042024`: `RRasConfigStore::SetRoutingDomainConfiguration`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RRasConfigStore::SetRoutingDomainConfiguration(
        __int64 a1,
        struct _GUID *a2,
        int a3,
        int a4,
        unsigned int a5,
        struct _MPRI_IPV4_CONFIG_1 *a6)
{
  void (*v10)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  __int64 v11; // rbx
  unsigned int v12; // ebx
  unsigned __int16 *v14; // [rsp+28h] [rbp-D8h]
  unsigned int v15; // [rsp+30h] [rbp-D0h]
  unsigned int v16; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v17; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v18; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v19; // [rsp+58h] [rbp-A8h]
  __int128 v20; // [rsp+68h] [rbp-98h]
  __int64 v21; // [rsp+78h] [rbp-88h]
  int v22; // [rsp+80h] [rbp-80h]
  int v23; // [rsp+84h] [rbp-7Ch]
  int v24; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v25[2044]; // [rsp+94h] [rbp-6Ch] BYREF

  v16 = 0;
  v24 = 0;
  memset_0(v25, 0, sizeof(v25));
  v19 = 0;
  v18 = 0;
  v20 = 0;
  v21 = 0;
  v22 = -1;
  v23 = 0;
  if ( *((_QWORD *)&xmmword_1800710A0 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v18,
      L"RRasConfigStore::SetRoutingDomainConfiguration",
      &v16,
      v10,
      a2,
      v14,
      v15);
  if ( a2 && a6 )
  {
    RtlAcquireResourceShared((PRTL_RESOURCE)(a1 + 112), 1u);
    std::_Hash<std::tr1::_Umap_traits<_GUID,RRasRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>,0>>::lower_bound(
      a1 + 16,
      &v17,
      a2);
    if ( v17 == *(_QWORD *)(a1 + 24) )
    {
      v16 = 1168;
    }
    else
    {
      v11 = *(_QWORD *)(v17 + 32);
      RtlAcquireResourceExclusive((PRTL_RESOURCE)(v11 + 728), 1u);
      v16 = RRasRoutingDomainConfig::SetConfigParam(v11, a3, a4, a5, a6);
      RtlReleaseResource((PRTL_RESOURCE)(v11 + 728));
    }
    RtlReleaseResource((PRTL_RESOURCE)(a1 + 112));
  }
  else
  {
    v16 = 87;
    if ( (_QWORD)xmmword_180071090 )
    {
      LOWORD(v24) = 0;
      FormatRRASErrorString(
        &v24,
        L"%hs(Line#%d): Invalid parameter.",
        "RRasConfigStore::SetRoutingDomainConfiguration",
        1017);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180071090,
        &v24);
    }
  }
  v12 = v16;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v18);
  return v12;
}

```

## disassembly

```asm
0x180041edc  push    rbp
0x180041ede  push    rbx
0x180041edf  push    rsi
0x180041ee0  push    rdi
0x180041ee1  push    r12
0x180041ee3  push    r14
0x180041ee5  push    r15
0x180041ee7  lea     rbp, [rsp-7A0h]
0x180041eef  sub     rsp, 8A0h
0x180041ef6  mov     rax, cs:__security_cookie
0x180041efd  xor     rax, rsp
0x180041f00  mov     [rbp+7D0h+var_40], rax
0x180041f07  mov     r12d, r9d
0x180041f0a  mov     r15d, r8d
0x180041f0d  mov     rbx, rdx
0x180041f10  mov     rdi, rcx
0x180041f13  mov     r14, [rbp+7D0h+arg_28]
0x180041f1a  xor     esi, esi
0x180041f1c  mov     [rsp+8D0h+var_890], esi
0x180041f20  mov     [rbp+7D0h+var_840], esi
0x180041f23  xor     edx, edx; Val
0x180041f25  mov     r8d, 7FCh; Size
0x180041f2b  lea     rcx, [rbp+7D0h+var_83C]; void *
0x180041f2f  call    memset_0
0x180041f34  xorps   xmm0, xmm0
0x180041f37  movdqu  [rsp+8D0h+var_878], xmm0
0x180041f3d  mov     [rsp+8D0h+var_880], rsi
0x180041f42  xorps   xmm1, xmm1
0x180041f45  movdqu  [rsp+8D0h+var_868], xmm1
0x180041f4b  mov     [rsp+8D0h+var_858], rsi
0x180041f50  mov     [rbp+7D0h+var_850], 0FFFFFFFFh
0x180041f57  mov     [rbp+7D0h+var_84C], esi
0x180041f5a  cmp     qword ptr cs:xmmword_1800710A0+8, rsi
0x180041f61  jz      short loc_180041F7E
0x180041f63  mov     [rsp+8D0h+var_8B0], rbx; struct _GUID *
0x180041f68  lea     r8, [rsp+8D0h+var_890]; unsigned int *
0x180041f6d  lea     rdx, aRrasconfigstor_13; "RRasConfigStore::SetRoutingDomainConfig"...
0x180041f74  lea     rcx, [rsp+8D0h+var_880]; this
0x180041f79  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x180041f7e  test    rbx, rbx
0x180041f81  jz      loc_180042009
0x180041f87  test    r14, r14
0x180041f8a  jz      short loc_180042009
0x180041f8c  lea     rsi, [rdi+70h]
0x180041f90  mov     dl, 1; Wait
0x180041f92  mov     rcx, rsi; Resource
0x180041f95  call    cs:__imp_RtlAcquireResourceShared
0x180041f9b  lea     rcx, [rdi+10h]
0x180041f9f  mov     r8, rbx
0x180041fa2  lea     rdx, [rsp+8D0h+var_888]
0x180041fa7  call    ?lower_bound@?$_Hash@V?$_Umap_traits@U_GUID@@PEAVRRasRoutingDomainConfig@@V?$_Hash_compare@U_GUID@@UGuidHash@@UGuidEquality@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@@4@$0A@@tr1@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@@2@@std@@@2@AEBU_GUID@@@Z; std::_Hash<std::tr1::_Umap_traits<_GUID,RRasRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>,0>>::lower_bound(_GUID const &)
0x180041fac  mov     rax, [rsp+8D0h+var_888]
0x180041fb1  cmp     rax, [rdi+18h]
0x180041fb5  jnz     short loc_180041FC1
0x180041fb7  mov     [rsp+8D0h+var_890], 490h
0x180041fbf  jmp     short loc_180041FFE
0x180041fc1  mov     rbx, [rax+20h]
0x180041fc5  lea     rdi, [rbx+2D8h]
0x180041fcc  mov     dl, 1; Wait
0x180041fce  mov     rcx, rdi; Resource
0x180041fd1  call    cs:__imp_RtlAcquireResourceExclusive
0x180041fd7  mov     [rsp+8D0h+var_8B0], r14
0x180041fdc  mov     r9d, [rbp+7D0h+arg_20]
0x180041fe3  mov     r8d, r12d
0x180041fe6  mov     edx, r15d
0x180041fe9  mov     rcx, rbx
0x180041fec  call    ?SetConfigParam@RRasRoutingDomainConfig@@QEAAKW4_RRAS_RD_CONFIG_TYPE@@HKPEAX@Z; RRasRoutingDomainConfig::SetConfigParam(_RRAS_RD_CONFIG_TYPE,int,ulong,void *)
0x180041ff1  mov     [rsp+8D0h+var_890], eax
0x180041ff5  mov     rcx, rdi; Resource
0x180041ff8  call    cs:__imp_RtlReleaseResource
0x180041ffe  mov     rcx, rsi; Resource
0x180042001  call    cs:__imp_RtlReleaseResource
0x180042007  jmp     short loc_180042059
0x180042009  mov     [rsp+8D0h+var_890], 57h ; 'W'
0x180042011  cmp     qword ptr cs:xmmword_180071090, rsi
0x180042018  jz      short loc_180042059
0x18004201a  mov     word ptr [rbp+7D0h+var_840], si
0x18004201e  mov     r9d, 3F9h
0x180042024  lea     r8, aRrasconfigstor_16; "RRasConfigStore::SetRoutingDomainConfig"...
0x18004202b  lea     rdx, aHsLineDInvalid; "%hs(Line#%d): Invalid parameter."
0x180042032  lea     rcx, [rbp+7D0h+var_840]
0x180042036  call    FormatRRASErrorString
0x18004203b  lea     r8, [rbp+7D0h+var_840]
0x18004203f  mov     rdx, qword ptr cs:xmmword_180071090
0x180042046  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18004204d  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180042054  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042059  mov     ebx, [rsp+8D0h+var_890]
0x18004205d  lea     rcx, [rsp+8D0h+var_880]; this
0x180042062  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180042067  mov     eax, ebx
0x180042069  mov     rcx, [rbp+7D0h+var_40]
0x180042070  xor     rcx, rsp; StackCookie
0x180042073  call    __security_check_cookie
0x180042078  add     rsp, 8A0h
0x18004207f  pop     r15
0x180042081  pop     r14
0x180042083  pop     r12
0x180042085  pop     rdi
0x180042086  pop     rsi
0x180042087  pop     rbx
0x180042088  pop     rbp
0x180042089  retn
```
