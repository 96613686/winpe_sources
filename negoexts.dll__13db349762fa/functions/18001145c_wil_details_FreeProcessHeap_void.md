# wil::details::FreeProcessHeap(void *)

- ea: `0x18001145c`
- end: `0x18001147f`
- name: `?FreeProcessHeap@details@wil@@YAXPEAX@Z`
- size: `35`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `12`
- callee_count: `0`
- tags: ``

## callers

- `0x18000dc48`
- `0x18000df88`
- `0x18000e048`
- `0x18000e154`
- `0x18000e244`
- `0x18000f0c8`
- `0x18000f16c`
- `0x180010a6c`
- `0x1800129bc`
- `0x180012ae0`
- `0x180013530`
- `0x180013ecc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011478`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011465`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011465`

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
0x18001145c  push    rbx
0x18001145e  sub     rsp, 20h
0x180011462  mov     rbx, rcx
0x180011465  call    cs:__imp_GetProcessHeap
0x18001146b  mov     r8, rbx
0x18001146e  xor     edx, edx
0x180011470  mov     rcx, rax
0x180011473  add     rsp, 20h
0x180011477  pop     rbx
0x180011478  jmp     cs:__imp_HeapFree
```
