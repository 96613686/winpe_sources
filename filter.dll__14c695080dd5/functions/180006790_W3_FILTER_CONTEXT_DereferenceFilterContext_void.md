# W3_FILTER_CONTEXT::DereferenceFilterContext(void)

- ea: `0x180006790`
- end: `0x1800067ea`
- name: `?DereferenceFilterContext@W3_FILTER_CONTEXT@@QEAAXXZ`
- size: `90`
- prototype: `void __fastcall(W3_FILTER_CONTEXT *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a3e0`
- `0x18000b230`

## callees

- `0x180006790`
- `0x18000d010`

## import_xrefs

- `iisutil!WriteRefTraceLog` at `0x1800067e2`
- `iisutil!WriteRefTraceLog` at `0x1800067e2`

## pseudocode

```c
void __fastcall W3_FILTER_CONTEXT::DereferenceFilterContext(W3_FILTER_CONTEXT *this)
{
  unsigned __int32 v2; // ebx

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 3);
  if ( W3_FILTER_CONTEXT::sm_pTraceLog )
    WriteRefTraceLog(W3_FILTER_CONTEXT::sm_pTraceLog, v2, this);
  if ( !v2 )
  {
    if ( this )
      (*(void (__fastcall **)(W3_FILTER_CONTEXT *, __int64))(*(_QWORD *)this + 8LL))(this, 1);
  }
}

```

## disassembly

```asm
0x180006790  mov     [rsp+arg_0], rbx
0x180006795  push    rdi
0x180006796  sub     rsp, 20h
0x18000679a  mov     rdi, rcx
0x18000679d  mov     ebx, 0FFFFFFFFh
0x1800067a2  lock xadd [rcx+0Ch], ebx
0x1800067a7  mov     rcx, cs:?sm_pTraceLog@W3_FILTER_CONTEXT@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * W3_FILTER_CONTEXT::sm_pTraceLog
0x1800067ae  dec     ebx
0x1800067b0  test    rcx, rcx
0x1800067b3  jnz     short loc_1800067DD
0x1800067b5  test    ebx, ebx
0x1800067b7  jnz     short loc_1800067D2
0x1800067b9  test    rdi, rdi
0x1800067bc  jz      short loc_1800067D2
0x1800067be  mov     rax, [rdi]
0x1800067c1  mov     edx, 1
0x1800067c6  mov     rcx, rdi
0x1800067c9  mov     rax, [rax+8]
0x1800067cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067d2  mov     rbx, [rsp+28h+arg_0]
0x1800067d7  add     rsp, 20h
0x1800067db  pop     rdi
0x1800067dc  retn
0x1800067dd  mov     r8, rdi
0x1800067e0  mov     edx, ebx
0x1800067e2  call    cs:__imp_WriteRefTraceLog
0x1800067e8  jmp     short loc_1800067B5
```
