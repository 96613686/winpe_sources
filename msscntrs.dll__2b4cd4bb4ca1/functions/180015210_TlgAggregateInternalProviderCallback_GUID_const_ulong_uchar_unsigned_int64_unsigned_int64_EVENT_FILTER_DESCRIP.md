# TlgAggregateInternalProviderCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)

- ea: `0x180015210`
- end: `0x180015261`
- name: `?TlgAggregateInternalProviderCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z`
- size: `81`
- prototype: `void __fastcall(const struct _GUID *, int, __int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180014d9c`
- `0x180015210`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x180015227`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x180015227`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180015255`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180015255`

## pseudocode

```c
void __fastcall TlgAggregateInternalProviderCallback(const struct _GUID *a1, int a2, __int64 a3, __int64 a4)
{
  __int64 i; // rbx

  if ( a2 == 2 && a4 == 32 && TryAcquireSRWLockExclusive(&stru_180022398) )
  {
    for ( i = qword_1800223A0; i; i = *(_QWORD *)(i + 336) )
      LookUpTableFlushComplete(i);
    ReleaseSRWLockExclusive(&stru_180022398);
  }
}

```

## disassembly

```asm
0x180015210  cmp     edx, 2
0x180015213  jnz     short locret_180015260
0x180015215  push    rbx
0x180015216  sub     rsp, 20h
0x18001521a  cmp     r9, 20h ; ' '
0x18001521e  jnz     short loc_18001525B
0x180015220  lea     rcx, stru_180022398; SRWLock
0x180015227  call    cs:__imp_TryAcquireSRWLockExclusive
0x18001522d  test    al, al
0x18001522f  jz      short loc_18001525B
0x180015231  mov     rbx, cs:qword_1800223A0
0x180015238  jmp     short loc_180015249
0x18001523a  mov     rcx, rbx
0x18001523d  call    LookUpTableFlushComplete
0x180015242  mov     rbx, [rbx+150h]
0x180015249  test    rbx, rbx
0x18001524c  jnz     short loc_18001523A
0x18001524e  lea     rcx, stru_180022398; SRWLock
0x180015255  call    cs:__imp_ReleaseSRWLockExclusive
0x18001525b  add     rsp, 20h
0x18001525f  pop     rbx
0x180015260  retn
```
