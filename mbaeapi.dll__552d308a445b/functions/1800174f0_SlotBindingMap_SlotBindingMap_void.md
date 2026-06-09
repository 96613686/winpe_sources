# SlotBindingMap::~SlotBindingMap(void)

- ea: `0x1800174f0`
- end: `0x180017555`
- name: `??1SlotBindingMap@@QEAA@XZ`
- size: `101`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001743c`
- `0x18003b004`
- `0x18003b4bc`

## callees

- `0x1800028b0`
- `0x180016a94`
- `0x180017144`
- `0x1800174f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180017501`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180017501`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall SlotBindingMap::~SlotBindingMap(struct _RTL_CRITICAL_SECTION *this)
{
  struct _RTL_CRITICAL_SECTION *CriticalSection; // rdi
  struct _RTL_CRITICAL_SECTION *v3; // rcx

  DeleteCriticalSection(this + 1);
  std::_Tree<std::_Tmap_traits<_GUID,std::vector<_GUID>,GUID_COMP,std::allocator<std::pair<_GUID const,std::vector<_GUID>>>,0>>::~_Tree<std::_Tmap_traits<_GUID,std::vector<_GUID>,GUID_COMP,std::allocator<std::pair<_GUID const,std::vector<_GUID>>>,0>>(&this->OwningThread);
  CriticalSection = this->DebugInfo->CriticalSection;
  while ( !BYTE1(CriticalSection->LockSemaphore) )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,SlotBindingMap::AdapterParameters>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<_GUID const,SlotBindingMap::AdapterParameters>,void *>>>(
      this,
      this,
      CriticalSection->OwningThread);
    v3 = CriticalSection;
    CriticalSection = (struct _RTL_CRITICAL_SECTION *)CriticalSection->DebugInfo;
    operator delete(v3);
  }
  operator delete(this->DebugInfo);
}

```

## disassembly

```asm
0x1800174f0  mov     [rsp+arg_0], rbx
0x1800174f5  push    rdi
0x1800174f6  sub     rsp, 20h
0x1800174fa  mov     rbx, rcx
0x1800174fd  add     rcx, 28h ; '('; lpCriticalSection
0x180017501  call    cs:__imp_DeleteCriticalSection
0x180017507  lea     rcx, [rbx+10h]
0x18001750b  call    ??1?$_Tree@V?$_Tmap_traits@U_GUID@@V?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@UGUID_COMP@@V?$allocator@U?$pair@$$CBU_GUID@@V?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<_GUID,std::vector<_GUID>,GUID_COMP,std::allocator<std::pair<_GUID const,std::vector<_GUID>>>,0>>::~_Tree<std::_Tmap_traits<_GUID,std::vector<_GUID>,GUID_COMP,std::allocator<std::pair<_GUID const,std::vector<_GUID>>>,0>>(void)
0x180017510  mov     rax, [rbx]
0x180017513  mov     rdi, [rax+8]
0x180017517  jmp     short loc_180017538
0x180017519  mov     r8, [rdi+10h]
0x18001751d  mov     rdx, rbx
0x180017520  mov     rcx, rbx
0x180017523  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@UAdapterParameters@SlotBindingMap@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@UAdapterParameters@SlotBindingMap@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@UAdapterParameters@SlotBindingMap@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@UAdapterParameters@SlotBindingMap@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,SlotBindingMap::AdapterParameters>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<_GUID const,SlotBindingMap::AdapterParameters>,void *>>>(std::allocator<std::_Tree_node<std::pair<_GUID const,SlotBindingMap::AdapterParameters>,void *>> &,std::_Tree_node<std::pair<_GUID const,SlotBindingMap::AdapterParameters>,void *> *)
0x180017528  mov     rcx, rdi; Block
0x18001752b  mov     edx, 48h ; 'H'
0x180017530  mov     rdi, [rdi]
0x180017533  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180017538  cmp     byte ptr [rdi+19h], 0
0x18001753c  jz      short loc_180017519
0x18001753e  mov     rcx, [rbx]; Block
0x180017541  mov     edx, 48h ; 'H'
0x180017546  mov     rbx, [rsp+28h+arg_0]
0x18001754b  add     rsp, 20h
0x18001754f  pop     rdi
0x180017550  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
