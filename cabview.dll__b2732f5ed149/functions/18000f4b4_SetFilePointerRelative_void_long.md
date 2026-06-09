# SetFilePointerRelative(void *,long)

- ea: `0x18000f4b4`
- end: `0x18000f4d6`
- name: `?SetFilePointerRelative@@YAHPEAXJ@Z`
- size: `34`
- prototype: `__int64 __fastcall(void *, int)`
- caller_count: `3`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x18000d53c`
- `0x18000d724`
- `0x18000d81c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18000f4c1`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18000f4c1`

## pseudocode

```c
_BOOL8 __fastcall SetFilePointerRelative(void *a1, LONG a2)
{
  return SetFilePointer(a1, a2, 0, 1u) != -1;
}

```

## disassembly

```asm
0x18000f4b4  sub     rsp, 28h
0x18000f4b8  mov     r9d, 1; dwMoveMethod
0x18000f4be  xor     r8d, r8d; lpDistanceToMoveHigh
0x18000f4c1  call    cs:__imp_SetFilePointer
0x18000f4c7  xor     ecx, ecx
0x18000f4c9  cmp     eax, 0FFFFFFFFh
0x18000f4cc  setnz   cl
0x18000f4cf  mov     eax, ecx
0x18000f4d1  add     rsp, 28h
0x18000f4d5  retn
```
