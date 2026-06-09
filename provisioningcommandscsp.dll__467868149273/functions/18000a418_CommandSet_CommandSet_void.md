# CommandSet::CommandSet(void)

- ea: `0x18000a418`
- end: `0x18000a46e`
- name: `??0CommandSet@@QEAA@XZ`
- size: `86`
- prototype: `CommandSet *__fastcall(CommandSet *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180006e40`
- `0x18000751c`
- `0x1800096c0`
- `0x18000bce8`

## callees

- `0x180007a08`

## pseudocode

```c
CommandSet *__fastcall CommandSet::CommandSet(CommandSet *this)
{
  __int64 v2; // rax

  *(_DWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  std::_List_alloc<0,std::_List_base_types<Command>>::_Buynode0((__int64)this, 0, 0);
  *((_QWORD *)this + 1) = v2;
  *((_QWORD *)this + 6) = 7;
  *((_QWORD *)this + 5) = 0;
  *((_WORD *)this + 12) = 0;
  return this;
}

```

## disassembly

```asm
0x18000a418  mov     [rsp+arg_8], rbx
0x18000a41d  push    rdi
0x18000a41e  sub     rsp, 20h
0x18000a422  mov     dword ptr [rcx], 0
0x18000a428  xor     r8d, r8d
0x18000a42b  xor     edx, edx
0x18000a42d  mov     qword ptr [rcx+8], 0
0x18000a435  mov     qword ptr [rcx+10h], 0
0x18000a43d  mov     rdi, rcx
0x18000a440  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@UCommand@@V?$allocator@UCommand@@@std@@@std@@@std@@QEAAPEAU?$_List_node@UCommand@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<Command>>::_Buynode0(std::_List_node<Command,void *> *,std::_List_node<Command,void *> *)
0x18000a445  mov     rbx, [rsp+28h+arg_8]
0x18000a44a  mov     [rdi+8], rax
0x18000a44e  xor     eax, eax
0x18000a450  mov     qword ptr [rdi+30h], 7
0x18000a458  mov     qword ptr [rdi+28h], 0
0x18000a460  mov     [rdi+18h], ax
0x18000a464  mov     rax, rdi
0x18000a467  add     rsp, 20h
0x18000a46b  pop     rdi
0x18000a46c  retn
```
