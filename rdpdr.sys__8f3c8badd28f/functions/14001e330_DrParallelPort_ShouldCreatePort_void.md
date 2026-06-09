# DrParallelPort::ShouldCreatePort(void)

- ea: `0x14001e330`
- end: `0x14001e343`
- name: `?ShouldCreatePort@DrParallelPort@@UEAAHXZ`
- size: `19`
- prototype: `__int64 __fastcall(DrParallelPort *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
_BOOL8 __fastcall DrParallelPort::ShouldCreatePort(DrParallelPort *this)
{
  return (*(_DWORD *)(*((_QWORD *)this + 4) + 592LL) & 0x40) == 0;
}

```

## disassembly

```asm
0x14001e330  mov     rax, [rcx+20h]
0x14001e334  mov     eax, [rax+250h]
0x14001e33a  shr     eax, 6
0x14001e33d  not     eax
0x14001e33f  and     eax, 1
0x14001e342  retn
```
