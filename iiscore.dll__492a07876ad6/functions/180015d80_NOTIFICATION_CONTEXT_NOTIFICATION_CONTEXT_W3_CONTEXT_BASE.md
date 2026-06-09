# NOTIFICATION_CONTEXT::NOTIFICATION_CONTEXT(W3_CONTEXT_BASE *)

- ea: `0x180015d80`
- end: `0x180015e39`
- name: `??0NOTIFICATION_CONTEXT@@QEAA@PEAVW3_CONTEXT_BASE@@@Z`
- size: `185`
- prototype: `NOTIFICATION_CONTEXT *__fastcall(NOTIFICATION_CONTEXT *__hidden this, struct W3_CONTEXT_BASE *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180021af0`
- `0x180022ff0`
- `0x180028e24`
- `0x180034700`

## callees

- `0x180015d80`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180015dc0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180015dc0`
- `iisutil!WriteRefTraceLog` at `0x180015e1e`
- `iisutil!WriteRefTraceLog` at `0x180015e1e`

## pseudocode

```c
NOTIFICATION_CONTEXT *__fastcall NOTIFICATION_CONTEXT::NOTIFICATION_CONTEXT(
        NOTIFICATION_CONTEXT *this,
        struct W3_CONTEXT_BASE *a2)
{
  DWORD TickCount; // eax
  __int64 v4; // rdx

  *((_DWORD *)this + 4) = -1;
  *((_DWORD *)this + 2) = 0;
  *(_QWORD *)this = &NOTIFICATION_CONTEXT::`vftable';
  *((_WORD *)this + 6) = 0;
  *((_QWORD *)this + 3) = a2;
  *((_DWORD *)this + 8) = 1480807502;
  *((_DWORD *)this + 9) = 1;
  *((_DWORD *)this + 10) = 1;
  TickCount = GetTickCount();
  v4 = *((_QWORD *)this + 3);
  *((_DWORD *)this + 11) = TickCount;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_DWORD *)this + 30) = 0;
  *((_DWORD *)this + 31) = -1;
  *((_QWORD *)this + 16) = 0;
  _InterlockedIncrement((volatile signed __int32 *)(v4 + 76));
  if ( W3_CONTEXT_BASE::sm_pTraceLog )
    WriteRefTraceLog(W3_CONTEXT_BASE::sm_pTraceLog, *(unsigned int *)(v4 + 76), v4);
  return this;
}

```

## disassembly

```asm
0x180015d80  mov     [rsp+arg_0], rbx
0x180015d85  push    rdi
0x180015d86  sub     rsp, 20h
0x180015d8a  xor     edi, edi
0x180015d8c  mov     dword ptr [rcx+10h], 0FFFFFFFFh
0x180015d93  lea     rax, ??_7NOTIFICATION_CONTEXT@@6B@; const NOTIFICATION_CONTEXT::`vftable'
0x180015d9a  mov     [rcx+8], edi
0x180015d9d  mov     [rcx], rax
0x180015da0  mov     rbx, rcx
0x180015da3  mov     [rcx+0Ch], di
0x180015da7  mov     [rcx+18h], rdx
0x180015dab  mov     dword ptr [rcx+20h], 5843544Eh
0x180015db2  mov     dword ptr [rcx+24h], 1
0x180015db9  mov     dword ptr [rcx+28h], 1
0x180015dc0  call    cs:__imp_GetTickCount
0x180015dc7  nop     dword ptr [rax+rax+00h]
0x180015dcc  mov     rdx, [rbx+18h]
0x180015dd0  mov     [rbx+2Ch], eax
0x180015dd3  mov     [rbx+30h], rdi
0x180015dd7  mov     [rbx+38h], rdi
0x180015ddb  mov     [rbx+40h], rdi
0x180015ddf  mov     [rbx+48h], rdi
0x180015de3  mov     [rbx+50h], rdi
0x180015de7  mov     [rbx+58h], rdi
0x180015deb  mov     [rbx+60h], rdi
0x180015def  mov     [rbx+68h], rdi
0x180015df3  mov     [rbx+70h], rdi
0x180015df7  mov     [rbx+78h], edi
0x180015dfa  mov     dword ptr [rbx+7Ch], 0FFFFFFFFh
0x180015e01  mov     [rbx+80h], rdi
0x180015e08  lock inc dword ptr [rdx+4Ch]
0x180015e0c  mov     rcx, cs:?sm_pTraceLog@W3_CONTEXT_BASE@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * W3_CONTEXT_BASE::sm_pTraceLog
0x180015e13  test    rcx, rcx
0x180015e16  jz      short loc_180015E2A
0x180015e18  mov     r8, rdx
0x180015e1b  mov     edx, [rdx+4Ch]
0x180015e1e  call    cs:__imp_WriteRefTraceLog
0x180015e25  nop     dword ptr [rax+rax+00h]
0x180015e2a  mov     rax, rbx
0x180015e2d  mov     rbx, [rsp+28h+arg_0]
0x180015e32  add     rsp, 20h
0x180015e36  pop     rdi
0x180015e37  retn
```
