# CExtensionHelperInfoContainer::~CExtensionHelperInfoContainer(void)

- ea: `0x18001ea34`
- end: `0x18001ea83`
- name: `??1CExtensionHelperInfoContainer@@QEAA@XZ`
- size: `79`
- prototype: `void __fastcall(void **this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x18001ed48`

## callees

- `0x180006d58`
- `0x180014f04`
- `0x18001ea34`
- `0x18001ef0c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001ea4b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001ea4b`

## pseudocode

```c
void __fastcall CExtensionHelperInfoContainer::~CExtensionHelperInfoContainer(void **this)
{
  void *v2; // rcx

  CExtensionHelperInfoContainer::CleanupResources((CExtensionHelperInfoContainer *)this);
  v2 = this[3];
  if ( v2 )
  {
    operator delete(v2);
    this[3] = 0;
    this[4] = 0;
    this[5] = 0;
  }
  std::_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CExtensionHelperInfoContainer *,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,CExtensionHelperInfoContainer *>>,0>>::~_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CExtensionHelperInfoContainer *,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,CExtensionHelperInfoContainer *>>,0>>(this + 1);
  ATL::CStringData::Release((ATL::CStringData *)((char *)*this - 24));
}

```

## disassembly

```asm
0x18001ea34  push    rbx
0x18001ea36  sub     rsp, 20h
0x18001ea3a  mov     rbx, rcx
0x18001ea3d  call    ?CleanupResources@CExtensionHelperInfoContainer@@QEAAXXZ; CExtensionHelperInfoContainer::CleanupResources(void)
0x18001ea42  mov     rcx, [rbx+18h]
0x18001ea46  test    rcx, rcx
0x18001ea49  jz      short loc_18001EA69
0x18001ea4b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001ea51  mov     qword ptr [rbx+18h], 0
0x18001ea59  mov     qword ptr [rbx+20h], 0
0x18001ea61  mov     qword ptr [rbx+28h], 0
0x18001ea69  lea     rcx, [rbx+8]
0x18001ea6d  call    ??1?$_Tree@V?$_Tmap_traits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCExtensionHelperInfoContainer@@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCExtensionHelperInfoContainer@@@std@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CExtensionHelperInfoContainer *,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,CExtensionHelperInfoContainer *>>,0>>::~_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CExtensionHelperInfoContainer *,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,CExtensionHelperInfoContainer *>>,0>>(void)
0x18001ea72  mov     rcx, [rbx]
0x18001ea75  sub     rcx, 18h; this
0x18001ea79  add     rsp, 20h
0x18001ea7d  pop     rbx
0x18001ea7e  jmp     ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
```
