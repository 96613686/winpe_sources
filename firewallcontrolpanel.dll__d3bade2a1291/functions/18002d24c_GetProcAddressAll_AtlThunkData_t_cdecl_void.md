# GetProcAddressAll_AtlThunkData_t___(__cdecl_)(void)_

- ea: `0x18002d24c`
- end: `0x18002d30c`
- name: `GetProcAddressAll_AtlThunkData_t___(__cdecl_)(void)_`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002d634`

## callees

- `0x18002d24c`
- `0x18002d4a4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18002d27d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18002d27d`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18002d267`

## string_xrefs

- `0x18002d270`: `atlthunk.dll`

## pseudocode

```c
PVOID GetProcAddressAll_AtlThunkData_t______cdecl___void__()
{
  HMODULE Library; // rax
  HMODULE v2; // rbx
  signed __int32 v3[10]; // [rsp+0h] [rbp-28h] BYREF

  if ( byte_180046328 )
    return DecodePointer((PVOID)qword_1800463A8);
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
    return DecodePointer((PVOID)qword_1800463A8);
  }
  return 0;
}

```

## disassembly

```asm
0x18002d24c  push    rbx
0x18002d24e  sub     rsp, 20h
0x18002d252  cmp     cs:byte_180046328, 0
0x18002d259  jz      short loc_18002D26E
0x18002d25b  mov     rcx, cs:qword_1800463A8
0x18002d262  add     rsp, 20h
0x18002d266  pop     rbx
0x18002d267  jmp     cs:__imp_DecodePointer
0x18002d26e  xor     edx, edx; hFile
0x18002d270  lea     rcx, LibFileName; "atlthunk.dll"
0x18002d277  mov     r8d, 800h; dwFlags
0x18002d27d  call    cs:__imp_LoadLibraryExA
0x18002d283  mov     rbx, rax
0x18002d286  test    rax, rax
0x18002d289  jz      short loc_18002D304
0x18002d28b  lea     r8, qword_1800463A8
0x18002d292  mov     rcx, rax
0x18002d295  lea     rdx, aAtlthunkAlloca; "AtlThunk_AllocateData"
0x18002d29c  call    GetProcAddressSingle
0x18002d2a1  test    al, al
0x18002d2a3  jz      short loc_18002D304
0x18002d2a5  lea     r8, qword_1800463A0
0x18002d2ac  mov     rcx, rbx
0x18002d2af  lea     rdx, aAtlthunkInitda; "AtlThunk_InitData"
0x18002d2b6  call    GetProcAddressSingle
0x18002d2bb  test    al, al
0x18002d2bd  jz      short loc_18002D304
0x18002d2bf  lea     r8, qword_180046398
0x18002d2c6  mov     rcx, rbx
0x18002d2c9  lea     rdx, aAtlthunkDatato; "AtlThunk_DataToCode"
0x18002d2d0  call    GetProcAddressSingle
0x18002d2d5  test    al, al
0x18002d2d7  jz      short loc_18002D304
0x18002d2d9  lea     r8, qword_180046390
0x18002d2e0  mov     rcx, rbx
0x18002d2e3  lea     rdx, aAtlthunkFreeda; "AtlThunk_FreeData"
0x18002d2ea  call    GetProcAddressSingle
0x18002d2ef  test    al, al
0x18002d2f1  jz      short loc_18002D304
0x18002d2f3  lock or [rsp+28h+var_28], 0
0x18002d2f8  mov     cs:byte_180046328, 1
0x18002d2ff  jmp     loc_18002D25B
0x18002d304  xor     eax, eax
0x18002d306  add     rsp, 20h
0x18002d30a  pop     rbx
0x18002d30b  retn
```
