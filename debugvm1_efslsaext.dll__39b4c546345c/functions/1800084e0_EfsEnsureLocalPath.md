# EfsEnsureLocalPath

- ea: `0x1800084e0`
- end: `0x18000853e`
- name: `EfsEnsureLocalPath`
- size: `94`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180007320`
- `0x180007460`
- `0x180007590`
- `0x180007750`
- `0x180007890`
- `0x180007a30`
- `0x180007b10`
- `0x180007c20`

## callees

- `0x18000842c`
- `0x1800084e0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000852b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000852b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000850a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000850a`

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
0x1800084e0  mov     rax, rsp
0x1800084e3  mov     [rax+8], rbx
0x1800084e7  push    rdi
0x1800084e8  sub     rsp, 40h
0x1800084ec  mov     qword ptr [rax-18h], 0
0x1800084f4  xor     r9d, r9d; lpSecurityAttributes
0x1800084f7  mov     dword ptr [rax-20h], 2000000h
0x1800084fe  xor     r8d, r8d; dwShareMode
0x180008501  xor     edx, edx; dwDesiredAccess
0x180008503  mov     dword ptr [rax-28h], 3
0x18000850a  call    cs:__imp_CreateFileW
0x180008510  mov     rdi, rax
0x180008513  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180008517  jnz     short loc_18000851E
0x180008519  lea     ebx, [rax+6]
0x18000851c  jmp     short loc_180008531
0x18000851e  mov     rcx, rdi
0x180008521  call    EfsEnsureLocalHandle
0x180008526  mov     ebx, eax
0x180008528  mov     rcx, rdi; hObject
0x18000852b  call    cs:__imp_CloseHandle
0x180008531  mov     eax, ebx
0x180008533  mov     rbx, [rsp+48h+arg_0]
0x180008538  add     rsp, 40h
0x18000853c  pop     rdi
0x18000853d  retn
```
