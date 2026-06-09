# IISCORE_ASYNC_CONTEXT::SetIoCompletionContext(W3_CONTEXT_BASE *)

- ea: `0x1800015f8`
- end: `0x180001630`
- name: `?SetIoCompletionContext@IISCORE_ASYNC_CONTEXT@@QEAAPEAVW3_CONTEXT_BASE@@PEAV2@@Z`
- size: `56`
- prototype: `struct W3_CONTEXT_BASE *__fastcall(IISCORE_ASYNC_CONTEXT *__hidden this, struct W3_CONTEXT_BASE *)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001acc`
- `0x180004340`
- `0x1800274f0`
- `0x1800278e8`

## callees

- `0x1800015f8`

## import_xrefs

- `iisutil!WriteRefTraceLog` at `0x180001621`
- `iisutil!WriteRefTraceLog` at `0x180001621`

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
0x1800015f8  push    rbx
0x1800015fa  sub     rsp, 20h
0x1800015fe  xor     eax, eax
0x180001600  lock cmpxchg [rcx+10h], rdx
0x180001606  mov     rbx, rax
0x180001609  jnz     short loc_180001627
0x18000160b  lock inc dword ptr [rdx+4Ch]
0x18000160f  mov     rcx, cs:?sm_pTraceLog@W3_CONTEXT_BASE@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * W3_CONTEXT_BASE::sm_pTraceLog
0x180001616  test    rcx, rcx
0x180001619  jz      short loc_180001627
0x18000161b  mov     r8, rdx
0x18000161e  mov     edx, [rdx+4Ch]
0x180001621  call    cs:__imp_WriteRefTraceLog
0x180001627  mov     rax, rbx
0x18000162a  add     rsp, 20h
0x18000162e  pop     rbx
0x18000162f  retn
```
