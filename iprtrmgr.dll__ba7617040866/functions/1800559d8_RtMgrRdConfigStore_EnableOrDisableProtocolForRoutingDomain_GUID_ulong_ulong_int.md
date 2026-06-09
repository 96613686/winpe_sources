# RtMgrRdConfigStore::EnableOrDisableProtocolForRoutingDomain(_GUID *,ulong,ulong,int)

- ea: `0x1800559d8`
- end: `0x180055ab2`
- name: `?EnableOrDisableProtocolForRoutingDomain@RtMgrRdConfigStore@@QEAAXPEAU_GUID@@KKH@Z`
- size: `218`
- prototype: `void(RtMgrRdConfigStore *__hidden this, struct _GUID *, unsigned int, unsigned int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180002878`

## callees

- `0x1800557a0`
- `0x1800559d8`
- `0x1800578dc`
- `0x180058068`
- `0x180058124`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180055a89`
- `ntdll!RtlReleaseResource` at `0x180055a89`
- `ntdll!RtlAcquireResourceShared` at `0x180055a48`
- `ntdll!RtlAcquireResourceShared` at `0x180055a48`

## string_xrefs

- `0x180055a2c`: `RtMgrRdConfigStore::EnableOrDisableProtocolForRoutingDomain`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall RtMgrRdConfigStore::EnableOrDisableProtocolForRoutingDomain(
        RtMgrRdConfigStore *this,
        struct _GUID *a2,
        unsigned int *a3,
        void (*a4)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int),
        unsigned int a5)
{
  int v5; // ebp
  unsigned int v6; // r14d
  unsigned __int16 *v9; // [rsp+28h] [rbp-70h]
  unsigned int v10; // [rsp+30h] [rbp-68h]
  __int64 v11; // [rsp+40h] [rbp-58h] BYREF
  __int128 v12; // [rsp+48h] [rbp-50h]
  __int128 v13; // [rsp+58h] [rbp-40h]
  __int64 v14; // [rsp+68h] [rbp-30h]
  int v15; // [rsp+70h] [rbp-28h]
  int v16; // [rsp+74h] [rbp-24h]
  __int64 v17; // [rsp+A0h] [rbp+8h] BYREF

  v5 = (int)a4;
  v6 = (unsigned int)a3;
  v12 = 0;
  v11 = 0;
  v13 = 0;
  v14 = 0;
  v15 = -1;
  v16 = 0;
  if ( *((_QWORD *)&xmmword_18008B450 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v11,
      L"RtMgrRdConfigStore::EnableOrDisableProtocolForRoutingDomain",
      a3,
      a4,
      a2,
      v9,
      v10);
  RtlAcquireResourceShared((PRTL_RESOURCE)((char *)this + 184), 1u);
  std::_Hash<std::tr1::_Umap_traits<_GUID,RtMgrRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RtMgrRoutingDomainConfig *>>,0>>::lower_bound(
    (char *)this + 8,
    &v17,
    a2);
  if ( v17 != *((_QWORD *)this + 2) )
    RtMgrRoutingDomainConfig::EnableOrDisableProtocol(
      *(struct _GUID **)(v17 + 32),
      v5,
      (unsigned int *)v6,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))a5);
  RtlReleaseResource((PRTL_RESOURCE)((char *)this + 184));
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v11);
}

```

## disassembly

```asm
0x1800559d8  mov     r11, rsp
0x1800559db  mov     [r11+10h], rbx
0x1800559df  mov     [r11+18h], rbp
0x1800559e3  push    rsi
0x1800559e4  push    rdi
0x1800559e5  push    r14
0x1800559e7  sub     rsp, 80h
0x1800559ee  mov     ebp, r9d
0x1800559f1  mov     r14d, r8d
0x1800559f4  mov     rsi, rdx
0x1800559f7  mov     rdi, rcx
0x1800559fa  xorps   xmm0, xmm0
0x1800559fd  movdqu  [rsp+98h+var_50], xmm0
0x180055a03  xor     eax, eax
0x180055a05  mov     [r11-58h], rax
0x180055a09  movdqu  [rsp+98h+var_40], xmm0
0x180055a0f  mov     [r11-30h], rax
0x180055a13  mov     [rsp+98h+var_28], 0FFFFFFFFh
0x180055a1b  mov     [rsp+98h+var_24], eax
0x180055a1f  cmp     qword ptr cs:xmmword_18008B450+8, rax
0x180055a26  jz      short loc_180055A3C
0x180055a28  mov     [r11-78h], rdx
0x180055a2c  lea     rdx, aRtmgrrdconfigs_5; "RtMgrRdConfigStore::EnableOrDisableProt"...
0x180055a33  lea     rcx, [r11-58h]; this
0x180055a37  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x180055a3c  lea     rbx, [rdi+0B8h]
0x180055a43  mov     dl, 1; Wait
0x180055a45  mov     rcx, rbx; Resource
0x180055a48  call    cs:__imp_RtlAcquireResourceShared
0x180055a4e  lea     rcx, [rdi+8]
0x180055a52  mov     r8, rsi
0x180055a55  lea     rdx, [rsp+98h+arg_0]
0x180055a5d  call    ?lower_bound@?$_Hash@V?$_Umap_traits@U_GUID@@PEAVRtMgrRoutingDomainConfig@@V?$_Hash_compare@U_GUID@@UGuidHash@@UGuidEquality@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRtMgrRoutingDomainConfig@@@std@@@4@$0A@@tr1@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$pair@$$CBU_GUID@@PEAVRtMgrRoutingDomainConfig@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRtMgrRoutingDomainConfig@@@std@@@2@@std@@@2@AEBU_GUID@@@Z; std::_Hash<std::tr1::_Umap_traits<_GUID,RtMgrRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RtMgrRoutingDomainConfig *>>,0>>::lower_bound(_GUID const &)
0x180055a62  mov     rcx, [rsp+98h+arg_0]
0x180055a6a  cmp     rcx, [rdi+10h]
0x180055a6e  jz      short loc_180055A86
0x180055a70  mov     r9d, [rsp+98h+arg_20]; int
0x180055a78  mov     r8d, r14d; unsigned int
0x180055a7b  mov     edx, ebp; unsigned int
0x180055a7d  mov     rcx, [rcx+20h]; this
0x180055a81  call    ?EnableOrDisableProtocol@RtMgrRoutingDomainConfig@@QEAAXKKH@Z; RtMgrRoutingDomainConfig::EnableOrDisableProtocol(ulong,ulong,int)
0x180055a86  mov     rcx, rbx; Resource
0x180055a89  call    cs:__imp_RtlReleaseResource
0x180055a8f  nop
0x180055a90  lea     rcx, [rsp+98h+var_58]; this
0x180055a95  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180055a9a  lea     r11, [rsp+98h+var_18]
0x180055aa2  mov     rbx, [r11+28h]
0x180055aa6  mov     rbp, [r11+30h]
0x180055aaa  mov     rsp, r11
0x180055aad  pop     r14
0x180055aaf  pop     rdi
0x180055ab0  pop     rsi
0x180055ab1  retn
```
