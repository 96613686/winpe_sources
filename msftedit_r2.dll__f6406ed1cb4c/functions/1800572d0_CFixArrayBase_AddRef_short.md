# CFixArrayBase::AddRef(short)

- ea: `0x1800572d0`
- end: `0x18005740b`
- name: `?AddRef@CFixArrayBase@@QEAAJF@Z`
- size: `315`
- prototype: `__int64 __fastcall(CFixArrayBase *__hidden this, __int16)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18010ff00`

## callees

- `0x1800572d0`
- `0x180057560`
- `0x18005921c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800573d0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800573d0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800573a4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800573a4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005730a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800573dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005730a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800573dc`

## pseudocode

```c
__int64 __fastcall CFixArrayBase::AddRef(CFixArrayBase *this, __int16 a2)
{
  unsigned int v2; // ebp
  signed int v3; // esi
  int v5; // r14d
  __int64 v6; // r8
  __int64 v7; // rdx
  RTL_SRWLOCK *v8; // rax
  RTL_SRWLOCK *Lock; // rax
  DWORD CurrentThreadId; // eax
  int v12; // [rsp+48h] [rbp+10h] BYREF

  v2 = -1;
  v3 = a2;
  if ( (unsigned int)a2 < *((_DWORD *)this + 3) )
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
    if ( (unsigned int)v3 >= *((_DWORD *)this + 3)
      || *(int *)(*((_DWORD *)this + 5) * (v3 % 16 + 1) + *(_QWORD *)(*(_QWORD *)this + 8LL * (v3 / 16)) - 4LL) <= 0 )
    {
      CWriteLock::~CWriteLock((CWriteLock *)&v12);
    }
    else
    {
      v6 = *((_DWORD *)this + 5) * (v3 % 16 + 1);
      v7 = *(_QWORD *)(*(_QWORD *)this + 8LL * (v3 / 16));
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
0x1800572d0  mov     [rsp+arg_0], rbx
0x1800572d5  mov     [rsp+arg_10], rbp
0x1800572da  push    rsi
0x1800572db  push    rdi
0x1800572dc  push    r14
0x1800572de  sub     rsp, 20h
0x1800572e2  or      ebp, 0FFFFFFFFh
0x1800572e5  movsx   esi, dx
0x1800572e8  mov     rdi, rcx
0x1800572eb  cmp     esi, [rcx+0Ch]
0x1800572ee  jnb     loc_1800573B0
0x1800572f4  mov     r14d, dword ptr cs:?LockOwner@CLockSharedData@@2PAIA; uint near * CLockSharedData::LockOwner
0x1800572fb  xor     ebx, ebx
0x1800572fd  mov     [rsp+38h+arg_8], ebx
0x180057301  test    r14d, r14d
0x180057304  jz      loc_1800573C6
0x18005730a  call    cs:__imp_GetCurrentThreadId
0x180057311  nop     dword ptr [rax+rax+00h]
0x180057316  cmp     r14d, eax
0x180057319  jnz     loc_1800573C6
0x18005731f  inc     cs:?LockTelemetry@CLockSharedData@@2PAULOCK_TELEMETRY@@A; LOCK_TELEMETRY near * CLockSharedData::LockTelemetry
0x180057325  cmp     esi, [rdi+0Ch]
0x180057328  jnb     loc_1800573FF
0x18005732e  mov     eax, esi
0x180057330  mov     r9d, 10h
0x180057336  cdq
0x180057337  idiv    r9d
0x18005733a  mov     eax, esi
0x18005733c  inc     edx
0x18005733e  imul    edx, [rdi+14h]
0x180057342  movsxd  r8, edx
0x180057345  cdq
0x180057346  idiv    r9d
0x180057349  movsxd  rcx, eax
0x18005734c  mov     rax, [rdi]
0x18005734f  mov     rcx, [rax+rcx*8]
0x180057353  cmp     [r8+rcx-4], ebx
0x180057358  jle     loc_1800573FF
0x18005735e  mov     eax, esi
0x180057360  cdq
0x180057361  idiv    r9d
0x180057364  mov     eax, esi
0x180057366  inc     edx
0x180057368  imul    edx, [rdi+14h]
0x18005736c  movsxd  r8, edx
0x18005736f  cdq
0x180057370  idiv    r9d
0x180057373  movsxd  rcx, eax
0x180057376  mov     rax, [rdi]
0x180057379  mov     rdx, [rax+rcx*8]
0x18005737d  lea     rcx, ?LockTelemetry@CLockSharedData@@2PAULOCK_TELEMETRY@@A; LOCK_TELEMETRY near * CLockSharedData::LockTelemetry
0x180057384  inc     dword ptr [r8+rdx-4]
0x180057389  mov     eax, [rcx]
0x18005738b  mov     ebp, [r8+rdx-4]
0x180057390  test    eax, eax
0x180057392  jg      short loc_1800573F9
0x180057394  xor     ecx, ecx
0x180057396  mov     dword ptr cs:?LockOwner@CLockSharedData@@2PAIA, ebx; uint near * CLockSharedData::LockOwner
0x18005739c  call    ?GetLock@CLockSharedOS@@SAAEAVCOSLock@1@W4LOCK_TYPE@@@Z; CLockSharedOS::GetLock(LOCK_TYPE)
0x1800573a1  mov     rcx, rax; SRWLock
0x1800573a4  call    cs:__imp_ReleaseSRWLockExclusive
0x1800573ab  nop     dword ptr [rax+rax+00h]
0x1800573b0  mov     rbx, [rsp+38h+arg_0]
0x1800573b5  mov     eax, ebp
0x1800573b7  mov     rbp, [rsp+38h+arg_10]
0x1800573bc  add     rsp, 20h
0x1800573c0  pop     r14
0x1800573c2  pop     rdi
0x1800573c3  pop     rsi
0x1800573c4  retn
0x1800573c6  xor     ecx, ecx
0x1800573c8  call    ?GetLock@CLockSharedOS@@SAAEAVCOSLock@1@W4LOCK_TYPE@@@Z; CLockSharedOS::GetLock(LOCK_TYPE)
0x1800573cd  mov     rcx, rax; SRWLock
0x1800573d0  call    cs:__imp_AcquireSRWLockExclusive
0x1800573d7  nop     dword ptr [rax+rax+00h]
0x1800573dc  call    cs:__imp_GetCurrentThreadId
0x1800573e3  nop     dword ptr [rax+rax+00h]
0x1800573e8  inc     cs:dword_1802E474C
0x1800573ee  mov     dword ptr cs:?LockOwner@CLockSharedData@@2PAIA, eax; uint near * CLockSharedData::LockOwner
0x1800573f4  jmp     loc_180057325
0x1800573f9  dec     eax
0x1800573fb  mov     [rcx], eax
0x1800573fd  jmp     short loc_1800573B0
0x1800573ff  lea     rcx, [rsp+38h+arg_8]; this
0x180057404  call    ??1CWriteLock@@QEAA@XZ; CWriteLock::~CWriteLock(void)
0x180057409  jmp     short loc_1800573B0
```
