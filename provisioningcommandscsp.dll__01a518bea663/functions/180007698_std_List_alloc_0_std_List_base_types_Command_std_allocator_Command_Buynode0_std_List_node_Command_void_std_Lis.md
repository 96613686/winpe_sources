# std::_List_alloc<0,std::_List_base_types<Command,std::allocator<Command>>>::_Buynode0(std::_List_node<Command,void *> *,std::_List_node<Command,void *> *)

- ea: `0x180007698`
- end: `0x1800076e5`
- name: `?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@UCommand@@V?$allocator@UCommand@@@std@@@std@@@std@@QEAAPEAU?$_List_node@UCommand@@PEAX@2@PEAU32@0@Z`
- size: `77`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006760`
- `0x180009f00`
- `0x180009f34`
- `0x18000a444`
- `0x18000be80`

## callees

- `0x1800016a4`
- `0x180007698`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x1800076c1`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x1800076c1`

## pseudocode

```c
_QWORD *__fastcall std::_List_alloc<0,std::_List_base_types<Command>>::_Buynode0(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  _QWORD *result; // rax
  __int64 v6; // rcx

  result = operator new(0x80u);
  if ( !result )
  {
    std::_Xbad_alloc();
    __debugbreak();
  }
  if ( !a2 )
  {
    a2 = result;
    a3 = result;
  }
  try
  {
    *result = a2;
    result[1] = a3;
  }
  catch ( ... )
  {
    std::_Wrap_alloc<std::allocator<unsigned short>>::deallocate(v6, result);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x180007698  mov     [rsp+arg_8], rbx
0x18000769d  mov     [rsp+arg_0], rcx
0x1800076a2  push    rdi
0x1800076a3  sub     rsp, 20h
0x1800076a7  mov     rdi, r8
0x1800076aa  mov     rbx, rdx
0x1800076ad  mov     ecx, 80h; Size
0x1800076b2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800076b7  mov     [rsp+28h+arg_0], rax
0x1800076bc  test    rax, rax
0x1800076bf  jnz     short loc_1800076C8
0x1800076c1  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x1800076c7  int     3; Trap to Debugger
0x1800076c8  test    rbx, rbx
0x1800076cb  jnz     short loc_1800076D3
0x1800076cd  mov     rbx, rax
0x1800076d0  mov     rdi, rax
0x1800076d3  mov     [rax], rbx
0x1800076d6  mov     [rax+8], rdi
0x1800076da  mov     rbx, [rsp+28h+arg_8]
0x1800076df  add     rsp, 20h
0x1800076e3  pop     rdi
0x1800076e4  retn
```
