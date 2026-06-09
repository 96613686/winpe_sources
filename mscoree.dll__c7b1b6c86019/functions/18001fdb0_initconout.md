# __initconout

- ea: `0x18001fdb0`
- end: `0x18001fdf1`
- name: `__initconout`
- size: `65`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x18001ec28`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18001fddf`
- `KERNEL32!CreateFileW` at `0x18001fddf`

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
0x18001fdb0  sub     rsp, 48h
0x18001fdb4  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18001fdbd  lea     rcx, FileName; "CONOUT$"
0x18001fdc4  mov     r8d, 3; dwShareMode
0x18001fdca  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18001fdd2  xor     r9d, r9d; lpSecurityAttributes
0x18001fdd5  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x18001fdda  mov     edx, 40000000h; dwDesiredAccess
0x18001fddf  call    cs:__imp_CreateFileW
0x18001fde5  mov     cs:_confh, rax
0x18001fdec  add     rsp, 48h
0x18001fdf0  retn
```
