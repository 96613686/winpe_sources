# CACHED_FILE_INFO::ReferenceCacheData(void)

- ea: `0x180002510`
- end: `0x180002542`
- name: `?ReferenceCacheData@CACHED_FILE_INFO@@UEAAXXZ`
- size: `50`
- prototype: `void __fastcall(CACHED_FILE_INFO *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002510`

## import_xrefs

- `iisutil!WriteRefTraceLog` at `0x18000253a`
- `iisutil!WriteRefTraceLog` at `0x18000253a`

## pseudocode

```c
void __fastcall CACHED_FILE_INFO::ReferenceCacheData(CACHED_FILE_INFO *this)
{
  __int64 v1; // rdx

  v1 = (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 65);
  if ( g_pTraceLog )
    WriteRefTraceLog(g_pTraceLog, v1, this);
}

```

## disassembly

```asm
0x180002510  sub     rsp, 28h
0x180002514  mov     edx, 1
0x180002519  lock xadd [rcx+104h], edx
0x180002521  mov     rax, cs:?g_pTraceLog@@3PEAU_TRACE_LOG@@EA; _TRACE_LOG * g_pTraceLog
0x180002528  inc     edx
0x18000252a  test    rax, rax
0x18000252d  jnz     short loc_180002534
0x18000252f  add     rsp, 28h
0x180002533  retn
0x180002534  mov     r8, rcx
0x180002537  mov     rcx, rax
0x18000253a  call    cs:__imp_WriteRefTraceLog
0x180002540  jmp     short loc_18000252F
```
