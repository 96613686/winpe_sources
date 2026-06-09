# W3_FILTER_CONTEXT::ReferenceFilterContext(void)

- ea: `0x18000c614`
- end: `0x18000c641`
- name: `?ReferenceFilterContext@W3_FILTER_CONTEXT@@QEAAXXZ`
- size: `45`
- prototype: `void __fastcall(W3_FILTER_CONTEXT *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b230`

## callees

- `0x18000c614`

## import_xrefs

- `iisutil!WriteRefTraceLog` at `0x18000c636`
- `iisutil!WriteRefTraceLog` at `0x18000c636`

## pseudocode

```c
void __fastcall W3_FILTER_CONTEXT::ReferenceFilterContext(W3_FILTER_CONTEXT *this)
{
  __int64 v1; // rdx

  v1 = (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 3);
  if ( W3_FILTER_CONTEXT::sm_pTraceLog )
    WriteRefTraceLog(W3_FILTER_CONTEXT::sm_pTraceLog, v1, this);
}

```

## disassembly

```asm
0x18000c614  sub     rsp, 28h
0x18000c618  mov     edx, 1
0x18000c61d  lock xadd [rcx+0Ch], edx
0x18000c622  mov     rax, cs:?sm_pTraceLog@W3_FILTER_CONTEXT@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * W3_FILTER_CONTEXT::sm_pTraceLog
0x18000c629  inc     edx
0x18000c62b  test    rax, rax
0x18000c62e  jz      short loc_18000C63C
0x18000c630  mov     r8, rcx
0x18000c633  mov     rcx, rax
0x18000c636  call    cs:__imp_WriteRefTraceLog
0x18000c63c  add     rsp, 28h
0x18000c640  retn
```
