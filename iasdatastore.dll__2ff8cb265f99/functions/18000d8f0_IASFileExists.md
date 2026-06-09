# IASFileExists

- ea: `0x18000d8f0`
- end: `0x18000d945`
- name: `IASFileExists`
- size: `85`
- prototype: `char __fastcall(const WCHAR *)`
- caller_count: `6`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800079fc`
- `0x1800081b8`
- `0x1800086c8`
- `0x18000a334`
- `0x18000a4a0`
- `0x18000b210`

## callees

- `0x18000d8f0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18000d926`
- `KERNEL32!CreateFileW` at `0x18000d926`
- `KERNEL32!CloseHandle` at `0x18000d937`
- `KERNEL32!CloseHandle` at `0x18000d937`

## pseudocode

```c
char __fastcall IASFileExists(const WCHAR *a1)
{
  char v2; // bl
  HANDLE FileW; // rax

  if ( !a1 )
    return 0;
  v2 = 0;
  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x8000000u, 0);
  if ( FileW != (HANDLE)-1LL )
  {
    v2 = 1;
    CloseHandle(FileW);
  }
  return v2;
}

```

## disassembly

```asm
0x18000d8f0  push    rbx
0x18000d8f2  sub     rsp, 40h
0x18000d8f6  test    rcx, rcx
0x18000d8f9  jnz     short loc_18000D8FF
0x18000d8fb  xor     al, al
0x18000d8fd  jmp     short loc_18000D93F
0x18000d8ff  xor     r9d, r9d; lpSecurityAttributes
0x18000d902  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18000d90b  mov     [rsp+48h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x18000d913  mov     edx, 80000000h; dwDesiredAccess
0x18000d918  xor     bl, bl
0x18000d91a  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x18000d922  lea     r8d, [r9+1]; dwShareMode
0x18000d926  call    cs:__imp_CreateFileW
0x18000d92c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000d930  jz      short loc_18000D93D
0x18000d932  mov     rcx, rax; hObject
0x18000d935  mov     bl, 1
0x18000d937  call    cs:__imp_CloseHandle
0x18000d93d  mov     al, bl
0x18000d93f  add     rsp, 40h
0x18000d943  pop     rbx
0x18000d944  retn
```
