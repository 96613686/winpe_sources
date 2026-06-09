# RtMgrRdConfigStore::AddRoutingDomain(_GUID *,ushort *,uint,ulong)

- ea: `0x180055654`
- end: `0x180055799`
- name: `?AddRoutingDomain@RtMgrRdConfigStore@@QEAAKPEAU_GUID@@PEAGIK@Z`
- size: `325`
- prototype: `unsigned int(RtMgrRdConfigStore *__hidden this, struct _GUID *, unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180057a64`

## callees

- `0x180003b00`
- `0x180055270`
- `0x180055528`
- `0x180055654`
- `0x180055ab8`
- `0x1800578dc`
- `0x180058068`
- `0x180058124`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x1800556c8`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800556c8`
- `ntdll!RtlReleaseResource` at `0x18005576a`
- `ntdll!RtlReleaseResource` at `0x18005576a`

## string_xrefs

- `0x1800556ac`: `RtMgrRdConfigStore::AddRoutingDomain`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RtMgrRdConfigStore::AddRoutingDomain(
        RtMgrRdConfigStore *this,
        struct _GUID *a2,
        unsigned int *a3,
        void (*a4)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int),
        unsigned int a5)
{
  unsigned int v5; // r15d
  unsigned int v9; // esi
  struct _RTL_RESOURCE *v10; // rbp
  char *v11; // r14
  RtMgrRoutingDomainConfig *v12; // rax
  struct _GUID *v13; // rbx
  unsigned __int16 *v15; // [rsp+28h] [rbp-80h]
  unsigned int v16; // [rsp+30h] [rbp-78h]
  __int64 v17; // [rsp+40h] [rbp-68h] BYREF
  __int128 v18; // [rsp+48h] [rbp-60h]
  __int128 v19; // [rsp+58h] [rbp-50h]
  __int64 v20; // [rsp+68h] [rbp-40h]
  int v21; // [rsp+70h] [rbp-38h]
  int v22; // [rsp+74h] [rbp-34h]
  RtMgrRoutingDomainConfig *v23; // [rsp+B0h] [rbp+8h] BYREF

  v5 = (unsigned int)a4;
  v9 = 0;
  v18 = 0;
  v17 = 0;
  v19 = 0;
  v20 = 0;
  v21 = -1;
  v22 = 0;
  if ( *((_QWORD *)&xmmword_18008B450 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v17,
      L"RtMgrRdConfigStore::AddRoutingDomain",
      a3,
      a4,
      a2,
      v15,
      v16);
  v10 = (struct _RTL_RESOURCE *)((char *)this + 184);
  RtlAcquireResourceExclusive((PRTL_RESOURCE)((char *)this + 184), 1u);
  v11 = (char *)this + 8;
  std::_Hash<std::tr1::_Umap_traits<_GUID,RtMgrRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RtMgrRoutingDomainConfig *>>,0>>::lower_bound(
    (char *)this + 8,
    &v23,
    a2);
  if ( v23 == *((RtMgrRoutingDomainConfig **)this + 2) )
  {
    v12 = (RtMgrRoutingDomainConfig *)operator new(0x300u);
    v23 = v12;
    if ( v12 )
      v13 = (struct _GUID *)RtMgrRoutingDomainConfig::RtMgrRoutingDomainConfig(v12, a2, (wchar_t *)a3, v5);
    else
      v13 = 0;
    if ( v13 )
    {
      RtMgrRoutingDomainConfig::EnableOrDisableTransport(v13, a5, 1);
      *(_QWORD *)std::tr1::unordered_map<_GUID,RtMgrRoutingDomainConfig *,GuidHash,GuidEquality,std::allocator<std::pair<_GUID const,RtMgrRoutingDomainConfig *>>>::operator[](
                   v11,
                   a2) = v13;
    }
    else
    {
      v9 = 8;
    }
  }
  else
  {
    RtMgrRoutingDomainConfig::EnableOrDisableTransport(*((struct _GUID **)v23 + 4), a5, 1);
  }
  RtlReleaseResource(v10);
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v17);
  return v9;
}

