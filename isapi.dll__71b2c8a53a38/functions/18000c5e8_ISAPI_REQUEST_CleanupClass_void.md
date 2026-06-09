# ISAPI_REQUEST::CleanupClass(void)

- ea: `0x18000c5e8`
- end: `0x18000c665`
- name: `?CleanupClass@ISAPI_REQUEST@@SAXXZ`
- size: `125`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x180001f2c`
- `0x1800032c0`

## callees

- `0x180001060`
- `0x1800050d4`
- `0x18000c5e8`

## import_xrefs

- `iisutil!DestroyRefTraceLog` at `0x18000c64f`
- `iisutil!DestroyRefTraceLog` at `0x18000c64f`
- `CRYPTSP!CryptReleaseContext` at `0x18000c616`
- `CRYPTSP!CryptReleaseContext` at `0x18000c616`

## pseudocode

```c
void ISAPI_REQUEST::CleanupClass(void)
{
  if ( ISAPI_REQUEST::sm_pLogonProvider )
  {
    operator delete(ISAPI_REQUEST::sm_pLogonProvider);
    ISAPI_REQUEST::sm_pLogonProvider = 0;
  }
  if ( TOKEN_KEY::sm_hCryptProv )
  {
    CryptReleaseContext(TOKEN_KEY::sm_hCryptProv, 0);
    TOKEN_KEY::sm_hCryptProv = 0;
  }
  if ( ISAPI_REQUEST::sm_pachIsapiRequest )
  {
    ALLOC_CACHE_HANDLER::`scalar deleting destructor'(ISAPI_REQUEST::sm_pachIsapiRequest);
    ISAPI_REQUEST::sm_pachIsapiRequest = 0;
  }
  if ( ISAPI_REQUEST::sm_pTraceLog )
  {
    DestroyRefTraceLog();
    ISAPI_REQUEST::sm_pTraceLog = 0;
  }
}

```

## disassembly

```asm
0x18000c5e8  sub     rsp, 28h
0x18000c5ec  mov     rcx, cs:?sm_pLogonProvider@ISAPI_REQUEST@@0PEAVIIS_LOGON_PROVIDER@@EA; Block
0x18000c5f3  test    rcx, rcx
0x18000c5f6  jz      short loc_18000C608
0x18000c5f8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c5fd  mov     cs:?sm_pLogonProvider@ISAPI_REQUEST@@0PEAVIIS_LOGON_PROVIDER@@EA, 0; IIS_LOGON_PROVIDER * ISAPI_REQUEST::sm_pLogonProvider
0x18000c608  mov     rcx, cs:?sm_hCryptProv@TOKEN_KEY@@0_KA; hProv
0x18000c60f  test    rcx, rcx
0x18000c612  jz      short loc_18000C627
0x18000c614  xor     edx, edx; dwFlags
0x18000c616  call    cs:__imp_CryptReleaseContext
0x18000c61c  mov     cs:?sm_hCryptProv@TOKEN_KEY@@0_KA, 0; unsigned __int64 TOKEN_KEY::sm_hCryptProv
0x18000c627  mov     rcx, cs:?sm_pachIsapiRequest@ISAPI_REQUEST@@0PEAVALLOC_CACHE_HANDLER@@EA; this
0x18000c62e  test    rcx, rcx
0x18000c631  jz      short loc_18000C643
0x18000c633  call    ??_GALLOC_CACHE_HANDLER@@QEAAPEAXI@Z; ALLOC_CACHE_HANDLER::`scalar deleting destructor'(uint)
0x18000c638  mov     cs:?sm_pachIsapiRequest@ISAPI_REQUEST@@0PEAVALLOC_CACHE_HANDLER@@EA, 0; ALLOC_CACHE_HANDLER * ISAPI_REQUEST::sm_pachIsapiRequest
0x18000c643  mov     rcx, cs:?sm_pTraceLog@ISAPI_REQUEST@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * ISAPI_REQUEST::sm_pTraceLog
0x18000c64a  test    rcx, rcx
0x18000c64d  jz      short loc_18000C660
0x18000c64f  call    cs:__imp_DestroyRefTraceLog
0x18000c655  mov     cs:?sm_pTraceLog@ISAPI_REQUEST@@0PEAU_TRACE_LOG@@EA, 0; _TRACE_LOG * ISAPI_REQUEST::sm_pTraceLog
0x18000c660  add     rsp, 28h
0x18000c664  retn
```
