# RRasConfigStore::RRasConfigStore(void)

- ea: `0x180038788`
- end: `0x180038822`
- name: `??0RRasConfigStore@@AEAA@XZ`
- size: `154`
- prototype: `RRasConfigStore *__fastcall(RRasConfigStore *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18003d380`

## callees

- `0x1800386dc`
- `0x180038788`
- `0x18004583c`
- `0x180045ad4`

## import_xrefs

- `ntdll!RtlInitializeResource` at `0x1800387fa`
- `ntdll!RtlInitializeResource` at `0x1800387fa`

## string_xrefs

- `0x1800387dd`: `RRasConfigStore::RRasConfigStore`

## pseudocode

```c
RRasConfigStore *__fastcall RRasConfigStore::RRasConfigStore(RRasConfigStore *this)
{
  void (*v2)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  __int64 v4; // [rsp+20h] [rbp-48h] BYREF
  __int128 v5; // [rsp+28h] [rbp-40h]
  __int128 v6; // [rsp+38h] [rbp-30h]
  __int64 v7; // [rsp+48h] [rbp-20h]
  int v8; // [rsp+50h] [rbp-18h]
  int v9; // [rsp+54h] [rbp-14h]

  std::tr1::unordered_map<_GUID,RRasRoutingDomainConfig *,GuidHash,GuidEquality,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>>::unordered_map<_GUID,RRasRoutingDomainConfig *,GuidHash,GuidEquality,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>>((__int64)this + 16);
  v5 = 0;
  v4 = 0;
  v6 = 0;
  v7 = 0;
  v8 = -1;
  v9 = 0;
  if ( *((_QWORD *)&xmmword_180071090 + 1) )
    EtwFuncEntryExitTracer::Initialize((EtwFuncEntryExitTracer *)&v4, L"RRasConfigStore::RRasConfigStore", 0, v2);
  *((_QWORD *)this + 13) = 0;
  RtlInitializeResource((PRTL_RESOURCE)((char *)this + 112));
  *((_DWORD *)this + 27) = 1;
  *(_QWORD *)this = 0;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v4);
  return this;
}

```

## disassembly

```asm
0x180038788  mov     [rsp+arg_0], rcx
0x18003878d  push    rbx
0x18003878e  sub     rsp, 60h
0x180038792  mov     rbx, rcx
0x180038795  add     rcx, 10h
0x180038799  call    ??0?$unordered_map@U_GUID@@PEAVRRasRoutingDomainConfig@@UGuidHash@@UGuidEquality@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@@std@@@tr1@std@@QEAA@XZ; std::tr1::unordered_map<_GUID,RRasRoutingDomainConfig *,GuidHash,GuidEquality,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>>::unordered_map<_GUID,RRasRoutingDomainConfig *,GuidHash,GuidEquality,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>>(void)
0x18003879e  nop
0x18003879f  xorps   xmm0, xmm0
0x1800387a2  movdqu  [rsp+68h+var_40], xmm0
0x1800387a8  mov     [rsp+68h+var_48], 0
0x1800387b1  movdqu  [rsp+68h+var_30], xmm0
0x1800387b7  mov     [rsp+68h+var_20], 0
0x1800387c0  mov     [rsp+68h+var_18], 0FFFFFFFFh
0x1800387c8  mov     [rsp+68h+var_14], 0
0x1800387d0  cmp     qword ptr cs:xmmword_180071090+8, 0
0x1800387d8  jz      short loc_1800387EE
0x1800387da  xor     r8d, r8d; unsigned int *
0x1800387dd  lea     rdx, aRrasconfigstor_8; "RRasConfigStore::RRasConfigStore"
0x1800387e4  lea     rcx, [rsp+68h+var_48]; this
0x1800387e9  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x1800387ee  mov     qword ptr [rbx+68h], 0
0x1800387f6  lea     rcx, [rbx+70h]; Resource
0x1800387fa  call    cs:__imp_RtlInitializeResource
0x180038800  mov     dword ptr [rbx+6Ch], 1
0x180038807  mov     qword ptr [rbx], 0
0x18003880e  lea     rcx, [rsp+68h+var_48]; this
0x180038813  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180038818  nop
0x180038819  mov     rax, rbx
0x18003881c  add     rsp, 60h
0x180038820  pop     rbx
0x180038821  retn
```
