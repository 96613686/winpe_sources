# wil::details::FreeProcessHeap(void *)

- ea: `0x1800041b8`
- end: `0x1800041db`
- name: `?FreeProcessHeap@details@wil@@YAXPEAX@Z`
- size: `35`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `13`
- callee_count: `0`
- tags: ``

## callers

- `0x180002bc8`
- `0x180002f80`
- `0x180003160`
- `0x180003224`
- `0x18000324c`
- `0x1800032ec`
- `0x1800035c4`
- `0x1800038b4`
- `0x1800041e4`
- `0x180004218`
- `0x18000a9b8`
- `0x18000d32c`
- `0x18000d450`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800041d4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800041c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800041c1`

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
0x1800041b8  push    rbx
0x1800041ba  sub     rsp, 20h
0x1800041be  mov     rbx, rcx
0x1800041c1  call    cs:__imp_GetProcessHeap
0x1800041c7  mov     r8, rbx
0x1800041ca  xor     edx, edx
0x1800041cc  mov     rcx, rax
0x1800041cf  add     rsp, 20h
0x1800041d3  pop     rbx
0x1800041d4  jmp     cs:__imp_HeapFree
```
