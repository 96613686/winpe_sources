# std::_Tree<std::_Tmap_traits<ulong,CounterHelper *,std::less<ulong>,std::allocator<std::pair<ulong const,CounterHelper *>>,0>>::_Erase(std::_Tree_node<std::pair<ulong const,CounterHelper *>,void *> *)

- ea: `0x180008f38`
- end: `0x180008f87`
- name: `?_Erase@?$_Tree@V?$_Tmap_traits@KPEAVCounterHelper@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@3@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBKPEAVCounterHelper@@@std@@PEAX@2@@Z`
- size: `79`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180006d0c`
- `0x180008f38`
- `0x18000906c`

## callees

- `0x180008f38`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180008f68`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008f68`

## pseudocode

```c
void __fastcall std::_Tree<std::_Tmap_traits<unsigned long,CounterHelper *,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,CounterHelper *>>,0>>::_Erase(
        __int64 a1,
        void *a2)
{
  void *v2; // rdi
  _QWORD *v4; // rbx

  v2 = a2;
  v4 = a2;
  if ( !*((_BYTE *)a2 + 25) )
  {
    do
    {
      std::_Tree<std::_Tmap_traits<unsigned long,CounterHelper *,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,CounterHelper *>>,0>>::_Erase(
        a1,
        v4[2]);
      v4 = (_QWORD *)*v4;
      operator delete(v2);
      v2 = v4;
    }
    while ( !*((_BYTE *)v4 + 25) );
  }
}

```

## disassembly

```asm
0x180008f38  mov     [rsp+arg_0], rbx
0x180008f3d  mov     [rsp+arg_8], rsi
0x180008f42  push    rdi
0x180008f43  sub     rsp, 20h
0x180008f47  cmp     byte ptr [rdx+19h], 0
0x180008f4b  mov     rdi, rdx
0x180008f4e  mov     rsi, rcx
0x180008f51  mov     rbx, rdx
0x180008f54  jnz     short loc_180008F77
0x180008f56  mov     rdx, [rbx+10h]
0x180008f5a  mov     rcx, rsi
0x180008f5d  call    ?_Erase@?$_Tree@V?$_Tmap_traits@KPEAVCounterHelper@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@3@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBKPEAVCounterHelper@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<ulong,CounterHelper *,std::less<ulong>,std::allocator<std::pair<ulong const,CounterHelper *>>,0>>::_Erase(std::_Tree_node<std::pair<ulong const,CounterHelper *>,void *> *)
0x180008f62  mov     rbx, [rbx]
0x180008f65  mov     rcx, rdi
0x180008f68  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180008f6e  cmp     byte ptr [rbx+19h], 0
0x180008f72  mov     rdi, rbx
0x180008f75  jz      short loc_180008F56
0x180008f77  mov     rbx, [rsp+28h+arg_0]
0x180008f7c  mov     rsi, [rsp+28h+arg_8]
0x180008f81  add     rsp, 20h
0x180008f85  pop     rdi
0x180008f86  retn
```
