# CDict::~CDict(void)

- ea: `0x1800047ec`
- end: `0x18000481b`
- name: `??1CDict@@QEAA@XZ`
- size: `47`
- prototype: `void __fastcall(CDict *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f7e8`
- `0x18000fb44`
- `0x180011b20`
- `0x180011df0`

## callees

- `0x180004760`
- `0x1800047ec`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x1800047fe`
- `KERNEL32!FreeLibrary` at `0x1800047fe`

## pseudocode

```c
void __fastcall CDict::~CDict(CDict *this)
{
  HMODULE v2; // rcx

  v2 = (HMODULE)*((_QWORD *)this + 6);
  if ( v2 )
    FreeLibrary(v2);
  std::_Tree<std::_Tmap_traits<_GUID const,TermInfo const *,GUIDLess,std::allocator<std::pair<_GUID const,TermInfo const *>>,0>>::~_Tree<std::_Tmap_traits<_GUID const,TermInfo const *,GUIDLess,std::allocator<std::pair<_GUID const,TermInfo const *>>,0>>((char *)this + 32);
  std::_Tree<std::_Tmap_traits<_GUID const,TermInfo const *,GUIDLess,std::allocator<std::pair<_GUID const,TermInfo const *>>,0>>::~_Tree<std::_Tmap_traits<_GUID const,TermInfo const *,GUIDLess,std::allocator<std::pair<_GUID const,TermInfo const *>>,0>>((char *)this + 16);
}

```

## disassembly

```asm
0x1800047ec  push    rbx
0x1800047ee  sub     rsp, 20h
0x1800047f2  mov     rbx, rcx
0x1800047f5  mov     rcx, [rcx+30h]; hLibModule
0x1800047f9  test    rcx, rcx
0x1800047fc  jz      short loc_180004804
0x1800047fe  call    cs:__imp_FreeLibrary
0x180004804  lea     rcx, [rbx+20h]
0x180004808  call    ??1?$_Tree@V?$_Tmap_traits@$$CBU_GUID@@PEBUTermInfo@@UGUIDLess@@V?$allocator@U?$pair@$$CBU_GUID@@PEBUTermInfo@@@std@@@std@@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<_GUID const,TermInfo const *,GUIDLess,std::allocator<std::pair<_GUID const,TermInfo const *>>,0>>::~_Tree<std::_Tmap_traits<_GUID const,TermInfo const *,GUIDLess,std::allocator<std::pair<_GUID const,TermInfo const *>>,0>>(void)
0x18000480d  lea     rcx, [rbx+10h]
0x180004811  add     rsp, 20h
0x180004815  pop     rbx
0x180004816  jmp     ??1?$_Tree@V?$_Tmap_traits@$$CBU_GUID@@PEBUTermInfo@@UGUIDLess@@V?$allocator@U?$pair@$$CBU_GUID@@PEBUTermInfo@@@std@@@std@@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<_GUID const,TermInfo const *,GUIDLess,std::allocator<std::pair<_GUID const,TermInfo const *>>,0>>::~_Tree<std::_Tmap_traits<_GUID const,TermInfo const *,GUIDLess,std::allocator<std::pair<_GUID const,TermInfo const *>>,0>>(void)
```
