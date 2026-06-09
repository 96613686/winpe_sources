# GetProcAddressAll_void_(__cdecl_)(AtlThunkData_t__)_

- ea: `0x180034590`
- end: `0x180034650`
- name: `GetProcAddressAll_void_(__cdecl_)(AtlThunkData_t__)_`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18003496c`

## callees

- `0x180034590`
- `0x180034720`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800345c1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800345c1`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800345ab`

## string_xrefs

- `0x1800345b4`: `atlthunk.dll`

## pseudocode

```c
PVOID GetProcAddressAll_void____cdecl___AtlThunkData_t____()
{
  HMODULE Library; // rax
  HMODULE v2; // rbx
  signed __int32 v3[10]; // [rsp+0h] [rbp-28h] BYREF

  if ( byte_180089D08 )
    return DecodePointer((PVOID)qword_180089CF0);
  Library = LoadLibraryExA("atlthunk.dll", 0, 0x800u);
  v2 = Library;
  if ( Library
    && (unsigned __int8)GetProcAddressSingle(Library, "AtlThunk_AllocateData", &qword_180089D10)
    && (unsigned __int8)GetProcAddressSingle(v2, "AtlThunk_InitData", &qword_180089D00)
    && (unsigned __int8)GetProcAddressSingle(v2, "AtlThunk_DataToCode", &qword_180089CF8)
    && (unsigned __int8)GetProcAddressSingle(v2, "AtlThunk_FreeData", &qword_180089CF0) )
  {
    _InterlockedOr(v3, 0);
    byte_180089D08 = 1;
    return DecodePointer((PVOID)qword_180089CF0);
  }
  return 0;
}

```

## disassembly

```asm
0x180034590  push    rbx
0x180034592  sub     rsp, 20h
0x180034596  cmp     cs:byte_180089D08, 0
0x18003459d  jz      short loc_1800345B2
0x18003459f  mov     rcx, cs:qword_180089CF0
0x1800345a6  add     rsp, 20h
0x1800345aa  pop     rbx
0x1800345ab  jmp     cs:__imp_DecodePointer
0x1800345b2  xor     edx, edx; hFile
0x1800345b4  lea     rcx, aAtlthunkDll; "atlthunk.dll"
0x1800345bb  mov     r8d, 800h; dwFlags
0x1800345c1  call    cs:__imp_LoadLibraryExA
0x1800345c7  mov     rbx, rax
0x1800345ca  test    rax, rax
0x1800345cd  jz      short loc_180034648
0x1800345cf  lea     r8, qword_180089D10
0x1800345d6  mov     rcx, rax
0x1800345d9  lea     rdx, aAtlthunkAlloca; "AtlThunk_AllocateData"
0x1800345e0  call    GetProcAddressSingle
0x1800345e5  test    al, al
0x1800345e7  jz      short loc_180034648
0x1800345e9  lea     r8, qword_180089D00
0x1800345f0  mov     rcx, rbx
0x1800345f3  lea     rdx, aAtlthunkInitda; "AtlThunk_InitData"
0x1800345fa  call    GetProcAddressSingle
0x1800345ff  test    al, al
0x180034601  jz      short loc_180034648
0x180034603  lea     r8, qword_180089CF8
0x18003460a  mov     rcx, rbx
0x18003460d  lea     rdx, aAtlthunkDatato; "AtlThunk_DataToCode"
0x180034614  call    GetProcAddressSingle
0x180034619  test    al, al
0x18003461b  jz      short loc_180034648
0x18003461d  lea     r8, qword_180089CF0
0x180034624  mov     rcx, rbx
0x180034627  lea     rdx, aAtlthunkFreeda; "AtlThunk_FreeData"
0x18003462e  call    GetProcAddressSingle
0x180034633  test    al, al
0x180034635  jz      short loc_180034648
0x180034637  lock or [rsp+28h+var_28], 0
0x18003463c  mov     cs:byte_180089D08, 1
0x180034643  jmp     loc_18003459F
0x180034648  xor     eax, eax
0x18003464a  add     rsp, 20h
0x18003464e  pop     rbx
0x18003464f  retn
```
