# __acrt_update_thread_multibyte_data

- ea: `0x180016dcc`
- end: `0x180016de8`
- name: `__acrt_update_thread_multibyte_data`
- size: `28`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1800176c0`
- `0x1800176f8`

## callees

- `0x1800153dc`
- `0x180016cb4`

## pseudocode

```c
__int64 *_acrt_update_thread_multibyte_data()
{
  __int64 v0; // rax

  v0 = _acrt_getptd();
  return update_thread_multibyte_data_internal(v0, (void **)&_acrt_current_multibyte_data);
}

```

## disassembly

```asm
0x180016dcc  sub     rsp, 28h
0x180016dd0  call    __acrt_getptd
0x180016dd5  lea     rdx, __acrt_current_multibyte_data
0x180016ddc  mov     rcx, rax
0x180016ddf  add     rsp, 28h
0x180016de3  jmp     update_thread_multibyte_data_internal
```
