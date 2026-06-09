# __initconout

- ea: `0x180023b08`
- end: `0x180023b49`
- name: `__initconout`
- size: `65`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x18001e4c0`
- `0x18001e648`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180023b37`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180023b37`

## pseudocode

```c
HANDLE _initconout()
{
  HANDLE result; // rax

  result = CreateFileW(L"CONOUT$", 0x40000000u, 3u, 0, 3u, 0, 0);
  confh = result;
  return result;
}

```

## disassembly

```asm
0x180023b08  sub     rsp, 48h
0x180023b0c  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x180023b15  lea     rcx, aConout; "CONOUT$"
0x180023b1c  mov     r8d, 3; dwShareMode
0x180023b22  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180023b2a  xor     r9d, r9d; lpSecurityAttributes
0x180023b2d  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x180023b32  mov     edx, 40000000h; dwDesiredAccess
0x180023b37  call    cs:__imp_CreateFileW
0x180023b3d  mov     cs:_confh, rax
0x180023b44  add     rsp, 48h
0x180023b48  retn
```
