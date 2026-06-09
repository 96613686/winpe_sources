# std::_List_alloc<0,std::_List_base_types<Command,std::allocator<Command>>>::_Buynode0(std::_List_node<Command,void *> *,std::_List_node<Command,void *> *)

- ea: `0x180007a08`
- end: `0x180007a5c`
- name: `?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@UCommand@@V?$allocator@UCommand@@@std@@@std@@@std@@QEAAPEAU?$_List_node@UCommand@@PEAX@2@PEAU32@0@Z`
- size: `84`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006a70`
- `0x18000a3e0`
- `0x18000a418`
- `0x18000a990`
- `0x18000c47c`

## callees

- `0x1800016b4`
- `0x180007a08`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x180007a31`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x180007a31`

## pseudocode

```c
void __fastcall std::_List_alloc<0,std::_List_base_types<Command>>::_Buynode0(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  _QWORD *v5; // rax
  __int64 v6; // rcx
  _QWORD *v7; // [rsp+30h] [rbp+8h]

  v5 = operator new(0x80u);
  v7 = v5;
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
  try
  {
    *v5 = a2;
    v5[1] = a3;
  }
  catch ( ... )
  {
    std::_Wrap_alloc<std::allocator<unsigned short>>::deallocate(v6, v7);
    throw;
  }
}

```

## disassembly

```asm
0x180007a08  mov     [rsp+arg_8], rbx
0x180007a0d  mov     [rsp+arg_0], rcx
0x180007a12  push    rdi
0x180007a13  sub     rsp, 20h
0x180007a17  mov     rdi, r8
0x180007a1a  mov     rbx, rdx
0x180007a1d  mov     ecx, 80h; Size
0x180007a22  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007a27  mov     [rsp+28h+arg_0], rax
0x180007a2c  test    rax, rax
0x180007a2f  jnz     short loc_180007A3E
0x180007a31  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180007a38  nop     dword ptr [rax+rax+00h]
0x180007a3d  int     3; Trap to Debugger
0x180007a3e  test    rbx, rbx
0x180007a41  jnz     short loc_180007A49
0x180007a43  mov     rbx, rax
0x180007a46  mov     rdi, rax
0x180007a49  mov     [rax], rbx
0x180007a4c  mov     [rax+8], rdi
0x180007a50  mov     rbx, [rsp+28h+arg_8]
0x180007a55  add     rsp, 20h
0x180007a59  pop     rdi
0x180007a5a  retn
```
