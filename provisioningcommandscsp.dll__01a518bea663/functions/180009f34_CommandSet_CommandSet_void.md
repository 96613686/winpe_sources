# CommandSet::CommandSet(void)

- ea: `0x180009f34`
- end: `0x180009f89`
- name: `??0CommandSet@@QEAA@XZ`
- size: `85`
- prototype: `CommandSet *__fastcall(CommandSet *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180006b10`
- `0x1800071d8`
- `0x180009290`
- `0x18000b660`

## callees

- `0x180007698`

## pseudocode

```c
CommandSet *__fastcall CommandSet::CommandSet(CommandSet *this)
{
  *(_DWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 1) = std::_List_alloc<0,std::_List_base_types<Command>>::_Buynode0(this, 0, 0);
  *((_QWORD *)this + 6) = 7;
  *((_QWORD *)this + 5) = 0;
  *((_WORD *)this + 12) = 0;
  return this;
}

```

## disassembly

```asm
0x180009f34  mov     [rsp+arg_8], rbx
0x180009f39  push    rdi
0x180009f3a  sub     rsp, 20h
0x180009f3e  mov     dword ptr [rcx], 0
0x180009f44  xor     r8d, r8d
0x180009f47  xor     edx, edx
0x180009f49  mov     qword ptr [rcx+8], 0
0x180009f51  mov     qword ptr [rcx+10h], 0
0x180009f59  mov     rdi, rcx
0x180009f5c  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@UCommand@@V?$allocator@UCommand@@@std@@@std@@@std@@QEAAPEAU?$_List_node@UCommand@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<Command>>::_Buynode0(std::_List_node<Command,void *> *,std::_List_node<Command,void *> *)
0x180009f61  mov     rbx, [rsp+28h+arg_8]
0x180009f66  mov     [rdi+8], rax
0x180009f6a  xor     eax, eax
0x180009f6c  mov     qword ptr [rdi+30h], 7
0x180009f74  mov     qword ptr [rdi+28h], 0
0x180009f7c  mov     [rdi+18h], ax
0x180009f80  mov     rax, rdi
0x180009f83  add     rsp, 20h
0x180009f87  pop     rdi
0x180009f88  retn
```
