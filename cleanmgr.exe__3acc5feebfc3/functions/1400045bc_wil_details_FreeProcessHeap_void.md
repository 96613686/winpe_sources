# wil::details::FreeProcessHeap(void *)

- ea: `0x1400045bc`
- end: `0x1400045df`
- name: `?FreeProcessHeap@details@wil@@YAXPEAX@Z`
- size: `35`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `13`
- callee_count: `0`
- tags: ``

## callers

- `0x1400040c4`
- `0x140006eac`
- `0x140006f5c`
- `0x140007000`
- `0x140007028`
- `0x14000705c`
- `0x140007118`
- `0x140007dd0`
- `0x140008cd4`
- `0x140008ff8`
- `0x140009520`
- `0x140009920`
- `0x14000a7cc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400045c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400045c5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400045d8`

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
0x1400045bc  push    rbx
0x1400045be  sub     rsp, 20h
0x1400045c2  mov     rbx, rcx
0x1400045c5  call    cs:__imp_GetProcessHeap
0x1400045cb  mov     r8, rbx
0x1400045ce  xor     edx, edx
0x1400045d0  mov     rcx, rax
0x1400045d3  add     rsp, 20h
0x1400045d7  pop     rbx
0x1400045d8  jmp     cs:__imp_HeapFree
```
