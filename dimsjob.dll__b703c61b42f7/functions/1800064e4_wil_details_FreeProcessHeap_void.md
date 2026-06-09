# wil::details::FreeProcessHeap(void *)

- ea: `0x1800064e4`
- end: `0x180006507`
- name: `?FreeProcessHeap@details@wil@@YAXPEAX@Z`
- size: `35`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `12`
- callee_count: `0`
- tags: ``

## callers

- `0x180003354`
- `0x180003698`
- `0x180003758`
- `0x180003864`
- `0x18000428c`
- `0x180004330`
- `0x180005ae4`
- `0x180005b6c`
- `0x1800075a8`
- `0x1800076cc`
- `0x1800083d8`
- `0x1800089dc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800064ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800064ed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006500`

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
0x1800064e4  push    rbx
0x1800064e6  sub     rsp, 20h
0x1800064ea  mov     rbx, rcx
0x1800064ed  call    cs:__imp_GetProcessHeap
0x1800064f3  mov     r8, rbx
0x1800064f6  xor     edx, edx
0x1800064f8  mov     rcx, rax
0x1800064fb  add     rsp, 20h
0x1800064ff  pop     rbx
0x180006500  jmp     cs:__imp_HeapFree
```
