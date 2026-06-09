# ISAPI_CONTEXT::Terminate(void)

- ea: `0x180005fc8`
- end: `0x180005fee`
- name: `?Terminate@ISAPI_CONTEXT@@SAXXZ`
- size: `38`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001f2c`
- `0x1800032c0`

## callees

- `0x180005fc8`

## import_xrefs

- `iisutil!DestroyRefTraceLog` at `0x180005fd8`
- `iisutil!DestroyRefTraceLog` at `0x180005fd8`

## pseudocode

```c
void ISAPI_CONTEXT::Terminate(void)
{
  if ( ISAPI_CONTEXT::sm_pTraceLog )
  {
    DestroyRefTraceLog();
    ISAPI_CONTEXT::sm_pTraceLog = 0;
  }
}

```

## disassembly

```asm
0x180005fc8  sub     rsp, 28h
0x180005fcc  mov     rcx, cs:?sm_pTraceLog@ISAPI_CONTEXT@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * ISAPI_CONTEXT::sm_pTraceLog
0x180005fd3  test    rcx, rcx
0x180005fd6  jz      short loc_180005FE9
0x180005fd8  call    cs:__imp_DestroyRefTraceLog
0x180005fde  mov     cs:?sm_pTraceLog@ISAPI_CONTEXT@@0PEAU_TRACE_LOG@@EA, 0; _TRACE_LOG * ISAPI_CONTEXT::sm_pTraceLog
0x180005fe9  add     rsp, 28h
0x180005fed  retn
```
