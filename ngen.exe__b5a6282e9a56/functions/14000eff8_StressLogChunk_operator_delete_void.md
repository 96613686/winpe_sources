# StressLogChunk::operator delete(void *)

- ea: `0x14000eff8`
- end: `0x14000f036`
- name: `??3StressLogChunk@@SAXPEAX@Z`
- size: `62`
- prototype: `void __fastcall(void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140015982`
- `0x1400159e8`

## callees

- `0x14000a184`
- `0x140013f30`

## pseudocode

```c
void __fastcall StressLogChunk::operator delete(void *a1)
{
  void *v2; // rdi
  struct IEEMemoryManager *EEMemoryManager; // rax

  v2 = StressLogChunk::s_LogChunkHeap;
  EEMemoryManager = GetEEMemoryManager();
  (*(void (__fastcall **)(struct IEEMemoryManager *, void *, _QWORD, void *))(*(_QWORD *)EEMemoryManager + 88LL))(
    EEMemoryManager,
    v2,
    0,
    a1);
}

```

## disassembly

```asm
0x14000eff8  mov     [rsp+arg_0], rbx
0x14000effd  push    rdi
0x14000effe  sub     rsp, 30h
0x14000f002  mov     rbx, rcx
0x14000f005  mov     rdi, cs:?s_LogChunkHeap@StressLogChunk@@2PEAXEA; void * StressLogChunk::s_LogChunkHeap
0x14000f00c  call    ?GetEEMemoryManager@@YAPEAUIEEMemoryManager@@XZ; GetEEMemoryManager(void)
0x14000f011  mov     rcx, rax
0x14000f014  mov     r8, [rax]
0x14000f017  mov     rax, [r8+58h]
0x14000f01b  mov     r9, rbx
0x14000f01e  xor     r8d, r8d
0x14000f021  mov     rdx, rdi
0x14000f024  call    cs:__guard_dispatch_icall_fptr
0x14000f02a  nop
0x14000f02b  mov     rbx, [rsp+38h+arg_0]
0x14000f030  add     rsp, 30h
0x14000f034  pop     rdi
0x14000f035  retn
```
