# GetProcAddressAll_AtlThunkData_t___(__cdecl_)(void)_

- ea: `0x1800344c8`
- end: `0x180034588`
- name: `GetProcAddressAll_AtlThunkData_t___(__cdecl_)(void)_`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800348b0`

## callees

- `0x1800344c8`
- `0x180034720`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800344f9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800344f9`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800344e3`

## string_xrefs

- `0x1800344ec`: `atlthunk.dll`

## pseudocode

```c
PVOID GetProcAddressAll_AtlThunkData_t______cdecl___void__()
{
  HMODULE Library; // rax
  HMODULE v2; // rbx
  signed __int32 v3[10]; // [rsp+0h] [rbp-28h] BYREF

  if ( byte_180089D08 )
    return DecodePointer((PVOID)qword_180089D10);
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
    return DecodePointer((PVOID)qword_180089D10);
  }
  return 0;
}

```

## disassembly

```asm
0x1800344c8  push    rbx
0x1800344ca  sub     rsp, 20h
0x1800344ce  cmp     cs:byte_180089D08, 0
0x1800344d5  jz      short loc_1800344EA
0x1800344d7  mov     rcx, cs:qword_180089D10
0x1800344de  add     rsp, 20h
0x1800344e2  pop     rbx
0x1800344e3  jmp     cs:__imp_DecodePointer
0x1800344ea  xor     edx, edx; hFile
0x1800344ec  lea     rcx, aAtlthunkDll; "atlthunk.dll"
0x1800344f3  mov     r8d, 800h; dwFlags
0x1800344f9  call    cs:__imp_LoadLibraryExA
0x1800344ff  mov     rbx, rax
0x180034502  test    rax, rax
0x180034505  jz      short loc_180034580
0x180034507  lea     r8, qword_180089D10
0x18003450e  mov     rcx, rax
0x180034511  lea     rdx, aAtlthunkAlloca; "AtlThunk_AllocateData"
0x180034518  call    GetProcAddressSingle
0x18003451d  test    al, al
0x18003451f  jz      short loc_180034580
0x180034521  lea     r8, qword_180089D00
0x180034528  mov     rcx, rbx
0x18003452b  lea     rdx, aAtlthunkInitda; "AtlThunk_InitData"
0x180034532  call    GetProcAddressSingle
0x180034537  test    al, al
0x180034539  jz      short loc_180034580
0x18003453b  lea     r8, qword_180089CF8
0x180034542  mov     rcx, rbx
0x180034545  lea     rdx, aAtlthunkDatato; "AtlThunk_DataToCode"
0x18003454c  call    GetProcAddressSingle
0x180034551  test    al, al
0x180034553  jz      short loc_180034580
0x180034555  lea     r8, qword_180089CF0
0x18003455c  mov     rcx, rbx
0x18003455f  lea     rdx, aAtlthunkFreeda; "AtlThunk_FreeData"
0x180034566  call    GetProcAddressSingle
0x18003456b  test    al, al
0x18003456d  jz      short loc_180034580
0x18003456f  lock or [rsp+28h+var_28], 0
0x180034574  mov     cs:byte_180089D08, 1
0x18003457b  jmp     loc_1800344D7
0x180034580  xor     eax, eax
0x180034582  add     rsp, 20h
0x180034586  pop     rbx
0x180034587  retn
```
