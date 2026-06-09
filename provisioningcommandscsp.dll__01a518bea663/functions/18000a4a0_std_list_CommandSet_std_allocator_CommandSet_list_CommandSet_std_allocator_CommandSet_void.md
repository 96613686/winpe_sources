# std::list<CommandSet,std::allocator<CommandSet>>::list<CommandSet,std::allocator<CommandSet>>(void)

- ea: `0x18000a4a0`
- end: `0x18000a4ce`
- name: `??0?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000ba18`

## pseudocode

```c
void __fastcall std::list<CommandSet>::list<CommandSet>(_QWORD *a1)
{
  *a1 = 0;
  a1[1] = 0;
  *a1 = std::_List_alloc<0,std::_List_base_types<CommandSet>>::_Buynode0(a1, 0, 0);
}

```

## disassembly

```asm
0x18000a4a0  push    rbx
0x18000a4a2  sub     rsp, 20h
0x18000a4a6  xor     r8d, r8d
0x18000a4a9  mov     qword ptr [rcx], 0
0x18000a4b0  xor     edx, edx
0x18000a4b2  mov     qword ptr [rcx+8], 0
0x18000a4ba  mov     rbx, rcx
0x18000a4bd  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@@std@@QEAAPEAU?$_List_node@UCommandSet@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<CommandSet>>::_Buynode0(std::_List_node<CommandSet,void *> *,std::_List_node<CommandSet,void *> *)
0x18000a4c2  mov     [rbx], rax
0x18000a4c5  mov     rax, rbx
0x18000a4c8  add     rsp, 20h
0x18000a4cc  pop     rbx
0x18000a4cd  retn
```
