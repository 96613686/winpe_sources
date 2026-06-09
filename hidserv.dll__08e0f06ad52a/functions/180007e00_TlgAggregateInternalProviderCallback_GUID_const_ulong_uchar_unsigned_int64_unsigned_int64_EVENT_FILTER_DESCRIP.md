# TlgAggregateInternalProviderCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)

- ea: `0x180007e00`
- end: `0x180007e51`
- name: `?TlgAggregateInternalProviderCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z`
- size: `81`
- prototype: `void __fastcall(const struct _GUID *, int, __int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180007988`
- `0x180007e00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x180007e17`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x180007e17`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007e45`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007e45`

## pseudocode

```c
void __fastcall TlgAggregateInternalProviderCallback(const struct _GUID *a1, int a2, __int64 a3, __int64 a4)
{
  __int64 i; // rbx

  if ( a2 == 2 && a4 == 32 && TryAcquireSRWLockExclusive(&SRWLock) )
  {
    for ( i = qword_18000D728; i; i = *(_QWORD *)(i + 336) )
      LookUpTableFlushComplete(i);
    ReleaseSRWLockExclusive(&SRWLock);
  }
}

```

## disassembly

```asm
0x180007e00  cmp     edx, 2
0x180007e03  jnz     short locret_180007E50
0x180007e05  push    rbx
0x180007e06  sub     rsp, 20h
0x180007e0a  cmp     r9, 20h ; ' '
0x180007e0e  jnz     short loc_180007E4B
0x180007e10  lea     rcx, SRWLock; SRWLock
0x180007e17  call    cs:__imp_TryAcquireSRWLockExclusive
0x180007e1d  test    al, al
0x180007e1f  jz      short loc_180007E4B
0x180007e21  mov     rbx, cs:qword_18000D728
0x180007e28  jmp     short loc_180007E39
0x180007e2a  mov     rcx, rbx
0x180007e2d  call    LookUpTableFlushComplete
0x180007e32  mov     rbx, [rbx+150h]
0x180007e39  test    rbx, rbx
0x180007e3c  jnz     short loc_180007E2A
0x180007e3e  lea     rcx, SRWLock; SRWLock
0x180007e45  call    cs:__imp_ReleaseSRWLockExclusive
0x180007e4b  add     rsp, 20h
0x180007e4f  pop     rbx
0x180007e50  retn
```
