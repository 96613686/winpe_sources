# W3_TRACE_LOG::~W3_TRACE_LOG(void)

- ea: `0x180029de0`
- end: `0x180029e0e`
- name: `??1W3_TRACE_LOG@@AEAA@XZ`
- size: `46`
- prototype: `void __fastcall(W3_TRACE_LOG *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180029f70`

## callees

- `0x180002b60`
- `0x180029de0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180029df3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180029df3`

## pseudocode

```c
void __fastcall W3_TRACE_LOG::~W3_TRACE_LOG(W3_TRACE_LOG *this)
{
  if ( *((_DWORD *)this + 14) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    *((_DWORD *)this + 14) = 0;
  }
  BUFFER::~BUFFER((W3_TRACE_LOG *)((char *)this + 72));
}

```

## disassembly

```asm
0x180029de0  push    rbx
0x180029de2  sub     rsp, 20h
0x180029de6  cmp     dword ptr [rcx+38h], 0
0x180029dea  mov     rbx, rcx
0x180029ded  jz      short loc_180029E00
0x180029def  add     rcx, 10h; lpCriticalSection
0x180029df3  call    cs:__imp_DeleteCriticalSection
0x180029df9  mov     dword ptr [rbx+38h], 0
0x180029e00  lea     rcx, [rbx+48h]; this
0x180029e04  add     rsp, 20h
0x180029e08  pop     rbx
0x180029e09  jmp     ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
```
