# __dcrt_lowio_ensure_console_output_initialized

- ea: `0x14015ef3c`
- end: `0x14015ef8e`
- name: `__dcrt_lowio_ensure_console_output_initialized`
- size: `82`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x14015a5a0`

## callees

- `0x14015ef3c`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x14015ef72`
- `KERNEL32!CreateFileW` at `0x14015ef72`

## pseudocode

```c
__int64 _dcrt_lowio_ensure_console_output_initialized()
{
  char *FileW; // rax
  unsigned int v1; // ebx

  FileW = (char *)hObject;
  v1 = 0;
  if ( hObject == (HANDLE)-2LL )
  {
    FileW = (char *)CreateFileW(L"CONOUT$", 0x40000000u, 3u, 0, 3u, 0, 0);
    hObject = FileW;
  }
  LOBYTE(v1) = FileW + 1 != 0;
  return v1;
}

```

## disassembly

```asm
0x14015ef3c  push    rbx
0x14015ef3e  sub     rsp, 40h
0x14015ef42  mov     rax, cs:hObject
0x14015ef49  xor     ebx, ebx
0x14015ef4b  cmp     rax, 0FFFFFFFFFFFFFFFEh
0x14015ef4f  jnz     short loc_14015EF7F
0x14015ef51  mov     [rsp+48h+hTemplateFile], rbx; hTemplateFile
0x14015ef56  lea     r8d, [rbx+3]; dwShareMode
0x14015ef5a  mov     [rsp+48h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x14015ef5e  lea     rcx, FileName
0x14015ef65  xor     r9d, r9d; lpSecurityAttributes
0x14015ef68  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x14015ef6d  mov     edx, 40000000h; dwDesiredAccess
0x14015ef72  call    cs:CreateFileW
0x14015ef78  mov     cs:hObject, rax
0x14015ef7f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14015ef83  setnz   bl
0x14015ef86  mov     eax, ebx
0x14015ef88  add     rsp, 40h
0x14015ef8c  pop     rbx
0x14015ef8d  retn
```
