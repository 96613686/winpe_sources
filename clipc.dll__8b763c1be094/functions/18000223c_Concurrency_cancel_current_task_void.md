# Concurrency::cancel_current_task(void)

- ea: `0x18000223c`
- end: `0x18000225c`
- name: `?cancel_current_task@Concurrency@@YAXXZ_0`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180001bcc`

## callees

- `0x180002148`
- `0x1800023b6`

## pseudocode

```c
void __noreturn Concurrency::cancel_current_task(void)
{
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  sub_180002148(pExceptionObject);
  throw (std::bad_array_new_length *)pExceptionObject;
}

```

## disassembly

```asm
0x18000223c  sub     rsp, 48h
0x180002240  lea     rcx, [rsp+48h+pExceptionObject]
0x180002245  call    sub_180002148
0x18000224a  lea     rdx, __TI3?AVbad_array_new_length@std@@; pThrowInfo
0x180002251  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180002256  call    _CxxThrowException
```
