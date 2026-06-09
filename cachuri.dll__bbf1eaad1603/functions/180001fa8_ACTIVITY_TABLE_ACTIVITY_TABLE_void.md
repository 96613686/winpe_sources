# ACTIVITY_TABLE::~ACTIVITY_TABLE(void)

- ea: `0x180001fa8`
- end: `0x180001fd0`
- name: `??1ACTIVITY_TABLE@@QEAA@XZ`
- size: `40`
- prototype: `void __fastcall(ACTIVITY_TABLE *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001bf8`

## callees

- `0x180001fa8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001fb6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001fb6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001fc4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001fc4`

## pseudocode

```c
void __fastcall ACTIVITY_TABLE::~ACTIVITY_TABLE(void **this)
{
  void *v1; // rbx
  HANDLE ProcessHeap; // rax

  v1 = *this;
  if ( *this )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v1);
  }
}

```

## disassembly

```asm
0x180001fa8  push    rbx
0x180001faa  sub     rsp, 20h
0x180001fae  mov     rbx, [rcx]
0x180001fb1  test    rbx, rbx
0x180001fb4  jz      short loc_180001FCA
0x180001fb6  call    cs:__imp_GetProcessHeap
0x180001fbc  mov     r8, rbx; lpMem
0x180001fbf  xor     edx, edx; dwFlags
0x180001fc1  mov     rcx, rax; hHeap
0x180001fc4  call    cs:__imp_HeapFree
0x180001fca  add     rsp, 20h
0x180001fce  pop     rbx
0x180001fcf  retn
```
