# MapMUIFile

- ea: `0x180345f58`
- end: `0x18034606b`
- name: `MapMUIFile`
- size: `275`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x1803460c8`
- `0x1803461f8`

## callees

- `0x180345f58`

## import_xrefs

- `KERNEL32!MapViewOfFile` at `0x180346011`
- `KERNEL32!MapViewOfFile` at `0x180346011`
- `KERNEL32!CreateFileMappingW` at `0x180345fd8`
- `KERNEL32!CreateFileMappingW` at `0x180345fd8`
- `KERNEL32!CreateFileW` at `0x180345fa2`
- `KERNEL32!CreateFileW` at `0x180345fa2`
- `KERNEL32!LoadLibraryExW` at `0x18034604f`
- `KERNEL32!LoadLibraryExW` at `0x18034604f`
- `KERNEL32!CloseHandle` at `0x180345fea`
- `KERNEL32!CloseHandle` at `0x180346023`
- `KERNEL32!CloseHandle` at `0x180345fea`
- `KERNEL32!CloseHandle` at `0x180346023`

## pseudocode

```c
HMODULE __fastcall MapMUIFile(const WCHAR *a1, int a2, int a3)
{
  HANDLE FileW; // rax
  void *v4; // rbx
  HANDLE FileMappingW; // rdi
  unsigned __int64 v6; // rbx

  if ( a1 )
  {
    if ( !a2 )
      return LoadLibraryExW(a1, 0, a3 != 0);
    FileW = CreateFileW(a1, 0x80000000, 5u, 0, 3u, 0, 0);
    v4 = FileW;
    if ( FileW != (HANDLE)-1LL )
    {
      FileMappingW = CreateFileMappingW(FileW, 0, 8u, 0, 0, 0);
      CloseHandle(v4);
      if ( FileMappingW )
      {
        v6 = (unsigned __int64)MapViewOfFile(FileMappingW, 1u, 0, 0, 0);
        CloseHandle(FileMappingW);
        return (HMODULE)((v6 | 1) & -(__int64)(v6 != 0));
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180345f58  mov     rax, rsp
0x180345f5b  mov     [rax+20h], rbx
0x180345f5f  mov     [rax+18h], r8d
0x180345f63  mov     [rax+10h], edx
0x180345f66  mov     [rax+8], rcx
0x180345f6a  push    rdi
0x180345f6b  sub     rsp, 40h
0x180345f6f  test    rcx, rcx
0x180345f72  jz      loc_18034605D
0x180345f78  test    edx, edx
0x180345f7a  jz      loc_180346041
0x180345f80  mov     qword ptr [rax-18h], 0
0x180345f88  xor     r9d, r9d; lpSecurityAttributes
0x180345f8b  mov     dword ptr [rax-20h], 0
0x180345f92  mov     edx, 80000000h; dwDesiredAccess
0x180345f97  mov     dword ptr [rax-28h], 3
0x180345f9e  lea     r8d, [r9+5]; dwShareMode
0x180345fa2  call    cs:__imp_CreateFileW
0x180345fa9  nop     dword ptr [rax+rax+00h]
0x180345fae  mov     rbx, rax
0x180345fb1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180345fb5  jz      loc_18034605D
0x180345fbb  xor     r9d, r9d; dwMaximumSizeHigh
0x180345fbe  mov     [rsp+48h+lpName], 0; lpName
0x180345fc7  xor     edx, edx; lpFileMappingAttributes
0x180345fc9  mov     [rsp+48h+dwMaximumSizeLow], 0; dwMaximumSizeLow
0x180345fd1  mov     rcx, rax; hFile
0x180345fd4  lea     r8d, [r9+8]; flProtect
0x180345fd8  call    cs:__imp_CreateFileMappingW
0x180345fdf  nop     dword ptr [rax+rax+00h]
0x180345fe4  mov     rcx, rbx; hObject
0x180345fe7  mov     rdi, rax
0x180345fea  call    cs:__imp_CloseHandle
0x180345ff1  nop     dword ptr [rax+rax+00h]
0x180345ff6  test    rdi, rdi
0x180345ff9  jz      short loc_18034605D
0x180345ffb  xor     r9d, r9d; dwFileOffsetLow
0x180345ffe  mov     qword ptr [rsp+48h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x180346007  xor     r8d, r8d; dwFileOffsetHigh
0x18034600a  mov     rcx, rdi; hFileMappingObject
0x18034600d  lea     edx, [r9+1]; dwDesiredAccess
0x180346011  call    cs:__imp_MapViewOfFile
0x180346018  nop     dword ptr [rax+rax+00h]
0x18034601d  mov     rcx, rdi; hObject
0x180346020  mov     rbx, rax
0x180346023  call    cs:__imp_CloseHandle
0x18034602a  nop     dword ptr [rax+rax+00h]
0x18034602f  mov     rcx, rbx
0x180346032  or      rcx, 1; lpLibFileName
0x180346036  neg     rbx
0x180346039  sbb     rax, rax
0x18034603c  and     rax, rcx
0x18034603f  jmp     short loc_18034605F
0x180346041  xor     r8d, r8d
0x180346044  cmp     [rsp+48h+arg_10], r8d
0x180346049  setnz   r8b; dwFlags
0x18034604d  xor     edx, edx; hFile
0x18034604f  call    cs:__imp_LoadLibraryExW
0x180346056  nop     dword ptr [rax+rax+00h]
0x18034605b  jmp     short loc_18034605F
0x18034605d  xor     eax, eax
0x18034605f  mov     rbx, [rsp+48h+arg_18]
0x180346064  add     rsp, 40h
0x180346068  pop     rdi
0x180346069  retn
```
