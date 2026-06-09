# TopObj::operator new(unsigned __int64,unsigned __int64)

- ea: `0x140003940`
- end: `0x140003964`
- name: `??2TopObj@@SAPEAX_K0@Z`
- size: `36`
- prototype: `void *__fastcall(unsigned __int64, unsigned __int64)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x1400010fc`
- `0x140011010`
- `0x140020100`
- `0x140026a48`
- `0x140026c18`
- `0x140027fe0`
- `0x14002e078`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140003952`
- `ntoskrnl!ExAllocatePool2` at `0x140003952`

## pseudocode

```c
__int64 __fastcall TopObj::operator new(__int64 a1)
{
  return ExAllocatePool2(64, a1, 1245859668);
}

```

## disassembly

```asm
0x140003940  sub     rsp, 28h
0x140003944  mov     rdx, rcx
0x140003947  mov     r8d, 4A424F54h
0x14000394d  mov     ecx, 40h ; '@'
0x140003952  call    cs:__imp_ExAllocatePool2
0x140003959  nop     dword ptr [rax+rax+00h]
0x14000395e  add     rsp, 28h
0x140003962  retn
```
