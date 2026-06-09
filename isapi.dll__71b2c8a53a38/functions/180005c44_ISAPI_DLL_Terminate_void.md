# ISAPI_DLL::Terminate(void)

- ea: `0x180005c44`
- end: `0x180005c86`
- name: `?Terminate@ISAPI_DLL@@SAXXZ`
- size: `66`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800032c0`

## callees

- `0x1800050d4`
- `0x180005c44`

## import_xrefs

- `iisutil!DestroyRefTraceLog` at `0x180005c70`
- `iisutil!DestroyRefTraceLog` at `0x180005c70`

## pseudocode

```c
void ISAPI_DLL::Terminate(void)
{
  if ( ISAPI_DLL::sm_pachIsapiDlls )
  {
    ALLOC_CACHE_HANDLER::`scalar deleting destructor'(ISAPI_DLL::sm_pachIsapiDlls);
    ISAPI_DLL::sm_pachIsapiDlls = 0;
  }
  if ( ISAPI_DLL::sm_pTraceLog )
  {
    DestroyRefTraceLog();
    ISAPI_DLL::sm_pTraceLog = 0;
  }
}

```

## disassembly

```asm
0x180005c44  sub     rsp, 28h
0x180005c48  mov     rcx, cs:?sm_pachIsapiDlls@ISAPI_DLL@@0PEAVALLOC_CACHE_HANDLER@@EA; this
0x180005c4f  test    rcx, rcx
0x180005c52  jz      short loc_180005C64
0x180005c54  call    ??_GALLOC_CACHE_HANDLER@@QEAAPEAXI@Z; ALLOC_CACHE_HANDLER::`scalar deleting destructor'(uint)
0x180005c59  mov     cs:?sm_pachIsapiDlls@ISAPI_DLL@@0PEAVALLOC_CACHE_HANDLER@@EA, 0; ALLOC_CACHE_HANDLER * ISAPI_DLL::sm_pachIsapiDlls
0x180005c64  mov     rcx, cs:?sm_pTraceLog@ISAPI_DLL@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * ISAPI_DLL::sm_pTraceLog
0x180005c6b  test    rcx, rcx
0x180005c6e  jz      short loc_180005C81
0x180005c70  call    cs:__imp_DestroyRefTraceLog
0x180005c76  mov     cs:?sm_pTraceLog@ISAPI_DLL@@0PEAU_TRACE_LOG@@EA, 0; _TRACE_LOG * ISAPI_DLL::sm_pTraceLog
0x180005c81  add     rsp, 28h
0x180005c85  retn
```
