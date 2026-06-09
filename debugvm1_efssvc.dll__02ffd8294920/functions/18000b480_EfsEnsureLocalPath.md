# EfsEnsureLocalPath

- ea: `0x18000b480`
- end: `0x18000b4de`
- name: `EfsEnsureLocalPath`
- size: `94`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800055b0`
- `0x1800058a0`
- `0x180005bc0`
- `0x1800063c0`
- `0x180006a00`
- `0x180006bb0`
- `0x180006df0`
- `0x180007810`

## callees

- `0x18000b3cc`
- `0x18000b480`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b4cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b4cb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000b4aa`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000b4aa`

## pseudocode

```c
__int64 __fastcall EfsEnsureLocalPath(const WCHAR *a1)
{
  HANDLE FileW; // rax
  void *v2; // rdi
  unsigned int v3; // ebx

  FileW = CreateFileW(a1, 0, 0, 0, 3u, 0x2000000u, 0);
  v2 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    return 5;
  }
  else
  {
    v3 = EfsEnsureLocalHandle(FileW);
    CloseHandle(v2);
  }
  return v3;
}

```

## disassembly

```asm
0x18000b480  mov     rax, rsp
0x18000b483  mov     [rax+8], rbx
0x18000b487  push    rdi
0x18000b488  sub     rsp, 40h
0x18000b48c  mov     qword ptr [rax-18h], 0
0x18000b494  xor     r9d, r9d; lpSecurityAttributes
0x18000b497  mov     dword ptr [rax-20h], 2000000h
0x18000b49e  xor     r8d, r8d; dwShareMode
0x18000b4a1  xor     edx, edx; dwDesiredAccess
0x18000b4a3  mov     dword ptr [rax-28h], 3
0x18000b4aa  call    cs:__imp_CreateFileW
0x18000b4b0  mov     rdi, rax
0x18000b4b3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000b4b7  jnz     short loc_18000B4BE
0x18000b4b9  lea     ebx, [rax+6]
0x18000b4bc  jmp     short loc_18000B4D1
0x18000b4be  mov     rcx, rdi
0x18000b4c1  call    EfsEnsureLocalHandle
0x18000b4c6  mov     ebx, eax
0x18000b4c8  mov     rcx, rdi; hObject
0x18000b4cb  call    cs:__imp_CloseHandle
0x18000b4d1  mov     eax, ebx
0x18000b4d3  mov     rbx, [rsp+48h+arg_0]
0x18000b4d8  add     rsp, 40h
0x18000b4dc  pop     rdi
0x18000b4dd  retn
```
