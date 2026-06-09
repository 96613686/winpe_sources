# bFileExists

- ea: `0x18002d6f8`
- end: `0x18002d71f`
- name: `bFileExists`
- size: `39`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002d428`

## callees

- `0x18002d6f8`

## import_xrefs

- `KERNEL32!_lopen` at `0x18002d6fe`
- `KERNEL32!_lopen` at `0x18002d6fe`
- `KERNEL32!_lclose` at `0x18002d70b`
- `KERNEL32!_lclose` at `0x18002d70b`

## pseudocode

```c
__int64 __fastcall bFileExists(const CHAR *a1)
{
  HFILE v1; // eax

  v1 = _lopen(a1, 0);
  if ( v1 == -1 )
    return 0;
  _lclose(v1);
  return 1;
}

```

## disassembly

```asm
0x18002d6f8  sub     rsp, 28h
0x18002d6fc  xor     edx, edx; iReadWrite
0x18002d6fe  call    cs:__imp__lopen
0x18002d704  cmp     eax, 0FFFFFFFFh
0x18002d707  jz      short loc_18002D718
0x18002d709  mov     ecx, eax; hFile
0x18002d70b  call    cs:__imp__lclose
0x18002d711  mov     eax, 1
0x18002d716  jmp     short loc_18002D71A
0x18002d718  xor     eax, eax
0x18002d71a  add     rsp, 28h
0x18002d71e  retn
```
