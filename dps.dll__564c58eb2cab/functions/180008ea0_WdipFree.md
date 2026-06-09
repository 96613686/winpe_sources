# WdipFree

- ea: `0x180008ea0`
- end: `0x180008ec3`
- name: `WdipFree`
- size: `35`
- prototype: `BOOL __fastcall(void *)`
- caller_count: `45`
- callee_count: `0`
- tags: ``

## callers

- `0x180002510`
- `0x180003020`
- `0x1800062a8`
- `0x1800065b8`
- `0x180008328`
- `0x1800086e8`
- `0x18000934c`
- `0x180009660`
- `0x18000b6d8`
- `0x18000b7ec`
- `0x18000c21c`
- `0x18000c9cc`
- `0x18000ce94`
- `0x18000d298`
- `0x18000d880`
- `0x18000dc30`
- `0x18000de94`
- `0x18000e024`
- `0x18000e1b4`
- `0x18000e254`
- `0x18000e334`
- `0x18000e3d4`
- `0x18000e434`
- `0x18000e9d4`
- `0x18000ed8c`
- `0x18000f534`
- `0x180010a00`
- `0x18001116c`
- `0x180011580`
- `0x180011714`
- `0x1800118f0`
- `0x180011c6c`
- `0x180011eec`
- `0x180011fd4`
- `0x18001246c`
- `0x180012cac`
- `0x180013214`
- `0x180013b4c`
- `0x1800146b0`
- `0x1800149dc`
- `0x180014df0`
- `0x1800166f4`
- `0x180016914`
- `0x1800178a8`
- `0x180018680`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008ebc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008ea9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008ea9`

## pseudocode

```c
BOOL __fastcall WdipFree(void *a1)
{
  HANDLE ProcessHeap; // rax

  ProcessHeap = GetProcessHeap();
  return HeapFree(ProcessHeap, 0, a1);
}

```

## disassembly

```asm
0x180008ea0  push    rbx
0x180008ea2  sub     rsp, 20h
0x180008ea6  mov     rbx, rcx
0x180008ea9  call    cs:__imp_GetProcessHeap
0x180008eaf  mov     r8, rbx
0x180008eb2  xor     edx, edx
0x180008eb4  mov     rcx, rax
0x180008eb7  add     rsp, 20h
0x180008ebb  pop     rbx
0x180008ebc  jmp     cs:__imp_HeapFree
```
