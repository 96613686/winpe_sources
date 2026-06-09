# NDXGI::CDevice::~CDevice(void)

- ea: `0x18008636c`
- end: `0x18008659b`
- name: `??1CDevice@NDXGI@@UEAA@XZ`
- size: `559`
- prototype: `void __fastcall(NDXGI::CDevice *__hidden this)`
- caller_count: `4`
- callee_count: `16`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800862bc`
- `0x180086328`
- `0x1800a59e4`
- `0x1800ae850`

## callees

- `0x180011050`
- `0x18002c7f0`
- `0x180030710`
- `0x180034550`
- `0x180044234`
- `0x18004429c`
- `0x180049310`
- `0x18004f47c`
- `0x180059644`
- `0x180059b30`
- `0x18008636c`
- `0x180086a50`
- `0x180086c6c`
- `0x18008814c`
- `0x18009d94c`
- `0x1800ae3c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180086449`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008652e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180086547`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180086449`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008652e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180086547`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180086385`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180086385`

## pseudocode

```c
void __fastcall NDXGI::CDevice::~CDevice(NDXGI::CDevice *this, unsigned int a2)
{
  void *v3; // rcx
  NDXGI::CUMDAdapter *v4; // rcx
  void *v5; // rcx
  std::_Ref_count_base *v6; // rcx
  _QWORD **v7; // rcx
  _QWORD *v8; // rcx
  _QWORD *v9; // rbx
  __int64 v10; // rcx
  __int64 v11; // rcx
  _QWORD **v12; // rcx
  _QWORD *v13; // rdx
  _QWORD *v14; // rbx

  v3 = (void *)*((_QWORD *)this + 122);
  if ( v3 )
    CloseHandle(v3);
  v4 = (NDXGI::CUMDAdapter *)*((_QWORD *)this + 12);
  if ( v4 )
    NDXGI::CUMDAdapter::`scalar deleting destructor'(v4, a2);
  v5 = (void *)*((_QWORD *)this + 119);
  *((_QWORD *)this + 12) = 0;
  operator delete(v5);
  v6 = (std::_Ref_count_base *)*((_QWORD *)this + 254);
  if ( v6 )
    std::_Ref_count_base::_Decref(v6);
  ATL::CComPtrBase<CBuffer>::~CComPtrBase<CBuffer>((char *)this + 2016);
  ATL::CComPtrBase<CBuffer>::~CComPtrBase<CBuffer>((char *)this + 2008);
  NDXGI::OpaqueHandleManager<BatchablePresentMPO>::~OpaqueHandleManager<BatchablePresentMPO>((char *)this + 1920);
  NDXGI::OpaqueHandleManager<BatchablePresent>::~OpaqueHandleManager<BatchablePresent>((char *)this + 1856);
  NDXGI::OpaqueHandleManager<std::shared_ptr<BatchablePresent>>::~OpaqueHandleManager<std::shared_ptr<BatchablePresent>>((char *)this + 1792);
  NDXGI::OpaqueHandleManager<NDXGI::SyncPacket>::~OpaqueHandleManager<NDXGI::SyncPacket>((char *)this + 1728);
  std::_Hash<std::_Umap_traits<SmallRasterizerStateDesc const *,CRasterizerState *,std::_Uhash_compare<SmallRasterizerStateDesc const *,HashDeref<SmallRasterizerStateDesc>,EqualToDeref<SmallRasterizerStateDesc>>,std::allocator<std::pair<SmallRasterizerStateDesc const * const,CRasterizerState *>>,0>>::~_Hash<std::_Umap_traits<SmallRasterizerStateDesc const *,CRasterizerState *,std::_Uhash_compare<SmallRasterizerStateDesc const *,HashDeref<SmallRasterizerStateDesc>,EqualToDeref<SmallRasterizerStateDesc>>,std::allocator<std::pair<SmallRasterizerStateDesc const * const,CRasterizerState *>>,0>>((char *)this + 1656);
  std::_Hash<std::_Umap_traits<unsigned long,NDXGI::CDevice::SCreateLayeredChildThreadLocalData *,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,NDXGI::CDevice::SCreateLayeredChildThreadLocalData *>>,0>>::~_Hash<std::_Umap_traits<unsigned long,NDXGI::CDevice::SCreateLayeredChildThreadLocalData *,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,NDXGI::CDevice::SCreateLayeredChildThreadLocalData *>>,0>>((char *)this + 1584);
  std::_Hash<std::_Umap_traits<SmallRasterizerStateDesc const *,CRasterizerState *,std::_Uhash_compare<SmallRasterizerStateDesc const *,HashDeref<SmallRasterizerStateDesc>,EqualToDeref<SmallRasterizerStateDesc>>,std::allocator<std::pair<SmallRasterizerStateDesc const * const,CRasterizerState *>>,0>>::~_Hash<std::_Umap_traits<SmallRasterizerStateDesc const *,CRasterizerState *,std::_Uhash_compare<SmallRasterizerStateDesc const *,HashDeref<SmallRasterizerStateDesc>,EqualToDeref<SmallRasterizerStateDesc>>,std::allocator<std::pair<SmallRasterizerStateDesc const * const,CRasterizerState *>>,0>>((char *)this + 1504);
  std::_Hash<std::_Umap_traits<SmallRasterizerStateDesc const *,CRasterizerState *,std::_Uhash_compare<SmallRasterizerStateDesc const *,HashDeref<SmallRasterizerStateDesc>,EqualToDeref<SmallRasterizerStateDesc>>,std::allocator<std::pair<SmallRasterizerStateDesc const * const,CRasterizerState *>>,0>>::~_Hash<std::_Umap_traits<SmallRasterizerStateDesc const *,CRasterizerState *,std::_Uhash_compare<SmallRasterizerStateDesc const *,HashDeref<SmallRasterizerStateDesc>,EqualToDeref<SmallRasterizerStateDesc>>,std::allocator<std::pair<SmallRasterizerStateDesc const * const,CRasterizerState *>>,0>>((char *)this + 1424);
  std::_Hash<std::_Umap_traits<SmallRasterizerStateDesc const *,CRasterizerState *,std::_Uhash_compare<SmallRasterizerStateDesc const *,HashDeref<SmallRasterizerStateDesc>,EqualToDeref<SmallRasterizerStateDesc>>,std::allocator<std::pair<SmallRasterizerStateDesc const * const,CRasterizerState *>>,0>>::~_Hash<std::_Umap_traits<SmallRasterizerStateDesc const *,CRasterizerState *,std::_Uhash_compare<SmallRasterizerStateDesc const *,HashDeref<SmallRasterizerStateDesc>,EqualToDeref<SmallRasterizerStateDesc>>,std::allocator<std::pair<SmallRasterizerStateDesc const * const,CRasterizerState *>>,0>>((char *)this + 1344);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1296));
  std::vector<void *>::_Tidy((char *)this + 1272);
  v7 = (_QWORD **)*((_QWORD *)this + 157);
  *v7[1] = 0;
  v8 = *v7;
  if ( v8 )
  {
    do
    {
      v9 = (_QWORD *)*v8;
      std::_Deallocate<16>(v8, 24);
      v8 = v9;
    }
    while ( v9 );
  }
  std::_Deallocate<16>(*((_QWORD *)this + 157), 24);
  v10 = *((_QWORD *)this + 153);
  if ( v10 )
  {
    std::_Deallocate<16>(v10, (*((_QWORD *)this + 155) - v10) & 0xFFFFFFFFFFFFFFF8uLL);
    *((_QWORD *)this + 153) = 0;
    *((_QWORD *)this + 154) = 0;
    *((_QWORD *)this + 155) = 0;
  }
  v11 = *((_QWORD *)this + 150);
  if ( v11 )
  {
    std::_Deallocate<16>(v11, (*((_QWORD *)this + 152) - v11) & 0xFFFFFFFFFFFFFFF8uLL);
    *((_QWORD *)this + 150) = 0;
    *((_QWORD *)this + 151) = 0;
    *((_QWORD *)this + 152) = 0;
  }
  std::vector<unsigned int>::_Tidy((char *)this + 1160);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 28);
  std::vector<unsigned int>::_Tidy((char *)this + 1096);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1056));
  v12 = (_QWORD **)*((_QWORD *)this + 130);
  *v12[1] = 0;
  v13 = *v12;
  if ( *v12 )
  {
    do
    {
      v14 = (_QWORD *)*v13;
      std::_List_node<NDXGI::CContext,void *>::_Freenode<std::allocator<std::_List_node<NDXGI::CContext,void *>>>();
      v13 = v14;
    }
    while ( v14 );
  }
  std::_Deallocate<16>(*((_QWORD *)this + 130), 136);
  ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>((char *)this + 56);
}

