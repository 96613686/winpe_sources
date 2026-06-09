# wil::details::FreeProcessHeap(void *)

- ea: `0x18000563c`
- end: `0x18000565f`
- name: `?FreeProcessHeap@details@wil@@YAXPEAX@Z`
- size: `35`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `12`
- callee_count: `0`
- tags: ``

## callers

- `0x180004878`
- `0x1800049d4`
- `0x180004a84`
- `0x180004b50`
- `0x180004b84`
- `0x180004c04`
- `0x18000672c`
- `0x180007240`
- `0x180007520`
- `0x180007b6c`
- `0x180008228`
- `0x180008d14`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005645`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005645`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005658`

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
0x18000563c  push    rbx
0x18000563e  sub     rsp, 20h
0x180005642  mov     rbx, rcx
0x180005645  call    cs:__imp_GetProcessHeap
0x18000564b  mov     r8, rbx
0x18000564e  xor     edx, edx
0x180005650  mov     rcx, rax
0x180005653  add     rsp, 20h
0x180005657  pop     rbx
0x180005658  jmp     cs:__imp_HeapFree
```
