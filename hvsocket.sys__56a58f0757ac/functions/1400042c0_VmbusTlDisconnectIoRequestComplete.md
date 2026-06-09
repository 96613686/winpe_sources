# VmbusTlDisconnectIoRequestComplete

- ea: `0x1400042c0`
- end: `0x1400042c8`
- name: `VmbusTlDisconnectIoRequestComplete`
- size: `8`
- prototype: `void __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
void __fastcall VmbusTlDisconnectIoRequestComplete(__int64 a1, __int64 a2, __int64 a3)
{
  *(_QWORD *)(a1 + 600) = a3;
}

```

## disassembly

```asm
0x1400042c0  mov     [rcx+258h], r8
0x1400042c7  retn
```
