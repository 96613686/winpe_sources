# RtMgrRdConfigStore::SetIpChangeNotificationHandleForRoutingDomain(_GUID *,ulong,void *)

- ea: `0x180056788`
- end: `0x18005685b`
- name: `?SetIpChangeNotificationHandleForRoutingDomain@RtMgrRdConfigStore@@QEAAXPEAU_GUID@@KPEAX@Z`
- size: `211`
- prototype: `void(RtMgrRdConfigStore *__hidden this, struct _GUID *, unsigned int, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180057d8c`

## callees

- `0x1800566e4`
- `0x180056788`
- `0x1800578dc`
- `0x180058068`
- `0x180058124`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180056832`
- `ntdll!RtlReleaseResource` at `0x180056832`
- `ntdll!RtlAcquireResourceShared` at `0x1800567f8`
- `ntdll!RtlAcquireResourceShared` at `0x1800567f8`

## string_xrefs

- `0x1800567dc`: `RtMgrRdConfigStore::SetIpChangeNotificationHandleForRoutingDomain`

## pseudocode

```c
void __fastcall RtMgrRdConfigStore::SetIpChangeNotificationHandleForRoutingDomain(
        RtMgrRdConfigStore *this,
        struct _GUID *a2,
        unsigned int *a3,
        void (*a4)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))
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
      L"RtMgrRdConfigStore::SetIpChangeNotificationHandleForRoutingDomain",
      a3,
      a4,
      a2,
      v8,
      v9);
  RtlAcquireResourceShared((PRTL_RESOURCE)((char *)this + 184), 1u);
  std::_Hash<std::tr1::_Umap_traits<_GUID,RtMgrRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RtMgrRoutingDomainConfig *>>,0>>::lower_bound(
    (char *)this + 8,
    &v16,
    a2);
  if ( v16 != *((_QWORD *)this + 2) )
    RtMgrRoutingDomainConfig::SetIpChangeNotificationHandle(*(struct _GUID **)(v16 + 32), v5, a4);
  RtlReleaseResource((PRTL_RESOURCE)((char *)this + 184));
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v10);
}

```

## disassembly

```asm
0x180056788  mov     r11, rsp
0x18005678b  mov     [r11+10h], rbx
0x18005678f  mov     [r11+18h], rbp
0x180056793  push    rsi
0x180056794  push    rdi
0x180056795  push    r14
0x180056797  sub     rsp, 80h
0x18005679e  mov     rbp, r9
0x1800567a1  mov     r14d, r8d
0x1800567a4  mov     rsi, rdx
0x1800567a7  mov     rdi, rcx
0x1800567aa  xorps   xmm0, xmm0
0x1800567ad  movdqu  [rsp+98h+var_50], xmm0
0x1800567b3  xor     eax, eax
0x1800567b5  mov     [r11-58h], rax
0x1800567b9  movdqu  [rsp+98h+var_40], xmm0
0x1800567bf  mov     [r11-30h], rax
0x1800567c3  mov     [rsp+98h+var_28], 0FFFFFFFFh
0x1800567cb  mov     [rsp+98h+var_24], eax
0x1800567cf  cmp     qword ptr cs:xmmword_18008B450+8, rax
0x1800567d6  jz      short loc_1800567EC
0x1800567d8  mov     [r11-78h], rdx
0x1800567dc  lea     rdx, aRtmgrrdconfigs_1; "RtMgrRdConfigStore::SetIpChangeNotifica"...
0x1800567e3  lea     rcx, [r11-58h]; this
0x1800567e7  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x1800567ec  lea     rbx, [rdi+0B8h]
0x1800567f3  mov     dl, 1; Wait
0x1800567f5  mov     rcx, rbx; Resource
0x1800567f8  call    cs:__imp_RtlAcquireResourceShared
0x1800567fe  lea     rcx, [rdi+8]
0x180056802  mov     r8, rsi
0x180056805  lea     rdx, [rsp+98h+arg_0]
0x18005680d  call    ?lower_bound@?$_Hash@V?$_Umap_traits@U_GUID@@PEAVRtMgrRoutingDomainConfig@@V?$_Hash_compare@U_GUID@@UGuidHash@@UGuidEquality@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRtMgrRoutingDomainConfig@@@std@@@4@$0A@@tr1@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$pair@$$CBU_GUID@@PEAVRtMgrRoutingDomainConfig@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRtMgrRoutingDomainConfig@@@std@@@2@@std@@@2@AEBU_GUID@@@Z; std::_Hash<std::tr1::_Umap_traits<_GUID,RtMgrRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RtMgrRoutingDomainConfig *>>,0>>::lower_bound(_GUID const &)
0x180056812  mov     rcx, [rsp+98h+arg_0]
0x18005681a  cmp     rcx, [rdi+10h]
0x18005681e  jz      short loc_18005682F
0x180056820  mov     r8, rbp; void *
0x180056823  mov     edx, r14d; unsigned int
0x180056826  mov     rcx, [rcx+20h]; this
0x18005682a  call    ?SetIpChangeNotificationHandle@RtMgrRoutingDomainConfig@@QEAAXKPEAX@Z; RtMgrRoutingDomainConfig::SetIpChangeNotificationHandle(ulong,void *)
0x18005682f  mov     rcx, rbx; Resource
0x180056832  call    cs:__imp_RtlReleaseResource
0x180056838  nop
0x180056839  lea     rcx, [rsp+98h+var_58]; this
0x18005683e  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180056843  lea     r11, [rsp+98h+var_18]
0x18005684b  mov     rbx, [r11+28h]
0x18005684f  mov     rbp, [r11+30h]
0x180056853  mov     rsp, r11
0x180056856  pop     r14
0x180056858  pop     rdi
0x180056859  pop     rsi
0x18005685a  retn
```
