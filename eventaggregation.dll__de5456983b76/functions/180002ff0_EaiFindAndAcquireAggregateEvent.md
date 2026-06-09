# EaiFindAndAcquireAggregateEvent

- ea: `0x180002ff0`
- end: `0x180003065`
- name: `EaiFindAndAcquireAggregateEvent`
- size: `117`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180007de0`
- `0x180007f00`
- `0x180008010`

## callees

- `0x180002ff0`

## import_xrefs

- `ntdll!RtlAcquireSRWLockShared` at `0x180003007`
- `ntdll!RtlAcquireSRWLockShared` at `0x180003007`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000303b`
- `ntdll!RtlReleaseSRWLockShared` at `0x180003058`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000303b`
- `ntdll!RtlReleaseSRWLockShared` at `0x180003058`
- `ntdll!RtlLookupEntryHashTable` at `0x18000301f`
- `ntdll!RtlLookupEntryHashTable` at `0x18000301f`

## pseudocode

```c
__int64 __fastcall EaiFindAndAcquireAggregateEvent(__int64 a1, __int64 *a2)
{
  __int64 v4; // rax
  __int64 v5; // rbx
  __int64 result; // rax

  RtlAcquireSRWLockShared(AggregateEventListLock, a2);
  if ( qword_180012148 && (v4 = RtlLookupEntryHashTable(qword_180012148, a1, 0), (v5 = v4) != 0) )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v4 + 136));
    RtlReleaseSRWLockShared(AggregateEventListLock);
    result = 0;
    *a2 = v5;
  }
  else
  {
    RtlReleaseSRWLockShared(AggregateEventListLock);
    return 3221225480LL;
  }
  return result;
}

```

## disassembly

```asm
0x180002ff0  mov     [rsp+arg_0], rbx
0x180002ff5  push    rdi
0x180002ff6  sub     rsp, 20h
0x180002ffa  mov     rbx, rcx
0x180002ffd  mov     rdi, rdx
0x180003000  lea     rcx, AggregateEventListLock
0x180003007  call    cs:__imp_RtlAcquireSRWLockShared
0x18000300d  mov     rcx, cs:qword_180012148
0x180003014  test    rcx, rcx
0x180003017  jz      short loc_180003051
0x180003019  xor     r8d, r8d
0x18000301c  mov     rdx, rbx
0x18000301f  call    cs:__imp_RtlLookupEntryHashTable
0x180003025  mov     rbx, rax
0x180003028  test    rax, rax
0x18000302b  jz      short loc_180003051
0x18000302d  lock inc dword ptr [rax+88h]
0x180003034  lea     rcx, AggregateEventListLock
0x18000303b  call    cs:__imp_RtlReleaseSRWLockShared
0x180003041  xor     eax, eax
0x180003043  mov     [rdi], rbx
0x180003046  mov     rbx, [rsp+28h+arg_0]
0x18000304b  add     rsp, 20h
0x18000304f  pop     rdi
0x180003050  retn
0x180003051  lea     rcx, AggregateEventListLock
0x180003058  call    cs:__imp_RtlReleaseSRWLockShared
0x18000305e  mov     eax, 0C0000008h
0x180003063  jmp     short loc_180003046
```
