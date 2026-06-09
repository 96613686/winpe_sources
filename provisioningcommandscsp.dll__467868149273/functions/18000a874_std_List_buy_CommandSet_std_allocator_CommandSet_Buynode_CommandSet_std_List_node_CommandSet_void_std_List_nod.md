# std::_List_buy<CommandSet,std::allocator<CommandSet>>::_Buynode<CommandSet>(std::_List_node<CommandSet,void *> *,std::_List_node<CommandSet,void *> *,CommandSet &&)

- ea: `0x18000a874`
- end: `0x18000a8ed`
- name: `??$_Buynode@UCommandSet@@@?$_List_buy@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAAPEAU?$_List_node@UCommandSet@@PEAX@1@PEAU21@0$$QEAUCommandSet@@@Z`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000be6c`

## callees

- `0x180007e9c`
- `0x18000a990`
- `0x18000c0d0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::_List_buy<CommandSet>::_Buynode<CommandSet>(__int64 a1, _QWORD *a2, _QWORD *a3, _DWORD *a4)
{
  __int64 v5; // rax
  __int64 v6; // rdi
  __int64 v7; // rbx
  __int64 v8; // rcx
  __int64 result; // rax
  __int64 v10; // [rsp+30h] [rbp+8h]

  std::_List_alloc<0,std::_List_base_types<CommandSet>>::_Buynode0(a1, a2, a3);
  v6 = v5;
  v10 = v5;
  v7 = v5 + 16;
  *(_DWORD *)(v5 + 16) = *a4;
  try
  {
    std::list<Command>::list<Command>();
    *(_QWORD *)(v7 + 48) = 7;
    *(_QWORD *)(v7 + 40) = 0;
    *(_WORD *)(v7 + 24) = 0;
    std::wstring::assign((void *)(v7 + 24));
    result = v6;
  }
  catch ( ... )
  {
    std::_Wrap_alloc<std::allocator<unsigned short>>::deallocate(v8, v10);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x18000a874  mov     [rsp+arg_8], rbx
0x18000a879  mov     [rsp+arg_10], rsi
0x18000a87e  mov     [rsp+arg_0], rcx
0x18000a883  push    rdi
0x18000a884  sub     rsp, 20h
0x18000a888  mov     rsi, r9
0x18000a88b  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@@std@@QEAAPEAU?$_List_node@UCommandSet@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<CommandSet>>::_Buynode0(std::_List_node<CommandSet,void *> *,std::_List_node<CommandSet,void *> *)
0x18000a890  mov     rdi, rax
0x18000a893  mov     [rsp+28h+arg_0], rax
0x18000a898  lea     rbx, [rax+10h]
0x18000a89c  mov     [rsp+28h+arg_18], rbx
0x18000a8a1  mov     ecx, [rsi]
0x18000a8a3  mov     [rbx], ecx
0x18000a8a5  lea     rdx, [rsi+8]
0x18000a8a9  lea     rcx, [rbx+8]
0x18000a8ad  call    ??0?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAA@AEBV01@@Z; std::list<Command>::list<Command>(std::list<Command> const &)
0x18000a8b2  nop
0x18000a8b3  lea     rcx, [rbx+18h]; void *
0x18000a8b7  mov     qword ptr [rcx+18h], 7
0x18000a8bf  xor     eax, eax
0x18000a8c1  mov     [rcx+10h], rax
0x18000a8c5  mov     [rcx], ax
0x18000a8c8  lea     rdx, [rsi+18h]
0x18000a8cc  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000a8d0  xor     r8d, r8d
0x18000a8d3  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18000a8d8  nop
0x18000a8d9  mov     rax, rdi
0x18000a8dc  mov     rbx, [rsp+28h+arg_8]
0x18000a8e1  mov     rsi, [rsp+28h+arg_10]
0x18000a8e6  add     rsp, 20h
0x18000a8ea  pop     rdi
0x18000a8eb  retn
```
