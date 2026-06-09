# wil::details::FreeProcessHeap(void *)

- ea: `0x18001fe7c`
- end: `0x18001fe9f`
- name: `?FreeProcessHeap@details@wil@@YAXPEAX@Z`
- size: `35`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `14`
- callee_count: `0`
- tags: ``

## callers

- `0x18000fae4`
- `0x18000fbdc`
- `0x18000fc7c`
- `0x1800117f8`
- `0x180011c80`
- `0x1800122d4`
- `0x180013620`
- `0x1800136c4`
- `0x18001f168`
- `0x18001f1fc`
- `0x180020d6c`
- `0x180020e98`
- `0x180021754`
- `0x180021d5c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fe85`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fe85`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001fe98`

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
0x18001fe7c  push    rbx
0x18001fe7e  sub     rsp, 20h
0x18001fe82  mov     rbx, rcx
0x18001fe85  call    cs:__imp_GetProcessHeap
0x18001fe8b  mov     r8, rbx
0x18001fe8e  xor     edx, edx
0x18001fe90  mov     rcx, rax
0x18001fe93  add     rsp, 20h
0x18001fe97  pop     rbx
0x18001fe98  jmp     cs:__imp_HeapFree
```
