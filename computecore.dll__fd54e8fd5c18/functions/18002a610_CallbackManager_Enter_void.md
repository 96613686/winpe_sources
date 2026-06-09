# CallbackManager::Enter(void)

- ea: `0x18002a610`
- end: `0x18002a6de`
- name: `?Enter@CallbackManager@@QEAA?AV?$optional@VCallbackReference@@@std@@XZ`
- size: `206`
- prototype: `__int64 __fastcall(PSRWLOCK SRWLock)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002a0b4`
- `0x18002ad50`
- `0x180048d5c`
- `0x180049b6c`
- `0x18004a4e0`
- `0x18004b114`
- `0x18004c990`

## callees

- `0x18000b948`
- `0x18002a610`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002a697`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002a697`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002a625`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002a625`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18002a654`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18002a654`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a62b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a62b`

## string_xrefs

- `0x18002a6b5`: `onecore\vm\compute\dll\lib\core\CallbackSynchronization.h`
- `0x18002a6cc`: `onecore\vm\compute\dll\lib\core\CallbackSynchronization.h`

## pseudocode

```c
__int64 __fastcall CallbackManager::Enter(PSRWLOCK SRWLock, __int64 a2)
{
  DWORD CurrentThreadId; // esi
  const char *v5; // r9
  int Ptr; // eax
  int v7; // ecx
  int Ptr_high; // edx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  AcquireSRWLockExclusive(SRWLock);
  CurrentThreadId = GetCurrentThreadId();
  Ptr = (int)SRWLock[2].Ptr;
  if ( Ptr )
  {
    do
    {
      v7 = Ptr;
      if ( Ptr == CurrentThreadId )
        break;
      if ( LOBYTE(SRWLock[3].Ptr) )
        goto LABEL_14;
      SleepConditionVariableSRW((PCONDITION_VARIABLE)&SRWLock[1], SRWLock, 0xFFFFFFFF, 0);
      Ptr = (int)SRWLock[2].Ptr;
      v7 = Ptr;
    }
    while ( Ptr );
  }
  else
  {
    v7 = 0;
  }
  if ( LOBYTE(SRWLock[3].Ptr) )
  {
LABEL_14:
    *(_BYTE *)(a2 + 8) = 0;
  }
  else
  {
    Ptr_high = HIDWORD(SRWLock[2].Ptr);
    if ( v7 )
    {
      if ( Ptr_high < 1 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x55,
          (unsigned int)"onecore\\vm\\compute\\dll\\lib\\core\\CallbackSynchronization.h",
          v5);
    }
    else
    {
      if ( Ptr_high )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x4F,
          (unsigned int)"onecore\\vm\\compute\\dll\\lib\\core\\CallbackSynchronization.h",
          v5);
      LODWORD(SRWLock[2].Ptr) = CurrentThreadId;
    }
    HIDWORD(SRWLock[2].Ptr) = Ptr_high + 1;
    *(_QWORD *)a2 = SRWLock;
    *(_BYTE *)(a2 + 8) = 1;
  }
  ReleaseSRWLockExclusive(SRWLock);
  return a2;
}

```

## disassembly

```asm
0x18002a610  mov     [rsp+arg_10], rbx
0x18002a615  mov     [rsp+arg_18], rsi
0x18002a61a  push    rdi
0x18002a61b  sub     rsp, 20h
0x18002a61f  mov     rdi, rdx
0x18002a622  mov     rbx, rcx
0x18002a625  call    cs:__imp_AcquireSRWLockExclusive
0x18002a62b  call    cs:__imp_GetCurrentThreadId
0x18002a631  mov     esi, eax
0x18002a633  mov     eax, [rbx+10h]
0x18002a636  test    eax, eax
0x18002a638  jz      short loc_18002A665
0x18002a63a  mov     ecx, eax
0x18002a63c  cmp     eax, esi
0x18002a63e  jz      short loc_18002A667
0x18002a640  cmp     byte ptr [rbx+18h], 0
0x18002a644  jnz     short loc_18002A690
0x18002a646  lea     rcx, [rbx+8]; ConditionVariable
0x18002a64a  xor     r9d, r9d; Flags
0x18002a64d  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x18002a651  mov     rdx, rbx; SRWLock
0x18002a654  call    cs:__imp_SleepConditionVariableSRW
0x18002a65a  mov     eax, [rbx+10h]
0x18002a65d  mov     ecx, eax
0x18002a65f  test    eax, eax
0x18002a661  jnz     short loc_18002A63A
0x18002a663  jmp     short loc_18002A667
0x18002a665  xor     ecx, ecx
0x18002a667  cmp     byte ptr [rbx+18h], 0
0x18002a66b  jnz     short loc_18002A690
0x18002a66d  mov     edx, [rbx+14h]
0x18002a670  test    ecx, ecx
0x18002a672  jnz     short loc_18002A689
0x18002a674  test    edx, edx
0x18002a676  jnz     short loc_18002A6B0
0x18002a678  mov     [rbx+10h], esi
0x18002a67b  inc     edx
0x18002a67d  mov     [rbx+14h], edx
0x18002a680  mov     [rdi], rbx
0x18002a683  mov     byte ptr [rdi+8], 1
0x18002a687  jmp     short loc_18002A694
0x18002a689  cmp     edx, 1
0x18002a68c  jl      short loc_18002A6C7
0x18002a68e  jmp     short loc_18002A67B
0x18002a690  mov     byte ptr [rdi+8], 0
0x18002a694  mov     rcx, rbx; SRWLock
0x18002a697  call    cs:__imp_ReleaseSRWLockExclusive
0x18002a69d  mov     rbx, [rsp+28h+arg_10]
0x18002a6a2  mov     rax, rdi
0x18002a6a5  mov     rsi, [rsp+28h+arg_18]
0x18002a6aa  add     rsp, 20h
0x18002a6ae  pop     rdi
0x18002a6af  retn
0x18002a6b0  mov     rcx, [rsp+28h]; this
0x18002a6b5  lea     r8, aOnecoreVmCompu_0; "onecore\\vm\\compute\\dll\\lib\\core\\C"...
0x18002a6bc  mov     edx, 4Fh ; 'O'; void *
0x18002a6c1  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18002a6c7  mov     rcx, [rsp+28h]; this
0x18002a6cc  lea     r8, aOnecoreVmCompu_0; "onecore\\vm\\compute\\dll\\lib\\core\\C"...
0x18002a6d3  mov     edx, 55h ; 'U'; void *
0x18002a6d8  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
