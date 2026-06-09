# std::_Tree_val<std::_Tree_simple_types<ulong>>::_Erase_tree<std::allocator<std::_Tree_node<ulong,void *>>>(std::allocator<std::_Tree_node<ulong,void *>> &,std::_Tree_node<ulong,void *> *)

- ea: `0x18000f4cc`
- end: `0x18000f520`
- name: `??$_Erase_tree@V?$allocator@U?$_Tree_node@KPEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@K@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@KPEAX@std@@@1@PEAU?$_Tree_node@KPEAX@1@@Z`
- size: `84`
- prototype: `void __fastcall(__int64, __int64, __int64)`
- caller_count: `7`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000f4cc`
- `0x18000f9f0`
- `0x18000fabc`
- `0x18000fb94`
- `0x18000fc84`
- `0x18000fcfc`
- `0x180010ea0`

## callees

- `0x180001d14`
- `0x18000f4cc`

## pseudocode

```c
void __fastcall std::_Tree_val<std::_Tree_simple_types<unsigned long>>::_Erase_tree<std::allocator<std::_Tree_node<unsigned long,void *>>>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  _QWORD *v3; // rbx
  void *v6; // rcx

  v3 = (_QWORD *)a3;
  if ( !*(_BYTE *)(a3 + 25) )
  {
    do
    {
      std::_Tree_val<std::_Tree_simple_types<unsigned long>>::_Erase_tree<std::allocator<std::_Tree_node<unsigned long,void *>>>(
        a1,
        a2,
        v3[2]);
      v6 = v3;
      v3 = (_QWORD *)*v3;
      operator delete(v6);
    }
    while ( !*((_BYTE *)v3 + 25) );
  }
}

```

## disassembly

```asm
0x18000f4cc  mov     [rsp+arg_0], rbx
0x18000f4d1  mov     [rsp+arg_8], rsi
0x18000f4d6  push    rdi
0x18000f4d7  sub     rsp, 20h
0x18000f4db  cmp     byte ptr [r8+19h], 0
0x18000f4e0  mov     rbx, r8
0x18000f4e3  mov     rdi, rdx
0x18000f4e6  mov     rsi, rcx
0x18000f4e9  jnz     short loc_18000F510
0x18000f4eb  mov     r8, [rbx+10h]
0x18000f4ef  mov     rdx, rdi
0x18000f4f2  mov     rcx, rsi
0x18000f4f5  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@KPEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@K@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@KPEAX@std@@@1@PEAU?$_Tree_node@KPEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<ulong>>::_Erase_tree<std::allocator<std::_Tree_node<ulong,void *>>>(std::allocator<std::_Tree_node<ulong,void *>> &,std::_Tree_node<ulong,void *> *)
0x18000f4fa  mov     rcx, rbx; Block
0x18000f4fd  mov     edx, 20h ; ' '
0x18000f502  mov     rbx, [rbx]
0x18000f505  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f50a  cmp     byte ptr [rbx+19h], 0
0x18000f50e  jz      short loc_18000F4EB
0x18000f510  mov     rbx, [rsp+28h+arg_0]
0x18000f515  mov     rsi, [rsp+28h+arg_8]
0x18000f51a  add     rsp, 20h
0x18000f51e  pop     rdi
0x18000f51f  retn
```
