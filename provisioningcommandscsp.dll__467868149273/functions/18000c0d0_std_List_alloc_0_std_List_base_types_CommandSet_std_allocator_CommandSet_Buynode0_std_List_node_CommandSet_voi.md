# std::_List_alloc<0,std::_List_base_types<CommandSet,std::allocator<CommandSet>>>::_Buynode0(std::_List_node<CommandSet,void *> *,std::_List_node<CommandSet,void *> *)

- ea: `0x18000c0d0`
- end: `0x18000c124`
- name: `?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@@std@@QEAAPEAU?$_List_node@UCommandSet@@PEAX@2@PEAU32@0@Z`
- size: `84`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a874`
- `0x18000a9f0`
- `0x18000b81c`
- `0x18000be6c`
- `0x18000c744`

## callees

- `0x1800016b4`
- `0x18000c0d0`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x18000c0f9`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x18000c0f9`

## pseudocode

```c
void __fastcall std::_List_alloc<0,std::_List_base_types<CommandSet>>::_Buynode0(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  _QWORD *v5; // rax

  v5 = operator new(0x48u);
  if ( !v5 )
  {
    std::_Xbad_alloc();
    __debugbreak();
  }
  if ( !a2 )
  {
    a2 = v5;
    a3 = v5;
  }
  *v5 = a2;
  v5[1] = a3;
}

```

## disassembly

```asm
0x18000c0d0  mov     [rsp+arg_8], rbx
0x18000c0d5  mov     [rsp+arg_0], rcx
0x18000c0da  push    rdi
0x18000c0db  sub     rsp, 20h
0x18000c0df  mov     rdi, r8
0x18000c0e2  mov     rbx, rdx
0x18000c0e5  mov     ecx, 48h ; 'H'; Size
0x18000c0ea  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c0ef  mov     [rsp+28h+arg_0], rax
0x18000c0f4  test    rax, rax
0x18000c0f7  jnz     short loc_18000C106
0x18000c0f9  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000c100  nop     dword ptr [rax+rax+00h]
0x18000c105  int     3; Trap to Debugger
0x18000c106  test    rbx, rbx
0x18000c109  jnz     short loc_18000C111
0x18000c10b  mov     rbx, rax
0x18000c10e  mov     rdi, rax
0x18000c111  mov     [rax], rbx
0x18000c114  mov     [rax+8], rdi
0x18000c118  mov     rbx, [rsp+28h+arg_8]
0x18000c11d  add     rsp, 20h
0x18000c121  pop     rdi
0x18000c122  retn
```
