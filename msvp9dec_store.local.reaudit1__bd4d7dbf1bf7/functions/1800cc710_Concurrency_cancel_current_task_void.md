# Concurrency::cancel_current_task(void)

- ea: `0x1800cc710`
- end: `0x1800cc730`
- name: `?cancel_current_task@Concurrency@@YAXXZ_0`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800cbe10`

## callees

- `0x180020ff4`
- `0x1800cdc78`

## pseudocode

```c
void __noreturn Concurrency::cancel_current_task(void)
{
  _BYTE v0[40]; // [rsp+20h] [rbp-28h] BYREF

  sub_180020FF4(v0);
  sub_1800CDC78(v0, &_TI2_AVbad_alloc_std__);
  JUMPOUT(0x1800CC72FLL);
}

```

## disassembly

```asm
0x1800cc710  sub     rsp, 48h
0x1800cc714  lea     rcx, [rsp+48h+var_28]
0x1800cc719  call    sub_180020FF4
0x1800cc71e  lea     rdx, __TI2?AVbad_alloc@std@@; throw info for 'class std::bad_alloc'
0x1800cc725  lea     rcx, [rsp+48h+var_28]
0x1800cc72a  call    sub_1800CDC78
```
