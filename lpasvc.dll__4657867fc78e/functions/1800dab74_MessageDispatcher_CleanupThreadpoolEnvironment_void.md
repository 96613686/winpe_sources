# MessageDispatcher::CleanupThreadpoolEnvironment(void)

- ea: `0x1800dab74`
- end: `0x1800dabc4`
- name: `?CleanupThreadpoolEnvironment@MessageDispatcher@@AEAAXXZ`
- size: `80`
- prototype: `void __fastcall(PVOID pvCleanupContext)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callers

- `0x1800dad58`
- `0x1800dae70`

## callees

- `0x18000e430`
- `0x1800dab74`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x1800dab8b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x1800dab8b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x1800dab95`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x1800dab95`

## pseudocode

```c
void __fastcall MessageDispatcher::CleanupThreadpoolEnvironment(PVOID pvCleanupContext)
{
  struct _TP_CLEANUP_GROUP *v2; // rcx
  void *v3; // rcx

  v2 = (struct _TP_CLEANUP_GROUP *)*((_QWORD *)pvCleanupContext + 15);
  if ( v2 )
  {
    CloseThreadpoolCleanupGroupMembers(v2, 0, pvCleanupContext);
    CloseThreadpoolCleanupGroup(*((PTP_CLEANUP_GROUP *)pvCleanupContext + 15));
    *((_QWORD *)pvCleanupContext + 15) = 0;
  }
  v3 = (void *)*((_QWORD *)pvCleanupContext + 14);
  if ( v3 )
  {
    operator delete(v3, (const struct std::nothrow_t *)0x48);
    *((_QWORD *)pvCleanupContext + 14) = 0;
  }
}

```

## disassembly

```asm
0x1800dab74  push    rbx
0x1800dab76  sub     rsp, 20h
0x1800dab7a  mov     rbx, rcx
0x1800dab7d  mov     rcx, [rcx+78h]; ptpcg
0x1800dab81  test    rcx, rcx
0x1800dab84  jz      short loc_1800DABA3
0x1800dab86  mov     r8, rbx; pvCleanupContext
0x1800dab89  xor     edx, edx; fCancelPendingCallbacks
0x1800dab8b  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x1800dab91  mov     rcx, [rbx+78h]; ptpcg
0x1800dab95  call    cs:__imp_CloseThreadpoolCleanupGroup
0x1800dab9b  mov     qword ptr [rbx+78h], 0
0x1800daba3  mov     rcx, [rbx+70h]; void *
0x1800daba7  test    rcx, rcx
0x1800dabaa  jz      short loc_1800DABBE
0x1800dabac  mov     edx, 48h ; 'H'; struct std::nothrow_t *
0x1800dabb1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800dabb6  mov     qword ptr [rbx+70h], 0
0x1800dabbe  add     rsp, 20h
0x1800dabc2  pop     rbx
0x1800dabc3  retn
```
