# NetworkDiagnosticsEngine::~NetworkDiagnosticsEngine(void)

- ea: `0x180018088`
- end: `0x180018176`
- name: `??1NetworkDiagnosticsEngine@@QEAA@XZ`
- size: `238`
- prototype: `void __fastcall(NetworkDiagnosticsEngine *this, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180004860`

## callees

- `0x180004178`
- `0x180005048`
- `0x180008c84`
- `0x180009a74`
- `0x1800100a8`
- `0x180017cf0`
- `0x180017eac`
- `0x180017ed8`
- `0x180018088`
- `0x18002f010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001810e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180018128`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001810e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180018128`
- `KERNEL32!DeleteCriticalSection` at `0x18001814b`
- `KERNEL32!DeleteCriticalSection` at `0x18001814b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall NetworkDiagnosticsEngine::~NetworkDiagnosticsEngine(
        NetworkDiagnosticsEngine *this,
        __int64 a2,
        __int64 a3)
{
  _QWORD *v4; // r14
  __int64 v5; // rbx
  NetworkIncident *v6; // rsi
  unsigned int v7; // edx
  __int64 v8; // rcx
  __int64 i; // rax
  void *v10; // rbx
  void *v11; // rbx
  void (__fastcall ***v12)(_QWORD, __int64); // rcx

  v4 = (_QWORD *)((char *)this + 8);
  v5 = **((_QWORD **)this + 1);
  while ( v5 != *v4 )
  {
    v6 = *(NetworkIncident **)(v5 + 48);
    if ( v6 )
    {
      NetworkIncident::Cancel(*(NetworkIncident **)(v5 + 48));
      NetworkIncident::`scalar deleting destructor'(v6, v7);
    }
    if ( !*(_BYTE *)(v5 + 25) )
    {
      v8 = *(_QWORD *)(v5 + 16);
      if ( *(_BYTE *)(v8 + 25) )
      {
        for ( i = *(_QWORD *)(v5 + 8); !*(_BYTE *)(i + 25) && v5 == *(_QWORD *)(i + 16); i = *(_QWORD *)(i + 8) )
          v5 = i;
      }
      else
      {
        i = std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,CExtensionHelperInfoContainer *>>>::_Min(
              v8,
              a2,
              a3);
      }
      v5 = i;
    }
  }
  std::_Tree<std::_Tmap_traits<_GUID,NetworkIncident *,std::less<_GUID>,std::allocator<std::pair<_GUID const,NetworkIncident *>>,0>>::clear(v4);
  v10 = (void *)*((_QWORD *)this + 5);
  if ( v10 )
  {
    CHelperMetaDataStore::~CHelperMetaDataStore(*((CHelperMetaDataStore **)this + 5));
    operator delete(v10);
  }
  v11 = (void *)*((_QWORD *)this + 6);
  if ( v11 )
  {
    CProblemInstanceCache::~CProblemInstanceCache(*((CProblemInstanceCache **)this + 6));
    operator delete(v11);
  }
  v12 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 4);
  if ( v12 )
    (**v12)(v12, 1);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  NetworkDiagnosticsEngine::m_engine = 0;
  ATL::CComPtrBase<INDFHelperClass>::~CComPtrBase<INDFHelperClass>((__int64 *)this + 3);
  std::_Tree<std::_Tmap_traits<_GUID,NetworkIncident *,std::less<_GUID>,std::allocator<std::pair<_GUID const,NetworkIncident *>>,0>>::~_Tree<std::_Tmap_traits<_GUID,NetworkIncident *,std::less<_GUID>,std::allocator<std::pair<_GUID const,NetworkIncident *>>,0>>(v4);
}

```

## disassembly

```asm
0x180018088  push    rbx
0x18001808a  push    rsi
0x18001808b  push    rdi
0x18001808c  push    r14
0x18001808e  sub     rsp, 28h
0x180018092  mov     rdi, rcx
0x180018095  lea     r14, [rcx+8]
0x180018099  mov     rbx, [r14]
0x18001809c  mov     rbx, [rbx]
0x18001809f  cmp     rbx, [r14]
0x1800180a2  jz      short loc_1800180F2
0x1800180a4  mov     rsi, [rbx+30h]
0x1800180a8  test    rsi, rsi
0x1800180ab  jz      short loc_1800180BD
0x1800180ad  mov     rcx, rsi; this
0x1800180b0  call    ?Cancel@NetworkIncident@@QEAAXXZ; NetworkIncident::Cancel(void)
0x1800180b5  mov     rcx, rsi; this
0x1800180b8  call    ??_GNetworkIncident@@QEAAPEAXI@Z; NetworkIncident::`scalar deleting destructor'(uint)
0x1800180bd  cmp     byte ptr [rbx+19h], 0
0x1800180c1  jnz     short loc_18001809F
0x1800180c3  mov     rcx, [rbx+10h]
0x1800180c7  cmp     byte ptr [rcx+19h], 0
0x1800180cb  jnz     short loc_1800180D4
0x1800180cd  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCExtensionHelperInfoContainer@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCExtensionHelperInfoContainer@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,CExtensionHelperInfoContainer *>>>::_Min(std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,CExtensionHelperInfoContainer *>,void *> *)
0x1800180d2  jmp     short loc_1800180ED
0x1800180d4  mov     rax, [rbx+8]
0x1800180d8  jmp     short loc_1800180E7
0x1800180da  cmp     rbx, [rax+10h]
0x1800180de  jnz     short loc_1800180ED
0x1800180e0  mov     rbx, rax
0x1800180e3  mov     rax, [rax+8]
0x1800180e7  cmp     byte ptr [rax+19h], 0
0x1800180eb  jz      short loc_1800180DA
0x1800180ed  mov     rbx, rax
0x1800180f0  jmp     short loc_18001809F
0x1800180f2  mov     rcx, r14
0x1800180f5  call    ?clear@?$_Tree@V?$_Tmap_traits@U_GUID@@PEAVNetworkIncident@@U?$less@U_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVNetworkIncident@@@std@@@4@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<_GUID,NetworkIncident *,std::less<_GUID>,std::allocator<std::pair<_GUID const,NetworkIncident *>>,0>>::clear(void)
0x1800180fa  mov     rbx, [rdi+28h]
0x1800180fe  test    rbx, rbx
0x180018101  jz      short loc_180018114
0x180018103  mov     rcx, rbx; this
0x180018106  call    ??1CHelperMetaDataStore@@QEAA@XZ; CHelperMetaDataStore::~CHelperMetaDataStore(void)
0x18001810b  mov     rcx, rbx
0x18001810e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180018114  mov     rbx, [rdi+30h]
0x180018118  test    rbx, rbx
0x18001811b  jz      short loc_18001812E
0x18001811d  mov     rcx, rbx; this
0x180018120  call    ??1CProblemInstanceCache@@QEAA@XZ; CProblemInstanceCache::~CProblemInstanceCache(void)
0x180018125  mov     rcx, rbx
0x180018128  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001812e  mov     rcx, [rdi+20h]
0x180018132  test    rcx, rcx
0x180018135  jz      short loc_180018147
0x180018137  mov     rax, [rcx]
0x18001813a  mov     edx, 1
0x18001813f  mov     rax, [rax]
0x180018142  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018147  lea     rcx, [rdi+40h]; lpCriticalSection
0x18001814b  call    cs:__imp_DeleteCriticalSection
0x180018151  mov     cs:?m_engine@NetworkDiagnosticsEngine@@0PEAV1@EA, 0; NetworkDiagnosticsEngine * NetworkDiagnosticsEngine::m_engine
0x18001815c  lea     rcx, [rdi+18h]
0x180018160  call    ??1?$CComPtrBase@UINDFHelperClass@@@ATL@@QEAA@XZ; ATL::CComPtrBase<INDFHelperClass>::~CComPtrBase<INDFHelperClass>(void)
0x180018165  mov     rcx, r14
0x180018168  add     rsp, 28h
0x18001816c  pop     r14
0x18001816e  pop     rdi
0x18001816f  pop     rsi
0x180018170  pop     rbx
0x180018171  jmp     ??1?$_Tree@V?$_Tmap_traits@U_GUID@@PEAVNetworkIncident@@U?$less@U_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVNetworkIncident@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<_GUID,NetworkIncident *,std::less<_GUID>,std::allocator<std::pair<_GUID const,NetworkIncident *>>,0>>::~_Tree<std::_Tmap_traits<_GUID,NetworkIncident *,std::less<_GUID>,std::allocator<std::pair<_GUID const,NetworkIncident *>>,0>>(void)
```
