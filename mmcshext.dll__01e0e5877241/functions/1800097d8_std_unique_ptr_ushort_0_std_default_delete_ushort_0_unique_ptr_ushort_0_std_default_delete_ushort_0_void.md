# std::unique_ptr<ushort [0],std::default_delete<ushort [0]>>::~unique_ptr<ushort [0],std::default_delete<ushort [0]>>(void)

- ea: `0x1800097d8`
- end: `0x1800097e2`
- name: `??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ`
- size: `10`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x18000aec5`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x1800097db`

## pseudocode

```c
void __fastcall std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(void **a1)
{
  operator delete[](*a1);
}

```

## disassembly

```asm
0x1800097d8  mov     rcx, [rcx]
0x1800097db  jmp     cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
```
