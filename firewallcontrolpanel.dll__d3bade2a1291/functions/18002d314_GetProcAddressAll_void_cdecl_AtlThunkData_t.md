# GetProcAddressAll_void_(__cdecl_)(AtlThunkData_t__)_

- ea: `0x18002d314`
- end: `0x18002d3d4`
- name: `GetProcAddressAll_void_(__cdecl_)(AtlThunkData_t__)_`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002d6f0`

## callees

- `0x18002d314`
- `0x18002d4a4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18002d345`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18002d345`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18002d32f`

## string_xrefs

- `0x18002d338`: `atlthunk.dll`

## pseudocode

```c
PVOID GetProcAddressAll_void____cdecl___AtlThunkData_t____()
{
  HMODULE Library; // rax
  HMODULE v2; // rbx
  signed __int32 v3[10]; // [rsp+0h] [rbp-28h] BYREF

  if ( byte_180046328 )
    return DecodePointer((PVOID)qword_180046390);
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
    return DecodePointer((PVOID)qword_180046390);
  }
  return 0;
}

```

## disassembly

```asm
0x18002d314  push    rbx
0x18002d316  sub     rsp, 20h
0x18002d31a  cmp     cs:byte_180046328, 0
0x18002d321  jz      short loc_18002D336
0x18002d323  mov     rcx, cs:qword_180046390
0x18002d32a  add     rsp, 20h
0x18002d32e  pop     rbx
0x18002d32f  jmp     cs:__imp_DecodePointer
0x18002d336  xor     edx, edx; hFile
0x18002d338  lea     rcx, LibFileName; "atlthunk.dll"
0x18002d33f  mov     r8d, 800h; dwFlags
0x18002d345  call    cs:__imp_LoadLibraryExA
0x18002d34b  mov     rbx, rax
0x18002d34e  test    rax, rax
0x18002d351  jz      short loc_18002D3CC
0x18002d353  lea     r8, qword_1800463A8
0x18002d35a  mov     rcx, rax
0x18002d35d  lea     rdx, aAtlthunkAlloca; "AtlThunk_AllocateData"
0x18002d364  call    GetProcAddressSingle
0x18002d369  test    al, al
0x18002d36b  jz      short loc_18002D3CC
0x18002d36d  lea     r8, qword_1800463A0
0x18002d374  mov     rcx, rbx
0x18002d377  lea     rdx, aAtlthunkInitda; "AtlThunk_InitData"
0x18002d37e  call    GetProcAddressSingle
0x18002d383  test    al, al
0x18002d385  jz      short loc_18002D3CC
0x18002d387  lea     r8, qword_180046398
0x18002d38e  mov     rcx, rbx
0x18002d391  lea     rdx, aAtlthunkDatato; "AtlThunk_DataToCode"
0x18002d398  call    GetProcAddressSingle
0x18002d39d  test    al, al
0x18002d39f  jz      short loc_18002D3CC
0x18002d3a1  lea     r8, qword_180046390
0x18002d3a8  mov     rcx, rbx
0x18002d3ab  lea     rdx, aAtlthunkFreeda; "AtlThunk_FreeData"
0x18002d3b2  call    GetProcAddressSingle
0x18002d3b7  test    al, al
0x18002d3b9  jz      short loc_18002D3CC
0x18002d3bb  lock or [rsp+28h+var_28], 0
0x18002d3c0  mov     cs:byte_180046328, 1
0x18002d3c7  jmp     loc_18002D323
0x18002d3cc  xor     eax, eax
0x18002d3ce  add     rsp, 20h
0x18002d3d2  pop     rbx
0x18002d3d3  retn
```
