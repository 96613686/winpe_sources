# Vml::VmSlimEvent::Wait(ulong)

- ea: `0x18002a8b0`
- end: `0x18002a958`
- name: `?Wait@VmSlimEvent@Vml@@QEAAHK@Z`
- size: `168`
- prototype: `__int64 __fastcall(PSRWLOCK SRWLock, DWORD dwMilliseconds)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180028cbc`
- `0x180029b08`

## callees

- `0x18002a8b0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18002a8f4`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18002a8f4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002a936`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002a936`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002a8ca`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002a8ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a8d6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a902`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a8d6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a902`

## pseudocode

```c
__int64 __fastcall Vml::VmSlimEvent::Wait(PSRWLOCK SRWLock, DWORD dwMilliseconds)
{
  unsigned int v4; // esi
  BOOL v5; // ebx

  v4 = 0;
  AcquireSRWLockExclusive(SRWLock);
  GetCurrentThreadId();
  do
  {
    if ( HIDWORD(SRWLock[3].Ptr) )
      break;
    LODWORD(SRWLock[1].Ptr) = 0;
    v5 = SleepConditionVariableSRW((PCONDITION_VARIABLE)&SRWLock[2], SRWLock, dwMilliseconds, 0);
    LODWORD(SRWLock[1].Ptr) = GetCurrentThreadId();
  }
  while ( v5 );
  if ( HIDWORD(SRWLock[3].Ptr) )
  {
    if ( LODWORD(SRWLock[3].Ptr) )
      HIDWORD(SRWLock[3].Ptr) = 0;
    v4 = 1;
  }
  LODWORD(SRWLock[1].Ptr) = 0;
  ReleaseSRWLockExclusive(SRWLock);
  return v4;
}

```

## disassembly

```asm
0x18002a8b0  mov     [rsp+arg_10], rbx
0x18002a8b5  mov     [rsp+arg_18], rbp
0x18002a8ba  push    rsi
0x18002a8bb  push    rdi
0x18002a8bc  push    r14
0x18002a8be  sub     rsp, 30h
0x18002a8c2  mov     r14d, edx
0x18002a8c5  mov     rdi, rcx
0x18002a8c8  xor     esi, esi
0x18002a8ca  call    cs:__imp_AcquireSRWLockExclusive
0x18002a8d1  nop     dword ptr [rax+rax+00h]
0x18002a8d6  call    cs:__imp_GetCurrentThreadId
0x18002a8dd  nop     dword ptr [rax+rax+00h]
0x18002a8e2  jmp     short loc_18002A915
0x18002a8e4  xor     r9d, r9d; Flags
0x18002a8e7  mov     [rdi+8], esi
0x18002a8ea  mov     r8d, r14d; dwMilliseconds
0x18002a8ed  lea     rcx, [rdi+10h]; ConditionVariable
0x18002a8f1  mov     rdx, rdi; SRWLock
0x18002a8f4  call    cs:__imp_SleepConditionVariableSRW
0x18002a8fb  nop     dword ptr [rax+rax+00h]
0x18002a900  mov     ebx, eax
0x18002a902  call    cs:__imp_GetCurrentThreadId
0x18002a909  nop     dword ptr [rax+rax+00h]
0x18002a90e  mov     [rdi+8], eax
0x18002a911  test    ebx, ebx
0x18002a913  jz      short loc_18002A91A
0x18002a915  cmp     [rdi+1Ch], esi
0x18002a918  jz      short loc_18002A8E4
0x18002a91a  cmp     [rdi+1Ch], esi
0x18002a91d  jz      short loc_18002A92C
0x18002a91f  cmp     [rdi+18h], esi
0x18002a922  jz      short loc_18002A927
0x18002a924  mov     [rdi+1Ch], esi
0x18002a927  mov     esi, 1
0x18002a92c  mov     rcx, rdi; SRWLock
0x18002a92f  mov     dword ptr [rdi+8], 0
0x18002a936  call    cs:__imp_ReleaseSRWLockExclusive
0x18002a93d  nop     dword ptr [rax+rax+00h]
0x18002a942  mov     rbx, [rsp+48h+arg_10]
0x18002a947  mov     eax, esi
0x18002a949  mov     rbp, [rsp+48h+arg_18]
0x18002a94e  add     rsp, 30h
0x18002a952  pop     r14
0x18002a954  pop     rdi
0x18002a955  pop     rsi
0x18002a956  retn
```
