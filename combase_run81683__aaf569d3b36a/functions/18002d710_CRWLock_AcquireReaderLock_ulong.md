# CRWLock::AcquireReaderLock(ulong)

- ea: `0x18002d710`
- end: `0x18002dc83`
- name: `?AcquireReaderLock@CRWLock@@QEAAKK@Z`
- size: `1395`
- prototype: `unsigned int __fastcall(CRWLock *this, unsigned int dwDesiredTimeout)`
- caller_count: `9`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002ba40`
- `0x18002c0b4`
- `0x18002c684`
- `0x18002cd2c`
- `0x18003aa1c`
- `0x18006fc04`
- `0x18016f77c`
- `0x180173678`
- `0x18018175c`

## callees

- `0x18002d330`
- `0x18002d710`
- `0x18002dc8c`
- `0x18002dd08`
- `0x18002e4c8`
- `0x1800e76b8`
- `0x1800e7738`
- `0x1800e79b0`

## import_xrefs

- `ntdll!RtlDllShutdownInProgress` at `0x18002d95e`
- `ntdll!RtlDllShutdownInProgress` at `0x18002d9dd`
- `ntdll!RtlDllShutdownInProgress` at `0x18002da02`
- `ntdll!RtlDllShutdownInProgress` at `0x18002db3e`
- `ntdll!RtlDllShutdownInProgress` at `0x18002db63`
- `ntdll!RtlDllShutdownInProgress` at `0x18002db88`
- `ntdll!RtlDllShutdownInProgress` at `0x18002d95e`
- `ntdll!RtlDllShutdownInProgress` at `0x18002d9dd`
- `ntdll!RtlDllShutdownInProgress` at `0x18002da02`
- `ntdll!RtlDllShutdownInProgress` at `0x18002db3e`
- `ntdll!RtlDllShutdownInProgress` at `0x18002db63`
- `ntdll!RtlDllShutdownInProgress` at `0x18002db88`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002d968`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002d9e7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002da0c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002db48`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002db6d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002db92`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002d968`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002d9e7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002da0c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002db48`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002db6d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002db92`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002dba7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002dba7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002d775`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002d775`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002d9ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002da12`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002db4e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002db73`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002d9ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002da12`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002db4e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002db73`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18002d9fb`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18002da20`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18002db5c`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18002db81`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18002d9fb`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18002da20`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18002db5c`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18002db81`
- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x18002dc31`
- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x18002dc31`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002d99e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002dc11`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002d99e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002dc11`

## pseudocode

```c
__int64 __fastcall CRWLock::AcquireReaderLock(CRWLock *this, unsigned int dwDesiredTimeout)
{
  _QWORD *ReservedForOle; // rsi
  LockEntry **v5; // rsi
  LockEntry *v6; // rbx
  CRWLock *pRWLock; // rax
  unsigned __int16 wReaderLevel; // ax
  int v9; // esi
  signed __int64 lockState; // rdx
  signed __int64 v11; // r8
  signed __int64 v13; // rcx
  int v14; // r15d
  DWORD TickCount; // r12d
  EventPoolEntry *PoolEntry; // rax
  unsigned int v17; // r14d
  signed __int64 v18; // rcx
  signed __int64 v19; // rdx
  signed __int64 v20; // r9
  int v21; // r8d
  _QWORD *v22; // rdx
  LockEntry **v23; // rdx
  HANDLE CurrentProcess; // rax
  HANDLE v25; // rax
  signed __int64 v26; // rdx
  unsigned __int64 v27; // rcx
  signed __int64 v28; // r15
  EventPoolEntry *volatile v29; // rax
  EventPoolEntry *volatile pPoolEntry; // rax
  HANDLE v31; // rax
  HANDLE v32; // rax
  char *v33; // rax
  unsigned int v34; // eax
  LockEntry *v35; // rdx
  LockEntry *v36; // rcx
  CRWLock *v37; // rax
  LockEntry *v38; // rcx
  LockEntry *pPrev; // rax
  int bWaited; // [rsp+60h] [rbp+18h] BYREF

  ReservedForOle = NtCurrentTeb()->ReservedForOle;
  if ( !ReservedForOle )
  {
    if ( !RtlDllShutdownInProgress() )
      IsDebuggerPresent();
    CurrentProcess = GetCurrentProcess();
    TerminateProcess(CurrentProcess, 0x8000FFFF);
    __debugbreak();
  }
  v5 = (LockEntry **)ReservedForOle[42];
  if ( !v5 )
  {
    if ( !RtlDllShutdownInProgress() )
      IsDebuggerPresent();
    v31 = GetCurrentProcess();
    TerminateProcess(v31, 0x8000FFFF);
    __debugbreak();
  }
  v6 = *v5;
  pRWLock = (*v5)->_pRWLock;
  if ( pRWLock )
  {
    if ( pRWLock != this )
    {
      while ( 1 )
      {
        v6 = v6->_pNext;
        if ( v6 == *v5 )
          break;
        v37 = v6->_pRWLock;
        if ( !v37 || v37 == this )
        {
          v6->_pPrev->_pNext = v6->_pNext;
          v6->_pNext->_pPrev = v6->_pPrev;
          goto LABEL_98;
        }
      }
      if ( !RtlDllShutdownInProgress() )
        IsDebuggerPresent();
      v33 = (char *)HeapAlloc(g_hHeap, 0, 0x20u);
      v6 = (LockEntry *)v33;
      if ( v33 )
      {
        *(_DWORD *)(v33 + 26) = 0;
        *((_WORD *)v33 + 15) = 0;
        *(_QWORD *)v33 = 0;
        *((_QWORD *)v33 + 1) = 0;
        *((_QWORD *)v33 + 2) = 0;
        *((_WORD *)v33 + 12) = 0;
LABEL_98:
        v38 = *v5;
        v6->_pNext = *v5;
        pPrev = v38->_pPrev;
        v6->_pPrev = pPrev;
        pPrev->_pNext = v6;
        v38->_pPrev = v6;
        *v5 = v6;
        v6->_pRWLock = this;
        goto LABEL_5;
      }
      v6 = 0;
    }
  }
  else
  {
    v6->_pRWLock = this;
  }
LABEL_5:
  if ( !v6 )
    return 14;
  wReaderLevel = v6->_wReaderLevel;
  if ( wReaderLevel )
  {
    v6->_wReaderLevel = wReaderLevel + 1;
    return 0;
  }
  if ( this->_dwWriterID == GetCurrentThreadId() )
  {
    CRWLock::AcquireWriterLock(this, dwDesiredTimeout);
    LockEntry::RecycleLockEntry(v6);
    return 0;
  }
  v9 = 0;
LABEL_9:
  while ( 2 )
  {
    lockState = (signed __int64)this->_lockState;
    do
    {
      while ( 1 )
      {
        v11 = lockState;
        if ( ((unsigned int)lockState & 0x1FFFFF) >= 0xFFFFFuLL )
          break;
        lockState = _InterlockedCompareExchange64((volatile signed __int64 *)this, lockState + 1, lockState);
        if ( lockState == v11 )
        {
          if ( v9 )
            CRWLock::ReleasePoolEntry(this);
          v6->_wReaderLevel = 1;
          return 0;
        }
      }
      if ( (lockState & 0xFFFFF000000LL) == 0xFFFFF000000LL || (lockState & 0xFFFFF) == 0xFFFFF )
      {
        SleepEx(0x3E8u, 1);
        goto LABEL_9;
      }
      v13 = lockState + 0x1000000;
      v14 = 0;
      if ( (lockState & 0x600000) == 0x600000 )
      {
        v13 &= 0xFFFFFFFFFF9FFFFFuLL;
      }
      else if ( (lockState & 0x400000) != 0 )
      {
        v13 &= ~0x400000uLL;
        if ( (lockState & 0x800000) == 0 )
        {
          v13 |= 0x800000uLL;
          v14 = 1;
        }
      }
      lockState = _InterlockedCompareExchange64((volatile signed __int64 *)this, v13, lockState);
    }
    while ( lockState != v11 );
    if ( dwDesiredTimeout == -1 )
      TickCount = 0;
    else
      TickCount = GetTickCount();
    bWaited = 0;
    if ( v14 )
    {
      v17 = 0;
    }
    else if ( (*(_BYTE *)&this->_eventState & 0x21) == 0x21 )
    {
      v17 = 0;
    }
    else
    {
      PoolEntry = CRWLock::GetPoolEntry(this);
      if ( PoolEntry )
        v17 = EventPoolEntry::WaitForReaderEvent(PoolEntry, dwDesiredTimeout, &bWaited, this);
      else
        v17 = 14;
    }
    v18 = (signed __int64)this->_lockState;
    do
    {
      v9 = 0;
      v19 = v18 - 0x1000000;
      v20 = v18;
      v21 = v14;
      if ( (v18 & 0x400000) != 0 )
      {
        if ( (v18 & 0xFFFFF000000LL) == 0x1000000 )
        {
          v19 &= ~0x400000uLL;
          if ( (v18 & 0x800000) == 0 )
          {
            v21 = 1;
            v19 |= 0x800000uLL;
          }
        }
        else if ( v14 )
        {
          v21 = 0;
          v19 &= ~0x800000uLL;
        }
      }
      if ( (v19 & 0xFFFFFFFFFF800000uLL) == 0 )
      {
        pPoolEntry = this->_pPoolEntry;
        if ( pPoolEntry )
        {
          if ( ((unsigned __int8)pPoolEntry & 3) == 0 && !*(_DWORD *)&pPoolEntry->_eventState )
          {
            v9 = 1;
            v19 |= 0x600000uLL;
          }
        }
      }
      v18 = _InterlockedCompareExchange64((volatile signed __int64 *)this, v19, v18);
    }
    while ( v18 != v20 );
    if ( v21 )
    {
      CRWLock::RWResetReaderSignal(this);
      v26 = (signed __int64)this->_lockState;
      do
      {
        v9 = 0;
        v27 = v26 & 0xFFFFFFFFFF7FFFFFuLL;
        v28 = v26;
        if ( (v26 & 0xFFFFFFFFFF000000uLL) == 0 )
        {
          v29 = this->_pPoolEntry;
          if ( v29 )
          {
            if ( ((unsigned __int8)v29 & 3) == 0 && !*(_DWORD *)&v29->_eventState )
            {
              v9 = 1;
              v27 = v26 & 0xFFFFFFFFFF1FFFFFuLL | 0x600000;
            }
          }
        }
        v26 = _InterlockedCompareExchange64((volatile signed __int64 *)this, v27, v26);
      }
      while ( v26 != v28 );
      if ( (v28 & 0x400000) != 0 )
        CRWLock::RWSetReaderSignal(this);
      if ( (v28 & 0xFFFFF00000000000uLL) != 0 && (v28 & 0xFFFFFFFFFFFLL) == 0 )
        v17 = 0;
    }
    if ( dwDesiredTimeout == -1 )
      goto LABEL_31;
    v34 = GetTickCount() - TickCount;
    if ( v34 < dwDesiredTimeout )
    {
      dwDesiredTimeout -= v34;
LABEL_31:
      if ( !v17 )
        continue;
      goto LABEL_32;
    }
    break;
  }
  v17 = 258;
LABEL_32:
  if ( v9 )
    CRWLock::ReleasePoolEntry(this);
  v22 = NtCurrentTeb()->ReservedForOle;
  if ( !v22 )
  {
    if ( !RtlDllShutdownInProgress() )
      IsDebuggerPresent();
    v25 = GetCurrentProcess();
    TerminateProcess(v25, 0x8000FFFF);
    __debugbreak();
  }
  v23 = (LockEntry **)v22[42];
  if ( !v23 )
  {
    if ( !RtlDllShutdownInProgress() )
      IsDebuggerPresent();
    v32 = GetCurrentProcess();
    TerminateProcess(v32, 0x8000FFFF);
    __debugbreak();
  }
  if ( v6 == *v23 )
  {
    *v23 = (*v23)->_pNext;
  }
  else if ( v6->_pNext->_pRWLock )
  {
    v6->_pPrev->_pNext = v6->_pNext;
    v6->_pNext->_pPrev = v6->_pPrev;
    v35 = *v23;
    v6->_pNext = v35;
    v36 = v35->_pPrev;
    v6->_pPrev = v36;
    v36->_pNext = v6;
    v35->_pPrev = v6;
  }
  v6->_pRWLock = 0;
  if ( !RtlDllShutdownInProgress() )
    IsDebuggerPresent();
  return v17;
}

