# wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)

- ea: `0x1800026d0`
- end: `0x1800026d7`
- name: `??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z`
- size: `7`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x18000289c`
- `0x180004820`
- `0x1800065a0`
- `0x180009e80`

## pseudocode

```c
_QWORD *__fastcall wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
        _QWORD *a1,
        __int64 a2)
{
  *a1 = a2;
  return a1;
}

```

## disassembly

```asm
0x1800026d0  mov     [rcx], rdx
0x1800026d3  mov     rax, rcx
0x1800026d6  retn
```
