# std::_Copy_memmove<CLocationEnvironmentHelper::BitMetadata *,CLocationEnvironmentHelper::BitMetadata *>(CLocationEnvironmentHelper::BitMetadata *,CLocationEnvironmentHelper::BitMetadata *,CLocationEnvironmentHelper::BitMetadata *)

- ea: `0x180005880`
- end: `0x180005891`
- name: `??$_Copy_memmove@PEAUBitMetadata@CLocationEnvironmentHelper@@PEAU12@@std@@YAPEAUBitMetadata@CLocationEnvironmentHelper@@PEAU12@00@Z`
- size: `17`
- prototype: `__int64 __fastcall(void *, __int64, void *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005ad0`

## callees

- `0x180005898`

## pseudocode

```c
__int64 __fastcall std::_Copy_memmove<CLocationEnvironmentHelper::BitMetadata *,CLocationEnvironmentHelper::BitMetadata *>(
        void *a1,
        __int64 a2,
        void *a3)
{
  return std::_Copy_memmove_tail<CLocationEnvironmentHelper::BitMetadata *>(a1, a3);
}

```

## disassembly

```asm
0x180005880  sub     rdx, rcx
0x180005883  mov     rax, r8
0x180005886  mov     r8, rdx
0x180005889  mov     rdx, rax; void *
0x18000588c  jmp     ??$_Copy_memmove_tail@PEAUBitMetadata@CLocationEnvironmentHelper@@@std@@YAPEAUBitMetadata@CLocationEnvironmentHelper@@QEBDQEAU12@_K2@Z; std::_Copy_memmove_tail<CLocationEnvironmentHelper::BitMetadata *>(char const * const,CLocationEnvironmentHelper::BitMetadata * const,unsigned __int64,unsigned __int64)
```
