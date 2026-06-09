# GetProcAddressAll___int64_(__cdecl_(__cdecl_)(AtlThunkData_t__))(HWND_____unsigned_int_unsigned___int64___int64)_

- ea: `0x18002d184`
- end: `0x18002d244`
- name: `GetProcAddressAll___int64_(__cdecl_(__cdecl_)(AtlThunkData_t__))(HWND_____unsigned_int_unsigned___int64___int64)_`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002d6ac`

## callees

- `0x18002d184`
- `0x18002d4a4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18002d1b5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18002d1b5`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18002d19f`

## string_xrefs

- `0x18002d1a8`: `atlthunk.dll`

## pseudocode

```c
PVOID GetProcAddressAll___int64____cdecl____cdecl___AtlThunkData_t_____HWND_____unsigned_int_unsigned___int64___int64__()
{
  HMODULE Library; // rax
  HMODULE v2; // rbx
  signed __int32 v3[10]; // [rsp+0h] [rbp-28h] BYREF

  if ( byte_180046328 )
    return DecodePointer((PVOID)qword_180046398);
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
    return DecodePointer((PVOID)qword_180046398);
  }
  return 0;
}

```

## disassembly

```asm
0x18002d184  push    rbx
0x18002d186  sub     rsp, 20h
0x18002d18a  cmp     cs:byte_180046328, 0
0x18002d191  jz      short loc_18002D1A6
0x18002d193  mov     rcx, cs:qword_180046398
0x18002d19a  add     rsp, 20h
0x18002d19e  pop     rbx
0x18002d19f  jmp     cs:__imp_DecodePointer
0x18002d1a6  xor     edx, edx; hFile
0x18002d1a8  lea     rcx, LibFileName; "atlthunk.dll"
0x18002d1af  mov     r8d, 800h; dwFlags
0x18002d1b5  call    cs:__imp_LoadLibraryExA
0x18002d1bb  mov     rbx, rax
0x18002d1be  test    rax, rax
0x18002d1c1  jz      short loc_18002D23C
0x18002d1c3  lea     r8, qword_1800463A8
0x18002d1ca  mov     rcx, rax
0x18002d1cd  lea     rdx, aAtlthunkAlloca; "AtlThunk_AllocateData"
0x18002d1d4  call    GetProcAddressSingle
0x18002d1d9  test    al, al
0x18002d1db  jz      short loc_18002D23C
0x18002d1dd  lea     r8, qword_1800463A0
0x18002d1e4  mov     rcx, rbx
0x18002d1e7  lea     rdx, aAtlthunkInitda; "AtlThunk_InitData"
0x18002d1ee  call    GetProcAddressSingle
0x18002d1f3  test    al, al
0x18002d1f5  jz      short loc_18002D23C
0x18002d1f7  lea     r8, qword_180046398
0x18002d1fe  mov     rcx, rbx
0x18002d201  lea     rdx, aAtlthunkDatato; "AtlThunk_DataToCode"
0x18002d208  call    GetProcAddressSingle
0x18002d20d  test    al, al
0x18002d20f  jz      short loc_18002D23C
0x18002d211  lea     r8, qword_180046390
0x18002d218  mov     rcx, rbx
0x18002d21b  lea     rdx, aAtlthunkFreeda; "AtlThunk_FreeData"
0x18002d222  call    GetProcAddressSingle
0x18002d227  test    al, al
0x18002d229  jz      short loc_18002D23C
0x18002d22b  lock or [rsp+28h+var_28], 0
0x18002d230  mov     cs:byte_180046328, 1
0x18002d237  jmp     loc_18002D193
0x18002d23c  xor     eax, eax
0x18002d23e  add     rsp, 20h
0x18002d242  pop     rbx
0x18002d243  retn
```
