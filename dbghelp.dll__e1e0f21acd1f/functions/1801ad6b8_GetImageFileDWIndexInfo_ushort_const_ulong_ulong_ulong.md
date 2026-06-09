# GetImageFileDWIndexInfo(ushort const *,ulong *,ulong *,ulong *)

- ea: `0x1801ad6b8`
- end: `0x1801ad731`
- name: `?GetImageFileDWIndexInfo@@YAHPEBGPEAK11@Z`
- size: `121`
- prototype: `int(const unsigned __int16 *, unsigned int *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1801ae340`

## callees

- `0x1801ad6b8`
- `0x1801ad7e8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801ad6f0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801ad6f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801ad719`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801ad719`

## pseudocode

```c
__int64 __fastcall GetImageFileDWIndexInfo(
        const unsigned __int16 *a1,
        unsigned int *a2,
        unsigned int *a3,
        unsigned int *a4)
{
  HANDLE FileW; // rax
  void *v7; // rdi
  unsigned int ImageIndexInfo; // ebx

  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0, 0);
  v7 = FileW;
  if ( FileW == (HANDLE)-1LL )
    return 0;
  ImageIndexInfo = GetImageIndexInfo(FileW, a2, a3, 0);
  CloseHandle(v7);
  return ImageIndexInfo;
}

```

## disassembly

```asm
0x1801ad6b8  mov     rax, rsp
0x1801ad6bb  mov     [rax+8], rbx
0x1801ad6bf  mov     [rax+10h], rsi
0x1801ad6c3  push    rdi
0x1801ad6c4  sub     rsp, 40h
0x1801ad6c8  mov     qword ptr [rax-18h], 0
0x1801ad6d0  xor     r9d, r9d; lpSecurityAttributes
0x1801ad6d3  mov     rbx, r8
0x1801ad6d6  mov     dword ptr [rax-20h], 0
0x1801ad6dd  mov     rsi, rdx
0x1801ad6e0  mov     dword ptr [rax-28h], 3
0x1801ad6e7  mov     edx, 80000000h; dwDesiredAccess
0x1801ad6ec  lea     r8d, [r9+1]; dwShareMode
0x1801ad6f0  call    cs:__imp_CreateFileW
0x1801ad6f6  mov     rdi, rax
0x1801ad6f9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801ad6fd  jnz     short loc_1801AD703
0x1801ad6ff  xor     eax, eax
0x1801ad701  jmp     short loc_1801AD721
0x1801ad703  xor     r9d, r9d; unsigned int *
0x1801ad706  mov     r8, rbx; unsigned int *
0x1801ad709  mov     rdx, rsi; unsigned int *
0x1801ad70c  mov     rcx, rdi; void *
0x1801ad70f  call    ?GetImageIndexInfo@@YAHPEAXPEAK11@Z; GetImageIndexInfo(void *,ulong *,ulong *,ulong *)
0x1801ad714  mov     rcx, rdi; hObject
0x1801ad717  mov     ebx, eax
0x1801ad719  call    cs:__imp_CloseHandle
0x1801ad71f  mov     eax, ebx
0x1801ad721  mov     rbx, [rsp+48h+arg_0]
0x1801ad726  mov     rsi, [rsp+48h+arg_8]
0x1801ad72b  add     rsp, 40h
0x1801ad72f  pop     rdi
0x1801ad730  retn
```
