# DeleteCustomFormat

- ea: `0x18000e08c`
- end: `0x18000e0bc`
- name: `DeleteCustomFormat`
- size: `48`
- prototype: `__int64 __fastcall(LPCVOID pMem)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180008964`
- `0x180010b68`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000e0b5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000e095`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000e0a7`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000e095`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000e0a7`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000e09e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000e09e`

## pseudocode

```c
HGLOBAL __fastcall DeleteCustomFormat(LPCVOID pMem)
{
  HGLOBAL v2; // rax
  HGLOBAL v3; // rax

  v2 = GlobalHandle(pMem);
  GlobalUnlock(v2);
  v3 = GlobalHandle(pMem);
  return GlobalFree(v3);
}

```

## disassembly

```asm
0x18000e08c  push    rbx
0x18000e08e  sub     rsp, 20h
0x18000e092  mov     rbx, rcx
0x18000e095  call    cs:__imp_GlobalHandle
0x18000e09b  mov     rcx, rax; hMem
0x18000e09e  call    cs:__imp_GlobalUnlock
0x18000e0a4  mov     rcx, rbx; pMem
0x18000e0a7  call    cs:__imp_GlobalHandle
0x18000e0ad  mov     rcx, rax
0x18000e0b0  add     rsp, 20h
0x18000e0b4  pop     rbx
0x18000e0b5  jmp     cs:__imp_GlobalFree
```
