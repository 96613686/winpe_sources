# W3_CONTEXT_BASE::~W3_CONTEXT_BASE(void)

- ea: `0x18001761c`
- end: `0x180017689`
- name: `??1W3_CONTEXT_BASE@@QEAA@XZ`
- size: `109`
- prototype: `void __fastcall(W3_CONTEXT_BASE *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800018c8`
- `0x180012dc0`
- `0x180016ad0`
- `0x18002129c`

## callees

- `0x18001761c`

## import_xrefs

- `iisutil!WriteRefTraceLog` at `0x18001767b`
- `iisutil!WriteRefTraceLog` at `0x18001767b`

## pseudocode

```c
void __fastcall W3_CONTEXT_BASE::~W3_CONTEXT_BASE(W3_CONTEXT_BASE *this)
{
  *(_QWORD *)this = &W3_CONTEXT_BASE::`vftable'{for `IHttpContext4'};
  *((_QWORD *)this + 1) = &W3_CONTEXT_BASE::`vftable'{for `IHttpTraceContext'};
  *((_QWORD *)this + 2) = &W3_CONTEXT_BASE::`vftable'{for `IMapHandlerProvider'};
  *((_QWORD *)this + 3) = &W3_CONTEXT_BASE::`vftable'{for `IModuleAllocator'};
  *((_QWORD *)this + 4) = &W3_CONTEXT_BASE::`vftable'{for `IAuthenticationProvider'};
  if ( W3_CONTEXT_BASE::sm_pTraceLog )
    WriteRefTraceLog(W3_CONTEXT_BASE::sm_pTraceLog, *((unsigned int *)this + 19), this);
  *((_DWORD *)this + 18) = 2019767159;
}

```

## disassembly

```asm
0x18001761c  push    rbx
0x18001761e  sub     rsp, 20h
0x180017622  lea     rax, ??_7W3_CONTEXT_BASE@@6BIHttpContext4@@@; const W3_CONTEXT_BASE::`vftable'{for `IHttpContext4'}
0x180017629  mov     rbx, rcx
0x18001762c  mov     [rcx], rax
0x18001762f  lea     rax, ??_7W3_CONTEXT_BASE@@6BIHttpTraceContext@@@; const W3_CONTEXT_BASE::`vftable'{for `IHttpTraceContext'}
0x180017636  mov     [rcx+8], rax
0x18001763a  lea     rax, ??_7W3_CONTEXT_BASE@@6BIMapHandlerProvider@@@; const W3_CONTEXT_BASE::`vftable'{for `IMapHandlerProvider'}
0x180017641  mov     [rcx+10h], rax
0x180017645  lea     rax, ??_7W3_CONTEXT_BASE@@6BIModuleAllocator@@@; const W3_CONTEXT_BASE::`vftable'{for `IModuleAllocator'}
0x18001764c  mov     [rcx+18h], rax
0x180017650  lea     rax, ??_7W3_CONTEXT_BASE@@6BIAuthenticationProvider@@@; const W3_CONTEXT_BASE::`vftable'{for `IAuthenticationProvider'}
0x180017657  mov     [rcx+20h], rax
0x18001765b  mov     rcx, cs:?sm_pTraceLog@W3_CONTEXT_BASE@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * W3_CONTEXT_BASE::sm_pTraceLog
0x180017662  test    rcx, rcx
0x180017665  jnz     short loc_180017675
0x180017667  mov     dword ptr [rbx+48h], 78633377h
0x18001766e  add     rsp, 20h
0x180017672  pop     rbx
0x180017673  retn
0x180017675  mov     edx, [rbx+4Ch]
0x180017678  mov     r8, rbx
0x18001767b  call    cs:__imp_WriteRefTraceLog
0x180017682  nop     dword ptr [rax+rax+00h]
0x180017687  jmp     short loc_180017667
```
