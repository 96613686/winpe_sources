# __dcrt_lowio_ensure_console_output_initialized

- ea: `0x18001d388`
- end: `0x18001d3e0`
- name: `__dcrt_lowio_ensure_console_output_initialized`
- size: `88`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18001d33c`

## callees

- `0x18001d388`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001d3c2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001d3c2`

## pseudocode

```c
_BOOL8 _dcrt_lowio_ensure_console_output_initialized()
{
  char *FileW; // rcx

  FileW = (char *)hObject;
  if ( hObject == (HANDLE)-2LL )
  {
    FileW = (char *)CreateFileW(L"CONOUT$", 0x40000000u, 3u, 0, 3u, 0, 0);
    hObject = FileW;
  }
  return FileW + 1 != 0;
}

```

## disassembly

```asm
0x18001d388  sub     rsp, 48h
0x18001d38c  mov     rcx, cs:hObject
0x18001d393  cmp     rcx, 0FFFFFFFFFFFFFFFEh
0x18001d397  jnz     short loc_18001D3D2
0x18001d399  lea     r8d, [rcx+5]; dwShareMode
0x18001d39d  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18001d3a6  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18001d3ae  lea     rcx, FileName; "CONOUT$"
0x18001d3b5  xor     r9d, r9d; lpSecurityAttributes
0x18001d3b8  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x18001d3bd  mov     edx, 40000000h; dwDesiredAccess
0x18001d3c2  call    cs:__imp_CreateFileW
0x18001d3c8  mov     rcx, rax
0x18001d3cb  mov     cs:hObject, rax
0x18001d3d2  xor     eax, eax
0x18001d3d4  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001d3d8  setnz   al
0x18001d3db  add     rsp, 48h
0x18001d3df  retn
```
