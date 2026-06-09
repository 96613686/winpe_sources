# DeinitThreading

- ea: `0x14001a7bc`
- end: `0x14001a7d2`
- name: `DeinitThreading`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400051f0`

## callees

- `0x14001ae5c`

## pseudocode

```c
void DeinitThreading()
{
  ThreadingInitialized = 0;
  WaitForThreadToDieAndCloseIt();
}

```

## disassembly

```asm
0x14001a7bc  sub     rsp, 28h
0x14001a7c0  mov     cs:ThreadingInitialized, 0
0x14001a7c7  call    WaitForThreadToDieAndCloseIt
0x14001a7cc  add     rsp, 28h
0x14001a7d0  retn
```
