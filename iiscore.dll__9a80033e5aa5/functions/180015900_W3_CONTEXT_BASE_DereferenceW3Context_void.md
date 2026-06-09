# W3_CONTEXT_BASE::DereferenceW3Context(void)

- ea: `0x180015900`
- end: `0x180015958`
- name: `?DereferenceW3Context@W3_CONTEXT_BASE@@QEAAXXZ`
- size: `88`
- prototype: `void __fastcall(W3_CONTEXT_BASE *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000df90`

## callees

- `0x180015900`
- `0x180016394`
- `0x180019598`

## import_xrefs

- `iisutil!WriteRefTraceLog` at `0x180015939`
- `iisutil!WriteRefTraceLog` at `0x180015939`

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
0x180015900  mov     [rsp+arg_0], rbx
0x180015905  push    rdi
0x180015906  sub     rsp, 20h
0x18001590a  mov     rdi, rcx
0x18001590d  mov     ebx, 0FFFFFFFFh
0x180015912  lock xadd [rcx+4Ch], ebx
0x180015917  mov     rcx, cs:?sm_pTraceLog@W3_CONTEXT_BASE@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * W3_CONTEXT_BASE::sm_pTraceLog
0x18001591e  dec     ebx
0x180015920  test    rcx, rcx
0x180015923  jnz     short loc_180015934
0x180015925  test    ebx, ebx
0x180015927  jz      short loc_180015941
0x180015929  mov     rbx, [rsp+28h+arg_0]
0x18001592e  add     rsp, 20h
0x180015932  pop     rdi
0x180015933  retn
0x180015934  mov     r8, rdi
0x180015937  mov     edx, ebx
0x180015939  call    cs:__imp_WriteRefTraceLog
0x18001593f  jmp     short loc_180015925
0x180015941  test    rdi, rdi
0x180015944  jz      short loc_180015929
0x180015946  mov     rcx, rdi; this
0x180015949  call    ??1W3_CONTEXT_BASE@@QEAA@XZ; W3_CONTEXT_BASE::~W3_CONTEXT_BASE(void)
0x18001594e  mov     rcx, rdi; Block
0x180015951  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180015956  jmp     short loc_180015929
```
