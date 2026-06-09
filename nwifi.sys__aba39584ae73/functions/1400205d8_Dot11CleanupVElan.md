# Dot11CleanupVElan

- ea: `0x1400205d8`
- end: `0x140020713`
- name: `Dot11CleanupVElan`
- size: `315`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400bd290`

## callees

- `0x1400205d8`
- `0x14002fb3c`
- `0x14009bbf0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400206cd`
- `ntoskrnl!IofCompleteRequest` at `0x1400206cd`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x1400206ec`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x1400206ec`
- `NDIS!NdisAcquireRWLockWrite` at `0x140020620`
- `NDIS!NdisAcquireRWLockWrite` at `0x140020620`
- `NDIS!NdisReleaseRWLock` at `0x14002069c`
- `NDIS!NdisReleaseRWLock` at `0x14002069c`

## pseudocode

```c
__int64 __fastcall Dot11CleanupVElan(__int64 a1)
{
  __int64 v1; // rsi
  __int64 v3; // rbx
  __int64 v4; // rax
  void (*v5)(void); // rax
  PIRP v6; // rax
  _QWORD PeekContext[2]; // [rsp+20h] [rbp-10h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+50h] [rbp+20h] BYREF

  v1 = *(_QWORD *)(a1 + 24);
  LockState.OldIrql = 0;
  *(_WORD *)&LockState.LockState = 0;
  if ( v1 )
  {
    v3 = *(_QWORD *)(v1 + 16);
    NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(v3 + 144), &LockState, 0);
    if ( *(_QWORD *)(v3 + 5888) == a1 )
    {
      v4 = *(_QWORD *)(v3 + 152);
      *(_QWORD *)(v3 + 5888) = 0;
      if ( v4 )
      {
        v5 = *(void (**)(void))(v4 + 240);
        if ( v5 )
        {
          if ( *(_QWORD *)(v3 + 8040) )
            v5();
        }
      }
    }
    if ( *(_QWORD *)(v3 + 5880) == a1 )
      *(_QWORD *)(v3 + 5880) = 0;
    if ( *(_QWORD *)(v3 + 5872) == a1 )
      *(_QWORD *)(v3 + 5872) = 0;
    NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v3 + 144), &LockState);
    if ( *(_DWORD *)(v1 + 32) )
      NwfCleanupAuthUpcall((PIO_CSQ)(v1 + 40));
    while ( 1 )
    {
      PeekContext[0] = 1;
      PeekContext[1] = a1;
      v6 = IoCsqRemoveNextIrp((PIO_CSQ)(v3 + 5440), PeekContext);
      if ( !v6 )
        break;
      v6->IoStatus.Status = -1073741248;
      v6->IoStatus.Information = 0;
      IofCompleteRequest(v6, 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1400205d8  mov     [rsp-18h+arg_8], rbx
0x1400205dd  mov     [rsp-18h+arg_10], rsi
0x1400205e2  push    rbp
0x1400205e3  push    rdi
0x1400205e4  push    r14
0x1400205e6  mov     rbp, rsp
0x1400205e9  sub     rsp, 30h
0x1400205ed  mov     rsi, [rcx+18h]
0x1400205f1  xor     eax, eax
0x1400205f3  mov     [rbp+LockState.OldIrql], 0
0x1400205f7  mov     rdi, rcx
0x1400205fa  mov     word ptr [rbp+LockState.LockState], ax
0x1400205fe  test    rsi, rsi
0x140020601  jz      loc_1400206FD
0x140020607  mov     rbx, [rsi+10h]
0x14002060b  lea     rdx, [rbp+LockState]; LockState
0x14002060f  xor     r8d, r8d; Flags
0x140020612  mov     rcx, [rbx+90h]; Lock
0x140020619  lea     r14, [rbx+1540h]
0x140020620  call    cs:__imp_NdisAcquireRWLockWrite
0x140020627  nop     dword ptr [rax+rax+00h]
0x14002062c  cmp     [rbx+1700h], rdi
0x140020633  jnz     short loc_140020669
0x140020635  mov     rax, [rbx+98h]
0x14002063c  mov     qword ptr [rbx+1700h], 0
0x140020647  test    rax, rax
0x14002064a  jz      short loc_140020669
0x14002064c  mov     rax, [rax+0F0h]
0x140020653  test    rax, rax
0x140020656  jz      short loc_140020669
0x140020658  mov     rcx, [rbx+1F68h]
0x14002065f  test    rcx, rcx
0x140020662  jz      short loc_140020669
0x140020664  call    _guard_dispatch_icall
0x140020669  cmp     [rbx+16F8h], rdi
0x140020670  jnz     short loc_14002067D
0x140020672  mov     qword ptr [rbx+16F8h], 0
0x14002067d  cmp     [rbx+16F0h], rdi
0x140020684  jnz     short loc_140020691
0x140020686  mov     qword ptr [rbx+16F0h], 0
0x140020691  mov     rcx, [rbx+90h]; Lock
0x140020698  lea     rdx, [rbp+LockState]; LockState
0x14002069c  call    cs:__imp_NdisReleaseRWLock
0x1400206a3  nop     dword ptr [rax+rax+00h]
0x1400206a8  cmp     dword ptr [rsi+20h], 0
0x1400206ac  jz      short loc_1400206D9
0x1400206ae  lea     rcx, [rsi+28h]; Csq
0x1400206b2  call    ?NwfCleanupAuthUpcall@@YAXPEAUNWF_AUTH_UPCALL@@@Z; NwfCleanupAuthUpcall(NWF_AUTH_UPCALL *)
0x1400206b7  jmp     short loc_1400206D9
0x1400206b9  xor     edx, edx; PriorityBoost
0x1400206bb  mov     dword ptr [rax+30h], 0C0000240h
0x1400206c2  mov     rcx, rax; Irp
0x1400206c5  mov     qword ptr [rax+38h], 0
0x1400206cd  call    cs:__imp_IofCompleteRequest
0x1400206d4  nop     dword ptr [rax+rax+00h]
0x1400206d9  lea     rdx, [rbp+PeekContext]; PeekContext
0x1400206dd  mov     [rbp+PeekContext], 1
0x1400206e5  mov     rcx, r14; Csq
0x1400206e8  mov     [rbp+var_8], rdi
0x1400206ec  call    cs:__imp_IoCsqRemoveNextIrp
0x1400206f3  nop     dword ptr [rax+rax+00h]
0x1400206f8  test    rax, rax
0x1400206fb  jnz     short loc_1400206B9
0x1400206fd  mov     rbx, [rsp+30h+arg_8]
0x140020702  xor     eax, eax
0x140020704  mov     rsi, [rsp+30h+arg_10]
0x140020709  add     rsp, 30h
0x14002070d  pop     r14
0x14002070f  pop     rdi
0x140020710  pop     rbp
0x140020711  retn
```
