# std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>::operator!=(std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>> const &)

- ea: `0x180006a98`
- end: `0x180006aa2`
- name: `??9?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@UCommand@@@std@@@std@@@std@@QEBA_NAEBV01@@Z`
- size: `10`
- prototype: `bool __fastcall(_QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000d372`

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
0x180006a98  mov     rax, [rdx]
0x180006a9b  cmp     [rcx], rax
0x180006a9e  setnz   al
0x180006aa1  retn
```
