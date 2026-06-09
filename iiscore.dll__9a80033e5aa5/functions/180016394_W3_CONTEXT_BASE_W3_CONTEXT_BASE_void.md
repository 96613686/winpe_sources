# W3_CONTEXT_BASE::~W3_CONTEXT_BASE(void)

- ea: `0x180016394`
- end: `0x1800163fa`
- name: `??1W3_CONTEXT_BASE@@QEAA@XZ`
- size: `102`
- prototype: `void __fastcall(W3_CONTEXT_BASE *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001850`
- `0x180011eb0`
- `0x180015900`
- `0x18001f6b4`

## callees

- `0x180016394`

## import_xrefs

- `iisutil!WriteRefTraceLog` at `0x1800163f2`
- `iisutil!WriteRefTraceLog` at `0x1800163f2`

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
0x180016394  push    rbx
0x180016396  sub     rsp, 20h
0x18001639a  lea     rax, ??_7W3_CONTEXT_BASE@@6BIHttpContext4@@@; const W3_CONTEXT_BASE::`vftable'{for `IHttpContext4'}
0x1800163a1  mov     rbx, rcx
0x1800163a4  mov     [rcx], rax
0x1800163a7  lea     rax, ??_7W3_CONTEXT_BASE@@6BIHttpTraceContext@@@; const W3_CONTEXT_BASE::`vftable'{for `IHttpTraceContext'}
0x1800163ae  mov     [rcx+8], rax
0x1800163b2  lea     rax, ??_7W3_CONTEXT_BASE@@6BIMapHandlerProvider@@@; const W3_CONTEXT_BASE::`vftable'{for `IMapHandlerProvider'}
0x1800163b9  mov     [rcx+10h], rax
0x1800163bd  lea     rax, ??_7W3_CONTEXT_BASE@@6BIModuleAllocator@@@; const W3_CONTEXT_BASE::`vftable'{for `IModuleAllocator'}
0x1800163c4  mov     [rcx+18h], rax
0x1800163c8  lea     rax, ??_7W3_CONTEXT_BASE@@6BIAuthenticationProvider@@@; const W3_CONTEXT_BASE::`vftable'{for `IAuthenticationProvider'}
0x1800163cf  mov     [rcx+20h], rax
0x1800163d3  mov     rcx, cs:?sm_pTraceLog@W3_CONTEXT_BASE@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * W3_CONTEXT_BASE::sm_pTraceLog
0x1800163da  test    rcx, rcx
0x1800163dd  jnz     short loc_1800163EC
0x1800163df  mov     dword ptr [rbx+48h], 78633377h
0x1800163e6  add     rsp, 20h
0x1800163ea  pop     rbx
0x1800163eb  retn
0x1800163ec  mov     edx, [rbx+4Ch]
0x1800163ef  mov     r8, rbx
0x1800163f2  call    cs:__imp_WriteRefTraceLog
0x1800163f8  jmp     short loc_1800163DF
```
