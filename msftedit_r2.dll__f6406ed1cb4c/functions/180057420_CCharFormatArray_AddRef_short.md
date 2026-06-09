# CCharFormatArray::AddRef(short)

- ea: `0x180057420`
- end: `0x18005755a`
- name: `?AddRef@CCharFormatArray@@UEAAJF@Z`
- size: `314`
- prototype: `__int64 __fastcall(CCharFormatArray *__hidden this, __int16)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180057420`
- `0x180057560`
- `0x18005921c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005751f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005751f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800574f3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800574f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005745a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005752b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005745a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005752b`

## pseudocode

```c
__int64 __fastcall CCharFormatArray::AddRef(CCharFormatArray *this, __int16 a2)
{
  unsigned int v2; // edi
  signed int v3; // ebp
  int v5; // r14d
  __int64 v6; // rax
  int v7; // edx
  RTL_SRWLOCK *v8; // rax
  RTL_SRWLOCK *Lock; // rax
  DWORD CurrentThreadId; // eax
  int v12; // [rsp+48h] [rbp+10h] BYREF

  v2 = -1;
  v3 = a2;
  if ( (unsigned int)a2 < *((_DWORD *)this + 5) )
  {
    v5 = (int)CLockSharedData::LockOwner;
    v12 = 0;
    if ( (_DWORD)CLockSharedData::LockOwner && v5 == GetCurrentThreadId() )
    {
      LODWORD(CLockSharedData::LockTelemetry) = (_DWORD)CLockSharedData::LockTelemetry + 1;
    }
    else
    {
      Lock = (RTL_SRWLOCK *)CLockSharedOS::GetLock(0);
      AcquireSRWLockExclusive(Lock);
      CurrentThreadId = GetCurrentThreadId();
      ++dword_1802E474C[0];
      LODWORD(CLockSharedData::LockOwner) = CurrentThreadId;
    }
    if ( (unsigned int)v3 >= *((_DWORD *)this + 5)
      || *(int *)(*(_QWORD *)(*((_QWORD *)this + 1) + 8LL * (v3 / 16)) + *((_DWORD *)this + 7) * (v3 % 16 + 1) - 4LL) <= 0 )
    {
      CWriteLock::~CWriteLock((CWriteLock *)&v12);
    }
    else
    {
      v6 = *(_QWORD *)(*((_QWORD *)this + 1) + 8LL * (v3 / 16));
      v7 = *((_DWORD *)this + 7) * (v3 % 16 + 1);
      v2 = ++*(_DWORD *)(v6 + v7 - 4);
      if ( (int)CLockSharedData::LockTelemetry > 0 )
      {
        LODWORD(CLockSharedData::LockTelemetry) = (_DWORD)CLockSharedData::LockTelemetry - 1;
      }
      else
      {
        LODWORD(CLockSharedData::LockOwner) = 0;
        v8 = (RTL_SRWLOCK *)CLockSharedOS::GetLock(0);
        ReleaseSRWLockExclusive(v8);
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180057420  mov     [rsp+arg_0], rbx
0x180057425  mov     [rsp+arg_10], rbp
0x18005742a  push    rsi
0x18005742b  push    rdi
0x18005742c  push    r14
0x18005742e  sub     rsp, 20h
0x180057432  or      edi, 0FFFFFFFFh
0x180057435  movsx   ebp, dx
0x180057438  mov     rsi, rcx
0x18005743b  cmp     ebp, [rcx+14h]
0x18005743e  jnb     loc_1800574FF
0x180057444  mov     r14d, dword ptr cs:?LockOwner@CLockSharedData@@2PAIA; uint near * CLockSharedData::LockOwner
0x18005744b  xor     ebx, ebx
0x18005744d  mov     [rsp+38h+arg_8], ebx
0x180057451  test    r14d, r14d
0x180057454  jz      loc_180057515
0x18005745a  call    cs:__imp_GetCurrentThreadId
0x180057461  nop     dword ptr [rax+rax+00h]
0x180057466  cmp     r14d, eax
0x180057469  jnz     loc_180057515
0x18005746f  inc     cs:?LockTelemetry@CLockSharedData@@2PAULOCK_TELEMETRY@@A; LOCK_TELEMETRY near * CLockSharedData::LockTelemetry
0x180057475  cmp     ebp, [rsi+14h]
0x180057478  jnb     loc_18005754E
0x18005747e  mov     rcx, [rsi+8]
0x180057482  mov     r10d, 10h
0x180057488  mov     eax, ebp
0x18005748a  cdq
0x18005748b  idiv    r10d
0x18005748e  movsxd  r8, eax
0x180057491  mov     eax, ebp
0x180057493  cdq
0x180057494  idiv    r10d
0x180057497  mov     rcx, [rcx+r8*8]
0x18005749b  inc     edx
0x18005749d  imul    edx, [rsi+1Ch]
0x1800574a1  movsxd  rdx, edx
0x1800574a4  cmp     [rcx+rdx-4], ebx
0x1800574a8  jle     loc_18005754E
0x1800574ae  mov     r8, [rsi+8]
0x1800574b2  mov     eax, ebp
0x1800574b4  cdq
0x1800574b5  idiv    r10d
0x1800574b8  movsxd  r9, eax
0x1800574bb  mov     eax, ebp
0x1800574bd  cdq
0x1800574be  idiv    r10d
0x1800574c1  mov     rax, [r8+r9*8]
0x1800574c5  inc     edx
0x1800574c7  imul    edx, [rsi+1Ch]
0x1800574cb  movsxd  rcx, edx
0x1800574ce  inc     dword ptr [rax+rcx-4]
0x1800574d2  mov     edi, [rax+rcx-4]
0x1800574d6  lea     rcx, ?LockTelemetry@CLockSharedData@@2PAULOCK_TELEMETRY@@A; LOCK_TELEMETRY near * CLockSharedData::LockTelemetry
0x1800574dd  mov     eax, [rcx]
0x1800574df  test    eax, eax
0x1800574e1  jg      short loc_180057548
0x1800574e3  xor     ecx, ecx
0x1800574e5  mov     dword ptr cs:?LockOwner@CLockSharedData@@2PAIA, ebx; uint near * CLockSharedData::LockOwner
0x1800574eb  call    ?GetLock@CLockSharedOS@@SAAEAVCOSLock@1@W4LOCK_TYPE@@@Z; CLockSharedOS::GetLock(LOCK_TYPE)
0x1800574f0  mov     rcx, rax; SRWLock
0x1800574f3  call    cs:__imp_ReleaseSRWLockExclusive
0x1800574fa  nop     dword ptr [rax+rax+00h]
0x1800574ff  mov     rbx, [rsp+38h+arg_0]
0x180057504  mov     eax, edi
0x180057506  mov     rbp, [rsp+38h+arg_10]
0x18005750b  add     rsp, 20h
0x18005750f  pop     r14
0x180057511  pop     rdi
0x180057512  pop     rsi
0x180057513  retn
0x180057515  xor     ecx, ecx
0x180057517  call    ?GetLock@CLockSharedOS@@SAAEAVCOSLock@1@W4LOCK_TYPE@@@Z; CLockSharedOS::GetLock(LOCK_TYPE)
0x18005751c  mov     rcx, rax; SRWLock
0x18005751f  call    cs:__imp_AcquireSRWLockExclusive
0x180057526  nop     dword ptr [rax+rax+00h]
0x18005752b  call    cs:__imp_GetCurrentThreadId
0x180057532  nop     dword ptr [rax+rax+00h]
0x180057537  inc     cs:dword_1802E474C
0x18005753d  mov     dword ptr cs:?LockOwner@CLockSharedData@@2PAIA, eax; uint near * CLockSharedData::LockOwner
0x180057543  jmp     loc_180057475
0x180057548  dec     eax
0x18005754a  mov     [rcx], eax
0x18005754c  jmp     short loc_1800574FF
0x18005754e  lea     rcx, [rsp+38h+arg_8]; this
0x180057553  call    ??1CWriteLock@@QEAA@XZ; CWriteLock::~CWriteLock(void)
0x180057558  jmp     short loc_1800574FF
```
