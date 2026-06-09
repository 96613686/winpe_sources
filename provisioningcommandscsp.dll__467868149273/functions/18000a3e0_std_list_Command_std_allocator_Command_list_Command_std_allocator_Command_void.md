# std::list<Command,std::allocator<Command>>::list<Command,std::allocator<Command>>(void)

- ea: `0x18000a3e0`
- end: `0x18000a40f`
- name: `??0?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAA@XZ`
- size: `47`
- prototype: `void(void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007a08`

## pseudocode

```c
void __fastcall std::list<Command>::list<Command>(_QWORD *a1)
{
  __int64 v2; // rax

  *a1 = 0;
  a1[1] = 0;
  std::_List_alloc<0,std::_List_base_types<Command>>::_Buynode0((__int64)a1, 0, 0);
  *a1 = v2;
}

```

## disassembly

```asm
0x18000a3e0  push    rbx
0x18000a3e2  sub     rsp, 20h
0x18000a3e6  xor     r8d, r8d
0x18000a3e9  mov     qword ptr [rcx], 0
0x18000a3f0  xor     edx, edx
0x18000a3f2  mov     qword ptr [rcx+8], 0
0x18000a3fa  mov     rbx, rcx
0x18000a3fd  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@UCommand@@V?$allocator@UCommand@@@std@@@std@@@std@@QEAAPEAU?$_List_node@UCommand@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<Command>>::_Buynode0(std::_List_node<Command,void *> *,std::_List_node<Command,void *> *)
0x18000a402  mov     [rbx], rax
0x18000a405  mov     rax, rbx
0x18000a408  add     rsp, 20h
0x18000a40c  pop     rbx
0x18000a40d  retn
```
