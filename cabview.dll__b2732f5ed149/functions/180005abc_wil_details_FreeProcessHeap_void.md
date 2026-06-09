# wil::details::FreeProcessHeap(void *)

- ea: `0x180005abc`
- end: `0x180005adf`
- name: `?FreeProcessHeap@details@wil@@YAXPEAX@Z`
- size: `35`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `12`
- callee_count: `0`
- tags: ``

## callers

- `0x180004088`
- `0x180004138`
- `0x180004204`
- `0x180004238`
- `0x1800042b8`
- `0x180006e60`
- `0x180006fd0`
- `0x180007ccc`
- `0x180007fe8`
- `0x1800086d0`
- `0x180008fbc`
- `0x180009eec`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005ad8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005ac5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005ac5`

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
0x180005abc  push    rbx
0x180005abe  sub     rsp, 20h
0x180005ac2  mov     rbx, rcx
0x180005ac5  call    cs:__imp_GetProcessHeap
0x180005acb  mov     r8, rbx
0x180005ace  xor     edx, edx
0x180005ad0  mov     rcx, rax
0x180005ad3  add     rsp, 20h
0x180005ad7  pop     rbx
0x180005ad8  jmp     cs:__imp_HeapFree
```
