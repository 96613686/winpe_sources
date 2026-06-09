# CConnectionList::Uninitialize(int)

- ea: `0x180015328`
- end: `0x18001537d`
- name: `?Uninitialize@CConnectionList@@QEAAXH@Z`
- size: `85`
- prototype: `void __fastcall(CConnectionList *__hidden this, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180003770`

## callees

- `0x180015328`
- `0x180015384`
- `0x18001e5b0`
- `0x180041c68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180015362`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180015362`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180015376`

## pseudocode

```c
void __fastcall CConnectionList::Uninitialize(CConnectionList *this)
{
  void *v2; // rdi

  CConnectionList::FlushConnectionList(this);
  v2 = *(void **)this;
  if ( *(_QWORD *)this )
  {
    std::_Tree<std::_Tmap_traits<_GUID const,ConnListEntry,std::less<_GUID const>,std::allocator<std::pair<_GUID const,ConnListEntry>>,0>>::~_Tree<std::_Tmap_traits<_GUID const,ConnListEntry,std::less<_GUID const>,std::allocator<std::pair<_GUID const,ConnListEntry>>,0>>(*(_QWORD *)this);
    operator delete(v2);
  }
  *(_QWORD *)this = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 2);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
}

```

## disassembly

```asm
0x180015328  mov     [rsp+arg_0], rbx
0x18001532d  push    rdi
0x18001532e  sub     rsp, 20h
0x180015332  mov     rbx, rcx
0x180015335  call    ?FlushConnectionList@CConnectionList@@QEAAXXZ; CConnectionList::FlushConnectionList(void)
0x18001533a  mov     rdi, [rbx]
0x18001533d  test    rdi, rdi
0x180015340  jz      short loc_180015357
0x180015342  mov     rcx, rdi
0x180015345  call    ??1?$_Tree@V?$_Tmap_traits@$$CBU_GUID@@VConnListEntry@@U?$less@$$CBU_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@VConnListEntry@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<_GUID const,ConnListEntry,std::less<_GUID const>,std::allocator<std::pair<_GUID const,ConnListEntry>>,0>>::~_Tree<std::_Tmap_traits<_GUID const,ConnListEntry,std::less<_GUID const>,std::allocator<std::pair<_GUID const,ConnListEntry>>,0>>(void)
0x18001534a  mov     edx, 10h; unsigned __int64
0x18001534f  mov     rcx, rdi; void *
0x180015352  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180015357  lea     rcx, [rbx+50h]; lpCriticalSection
0x18001535b  mov     qword ptr [rbx], 0
0x180015362  call    cs:__imp_DeleteCriticalSection
0x180015368  lea     rcx, [rbx+10h]
0x18001536c  mov     rbx, [rsp+28h+arg_0]
0x180015371  add     rsp, 20h
0x180015375  pop     rdi
0x180015376  jmp     cs:__imp_DeleteCriticalSection
```
