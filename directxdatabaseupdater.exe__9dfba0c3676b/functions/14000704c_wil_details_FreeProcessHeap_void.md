# wil::details::FreeProcessHeap(void *)

- ea: `0x14000704c`
- end: `0x14000706f`
- name: `?FreeProcessHeap@details@wil@@YAXPEAX@Z`
- size: `35`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `12`
- callee_count: `0`
- tags: ``

## callers

- `0x140005fbc`
- `0x14000608c`
- `0x14000611c`
- `0x14000622c`
- `0x1400063ec`
- `0x140008a14`
- `0x140008b78`
- `0x1400099ec`
- `0x140009d04`
- `0x14000a6cc`
- `0x14000cf30`
- `0x14000e538`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007055`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007055`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007068`

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
0x14000704c  push    rbx
0x14000704e  sub     rsp, 20h
0x140007052  mov     rbx, rcx
0x140007055  call    cs:__imp_GetProcessHeap
0x14000705b  mov     r8, rbx
0x14000705e  xor     edx, edx
0x140007060  mov     rcx, rax
0x140007063  add     rsp, 20h
0x140007067  pop     rbx
0x140007068  jmp     cs:__imp_HeapFree
```
