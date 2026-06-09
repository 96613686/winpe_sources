# PublicNetworkListManager::~PublicNetworkListManager(void)

- ea: `0x180015dc4`
- end: `0x180015eba`
- name: `??1PublicNetworkListManager@@QEAA@XZ`
- size: `246`
- prototype: `void __fastcall(PublicNetworkListManager *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180015760`
- `0x18001587c`

## callees

- `0x180006b50`
- `0x1800076f0`
- `0x180008020`
- `0x180009d98`
- `0x18000c650`
- `0x18001596c`
- `0x180015dc4`

## import_xrefs

- `api-ms-win-service-private-l1-1-0!UnsubscribeServiceChangeNotifications` at `0x180015e71`
- `api-ms-win-service-private-l1-1-0!UnsubscribeServiceChangeNotifications` at `0x180015e71`

## pseudocode

```c
void __fastcall PublicNetworkListManager::~PublicNetworkListManager(PublicNetworkListManager *this)
{
  _QWORD **v2; // rdx
  _QWORD *v3; // rcx
  _QWORD *v4; // rbx

  CLIENT_DEST_EVENT_MGR::~CLIENT_DEST_EVENT_MGR((PublicNetworkListManager *)((char *)this + 704));
  v2 = (_QWORD **)*((_QWORD *)this + 75);
  *v2[1] = 0;
  v3 = *v2;
  if ( *v2 )
  {
    do
    {
      v4 = (_QWORD *)*v3;
      std::_Deallocate<16>(v3, 0x18u);
      v3 = v4;
    }
    while ( v4 );
  }
  std::_Deallocate<16>(*((void **)this + 75), 0x18u);
  std::_Tree<std::_Tmap_traits<unsigned long,CLIENT_CALLBACK_INTERFACE,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,CLIENT_CALLBACK_INTERFACE>>,0>>::~_Tree<std::_Tmap_traits<unsigned long,CLIENT_CALLBACK_INTERFACE,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,CLIENT_CALLBACK_INTERFACE>>,0>>((char *)this + 544);
  std::_Tree<std::_Tmap_traits<unsigned long,CLIENT_CALLBACK_INTERFACE,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,CLIENT_CALLBACK_INTERFACE>>,0>>::~_Tree<std::_Tmap_traits<unsigned long,CLIENT_CALLBACK_INTERFACE,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,CLIENT_CALLBACK_INTERFACE>>,0>>((char *)this + 488);
  std::_Tree<std::_Tmap_traits<unsigned long,CLIENT_CALLBACK_INTERFACE,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,CLIENT_CALLBACK_INTERFACE>>,0>>::~_Tree<std::_Tmap_traits<unsigned long,CLIENT_CALLBACK_INTERFACE,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,CLIENT_CALLBACK_INTERFACE>>,0>>((char *)this + 432);
  std::_Tree<std::_Tmap_traits<unsigned long,CLIENT_CALLBACK_INTERFACE,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,CLIENT_CALLBACK_INTERFACE>>,0>>::~_Tree<std::_Tmap_traits<unsigned long,CLIENT_CALLBACK_INTERFACE,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,CLIENT_CALLBACK_INTERFACE>>,0>>((char *)this + 376);
  std::_Tree<std::_Tmap_traits<unsigned long,CLIENT_CALLBACK_INTERFACE,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,CLIENT_CALLBACK_INTERFACE>>,0>>::~_Tree<std::_Tmap_traits<unsigned long,CLIENT_CALLBACK_INTERFACE,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,CLIENT_CALLBACK_INTERFACE>>,0>>((char *)this + 320);
  ATL::CComPtrBase<IGlobalInterfaceTable>::~CComPtrBase<IGlobalInterfaceTable>((__int64 *)this + 28);
  if ( *((_QWORD *)this + 25) )
    UnsubscribeServiceChangeNotifications();
  ATL::IConnectionPointImpl<PublicNetworkListManager,&_GUID const IID_INetworkConnectionEvents,ATL::CComDynamicUnkArray>::~IConnectionPointImpl<PublicNetworkListManager,&_GUID const IID_INetworkConnectionEvents,ATL::CComDynamicUnkArray>((__int64)this + 104);
  ATL::IConnectionPointImpl<PublicNetworkListManager,&_GUID const IID_INetworkConnectionEvents,ATL::CComDynamicUnkArray>::~IConnectionPointImpl<PublicNetworkListManager,&_GUID const IID_INetworkConnectionEvents,ATL::CComDynamicUnkArray>((__int64)this + 80);
  ATL::IConnectionPointImpl<PublicNetworkListManager,&_GUID const IID_INetworkConnectionEvents,ATL::CComDynamicUnkArray>::~IConnectionPointImpl<PublicNetworkListManager,&_GUID const IID_INetworkConnectionEvents,ATL::CComDynamicUnkArray>((__int64)this + 56);
  ATL::IConnectionPointImpl<PublicNetworkListManager,&_GUID const IID_INetworkConnectionEvents,ATL::CComDynamicUnkArray>::~IConnectionPointImpl<PublicNetworkListManager,&_GUID const IID_INetworkConnectionEvents,ATL::CComDynamicUnkArray>((__int64)this + 32);
  ATL::IConnectionPointImpl<PublicNetworkListManager,&_GUID const IID_INetworkConnectionEvents,ATL::CComDynamicUnkArray>::~IConnectionPointImpl<PublicNetworkListManager,&_GUID const IID_INetworkConnectionEvents,ATL::CComDynamicUnkArray>((__int64)this + 8);
  ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>((__int64)this + 144);
}

```

