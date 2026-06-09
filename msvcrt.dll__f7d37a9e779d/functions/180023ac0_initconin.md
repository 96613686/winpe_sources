# __initconin

- ea: `0x180023ac0`
- end: `0x180023b01`
- name: `__initconin`
- size: `65`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x18001dd50`
- `0x18001f0e0`
- `0x18001f390`
- `0x1800202d4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180023aef`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180023aef`

## pseudocode

```c
HANDLE _initconin()
{
  HANDLE result; // rax

  result = CreateFileW(L"CONIN$", 0xC0000000, 3u, 0, 3u, 0, 0);
  coninpfh = result;
  return result;
}

```

## disassembly

```asm
0x180023ac0  sub     rsp, 48h
0x180023ac4  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x180023acd  lea     rcx, aConin; "CONIN$"
0x180023ad4  mov     r8d, 3; dwShareMode
0x180023ada  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180023ae2  xor     r9d, r9d; lpSecurityAttributes
0x180023ae5  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x180023aea  mov     edx, 0C0000000h; dwDesiredAccess
0x180023aef  call    cs:__imp_CreateFileW
0x180023af5  mov     cs:_coninpfh, rax
0x180023afc  add     rsp, 48h
0x180023b00  retn
```
