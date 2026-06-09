# W3_TRACE_LOG::~W3_TRACE_LOG(void)

- ea: `0x18002bc30`
- end: `0x18002bc64`
- name: `??1W3_TRACE_LOG@@AEAA@XZ`
- size: `52`
- prototype: `void __fastcall(W3_TRACE_LOG *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002bdf0`

## callees

- `0x1800034f0`
- `0x18002bc30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002bc43`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002bc43`

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
0x18002bc30  push    rbx
0x18002bc32  sub     rsp, 20h
0x18002bc36  cmp     dword ptr [rcx+38h], 0
0x18002bc3a  mov     rbx, rcx
0x18002bc3d  jz      short loc_18002BC56
0x18002bc3f  add     rcx, 10h; lpCriticalSection
0x18002bc43  call    cs:__imp_DeleteCriticalSection
0x18002bc4a  nop     dword ptr [rax+rax+00h]
0x18002bc4f  mov     dword ptr [rbx+38h], 0
0x18002bc56  lea     rcx, [rbx+48h]; this
0x18002bc5a  add     rsp, 20h
0x18002bc5e  pop     rbx
0x18002bc5f  jmp     ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
```
