# std::_List_alloc<0,std::_List_base_types<Command,std::allocator<Command>>>::_Buynode0(std::_List_node<Command,void *> *,std::_List_node<Command,void *> *)

- ea: `0x140007d20`
- end: `0x140007d6d`
- name: `?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@UCommand@@V?$allocator@UCommand@@@std@@@std@@@std@@QEAAPEAU?$_List_node@UCommand@@PEAX@2@PEAU32@0@Z`
- size: `77`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140007bf0`
- `0x1400080e0`
- `0x140008234`
- `0x140008f54`
- `0x140009c08`

## callees

- `0x140001864`
- `0x140007d20`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x140007d49`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x140007d49`

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
0x140007d20  mov     [rsp+arg_8], rbx
0x140007d25  mov     [rsp+arg_0], rcx
0x140007d2a  push    rdi
0x140007d2b  sub     rsp, 20h
0x140007d2f  mov     rdi, r8
0x140007d32  mov     rbx, rdx
0x140007d35  mov     ecx, 80h; Size
0x140007d3a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140007d3f  mov     [rsp+28h+arg_0], rax
0x140007d44  test    rax, rax
0x140007d47  jnz     short loc_140007D50
0x140007d49  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x140007d4f  int     3; Trap to Debugger
0x140007d50  test    rbx, rbx
0x140007d53  jnz     short loc_140007D5B
0x140007d55  mov     rbx, rax
0x140007d58  mov     rdi, rax
0x140007d5b  mov     [rax], rbx
0x140007d5e  mov     [rax+8], rdi
0x140007d62  mov     rbx, [rsp+28h+arg_8]
0x140007d67  add     rsp, 20h
0x140007d6b  pop     rdi
0x140007d6c  retn
```
