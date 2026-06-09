# std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>::operator++(void)

- ea: `0x180006dd8`
- end: `0x180006de5`
- name: `??E?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@UCommand@@@std@@@std@@@std@@QEAAAEAV01@XZ`
- size: `13`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000da3e`

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
0x180006dd8  mov     rax, [rcx]
0x180006ddb  mov     rdx, [rax]
0x180006dde  mov     rax, rcx
0x180006de1  mov     [rcx], rdx
0x180006de4  retn
```