```

## disassembly

```asm
0x18008636c  mov     [rsp+arg_0], rbx
0x180086371  push    rdi
0x180086372  sub     rsp, 20h
0x180086376  mov     rdi, rcx
0x180086379  mov     rcx, [rcx+3D0h]; hObject
0x180086380  test    rcx, rcx
0x180086383  jz      short loc_18008638B
0x180086385  call    cs:__imp_CloseHandle
0x18008638b  mov     rcx, [rdi+60h]; this
0x18008638f  test    rcx, rcx
0x180086392  jz      short loc_180086399
0x180086394  call    ??_GCUMDAdapter@NDXGI@@QEAAPEAXI@Z; NDXGI::CUMDAdapter::`scalar deleting destructor'(uint)
0x180086399  mov     rcx, [rdi+3B8h]; lpMem
0x1800863a0  mov     qword ptr [rdi+60h], 0
0x1800863a8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800863ad  mov     rcx, [rdi+7F0h]; this
0x1800863b4  test    rcx, rcx
0x1800863b7  jz      short loc_1800863BE
0x1800863b9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800863be  lea     rcx, [rdi+7E0h]
0x1800863c5  call    ??1?$CComPtrBase@VCBuffer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CBuffer>::~CComPtrBase<CBuffer>(void)
0x1800863ca  lea     rcx, [rdi+7D8h]
0x1800863d1  call    ??1?$CComPtrBase@VCBuffer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CBuffer>::~CComPtrBase<CBuffer>(void)
0x1800863d6  lea     rcx, [rdi+780h]
0x1800863dd  call    ??1?$OpaqueHandleManager@UBatchablePresentMPO@@@NDXGI@@QEAA@XZ; NDXGI::OpaqueHandleManager<BatchablePresentMPO>::~OpaqueHandleManager<BatchablePresentMPO>(void)
0x1800863e2  lea     rcx, [rdi+740h]
0x1800863e9  call    ??1?$OpaqueHandleManager@UBatchablePresent@@@NDXGI@@QEAA@XZ; NDXGI::OpaqueHandleManager<BatchablePresent>::~OpaqueHandleManager<BatchablePresent>(void)
0x1800863ee  lea     rcx, [rdi+700h]
0x1800863f5  call    ??1?$OpaqueHandleManager@V?$shared_ptr@UBatchablePresent@@@std@@@NDXGI@@QEAA@XZ; NDXGI::OpaqueHandleManager<std::shared_ptr<BatchablePresent>>::~OpaqueHandleManager<std::shared_ptr<BatchablePresent>>(void)
0x1800863fa  lea     rcx, [rdi+6C0h]
0x180086401  call    ??1?$OpaqueHandleManager@USyncPacket@NDXGI@@@NDXGI@@QEAA@XZ; NDXGI::OpaqueHandleManager<NDXGI::SyncPacket>::~OpaqueHandleManager<NDXGI::SyncPacket>(void)
0x180086406  lea     rcx, [rdi+678h]
0x18008640d  call    ??1?$_Hash@V?$_Umap_traits@PEBVSmallRasterizerStateDesc@@PEAVCRasterizerState@@V?$_Uhash_compare@PEBVSmallRasterizerStateDesc@@V?$HashDeref@VSmallRasterizerStateDesc@@@@V?$EqualToDeref@VSmallRasterizerStateDesc@@@@@std@@V?$allocator@U?$pair@QEBVSmallRasterizerStateDesc@@PEAVCRasterizerState@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<SmallRasterizerStateDesc const *,CRasterizerState *,std::_Uhash_compare<SmallRasterizerStateDesc const *,HashDeref<SmallRasterizerStateDesc>,EqualToDeref<SmallRasterizerStateDesc>>,std::allocator<std::pair<SmallRasterizerStateDesc const * const,CRasterizerState *>>,0>>::~_Hash<std::_Umap_traits<SmallRasterizerStateDesc const *,CRasterizerState *,std::_Uhash_compare<SmallRasterizerStateDesc const *,HashDeref<SmallRasterizerStateDesc>,EqualToDeref<SmallRasterizerStateDesc>>,std::allocator<std::pair<SmallRasterizerStateDesc const * const,CRasterizerState *>>,0>>(void)
0x180086412  lea     rcx, [rdi+630h]
0x180086419  call    ??1?$_Hash@V?$_Umap_traits@KPEAUSCreateLayeredChildThreadLocalData@CDevice@NDXGI@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@V?$allocator@U?$pair@$$CBKPEAUSCreateLayeredChildThreadLocalData@CDevice@NDXGI@@@std@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<ulong,NDXGI::CDevice::SCreateLayeredChildThreadLocalData *,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,NDXGI::CDevice::SCreateLayeredChildThreadLocalData *>>,0>>::~_Hash<std::_Umap_traits<ulong,NDXGI::CDevice::SCreateLayeredChildThreadLocalData *,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,NDXGI::CDevice::SCreateLayeredChildThreadLocalData *>>,0>>(void)
0x18008641e  lea     rcx, [rdi+5E0h]
0x180086425  call    ??1?$_Hash@V?$_Umap_traits@PEBVSmallRasterizerStateDesc@@PEAVCRasterizerState@@V?$_Uhash_compare@PEBVSmallRasterizerStateDesc@@V?$HashDeref@VSmallRasterizerStateDesc@@@@V?$EqualToDeref@VSmallRasterizerStateDesc@@@@@std@@V?$allocator@U?$pair@QEBVSmallRasterizerStateDesc@@PEAVCRasterizerState@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<SmallRasterizerStateDesc const *,CRasterizerState *,std::_Uhash_compare<SmallRasterizerStateDesc const *,HashDeref<SmallRasterizerStateDesc>,EqualToDeref<SmallRasterizerStateDesc>>,std::allocator<std::pair<SmallRasterizerStateDesc const * const,CRasterizerState *>>,0>>::~_Hash<std::_Umap_traits<SmallRasterizerStateDesc const *,CRasterizerState *,std::_Uhash_compare<SmallRasterizerStateDesc const *,HashDeref<SmallRasterizerStateDesc>,EqualToDeref<SmallRasterizerStateDesc>>,std::allocator<std::pair<SmallRasterizerStateDesc const * const,CRasterizerState *>>,0>>(void)
0x18008642a  lea     rcx, [rdi+590h]
0x180086431  call    ??1?$_Hash@V?$_Umap_traits@PEBVSmallRasterizerStateDesc@@PEAVCRasterizerState@@V?$_Uhash_compare@PEBVSmallRasterizerStateDesc@@V?$HashDeref@VSmallRasterizerStateDesc@@@@V?$EqualToDeref@VSmallRasterizerStateDesc@@@@@std@@V?$allocator@U?$pair@QEBVSmallRasterizerStateDesc@@PEAVCRasterizerState@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<SmallRasterizerStateDesc const *,CRasterizerState *,std::_Uhash_compare<SmallRasterizerStateDesc const *,HashDeref<SmallRasterizerStateDesc>,EqualToDeref<SmallRasterizerStateDesc>>,std::allocator<std::pair<SmallRasterizerStateDesc const * const,CRasterizerState *>>,0>>::~_Hash<std::_Umap_traits<SmallRasterizerStateDesc const *,CRasterizerState *,std::_Uhash_compare<SmallRasterizerStateDesc const *,HashDeref<SmallRasterizerStateDesc>,EqualToDeref<SmallRasterizerStateDesc>>,std::allocator<std::pair<SmallRasterizerStateDesc const * const,CRasterizerState *>>,0>>(void)
0x180086436  lea     rcx, [rdi+540h]
0x18008643d  call    ??1?$_Hash@V?$_Umap_traits@PEBVSmallRasterizerStateDesc@@PEAVCRasterizerState@@V?$_Uhash_compare@PEBVSmallRasterizerStateDesc@@V?$HashDeref@VSmallRasterizerStateDesc@@@@V?$EqualToDeref@VSmallRasterizerStateDesc@@@@@std@@V?$allocator@U?$pair@QEBVSmallRasterizerStateDesc@@PEAVCRasterizerState@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<SmallRasterizerStateDesc const *,CRasterizerState *,std::_Uhash_compare<SmallRasterizerStateDesc const *,HashDeref<SmallRasterizerStateDesc>,EqualToDeref<SmallRasterizerStateDesc>>,std::allocator<std::pair<SmallRasterizerStateDesc const * const,CRasterizerState *>>,0>>::~_Hash<std::_Umap_traits<SmallRasterizerStateDesc const *,CRasterizerState *,std::_Uhash_compare<SmallRasterizerStateDesc const *,HashDeref<SmallRasterizerStateDesc>,EqualToDeref<SmallRasterizerStateDesc>>,std::allocator<std::pair<SmallRasterizerStateDesc const * const,CRasterizerState *>>,0>>(void)
0x180086442  lea     rcx, [rdi+510h]; lpCriticalSection
0x180086449  call    cs:__imp_DeleteCriticalSection
0x18008644f  lea     rcx, [rdi+4F8h]
0x180086456  call    ?_Tidy@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::vector<void *>::_Tidy(void)
0x18008645b  mov     rcx, [rdi+4E8h]
0x180086462  mov     rax, [rcx+8]
0x180086466  mov     qword ptr [rax], 0
0x18008646d  mov     rcx, [rcx]
0x180086470  test    rcx, rcx
0x180086473  jz      short loc_18008648A
0x180086475  mov     rbx, [rcx]
0x180086478  mov     edx, 18h
0x18008647d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180086482  mov     rcx, rbx
0x180086485  test    rbx, rbx
0x180086488  jnz     short loc_180086475
0x18008648a  mov     rcx, [rdi+4E8h]
0x180086491  mov     edx, 18h
0x180086496  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18008649b  mov     rcx, [rdi+4C8h]
0x1800864a2  test    rcx, rcx
0x1800864a5  jz      short loc_1800864DB
0x1800864a7  mov     rdx, [rdi+4D8h]
0x1800864ae  sub     rdx, rcx
0x1800864b1  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1800864b5  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800864ba  mov     qword ptr [rdi+4C8h], 0
0x1800864c5  mov     qword ptr [rdi+4D0h], 0
0x1800864d0  mov     qword ptr [rdi+4D8h], 0
0x1800864db  mov     rcx, [rdi+4B0h]
0x1800864e2  test    rcx, rcx
0x1800864e5  jz      short loc_18008651B
0x1800864e7  mov     rdx, [rdi+4C0h]
0x1800864ee  sub     rdx, rcx
0x1800864f1  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1800864f5  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800864fa  mov     qword ptr [rdi+4B0h], 0
0x180086505  mov     qword ptr [rdi+4B8h], 0
0x180086510  mov     qword ptr [rdi+4C0h], 0
0x18008651b  lea     rcx, [rdi+488h]
0x180086522  call    ?_Tidy@?$vector@IV?$allocator@I@std@@@std@@AEAAXXZ; std::vector<uint>::_Tidy(void)
0x180086527  lea     rcx, [rdi+460h]; lpCriticalSection
0x18008652e  call    cs:__imp_DeleteCriticalSection
0x180086534  lea     rcx, [rdi+448h]
0x18008653b  call    ?_Tidy@?$vector@IV?$allocator@I@std@@@std@@AEAAXXZ; std::vector<uint>::_Tidy(void)
0x180086540  lea     rcx, [rdi+420h]; lpCriticalSection
0x180086547  call    cs:__imp_DeleteCriticalSection
0x18008654d  mov     rcx, [rdi+410h]
0x180086554  mov     rax, [rcx+8]
0x180086558  mov     qword ptr [rax], 0
0x18008655f  mov     rdx, [rcx]
0x180086562  test    rdx, rdx
0x180086565  jz      short loc_180086577
0x180086567  mov     rbx, [rdx]
0x18008656a  call    ??$_Freenode@V?$allocator@U?$_List_node@VCContext@NDXGI@@PEAX@std@@@std@@@?$_List_node@VCContext@NDXGI@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@VCContext@NDXGI@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<NDXGI::CContext,void *>::_Freenode<std::allocator<std::_List_node<NDXGI::CContext,void *>>>(std::allocator<std::_List_node<NDXGI::CContext,void *>> &,std::_List_node<NDXGI::CContext,void *> *)
0x18008656f  mov     rdx, rbx
0x180086572  test    rbx, rbx
0x180086575  jnz     short loc_180086567
0x180086577  mov     rcx, [rdi+410h]
0x18008657e  mov     edx, 88h
0x180086583  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180086588  lea     rcx, [rdi+38h]
0x18008658c  mov     rbx, [rsp+28h+arg_0]
0x180086591  add     rsp, 20h
0x180086595  pop     rdi
0x180086596  jmp     ??1?$CComPtrBase@UIDXGIFactory4@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(void)
```
