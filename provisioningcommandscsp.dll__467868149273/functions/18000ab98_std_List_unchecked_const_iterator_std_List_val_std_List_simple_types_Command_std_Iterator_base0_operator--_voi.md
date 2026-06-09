# std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<Command>>,std::_Iterator_base0>::operator--(void)

- ea: `0x18000ab98`
- end: `0x18000aba6`
- name: `??F?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@UCommand@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ`
- size: `14`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000da3e`

## pseudocode

```c
__int64 __fastcall std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<Command>>,std::_Iterator_base0>::operator--(
        __int64 a1)
{
  __int64 result; // rax

  result = a1;
  *(_QWORD *)a1 = *(_QWORD *)(*(_QWORD *)a1 + 8LL);
  return result;
}

```

## disassembly

```asm
0x18000ab98  mov     rax, [rcx]
0x18000ab9b  mov     rdx, [rax+8]
0x18000ab9f  mov     rax, rcx
0x18000aba2  mov     [rcx], rdx
0x18000aba5  retn
```
