# __dcrt_lowio_initialize_console_output

- ea: `0x18001e7d0`
- end: `0x18001e80b`
- name: `__dcrt_lowio_initialize_console_output`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x18001e1e0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18001e7f9`
- `KERNEL32!CreateFileW` at `0x18001e7f9`

## pseudocode

```c
HANDLE _dcrt_lowio_initialize_console_output()
{
  HANDLE result; // rax

  result = CreateFileW(L"CONOUT$", 0x40000000u, 3u, 0, 3u, 0, 0);
  _dcrt_lowio_console_output_handle = result;
  return result;
}

```

## disassembly

```asm
0x18001e7d0  sub     rsp, 48h
0x18001e7d4  and     [rsp+48h+var_18], 0
0x18001e7da  lea     rcx, FileName
0x18001e7e1  and     [rsp+48h+var_20], 0
0x18001e7e6  mov     r8d, 3; dwShareMode
0x18001e7ec  xor     r9d, r9d; lpSecurityAttributes
0x18001e7ef  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x18001e7f4  mov     edx, 40000000h; dwDesiredAccess
0x18001e7f9  call    cs:__imp_CreateFileW
0x18001e7ff  mov     cs:__dcrt_lowio_console_output_handle, rax
0x18001e806  add     rsp, 48h
0x18001e80a  retn
```
