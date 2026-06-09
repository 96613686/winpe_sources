# W3_CONNECTION::DereferenceConnection(void)

- ea: `0x1800240e8`
- end: `0x18002413c`
- name: `?DereferenceConnection@W3_CONNECTION@@QEAAXXZ`
- size: `84`
- prototype: `void __fastcall(W3_CONNECTION *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ded4`
- `0x180015f5c`
- `0x180017a80`

## callees

- `0x1800240e8`
- `0x180035010`

## import_xrefs

- `iisutil!WriteRefTraceLog` at `0x180024110`
- `iisutil!WriteRefTraceLog` at `0x180024110`

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
0x1800240e8  mov     [rsp+arg_0], rbx
0x1800240ed  push    rdi
0x1800240ee  sub     rsp, 20h
0x1800240f2  mov     rbx, rcx
0x1800240f5  or      edi, 0FFFFFFFFh
0x1800240f8  lock xadd [rcx+18h], edi
0x1800240fd  mov     rcx, cs:?sm_pTraceLog@W3_CONNECTION@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * W3_CONNECTION::sm_pTraceLog
0x180024104  dec     edi
0x180024106  test    rcx, rcx
0x180024109  jz      short loc_180024116
0x18002410b  mov     r8, rbx
0x18002410e  mov     edx, edi
0x180024110  call    cs:__imp_WriteRefTraceLog
0x180024116  test    edi, edi
0x180024118  jnz     short loc_180024131
0x18002411a  test    rbx, rbx
0x18002411d  jz      short loc_180024131
0x18002411f  mov     rax, [rbx]
0x180024122  lea     edx, [rdi+1]
0x180024125  mov     rcx, rbx
0x180024128  mov     rax, [rax+18h]
0x18002412c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024131  mov     rbx, [rsp+28h+arg_0]
0x180024136  add     rsp, 20h
0x18002413a  pop     rdi
0x18002413b  retn
```
