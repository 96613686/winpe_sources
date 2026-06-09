# BUFFER::FreeMemoryInternal(void)

- ea: `0x180002ff8`
- end: `0x18000301c`
- name: `?FreeMemoryInternal@BUFFER@@AEAAXXZ`
- size: `36`
- prototype: `void __fastcall(BUFFER *__hidden this)`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x180001b90`
- `0x180001d7c`
- `0x18000200c`
- `0x180002330`
- `0x18000260c`
- `0x18000283c`
- `0x180002b90`
- `0x180002d14`
- `0x18000351c`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180003002`
- `KERNEL32!GetProcessHeap` at `0x180003002`
- `KERNEL32!HeapFree` at `0x180003015`

## pseudocode

```c
void __fastcall BUFFER::FreeMemoryInternal(BUFFER *this)
{
  void *v1; // rbx
  HANDLE ProcessHeap; // rax

  v1 = (void *)*((_QWORD *)this + 4);
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, v1);
}

```

## disassembly

```asm
0x180002ff8  push    rbx
0x180002ffa  sub     rsp, 20h
0x180002ffe  mov     rbx, [rcx+20h]
0x180003002  call    cs:__imp_GetProcessHeap
0x180003008  mov     r8, rbx
0x18000300b  xor     edx, edx
0x18000300d  mov     rcx, rax
0x180003010  add     rsp, 20h
0x180003014  pop     rbx
0x180003015  jmp     cs:__imp_HeapFree
```
