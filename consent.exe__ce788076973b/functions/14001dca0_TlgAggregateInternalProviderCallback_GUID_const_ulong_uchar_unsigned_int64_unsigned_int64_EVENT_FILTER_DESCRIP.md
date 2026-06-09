# TlgAggregateInternalProviderCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)

- ea: `0x14001dca0`
- end: `0x14001dcf1`
- name: `?TlgAggregateInternalProviderCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z`
- size: `81`
- prototype: `void __fastcall(const struct _GUID *, int, __int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14001d8c0`
- `0x14001dca0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001dce5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001dce5`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x14001dcb7`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x14001dcb7`

## pseudocode

```c
void __fastcall TlgAggregateInternalProviderCallback(const struct _GUID *a1, int a2, __int64 a3, __int64 a4)
{
  __int64 i; // rbx

  if ( a2 == 2 && a4 == 32 && TryAcquireSRWLockExclusive(&stru_140029C80) )
  {
    for ( i = qword_140029C88; i; i = *(_QWORD *)(i + 336) )
      LookUpTableFlushComplete(i);
    ReleaseSRWLockExclusive(&stru_140029C80);
  }
}

```

## disassembly

```asm
0x14001dca0  cmp     edx, 2
0x14001dca3  jnz     short locret_14001DCF0
0x14001dca5  push    rbx
0x14001dca6  sub     rsp, 20h
0x14001dcaa  cmp     r9, 20h ; ' '
0x14001dcae  jnz     short loc_14001DCEB
0x14001dcb0  lea     rcx, stru_140029C80; SRWLock
0x14001dcb7  call    cs:__imp_TryAcquireSRWLockExclusive
0x14001dcbd  test    al, al
0x14001dcbf  jz      short loc_14001DCEB
0x14001dcc1  mov     rbx, cs:qword_140029C88
0x14001dcc8  jmp     short loc_14001DCD9
0x14001dcca  mov     rcx, rbx
0x14001dccd  call    LookUpTableFlushComplete
0x14001dcd2  mov     rbx, [rbx+150h]
0x14001dcd9  test    rbx, rbx
0x14001dcdc  jnz     short loc_14001DCCA
0x14001dcde  lea     rcx, stru_140029C80; SRWLock
0x14001dce5  call    cs:__imp_ReleaseSRWLockExclusive
0x14001dceb  add     rsp, 20h
0x14001dcef  pop     rbx
0x14001dcf0  retn
```
