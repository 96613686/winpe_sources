# OpenBthpanHandle

- ea: `0x180033fb0`
- end: `0x18003400e`
- name: `OpenBthpanHandle`
- size: `94`
- prototype: `DWORD __fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800331bc`
- `0x180034014`

## callees

- `0x180033fb0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180033ffc`
- `KERNEL32!CreateFileW` at `0x180033feb`
- `KERNEL32!CreateFileW` at `0x180033feb`

## pseudocode

```c
DWORD __fastcall OpenBthpanHandle(_QWORD *a1)
{
  HANDLE FileW; // rax

  *a1 = -1;
  FileW = CreateFileW(L"\\\\.\\\\BthPan", 0xC0000000, 0, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
    return GetLastError();
  *a1 = FileW;
  return 0;
}

```

## disassembly

```asm
0x180033fb0  push    rbx
0x180033fb2  sub     rsp, 40h
0x180033fb6  mov     rbx, rcx
0x180033fb9  mov     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x180033fc0  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x180033fc9  lea     rcx, FileName; "\\\\.\\\\BthPan"
0x180033fd0  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180033fd8  xor     r9d, r9d; lpSecurityAttributes
0x180033fdb  xor     r8d, r8d; dwShareMode
0x180033fde  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180033fe6  mov     edx, 0C0000000h; dwDesiredAccess
0x180033feb  call    cs:__imp_CreateFileW
0x180033ff1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180033ff5  jnz     short loc_180034003
0x180033ff7  add     rsp, 40h
0x180033ffb  pop     rbx
0x180033ffc  jmp     cs:__imp_GetLastError
0x180034003  mov     [rbx], rax
0x180034006  xor     eax, eax
0x180034008  add     rsp, 40h
0x18003400c  pop     rbx
0x18003400d  retn
```
