# RtMgrRdConfigStore::RemoveRoutingDomain(_GUID *,ulong)

- ea: `0x180056434`
- end: `0x18005655e`
- name: `?RemoveRoutingDomain@RtMgrRdConfigStore@@QEAAXPEAU_GUID@@K@Z`
- size: `298`
- prototype: `void(RtMgrRdConfigStore *__hidden this, struct _GUID *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180057d14`

## callees

- `0x180002fd4`
- `0x1800555e8`
- `0x180055ab8`
- `0x180056370`
- `0x180056434`
- `0x180057640`
- `0x180057788`
- `0x1800578dc`
- `0x180058068`
- `0x180058124`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x1800564a8`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800564a8`
- `ntdll!RtlReleaseResource` at `0x180056523`
- `ntdll!RtlReleaseResource` at `0x180056523`

## string_xrefs

- `0x18005648c`: `RtMgrRdConfigStore::RemoveRoutingDomain`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall RtMgrRdConfigStore::RemoveRoutingDomain(
        RtMgrRdConfigStore *this,
        struct _GUID *a2,
        unsigned int *a3,
        void (*a4)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))
{
  unsigned int v4; // r15d
  struct _RTL_RESOURCE *v7; // r14
  char *v8; // rdi
  struct _GUID *v9; // rbx
  unsigned int v10; // edx
  _QWORD *v11; // rbx
  _QWORD *v12; // rax
  _QWORD *v13; // r8
  unsigned __int16 *v14; // [rsp+28h] [rbp-41h]
  unsigned int v15; // [rsp+30h] [rbp-39h]
  _QWORD *v16; // [rsp+40h] [rbp-29h] BYREF
  _QWORD *v17; // [rsp+48h] [rbp-21h]
  __int64 v18; // [rsp+50h] [rbp-19h] BYREF
  __int128 v19; // [rsp+58h] [rbp-11h]
  __int128 v20; // [rsp+68h] [rbp-1h]
  __int64 v21; // [rsp+78h] [rbp+Fh]
  int v22; // [rsp+80h] [rbp+17h]
  int v23; // [rsp+84h] [rbp+1Bh]
  __int64 v24; // [rsp+D0h] [rbp+67h] BYREF

  v4 = (unsigned int)a3;
  v19 = 0;
  v18 = 0;
  v20 = 0;
  v21 = 0;
  v22 = -1;
  v23 = 0;
  if ( *((_QWORD *)&xmmword_18008B450 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v18,
      L"RtMgrRdConfigStore::RemoveRoutingDomain",
      a3,
      a4,
      a2,
      v14,
      v15);
  v7 = (struct _RTL_RESOURCE *)((char *)this + 184);
  RtlAcquireResourceExclusive((PRTL_RESOURCE)((char *)this + 184), 1u);
  v8 = (char *)this + 8;
  std::_Hash<std::tr1::_Umap_traits<_GUID,RtMgrRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RtMgrRoutingDomainConfig *>>,0>>::lower_bound(
    (char *)this + 8,
    &v24,
    a2);
  if ( v24 != *((_QWORD *)this + 2) )
  {
    v9 = *(struct _GUID **)(v24 + 32);
    RtMgrRoutingDomainConfig::EnableOrDisableTransport(v9, v4, 0);
    if ( (unsigned int)RtMgrRoutingDomainConfig::IsSafeToDelete((RtMgrRoutingDomainConfig *)v9) )
    {
      if ( v9 )
        RtMgrRoutingDomainConfig::`scalar deleting destructor'((RtMgrRoutingDomainConfig *)v9, v10);
      std::_Hash<std::tr1::_Umap_traits<_GUID,RtMgrRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RtMgrRoutingDomainConfig *>>,0>>::equal_range(
        v8,
        &v16,
        a2);
      v11 = v16;
      v12 = (_QWORD *)*((_QWORD *)v8 + 1);
      if ( v16 == (_QWORD *)*v12 && v17 == v12 )
      {
        std::_Hash<std::tr1::_Umap_traits<void *,RtMgrRoutingDomainConfig *,std::_Hash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,RtMgrRoutingDomainConfig *>>,0>>::clear(v8);
      }
      else
      {
        while ( v11 != v17 )
        {
          v13 = v11;
          v11 = (_QWORD *)*v11;
          std::_Hash<std::tr1::_Umap_traits<_GUID,RtMgrRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RtMgrRoutingDomainConfig *>>,0>>::erase(
            v8,
            &v24,
            v13);
        }
      }
    }
  }
  RtlReleaseResource(v7);
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v18);
}

```

## disassembly

```asm
0x180056434  push    rbp
0x180056436  push    rbx
0x180056437  push    rsi
0x180056438  push    rdi
0x180056439  push    r14
0x18005643b  push    r15
0x18005643d  lea     rbp, [rsp-2Fh]
0x180056442  sub     rsp, 98h
0x180056449  mov     r15d, r8d
0x18005644c  mov     rsi, rdx
0x18005644f  mov     rbx, rcx
0x180056452  xorps   xmm0, xmm0
0x180056455  movdqu  [rbp+57h+var_68], xmm0
0x18005645a  mov     [rbp+57h+var_70], 0
0x180056462  movdqu  [rbp+57h+var_58], xmm0
0x180056467  mov     [rbp+57h+var_48], 0
0x18005646f  mov     [rbp+57h+var_40], 0FFFFFFFFh
0x180056476  mov     [rbp+57h+var_3C], 0
0x18005647d  cmp     qword ptr cs:xmmword_18008B450+8, 0
0x180056485  jz      short loc_18005649C
0x180056487  mov     [rsp+0C0h+var_A0], rdx; struct _GUID *
0x18005648c  lea     rdx, aRtmgrrdconfigs_0; "RtMgrRdConfigStore::RemoveRoutingDomain"
0x180056493  lea     rcx, [rbp+57h+var_70]; this
0x180056497  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x18005649c  lea     r14, [rbx+0B8h]
0x1800564a3  mov     dl, 1; Wait
0x1800564a5  mov     rcx, r14; Resource
0x1800564a8  call    cs:__imp_RtlAcquireResourceExclusive
0x1800564ae  lea     rdi, [rbx+8]
0x1800564b2  mov     r8, rsi
0x1800564b5  lea     rdx, [rbp+57h+arg_0]
0x1800564b9  mov     rcx, rdi
0x1800564bc  call    ?lower_bound@?$_Hash@V?$_Umap_traits@U_GUID@@PEAVRtMgrRoutingDomainConfig@@V?$_Hash_compare@U_GUID@@UGuidHash@@UGuidEquality@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRtMgrRoutingDomainConfig@@@std@@@4@$0A@@tr1@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$pair@$$CBU_GUID@@PEAVRtMgrRoutingDomainConfig@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRtMgrRoutingDomainConfig@@@std@@@2@@std@@@2@AEBU_GUID@@@Z; std::_Hash<std::tr1::_Umap_traits<_GUID,RtMgrRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RtMgrRoutingDomainConfig *>>,0>>::lower_bound(_GUID const &)
0x1800564c1  mov     rax, [rbp+57h+arg_0]
0x1800564c5  cmp     rax, [rbx+10h]
0x1800564c9  jz      short loc_180056520
0x1800564cb  mov     rbx, [rax+20h]
0x1800564cf  xor     r8d, r8d; int
0x1800564d2  mov     edx, r15d; unsigned int
0x1800564d5  mov     rcx, rbx; this
0x1800564d8  call    ?EnableOrDisableTransport@RtMgrRoutingDomainConfig@@QEAAXKH@Z; RtMgrRoutingDomainConfig::EnableOrDisableTransport(ulong,int)
0x1800564dd  mov     rcx, rbx; this
0x1800564e0  call    ?IsSafeToDelete@RtMgrRoutingDomainConfig@@QEAAHXZ; RtMgrRoutingDomainConfig::IsSafeToDelete(void)
0x1800564e5  test    eax, eax
0x1800564e7  jz      short loc_180056520
0x1800564e9  test    rbx, rbx
0x1800564ec  jz      short loc_1800564F6
0x1800564ee  mov     rcx, rbx; this
0x1800564f1  call    ??_GRtMgrRoutingDomainConfig@@QEAAPEAXI@Z; RtMgrRoutingDomainConfig::`scalar deleting destructor'(uint)
0x1800564f6  mov     r8, rsi
0x1800564f9  lea     rdx, [rbp+57h+var_80]
0x1800564fd  mov     rcx, rdi
0x180056500  call    ?equal_range@?$_Hash@V?$_Umap_traits@U_GUID@@PEAVRtMgrRoutingDomainConfig@@V?$_Hash_compare@U_GUID@@UGuidHash@@UGuidEquality@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRtMgrRoutingDomainConfig@@@std@@@4@$0A@@tr1@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$pair@$$CBU_GUID@@PEAVRtMgrRoutingDomainConfig@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRtMgrRoutingDomainConfig@@@std@@@2@@std@@@std@@V12@@2@AEBU_GUID@@@Z; std::_Hash<std::tr1::_Umap_traits<_GUID,RtMgrRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RtMgrRoutingDomainConfig *>>,0>>::equal_range(_GUID const &)
0x180056505  mov     rbx, [rbp+57h+var_80]
0x180056509  mov     rax, [rdi+8]
0x18005650d  cmp     rbx, [rax]
0x180056510  jnz     short loc_180056543
0x180056512  cmp     [rbp+57h+var_78], rax
0x180056516  jnz     short loc_180056543
0x180056518  mov     rcx, rdi
0x18005651b  call    ?clear@?$_Hash@V?$_Umap_traits@PEAXPEAVRtMgrRoutingDomainConfig@@V?$_Hash_compare@PEAXV?$hash@PEAX@std@@U?$equal_to@PEAX@2@@std@@V?$allocator@U?$pair@QEAXPEAVRtMgrRoutingDomainConfig@@@std@@@3@$0A@@tr1@std@@@std@@QEAAXXZ; std::_Hash<std::tr1::_Umap_traits<void *,RtMgrRoutingDomainConfig *,std::_Hash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,RtMgrRoutingDomainConfig *>>,0>>::clear(void)
0x180056520  mov     rcx, r14; Resource
0x180056523  call    cs:__imp_RtlReleaseResource
0x180056529  nop
0x18005652a  lea     rcx, [rbp+57h+var_70]; this
0x18005652e  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180056533  add     rsp, 98h
0x18005653a  pop     r15
0x18005653c  pop     r14
0x18005653e  pop     rdi
0x18005653f  pop     rsi
0x180056540  pop     rbx
0x180056541  pop     rbp
0x180056542  retn
0x180056543  cmp     rbx, [rbp+57h+var_78]
0x180056547  jz      short loc_180056520
0x180056549  mov     r8, rbx
0x18005654c  mov     rbx, [rbx]
0x18005654f  lea     rdx, [rbp+57h+arg_0]
0x180056553  mov     rcx, rdi
0x180056556  call    ?erase@?$_Hash@V?$_Umap_traits@U_GUID@@PEAVRtMgrRoutingDomainConfig@@V?$_Hash_compare@U_GUID@@UGuidHash@@UGuidEquality@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRtMgrRoutingDomainConfig@@@std@@@4@$0A@@tr1@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$pair@$$CBU_GUID@@PEAVRtMgrRoutingDomainConfig@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRtMgrRoutingDomainConfig@@@std@@@2@@std@@@2@V?$_List_const_iterator@V?$_List_val@U?$pair@$$CBU_GUID@@PEAVRtMgrRoutingDomainConfig@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRtMgrRoutingDomainConfig@@@std@@@2@@std@@@2@@Z; std::_Hash<std::tr1::_Umap_traits<_GUID,RtMgrRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RtMgrRoutingDomainConfig *>>,0>>::erase(std::_List_const_iterator<std::_List_val<std::pair<_GUID const,RtMgrRoutingDomainConfig *>>>)
0x18005655b  jmp     short loc_180056543
```
