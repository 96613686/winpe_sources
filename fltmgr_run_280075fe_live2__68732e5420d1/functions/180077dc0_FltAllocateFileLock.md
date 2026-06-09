# FltAllocateFileLock

- ea: `0x180077dc0`
- end: `0x180077e3e`
- name: `FltAllocateFileLock`
- size: `126`
- prototype: `PFILE_LOCK __stdcall(PFLT_COMPLETE_LOCK_CALLBACK_DATA_ROUTINE CompleteLockCallbackDataRoutine, PUNLOCK_ROUTINE UnlockRoutine)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180077dc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x180077df9`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x180077df9`
- `ntoskrnl!FsRtlInitializeFileLock` at `0x180077e1a`
- `ntoskrnl!FsRtlInitializeFileLock` at `0x180077e1a`
- `ntoskrnl!FsRtlAllocateFileLock` at `0x180077dd5`
- `ntoskrnl!FsRtlAllocateFileLock` at `0x180077dd5`

## pseudocode

```c
PFILE_LOCK __stdcall FltAllocateFileLock(
        PFLT_COMPLETE_LOCK_CALLBACK_DATA_ROUTINE CompleteLockCallbackDataRoutine,
        PUNLOCK_ROUTINE UnlockRoutine)
{
  FILE_LOCK *v5; // rax
  FILE_LOCK *v6; // rsi

  if ( !CompleteLockCallbackDataRoutine )
    return FsRtlAllocateFileLock(0, UnlockRoutine);
  v5 = (FILE_LOCK *)ExAllocateFromPagedLookasideList(&stru_18003EF40);
  v6 = v5;
  if ( v5 )
  {
    FsRtlInitializeFileLock(v5, FltpCompleteLockIrpRoutine, UnlockRoutine);
    v6[1].CompleteLockIrpRoutine = (PCOMPLETE_LOCK_IRP_ROUTINE)CompleteLockCallbackDataRoutine;
  }
  return v6;
}

```

## disassembly

```asm
0x180077dc0  mov     [rsp+arg_8], rbx
0x180077dc5  push    rdi
0x180077dc6  sub     rsp, 20h
0x180077dca  mov     rdi, rdx
0x180077dcd  mov     rbx, rcx
0x180077dd0  test    rcx, rcx
0x180077dd3  jnz     short loc_180077DED
0x180077dd5  call    cs:__imp_FsRtlAllocateFileLock
0x180077ddc  nop     dword ptr [rax+rax+00h]
0x180077de1  mov     rbx, [rsp+28h+arg_8]
0x180077de6  add     rsp, 20h
0x180077dea  pop     rdi
0x180077deb  retn
0x180077ded  lea     rcx, stru_18003EF40; Lookaside
0x180077df4  mov     [rsp+28h+arg_0], rsi
0x180077df9  call    cs:__imp_ExAllocateFromPagedLookasideList
0x180077e00  nop     dword ptr [rax+rax+00h]
0x180077e05  mov     rsi, rax
0x180077e08  test    rax, rax
0x180077e0b  jz      short loc_180077E2A
0x180077e0d  mov     r8, rdi; UnlockRoutine
0x180077e10  lea     rdx, FltpCompleteLockIrpRoutine; CompleteLockIrpRoutine
0x180077e17  mov     rcx, rax; FileLock
0x180077e1a  call    cs:__imp_FsRtlInitializeFileLock
0x180077e21  nop     dword ptr [rax+rax+00h]
0x180077e26  mov     [rsi+60h], rbx
0x180077e2a  mov     rbx, [rsp+28h+arg_8]
0x180077e2f  mov     rax, rsi
0x180077e32  mov     rsi, [rsp+28h+arg_0]
0x180077e37  add     rsp, 20h
0x180077e3b  pop     rdi
0x180077e3c  retn
```
