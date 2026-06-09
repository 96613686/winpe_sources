# PortSetIoCompletionPort

- ea: `0x180014770`
- end: `0x18001477a`
- name: `PortSetIoCompletionPort`
- size: `10`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall PortSetIoCompletionPort(void *a1)
{
  g_hIoCompletionPort = a1;
  return 0;
}

```

## disassembly

```asm
0x180014770  mov     cs:g_hIoCompletionPort, rcx
0x180014777  xor     eax, eax
0x180014779  retn
```
