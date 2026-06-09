# TlgAggregateInternalProviderCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)

- ea: `0x18001c680`
- end: `0x18001c6de`
- name: `?TlgAggregateInternalProviderCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z`
- size: `94`
- prototype: `void __fastcall(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18001c1fc`
- `0x18001c680`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c6cb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c6cb`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x18001c697`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x18001c697`

## pseudocode

```c
void __fastcall TlgAggregateInternalProviderCallback(const struct _GUID *a1, int a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rdx
  int v5; // r8d
  int v6; // r9d
  const __m128i *i; // rbx

  if ( a2 == 2 && a4 == 32 && TryAcquireSRWLockExclusive(&SRWLock) )
  {
    for ( i = (const __m128i *)qword_18002A920; i; i = (const __m128i *)i[21].m128i_i64[0] )
      LookUpTableFlushComplete(i, v4, v5, v6);
    ReleaseSRWLockExclusive(&SRWLock);
  }
}

```

## disassembly

```asm
0x18001c680  cmp     edx, 2
0x18001c683  jnz     short locret_18001C6DC
0x18001c685  push    rbx
0x18001c686  sub     rsp, 20h
0x18001c68a  cmp     r9, 20h ; ' '
0x18001c68e  jnz     short loc_18001C6D7
0x18001c690  lea     rcx, SRWLock; SRWLock
0x18001c697  call    cs:__imp_TryAcquireSRWLockExclusive
0x18001c69e  nop     dword ptr [rax+rax+00h]
0x18001c6a3  test    al, al
0x18001c6a5  jz      short loc_18001C6D7
0x18001c6a7  mov     rbx, cs:qword_18002A920
0x18001c6ae  jmp     short loc_18001C6BF
0x18001c6b0  mov     rcx, rbx
0x18001c6b3  call    LookUpTableFlushComplete
0x18001c6b8  mov     rbx, [rbx+150h]
0x18001c6bf  test    rbx, rbx
0x18001c6c2  jnz     short loc_18001C6B0
0x18001c6c4  lea     rcx, SRWLock; SRWLock
0x18001c6cb  call    cs:__imp_ReleaseSRWLockExclusive
0x18001c6d2  nop     dword ptr [rax+rax+00h]
0x18001c6d7  add     rsp, 20h
0x18001c6db  pop     rbx
0x18001c6dc  retn
```
