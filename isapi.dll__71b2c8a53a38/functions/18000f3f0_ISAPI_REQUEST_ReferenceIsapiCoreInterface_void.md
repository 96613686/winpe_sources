# ISAPI_REQUEST::ReferenceIsapiCoreInterface(void)

- ea: `0x18000f3f0`
- end: `0x18000f41d`
- name: `?ReferenceIsapiCoreInterface@ISAPI_REQUEST@@UEAAXXZ`
- size: `45`
- prototype: `void __fastcall(ISAPI_REQUEST *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000f3f0`

## import_xrefs

- `iisutil!WriteRefTraceLog` at `0x18000f412`
- `iisutil!WriteRefTraceLog` at `0x18000f412`

## pseudocode

```c
void __fastcall ISAPI_REQUEST::ReferenceIsapiCoreInterface(ISAPI_REQUEST *this)
{
  __int64 v1; // rdx

  v1 = (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 3);
  if ( ISAPI_REQUEST::sm_pTraceLog )
    WriteRefTraceLog(ISAPI_REQUEST::sm_pTraceLog, v1, this);
}

```

## disassembly

```asm
0x18000f3f0  sub     rsp, 28h
0x18000f3f4  mov     edx, 1
0x18000f3f9  lock xadd [rcx+0Ch], edx
0x18000f3fe  mov     rax, cs:?sm_pTraceLog@ISAPI_REQUEST@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * ISAPI_REQUEST::sm_pTraceLog
0x18000f405  inc     edx
0x18000f407  test    rax, rax
0x18000f40a  jz      short loc_18000F418
0x18000f40c  mov     r8, rcx
0x18000f40f  mov     rcx, rax
0x18000f412  call    cs:__imp_WriteRefTraceLog
0x18000f418  add     rsp, 28h
0x18000f41c  retn
```
