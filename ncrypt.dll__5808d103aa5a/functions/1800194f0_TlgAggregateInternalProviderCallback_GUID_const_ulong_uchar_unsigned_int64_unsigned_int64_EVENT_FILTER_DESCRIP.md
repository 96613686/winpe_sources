# TlgAggregateInternalProviderCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)

- ea: `0x1800194f0`
- end: `0x180019541`
- name: `?TlgAggregateInternalProviderCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z`
- size: `81`
- prototype: `void __fastcall(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180018a08`
- `0x1800194f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019535`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019535`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x180019507`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x180019507`

## pseudocode

```c
void __fastcall TlgAggregateInternalProviderCallback(const struct _GUID *a1, int a2, __int64 a3, __int64 a4)
{
  __int64 i; // rbx

  if ( a2 == 2 && a4 == 32 && TryAcquireSRWLockExclusive(&SRWLock) )
  {
    for ( i = qword_18002AF60; i; i = *(_QWORD *)(i + 336) )
      LookUpTableFlushComplete(i);
    ReleaseSRWLockExclusive(&SRWLock);
  }
}

```

## disassembly

```asm
0x1800194f0  cmp     edx, 2
0x1800194f3  jnz     short locret_180019540
0x1800194f5  push    rbx
0x1800194f6  sub     rsp, 20h
0x1800194fa  cmp     r9, 20h ; ' '
0x1800194fe  jnz     short loc_18001953B
0x180019500  lea     rcx, SRWLock; SRWLock
0x180019507  call    cs:__imp_TryAcquireSRWLockExclusive
0x18001950d  test    al, al
0x18001950f  jz      short loc_18001953B
0x180019511  mov     rbx, cs:qword_18002AF60
0x180019518  jmp     short loc_180019529
0x18001951a  mov     rcx, rbx
0x18001951d  call    LookUpTableFlushComplete
0x180019522  mov     rbx, [rbx+150h]
0x180019529  test    rbx, rbx
0x18001952c  jnz     short loc_18001951A
0x18001952e  lea     rcx, SRWLock; SRWLock
0x180019535  call    cs:__imp_ReleaseSRWLockExclusive
0x18001953b  add     rsp, 20h
0x18001953f  pop     rbx
0x180019540  retn
```
