# wistd::unique_ptr<void,wil::process_heap_deleter>::release(void)

- ea: `0x180008d00`
- end: `0x180008d0b`
- name: `?release@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAPEAXXZ`
- size: `11`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800065dc`

## pseudocode

```c
__int64 __fastcall wistd::unique_ptr<void,wil::process_heap_deleter>::release(__int64 *a1)
{
  __int64 result; // rax

  result = *a1;
  *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x180008d00  mov     rax, [rcx]
0x180008d03  mov     qword ptr [rcx], 0
0x180008d0a  retn
```
