# CCharFormatArray::Release(short)

- ea: `0x1800b9050`
- end: `0x1800b91a8`
- name: `?Release@CCharFormatArray@@UEAAJF@Z`
- size: `344`
- prototype: `__int64 __fastcall(CCharFormatArray *__hidden this, __int16)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18005921c`
- `0x1800b9050`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b913f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b913f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b9120`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b9120`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b9081`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b914b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b9081`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b914b`

## pseudocode

```c
__int64 __fastcall CCharFormatArray::Release(CCharFormatArray *this, __int16 a2)
{
  unsigned int v2; // esi
  unsigned int v3; // edi
  int v5; // ebp
  int v6; // r8d
  __int64 v7; // r9
  __int64 v8; // rdx
  __int64 v9; // rcx
  bool v10; // zf
  DWORD CurrentThreadId; // eax
  int v13; // [rsp+58h] [rbp+10h] BYREF

  v2 = -1;
  v3 = a2;
  if ( (unsigned int)a2 < *((_DWORD *)this + 5) )
  {
    v5 = (int)CLockSharedData::LockOwner;
    v13 = 0;
    if ( (_DWORD)CLockSharedData::LockOwner && v5 == GetCurrentThreadId() )
    {
      LODWORD(CLockSharedData::LockTelemetry) = (_DWORD)CLockSharedData::LockTelemetry + 1;
    }
    else
    {
      AcquireSRWLockExclusive(&SRW_RELock);
      CurrentThreadId = GetCurrentThreadId();
      ++dword_1802E474C[0];
      LODWORD(CLockSharedData::LockOwner) = CurrentThreadId;
    }
    if ( v3 >= *((_DWORD *)this + 5)
      || *(int *)(*((_DWORD *)this + 7) * ((int)v3 % 16 + 1)
                + *(_QWORD *)(*((_QWORD *)this + 1) + 8LL * ((int)v3 / 16))
                - 4LL) <= 0 )
    {
      CWriteLock::~CWriteLock((CWriteLock *)&v13);
    }
    else
    {
      v6 = (int)v3 % 16 + 1;
      v7 = (int)v3 / 16;
      v8 = *((_DWORD *)this + 7) * v6;
      v9 = *(_QWORD *)(*((_QWORD *)this + 1) + 8 * v7);
      v10 = (*(_DWORD *)(v8 + v9 - 4))-- == 1;
      v2 = *(_DWORD *)(v8 + v9 - 4);
      if ( v10 && v3 < *((_DWORD *)this + 5) )
      {
        *(_DWORD *)(*((_DWORD *)this + 7) * v6 + *(_QWORD *)(*((_QWORD *)this + 1) + 8 * v7) - 4LL) = *((_DWORD *)this + 6);
        *((_DWORD *)this + 6) = v3 | 0x80000000;
      }
      if ( (int)CLockSharedData::LockTelemetry > 0 )
      {
        LODWORD(CLockSharedData::LockTelemetry) = (_DWORD)CLockSharedData::LockTelemetry - 1;
      }
      else
      {
        LODWORD(CLockSharedData::LockOwner) = 0;
        ReleaseSRWLockExclusive(&SRW_RELock);
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1800b9050  push    rbx
0x1800b9052  push    rbp
0x1800b9053  push    rsi
0x1800b9054  push    rdi
0x1800b9055  sub     rsp, 28h
0x1800b9059  or      esi, 0FFFFFFFFh
0x1800b905c  movsx   edi, dx
0x1800b905f  mov     rbx, rcx
0x1800b9062  cmp     edi, [rcx+14h]
0x1800b9065  jnb     loc_1800B912C
0x1800b906b  mov     ebp, dword ptr cs:?LockOwner@CLockSharedData@@2PAIA; uint near * CLockSharedData::LockOwner
0x1800b9071  mov     [rsp+48h+arg_8], 0
0x1800b9079  test    ebp, ebp
0x1800b907b  jz      loc_1800B9138
0x1800b9081  call    cs:__imp_GetCurrentThreadId
0x1800b9088  nop     dword ptr [rax+rax+00h]
0x1800b908d  cmp     ebp, eax
0x1800b908f  jnz     loc_1800B9138
0x1800b9095  inc     cs:?LockTelemetry@CLockSharedData@@2PAULOCK_TELEMETRY@@A; LOCK_TELEMETRY near * CLockSharedData::LockTelemetry
0x1800b909b  cmp     edi, [rbx+14h]
0x1800b909e  jnb     loc_1800B919C
0x1800b90a4  mov     eax, edi
0x1800b90a6  mov     r9d, 10h
0x1800b90ac  cdq
0x1800b90ad  idiv    r9d
0x1800b90b0  mov     eax, edi
0x1800b90b2  inc     edx
0x1800b90b4  imul    edx, [rbx+1Ch]
0x1800b90b8  movsxd  r8, edx
0x1800b90bb  cdq
0x1800b90bc  idiv    r9d
0x1800b90bf  movsxd  rcx, eax
0x1800b90c2  mov     rax, [rbx+8]
0x1800b90c6  mov     rcx, [rax+rcx*8]
0x1800b90ca  cmp     dword ptr [r8+rcx-4], 0
0x1800b90d0  jle     loc_1800B919C
0x1800b90d6  mov     eax, edi
0x1800b90d8  cdq
0x1800b90d9  idiv    r9d
0x1800b90dc  mov     eax, edi
0x1800b90de  lea     r8d, [rdx+1]
0x1800b90e2  cdq
0x1800b90e3  idiv    r9d
0x1800b90e6  movsxd  r9, eax
0x1800b90e9  mov     eax, r8d
0x1800b90ec  imul    eax, [rbx+1Ch]
0x1800b90f0  movsxd  rdx, eax
0x1800b90f3  mov     rax, [rbx+8]
0x1800b90f7  mov     rcx, [rax+r9*8]
0x1800b90fb  add     [rdx+rcx-4], esi
0x1800b90ff  mov     esi, [rdx+rcx-4]
0x1800b9103  jz      short loc_1800B9172
0x1800b9105  mov     eax, cs:?LockTelemetry@CLockSharedData@@2PAULOCK_TELEMETRY@@A; LOCK_TELEMETRY near * CLockSharedData::LockTelemetry
0x1800b910b  test    eax, eax
0x1800b910d  jg      short loc_1800B9168
0x1800b910f  lea     rcx, ?SRW_RELock@@3U_RTL_SRWLOCK@@A; SRWLock
0x1800b9116  mov     dword ptr cs:?LockOwner@CLockSharedData@@2PAIA, 0; uint near * CLockSharedData::LockOwner
0x1800b9120  call    cs:__imp_ReleaseSRWLockExclusive
0x1800b9127  nop     dword ptr [rax+rax+00h]
0x1800b912c  mov     eax, esi
0x1800b912e  add     rsp, 28h
0x1800b9132  pop     rdi
0x1800b9133  pop     rsi
0x1800b9134  pop     rbp
0x1800b9135  pop     rbx
0x1800b9136  retn
0x1800b9138  lea     rcx, ?SRW_RELock@@3U_RTL_SRWLOCK@@A; SRWLock
0x1800b913f  call    cs:__imp_AcquireSRWLockExclusive
0x1800b9146  nop     dword ptr [rax+rax+00h]
0x1800b914b  call    cs:__imp_GetCurrentThreadId
0x1800b9152  nop     dword ptr [rax+rax+00h]
0x1800b9157  inc     cs:dword_1802E474C
0x1800b915d  mov     dword ptr cs:?LockOwner@CLockSharedData@@2PAIA, eax; uint near * CLockSharedData::LockOwner
0x1800b9163  jmp     loc_1800B909B
0x1800b9168  dec     eax
0x1800b916a  mov     cs:?LockTelemetry@CLockSharedData@@2PAULOCK_TELEMETRY@@A, eax; LOCK_TELEMETRY near * CLockSharedData::LockTelemetry
0x1800b9170  jmp     short loc_1800B912C
0x1800b9172  cmp     edi, [rbx+14h]
0x1800b9175  jnb     short loc_1800B9105
0x1800b9177  imul    r8d, [rbx+1Ch]
0x1800b917c  mov     rax, [rbx+8]
0x1800b9180  or      edi, 80000000h
0x1800b9186  mov     rcx, [rax+r9*8]
0x1800b918a  mov     eax, [rbx+18h]
0x1800b918d  movsxd  rdx, r8d
0x1800b9190  mov     [rdx+rcx-4], eax
0x1800b9194  mov     [rbx+18h], edi
0x1800b9197  jmp     loc_1800B9105
0x1800b919c  lea     rcx, [rsp+48h+arg_8]; this
0x1800b91a1  call    ??1CWriteLock@@QEAA@XZ; CWriteLock::~CWriteLock(void)
0x1800b91a6  jmp     short loc_1800B912C
```
