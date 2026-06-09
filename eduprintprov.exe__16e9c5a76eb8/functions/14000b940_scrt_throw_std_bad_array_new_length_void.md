# __scrt_throw_std_bad_array_new_length(void)

- ea: `0x14000b940`
- end: `0x14000b960`
- name: `?__scrt_throw_std_bad_array_new_length@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x140002630`
- `0x14000452c`
- `0x14000466c`
- `0x14000c318`
- `0x14000cc6c`
- `0x14000e440`
- `0x14000f330`
- `0x14000fa88`

## callees

- `0x14000318c`
- `0x140004be8`

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
0x14000b940  sub     rsp, 48h
0x14000b944  lea     rcx, [rsp+48h+pExceptionObject]; this
0x14000b949  call    ??0bad_array_new_length@std@@QEAA@XZ; std::bad_array_new_length::bad_array_new_length(void)
0x14000b94e  lea     rdx, _TI3?AVbad_array_new_length@std@@; pThrowInfo
0x14000b955  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x14000b95a  call    _CxxThrowException_0
```
