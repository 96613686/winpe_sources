# LoadImageMappings

- ea: `0x180035cc4`
- end: `0x180035d77`
- name: `LoadImageMappings`
- size: `179`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x180035b74`

## callees

- `0x180035cc4`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x180035d2d`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x180035d2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035d5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035d5c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180035cf8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180035cf8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180035d4c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180035d4c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180035d11`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180035d11`

## pseudocode

```c
__int64 __fastcall LoadImageMappings(__int64 a1)
{
  HANDLE FileW; // rax
  HMODULE Library; // rax
  unsigned int v4; // edi
  HMODULE v5; // rcx
  void *v6; // rcx

  FileW = CreateFileW(*(LPCWSTR *)a1, 0x80000000, 5u, 0, 3u, 0x80u, 0);
  *(_QWORD *)(a1 + 56) = FileW;
  if ( FileW != (HANDLE)-1LL
    && (Library = LoadLibraryExW(*(LPCWSTR *)a1, 0, 0x22u), (*(_QWORD *)(a1 + 64) = Library) != 0)
    && VirtualQuery(Library, (PMEMORY_BASIC_INFORMATION)(a1 + 8), 0x30u) == 48 )
  {
    v4 = 1;
    *(_DWORD *)(a1 + 92) = 1;
  }
  else
  {
    v5 = *(HMODULE *)(a1 + 64);
    v4 = 0;
    if ( v5 )
      FreeLibrary(v5);
    v6 = *(void **)(a1 + 56);
    if ( v6 != (void *)-1LL )
    {
      CloseHandle(v6);
      *(_QWORD *)(a1 + 56) = -1;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180035cc4  mov     rax, rsp
0x180035cc7  mov     [rax+8], rbx
0x180035ccb  push    rdi
0x180035ccc  sub     rsp, 40h
0x180035cd0  mov     qword ptr [rax-18h], 0
0x180035cd8  xor     r9d, r9d; lpSecurityAttributes
0x180035cdb  mov     rbx, rcx
0x180035cde  mov     dword ptr [rax-20h], 80h
0x180035ce5  mov     rcx, [rcx]; lpFileName
0x180035ce8  mov     edx, 80000000h; dwDesiredAccess
0x180035ced  mov     dword ptr [rax-28h], 3
0x180035cf4  lea     r8d, [r9+5]; dwShareMode
0x180035cf8  call    cs:__imp_CreateFileW
0x180035cfe  mov     [rbx+38h], rax
0x180035d02  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180035d06  jz      short loc_180035D41
0x180035d08  mov     rcx, [rbx]; lpLibFileName
0x180035d0b  xor     edx, edx; hFile
0x180035d0d  lea     r8d, [rdx+22h]; dwFlags
0x180035d11  call    cs:__imp_LoadLibraryExW
0x180035d17  mov     [rbx+40h], rax
0x180035d1b  test    rax, rax
0x180035d1e  jz      short loc_180035D41
0x180035d20  lea     rdx, [rbx+8]; lpBuffer
0x180035d24  mov     r8d, 30h ; '0'; dwLength
0x180035d2a  mov     rcx, rax; lpAddress
0x180035d2d  call    cs:__imp_VirtualQuery
0x180035d33  cmp     rax, 30h ; '0'
0x180035d37  jnz     short loc_180035D41
0x180035d39  lea     edi, [rax-2Fh]
0x180035d3c  mov     [rbx+5Ch], edi
0x180035d3f  jmp     short loc_180035D6A
0x180035d41  mov     rcx, [rbx+40h]; hLibModule
0x180035d45  xor     edi, edi
0x180035d47  test    rcx, rcx
0x180035d4a  jz      short loc_180035D52
0x180035d4c  call    cs:__imp_FreeLibrary
0x180035d52  mov     rcx, [rbx+38h]; hObject
0x180035d56  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180035d5a  jz      short loc_180035D6A
0x180035d5c  call    cs:__imp_CloseHandle
0x180035d62  mov     qword ptr [rbx+38h], 0FFFFFFFFFFFFFFFFh
0x180035d6a  mov     rbx, [rsp+48h+arg_0]
0x180035d6f  mov     eax, edi
0x180035d71  add     rsp, 40h
0x180035d75  pop     rdi
0x180035d76  retn
```
