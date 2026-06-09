# std::_List_alloc<0,std::_List_base_types<CommandSet,std::allocator<CommandSet>>>::_Buynode0(std::_List_node<CommandSet,void *> *,std::_List_node<CommandSet,void *> *)

- ea: `0x18000ba18`
- end: `0x18000ba65`
- name: `?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@@std@@QEAAPEAU?$_List_node@UCommandSet@@PEAX@2@PEAU32@0@Z`
- size: `77`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a330`
- `0x18000a4a0`
- `0x18000b1c8`
- `0x18000b7dc`
- `0x18000c144`

## callees

- `0x1800016a4`
- `0x18000ba18`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x18000ba41`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x18000ba41`

## pseudocode

```c
_QWORD *__fastcall std::_List_alloc<0,std::_List_base_types<CommandSet>>::_Buynode0(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  _QWORD *result; // rax

  result = operator new(0x48u);
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
  *result = a2;
  result[1] = a3;
  return result;
}

```

## disassembly

```asm
0x18000ba18  mov     [rsp+arg_8], rbx
0x18000ba1d  mov     [rsp+arg_0], rcx
0x18000ba22  push    rdi
0x18000ba23  sub     rsp, 20h
0x18000ba27  mov     rdi, r8
0x18000ba2a  mov     rbx, rdx
0x18000ba2d  mov     ecx, 48h ; 'H'; Size
0x18000ba32  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ba37  mov     [rsp+28h+arg_0], rax
0x18000ba3c  test    rax, rax
0x18000ba3f  jnz     short loc_18000BA48
0x18000ba41  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000ba47  int     3; Trap to Debugger
0x18000ba48  test    rbx, rbx
0x18000ba4b  jnz     short loc_18000BA53
0x18000ba4d  mov     rbx, rax
0x18000ba50  mov     rdi, rax
0x18000ba53  mov     [rax], rbx
0x18000ba56  mov     [rax+8], rdi
0x18000ba5a  mov     rbx, [rsp+28h+arg_8]
0x18000ba5f  add     rsp, 20h
0x18000ba63  pop     rdi
0x18000ba64  retn
```
