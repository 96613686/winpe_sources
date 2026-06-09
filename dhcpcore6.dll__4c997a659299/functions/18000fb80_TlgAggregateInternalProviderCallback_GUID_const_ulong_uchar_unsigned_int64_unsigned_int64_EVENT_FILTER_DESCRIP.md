# TlgAggregateInternalProviderCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)

- ea: `0x18000fb80`
- end: `0x18000fbde`
- name: `?TlgAggregateInternalProviderCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z`
- size: `94`
- prototype: `void __fastcall(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000f4fc`
- `0x18000fb80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000fbcb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000fbcb`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x18000fb97`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x18000fb97`

## pseudocode

```c
void __fastcall TlgAggregateInternalProviderCallback(const struct _GUID *a1, int a2, __int64 a3, __int64 a4)
{
  __int64 i; // rbx

  if ( a2 == 2 && a4 == 32 && TryAcquireSRWLockExclusive(&SRWLock) )
  {
    for ( i = qword_180042698; i; i = *(_QWORD *)(i + 336) )
      LookUpTableFlushComplete(i);
    ReleaseSRWLockExclusive(&SRWLock);
  }
}

```

## disassembly

```asm
0x18000fb80  cmp     edx, 2
0x18000fb83  jnz     short locret_18000FBDC
0x18000fb85  push    rbx
0x18000fb86  sub     rsp, 20h
0x18000fb8a  cmp     r9, 20h ; ' '
0x18000fb8e  jnz     short loc_18000FBD7
0x18000fb90  lea     rcx, SRWLock; SRWLock
0x18000fb97  call    cs:__imp_TryAcquireSRWLockExclusive
0x18000fb9e  nop     dword ptr [rax+rax+00h]
0x18000fba3  test    al, al
0x18000fba5  jz      short loc_18000FBD7
0x18000fba7  mov     rbx, cs:qword_180042698
0x18000fbae  jmp     short loc_18000FBBF
0x18000fbb0  mov     rcx, rbx
0x18000fbb3  call    LookUpTableFlushComplete
0x18000fbb8  mov     rbx, [rbx+150h]
0x18000fbbf  test    rbx, rbx
0x18000fbc2  jnz     short loc_18000FBB0
0x18000fbc4  lea     rcx, SRWLock; SRWLock
0x18000fbcb  call    cs:__imp_ReleaseSRWLockExclusive
0x18000fbd2  nop     dword ptr [rax+rax+00h]
0x18000fbd7  add     rsp, 20h
0x18000fbdb  pop     rbx
0x18000fbdc  retn
```
