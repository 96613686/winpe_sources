# GetProcAddressAll_void_(__cdecl_)(AtlThunkData_t___void___unsigned___int64)_

- ea: `0x18002d3dc`
- end: `0x18002d49c`
- name: `GetProcAddressAll_void_(__cdecl_)(AtlThunkData_t___void___unsigned___int64)_`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002d748`

## callees

- `0x18002d3dc`
- `0x18002d4a4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18002d40d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18002d40d`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18002d3f7`

## string_xrefs

- `0x18002d400`: `atlthunk.dll`

## pseudocode

```c
PVOID GetProcAddressAll_void____cdecl___AtlThunkData_t___void___unsigned___int64__()
{
  HMODULE Library; // rax
  HMODULE v2; // rbx
  signed __int32 v3[10]; // [rsp+0h] [rbp-28h] BYREF

  if ( byte_180046328 )
    return DecodePointer((PVOID)qword_1800463A0);
  Library = LoadLibraryExA("atlthunk.dll", 0, 0x800u);
  v2 = Library;
  if ( Library
    && (unsigned __int8)GetProcAddressSingle(Library, "AtlThunk_AllocateData", &qword_1800463A8)
    && (unsigned __int8)GetProcAddressSingle(v2, "AtlThunk_InitData", &qword_1800463A0)
    && (unsigned __int8)GetProcAddressSingle(v2, "AtlThunk_DataToCode", &qword_180046398)
    && (unsigned __int8)GetProcAddressSingle(v2, "AtlThunk_FreeData", &qword_180046390) )
  {
    _InterlockedOr(v3, 0);
    byte_180046328 = 1;
    return DecodePointer((PVOID)qword_1800463A0);
  }
  return 0;
}

```

## disassembly

```asm
0x18002d3dc  push    rbx
0x18002d3de  sub     rsp, 20h
0x18002d3e2  cmp     cs:byte_180046328, 0
0x18002d3e9  jz      short loc_18002D3FE
0x18002d3eb  mov     rcx, cs:qword_1800463A0
0x18002d3f2  add     rsp, 20h
0x18002d3f6  pop     rbx
0x18002d3f7  jmp     cs:__imp_DecodePointer
0x18002d3fe  xor     edx, edx; hFile
0x18002d400  lea     rcx, LibFileName; "atlthunk.dll"
0x18002d407  mov     r8d, 800h; dwFlags
0x18002d40d  call    cs:__imp_LoadLibraryExA
0x18002d413  mov     rbx, rax
0x18002d416  test    rax, rax
0x18002d419  jz      short loc_18002D494
0x18002d41b  lea     r8, qword_1800463A8
0x18002d422  mov     rcx, rax
0x18002d425  lea     rdx, aAtlthunkAlloca; "AtlThunk_AllocateData"
0x18002d42c  call    GetProcAddressSingle
0x18002d431  test    al, al
0x18002d433  jz      short loc_18002D494
0x18002d435  lea     r8, qword_1800463A0
0x18002d43c  mov     rcx, rbx
0x18002d43f  lea     rdx, aAtlthunkInitda; "AtlThunk_InitData"
0x18002d446  call    GetProcAddressSingle
0x18002d44b  test    al, al
0x18002d44d  jz      short loc_18002D494
0x18002d44f  lea     r8, qword_180046398
0x18002d456  mov     rcx, rbx
0x18002d459  lea     rdx, aAtlthunkDatato; "AtlThunk_DataToCode"
0x18002d460  call    GetProcAddressSingle
0x18002d465  test    al, al
0x18002d467  jz      short loc_18002D494
0x18002d469  lea     r8, qword_180046390
0x18002d470  mov     rcx, rbx
0x18002d473  lea     rdx, aAtlthunkFreeda; "AtlThunk_FreeData"
0x18002d47a  call    GetProcAddressSingle
0x18002d47f  test    al, al
0x18002d481  jz      short loc_18002D494
0x18002d483  lock or [rsp+28h+var_28], 0
0x18002d488  mov     cs:byte_180046328, 1
0x18002d48f  jmp     loc_18002D3EB
0x18002d494  xor     eax, eax
0x18002d496  add     rsp, 20h
0x18002d49a  pop     rbx
0x18002d49b  retn
```
