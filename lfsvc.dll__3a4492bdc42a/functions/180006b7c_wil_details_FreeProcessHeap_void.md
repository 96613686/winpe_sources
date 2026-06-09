# wil::details::FreeProcessHeap(void *)

- ea: `0x180006b7c`
- end: `0x180006b9f`
- name: `?FreeProcessHeap@details@wil@@YAXPEAX@Z`
- size: `35`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `12`
- callee_count: `0`
- tags: ``

## callers

- `0x180002c7c`
- `0x180002d78`
- `0x180003098`
- `0x180003494`
- `0x180003de8`
- `0x180003ea8`
- `0x180006028`
- `0x1800060b8`
- `0x180007c9c`
- `0x180007df0`
- `0x1800086dc`
- `0x180008ddc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006b85`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006b85`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006b98`

## pseudocode

```c
void __fastcall wil::details::FreeProcessHeap(wil::details *this, void *a2)
{
  HANDLE ProcessHeap; // rax

  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, this);
}

```

## disassembly

```asm
0x180006b7c  push    rbx
0x180006b7e  sub     rsp, 20h
0x180006b82  mov     rbx, rcx
0x180006b85  call    cs:__imp_GetProcessHeap
0x180006b8b  mov     r8, rbx
0x180006b8e  xor     edx, edx
0x180006b90  mov     rcx, rax
0x180006b93  add     rsp, 20h
0x180006b97  pop     rbx
0x180006b98  jmp     cs:__imp_HeapFree
```