## disassembly

```asm
0x180015dc4  mov     [rsp+arg_0], rbx
0x180015dc9  push    rdi
0x180015dca  sub     rsp, 20h
0x180015dce  mov     rdi, rcx
0x180015dd1  add     rcx, 2C0h; this
0x180015dd8  call    ??1CLIENT_DEST_EVENT_MGR@@QEAA@XZ; CLIENT_DEST_EVENT_MGR::~CLIENT_DEST_EVENT_MGR(void)
0x180015ddd  mov     rdx, [rdi+258h]
0x180015de4  mov     rax, [rdx+8]
0x180015de8  mov     qword ptr [rax], 0
0x180015def  mov     rcx, [rdx]
0x180015df2  test    rcx, rcx
0x180015df5  jz      short loc_180015E0C
0x180015df7  mov     rbx, [rcx]
0x180015dfa  mov     edx, 18h
0x180015dff  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180015e04  mov     rcx, rbx
0x180015e07  test    rbx, rbx
0x180015e0a  jnz     short loc_180015DF7
0x180015e0c  mov     rcx, [rdi+258h]
0x180015e13  mov     edx, 18h
0x180015e18  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180015e1d  lea     rcx, [rdi+220h]
0x180015e24  call    ??1?$_Tree@V?$_Tmap_traits@KUCLIENT_CALLBACK_INTERFACE@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKUCLIENT_CALLBACK_INTERFACE@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ulong,CLIENT_CALLBACK_INTERFACE,std::less<ulong>,std::allocator<std::pair<ulong const,CLIENT_CALLBACK_INTERFACE>>,0>>::~_Tree<std::_Tmap_traits<ulong,CLIENT_CALLBACK_INTERFACE,std::less<ulong>,std::allocator<std::pair<ulong const,CLIENT_CALLBACK_INTERFACE>>,0>>(void)
0x180015e29  lea     rcx, [rdi+1E8h]
0x180015e30  call    ??1?$_Tree@V?$_Tmap_traits@KUCLIENT_CALLBACK_INTERFACE@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKUCLIENT_CALLBACK_INTERFACE@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ulong,CLIENT_CALLBACK_INTERFACE,std::less<ulong>,std::allocator<std::pair<ulong const,CLIENT_CALLBACK_INTERFACE>>,0>>::~_Tree<std::_Tmap_traits<ulong,CLIENT_CALLBACK_INTERFACE,std::less<ulong>,std::allocator<std::pair<ulong const,CLIENT_CALLBACK_INTERFACE>>,0>>(void)
0x180015e35  lea     rcx, [rdi+1B0h]
0x180015e3c  call    ??1?$_Tree@V?$_Tmap_traits@KUCLIENT_CALLBACK_INTERFACE@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKUCLIENT_CALLBACK_INTERFACE@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ulong,CLIENT_CALLBACK_INTERFACE,std::less<ulong>,std::allocator<std::pair<ulong const,CLIENT_CALLBACK_INTERFACE>>,0>>::~_Tree<std::_Tmap_traits<ulong,CLIENT_CALLBACK_INTERFACE,std::less<ulong>,std::allocator<std::pair<ulong const,CLIENT_CALLBACK_INTERFACE>>,0>>(void)
0x180015e41  lea     rcx, [rdi+178h]
0x180015e48  call    ??1?$_Tree@V?$_Tmap_traits@KUCLIENT_CALLBACK_INTERFACE@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKUCLIENT_CALLBACK_INTERFACE@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ulong,CLIENT_CALLBACK_INTERFACE,std::less<ulong>,std::allocator<std::pair<ulong const,CLIENT_CALLBACK_INTERFACE>>,0>>::~_Tree<std::_Tmap_traits<ulong,CLIENT_CALLBACK_INTERFACE,std::less<ulong>,std::allocator<std::pair<ulong const,CLIENT_CALLBACK_INTERFACE>>,0>>(void)
0x180015e4d  lea     rcx, [rdi+140h]
0x180015e54  call    ??1?$_Tree@V?$_Tmap_traits@KUCLIENT_CALLBACK_INTERFACE@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKUCLIENT_CALLBACK_INTERFACE@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ulong,CLIENT_CALLBACK_INTERFACE,std::less<ulong>,std::allocator<std::pair<ulong const,CLIENT_CALLBACK_INTERFACE>>,0>>::~_Tree<std::_Tmap_traits<ulong,CLIENT_CALLBACK_INTERFACE,std::less<ulong>,std::allocator<std::pair<ulong const,CLIENT_CALLBACK_INTERFACE>>,0>>(void)
0x180015e59  lea     rcx, [rdi+0E0h]
0x180015e60  call    ??1?$CComPtrBase@UIGlobalInterfaceTable@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IGlobalInterfaceTable>::~CComPtrBase<IGlobalInterfaceTable>(void)
0x180015e65  mov     rcx, [rdi+0C8h]
0x180015e6c  test    rcx, rcx
0x180015e6f  jz      short loc_180015E77
0x180015e71  call    cs:__imp_UnsubscribeServiceChangeNotifications
0x180015e77  lea     rcx, [rdi+68h]
0x180015e7b  call    ??1?$IConnectionPointImpl@VPublicNetworkListManager@@$1?IID_INetworkConnectionEvents@@3U_GUID@@BVCComDynamicUnkArray@ATL@@@ATL@@QEAA@XZ; ATL::IConnectionPointImpl<PublicNetworkListManager,&_GUID const IID_INetworkConnectionEvents,ATL::CComDynamicUnkArray>::~IConnectionPointImpl<PublicNetworkListManager,&_GUID const IID_INetworkConnectionEvents,ATL::CComDynamicUnkArray>(void)
0x180015e80  lea     rcx, [rdi+50h]
0x180015e84  call    ??1?$IConnectionPointImpl@VPublicNetworkListManager@@$1?IID_INetworkConnectionEvents@@3U_GUID@@BVCComDynamicUnkArray@ATL@@@ATL@@QEAA@XZ; ATL::IConnectionPointImpl<PublicNetworkListManager,&_GUID const IID_INetworkConnectionEvents,ATL::CComDynamicUnkArray>::~IConnectionPointImpl<PublicNetworkListManager,&_GUID const IID_INetworkConnectionEvents,ATL::CComDynamicUnkArray>(void)
0x180015e89  lea     rcx, [rdi+38h]
0x180015e8d  call    ??1?$IConnectionPointImpl@VPublicNetworkListManager@@$1?IID_INetworkConnectionEvents@@3U_GUID@@BVCComDynamicUnkArray@ATL@@@ATL@@QEAA@XZ; ATL::IConnectionPointImpl<PublicNetworkListManager,&_GUID const IID_INetworkConnectionEvents,ATL::CComDynamicUnkArray>::~IConnectionPointImpl<PublicNetworkListManager,&_GUID const IID_INetworkConnectionEvents,ATL::CComDynamicUnkArray>(void)
0x180015e92  lea     rcx, [rdi+20h]
0x180015e96  call    ??1?$IConnectionPointImpl@VPublicNetworkListManager@@$1?IID_INetworkConnectionEvents@@3U_GUID@@BVCComDynamicUnkArray@ATL@@@ATL@@QEAA@XZ; ATL::IConnectionPointImpl<PublicNetworkListManager,&_GUID const IID_INetworkConnectionEvents,ATL::CComDynamicUnkArray>::~IConnectionPointImpl<PublicNetworkListManager,&_GUID const IID_INetworkConnectionEvents,ATL::CComDynamicUnkArray>(void)
0x180015e9b  lea     rcx, [rdi+8]
0x180015e9f  call    ??1?$IConnectionPointImpl@VPublicNetworkListManager@@$1?IID_INetworkConnectionEvents@@3U_GUID@@BVCComDynamicUnkArray@ATL@@@ATL@@QEAA@XZ; ATL::IConnectionPointImpl<PublicNetworkListManager,&_GUID const IID_INetworkConnectionEvents,ATL::CComDynamicUnkArray>::~IConnectionPointImpl<PublicNetworkListManager,&_GUID const IID_INetworkConnectionEvents,ATL::CComDynamicUnkArray>(void)
0x180015ea4  lea     rcx, [rdi+90h]
0x180015eab  mov     rbx, [rsp+28h+arg_0]
0x180015eb0  add     rsp, 20h
0x180015eb4  pop     rdi
0x180015eb5  jmp     ??1?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(void)
```
