# TlgAggregateInternalProviderCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)

- ea: `0x1800048c0`
- end: `0x180004911`
- name: `?TlgAggregateInternalProviderCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z`
- size: `81`
- prototype: `void __fastcall(const struct _GUID *, int, __int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000444c`
- `0x1800048c0`

## import_xrefs

- `KERNEL32!TryAcquireSRWLockExclusive` at `0x1800048d7`
- `KERNEL32!TryAcquireSRWLockExclusive` at `0x1800048d7`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180004905`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180004905`

## pseudocode

```c
void __fastcall TlgAggregateInternalProviderCallback(const struct _GUID *a1, int a2, __int64 a3, __int64 a4)
{
  __int64 i; // rbx

  if ( a2 == 2 && a4 == 32 && TryAcquireSRWLockExclusive(&SRWLock) )
  {
    for ( i = qword_18000A730; i; i = *(_QWORD *)(i + 336) )
      LookUpTableFlushComplete(i);
    ReleaseSRWLockExclusive(&SRWLock);
  }
}

```

## disassembly

```asm
0x1800048c0  cmp     edx, 2
0x1800048c3  jnz     short locret_180004910
0x1800048c5  push    rbx
0x1800048c6  sub     rsp, 20h
0x1800048ca  cmp     r9, 20h ; ' '
0x1800048ce  jnz     short loc_18000490B
0x1800048d0  lea     rcx, SRWLock; SRWLock
0x1800048d7  call    cs:__imp_TryAcquireSRWLockExclusive
0x1800048dd  test    al, al
0x1800048df  jz      short loc_18000490B
0x1800048e1  mov     rbx, cs:qword_18000A730
0x1800048e8  jmp     short loc_1800048F9
0x1800048ea  mov     rcx, rbx
0x1800048ed  call    LookUpTableFlushComplete
0x1800048f2  mov     rbx, [rbx+150h]
0x1800048f9  test    rbx, rbx
0x1800048fc  jnz     short loc_1800048EA
0x1800048fe  lea     rcx, SRWLock; SRWLock
0x180004905  call    cs:__imp_ReleaseSRWLockExclusive
0x18000490b  add     rsp, 20h
0x18000490f  pop     rbx
0x180004910  retn
```
