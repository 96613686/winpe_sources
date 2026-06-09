# DOSGetFilePosition(x,x)

- ea: `0x1000b830`
- end: `0x1000b857`
- name: `_DOSGetFilePosition@8`
- size: `39`
- prototype: `int __stdcall(HANDLE hFile, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1001d570`

## callees

- `0x1000b830`

## import_xrefs

- `KERNEL32!SetFilePointer` at `0x1000b83a`
- `KERNEL32!SetFilePointer` at `0x1000b83a`

## pseudocode

```c
DWORD __stdcall DOSGetFilePosition(HANDLE hFile, DWORD *a2)
{
  DWORD result; // eax

  result = SetFilePointer(hFile, 0, 0, 1u);
  if ( result != -1 )
  {
    *a2 = result;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1000b830  push    1; dwMoveMethod
0x1000b832  push    0; lpDistanceToMoveHigh
0x1000b834  push    0; lDistanceToMove
0x1000b836  push    [esp+0Ch+hFile]; hFile
0x1000b83a  call    ds:__imp__SetFilePointer@16; SetFilePointer(x,x,x,x)
0x1000b840  mov     ecx, eax
0x1000b842  cmp     ecx, 0FFFFFFFFh
0x1000b845  jnz     short loc_1000B84C
0x1000b847  or      eax, eax
0x1000b849  retn    8
0x1000b84c  mov     eax, [esp+arg_4]
0x1000b850  mov     [eax], ecx
0x1000b852  xor     eax, eax
0x1000b854  retn    8
```
