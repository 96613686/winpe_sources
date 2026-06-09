# CDevice::~CDevice(void)

- ea: `0x180086fcc`
- end: `0x18008709f`
- name: `??1CDevice@@QEAA@XZ`
- size: `211`
- prototype: `void __fastcall(CDevice *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180086ef8`
- `0x180086f78`

## callees

- `0x180029fbc`
- `0x18002bd40`
- `0x18004418c`
- `0x180044234`
- `0x180047324`
- `0x180084ed0`
- `0x18009d94c`
- `0x1800ae4fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180087005`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180087072`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008707f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180087005`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180087072`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008707f`

## pseudocode

```c
void __fastcall CDevice::~CDevice(CDevice *this)
{
  __int64 v2; // rcx

  CShaderCacheAdapter::~CShaderCacheAdapter((CDevice *)((char *)this + 3768));
  std::_List_node<NotificationRegistry::NotificationRecord,void *>::_Free_non_head<std::allocator<std::_List_node<NotificationRegistry::NotificationRecord,void *>>>(
    v2,
    *((_QWORD *)this + 469));
  std::_Deallocate<16>(*((_QWORD *)this + 469), 40);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 3712));
  std::_Hash<std::_Umap_traits<SmallRasterizerStateDesc const *,CRasterizerState *,std::_Uhash_compare<SmallRasterizerStateDesc const *,HashDeref<SmallRasterizerStateDesc>,EqualToDeref<SmallRasterizerStateDesc>>,std::allocator<std::pair<SmallRasterizerStateDesc const * const,CRasterizerState *>>,0>>::~_Hash<std::_Umap_traits<SmallRasterizerStateDesc const *,CRasterizerState *,std::_Uhash_compare<SmallRasterizerStateDesc const *,HashDeref<SmallRasterizerStateDesc>,EqualToDeref<SmallRasterizerStateDesc>>,std::allocator<std::pair<SmallRasterizerStateDesc const * const,CRasterizerState *>>,0>>((char *)this + 3568);
  std::_Hash<std::_Umap_traits<SmallRasterizerStateDesc const *,CRasterizerState *,std::_Uhash_compare<SmallRasterizerStateDesc const *,HashDeref<SmallRasterizerStateDesc>,EqualToDeref<SmallRasterizerStateDesc>>,std::allocator<std::pair<SmallRasterizerStateDesc const * const,CRasterizerState *>>,0>>::~_Hash<std::_Umap_traits<SmallRasterizerStateDesc const *,CRasterizerState *,std::_Uhash_compare<SmallRasterizerStateDesc const *,HashDeref<SmallRasterizerStateDesc>,EqualToDeref<SmallRasterizerStateDesc>>,std::allocator<std::pair<SmallRasterizerStateDesc const * const,CRasterizerState *>>,0>>((char *)this + 3504);
  std::_Hash<std::_Umap_traits<SmallRasterizerStateDesc const *,CRasterizerState *,std::_Uhash_compare<SmallRasterizerStateDesc const *,HashDeref<SmallRasterizerStateDesc>,EqualToDeref<SmallRasterizerStateDesc>>,std::allocator<std::pair<SmallRasterizerStateDesc const * const,CRasterizerState *>>,0>>::~_Hash<std::_Umap_traits<SmallRasterizerStateDesc const *,CRasterizerState *,std::_Uhash_compare<SmallRasterizerStateDesc const *,HashDeref<SmallRasterizerStateDesc>,EqualToDeref<SmallRasterizerStateDesc>>,std::allocator<std::pair<SmallRasterizerStateDesc const * const,CRasterizerState *>>,0>>((char *)this + 3432);
  std::_Hash<std::_Umap_traits<SmallRasterizerStateDesc const *,CRasterizerState *,std::_Uhash_compare<SmallRasterizerStateDesc const *,HashDeref<SmallRasterizerStateDesc>,EqualToDeref<SmallRasterizerStateDesc>>,std::allocator<std::pair<SmallRasterizerStateDesc const * const,CRasterizerState *>>,0>>::~_Hash<std::_Umap_traits<SmallRasterizerStateDesc const *,CRasterizerState *,std::_Uhash_compare<SmallRasterizerStateDesc const *,HashDeref<SmallRasterizerStateDesc>,EqualToDeref<SmallRasterizerStateDesc>>,std::allocator<std::pair<SmallRasterizerStateDesc const * const,CRasterizerState *>>,0>>((char *)this + 3368);
  std::_Hash<std::_Umap_traits<SmallRasterizerStateDesc const *,CRasterizerState *,std::_Uhash_compare<SmallRasterizerStateDesc const *,HashDeref<SmallRasterizerStateDesc>,EqualToDeref<SmallRasterizerStateDesc>>,std::allocator<std::pair<SmallRasterizerStateDesc const * const,CRasterizerState *>>,0>>::~_Hash<std::_Umap_traits<SmallRasterizerStateDesc const *,CRasterizerState *,std::_Uhash_compare<SmallRasterizerStateDesc const *,HashDeref<SmallRasterizerStateDesc>,EqualToDeref<SmallRasterizerStateDesc>>,std::allocator<std::pair<SmallRasterizerStateDesc const * const,CRasterizerState *>>,0>>((char *)this + 3304);
  std::_Hash<std::_Umap_traits<SmallBlendStateDesc const *,CBlendState *,std::_Uhash_compare<SmallBlendStateDesc const *,HashDeref<SmallBlendStateDesc>,EqualToDeref<SmallBlendStateDesc>>,std::allocator<std::pair<SmallBlendStateDesc const * const,CBlendState *>>,0>>::~_Hash<std::_Umap_traits<SmallBlendStateDesc const *,CBlendState *,std::_Uhash_compare<SmallBlendStateDesc const *,HashDeref<SmallBlendStateDesc>,EqualToDeref<SmallBlendStateDesc>>,std::allocator<std::pair<SmallBlendStateDesc const * const,CBlendState *>>,0>>((char *)this + 3240);
  std::_Hash<std::_Umap_traits<SmallRasterizerStateDesc const *,CRasterizerState *,std::_Uhash_compare<SmallRasterizerStateDesc const *,HashDeref<SmallRasterizerStateDesc>,EqualToDeref<SmallRasterizerStateDesc>>,std::allocator<std::pair<SmallRasterizerStateDesc const * const,CRasterizerState *>>,0>>::~_Hash<std::_Umap_traits<SmallRasterizerStateDesc const *,CRasterizerState *,std::_Uhash_compare<SmallRasterizerStateDesc const *,HashDeref<SmallRasterizerStateDesc>,EqualToDeref<SmallRasterizerStateDesc>>,std::allocator<std::pair<SmallRasterizerStateDesc const * const,CRasterizerState *>>,0>>((char *)this + 3176);
  CCLSAllocator::~CCLSAllocator((CDevice *)((char *)this + 3040));
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 75);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1792));
  CDestructionNotifier::~CDestructionNotifier((CDevice *)((char *)this + 128));
  CPrivateDataImpl<ID3D11UnorderedAccessView1>::~CPrivateDataImpl<ID3D11UnorderedAccessView1>((char *)this + 16);
}

```

