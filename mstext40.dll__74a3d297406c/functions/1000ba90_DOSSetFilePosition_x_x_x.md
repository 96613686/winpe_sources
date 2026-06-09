# DOSSetFilePosition(x,x,x)

- ea: `0x1000ba90`
- end: `0x1000baaf`
- name: `_DOSSetFilePosition@12`
- size: `31`
- prototype: `int __stdcall(HANDLE hFile, DWORD dwMoveMethod, LONG lDistanceToMove)`
- caller_count: `6`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x1001ad40`
- `0x1001d440`
- `0x1001d570`
- `0x1001d6a0`
- `0x1001d770`
- `0x1001da60`

## import_xrefs

- `KERNEL32!SetFilePointer` at `0x1000ba9e`
- `KERNEL32!SetFilePointer` at `0x1000ba9e`

## pseudocode

```c
int __stdcall DOSSetFilePosition(HANDLE hFile, DWORD dwMoveMethod, LONG lDistanceToMove)
{
  return (SetFilePointer(hFile, lDistanceToMove, 0, dwMoveMethod) != -1) - 1;
}

```

## disassembly

```asm
0x1000ba90  push    [esp+dwMoveMethod]; dwMoveMethod
0x1000ba94  push    0; lpDistanceToMoveHigh
0x1000ba96  push    [esp+8+lDistanceToMove]; lDistanceToMove
0x1000ba9a  push    [esp+0Ch+hFile]; hFile
0x1000ba9e  call    ds:__imp__SetFilePointer@16; SetFilePointer(x,x,x,x)
0x1000baa4  inc     eax
0x1000baa5  neg     eax
0x1000baa7  sbb     eax, eax
0x1000baa9  neg     eax
0x1000baab  dec     eax
0x1000baac  retn    0Ch
```
