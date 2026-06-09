# RemoveCallback(void *,long)

- ea: `0x18000fe70`
- end: `0x18000fe7d`
- name: `?RemoveCallback@@YAXPEAXJ@Z`
- size: `13`
- prototype: `void __fastcall(void *, int)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNEL32!SetEvent` at `0x18000fe76`

## pseudocode

```c
void __fastcall RemoveCallback(HANDLE *a1, int a2)
{
  *((_DWORD *)a1 + 2) = a2;
  SetEvent(*a1);
}

```

## disassembly

```asm
0x18000fe70  mov     [rcx+8], edx
0x18000fe73  mov     rcx, [rcx]
0x18000fe76  jmp     cs:__imp_SetEvent
```
