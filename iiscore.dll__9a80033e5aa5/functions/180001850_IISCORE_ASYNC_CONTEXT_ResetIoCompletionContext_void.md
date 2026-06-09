# IISCORE_ASYNC_CONTEXT::ResetIoCompletionContext(void)

- ea: `0x180001850`
- end: `0x1800018ca`
- name: `?ResetIoCompletionContext@IISCORE_ASYNC_CONTEXT@@QEAAPEAVW3_CONTEXT_BASE@@XZ`
- size: `122`
- prototype: `struct W3_CONTEXT_BASE *__fastcall(IISCORE_ASYNC_CONTEXT *__hidden this)`
- caller_count: `7`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180001640`
- `0x180001acc`
- `0x180004340`
- `0x1800052b0`
- `0x1800274f0`
- `0x180027770`
- `0x1800278e8`

## callees

- `0x180001850`
- `0x180016394`
- `0x180019598`

## import_xrefs

- `iisutil!WriteRefTraceLog` at `0x1800018b0`
- `iisutil!WriteRefTraceLog` at `0x1800018b0`

## pseudocode

```c
struct W3_CONTEXT_BASE *__fastcall IISCORE_ASYNC_CONTEXT::ResetIoCompletionContext(IISCORE_ASYNC_CONTEXT *this)
{
  volatile signed __int32 *v1; // rbx
  unsigned __int32 v3; // edi
  signed __int64 v4; // rdx

  v1 = (volatile signed __int32 *)*((_QWORD *)this + 2);
  if ( v1 )
  {
    v3 = _InterlockedDecrement(v1 + 19);
    if ( W3_CONTEXT_BASE::sm_pTraceLog )
      WriteRefTraceLog(W3_CONTEXT_BASE::sm_pTraceLog, v3, v1);
    if ( !v3 )
    {
      W3_CONTEXT_BASE::~W3_CONTEXT_BASE((W3_CONTEXT_BASE *)v1);
      operator delete((void *)v1);
    }
    v4 = *((_QWORD *)this + 2);
  }
  else
  {
    v4 = 0;
  }
  _InterlockedCompareExchange64((volatile signed __int64 *)this + 2, 0, v4);
  return (struct W3_CONTEXT_BASE *)v4;
}

```

## disassembly

```asm
0x180001850  mov     [rsp+arg_0], rbx
0x180001855  mov     [rsp+arg_8], rsi
0x18000185a  push    rdi
0x18000185b  sub     rsp, 20h
0x18000185f  mov     rbx, [rcx+10h]
0x180001863  mov     rsi, rcx
0x180001866  test    rbx, rbx
0x180001869  jz      short loc_1800018A7
0x18000186b  or      edi, 0FFFFFFFFh
0x18000186e  lock xadd [rbx+4Ch], edi
0x180001873  mov     rcx, cs:?sm_pTraceLog@W3_CONTEXT_BASE@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * W3_CONTEXT_BASE::sm_pTraceLog
0x18000187a  dec     edi
0x18000187c  test    rcx, rcx
0x18000187f  jnz     short loc_1800018AB
0x180001881  test    edi, edi
0x180001883  jz      short loc_1800018B8
0x180001885  mov     rdx, [rsi+10h]
0x180001889  xor     ecx, ecx
0x18000188b  mov     rax, rdx
0x18000188e  lock cmpxchg [rsi+10h], rcx
0x180001894  mov     rbx, [rsp+28h+arg_0]
0x180001899  mov     rax, rdx
0x18000189c  mov     rsi, [rsp+28h+arg_8]
0x1800018a1  add     rsp, 20h
0x1800018a5  pop     rdi
0x1800018a6  retn
0x1800018a7  xor     edx, edx
0x1800018a9  jmp     short loc_180001889
0x1800018ab  mov     r8, rbx
0x1800018ae  mov     edx, edi
0x1800018b0  call    cs:__imp_WriteRefTraceLog
0x1800018b6  jmp     short loc_180001881
0x1800018b8  mov     rcx, rbx; this
0x1800018bb  call    ??1W3_CONTEXT_BASE@@QEAA@XZ; W3_CONTEXT_BASE::~W3_CONTEXT_BASE(void)
0x1800018c0  mov     rcx, rbx; Block
0x1800018c3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800018c8  jmp     short loc_180001885
```
