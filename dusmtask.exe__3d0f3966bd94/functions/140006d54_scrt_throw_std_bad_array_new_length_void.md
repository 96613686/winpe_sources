# __scrt_throw_std_bad_array_new_length(void)

- ea: `0x140006d54`
- end: `0x140006d74`
- name: `?__scrt_throw_std_bad_array_new_length@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140001494`
- `0x14000311c`
- `0x1400032b8`
- `0x140003438`
- `0x14000356c`

## callees

- `0x140001f1a`
- `0x14000396c`

## pseudocode

```c
void __noreturn __scrt_throw_std_bad_array_new_length(void)
{
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  std::bad_array_new_length::bad_array_new_length((std::bad_array_new_length *)pExceptionObject);
  throw (std::bad_array_new_length *)pExceptionObject;
}

```

## disassembly

```asm
0x140006d54  sub     rsp, 48h
0x140006d58  lea     rcx, [rsp+48h+pExceptionObject]; this
0x140006d5d  call    ??0bad_array_new_length@std@@QEAA@XZ; std::bad_array_new_length::bad_array_new_length(void)
0x140006d62  lea     rdx, _TI3?AVbad_array_new_length@std@@; pThrowInfo
0x140006d69  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x140006d6e  call    _CxxThrowException_0
```
