# W3_CONTEXT_BASE::DereferenceW3Context(void)

- ea: `0x180016ad0`
- end: `0x180016b2f`
- name: `?DereferenceW3Context@W3_CONTEXT_BASE@@QEAAXXZ`
- size: `95`
- prototype: `void __fastcall(W3_CONTEXT_BASE *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000eb20`

## callees

- `0x180016ad0`
- `0x18001761c`
- `0x18001ab70`

## import_xrefs

- `iisutil!WriteRefTraceLog` at `0x180016b0a`
- `iisutil!WriteRefTraceLog` at `0x180016b0a`

## pseudocode

```c
void __fastcall W3_CONTEXT_BASE::DereferenceW3Context(W3_CONTEXT_BASE *this)
{
  unsigned __int32 v2; // ebx

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 19);
  if ( W3_CONTEXT_BASE::sm_pTraceLog )
    WriteRefTraceLog(W3_CONTEXT_BASE::sm_pTraceLog, v2, this);
  if ( !v2 )
  {
    if ( this )
    {
      W3_CONTEXT_BASE::~W3_CONTEXT_BASE(this);
      operator delete(this);
    }
  }
}

```

## disassembly

```asm
0x180016ad0  mov     [rsp+arg_0], rbx
0x180016ad5  push    rdi
0x180016ad6  sub     rsp, 20h
0x180016ada  mov     rdi, rcx
0x180016add  mov     ebx, 0FFFFFFFFh
0x180016ae2  lock xadd [rcx+4Ch], ebx
0x180016ae7  mov     rcx, cs:?sm_pTraceLog@W3_CONTEXT_BASE@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * W3_CONTEXT_BASE::sm_pTraceLog
0x180016aee  dec     ebx
0x180016af0  test    rcx, rcx
0x180016af3  jnz     short loc_180016B05
0x180016af5  test    ebx, ebx
0x180016af7  jz      short loc_180016B18
0x180016af9  mov     rbx, [rsp+28h+arg_0]
0x180016afe  add     rsp, 20h
0x180016b02  pop     rdi
0x180016b03  retn
0x180016b05  mov     r8, rdi
0x180016b08  mov     edx, ebx
0x180016b0a  call    cs:__imp_WriteRefTraceLog
0x180016b11  nop     dword ptr [rax+rax+00h]
0x180016b16  jmp     short loc_180016AF5
0x180016b18  test    rdi, rdi
0x180016b1b  jz      short loc_180016AF9
0x180016b1d  mov     rcx, rdi; this
0x180016b20  call    ??1W3_CONTEXT_BASE@@QEAA@XZ; W3_CONTEXT_BASE::~W3_CONTEXT_BASE(void)
0x180016b25  mov     rcx, rdi; Block
0x180016b28  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016b2d  jmp     short loc_180016AF9
```
