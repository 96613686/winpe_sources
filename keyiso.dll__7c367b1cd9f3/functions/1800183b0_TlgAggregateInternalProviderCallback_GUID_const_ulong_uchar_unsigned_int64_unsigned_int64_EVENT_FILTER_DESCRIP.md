# TlgAggregateInternalProviderCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)

- ea: `0x1800183b0`
- end: `0x180018401`
- name: `?TlgAggregateInternalProviderCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z`
- size: `81`
- prototype: `void __fastcall(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180017f88`
- `0x1800183b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x1800183c7`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x1800183c7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800183f5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800183f5`

## pseudocode

```c
void __fastcall TlgAggregateInternalProviderCallback(const struct _GUID *a1, int a2, __int64 a3, __int64 a4)
{
  __int64 i; // rbx

  if ( a2 == 2 && a4 == 32 && TryAcquireSRWLockExclusive(&SRWLock) )
  {
    for ( i = qword_180026010; i; i = *(_QWORD *)(i + 336) )
      LookUpTableFlushComplete(i);
    ReleaseSRWLockExclusive(&SRWLock);
  }
}

```

## disassembly

```asm
0x1800183b0  cmp     edx, 2
0x1800183b3  jnz     short locret_180018400
0x1800183b5  push    rbx
0x1800183b6  sub     rsp, 20h
0x1800183ba  cmp     r9, 20h ; ' '
0x1800183be  jnz     short loc_1800183FB
0x1800183c0  lea     rcx, SRWLock; SRWLock
0x1800183c7  call    cs:__imp_TryAcquireSRWLockExclusive
0x1800183cd  test    al, al
0x1800183cf  jz      short loc_1800183FB
0x1800183d1  mov     rbx, cs:qword_180026010
0x1800183d8  jmp     short loc_1800183E9
0x1800183da  mov     rcx, rbx
0x1800183dd  call    LookUpTableFlushComplete
0x1800183e2  mov     rbx, [rbx+150h]
0x1800183e9  test    rbx, rbx
0x1800183ec  jnz     short loc_1800183DA
0x1800183ee  lea     rcx, SRWLock; SRWLock
0x1800183f5  call    cs:__imp_ReleaseSRWLockExclusive
0x1800183fb  add     rsp, 20h
0x1800183ff  pop     rbx
0x180018400  retn
```