```

## disassembly

```asm
0x180055654  mov     rax, rsp
0x180055657  mov     [rax+10h], rbx
0x18005565b  mov     [rax+18h], rbp
0x18005565f  push    rsi
0x180055660  push    rdi
0x180055661  push    r12
0x180055663  push    r14
0x180055665  push    r15
0x180055667  sub     rsp, 80h
0x18005566e  mov     r15d, r9d
0x180055671  mov     r12, r8
0x180055674  mov     rdi, rdx
0x180055677  mov     rbx, rcx
0x18005567a  xor     esi, esi
0x18005567c  xorps   xmm0, xmm0
0x18005567f  movdqu  xmmword ptr [rax-60h], xmm0
0x180055684  mov     [rax-68h], rsi
0x180055688  xorps   xmm1, xmm1
0x18005568b  movdqu  xmmword ptr [rax-50h], xmm1
0x180055690  mov     [rax-40h], rsi
0x180055694  mov     dword ptr [rax-38h], 0FFFFFFFFh
0x18005569b  mov     [rax-34h], esi
0x18005569e  cmp     qword ptr cs:xmmword_18008B450+8, rsi
0x1800556a5  jz      short loc_1800556BC
0x1800556a7  mov     [rsp+0A8h+var_88], rdx; struct _GUID *
0x1800556ac  lea     rdx, aRtmgrrdconfigs_4; "RtMgrRdConfigStore::AddRoutingDomain"
0x1800556b3  lea     rcx, [rax-68h]; this
0x1800556b7  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x1800556bc  lea     rbp, [rbx+0B8h]
0x1800556c3  mov     dl, 1; Wait
0x1800556c5  mov     rcx, rbp; Resource
0x1800556c8  call    cs:__imp_RtlAcquireResourceExclusive
0x1800556ce  lea     r14, [rbx+8]
0x1800556d2  mov     r8, rdi
0x1800556d5  lea     rdx, [rsp+0A8h+arg_0]
0x1800556dd  mov     rcx, r14
0x1800556e0  call    ?lower_bound@?$_Hash@V?$_Umap_traits@U_GUID@@PEAVRtMgrRoutingDomainConfig@@V?$_Hash_compare@U_GUID@@UGuidHash@@UGuidEquality@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRtMgrRoutingDomainConfig@@@std@@@4@$0A@@tr1@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$pair@$$CBU_GUID@@PEAVRtMgrRoutingDomainConfig@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRtMgrRoutingDomainConfig@@@std@@@2@@std@@@2@AEBU_GUID@@@Z; std::_Hash<std::tr1::_Umap_traits<_GUID,RtMgrRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RtMgrRoutingDomainConfig *>>,0>>::lower_bound(_GUID const &)
0x1800556e5  mov     rcx, [rsp+0A8h+arg_0]
0x1800556ed  cmp     rcx, [rbx+10h]
0x1800556f1  jz      short loc_18005570B
0x1800556f3  mov     r8d, 1; int
0x1800556f9  mov     edx, [rsp+0A8h+arg_20]; unsigned int
0x180055700  mov     rcx, [rcx+20h]; this
0x180055704  call    ?EnableOrDisableTransport@RtMgrRoutingDomainConfig@@QEAAXKH@Z; RtMgrRoutingDomainConfig::EnableOrDisableTransport(ulong,int)
0x180055709  jmp     short loc_180055767
0x18005570b  mov     ecx, 300h; Size
0x180055710  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180055715  mov     [rsp+0A8h+arg_0], rax
0x18005571d  test    rax, rax
0x180055720  jz      short loc_180055738
0x180055722  mov     r9d, r15d; unsigned int
0x180055725  mov     r8, r12; Source
0x180055728  mov     rdx, rdi; struct _GUID *
0x18005572b  mov     rcx, rax; this
0x18005572e  call    ??0RtMgrRoutingDomainConfig@@QEAA@PEAU_GUID@@PEAGI@Z; RtMgrRoutingDomainConfig::RtMgrRoutingDomainConfig(_GUID *,ushort *,uint)
0x180055733  mov     rbx, rax
0x180055736  jmp     short loc_18005573A
0x180055738  xor     ebx, ebx
0x18005573a  test    rbx, rbx
0x18005573d  jnz     short loc_180055744
0x18005573f  lea     esi, [rbx+8]
0x180055742  jmp     short loc_180055767
0x180055744  mov     r8d, 1; int
0x18005574a  mov     edx, [rsp+0A8h+arg_20]; unsigned int
0x180055751  mov     rcx, rbx; this
0x180055754  call    ?EnableOrDisableTransport@RtMgrRoutingDomainConfig@@QEAAXKH@Z; RtMgrRoutingDomainConfig::EnableOrDisableTransport(ulong,int)
0x180055759  mov     rdx, rdi
0x18005575c  mov     rcx, r14
0x18005575f  call    ??A?$unordered_map@U_GUID@@PEAVRtMgrRoutingDomainConfig@@UGuidHash@@UGuidEquality@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRtMgrRoutingDomainConfig@@@std@@@std@@@tr1@std@@QEAAAEAPEAVRtMgrRoutingDomainConfig@@AEBU_GUID@@@Z; std::tr1::unordered_map<_GUID,RtMgrRoutingDomainConfig *,GuidHash,GuidEquality,std::allocator<std::pair<_GUID const,RtMgrRoutingDomainConfig *>>>::operator[](_GUID const &)
0x180055764  mov     [rax], rbx
0x180055767  mov     rcx, rbp; Resource
0x18005576a  call    cs:__imp_RtlReleaseResource
0x180055770  nop
0x180055771  lea     rcx, [rsp+0A8h+var_68]; this
0x180055776  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18005577b  mov     eax, esi
0x18005577d  lea     r11, [rsp+0A8h+var_28]
0x180055785  mov     rbx, [r11+38h]
0x180055789  mov     rbp, [r11+40h]
0x18005578d  mov     rsp, r11
0x180055790  pop     r15
0x180055792  pop     r14
0x180055794  pop     r12
0x180055796  pop     rdi
0x180055797  pop     rsi
0x180055798  retn
```