```

## disassembly

```asm
0x18002d710  push    rbp
0x18002d712  push    rsi
0x18002d713  push    rdi
0x18002d714  sub     rsp, 30h
0x18002d718  mov     rax, gs:30h
0x18002d721  mov     ebp, dwDesiredTimeout
0x18002d723  mov     rdi, this
0x18002d726  mov     rsi, [rax+1758h]
0x18002d72d  test    rsi, rsi
0x18002d730  jz      loc_18002D9DD
0x18002d736  mov     rsi, [rsi+150h]
0x18002d73d  test    rsi, rsi
0x18002d740  jz      loc_18002DB3E
0x18002d746  mov     [rsp+48h+arg_0], rbx
0x18002d74b  mov     rbx, [rsi]
0x18002d74e  mov     rax, [rbx+10h]
0x18002d752  test    rax, rax
0x18002d755  jnz     loc_18002DBDA
0x18002d75b  mov     [rbx+10h], this
0x18002d75f  test    rbx, rbx
0x18002d762  jz      loc_18002DA27
0x18002d768  movzx   eax, word ptr [rbx+18h]
0x18002d76c  test    ax, ax
0x18002d76f  jnz     loc_18002DBEB
0x18002d775  call    cs:__imp_GetCurrentThreadId
0x18002d77b  mov     ecx, [rdi+0Ch]
0x18002d77e  cmp     ecx, eax
0x18002d780  jz      loc_18002D9BC
0x18002d786  mov     [rsp+48h+arg_18], r13
0x18002d78b  xor     esi, esi
0x18002d78d  mov     [rsp+48h+var_28], r15
0x18002d792  mov     r13d, 1
0x18002d798  mov     [rsp+48h+arg_8], r12
0x18002d79d  mov     [rsp+48h+var_20], r14
0x18002d7a2  mov     rdx, [rdi]
0x18002d7a5  mov     r9, 0FFFFF000000h
0x18002d7af  mov     this, rdx
0x18002d7b2  mov     r8, rdx
0x18002d7b5  and     ecx, 1FFFFFh
0x18002d7bb  mov     rax, rdx
0x18002d7be  cmp     this, 0FFFFFh
0x18002d7c5  jnb     short loc_18002D808
0x18002d7c7  lea     this, [rdx+1]
0x18002d7cb  lock cmpxchg [rdi], this
0x18002d7d0  mov     rdx, rax
0x18002d7d3  cmp     rax, r8
0x18002d7d6  jnz     short loc_18002D7AF
0x18002d7d8  test    esi, esi
0x18002d7da  jnz     loc_18002DA39
0x18002d7e0  mov     [rbx+18h], r13w
0x18002d7e5  xor     eax, eax
0x18002d7e7  mov     r14, [rsp+48h+var_20]
0x18002d7ec  mov     r12, [rsp+48h+arg_8]
0x18002d7f1  mov     r13, [rsp+48h+arg_18]
0x18002d7f6  mov     r15, [rsp+48h+var_28]
0x18002d7fb  mov     rbx, [rsp+48h+arg_0]
0x18002d800  add     rsp, 30h
0x18002d804  pop     rdi
0x18002d805  pop     rsi
0x18002d806  pop     rbp
0x18002d807  retn
0x18002d808  and     rax, r9
0x18002d80b  cmp     rax, r9
0x18002d80e  mov     rax, rdx
0x18002d811  setnz   cl
0x18002d814  and     eax, 0FFFFFh
0x18002d819  cmp     rax, 0FFFFFh
0x18002d81f  setnz   al
0x18002d822  test    al, cl
0x18002d824  jz      loc_18002DC29
0x18002d82a  mov     rax, rdx
0x18002d82d  lea     this, [rdx+1000000h]
0x18002d834  and     eax, 600000h
0x18002d839  xor     r15d, r15d
0x18002d83c  cmp     rax, 600000h
0x18002d842  jnz     loc_18002D976
0x18002d848  and     this, 0FFFFFFFFFF9FFFFFh
0x18002d84f  mov     rax, rdx
0x18002d852  lock cmpxchg [rdi], this
0x18002d857  mov     rdx, rax
0x18002d85a  cmp     rax, r8
0x18002d85d  jnz     loc_18002D7AF
0x18002d863  cmp     ebp, 0FFFFFFFFh
0x18002d866  jnz     loc_18002D99E
0x18002d86c  xor     r12d, r12d
0x18002d86f  mov     [rsp+48h+bWaited], 0
0x18002d877  test    r15d, r15d
0x18002d87a  jnz     loc_18002D9AC
0x18002d880  mov     eax, [rdi+18h]
0x18002d883  and     eax, 21h
0x18002d886  cmp     al, 21h ; '!'
0x18002d888  jz      loc_18002D9B4
0x18002d88e  mov     this, rdi; this
0x18002d891  call    ?GetPoolEntry@CRWLock@@AEAAREAVEventPoolEntry@@XZ; CRWLock::GetPoolEntry(void)
0x18002d896  test    rax, rax
0x18002d899  jz      loc_18002DBF9
0x18002d89f  mov     r9, rdi; pLock
0x18002d8a2  lea     r8, [rsp+48h+bWaited]; bWaited
0x18002d8a7  mov     dwDesiredTimeout, ebp; dwTimeout
0x18002d8a9  mov     this, rax; this
0x18002d8ac  call    ?WaitForReaderEvent@EventPoolEntry@@QEAAKKAEAHPEAVCRWLock@@@Z; EventPoolEntry::WaitForReaderEvent(ulong,int &,CRWLock *)
0x18002d8b1  mov     r14d, eax
0x18002d8b4  mov     this, [rdi]
0x18002d8b7  mov     r10, 0FFFFF000000h
0x18002d8c1  xor     esi, esi
0x18002d8c3  lea     rdx, [this-1000000h]
0x18002d8ca  mov     r9, this
0x18002d8cd  mov     r8d, r15d
0x18002d8d0  bt      this, 16h
0x18002d8d5  jb      loc_18002DACF
0x18002d8db  test    rdx, 0FFFFFFFFFF800000h
0x18002d8e2  jz      loc_18002DAFA
0x18002d8e8  mov     rax, this
0x18002d8eb  lock cmpxchg [rdi], rdx
0x18002d8f0  mov     this, rax
0x18002d8f3  cmp     rax, r9
0x18002d8f6  jnz     short loc_18002D8C1
0x18002d8f8  test    r8d, r8d
0x18002d8fb  jnz     loc_18002DA46
0x18002d901  cmp     ebp, 0FFFFFFFFh
0x18002d904  jnz     loc_18002DC11
0x18002d90a  test    r14d, r14d
0x18002d90d  jz      loc_18002D7A2
0x18002d913  test    esi, esi
0x18002d915  jnz     loc_18002DC3C
0x18002d91b  mov     rax, gs:30h
0x18002d924  mov     rdx, [rax+1758h]
0x18002d92b  test    rdx, rdx
0x18002d92e  jz      loc_18002DA02
0x18002d934  mov     rdx, [rdx+150h]
0x18002d93b  test    rdx, rdx
0x18002d93e  jz      loc_18002DB63
0x18002d944  mov     rax, [rdx]
0x18002d947  cmp     rbx, rax
0x18002d94a  jnz     loc_18002DC49
0x18002d950  mov     rax, [rax]
0x18002d953  mov     [rdx], rax
0x18002d956  mov     qword ptr [rbx+10h], 0
0x18002d95e  call    cs:__imp_RtlDllShutdownInProgress
0x18002d964  test    al, al
0x18002d966  jnz     short loc_18002D96E
0x18002d968  call    cs:__imp_IsDebuggerPresent
0x18002d96e  mov     eax, r14d
0x18002d971  jmp     loc_18002D7E7
0x18002d976  bt      rdx, 16h
0x18002d97b  jnb     loc_18002D84F
0x18002d981  btr     this, 16h
0x18002d986  bt      rdx, 17h
0x18002d98b  jb      loc_18002D84F
0x18002d991  bts     this, 17h
0x18002d996  mov     r15d, r13d
0x18002d999  jmp     loc_18002D84F
0x18002d99e  call    cs:__imp_GetTickCount
0x18002d9a4  mov     r12d, eax
0x18002d9a7  jmp     loc_18002D86F
0x18002d9ac  xor     r14d, r14d
0x18002d9af  jmp     loc_18002D8B4
0x18002d9b4  xor     r14d, r14d
0x18002d9b7  jmp     loc_18002D8B4
0x18002d9bc  mov     dwDesiredTimeout, ebp; dwDesiredTimeout
0x18002d9be  mov     this, rdi; this
0x18002d9c1  call    ?AcquireWriterLock@CRWLock@@QEAAKK@Z; CRWLock::AcquireWriterLock(ulong)
0x18002d9c6  mov     this, rbx; this
0x18002d9c9  call    ?RecycleLockEntry@LockEntry@@QEAAXXZ; LockEntry::RecycleLockEntry(void)
0x18002d9ce  mov     rbx, [rsp+48h+arg_0]
0x18002d9d3  xor     eax, eax
0x18002d9d5  add     rsp, 30h
0x18002d9d9  pop     rdi
0x18002d9da  pop     rsi
0x18002d9db  pop     rbp
0x18002d9dc  retn
0x18002d9dd  call    cs:__imp_RtlDllShutdownInProgress
0x18002d9e3  test    al, al
0x18002d9e5  jnz     short loc_18002D9ED
0x18002d9e7  call    cs:__imp_IsDebuggerPresent
0x18002d9ed  call    cs:__imp_GetCurrentProcess
0x18002d9f3  mov     this, rax; hProcess
0x18002d9f6  mov     dwDesiredTimeout, 8000FFFFh; uExitCode
0x18002d9fb  call    cs:__imp_TerminateProcess
0x18002da01  int     3; Trap to Debugger
0x18002da02  call    cs:__imp_RtlDllShutdownInProgress
0x18002da08  test    al, al
0x18002da0a  jnz     short loc_18002DA12
0x18002da0c  call    cs:__imp_IsDebuggerPresent
0x18002da12  call    cs:__imp_GetCurrentProcess
0x18002da18  mov     this, rax; hProcess
0x18002da1b  mov     dwDesiredTimeout, 8000FFFFh; uExitCode
0x18002da20  call    cs:__imp_TerminateProcess
0x18002da26  int     3; Trap to Debugger
0x18002da27  mov     rbx, [rsp+48h+arg_0]
0x18002da2c  mov     eax, 0Eh
0x18002da31  add     rsp, 30h
0x18002da35  pop     rdi
0x18002da36  pop     rsi
0x18002da37  pop     rbp
0x18002da38  retn
0x18002da39  mov     this, rdi; this
0x18002da3c  call    ?ReleasePoolEntry@CRWLock@@AEAAHXZ; CRWLock::ReleasePoolEntry(void)
0x18002da41  jmp     loc_18002D7E0
0x18002da46  mov     this, rdi; this
0x18002da49  call    ?RWResetReaderSignal@CRWLock@@AEAAXXZ; CRWLock::RWResetReaderSignal(void)
0x18002da4e  mov     rdx, [rdi]
0x18002da51  mov     this, rdx
0x18002da54  xor     esi, esi
0x18002da56  btr     this, 17h
0x18002da5b  mov     r15, rdx
0x18002da5e  test    rdx, 0FFFFFFFFFF000000h
0x18002da65  jnz     short loc_18002DA84
0x18002da67  mov     rax, [rdi+18h]
0x18002da6b  test    rax, rax
0x18002da6e  jz      short loc_18002DA84
0x18002da70  test    al, 3
0x18002da72  jnz     short loc_18002DA84
0x18002da74  mov     eax, [rax]
0x18002da76  test    eax, eax
0x18002da78  jnz     short loc_18002DA84
0x18002da7a  mov     esi, r13d
0x18002da7d  or      this, 600000h
0x18002da84  mov     rax, rdx
0x18002da87  lock cmpxchg [rdi], this
0x18002da8c  mov     rdx, rax
0x18002da8f  cmp     rax, r15
0x18002da92  jnz     short loc_18002DA51
0x18002da94  bt      r15, 16h
0x18002da99  jb      loc_18002DC04
0x18002da9f  mov     rax, 0FFFFF00000000000h
0x18002daa9  test    rax, r15
0x18002daac  mov     rax, 0FFFFFFFFFFFh
0x18002dab6  setnz   cl
0x18002dab9  test    rax, r15
0x18002dabc  setz    al
0x18002dabf  test    al, cl
0x18002dac1  jz      loc_18002D901
0x18002dac7  xor     r14d, r14d
0x18002daca  jmp     loc_18002D901
0x18002dacf  mov     rax, this
0x18002dad2  and     rax, r10
0x18002dad5  cmp     rax, 1000000h
0x18002dadb  jnz     short loc_18002DB28
0x18002dadd  btr     rdx, 16h
0x18002dae2  bt      this, 17h
0x18002dae7  jb      loc_18002D8DB
0x18002daed  mov     r8d, r13d
0x18002daf0  bts     rdx, 17h
0x18002daf5  jmp     loc_18002D8DB
0x18002dafa  mov     rax, [rdi+18h]
0x18002dafe  test    rax, rax
0x18002db01  jz      loc_18002D8E8
0x18002db07  test    al, 3
0x18002db09  jnz     loc_18002D8E8
0x18002db0f  mov     eax, [rax]
0x18002db11  test    eax, eax
0x18002db13  jnz     loc_18002D8E8
0x18002db19  mov     esi, r13d
0x18002db1c  or      rdx, 600000h
0x18002db23  jmp     loc_18002D8E8
0x18002db28  test    r15d, r15d
0x18002db2b  jz      loc_18002D8DB
0x18002db31  xor     r8d, r8d
0x18002db34  btr     rdx, 17h
0x18002db39  jmp     loc_18002D8DB
0x18002db3e  call    cs:__imp_RtlDllShutdownInProgress
0x18002db44  test    al, al
0x18002db46  jnz     short loc_18002DB4E
0x18002db48  call    cs:__imp_IsDebuggerPresent
0x18002db4e  call    cs:__imp_GetCurrentProcess
0x18002db54  mov     this, rax; hProcess
0x18002db57  mov     dwDesiredTimeout, 8000FFFFh; uExitCode
0x18002db5c  call    cs:__imp_TerminateProcess
0x18002db62  int     3; Trap to Debugger
0x18002db63  call    cs:__imp_RtlDllShutdownInProgress
0x18002db69  test    al, al
0x18002db6b  jnz     short loc_18002DB73
0x18002db6d  call    cs:__imp_IsDebuggerPresent
0x18002db73  call    cs:__imp_GetCurrentProcess
0x18002db79  mov     this, rax; hProcess
0x18002db7c  mov     dwDesiredTimeout, 8000FFFFh; uExitCode
0x18002db81  call    cs:__imp_TerminateProcess
0x18002db87  int     3; Trap to Debugger
0x18002db88  call    cs:__imp_RtlDllShutdownInProgress
0x18002db8e  test    al, al
0x18002db90  jnz     short loc_18002DB98
0x18002db92  call    cs:__imp_IsDebuggerPresent
0x18002db98  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x18002db9f  xor     dwDesiredTimeout, dwDesiredTimeout; dwFlags
0x18002dba1  mov     r8d, 20h ; ' '; dwBytes
0x18002dba7  call    cs:__imp_HeapAlloc
0x18002dbad  mov     rbx, rax
0x18002dbb0  test    rax, rax
0x18002dbb3  jz      loc_1802463F8
0x18002dbb9  mov     dword ptr [rax+1Ah], 0
0x18002dbc0  xor     eax, eax
0x18002dbc2  mov     [rbx+1Eh], ax
0x18002dbc6  mov     [rbx], rax
0x18002dbc9  mov     [rbx+8], rax
0x18002dbcd  mov     [rbx+10h], rax
0x18002dbd1  mov     [rbx+18h], ax
0x18002dbd5  jmp     loc_1802463D7
0x18002dbda  cmp     rax, rdi
0x18002dbdd  jz      loc_18002D75F
  ... truncated ...
```
