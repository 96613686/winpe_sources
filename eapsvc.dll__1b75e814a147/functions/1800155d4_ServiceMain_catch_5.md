# ServiceMain$catch$5

- ea: `0x1800155d4`
- end: `0x1800155f2`
- name: `ServiceMain$catch$5`
- size: `30`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## pseudocode

```c
__int64 ServiceMain_catch_5()
{
  return 0;
}

```

## disassembly

```asm
0x1800155d4  mov     [rsp+arg_8], rdx
0x1800155d9  push    rbp
0x1800155da  sub     rsp, 30h
0x1800155de  mov     rbp, rdx
0x1800155e1  mov     rax, 0
0x1800155eb  add     rsp, 30h
0x1800155ef  pop     rbp
0x1800155f0  retn
```
