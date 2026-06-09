# CLockedDoubleList::InsertHead(CListEntry * const)

- ea: `0x180019cfc`
- end: `0x180019d92`
- name: `?InsertHead@CLockedDoubleList@@QEAAXQEAVCListEntry@@@Z`
- size: `150`
- prototype: `void __fastcall(CLockedDoubleList *__hidden this, struct CListEntry *const)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001a424`

## callees

- `0x180019948`
- `0x180019cfc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019d0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019d29`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019d0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019d29`

## pseudocode

```c
void __fastcall CLockedDoubleList::InsertHead(CLockedDoubleList *this, struct CListEntry *const a2)
{
  DWORD CurrentThreadId; // eax
  CSpinLock *v4; // rcx
  _QWORD *v5; // rax

  if ( LKRhash::CLKRLinearHashTable::sm_llGlobalList
    || _InterlockedCompareExchange(
         (volatile signed __int32 *)&LKRhash::CLKRLinearHashTable::sm_llGlobalList,
         GetCurrentThreadId() & 0xFFFFFFFC | 1,
         0) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v4 = (CSpinLock *)(LKRhash::CLKRLinearHashTable::sm_llGlobalList & 0xFFFFFFFC);
    if ( (_DWORD)v4 == (CurrentThreadId & 0xFFFFFFFC) )
      _InterlockedExchange(
        (volatile __int32 *)&LKRhash::CLKRLinearHashTable::sm_llGlobalList,
        LKRhash::CLKRLinearHashTable::sm_llGlobalList + 1);
    else
      CSpinLock::_LockSpin(v4);
  }
  *((_QWORD *)a2 + 1) = &off_18002B438;
  v5 = off_18002B438;
  *(_QWORD *)a2 = off_18002B438;
  v5[1] = a2;
  off_18002B438 = a2;
  _InterlockedExchange(
    (volatile __int32 *)&LKRhash::CLKRLinearHashTable::sm_llGlobalList,
    ((LKRhash::CLKRLinearHashTable::sm_llGlobalList - 1) & 3) != 0
  ? LKRhash::CLKRLinearHashTable::sm_llGlobalList - 1
  : 0);
}

```

## disassembly

```asm
0x180019cfc  push    rbx
0x180019cfe  sub     rsp, 20h
0x180019d02  mov     eax, cs:?sm_llGlobalList@CLKRLinearHashTable@LKRhash@@0VCLockedDoubleList@@A; CLockedDoubleList LKRhash::CLKRLinearHashTable::sm_llGlobalList
0x180019d08  mov     rbx, rdx
0x180019d0b  test    eax, eax
0x180019d0d  jnz     short loc_180019D29
0x180019d0f  call    cs:__imp_GetCurrentThreadId
0x180019d15  mov     ecx, eax
0x180019d17  and     ecx, 0FFFFFFFDh
0x180019d1a  or      ecx, 1
0x180019d1d  xor     eax, eax
0x180019d1f  lock cmpxchg cs:?sm_llGlobalList@CLKRLinearHashTable@LKRhash@@0VCLockedDoubleList@@A, ecx; CLockedDoubleList LKRhash::CLKRLinearHashTable::sm_llGlobalList
0x180019d27  jz      short loc_180019D54
0x180019d29  call    cs:__imp_GetCurrentThreadId
0x180019d2f  mov     ecx, cs:?sm_llGlobalList@CLKRLinearHashTable@LKRhash@@0VCLockedDoubleList@@A; CLockedDoubleList LKRhash::CLKRLinearHashTable::sm_llGlobalList
0x180019d35  and     eax, 0FFFFFFFCh
0x180019d38  and     ecx, 0FFFFFFFCh; this
0x180019d3b  cmp     ecx, eax
0x180019d3d  jnz     short loc_180019D4F
0x180019d3f  mov     eax, cs:?sm_llGlobalList@CLKRLinearHashTable@LKRhash@@0VCLockedDoubleList@@A; CLockedDoubleList LKRhash::CLKRLinearHashTable::sm_llGlobalList
0x180019d45  inc     eax
0x180019d47  xchg    eax, cs:?sm_llGlobalList@CLKRLinearHashTable@LKRhash@@0VCLockedDoubleList@@A; CLockedDoubleList LKRhash::CLKRLinearHashTable::sm_llGlobalList
0x180019d4d  jmp     short loc_180019D54
0x180019d4f  call    ?_LockSpin@CSpinLock@@AEAAXXZ; CSpinLock::_LockSpin(void)
0x180019d54  lea     rax, off_18002B438
0x180019d5b  mov     [rbx+8], rax
0x180019d5f  mov     rax, cs:off_18002B438
0x180019d66  mov     [rbx], rax
0x180019d69  mov     [rax+8], rbx
0x180019d6d  mov     edx, cs:?sm_llGlobalList@CLKRLinearHashTable@LKRhash@@0VCLockedDoubleList@@A; CLockedDoubleList LKRhash::CLKRLinearHashTable::sm_llGlobalList
0x180019d73  dec     edx
0x180019d75  mov     cs:off_18002B438, rbx
0x180019d7c  mov     eax, edx
0x180019d7e  and     al, 3
0x180019d80  neg     al
0x180019d82  sbb     ecx, ecx
0x180019d84  and     ecx, edx
0x180019d86  xchg    ecx, cs:?sm_llGlobalList@CLKRLinearHashTable@LKRhash@@0VCLockedDoubleList@@A; CLockedDoubleList LKRhash::CLKRLinearHashTable::sm_llGlobalList
0x180019d8c  add     rsp, 20h
0x180019d90  pop     rbx
0x180019d91  retn
```
