# RtMgrRdConfigStore::SetInternalInterfaceForRoutingDomain(_GUID *,ulong,_ICB *)

- ea: `0x180056608`
- end: `0x1800566db`
- name: `?SetInternalInterfaceForRoutingDomain@RtMgrRdConfigStore@@QEAAXPEAU_GUID@@KPEAU_ICB@@@Z`
- size: `211`
- prototype: `void(RtMgrRdConfigStore *__hidden this, struct _GUID *, unsigned int, struct _ICB *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180057d48`

## callees

- `0x180056564`
- `0x180056608`
- `0x1800578dc`
- `0x180058068`
- `0x180058124`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x1800566b2`
- `ntdll!RtlReleaseResource` at `0x1800566b2`
- `ntdll!RtlAcquireResourceShared` at `0x180056678`
- `ntdll!RtlAcquireResourceShared` at `0x180056678`

## string_xrefs

- `0x18005665c`: `RtMgrRdConfigStore::SetInternalInterfaceForRoutingDomain`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall RtMgrRdConfigStore::SetInternalInterfaceForRoutingDomain(
        RtMgrRdConfigStore *this,
        struct _GUID *a2,
        unsigned int *a3,
        struct _ICB *a4)
{
  unsigned int v5; // r14d
  unsigned __int16 *v8; // [rsp+28h] [rbp-70h]
  unsigned int v9; // [rsp+30h] [rbp-68h]
  __int64 v10; // [rsp+40h] [rbp-58h] BYREF
  __int128 v11; // [rsp+48h] [rbp-50h]
  __int128 v12; // [rsp+58h] [rbp-40h]
  __int64 v13; // [rsp+68h] [rbp-30h]
  int v14; // [rsp+70h] [rbp-28h]
  int v15; // [rsp+74h] [rbp-24h]
  __int64 v16; // [rsp+A0h] [rbp+8h] BYREF

  v5 = (unsigned int)a3;
  v11 = 0;
  v10 = 0;
  v12 = 0;
  v13 = 0;
  v14 = -1;
  v15 = 0;
  if ( *((_QWORD *)&xmmword_18008B450 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v10,
      L"RtMgrRdConfigStore::SetInternalInterfaceForRoutingDomain",
      a3,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))a4,
      a2,
      v8,
      v9);
  RtlAcquireResourceShared((PRTL_RESOURCE)((char *)this + 184), 1u);
  std::_Hash<std::tr1::_Umap_traits<_GUID,RtMgrRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RtMgrRoutingDomainConfig *>>,0>>::lower_bound(
    (char *)this + 8,
    &v16,
    a2);
  if ( v16 != *((_QWORD *)this + 2) )
    RtMgrRoutingDomainConfig::SetInternalInterface(*(struct _GUID **)(v16 + 32), v5, a4);
  RtlReleaseResource((PRTL_RESOURCE)((char *)this + 184));
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v10);
}

```

## disassembly

```asm
0x180056608  mov     r11, rsp
0x18005660b  mov     [r11+10h], rbx
0x18005660f  mov     [r11+18h], rbp
0x180056613  push    rsi
0x180056614  push    rdi
0x180056615  push    r14
0x180056617  sub     rsp, 80h
0x18005661e  mov     rbp, r9
0x180056621  mov     r14d, r8d
0x180056624  mov     rsi, rdx
0x180056627  mov     rdi, rcx
0x18005662a  xorps   xmm0, xmm0
0x18005662d  movdqu  [rsp+98h+var_50], xmm0
0x180056633  xor     eax, eax
0x180056635  mov     [r11-58h], rax
0x180056639  movdqu  [rsp+98h+var_40], xmm0
0x18005663f  mov     [r11-30h], rax
0x180056643  mov     [rsp+98h+var_28], 0FFFFFFFFh
0x18005664b  mov     [rsp+98h+var_24], eax
0x18005664f  cmp     qword ptr cs:xmmword_18008B450+8, rax
0x180056656  jz      short loc_18005666C
0x180056658  mov     [r11-78h], rdx
0x18005665c  lea     rdx, aRtmgrrdconfigs_3; "RtMgrRdConfigStore::SetInternalInterfac"...
0x180056663  lea     rcx, [r11-58h]; this
0x180056667  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x18005666c  lea     rbx, [rdi+0B8h]
0x180056673  mov     dl, 1; Wait
0x180056675  mov     rcx, rbx; Resource
0x180056678  call    cs:__imp_RtlAcquireResourceShared
0x18005667e  lea     rcx, [rdi+8]
0x180056682  mov     r8, rsi
0x180056685  lea     rdx, [rsp+98h+arg_0]
0x18005668d  call    ?lower_bound@?$_Hash@V?$_Umap_traits@U_GUID@@PEAVRtMgrRoutingDomainConfig@@V?$_Hash_compare@U_GUID@@UGuidHash@@UGuidEquality@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRtMgrRoutingDomainConfig@@@std@@@4@$0A@@tr1@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$pair@$$CBU_GUID@@PEAVRtMgrRoutingDomainConfig@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRtMgrRoutingDomainConfig@@@std@@@2@@std@@@2@AEBU_GUID@@@Z; std::_Hash<std::tr1::_Umap_traits<_GUID,RtMgrRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RtMgrRoutingDomainConfig *>>,0>>::lower_bound(_GUID const &)
0x180056692  mov     rcx, [rsp+98h+arg_0]
0x18005669a  cmp     rcx, [rdi+10h]
0x18005669e  jz      short loc_1800566AF
0x1800566a0  mov     r8, rbp; struct _ICB *
0x1800566a3  mov     edx, r14d; unsigned int
0x1800566a6  mov     rcx, [rcx+20h]; this
0x1800566aa  call    ?SetInternalInterface@RtMgrRoutingDomainConfig@@QEAAXKPEAU_ICB@@@Z; RtMgrRoutingDomainConfig::SetInternalInterface(ulong,_ICB *)
0x1800566af  mov     rcx, rbx; Resource
0x1800566b2  call    cs:__imp_RtlReleaseResource
0x1800566b8  nop
0x1800566b9  lea     rcx, [rsp+98h+var_58]; this
0x1800566be  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x1800566c3  lea     r11, [rsp+98h+var_18]
0x1800566cb  mov     rbx, [r11+28h]
0x1800566cf  mov     rbp, [r11+30h]
0x1800566d3  mov     rsp, r11
0x1800566d6  pop     r14
0x1800566d8  pop     rdi
0x1800566d9  pop     rsi
0x1800566da  retn
```
