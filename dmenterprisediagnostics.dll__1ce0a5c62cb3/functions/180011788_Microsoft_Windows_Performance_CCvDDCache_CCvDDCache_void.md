# Microsoft::Windows::Performance::CCvDDCache::~CCvDDCache(void)

- ea: `0x180011788`
- end: `0x180011808`
- name: `??1CCvDDCache@Performance@Windows@Microsoft@@QEAA@XZ`
- size: `128`
- prototype: `void __fastcall(void **this)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001182c`
- `0x180024f87`

## callees

- `0x1800035c4`
- `0x18001159c`
- `0x1800115cc`
- `0x1800115fc`
- `0x180011724`
- `0x180011788`

## pseudocode

```c
void __fastcall Microsoft::Windows::Performance::CCvDDCache::~CCvDDCache(void **this)
{
  void **v2; // rdx
  void **v3; // rsi
  void **v4; // rbx

  std::_Tree<std::_Tset_traits<unsigned short const *,std::less<unsigned short const *>,std::allocator<unsigned short const *>,0>>::~_Tree<std::_Tset_traits<unsigned short const *,std::less<unsigned short const *>,std::allocator<unsigned short const *>,0>>(this + 6);
  std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::~_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>(this + 4);
  std::_Tree<std::_Tmap_traits<unsigned long,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>,0>>::~_Tree<std::_Tmap_traits<unsigned long,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>,0>>(this + 2);
  v2 = (void **)*this;
  **((_QWORD **)*this + 1) = 0;
  v3 = (void **)*v2;
  if ( *v2 )
  {
    do
    {
      v4 = (void **)*v3;
      Microsoft::Windows::Performance::CCvDDCache::CCvDD::~CCvDD(v3 + 2);
      std::_Deallocate<16>(v3, 0xA0u);
      v3 = v4;
    }
    while ( v4 );
  }
  std::_Deallocate<16>(*this, 0xA0u);
}

```

## disassembly

```asm
0x180011788  mov     [rsp+arg_0], rbx
0x18001178d  mov     [rsp+arg_8], rsi
0x180011792  push    rdi
0x180011793  sub     rsp, 20h
0x180011797  mov     rdi, rcx
0x18001179a  add     rcx, 30h ; '0'
0x18001179e  call    ??1?$_Tree@V?$_Tset_traits@PEBGU?$less@PEBG@std@@V?$allocator@PEBG@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<ushort const *,std::less<ushort const *>,std::allocator<ushort const *>,0>>::~_Tree<std::_Tset_traits<ushort const *,std::less<ushort const *>,std::allocator<ushort const *>,0>>(void)
0x1800117a3  lea     rcx, [rdi+20h]
0x1800117a7  call    ??1?$_Tree@V?$_Tmap_traits@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::~_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>(void)
0x1800117ac  lea     rcx, [rdi+10h]
0x1800117b0  call    ??1?$_Tree@V?$_Tmap_traits@KV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>,std::less<ulong>,std::allocator<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>,0>>::~_Tree<std::_Tmap_traits<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>,std::less<ulong>,std::allocator<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>,0>>(void)
0x1800117b5  mov     rdx, [rdi]
0x1800117b8  mov     rax, [rdx+8]
0x1800117bc  mov     qword ptr [rax], 0
0x1800117c3  mov     rsi, [rdx]
0x1800117c6  test    rsi, rsi
0x1800117c9  jz      short loc_1800117EC
0x1800117cb  mov     rbx, [rsi]
0x1800117ce  lea     rcx, [rsi+10h]; this
0x1800117d2  call    ??1CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CCvDDCache::CCvDD::~CCvDD(void)
0x1800117d7  mov     edx, 0A0h
0x1800117dc  mov     rcx, rsi
0x1800117df  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800117e4  mov     rsi, rbx
0x1800117e7  test    rbx, rbx
0x1800117ea  jnz     short loc_1800117CB
0x1800117ec  mov     rcx, [rdi]
0x1800117ef  mov     edx, 0A0h
0x1800117f4  mov     rbx, [rsp+28h+arg_0]
0x1800117f9  mov     rsi, [rsp+28h+arg_8]
0x1800117fe  add     rsp, 20h
0x180011802  pop     rdi
0x180011803  jmp     ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
```
