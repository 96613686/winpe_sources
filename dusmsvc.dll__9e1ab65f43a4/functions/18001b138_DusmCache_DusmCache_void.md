# DusmCache::~DusmCache(void)

- ea: `0x18001b138`
- end: `0x18001b158`
- name: `??1DusmCache@@AEAA@XZ`
- size: `32`
- prototype: `void __fastcall(DusmCache *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001d8b4`

## callees

- `0x18001afd8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b145`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b145`

## pseudocode

```c
void __fastcall DusmCache::~DusmCache(DusmCache *this)
{
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  std::_Tree<std::_Tmap_traits<_GUID,std::map<std::wstring,DusmCache::DusmCacheCost>,DusmCache::GuidCompare,std::allocator<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>>,0>>::~_Tree<std::_Tmap_traits<_GUID,std::map<std::wstring,DusmCache::DusmCacheCost>,DusmCache::GuidCompare,std::allocator<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>>,0>>((void **)this);
}

```

## disassembly

```asm
0x18001b138  push    rbx
0x18001b13a  sub     rsp, 20h
0x18001b13e  mov     rbx, rcx
0x18001b141  add     rcx, 10h; lpCriticalSection
0x18001b145  call    cs:__imp_DeleteCriticalSection
0x18001b14b  mov     rcx, rbx
0x18001b14e  add     rsp, 20h
0x18001b152  pop     rbx
0x18001b153  jmp     ??1?$_Tree@V?$_Tmap_traits@U_GUID@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@@std@@@2@@std@@UGuidCompare@DusmCache@@V?$allocator@U?$pair@$$CBU_GUID@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@@std@@@2@@std@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<_GUID,std::map<std::wstring,DusmCache::DusmCacheCost>,DusmCache::GuidCompare,std::allocator<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>>,0>>::~_Tree<std::_Tmap_traits<_GUID,std::map<std::wstring,DusmCache::DusmCacheCost>,DusmCache::GuidCompare,std::allocator<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>>,0>>(void)
```
