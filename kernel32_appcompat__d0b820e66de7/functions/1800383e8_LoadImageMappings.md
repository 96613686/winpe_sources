# LoadImageMappings

- ea: `0x1800383e8`
- end: `0x1800384ba`
- name: `LoadImageMappings`
- size: `210`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x180038290`

## callees

- `0x1800383e8`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x18003845d`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x18003845d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038498`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038498`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003841c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003841c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180038482`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180038482`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003843b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003843b`

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
0x1800383e8  mov     rax, rsp
0x1800383eb  mov     [rax+8], rbx
0x1800383ef  push    rdi
0x1800383f0  sub     rsp, 40h
0x1800383f4  mov     qword ptr [rax-18h], 0
0x1800383fc  xor     r9d, r9d; lpSecurityAttributes
0x1800383ff  mov     rbx, rcx
0x180038402  mov     dword ptr [rax-20h], 80h
0x180038409  mov     rcx, [rcx]; lpFileName
0x18003840c  mov     edx, 80000000h; dwDesiredAccess
0x180038411  mov     dword ptr [rax-28h], 3
0x180038418  lea     r8d, [r9+5]; dwShareMode
0x18003841c  call    cs:__imp_CreateFileW
0x180038423  nop     dword ptr [rax+rax+00h]
0x180038428  mov     [rbx+38h], rax
0x18003842c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180038430  jz      short loc_180038477
0x180038432  mov     rcx, [rbx]; lpLibFileName
0x180038435  xor     edx, edx; hFile
0x180038437  lea     r8d, [rdx+22h]; dwFlags
0x18003843b  call    cs:__imp_LoadLibraryExW
0x180038442  nop     dword ptr [rax+rax+00h]
0x180038447  mov     [rbx+40h], rax
0x18003844b  test    rax, rax
0x18003844e  jz      short loc_180038477
0x180038450  lea     rdx, [rbx+8]; lpBuffer
0x180038454  mov     r8d, 30h ; '0'; dwLength
0x18003845a  mov     rcx, rax; lpAddress
0x18003845d  call    cs:__imp_VirtualQuery
0x180038464  nop     dword ptr [rax+rax+00h]
0x180038469  cmp     rax, 30h ; '0'
0x18003846d  jnz     short loc_180038477
0x18003846f  lea     edi, [rax-2Fh]
0x180038472  mov     [rbx+5Ch], edi
0x180038475  jmp     short loc_1800384AC
0x180038477  mov     rcx, [rbx+40h]; hLibModule
0x18003847b  xor     edi, edi
0x18003847d  test    rcx, rcx
0x180038480  jz      short loc_18003848E
0x180038482  call    cs:__imp_FreeLibrary
0x180038489  nop     dword ptr [rax+rax+00h]
0x18003848e  mov     rcx, [rbx+38h]; hObject
0x180038492  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180038496  jz      short loc_1800384AC
0x180038498  call    cs:__imp_CloseHandle
0x18003849f  nop     dword ptr [rax+rax+00h]
0x1800384a4  mov     qword ptr [rbx+38h], 0FFFFFFFFFFFFFFFFh
0x1800384ac  mov     rbx, [rsp+48h+arg_0]
0x1800384b1  mov     eax, edi
0x1800384b3  add     rsp, 40h
0x1800384b7  pop     rdi
0x1800384b8  retn
```
