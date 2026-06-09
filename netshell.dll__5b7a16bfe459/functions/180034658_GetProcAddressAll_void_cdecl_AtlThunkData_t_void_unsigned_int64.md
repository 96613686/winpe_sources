# GetProcAddressAll_void_(__cdecl_)(AtlThunkData_t___void___unsigned___int64)_

- ea: `0x180034658`
- end: `0x180034718`
- name: `GetProcAddressAll_void_(__cdecl_)(AtlThunkData_t___void___unsigned___int64)_`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800349c4`

## callees

- `0x180034658`
- `0x180034720`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180034689`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180034689`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180034673`

## string_xrefs

- `0x18003467c`: `atlthunk.dll`

## pseudocode

```c
PVOID GetProcAddressAll_void____cdecl___AtlThunkData_t___void___unsigned___int64__()
{
  HMODULE Library; // rax
  HMODULE v2; // rbx
  signed __int32 v3[10]; // [rsp+0h] [rbp-28h] BYREF

  if ( byte_180089D08 )
    return DecodePointer((PVOID)qword_180089D00);
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
    return DecodePointer((PVOID)qword_180089D00);
  }
  return 0;
}

```

## disassembly

```asm
0x180034658  push    rbx
0x18003465a  sub     rsp, 20h
0x18003465e  cmp     cs:byte_180089D08, 0
0x180034665  jz      short loc_18003467A
0x180034667  mov     rcx, cs:qword_180089D00
0x18003466e  add     rsp, 20h
0x180034672  pop     rbx
0x180034673  jmp     cs:__imp_DecodePointer
0x18003467a  xor     edx, edx; hFile
0x18003467c  lea     rcx, aAtlthunkDll; "atlthunk.dll"
0x180034683  mov     r8d, 800h; dwFlags
0x180034689  call    cs:__imp_LoadLibraryExA
0x18003468f  mov     rbx, rax
0x180034692  test    rax, rax
0x180034695  jz      short loc_180034710
0x180034697  lea     r8, qword_180089D10
0x18003469e  mov     rcx, rax
0x1800346a1  lea     rdx, aAtlthunkAlloca; "AtlThunk_AllocateData"
0x1800346a8  call    GetProcAddressSingle
0x1800346ad  test    al, al
0x1800346af  jz      short loc_180034710
0x1800346b1  lea     r8, qword_180089D00
0x1800346b8  mov     rcx, rbx
0x1800346bb  lea     rdx, aAtlthunkInitda; "AtlThunk_InitData"
0x1800346c2  call    GetProcAddressSingle
0x1800346c7  test    al, al
0x1800346c9  jz      short loc_180034710
0x1800346cb  lea     r8, qword_180089CF8
0x1800346d2  mov     rcx, rbx
0x1800346d5  lea     rdx, aAtlthunkDatato; "AtlThunk_DataToCode"
0x1800346dc  call    GetProcAddressSingle
0x1800346e1  test    al, al
0x1800346e3  jz      short loc_180034710
0x1800346e5  lea     r8, qword_180089CF0
0x1800346ec  mov     rcx, rbx
0x1800346ef  lea     rdx, aAtlthunkFreeda; "AtlThunk_FreeData"
0x1800346f6  call    GetProcAddressSingle
0x1800346fb  test    al, al
0x1800346fd  jz      short loc_180034710
0x1800346ff  lock or [rsp+28h+var_28], 0
0x180034704  mov     cs:byte_180089D08, 1
0x18003470b  jmp     loc_180034667
0x180034710  xor     eax, eax
0x180034712  add     rsp, 20h
0x180034716  pop     rbx
0x180034717  retn
```
