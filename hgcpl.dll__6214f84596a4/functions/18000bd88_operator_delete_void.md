# operator delete(void *)

- ea: `0x18000bd88`
- end: `0x18000bdaf`
- name: `??3@YAXPEAX@Z`
- size: `39`
- prototype: `void __fastcall(void *lpMem)`
- caller_count: `26`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002970`
- `0x180007010`
- `0x1800072a0`
- `0x1800072cc`
- `0x180007300`
- `0x180007340`
- `0x180007370`
- `0x18000abc8`
- `0x18000af78`
- `0x18000afcc`
- `0x18000b300`
- `0x18000b3b0`
- `0x18000bdc0`
- `0x18000be00`
- `0x18000bedc`
- `0x18000c894`
- `0x18000dedc`
- `0x18000eb70`
- `0x18000ebb0`
- `0x18000f110`
- `0x18000f150`
- `0x18000f1b0`
- `0x1800102c0`
- `0x1800132a0`
- `0x180016650`
- `0x180017a40`

## callees

- `0x18000bd88`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bda3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bda3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bd95`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bd95`

## pseudocode

```c
void __fastcall operator delete(void *lpMem)
{
  HANDLE ProcessHeap; // rax

  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpMem);
  }
}

```

## disassembly

```asm
0x18000bd88  test    rcx, rcx
0x18000bd8b  jz      short locret_18000BDAE
0x18000bd8d  push    rbx
0x18000bd8e  sub     rsp, 20h
0x18000bd92  mov     rbx, rcx
0x18000bd95  call    cs:__imp_GetProcessHeap
0x18000bd9b  mov     r8, rbx; lpMem
0x18000bd9e  xor     edx, edx; dwFlags
0x18000bda0  mov     rcx, rax; hHeap
0x18000bda3  call    cs:__imp_HeapFree
0x18000bda9  add     rsp, 20h
0x18000bdad  pop     rbx
0x18000bdae  retn
```
