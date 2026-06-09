# Concurrency::cancel_current_task(void)

- ea: `0x180001bd0`
- end: `0x180001bf0`
- name: `?cancel_current_task@Concurrency@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180019170`
- `0x1800cbe10`

## callees

- `0x180001ba0`
- `0x1800cdc78`

## pseudocode

```c
void __noreturn Concurrency::cancel_current_task(void)
{
  _BYTE v0[40]; // [rsp+20h] [rbp-28h] BYREF

  sub_180001BA0(v0);
  sub_1800CDC78(v0, &_TI3_AVbad_array_new_length_std__);
  JUMPOUT(0x180001BEFLL);
}

```

## disassembly

```asm
0x180001bd0  sub     rsp, 48h
0x180001bd4  lea     rcx, [rsp+48h+var_28]
0x180001bd9  call    sub_180001BA0
0x180001bde  lea     rdx, __TI3?AVbad_array_new_length@std@@; throw info for 'class std::bad_array_new_length'
0x180001be5  lea     rcx, [rsp+48h+var_28]
0x180001bea  call    sub_1800CDC78
```
