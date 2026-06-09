# CFixArrayBase::Release(short)

- ea: `0x18000ed34`
- end: `0x18000ee88`
- name: `?Release@CFixArrayBase@@QEAAJF@Z`
- size: `340`
- prototype: `__int64 __fastcall(CFixArrayBase *__hidden this, __int16)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e040`
- `0x18000ee90`

## callees

- `0x18000ed34`
- `0x18005921c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ee20`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ee20`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ee01`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ee01`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ed65`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ee2c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ed65`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ee2c`

## pseudocode

```c
__int64 __fastcall CFixArrayBase::Release(CFixArrayBase *this, __int16 a2)
{
  unsigned int v2; // esi
  signed int v3; // edi
  int v5; // ebp
  __int64 v6; // r9
  __int64 v7; // rdx
  __int64 v8; // rcx
  bool v9; // zf
  DWORD CurrentThreadId; // eax
  int v12; // [rsp+58h] [rbp+10h] BYREF

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
      AcquireSRWLockExclusive(&SRW_RELock);
      CurrentThreadId = GetCurrentThreadId();
      ++dword_1802E474C[0];
      LODWORD(CLockSharedData::LockOwner) = CurrentThreadId;
    }
    if ( (unsigned int)v3 >= *((_DWORD *)this + 3)
      || *(int *)(*(_QWORD *)(*(_QWORD *)this + 8LL * (v3 / 16)) + *((_DWORD *)this + 5) * (v3 % 16 + 1) - 4LL) <= 0 )
    {
      CWriteLock::~CWriteLock((CWriteLock *)&v12);
    }
    else
    {
      v6 = v3 / 16;
      v7 = *((_DWORD *)this + 5) * (v3 % 16 + 1);
      v8 = *(_QWORD *)(*(_QWORD *)this + 8 * v6);
      v9 = (*(_DWORD *)(v7 + v8 - 4))-- == 1;
      v2 = *(_DWORD *)(v7 + v8 - 4);
      if ( v9 && (unsigned int)v3 < *((_DWORD *)this + 3) )
      {
        *(_DWORD *)(*((_DWORD *)this + 5) * (v3 % 16 + 1) + *(_QWORD *)(*(_QWORD *)this + 8 * v6) - 4LL) = *((_DWORD *)this + 4);
        *((_DWORD *)this + 4) = v3 | 0x80000000;
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
0x18000ed34  push    rbx
0x18000ed36  push    rbp
0x18000ed37  push    rsi
0x18000ed38  push    rdi
0x18000ed39  sub     rsp, 28h
0x18000ed3d  or      esi, 0FFFFFFFFh
0x18000ed40  movsx   edi, dx
0x18000ed43  mov     rbx, rcx
0x18000ed46  cmp     edi, [rcx+0Ch]
0x18000ed49  jnb     loc_18000EE0D
0x18000ed4f  mov     ebp, dword ptr cs:?LockOwner@CLockSharedData@@2PAIA; uint near * CLockSharedData::LockOwner
0x18000ed55  mov     [rsp+48h+arg_8], 0
0x18000ed5d  test    ebp, ebp
0x18000ed5f  jz      loc_18000EE19
0x18000ed65  call    cs:__imp_GetCurrentThreadId
0x18000ed6c  nop     dword ptr [rax+rax+00h]
0x18000ed71  cmp     ebp, eax
0x18000ed73  jnz     loc_18000EE19
0x18000ed79  inc     cs:?LockTelemetry@CLockSharedData@@2PAULOCK_TELEMETRY@@A; LOCK_TELEMETRY near * CLockSharedData::LockTelemetry
0x18000ed7f  cmp     edi, [rbx+0Ch]
0x18000ed82  jnb     loc_18000EE7C
0x18000ed88  mov     r8, [rbx]
0x18000ed8b  mov     eax, edi
0x18000ed8d  cdq
0x18000ed8e  mov     r10d, 10h
0x18000ed94  idiv    r10d
0x18000ed97  movsxd  r9, eax
0x18000ed9a  mov     eax, edi
0x18000ed9c  cdq
0x18000ed9d  idiv    r10d
0x18000eda0  mov     rax, [r8+r9*8]
0x18000eda4  inc     edx
0x18000eda6  imul    edx, [rbx+14h]
0x18000edaa  movsxd  rcx, edx
0x18000edad  cmp     dword ptr [rax+rcx-4], 0
0x18000edb2  jle     loc_18000EE7C
0x18000edb8  mov     eax, edi
0x18000edba  cdq
0x18000edbb  idiv    r10d
0x18000edbe  mov     eax, edi
0x18000edc0  lea     r8d, [rdx+1]
0x18000edc4  cdq
0x18000edc5  idiv    r10d
0x18000edc8  movsxd  r9, eax
0x18000edcb  mov     eax, r8d
0x18000edce  imul    eax, [rbx+14h]
0x18000edd2  movsxd  rdx, eax
0x18000edd5  mov     rax, [rbx]
0x18000edd8  mov     rcx, [rax+r9*8]
0x18000eddc  add     [rdx+rcx-4], esi
0x18000ede0  mov     esi, [rdx+rcx-4]
0x18000ede4  jz      short loc_18000EE53
0x18000ede6  mov     eax, cs:?LockTelemetry@CLockSharedData@@2PAULOCK_TELEMETRY@@A; LOCK_TELEMETRY near * CLockSharedData::LockTelemetry
0x18000edec  test    eax, eax
0x18000edee  jg      short loc_18000EE49
0x18000edf0  lea     rcx, ?SRW_RELock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18000edf7  mov     dword ptr cs:?LockOwner@CLockSharedData@@2PAIA, 0; uint near * CLockSharedData::LockOwner
0x18000ee01  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ee08  nop     dword ptr [rax+rax+00h]
0x18000ee0d  mov     eax, esi
0x18000ee0f  add     rsp, 28h
0x18000ee13  pop     rdi
0x18000ee14  pop     rsi
0x18000ee15  pop     rbp
0x18000ee16  pop     rbx
0x18000ee17  retn
0x18000ee19  lea     rcx, ?SRW_RELock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18000ee20  call    cs:__imp_AcquireSRWLockExclusive
0x18000ee27  nop     dword ptr [rax+rax+00h]
0x18000ee2c  call    cs:__imp_GetCurrentThreadId
0x18000ee33  nop     dword ptr [rax+rax+00h]
0x18000ee38  inc     cs:dword_1802E474C
0x18000ee3e  mov     dword ptr cs:?LockOwner@CLockSharedData@@2PAIA, eax; uint near * CLockSharedData::LockOwner
0x18000ee44  jmp     loc_18000ED7F
0x18000ee49  dec     eax
0x18000ee4b  mov     cs:?LockTelemetry@CLockSharedData@@2PAULOCK_TELEMETRY@@A, eax; LOCK_TELEMETRY near * CLockSharedData::LockTelemetry
0x18000ee51  jmp     short loc_18000EE0D
0x18000ee53  cmp     edi, [rbx+0Ch]
0x18000ee56  jnb     short loc_18000EDE6
0x18000ee58  imul    r8d, [rbx+14h]
0x18000ee5d  mov     rax, [rbx]
0x18000ee60  or      edi, 80000000h
0x18000ee66  mov     rcx, [rax+r9*8]
0x18000ee6a  mov     eax, [rbx+10h]
0x18000ee6d  movsxd  rdx, r8d
0x18000ee70  mov     [rdx+rcx-4], eax
0x18000ee74  mov     [rbx+10h], edi
0x18000ee77  jmp     loc_18000EDE6
0x18000ee7c  lea     rcx, [rsp+48h+arg_8]; this
0x18000ee81  call    ??1CWriteLock@@QEAA@XZ; CWriteLock::~CWriteLock(void)
0x18000ee86  jmp     short loc_18000EE0D
```
