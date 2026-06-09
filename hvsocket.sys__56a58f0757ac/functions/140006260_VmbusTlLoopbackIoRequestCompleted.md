# VmbusTlLoopbackIoRequestCompleted

- ea: `0x140006260`
- end: `0x14000627e`
- name: `VmbusTlLoopbackIoRequestCompleted`
- size: `30`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140007794`

## pseudocode

```c
__int64 __fastcall VmbusTlLoopbackIoRequestCompleted(__int64 a1, __int64 a2, __int64 a3)
{
  VmbusTlConnectIoRequestCompleted(*(char **)(a3 + 128), (_OWORD *)a3);
  return 3221225494LL;
}

```

## disassembly

```asm
0x140006260  sub     rsp, 28h
0x140006264  mov     rcx, [r8+80h]; P
0x14000626b  mov     rdx, r8; PVOID
0x14000626e  call    VmbusTlConnectIoRequestCompleted
0x140006273  mov     eax, 0C0000016h
0x140006278  add     rsp, 28h
0x14000627c  retn
```
