# wil::details::FreeProcessHeap(void *)

- ea: `0x180008794`
- end: `0x1800087b7`
- name: `?FreeProcessHeap@details@wil@@YAXPEAX@Z`
- size: `35`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `14`
- callee_count: `0`
- tags: ``

## callers

- `0x180007a60`
- `0x180007b10`
- `0x180007bb4`
- `0x180007c04`
- `0x180007c38`
- `0x180007cf8`
- `0x1800097dc`
- `0x18000990c`
- `0x18000a7d4`
- `0x18000aaec`
- `0x18000b0fc`
- `0x18000b8ec`
- `0x18000caa4`
- `0x180011558`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800087b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000879d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000879d`

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
0x180008794  push    rbx
0x180008796  sub     rsp, 20h
0x18000879a  mov     rbx, rcx
0x18000879d  call    cs:__imp_GetProcessHeap
0x1800087a3  mov     r8, rbx
0x1800087a6  xor     edx, edx
0x1800087a8  mov     rcx, rax
0x1800087ab  add     rsp, 20h
0x1800087af  pop     rbx
0x1800087b0  jmp     cs:__imp_HeapFree
```
