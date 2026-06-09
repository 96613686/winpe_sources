# std::unique_ptr<ushort [0],std::default_delete<ushort [0]>>::~unique_ptr<ushort [0],std::default_delete<ushort [0]>>(void)

- ea: `0x18000fa08`
- end: `0x18000fa12`
- name: `??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(void **)`
- caller_count: `7`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x18003c58c`
- `0x18003c7ca`
- `0x18003c8a2`
- `0x18003c91f`
- `0x18003cb5d`
- `0x18003cc2c`
- `0x18003cc3e`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18000fa0b`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(void **a1)
{
  operator delete[](*a1);
}

```

## disassembly

```asm
0x18000fa08  mov     rcx, [rcx]
0x18000fa0b  jmp     cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
```
