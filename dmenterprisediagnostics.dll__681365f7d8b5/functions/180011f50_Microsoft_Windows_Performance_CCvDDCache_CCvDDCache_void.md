# Microsoft::Windows::Performance::CCvDDCache::~CCvDDCache(void)

- ea: `0x180011f50`
- end: `0x180011fd0`
- name: `??1CCvDDCache@Performance@Windows@Microsoft@@QEAA@XZ`
- size: `128`
- prototype: `void __fastcall(Microsoft::Windows::Performance::CCvDDCache *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180011ff4`
- `0x180025e5b`

## callees

- `0x180003618`
- `0x180011d5c`
- `0x180011d8c`
- `0x180011dbc`
- `0x180011eec`
- `0x180011f50`

## pseudocode

```c
void __fastcall Microsoft::Windows::Performance::CCvDDCache::~CCvDDCache(void ****this)
{
  void ***v2; // rdx
  void **v3; // rsi
  void **v4; // rbx

  std::_Tree<std::_Tset_traits<unsigned short const *,std::less<unsigned short const *>,std::allocator<unsigned short const *>,0>>::~_Tree<std::_Tset_traits<unsigned short const *,std::less<unsigned short const *>,std::allocator<unsigned short const *>,0>>(this + 6);
  std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::~_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>(this + 4);
  std::_Tree<std::_Tmap_traits<unsigned long,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>,0>>::~_Tree<std::_Tmap_traits<unsigned long,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>,0>>(this + 2);
  v2 = *this;
  *(*this)[1] = 0;
  v3 = *v2;
  if ( *v2 )
  {
    do
    {
      v4 = (void **)*v3;
      Microsoft::Windows::Performance::CCvDDCache::CCvDD::~CCvDD(v3 + 2);
      std::_Deallocate<16>(v3, 160);
      v3 = v4;
    }
    while ( v4 );
  }
  std::_Deallocate<16>(*this, 160);
}

```

## disassembly

```asm
0x180011f50  mov     [rsp+arg_0], rbx
0x180011f55  mov     [rsp+arg_8], rsi
0x180011f5a  push    rdi
0x180011f5b  sub     rsp, 20h
0x180011f5f  mov     rdi, rcx
0x180011f62  add     rcx, 30h ; '0'
0x180011f66  call    ??1?$_Tree@V?$_Tset_traits@PEBGU?$less@PEBG@std@@V?$allocator@PEBG@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<ushort const *,std::less<ushort const *>,std::allocator<ushort const *>,0>>::~_Tree<std::_Tset_traits<ushort const *,std::less<ushort const *>,std::allocator<ushort const *>,0>>(void)
0x180011f6b  lea     rcx, [rdi+20h]
0x180011f6f  call    ??1?$_Tree@V?$_Tmap_traits@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::~_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>(void)
0x180011f74  lea     rcx, [rdi+10h]
0x180011f78  call    ??1?$_Tree@V?$_Tmap_traits@KV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>,std::less<ulong>,std::allocator<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>,0>>::~_Tree<std::_Tmap_traits<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>,std::less<ulong>,std::allocator<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>,0>>(void)
0x180011f7d  mov     rdx, [rdi]
0x180011f80  mov     rax, [rdx+8]
0x180011f84  mov     qword ptr [rax], 0
0x180011f8b  mov     rsi, [rdx]
0x180011f8e  test    rsi, rsi
0x180011f91  jz      short loc_180011FB4
0x180011f93  mov     rbx, [rsi]
0x180011f96  lea     rcx, [rsi+10h]; this
0x180011f9a  call    ??1CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CCvDDCache::CCvDD::~CCvDD(void)
0x180011f9f  mov     edx, 0A0h
0x180011fa4  mov     rcx, rsi
0x180011fa7  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180011fac  mov     rsi, rbx
0x180011faf  test    rbx, rbx
0x180011fb2  jnz     short loc_180011F93
0x180011fb4  mov     rcx, [rdi]
0x180011fb7  mov     edx, 0A0h
0x180011fbc  mov     rbx, [rsp+28h+arg_0]
0x180011fc1  mov     rsi, [rsp+28h+arg_8]
0x180011fc6  add     rsp, 20h
0x180011fca  pop     rdi
0x180011fcb  jmp     ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
```
