# CSxRefTraceList::~CSxRefTraceList(void)

- ea: `0x180044f90`
- end: `0x180044fcc`
- name: `??1CSxRefTraceList@@AEAA@XZ`
- size: `60`
- prototype: `void __fastcall(CSxRefTraceList *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800458cc`

## callees

- `0x180044f90`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180044fb2`
- `ntdll!RtlFreeHeap` at `0x180044fb2`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180044fbb`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180044fbb`

## pseudocode

```c
void __fastcall CSxRefTraceList::~CSxRefTraceList(CSxRefTraceList *this)
{
  union _SLIST_HEADER *v1; // rbx
  PSLIST_ENTRY v2; // rax

  v1 = (union _SLIST_HEADER *)((char *)this + 16);
  while ( 1 )
  {
    v2 = InterlockedPopEntrySList(v1);
    if ( !v2 )
      break;
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, &v2[-17]);
  }
}

```

## disassembly

```asm
0x180044f90  push    rbx
0x180044f92  sub     rsp, 20h
0x180044f96  lea     rbx, [rcx+10h]
0x180044f9a  jmp     short loc_180044FB8
0x180044f9c  mov     rcx, gs:60h
0x180044fa5  lea     r8, [rax-110h]; P
0x180044fac  xor     edx, edx; Flags
0x180044fae  mov     rcx, [rcx+30h]; HeapHandle
0x180044fb2  call    cs:__imp_RtlFreeHeap
0x180044fb8  mov     rcx, rbx; ListHead
0x180044fbb  call    cs:__imp_InterlockedPopEntrySList
0x180044fc1  test    rax, rax
0x180044fc4  jnz     short loc_180044F9C
0x180044fc6  add     rsp, 20h
0x180044fca  pop     rbx
0x180044fcb  retn
```
