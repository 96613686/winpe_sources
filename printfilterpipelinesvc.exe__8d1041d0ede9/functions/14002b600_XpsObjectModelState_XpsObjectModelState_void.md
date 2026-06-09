# XpsObjectModelState::~XpsObjectModelState(void)

- ea: `0x14002b600`
- end: `0x14002b697`
- name: `??1XpsObjectModelState@@UEAA@XZ`
- size: `151`
- prototype: `void __fastcall(XpsObjectModelState *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14002be70`

## callees

- `0x14000fa68`
- `0x14002abf4`
- `0x14002acb0`
- `0x14002ace0`
- `0x14002ad10`
- `0x14002b600`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14002b66e`
- `KERNEL32!DeleteCriticalSection` at `0x14002b66e`

## pseudocode

```c
void __fastcall XpsObjectModelState::~XpsObjectModelState(XpsObjectModelState *this)
{
  *(_QWORD *)this = &XpsObjectModelState::`vftable'{for `NCOMLibrary::TUnknown'};
  *((_QWORD *)this + 2) = &XpsObjectModelState::`vftable'{for `IShutdownComponent'};
  std::_Tree<std::_Tset_traits<win_dox::OpcPartUri,std::less<win_dox::OpcPartUri>,std::allocator<win_dox::OpcPartUri>,0>>::~_Tree<std::_Tset_traits<win_dox::OpcPartUri,std::less<win_dox::OpcPartUri>,std::allocator<win_dox::OpcPartUri>,0>>((void **)this + 34);
  std::_Tree<std::_Tmap_traits<win_dox::OpcPartUri const,win_dox::OpcPartUri const,std::less<win_dox::OpcPartUri const>,std::allocator<std::pair<win_dox::OpcPartUri const,win_dox::OpcPartUri const>>,1>>::~_Tree<std::_Tmap_traits<win_dox::OpcPartUri const,win_dox::OpcPartUri const,std::less<win_dox::OpcPartUri const>,std::allocator<std::pair<win_dox::OpcPartUri const,win_dox::OpcPartUri const>>,1>>((void **)this + 31);
  PrnExcept::SmartRelease<IPartResourceDictionary>((__int64 *)this + 28);
  PrnExcept::SmartRelease<IPartResourceDictionary>((__int64 *)this + 27);
  WaitingLockedQueue<IUnknown>::~WaitingLockedQueue<IUnknown>((LPCRITICAL_SECTION)((char *)this + 96));
  std::_Tree<std::_Tmap_traits<win_dox::OpcPartUri,PartMapItem,std::less<win_dox::OpcPartUri>,std::allocator<std::pair<win_dox::OpcPartUri const,PartMapItem>>,0>>::~_Tree<std::_Tmap_traits<win_dox::OpcPartUri,PartMapItem,std::less<win_dox::OpcPartUri>,std::allocator<std::pair<win_dox::OpcPartUri const,PartMapItem>>,0>>((void **)this + 10);
  if ( *((int *)this + 18) >= 0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    *((_DWORD *)this + 18) = -2147467259;
  }
  *(_QWORD *)this = &NCOMLibrary::TUnknown::`vftable';
  _InterlockedDecrement(&NCOMLibrary::TUnknown::g_cOutStandingObjectCount);
}

```

## disassembly

```asm
0x14002b600  mov     [rsp+arg_0], rbx
0x14002b605  push    rdi
0x14002b606  sub     rsp, 20h
0x14002b60a  lea     rax, ??_7XpsObjectModelState@@6BTUnknown@NCOMLibrary@@@; const XpsObjectModelState::`vftable'{for `NCOMLibrary::TUnknown'}
0x14002b611  mov     rbx, rcx
0x14002b614  mov     [rcx], rax
0x14002b617  lea     rax, ??_7XpsObjectModelState@@6BIShutdownComponent@@@; const XpsObjectModelState::`vftable'{for `IShutdownComponent'}
0x14002b61e  mov     [rcx+10h], rax
0x14002b622  add     rcx, 110h
0x14002b629  call    ??1?$_Tree@V?$_Tset_traits@VOpcPartUri@win_dox@@U?$less@VOpcPartUri@win_dox@@@std@@V?$allocator@VOpcPartUri@win_dox@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<win_dox::OpcPartUri,std::less<win_dox::OpcPartUri>,std::allocator<win_dox::OpcPartUri>,0>>::~_Tree<std::_Tset_traits<win_dox::OpcPartUri,std::less<win_dox::OpcPartUri>,std::allocator<win_dox::OpcPartUri>,0>>(void)
0x14002b62e  lea     rcx, [rbx+0F8h]
0x14002b635  call    ??1?$_Tree@V?$_Tmap_traits@$$CBVOpcPartUri@win_dox@@$$CBV12@U?$less@$$CBVOpcPartUri@win_dox@@@std@@V?$allocator@U?$pair@$$CBVOpcPartUri@win_dox@@$$CBV12@@std@@@4@$00@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<win_dox::OpcPartUri const,win_dox::OpcPartUri const,std::less<win_dox::OpcPartUri const>,std::allocator<std::pair<win_dox::OpcPartUri const,win_dox::OpcPartUri const>>,1>>::~_Tree<std::_Tmap_traits<win_dox::OpcPartUri const,win_dox::OpcPartUri const,std::less<win_dox::OpcPartUri const>,std::allocator<std::pair<win_dox::OpcPartUri const,win_dox::OpcPartUri const>>,1>>(void)
0x14002b63a  lea     rcx, [rbx+0E0h]
0x14002b641  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x14002b646  lea     rcx, [rbx+0D8h]
0x14002b64d  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x14002b652  lea     rcx, [rbx+60h]; lpCriticalSection
0x14002b656  call    ??1?$WaitingLockedQueue@UIUnknown@@@@QEAA@XZ; WaitingLockedQueue<IUnknown>::~WaitingLockedQueue<IUnknown>(void)
0x14002b65b  lea     rcx, [rbx+50h]
0x14002b65f  call    ??1?$_Tree@V?$_Tmap_traits@VOpcPartUri@win_dox@@UPartMapItem@@U?$less@VOpcPartUri@win_dox@@@std@@V?$allocator@U?$pair@$$CBVOpcPartUri@win_dox@@UPartMapItem@@@std@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<win_dox::OpcPartUri,PartMapItem,std::less<win_dox::OpcPartUri>,std::allocator<std::pair<win_dox::OpcPartUri const,PartMapItem>>,0>>::~_Tree<std::_Tmap_traits<win_dox::OpcPartUri,PartMapItem,std::less<win_dox::OpcPartUri>,std::allocator<std::pair<win_dox::OpcPartUri const,PartMapItem>>,0>>(void)
0x14002b664  cmp     dword ptr [rbx+48h], 0
0x14002b668  jl      short loc_14002B67B
0x14002b66a  lea     rcx, [rbx+18h]; lpCriticalSection
0x14002b66e  call    cs:__imp_DeleteCriticalSection
0x14002b674  mov     dword ptr [rbx+48h], 80004005h
0x14002b67b  lea     rax, ??_7TUnknown@NCOMLibrary@@6B@; const NCOMLibrary::TUnknown::`vftable'
0x14002b682  mov     [rbx], rax
0x14002b685  lock dec cs:?g_cOutStandingObjectCount@TUnknown@NCOMLibrary@@0JA; long NCOMLibrary::TUnknown::g_cOutStandingObjectCount
0x14002b68c  mov     rbx, [rsp+28h+arg_0]
0x14002b691  add     rsp, 20h
0x14002b695  pop     rdi
0x14002b696  retn
```
