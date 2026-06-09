# EaiReleaseAggregateEvent

- ea: `0x180001730`
- end: `0x1800017aa`
- name: `EaiReleaseAggregateEvent`
- size: `122`
- prototype: `char __fastcall(__int64)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800011e0`
- `0x1800013a0`
- `0x180004cd0`
- `0x1800054c0`
- `0x180007de0`
- `0x180007f00`
- `0x180008010`

## callees

- `0x180001730`
- `0x1800017b0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180001799`
- `ntdll!RtlFreeHeap` at `0x18000177d`
- `ntdll!RtlFreeHeap` at `0x180001799`

## pseudocode

```c
char __fastcall EaiReleaseAggregateEvent(__int64 a1)
{
  signed __int32 v2; // eax
  void *v3; // r8

  v2 = _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 136), 0xFFFFFFFF);
  if ( v2 == 1 )
  {
    v3 = *(void **)(a1 + 96);
    if ( v3 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v3);
      *(_QWORD *)(a1 + 96) = 0;
      *(_DWORD *)(a1 + 104) = 0;
    }
    if ( (*(_BYTE *)(a1 + 140) & 8) == 0 )
      EaiFreeEaAggregateEvent(a1 + 56);
    LOBYTE(v2) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)a1);
  }
  return v2;
}

```

## disassembly

```asm
0x180001730  push    rbx
0x180001732  sub     rsp, 20h
0x180001736  mov     rbx, rcx
0x180001739  mov     eax, 0FFFFFFFFh
0x18000173e  lock xadd [rcx+88h], eax
0x180001746  cmp     eax, 1
0x180001749  jnz     short loc_180001784
0x18000174b  mov     r8, [rcx+60h]; P
0x18000174f  test    r8, r8
0x180001752  jnz     short loc_18000178A
0x180001754  test    byte ptr [rbx+8Ch], 8
0x18000175b  jnz     short loc_180001766
0x18000175d  lea     rcx, [rbx+38h]
0x180001761  call    EaiFreeEaAggregateEvent
0x180001766  mov     rcx, gs:60h
0x18000176f  mov     r8, rbx
0x180001772  xor     edx, edx
0x180001774  mov     rcx, [rcx+30h]
0x180001778  add     rsp, 20h
0x18000177c  pop     rbx
0x18000177d  jmp     cs:__imp_RtlFreeHeap
0x180001784  add     rsp, 20h
0x180001788  pop     rbx
0x180001789  retn
0x18000178a  mov     rcx, gs:60h
0x180001793  xor     edx, edx; Flags
0x180001795  mov     rcx, [rcx+30h]; HeapHandle
0x180001799  call    cs:__imp_RtlFreeHeap
0x18000179f  xor     eax, eax
0x1800017a1  mov     [rbx+60h], rax
0x1800017a5  mov     [rbx+68h], eax
0x1800017a8  jmp     short loc_180001754
```
