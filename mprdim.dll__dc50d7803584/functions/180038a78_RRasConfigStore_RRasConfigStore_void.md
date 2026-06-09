# RRasConfigStore::~RRasConfigStore(void)

- ea: `0x180038a78`
- end: `0x180038a9e`
- name: `??1RRasConfigStore@@QEAA@XZ`
- size: `38`
- prototype: `void __fastcall(RRasConfigStore *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180034eec`

## callees

- `0x1800389e4`
- `0x180038dc0`

## import_xrefs

- `ntdll!RtlDeleteResource` at `0x180038a8a`
- `ntdll!RtlDeleteResource` at `0x180038a8a`

## pseudocode

```c
void __fastcall RRasConfigStore::~RRasConfigStore(RRasConfigStore *this)
{
  RRasConfigStore::CleanupConfigStore(this);
  RtlDeleteResource((PRTL_RESOURCE)((char *)this + 112));
  std::_Hash<std::tr1::_Umap_traits<_GUID,RRasRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>,0>>::~_Hash<std::tr1::_Umap_traits<_GUID,RRasRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>,0>>((__int64)this + 16);
}

```

## disassembly

```asm
0x180038a78  push    rbx
0x180038a7a  sub     rsp, 20h
0x180038a7e  mov     rbx, rcx
0x180038a81  call    ?CleanupConfigStore@RRasConfigStore@@QEAAKXZ; RRasConfigStore::CleanupConfigStore(void)
0x180038a86  lea     rcx, [rbx+70h]; Resource
0x180038a8a  call    cs:__imp_RtlDeleteResource
0x180038a90  lea     rcx, [rbx+10h]
0x180038a94  add     rsp, 20h
0x180038a98  pop     rbx
0x180038a99  jmp     ??1?$_Hash@V?$_Umap_traits@U_GUID@@PEAVRRasRoutingDomainConfig@@V?$_Hash_compare@U_GUID@@UGuidHash@@UGuidEquality@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@@4@$0A@@tr1@std@@@std@@QEAA@XZ; std::_Hash<std::tr1::_Umap_traits<_GUID,RRasRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>,0>>::~_Hash<std::tr1::_Umap_traits<_GUID,RRasRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>,0>>(void)
```
