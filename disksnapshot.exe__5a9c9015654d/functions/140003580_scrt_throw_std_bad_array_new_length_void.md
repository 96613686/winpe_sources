# __scrt_throw_std_bad_array_new_length(void)

- ea: `0x140003580`
- end: `0x1400035a0`
- name: `?__scrt_throw_std_bad_array_new_length@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x140001c74`
- `0x140002c84`
- `0x140002d90`
- `0x140004dc8`
- `0x140004fec`
- `0x1400052b0`
- `0x14000ae5c`
- `0x14000c310`

## callees

- `0x14000280e`
- `0x140002f58`

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
0x140003580  sub     rsp, 48h
0x140003584  lea     rcx, [rsp+48h+pExceptionObject]; this
0x140003589  call    ??0bad_array_new_length@std@@QEAA@XZ; std::bad_array_new_length::bad_array_new_length(void)
0x14000358e  lea     rdx, _TI3?AVbad_array_new_length@std@@; pThrowInfo
0x140003595  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x14000359a  call    _CxxThrowException_0
```
