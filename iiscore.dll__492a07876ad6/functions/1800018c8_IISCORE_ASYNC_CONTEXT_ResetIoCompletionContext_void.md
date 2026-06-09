# IISCORE_ASYNC_CONTEXT::ResetIoCompletionContext(void)

- ea: `0x1800018c8`
- end: `0x180001949`
- name: `?ResetIoCompletionContext@IISCORE_ASYNC_CONTEXT@@QEAAPEAVW3_CONTEXT_BASE@@XZ`
- size: `129`
- prototype: `struct W3_CONTEXT_BASE *__fastcall(IISCORE_ASYNC_CONTEXT *__hidden this)`
- caller_count: `7`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800016a0`
- `0x180001b60`
- `0x180004710`
- `0x180005700`
- `0x1800296b0`
- `0x180029930`
- `0x180029ac8`

## callees

- `0x1800018c8`
- `0x18001761c`
- `0x18001ab70`

## import_xrefs

- `iisutil!WriteRefTraceLog` at `0x180001929`
- `iisutil!WriteRefTraceLog` at `0x180001929`

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
0x1800018c8  mov     [rsp+arg_0], rbx
0x1800018cd  mov     [rsp+arg_8], rsi
0x1800018d2  push    rdi
0x1800018d3  sub     rsp, 20h
0x1800018d7  mov     rbx, [rcx+10h]
0x1800018db  mov     rsi, rcx
0x1800018de  test    rbx, rbx
0x1800018e1  jz      short loc_180001920
0x1800018e3  or      edi, 0FFFFFFFFh
0x1800018e6  lock xadd [rbx+4Ch], edi
0x1800018eb  mov     rcx, cs:?sm_pTraceLog@W3_CONTEXT_BASE@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * W3_CONTEXT_BASE::sm_pTraceLog
0x1800018f2  dec     edi
0x1800018f4  test    rcx, rcx
0x1800018f7  jnz     short loc_180001924
0x1800018f9  test    edi, edi
0x1800018fb  jz      short loc_180001937
0x1800018fd  mov     rdx, [rsi+10h]
0x180001901  xor     ecx, ecx
0x180001903  mov     rax, rdx
0x180001906  lock cmpxchg [rsi+10h], rcx
0x18000190c  mov     rbx, [rsp+28h+arg_0]
0x180001911  mov     rax, rdx
0x180001914  mov     rsi, [rsp+28h+arg_8]
0x180001919  add     rsp, 20h
0x18000191d  pop     rdi
0x18000191e  retn
0x180001920  xor     edx, edx
0x180001922  jmp     short loc_180001901
0x180001924  mov     r8, rbx
0x180001927  mov     edx, edi
0x180001929  call    cs:__imp_WriteRefTraceLog
0x180001930  nop     dword ptr [rax+rax+00h]
0x180001935  jmp     short loc_1800018F9
0x180001937  mov     rcx, rbx; this
0x18000193a  call    ??1W3_CONTEXT_BASE@@QEAA@XZ; W3_CONTEXT_BASE::~W3_CONTEXT_BASE(void)
0x18000193f  mov     rcx, rbx; Block
0x180001942  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001947  jmp     short loc_1800018FD
```
