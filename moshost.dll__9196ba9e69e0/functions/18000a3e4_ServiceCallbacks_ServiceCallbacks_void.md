# ServiceCallbacks::~ServiceCallbacks(void)

- ea: `0x18000a3e4`
- end: `0x18000a44f`
- name: `??1ServiceCallbacks@@QEAA@XZ`
- size: `107`
- prototype: `void __fastcall(ServiceCallbacks *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, service_task`

## callers

- `0x18000ce30`

## callees

- `0x180001d24`
- `0x18000a2b8`
- `0x18000a3e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a448`

## pseudocode

```c
void __fastcall ServiceCallbacks::~ServiceCallbacks(ServiceCallbacks *this)
{
  void **v1; // rdi
  _QWORD *v3; // rbx
  void *v4; // rcx

  v1 = (void **)((char *)this + 56);
  v3 = *(_QWORD **)(*((_QWORD *)this + 7) + 8LL);
  while ( !*((_BYTE *)v3 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,enum CallingState>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned long const,enum CallingState>,void *>>>(
      v1,
      v1,
      v3[2]);
    v4 = v3;
    v3 = (_QWORD *)*v3;
    operator delete(v4);
  }
  operator delete(*v1);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
}

```

## disassembly

```asm
0x18000a3e4  mov     [rsp+arg_0], rbx
0x18000a3e9  mov     [rsp+arg_8], rsi
0x18000a3ee  push    rdi
0x18000a3ef  sub     rsp, 20h
0x18000a3f3  lea     rdi, [rcx+38h]
0x18000a3f7  mov     rsi, rcx
0x18000a3fa  mov     rax, [rdi]
0x18000a3fd  mov     rbx, [rax+8]
0x18000a401  jmp     short loc_18000A422
0x18000a403  mov     r8, [rbx+10h]
0x18000a407  mov     rdx, rdi
0x18000a40a  mov     rcx, rdi
0x18000a40d  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBKW4CallingState@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKW4CallingState@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBKW4CallingState@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBKW4CallingState@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,CallingState>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<ulong const,CallingState>,void *>>>(std::allocator<std::_Tree_node<std::pair<ulong const,CallingState>,void *>> &,std::_Tree_node<std::pair<ulong const,CallingState>,void *> *)
0x18000a412  mov     rcx, rbx; Block
0x18000a415  mov     edx, 28h ; '('
0x18000a41a  mov     rbx, [rbx]
0x18000a41d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a422  cmp     byte ptr [rbx+19h], 0
0x18000a426  jz      short loc_18000A403
0x18000a428  mov     rcx, [rdi]; Block
0x18000a42b  mov     edx, 28h ; '('
0x18000a430  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a435  lea     rcx, [rsi+10h]
0x18000a439  mov     rbx, [rsp+28h+arg_0]
0x18000a43e  mov     rsi, [rsp+28h+arg_8]
0x18000a443  add     rsp, 20h
0x18000a447  pop     rdi
0x18000a448  jmp     cs:__imp_DeleteCriticalSection
```
