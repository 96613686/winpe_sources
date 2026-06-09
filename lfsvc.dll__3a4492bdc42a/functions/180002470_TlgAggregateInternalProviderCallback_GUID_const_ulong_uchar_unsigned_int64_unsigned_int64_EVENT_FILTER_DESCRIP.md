# TlgAggregateInternalProviderCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)

- ea: `0x180002470`
- end: `0x1800024ce`
- name: `?TlgAggregateInternalProviderCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z`
- size: `94`
- prototype: `void __fastcall(const struct _GUID *, int, __int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180001a20`
- `0x180002470`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x18000248b`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x18000248b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800024c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800024c1`

## pseudocode

```c
void __fastcall TlgAggregateInternalProviderCallback(const struct _GUID *a1, int a2, __int64 a3, __int64 a4)
{
  __int64 i; // rbx

  if ( a2 == 2 && a4 == 32 && TryAcquireSRWLockExclusive(&SRWLock) )
  {
    for ( i = qword_180012538; i; i = *(_QWORD *)(i + 336) )
      LookUpTableFlushComplete(i);
    ReleaseSRWLockExclusive(&SRWLock);
  }
}

```

## disassembly

```asm
0x180002470  sub     rsp, 28h
0x180002474  cmp     edx, 2
0x180002477  jz      short loc_18000247E
0x180002479  add     rsp, 28h
0x18000247d  retn
0x18000247e  cmp     r9, 20h ; ' '
0x180002482  jnz     short loc_180002479
0x180002484  lea     rcx, SRWLock; SRWLock
0x18000248b  call    cs:__imp_TryAcquireSRWLockExclusive
0x180002491  test    al, al
0x180002493  jz      short loc_180002479
0x180002495  mov     [rsp+28h+var_8], rbx
0x18000249a  mov     rbx, cs:qword_180012538
0x1800024a1  test    rbx, rbx
0x1800024a4  jz      short loc_1800024BA
0x1800024a6  mov     rcx, rbx
0x1800024a9  call    LookUpTableFlushComplete
0x1800024ae  mov     rbx, [rbx+150h]
0x1800024b5  test    rbx, rbx
0x1800024b8  jnz     short loc_1800024A6
0x1800024ba  lea     rcx, SRWLock; SRWLock
0x1800024c1  call    cs:__imp_ReleaseSRWLockExclusive
0x1800024c7  mov     rbx, [rsp+28h+var_8]
0x1800024cc  jmp     short loc_180002479
```
