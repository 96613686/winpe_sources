# IISCORE_ASYNC_CONTEXT::SetIoCompletionContext(W3_CONTEXT_BASE *)

- ea: `0x18000164c`
- end: `0x18000168b`
- name: `?SetIoCompletionContext@IISCORE_ASYNC_CONTEXT@@QEAAPEAVW3_CONTEXT_BASE@@PEAV2@@Z`
- size: `63`
- prototype: `struct W3_CONTEXT_BASE *__fastcall(IISCORE_ASYNC_CONTEXT *__hidden this, struct W3_CONTEXT_BASE *)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001b60`
- `0x180004710`
- `0x1800296b0`
- `0x180029ac8`

## callees

- `0x18000164c`

## import_xrefs

- `iisutil!WriteRefTraceLog` at `0x180001675`
- `iisutil!WriteRefTraceLog` at `0x180001675`

## pseudocode

```c
struct W3_CONTEXT_BASE *__fastcall IISCORE_ASYNC_CONTEXT::SetIoCompletionContext(
        IISCORE_ASYNC_CONTEXT *this,
        struct W3_CONTEXT_BASE *a2)
{
  signed __int64 v2; // rbx

  v2 = _InterlockedCompareExchange64((volatile signed __int64 *)this + 2, (signed __int64)a2, 0);
  if ( !v2 )
  {
    _InterlockedIncrement((volatile signed __int32 *)a2 + 19);
    if ( W3_CONTEXT_BASE::sm_pTraceLog )
      WriteRefTraceLog(W3_CONTEXT_BASE::sm_pTraceLog, *((unsigned int *)a2 + 19), a2);
  }
  return (struct W3_CONTEXT_BASE *)v2;
}

```

## disassembly

```asm
0x18000164c  push    rbx
0x18000164e  sub     rsp, 20h
0x180001652  xor     eax, eax
0x180001654  lock cmpxchg [rcx+10h], rdx
0x18000165a  mov     rbx, rax
0x18000165d  jnz     short loc_180001681
0x18000165f  lock inc dword ptr [rdx+4Ch]
0x180001663  mov     rcx, cs:?sm_pTraceLog@W3_CONTEXT_BASE@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * W3_CONTEXT_BASE::sm_pTraceLog
0x18000166a  test    rcx, rcx
0x18000166d  jz      short loc_180001681
0x18000166f  mov     r8, rdx
0x180001672  mov     edx, [rdx+4Ch]
0x180001675  call    cs:__imp_WriteRefTraceLog
0x18000167c  nop     dword ptr [rax+rax+00h]
0x180001681  mov     rax, rbx
0x180001684  add     rsp, 20h
0x180001688  pop     rbx
0x180001689  retn
```
