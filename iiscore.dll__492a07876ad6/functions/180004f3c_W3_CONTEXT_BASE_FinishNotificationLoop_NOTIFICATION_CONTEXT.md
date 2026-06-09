# W3_CONTEXT_BASE::FinishNotificationLoop(NOTIFICATION_CONTEXT *)

- ea: `0x180004f3c`
- end: `0x18000501d`
- name: `?FinishNotificationLoop@W3_CONTEXT_BASE@@SA?AW4ASYNC_STATUS@@PEAVNOTIFICATION_CONTEXT@@@Z`
- size: `225`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x180001b60`
- `0x180002db0`
- `0x180003720`
- `0x180004520`
- `0x18000468c`
- `0x180004710`
- `0x180004dd0`
- `0x180021af0`
- `0x180022ff0`
- `0x180034700`

## callees

- `0x180004f3c`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000500a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000500a`
- `iisutil!WriteRefTraceLog` at `0x180004f90`
- `iisutil!WriteRefTraceLog` at `0x180004fdc`
- `iisutil!WriteRefTraceLog` at `0x180004f90`
- `iisutil!WriteRefTraceLog` at `0x180004fdc`

## pseudocode

```c
__int64 __fastcall W3_CONTEXT_BASE::FinishNotificationLoop(__int64 a1)
{
  void *v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rdi
  __int64 v5; // r14
  unsigned __int32 v6; // esi
  unsigned __int32 v7; // edi

  v2 = *(void **)(a1 + 64);
  if ( v2 )
  {
    SetEvent(v2);
    return 1;
  }
  else
  {
    v3 = *(_QWORD *)(a1 + 24);
    v4 = *(_QWORD *)(v3 + 80);
    if ( v4 )
    {
      *(_QWORD *)(v3 + 80) = *(_QWORD *)(v4 + 56);
      v5 = *(_QWORD *)(v4 + 56);
      if ( v5 )
      {
        v6 = _InterlockedDecrement((volatile signed __int32 *)(v5 + 36));
        if ( NOTIFICATION_CONTEXT::sm_pTraceLog )
          WriteRefTraceLog(NOTIFICATION_CONTEXT::sm_pTraceLog, v6, v5);
        if ( !v6 )
          (**(void (__fastcall ***)(__int64, __int64))v5)(v5, 1);
        _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)(v4 + 56) + 52LL));
      }
      *(_QWORD *)(v4 + 56) = 0;
    }
    v7 = _InterlockedDecrement((volatile signed __int32 *)(a1 + 36));
    if ( NOTIFICATION_CONTEXT::sm_pTraceLog )
      WriteRefTraceLog(NOTIFICATION_CONTEXT::sm_pTraceLog, v7, a1);
    if ( !v7 )
      (**(void (__fastcall ***)(__int64, __int64))a1)(a1, 1);
    return 0;
  }
}

```

## disassembly

```asm
0x180004f3c  push    rbx
0x180004f3e  push    rsi
0x180004f3f  push    rdi
0x180004f40  push    r14
0x180004f42  sub     rsp, 28h
0x180004f46  mov     rbx, rcx
0x180004f49  mov     rcx, [rcx+40h]; hEvent
0x180004f4d  test    rcx, rcx
0x180004f50  jnz     loc_18000500A
0x180004f56  mov     rcx, [rbx+18h]
0x180004f5a  mov     rdi, [rcx+50h]
0x180004f5e  test    rdi, rdi
0x180004f61  jz      short loc_180004FC1
0x180004f63  mov     rax, [rdi+38h]
0x180004f67  mov     [rcx+50h], rax
0x180004f6b  mov     r14, [rdi+38h]
0x180004f6f  test    r14, r14
0x180004f72  jz      short loc_180004FB9
0x180004f74  or      esi, 0FFFFFFFFh
0x180004f77  lock xadd [r14+24h], esi
0x180004f7d  mov     rcx, cs:?sm_pTraceLog@NOTIFICATION_CONTEXT@@2PEAU_TRACE_LOG@@EA; _TRACE_LOG * NOTIFICATION_CONTEXT::sm_pTraceLog
0x180004f84  dec     esi
0x180004f86  test    rcx, rcx
0x180004f89  jz      short loc_180004F9C
0x180004f8b  mov     r8, r14
0x180004f8e  mov     edx, esi
0x180004f90  call    cs:__imp_WriteRefTraceLog
0x180004f97  nop     dword ptr [rax+rax+00h]
0x180004f9c  test    esi, esi
0x180004f9e  jnz     short loc_180004FB1
0x180004fa0  mov     rax, [r14]
0x180004fa3  lea     edx, [rsi+1]
0x180004fa6  mov     rcx, r14
0x180004fa9  mov     rax, [rax]
0x180004fac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fb1  mov     rax, [rdi+38h]
0x180004fb5  lock dec dword ptr [rax+34h]
0x180004fb9  mov     qword ptr [rdi+38h], 0
0x180004fc1  or      edi, 0FFFFFFFFh
0x180004fc4  lock xadd [rbx+24h], edi
0x180004fc9  mov     rcx, cs:?sm_pTraceLog@NOTIFICATION_CONTEXT@@2PEAU_TRACE_LOG@@EA; _TRACE_LOG * NOTIFICATION_CONTEXT::sm_pTraceLog
0x180004fd0  dec     edi
0x180004fd2  test    rcx, rcx
0x180004fd5  jz      short loc_180004FE8
0x180004fd7  mov     r8, rbx
0x180004fda  mov     edx, edi
0x180004fdc  call    cs:__imp_WriteRefTraceLog
0x180004fe3  nop     dword ptr [rax+rax+00h]
0x180004fe8  test    edi, edi
0x180004fea  jnz     short loc_180004FFD
0x180004fec  mov     rax, [rbx]
0x180004fef  lea     edx, [rdi+1]
0x180004ff2  mov     rcx, rbx
0x180004ff5  mov     rax, [rax]
0x180004ff8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ffd  xor     eax, eax
0x180004fff  add     rsp, 28h
0x180005003  pop     r14
0x180005005  pop     rdi
0x180005006  pop     rsi
0x180005007  pop     rbx
0x180005008  retn
0x18000500a  call    cs:__imp_SetEvent
0x180005011  nop     dword ptr [rax+rax+00h]
0x180005016  mov     eax, 1
0x18000501b  jmp     short loc_180004FFF
```
