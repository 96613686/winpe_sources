# _update_thread_multibyte_data_internal_::_1_::fin$0

- ea: `0x180025c5c`
- end: `0x180025c75`
- name: `_update_thread_multibyte_data_internal_::_1_::fin$0`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1800160d4`

## pseudocode

```c
__int64 update_thread_multibyte_data_internal_::_1_::fin_0()
{
  return _acrt_unlock(5);
}

```

## disassembly

```asm
0x180025c5c  push    rbp
0x180025c5e  sub     rsp, 20h
0x180025c62  mov     rbp, rdx
0x180025c65  mov     ecx, 5
0x180025c6a  add     rsp, 20h
0x180025c6e  pop     rbp
0x180025c6f  jmp     __acrt_unlock
```
