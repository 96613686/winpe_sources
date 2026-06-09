# FCGI_BUFFER::~FCGI_BUFFER(void)

- ea: `0x180008f50`
- end: `0x180008f87`
- name: `??1FCGI_BUFFER@@AEAA@XZ`
- size: `55`
- prototype: `void __fastcall(FCGI_BUFFER *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180008f90`
- `0x180009128`
- `0x1800092d4`

## callees

- `0x180008f50`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008f74`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008f74`

## pseudocode

```c
void __fastcall FCGI_BUFFER::~FCGI_BUFFER(FCGI_BUFFER *this)
{
  void *v2; // r8

  if ( *(_QWORD *)this )
  {
    v2 = (void *)(*(_QWORD *)this - 8LL);
    *(_QWORD *)this = v2;
    HeapFree(FCGI_BUFFER::sm_hHeap, 1u, v2);
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x180008f50  push    rbx
0x180008f52  sub     rsp, 20h
0x180008f56  mov     r8, [rcx]
0x180008f59  mov     rbx, rcx
0x180008f5c  test    r8, r8
0x180008f5f  jz      short loc_180008F81
0x180008f61  add     r8, 0FFFFFFFFFFFFFFF8h; lpMem
0x180008f65  mov     edx, 1; dwFlags
0x180008f6a  mov     [rcx], r8
0x180008f6d  mov     rcx, cs:?sm_hHeap@FCGI_BUFFER@@0PEAXEA; hHeap
0x180008f74  call    cs:__imp_HeapFree
0x180008f7a  mov     qword ptr [rbx], 0
0x180008f81  add     rsp, 20h
0x180008f85  pop     rbx
0x180008f86  retn
```
