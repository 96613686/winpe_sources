# std::list<Command,std::allocator<Command>>::list<Command,std::allocator<Command>>(void)

- ea: `0x140007bf0`
- end: `0x140007c1e`
- name: `??0?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAA@XZ`
- size: `46`
- prototype: `void(void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140007d20`

## pseudocode

```c
void __fastcall std::list<Command>::list<Command>(_QWORD *a1)
{
  *a1 = 0;
  a1[1] = 0;
  *a1 = std::_List_alloc<0,std::_List_base_types<Command>>::_Buynode0((__int64)a1, 0, 0);
}

```

## disassembly

```asm
0x140007bf0  push    rbx
0x140007bf2  sub     rsp, 20h
0x140007bf6  xor     r8d, r8d
0x140007bf9  mov     qword ptr [rcx], 0
0x140007c00  xor     edx, edx
0x140007c02  mov     qword ptr [rcx+8], 0
0x140007c0a  mov     rbx, rcx
0x140007c0d  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@UCommand@@V?$allocator@UCommand@@@std@@@std@@@std@@QEAAPEAU?$_List_node@UCommand@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<Command>>::_Buynode0(std::_List_node<Command,void *> *,std::_List_node<Command,void *> *)
0x140007c12  mov     [rbx], rax
0x140007c15  mov     rax, rbx
0x140007c18  add     rsp, 20h
0x140007c1c  pop     rbx
0x140007c1d  retn
```
