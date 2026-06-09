# SmartPtr<CWorkerThread>::SmartPtr<CWorkerThread>(CWorkerThread *)

- ea: `0x18000b1cc`
- end: `0x18000b1df`
- name: `??0?$SmartPtr@VCWorkerThread@@@@QEAA@PEAVCWorkerThread@@@Z`
- size: `19`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x18000a360`
- `0x18000ac48`
- `0x18000ed14`

## pseudocode

```c
_QWORD *__fastcall SmartPtr<CWorkerThread>::SmartPtr<CWorkerThread>(_QWORD *a1)
{
  *a1 = 0;
  return a1;
}

```

## disassembly

```asm
0x18000b1cc  sub     rsp, 28h
0x18000b1d0  mov     qword ptr [rcx], 0
0x18000b1d7  mov     rax, rcx
0x18000b1da  add     rsp, 28h
0x18000b1de  retn
```