## disassembly

```asm
0x180086fcc  push    rbx
0x180086fce  sub     rsp, 20h
0x180086fd2  mov     rbx, rcx
0x180086fd5  add     rcx, 0EB8h; this
0x180086fdc  call    ??1CShaderCacheAdapter@@QEAA@XZ; CShaderCacheAdapter::~CShaderCacheAdapter(void)
0x180086fe1  mov     rdx, [rbx+0EA8h]
0x180086fe8  call    ??$_Free_non_head@V?$allocator@U?$_List_node@UNotificationRecord@NotificationRegistry@@PEAX@std@@@std@@@?$_List_node@UNotificationRecord@NotificationRegistry@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@UNotificationRecord@NotificationRegistry@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<NotificationRegistry::NotificationRecord,void *>::_Free_non_head<std::allocator<std::_List_node<NotificationRegistry::NotificationRecord,void *>>>(std::allocator<std::_List_node<NotificationRegistry::NotificationRecord,void *>> &,std::_List_node<NotificationRegistry::NotificationRecord,void *> *)
0x180086fed  mov     rcx, [rbx+0EA8h]
0x180086ff4  mov     edx, 28h ; '('
0x180086ff9  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180086ffe  lea     rcx, [rbx+0E80h]; lpCriticalSection
0x180087005  call    cs:__imp_DeleteCriticalSection
0x18008700b  lea     rcx, [rbx+0DF0h]
0x180087012  call    ??1?$_Hash@V?$_Umap_traits@PEBVSmallRasterizerStateDesc@@PEAVCRasterizerState@@V?$_Uhash_compare@PEBVSmallRasterizerStateDesc@@V?$HashDeref@VSmallRasterizerStateDesc@@@@V?$EqualToDeref@VSmallRasterizerStateDesc@@@@@std@@V?$allocator@U?$pair@QEBVSmallRasterizerStateDesc@@PEAVCRasterizerState@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<SmallRasterizerStateDesc const *,CRasterizerState *,std::_Uhash_compare<SmallRasterizerStateDesc const *,HashDeref<SmallRasterizerStateDesc>,EqualToDeref<SmallRasterizerStateDesc>>,std::allocator<std::pair<SmallRasterizerStateDesc const * const,CRasterizerState *>>,0>>::~_Hash<std::_Umap_traits<SmallRasterizerStateDesc const *,CRasterizerState *,std::_Uhash_compare<SmallRasterizerStateDesc const *,HashDeref<SmallRasterizerStateDesc>,EqualToDeref<SmallRasterizerStateDesc>>,std::allocator<std::pair<SmallRasterizerStateDesc const * const,CRasterizerState *>>,0>>(void)
0x180087017  lea     rcx, [rbx+0DB0h]
0x18008701e  call    ??1?$_Hash@V?$_Umap_traits@PEBVSmallRasterizerStateDesc@@PEAVCRasterizerState@@V?$_Uhash_compare@PEBVSmallRasterizerStateDesc@@V?$HashDeref@VSmallRasterizerStateDesc@@@@V?$EqualToDeref@VSmallRasterizerStateDesc@@@@@std@@V?$allocator@U?$pair@QEBVSmallRasterizerStateDesc@@PEAVCRasterizerState@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<SmallRasterizerStateDesc const *,CRasterizerState *,std::_Uhash_compare<SmallRasterizerStateDesc const *,HashDeref<SmallRasterizerStateDesc>,EqualToDeref<SmallRasterizerStateDesc>>,std::allocator<std::pair<SmallRasterizerStateDesc const * const,CRasterizerState *>>,0>>::~_Hash<std::_Umap_traits<SmallRasterizerStateDesc const *,CRasterizerState *,std::_Uhash_compare<SmallRasterizerStateDesc const *,HashDeref<SmallRasterizerStateDesc>,EqualToDeref<SmallRasterizerStateDesc>>,std::allocator<std::pair<SmallRasterizerStateDesc const * const,CRasterizerState *>>,0>>(void)
0x180087023  lea     rcx, [rbx+0D68h]
0x18008702a  call    ??1?$_Hash@V?$_Umap_traits@PEBVSmallRasterizerStateDesc@@PEAVCRasterizerState@@V?$_Uhash_compare@PEBVSmallRasterizerStateDesc@@V?$HashDeref@VSmallRasterizerStateDesc@@@@V?$EqualToDeref@VSmallRasterizerStateDesc@@@@@std@@V?$allocator@U?$pair@QEBVSmallRasterizerStateDesc@@PEAVCRasterizerState@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<SmallRasterizerStateDesc const *,CRasterizerState *,std::_Uhash_compare<SmallRasterizerStateDesc const *,HashDeref<SmallRasterizerStateDesc>,EqualToDeref<SmallRasterizerStateDesc>>,std::allocator<std::pair<SmallRasterizerStateDesc const * const,CRasterizerState *>>,0>>::~_Hash<std::_Umap_traits<SmallRasterizerStateDesc const *,CRasterizerState *,std::_Uhash_compare<SmallRasterizerStateDesc const *,HashDeref<SmallRasterizerStateDesc>,EqualToDeref<SmallRasterizerStateDesc>>,std::allocator<std::pair<SmallRasterizerStateDesc const * const,CRasterizerState *>>,0>>(void)
0x18008702f  lea     rcx, [rbx+0D28h]
0x180087036  call    ??1?$_Hash@V?$_Umap_traits@PEBVSmallRasterizerStateDesc@@PEAVCRasterizerState@@V?$_Uhash_compare@PEBVSmallRasterizerStateDesc@@V?$HashDeref@VSmallRasterizerStateDesc@@@@V?$EqualToDeref@VSmallRasterizerStateDesc@@@@@std@@V?$allocator@U?$pair@QEBVSmallRasterizerStateDesc@@PEAVCRasterizerState@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<SmallRasterizerStateDesc const *,CRasterizerState *,std::_Uhash_compare<SmallRasterizerStateDesc const *,HashDeref<SmallRasterizerStateDesc>,EqualToDeref<SmallRasterizerStateDesc>>,std::allocator<std::pair<SmallRasterizerStateDesc const * const,CRasterizerState *>>,0>>::~_Hash<std::_Umap_traits<SmallRasterizerStateDesc const *,CRasterizerState *,std::_Uhash_compare<SmallRasterizerStateDesc const *,HashDeref<SmallRasterizerStateDesc>,EqualToDeref<SmallRasterizerStateDesc>>,std::allocator<std::pair<SmallRasterizerStateDesc const * const,CRasterizerState *>>,0>>(void)
0x18008703b  lea     rcx, [rbx+0CE8h]
0x180087042  call    ??1?$_Hash@V?$_Umap_traits@PEBVSmallRasterizerStateDesc@@PEAVCRasterizerState@@V?$_Uhash_compare@PEBVSmallRasterizerStateDesc@@V?$HashDeref@VSmallRasterizerStateDesc@@@@V?$EqualToDeref@VSmallRasterizerStateDesc@@@@@std@@V?$allocator@U?$pair@QEBVSmallRasterizerStateDesc@@PEAVCRasterizerState@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<SmallRasterizerStateDesc const *,CRasterizerState *,std::_Uhash_compare<SmallRasterizerStateDesc const *,HashDeref<SmallRasterizerStateDesc>,EqualToDeref<SmallRasterizerStateDesc>>,std::allocator<std::pair<SmallRasterizerStateDesc const * const,CRasterizerState *>>,0>>::~_Hash<std::_Umap_traits<SmallRasterizerStateDesc const *,CRasterizerState *,std::_Uhash_compare<SmallRasterizerStateDesc const *,HashDeref<SmallRasterizerStateDesc>,EqualToDeref<SmallRasterizerStateDesc>>,std::allocator<std::pair<SmallRasterizerStateDesc const * const,CRasterizerState *>>,0>>(void)
0x180087047  lea     rcx, [rbx+0CA8h]
0x18008704e  call    ??1?$_Hash@V?$_Umap_traits@PEBVSmallBlendStateDesc@@PEAVCBlendState@@V?$_Uhash_compare@PEBVSmallBlendStateDesc@@V?$HashDeref@VSmallBlendStateDesc@@@@V?$EqualToDeref@VSmallBlendStateDesc@@@@@std@@V?$allocator@U?$pair@QEBVSmallBlendStateDesc@@PEAVCBlendState@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<SmallBlendStateDesc const *,CBlendState *,std::_Uhash_compare<SmallBlendStateDesc const *,HashDeref<SmallBlendStateDesc>,EqualToDeref<SmallBlendStateDesc>>,std::allocator<std::pair<SmallBlendStateDesc const * const,CBlendState *>>,0>>::~_Hash<std::_Umap_traits<SmallBlendStateDesc const *,CBlendState *,std::_Uhash_compare<SmallBlendStateDesc const *,HashDeref<SmallBlendStateDesc>,EqualToDeref<SmallBlendStateDesc>>,std::allocator<std::pair<SmallBlendStateDesc const * const,CBlendState *>>,0>>(void)
0x180087053  lea     rcx, [rbx+0C68h]
0x18008705a  call    ??1?$_Hash@V?$_Umap_traits@PEBVSmallRasterizerStateDesc@@PEAVCRasterizerState@@V?$_Uhash_compare@PEBVSmallRasterizerStateDesc@@V?$HashDeref@VSmallRasterizerStateDesc@@@@V?$EqualToDeref@VSmallRasterizerStateDesc@@@@@std@@V?$allocator@U?$pair@QEBVSmallRasterizerStateDesc@@PEAVCRasterizerState@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<SmallRasterizerStateDesc const *,CRasterizerState *,std::_Uhash_compare<SmallRasterizerStateDesc const *,HashDeref<SmallRasterizerStateDesc>,EqualToDeref<SmallRasterizerStateDesc>>,std::allocator<std::pair<SmallRasterizerStateDesc const * const,CRasterizerState *>>,0>>::~_Hash<std::_Umap_traits<SmallRasterizerStateDesc const *,CRasterizerState *,std::_Uhash_compare<SmallRasterizerStateDesc const *,HashDeref<SmallRasterizerStateDesc>,EqualToDeref<SmallRasterizerStateDesc>>,std::allocator<std::pair<SmallRasterizerStateDesc const * const,CRasterizerState *>>,0>>(void)
0x18008705f  lea     rcx, [rbx+0BE0h]; this
0x180087066  call    ??1CCLSAllocator@@QEAA@XZ; CCLSAllocator::~CCLSAllocator(void)
0x18008706b  lea     rcx, [rbx+0BB8h]; lpCriticalSection
0x180087072  call    cs:__imp_DeleteCriticalSection
0x180087078  lea     rcx, [rbx+700h]; lpCriticalSection
0x18008707f  call    cs:__imp_DeleteCriticalSection
0x180087085  lea     rcx, [rbx+80h]; this
0x18008708c  call    ??1CDestructionNotifier@@QEAA@XZ; CDestructionNotifier::~CDestructionNotifier(void)
0x180087091  lea     rcx, [rbx+10h]
0x180087095  add     rsp, 20h
0x180087099  pop     rbx
0x18008709a  jmp     ??1?$CPrivateDataImpl@UID3D11UnorderedAccessView1@@@@QEAA@XZ; CPrivateDataImpl<ID3D11UnorderedAccessView1>::~CPrivateDataImpl<ID3D11UnorderedAccessView1>(void)
```
