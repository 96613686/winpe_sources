# EfsEnsureLocalPath

- ea: `0x18000c094`
- end: `0x18000c0ff`
- name: `EfsEnsureLocalPath`
- size: `107`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800059a0`
- `0x180005d00`
- `0x1800060c0`
- `0x1800069d0`
- `0x1800070d0`
- `0x1800072b0`
- `0x180007530`
- `0x1800080c4`

## callees

- `0x18000bfd4`
- `0x18000c094`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c0e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c0e5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000c0be`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000c0be`

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
0x18000c094  mov     rax, rsp
0x18000c097  mov     [rax+8], rbx
0x18000c09b  push    rdi
0x18000c09c  sub     rsp, 40h
0x18000c0a0  mov     qword ptr [rax-18h], 0
0x18000c0a8  xor     r9d, r9d; lpSecurityAttributes
0x18000c0ab  mov     dword ptr [rax-20h], 2000000h
0x18000c0b2  xor     r8d, r8d; dwShareMode
0x18000c0b5  xor     edx, edx; dwDesiredAccess
0x18000c0b7  mov     dword ptr [rax-28h], 3
0x18000c0be  call    cs:__imp_CreateFileW
0x18000c0c5  nop     dword ptr [rax+rax+00h]
0x18000c0ca  mov     rdi, rax
0x18000c0cd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000c0d1  jnz     short loc_18000C0D8
0x18000c0d3  lea     ebx, [rax+6]
0x18000c0d6  jmp     short loc_18000C0F1
0x18000c0d8  mov     rcx, rdi
0x18000c0db  call    EfsEnsureLocalHandle
0x18000c0e0  mov     ebx, eax
0x18000c0e2  mov     rcx, rdi; hObject
0x18000c0e5  call    cs:__imp_CloseHandle
0x18000c0ec  nop     dword ptr [rax+rax+00h]
0x18000c0f1  mov     eax, ebx
0x18000c0f3  mov     rbx, [rsp+48h+arg_0]
0x18000c0f8  add     rsp, 40h
0x18000c0fc  pop     rdi
0x18000c0fd  retn
```
