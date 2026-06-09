# std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>::operator++(void)

- ea: `0x14000845c`
- end: `0x140008469`
- name: `??E?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@UCommand@@@std@@@std@@@std@@QEAAAEAV01@XZ`
- size: `13`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x14000abca`

## pseudocode

```c
_QWORD **__fastcall std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>::operator++(
        _QWORD **a1)
{
  _QWORD **result; // rax

  result = a1;
  *a1 = (_QWORD *)**a1;
  return result;
}

```

## disassembly

```asm
0x14000845c  mov     rax, [rcx]
0x14000845f  mov     rdx, [rax]
0x140008462  mov     rax, rcx
0x140008465  mov     [rcx], rdx
0x140008468  retn
```
