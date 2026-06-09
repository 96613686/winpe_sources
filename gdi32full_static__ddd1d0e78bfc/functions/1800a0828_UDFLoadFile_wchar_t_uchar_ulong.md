# UDFLoadFile(wchar_t *,uchar *,ulong)

- ea: `0x1800a0828`
- end: `0x1800a08dc`
- name: `?UDFLoadFile@@YAHPEA_WPEAEK@Z`
- size: `180`
- prototype: `int(wchar_t *, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800a08e4`

## callees

- `0x1800a0828`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a086b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a086b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800a089e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800a089e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a08bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a08bd`

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
0x1800a0828  mov     rax, rsp
0x1800a082b  mov     [rax+8], rbx
0x1800a082f  mov     [rax+10h], rsi
0x1800a0833  mov     [rax+18h], r8d
0x1800a0837  push    rdi
0x1800a0838  sub     rsp, 40h
0x1800a083c  mov     qword ptr [rax-18h], 0
0x1800a0844  xor     r9d, r9d; lpSecurityAttributes
0x1800a0847  mov     rsi, rdx
0x1800a084a  mov     dword ptr [rax-20h], 80h
0x1800a0851  mov     edx, 80000000h; dwDesiredAccess
0x1800a0856  mov     dword ptr [rax+18h], 0
0x1800a085d  mov     dword ptr [rax-28h], 3
0x1800a0864  lea     ebx, [r9+1]
0x1800a0868  mov     r8d, ebx; dwShareMode
0x1800a086b  call    cs:__imp_CreateFileW
0x1800a0872  nop     dword ptr [rax+rax+00h]
0x1800a0877  mov     rdi, rax
0x1800a087a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800a087e  jnz     short loc_1800A0884
0x1800a0880  xor     eax, eax
0x1800a0882  jmp     short loc_1800A08CB
0x1800a0884  lea     r9, [rsp+48h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800a0889  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x1800a0892  mov     r8d, 102h; nNumberOfBytesToRead
0x1800a0898  mov     rdx, rsi; lpBuffer
0x1800a089b  mov     rcx, rdi; hFile
0x1800a089e  call    cs:__imp_ReadFile
0x1800a08a5  nop     dword ptr [rax+rax+00h]
0x1800a08aa  test    eax, eax
0x1800a08ac  jz      short loc_1800A08B8
0x1800a08ae  cmp     [rsp+48h+NumberOfBytesRead], 102h
0x1800a08b6  jz      short loc_1800A08BA
0x1800a08b8  xor     ebx, ebx
0x1800a08ba  mov     rcx, rdi; hObject
0x1800a08bd  call    cs:__imp_CloseHandle
0x1800a08c4  nop     dword ptr [rax+rax+00h]
0x1800a08c9  mov     eax, ebx
0x1800a08cb  mov     rbx, [rsp+48h+arg_0]
0x1800a08d0  mov     rsi, [rsp+48h+arg_8]
0x1800a08d5  add     rsp, 40h
0x1800a08d9  pop     rdi
0x1800a08da  retn
```
