# DAF_user_alloc

- ea: `0x140009060`
- end: `0x140009083`
- name: `DAF_user_alloc`
- size: `35`
- prototype: `LPVOID __fastcall(SIZE_T)`
- caller_count: `36`
- callee_count: `0`
- tags: ``

## callers

- `0x140009468`
- `0x140009850`
- `0x14000a380`
- `0x14000a4f4`
- `0x14000b494`
- `0x14000b5d4`
- `0x14000b994`
- `0x14000be64`
- `0x14000bf80`
- `0x14000c350`
- `0x14000cdac`
- `0x14000d1f0`
- `0x14000deb0`
- `0x14000faa8`
- `0x14000fea4`
- `0x14001211c`
- `0x140014828`
- `0x140014fd8`
- `0x140016900`
- `0x140016d70`
- `0x140017000`
- `0x140017880`
- `0x140017ad0`
- `0x140017d90`
- `0x140018634`
- `0x140018b78`
- `0x1400191ec`
- `0x140019940`
- `0x140019ac8`
- `0x140019b20`
- `0x140019c5c`
- `0x140019e10`
- `0x14001a0e0`
- `0x14001a208`
- `0x14001a3a8`
- `0x14001a494`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000907c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140009069`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140009069`

## pseudocode

```c
LPVOID __fastcall DAF_user_alloc(SIZE_T a1)
{
  HANDLE ProcessHeap; // rax

  ProcessHeap = GetProcessHeap();
  return HeapAlloc(ProcessHeap, 0, a1);
}

```

## disassembly

```asm
0x140009060  push    rbx
0x140009062  sub     rsp, 20h
0x140009066  mov     rbx, rcx
0x140009069  call    cs:__imp_GetProcessHeap
0x14000906f  mov     r8, rbx
0x140009072  xor     edx, edx
0x140009074  mov     rcx, rax
0x140009077  add     rsp, 20h
0x14000907b  pop     rbx
0x14000907c  jmp     cs:__imp_HeapAlloc
```
