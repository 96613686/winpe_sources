# ___initconout

- ea: `0x1003cd3f`
- end: `0x1003cd5e`
- name: `___initconout`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x1003bd7f`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x1003cd52`
- `KERNEL32!CreateFileW` at `0x1003cd52`

## pseudocode

```c
HANDLE __initconout()
{
  HANDLE result; // eax

  result = CreateFileW(L"CONOUT$", 0x40000000u, 3u, 0, 3u, 0, 0);
  _confh = result;
  return result;
}

```

## disassembly

```asm
0x1003cd3f  xor     eax, eax
0x1003cd41  push    eax; hTemplateFile
0x1003cd42  push    eax; dwFlagsAndAttributes
0x1003cd43  push    3; dwCreationDisposition
0x1003cd45  push    eax; lpSecurityAttributes
0x1003cd46  push    3; dwShareMode
0x1003cd48  push    40000000h; dwDesiredAccess
0x1003cd4d  push    offset aConout
0x1003cd52  call    ds:__imp__CreateFileW@28
0x1003cd58  mov     __confh, eax
0x1003cd5d  retn
```
