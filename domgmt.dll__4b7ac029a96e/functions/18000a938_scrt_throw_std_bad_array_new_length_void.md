# __scrt_throw_std_bad_array_new_length(void)

- ea: `0x18000a938`
- end: `0x18000a958`
- name: `?__scrt_throw_std_bad_array_new_length@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x180001fb8`
- `0x18000739c`
- `0x180007414`
- `0x180007834`
- `0x180007ae8`
- `0x180007c50`
- `0x180007ec0`
- `0x1800081ec`

## callees

- `0x180002990`
- `0x1800088d0`

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
0x18000a938  sub     rsp, 48h
0x18000a93c  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18000a941  call    ??0bad_array_new_length@std@@QEAA@XZ
0x18000a946  lea     rdx, _TI3?AVbad_array_new_length@std@@; pThrowInfo
0x18000a94d  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000a952  call    _CxxThrowException_0
```
