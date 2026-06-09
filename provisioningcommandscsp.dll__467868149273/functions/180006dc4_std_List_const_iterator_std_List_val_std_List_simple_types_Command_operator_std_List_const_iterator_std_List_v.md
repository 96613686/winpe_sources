# std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>::operator!=(std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>> const &)

- ea: `0x180006dc4`
- end: `0x180006dce`
- name: `??9?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@UCommand@@@std@@@std@@@std@@QEBA_NAEBV01@@Z`
- size: `10`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000da3e`

## pseudocode

```c
bool __fastcall std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>::operator!=(
        _QWORD *a1,
        _QWORD *a2)
{
  return *a1 != *a2;
}

```

## disassembly

```asm
0x180006dc4  mov     rax, [rdx]
0x180006dc7  cmp     [rcx], rax
0x180006dca  setnz   al
0x180006dcd  retn
```
