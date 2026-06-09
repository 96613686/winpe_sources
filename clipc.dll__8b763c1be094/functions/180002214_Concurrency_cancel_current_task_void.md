# Concurrency::cancel_current_task(void)

- ea: `0x180002214`
- end: `0x180002234`
- name: `?cancel_current_task@Concurrency@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180001bcc`

## callees

- `0x1800020dc`
- `0x1800023b6`

## pseudocode

```c
void __noreturn Concurrency::cancel_current_task(void)
{
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  sub_1800020DC(pExceptionObject);
  throw (std::bad_alloc *)pExceptionObject;
}

```

## disassembly

```asm
0x180002214  sub     rsp, 48h
0x180002218  lea     rcx, [rsp+48h+pExceptionObject]
0x18000221d  call    sub_1800020DC
0x180002222  lea     rdx, __TI2?AVbad_alloc@std@@; pThrowInfo
0x180002229  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000222e  call    _CxxThrowException
```
