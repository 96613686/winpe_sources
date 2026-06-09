# std::list<Command,std::allocator<Command>>::list<Command,std::allocator<Command>>(void)

- ea: `0x180009f00`
- end: `0x180009f2e`
- name: `??0?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007698`

## pseudocode

```c
void __fastcall std::list<Command>::list<Command>(_QWORD *a1)
{
  *a1 = 0;
  a1[1] = 0;
  *a1 = std::_List_alloc<0,std::_List_base_types<Command>>::_Buynode0(a1, 0, 0);
}

```

## disassembly

```asm
0x180009f00  push    rbx
0x180009f02  sub     rsp, 20h
0x180009f06  xor     r8d, r8d
0x180009f09  mov     qword ptr [rcx], 0
0x180009f10  xor     edx, edx
0x180009f12  mov     qword ptr [rcx+8], 0
0x180009f1a  mov     rbx, rcx
0x180009f1d  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@UCommand@@V?$allocator@UCommand@@@std@@@std@@@std@@QEAAPEAU?$_List_node@UCommand@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<Command>>::_Buynode0(std::_List_node<Command,void *> *,std::_List_node<Command,void *> *)
0x180009f22  mov     [rbx], rax
0x180009f25  mov     rax, rbx
0x180009f28  add     rsp, 20h
0x180009f2c  pop     rbx
0x180009f2d  retn
```
