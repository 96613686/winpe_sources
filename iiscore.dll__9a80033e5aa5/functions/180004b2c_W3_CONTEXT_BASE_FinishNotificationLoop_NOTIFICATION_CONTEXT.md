# W3_CONTEXT_BASE::FinishNotificationLoop(NOTIFICATION_CONTEXT *)

- ea: `0x180004b2c`
- end: `0x180004bfa`
- name: `?FinishNotificationLoop@W3_CONTEXT_BASE@@SA?AW4ASYNC_STATUS@@PEAVNOTIFICATION_CONTEXT@@@Z`
- size: `206`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x180001acc`
- `0x180002bf0`
- `0x180003490`
- `0x180004160`
- `0x1800042cc`
- `0x180004340`
- `0x1800049d0`
- `0x18001ff10`
- `0x180021380`
- `0x1800318e0`

## callees

- `0x180004b2c`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180004bed`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180004bed`
- `iisutil!WriteRefTraceLog` at `0x180004b80`
- `iisutil!WriteRefTraceLog` at `0x180004bc6`
- `iisutil!WriteRefTraceLog` at `0x180004b80`
- `iisutil!WriteRefTraceLog` at `0x180004bc6`

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
0x180004b2c  push    rbx
0x180004b2e  push    rsi
0x180004b2f  push    rdi
0x180004b30  push    r14
0x180004b32  sub     rsp, 28h
0x180004b36  mov     rbx, rcx
0x180004b39  mov     rcx, [rcx+40h]; hEvent
0x180004b3d  test    rcx, rcx
0x180004b40  jnz     loc_180004BED
0x180004b46  mov     rcx, [rbx+18h]
0x180004b4a  mov     rdi, [rcx+50h]
0x180004b4e  test    rdi, rdi
0x180004b51  jz      short loc_180004BAB
0x180004b53  mov     rax, [rdi+38h]
0x180004b57  mov     [rcx+50h], rax
0x180004b5b  mov     r14, [rdi+38h]
0x180004b5f  test    r14, r14
0x180004b62  jz      short loc_180004BA3
0x180004b64  or      esi, 0FFFFFFFFh
0x180004b67  lock xadd [r14+24h], esi
0x180004b6d  mov     rcx, cs:?sm_pTraceLog@NOTIFICATION_CONTEXT@@2PEAU_TRACE_LOG@@EA; _TRACE_LOG * NOTIFICATION_CONTEXT::sm_pTraceLog
0x180004b74  dec     esi
0x180004b76  test    rcx, rcx
0x180004b79  jz      short loc_180004B86
0x180004b7b  mov     r8, r14
0x180004b7e  mov     edx, esi
0x180004b80  call    cs:__imp_WriteRefTraceLog
0x180004b86  test    esi, esi
0x180004b88  jnz     short loc_180004B9B
0x180004b8a  mov     rax, [r14]
0x180004b8d  lea     edx, [rsi+1]
0x180004b90  mov     rcx, r14
0x180004b93  mov     rax, [rax]
0x180004b96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b9b  mov     rax, [rdi+38h]
0x180004b9f  lock dec dword ptr [rax+34h]
0x180004ba3  mov     qword ptr [rdi+38h], 0
0x180004bab  or      edi, 0FFFFFFFFh
0x180004bae  lock xadd [rbx+24h], edi
0x180004bb3  mov     rcx, cs:?sm_pTraceLog@NOTIFICATION_CONTEXT@@2PEAU_TRACE_LOG@@EA; _TRACE_LOG * NOTIFICATION_CONTEXT::sm_pTraceLog
0x180004bba  dec     edi
0x180004bbc  test    rcx, rcx
0x180004bbf  jz      short loc_180004BCC
0x180004bc1  mov     r8, rbx
0x180004bc4  mov     edx, edi
0x180004bc6  call    cs:__imp_WriteRefTraceLog
0x180004bcc  test    edi, edi
0x180004bce  jnz     short loc_180004BE1
0x180004bd0  mov     rax, [rbx]
0x180004bd3  lea     edx, [rdi+1]
0x180004bd6  mov     rcx, rbx
0x180004bd9  mov     rax, [rax]
0x180004bdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004be1  xor     eax, eax
0x180004be3  add     rsp, 28h
0x180004be7  pop     r14
0x180004be9  pop     rdi
0x180004bea  pop     rsi
0x180004beb  pop     rbx
0x180004bec  retn
0x180004bed  call    cs:__imp_SetEvent
0x180004bf3  mov     eax, 1
0x180004bf8  jmp     short loc_180004BE3
```
