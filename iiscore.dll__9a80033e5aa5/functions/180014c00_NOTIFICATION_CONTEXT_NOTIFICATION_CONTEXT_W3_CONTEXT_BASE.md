# NOTIFICATION_CONTEXT::NOTIFICATION_CONTEXT(W3_CONTEXT_BASE *)

- ea: `0x180014c00`
- end: `0x180014cac`
- name: `??0NOTIFICATION_CONTEXT@@QEAA@PEAVW3_CONTEXT_BASE@@@Z`
- size: `172`
- prototype: `NOTIFICATION_CONTEXT *__fastcall(NOTIFICATION_CONTEXT *__hidden this, struct W3_CONTEXT_BASE *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18001ff10`
- `0x180021380`
- `0x180026d7c`
- `0x1800318e0`

## callees

- `0x180014c00`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180014c40`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180014c40`
- `iisutil!WriteRefTraceLog` at `0x180014c98`
- `iisutil!WriteRefTraceLog` at `0x180014c98`

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
0x180014c00  mov     [rsp+arg_0], rbx
0x180014c05  push    rdi
0x180014c06  sub     rsp, 20h
0x180014c0a  xor     edi, edi
0x180014c0c  mov     dword ptr [rcx+10h], 0FFFFFFFFh
0x180014c13  lea     rax, ??_7NOTIFICATION_CONTEXT@@6B@; const NOTIFICATION_CONTEXT::`vftable'
0x180014c1a  mov     [rcx+8], edi
0x180014c1d  mov     [rcx], rax
0x180014c20  mov     rbx, rcx
0x180014c23  mov     [rcx+0Ch], di
0x180014c27  mov     [rcx+18h], rdx
0x180014c2b  mov     dword ptr [rcx+20h], 5843544Eh
0x180014c32  mov     dword ptr [rcx+24h], 1
0x180014c39  mov     dword ptr [rcx+28h], 1
0x180014c40  call    cs:__imp_GetTickCount
0x180014c46  mov     rdx, [rbx+18h]
0x180014c4a  mov     [rbx+2Ch], eax
0x180014c4d  mov     [rbx+30h], rdi
0x180014c51  mov     [rbx+38h], rdi
0x180014c55  mov     [rbx+40h], rdi
0x180014c59  mov     [rbx+48h], rdi
0x180014c5d  mov     [rbx+50h], rdi
0x180014c61  mov     [rbx+58h], rdi
0x180014c65  mov     [rbx+60h], rdi
0x180014c69  mov     [rbx+68h], rdi
0x180014c6d  mov     [rbx+70h], rdi
0x180014c71  mov     [rbx+78h], edi
0x180014c74  mov     dword ptr [rbx+7Ch], 0FFFFFFFFh
0x180014c7b  mov     [rbx+80h], rdi
0x180014c82  lock inc dword ptr [rdx+4Ch]
0x180014c86  mov     rcx, cs:?sm_pTraceLog@W3_CONTEXT_BASE@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * W3_CONTEXT_BASE::sm_pTraceLog
0x180014c8d  test    rcx, rcx
0x180014c90  jz      short loc_180014C9E
0x180014c92  mov     r8, rdx
0x180014c95  mov     edx, [rdx+4Ch]
0x180014c98  call    cs:__imp_WriteRefTraceLog
0x180014c9e  mov     rax, rbx
0x180014ca1  mov     rbx, [rsp+28h+arg_0]
0x180014ca6  add     rsp, 20h
0x180014caa  pop     rdi
0x180014cab  retn
```
