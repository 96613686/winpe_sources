# W3_FILTER_CONTEXT::CleanupStoredContext(void)

- ea: `0x180006720`
- end: `0x18000677d`
- name: `?CleanupStoredContext@W3_FILTER_CONTEXT@@UEAAXXZ`
- size: `93`
- prototype: `void __fastcall(W3_FILTER_CONTEXT *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180006720`
- `0x18000d010`

## import_xrefs

- `iisutil!WriteRefTraceLog` at `0x180006775`
- `iisutil!WriteRefTraceLog` at `0x180006775`

## pseudocode

```c
void __fastcall W3_FILTER_CONTEXT::CleanupStoredContext(W3_FILTER_CONTEXT *this)
{
  unsigned __int32 v2; // ebx

  *((_QWORD *)this + 3) = 0;
  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 3);
  if ( W3_FILTER_CONTEXT::sm_pTraceLog )
    WriteRefTraceLog(W3_FILTER_CONTEXT::sm_pTraceLog, v2, this);
  if ( !v2 )
    (*(void (__fastcall **)(W3_FILTER_CONTEXT *, __int64))(*(_QWORD *)this + 8LL))(this, 1);
}

```

## disassembly

```asm
0x180006720  mov     [rsp+arg_0], rbx
0x180006725  push    rdi
0x180006726  sub     rsp, 20h
0x18000672a  mov     rdi, rcx
0x18000672d  mov     qword ptr [rcx+18h], 0
0x180006735  mov     ebx, 0FFFFFFFFh
0x18000673a  lock xadd [rcx+0Ch], ebx
0x18000673f  mov     rcx, cs:?sm_pTraceLog@W3_FILTER_CONTEXT@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * W3_FILTER_CONTEXT::sm_pTraceLog
0x180006746  dec     ebx
0x180006748  test    rcx, rcx
0x18000674b  jnz     short loc_180006770
0x18000674d  test    ebx, ebx
0x18000674f  jnz     short loc_180006765
0x180006751  mov     rax, [rdi]
0x180006754  mov     edx, 1
0x180006759  mov     rcx, rdi
0x18000675c  mov     rax, [rax+8]
0x180006760  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006765  mov     rbx, [rsp+28h+arg_0]
0x18000676a  add     rsp, 20h
0x18000676e  pop     rdi
0x18000676f  retn
0x180006770  mov     r8, rdi
0x180006773  mov     edx, ebx
0x180006775  call    cs:__imp_WriteRefTraceLog
0x18000677b  jmp     short loc_18000674D
```
