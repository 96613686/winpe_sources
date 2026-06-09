# ISAPI_CONTEXT::ReferenceIsapiContext(void)

- ea: `0x180005f90`
- end: `0x180005fc0`
- name: `?ReferenceIsapiContext@ISAPI_CONTEXT@@QEAAXXZ`
- size: `48`
- prototype: `void __fastcall(ISAPI_CONTEXT *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180003744`
- `0x1800038ec`
- `0x180003ef0`
- `0x180005ff4`

## callees

- `0x180005f90`

## import_xrefs

- `iisutil!WriteRefTraceLog` at `0x180005fb5`
- `iisutil!WriteRefTraceLog` at `0x180005fb5`

## pseudocode

```c
void __fastcall ISAPI_CONTEXT::ReferenceIsapiContext(ISAPI_CONTEXT *this)
{
  __int64 v1; // rdx

  v1 = (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 65);
  if ( ISAPI_CONTEXT::sm_pTraceLog )
    WriteRefTraceLog(ISAPI_CONTEXT::sm_pTraceLog, v1, this);
}

```

## disassembly

```asm
0x180005f90  sub     rsp, 28h
0x180005f94  mov     edx, 1
0x180005f99  lock xadd [rcx+104h], edx
0x180005fa1  mov     rax, cs:?sm_pTraceLog@ISAPI_CONTEXT@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * ISAPI_CONTEXT::sm_pTraceLog
0x180005fa8  inc     edx
0x180005faa  test    rax, rax
0x180005fad  jz      short loc_180005FBB
0x180005faf  mov     r8, rcx
0x180005fb2  mov     rcx, rax
0x180005fb5  call    cs:__imp_WriteRefTraceLog
0x180005fbb  add     rsp, 28h
0x180005fbf  retn
```
