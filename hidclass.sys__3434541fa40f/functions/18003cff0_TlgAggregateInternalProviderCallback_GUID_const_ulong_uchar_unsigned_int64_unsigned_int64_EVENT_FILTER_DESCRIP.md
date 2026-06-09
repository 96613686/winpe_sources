# TlgAggregateInternalProviderCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)

- ea: `0x18003cff0`
- end: `0x18003d052`
- name: `?TlgAggregateInternalProviderCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z`
- size: `98`
- prototype: `void __fastcall(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18003cb80`
- `0x18003cff0`

## import_xrefs

- `ntoskrnl!ExTryAcquirePushLockExclusiveEx` at `0x18003d009`
- `ntoskrnl!ExTryAcquirePushLockExclusiveEx` at `0x18003d009`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x18003d03f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x18003d03f`

## pseudocode

```c
void __fastcall TlgAggregateInternalProviderCallback(const struct _GUID *a1, int a2, __int64 a3, __int64 a4)
{
  __int64 i; // rbx

  if ( a2 == 2 && a4 == 32 && (unsigned __int8)ExTryAcquirePushLockExclusiveEx(&qword_180031550, 0) )
  {
    for ( i = qword_180031558; i; i = *(_QWORD *)(i + 352) )
      LookUpTableFlushComplete(i);
    ExReleasePushLockExclusiveEx(&qword_180031550, 0);
  }
}

```

## disassembly

```asm
0x18003cff0  cmp     edx, 2
0x18003cff3  jnz     short locret_18003D050
0x18003cff5  push    rbx
0x18003cff6  sub     rsp, 20h
0x18003cffa  cmp     r9, 20h ; ' '
0x18003cffe  jnz     short loc_18003D04B
0x18003d000  xor     edx, edx
0x18003d002  lea     rcx, qword_180031550
0x18003d009  call    cs:__imp_ExTryAcquirePushLockExclusiveEx
0x18003d010  nop     dword ptr [rax+rax+00h]
0x18003d015  test    al, al
0x18003d017  jz      short loc_18003D04B
0x18003d019  mov     rbx, cs:qword_180031558
0x18003d020  jmp     short loc_18003D031
0x18003d022  mov     rcx, rbx
0x18003d025  call    LookUpTableFlushComplete
0x18003d02a  mov     rbx, [rbx+160h]
0x18003d031  test    rbx, rbx
0x18003d034  jnz     short loc_18003D022
0x18003d036  xor     edx, edx
0x18003d038  lea     rcx, qword_180031550
0x18003d03f  call    cs:__imp_ExReleasePushLockExclusiveEx
0x18003d046  nop     dword ptr [rax+rax+00h]
0x18003d04b  add     rsp, 20h
0x18003d04f  pop     rbx
0x18003d050  retn
```
