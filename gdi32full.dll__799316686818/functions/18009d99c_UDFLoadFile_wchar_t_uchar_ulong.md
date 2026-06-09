# UDFLoadFile(wchar_t *,uchar *,ulong)

- ea: `0x18009d99c`
- end: `0x18009da3d`
- name: `?UDFLoadFile@@YAHPEA_WPEAEK@Z`
- size: `161`
- prototype: `int(wchar_t *, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18009da44`

## callees

- `0x18009d99c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009d9df`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009d9df`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18009da0c`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18009da0c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009da25`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009da25`

## pseudocode

```c
__int64 __fastcall UDFLoadFile(wchar_t *a1, unsigned __int8 *a2)
{
  unsigned int v3; // ebx
  HANDLE FileW; // rax
  void *v5; // rdi
  DWORD NumberOfBytesRead; // [rsp+60h] [rbp+18h] BYREF

  NumberOfBytesRead = 0;
  v3 = 1;
  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v5 = FileW;
  if ( FileW == (HANDLE)-1LL )
    return 0;
  if ( !ReadFile(FileW, a2, 0x102u, &NumberOfBytesRead, 0) || NumberOfBytesRead != 258 )
    v3 = 0;
  CloseHandle(v5);
  return v3;
}

```

## disassembly

```asm
0x18009d99c  mov     rax, rsp
0x18009d99f  mov     [rax+8], rbx
0x18009d9a3  mov     [rax+10h], rsi
0x18009d9a7  mov     [rax+18h], r8d
0x18009d9ab  push    rdi
0x18009d9ac  sub     rsp, 40h
0x18009d9b0  mov     qword ptr [rax-18h], 0
0x18009d9b8  xor     r9d, r9d; lpSecurityAttributes
0x18009d9bb  mov     rsi, rdx
0x18009d9be  mov     dword ptr [rax-20h], 80h
0x18009d9c5  mov     edx, 80000000h; dwDesiredAccess
0x18009d9ca  mov     dword ptr [rax+18h], 0
0x18009d9d1  mov     dword ptr [rax-28h], 3
0x18009d9d8  lea     ebx, [r9+1]
0x18009d9dc  mov     r8d, ebx; dwShareMode
0x18009d9df  call    cs:__imp_CreateFileW
0x18009d9e5  mov     rdi, rax
0x18009d9e8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18009d9ec  jnz     short loc_18009D9F2
0x18009d9ee  xor     eax, eax
0x18009d9f0  jmp     short loc_18009DA2D
0x18009d9f2  lea     r9, [rsp+48h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18009d9f7  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x18009da00  mov     r8d, 102h; nNumberOfBytesToRead
0x18009da06  mov     rdx, rsi; lpBuffer
0x18009da09  mov     rcx, rdi; hFile
0x18009da0c  call    cs:__imp_ReadFile
0x18009da12  test    eax, eax
0x18009da14  jz      short loc_18009DA20
0x18009da16  cmp     [rsp+48h+NumberOfBytesRead], 102h
0x18009da1e  jz      short loc_18009DA22
0x18009da20  xor     ebx, ebx
0x18009da22  mov     rcx, rdi; hObject
0x18009da25  call    cs:__imp_CloseHandle
0x18009da2b  mov     eax, ebx
0x18009da2d  mov     rbx, [rsp+48h+arg_0]
0x18009da32  mov     rsi, [rsp+48h+arg_8]
0x18009da37  add     rsp, 40h
0x18009da3b  pop     rdi
0x18009da3c  retn
```
