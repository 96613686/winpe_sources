# W3_CONNECTION::DereferenceConnection(void)

- ea: `0x180025f88`
- end: `0x180025fe3`
- name: `?DereferenceConnection@W3_CONNECTION@@QEAAXXZ`
- size: `91`
- prototype: `void __fastcall(W3_CONNECTION *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ea5c`
- `0x1800171ac`
- `0x180018ee0`

## callees

- `0x180025f88`
- `0x180038010`

## import_xrefs

- `iisutil!WriteRefTraceLog` at `0x180025fb0`
- `iisutil!WriteRefTraceLog` at `0x180025fb0`

## pseudocode

```c
void __fastcall W3_CONNECTION::DereferenceConnection(W3_CONNECTION *this)
{
  unsigned __int32 v2; // edi

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 6);
  if ( W3_CONNECTION::sm_pTraceLog )
    WriteRefTraceLog(W3_CONNECTION::sm_pTraceLog, v2, this);
  if ( !v2 )
  {
    if ( this )
      (*(void (__fastcall **)(W3_CONNECTION *, __int64))(*(_QWORD *)this + 24LL))(this, 1);
  }
}

```

## disassembly

```asm
0x180025f88  mov     [rsp+arg_0], rbx
0x180025f8d  push    rdi
0x180025f8e  sub     rsp, 20h
0x180025f92  mov     rbx, rcx
0x180025f95  or      edi, 0FFFFFFFFh
0x180025f98  lock xadd [rcx+18h], edi
0x180025f9d  mov     rcx, cs:?sm_pTraceLog@W3_CONNECTION@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * W3_CONNECTION::sm_pTraceLog
0x180025fa4  dec     edi
0x180025fa6  test    rcx, rcx
0x180025fa9  jz      short loc_180025FBC
0x180025fab  mov     r8, rbx
0x180025fae  mov     edx, edi
0x180025fb0  call    cs:__imp_WriteRefTraceLog
0x180025fb7  nop     dword ptr [rax+rax+00h]
0x180025fbc  test    edi, edi
0x180025fbe  jnz     short loc_180025FD7
0x180025fc0  test    rbx, rbx
0x180025fc3  jz      short loc_180025FD7
0x180025fc5  mov     rax, [rbx]
0x180025fc8  lea     edx, [rdi+1]
0x180025fcb  mov     rcx, rbx
0x180025fce  mov     rax, [rax+18h]
0x180025fd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025fd7  mov     rbx, [rsp+28h+arg_0]
0x180025fdc  add     rsp, 20h
0x180025fe0  pop     rdi
0x180025fe1  retn
```
