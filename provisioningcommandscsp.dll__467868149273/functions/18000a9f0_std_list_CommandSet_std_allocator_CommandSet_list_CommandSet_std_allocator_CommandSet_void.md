# std::list<CommandSet,std::allocator<CommandSet>>::list<CommandSet,std::allocator<CommandSet>>(void)

- ea: `0x18000a9f0`
- end: `0x18000aa1f`
- name: `??0?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAA@XZ`
- size: `47`
- prototype: `void(void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000c0d0`

## pseudocode

```c
void __fastcall std::list<CommandSet>::list<CommandSet>(_QWORD *a1)
{
  __int64 v2; // rax

  *a1 = 0;
  a1[1] = 0;
  std::_List_alloc<0,std::_List_base_types<CommandSet>>::_Buynode0((__int64)a1, 0, 0);
  *a1 = v2;
}

```

## disassembly

```asm
0x18000a9f0  push    rbx
0x18000a9f2  sub     rsp, 20h
0x18000a9f6  xor     r8d, r8d
0x18000a9f9  mov     qword ptr [rcx], 0
0x18000aa00  xor     edx, edx
0x18000aa02  mov     qword ptr [rcx+8], 0
0x18000aa0a  mov     rbx, rcx
0x18000aa0d  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@@std@@QEAAPEAU?$_List_node@UCommandSet@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<CommandSet>>::_Buynode0(std::_List_node<CommandSet,void *> *,std::_List_node<CommandSet,void *> *)
0x18000aa12  mov     [rbx], rax
0x18000aa15  mov     rax, rbx
0x18000aa18  add     rsp, 20h
0x18000aa1c  pop     rbx
0x18000aa1d  retn
```
