# GetProcAddressAll___int64_(__cdecl_(__cdecl_)(AtlThunkData_t__))(HWND_____unsigned_int_unsigned___int64___int64)_

- ea: `0x180034400`
- end: `0x1800344c0`
- name: `GetProcAddressAll___int64_(__cdecl_(__cdecl_)(AtlThunkData_t__))(HWND_____unsigned_int_unsigned___int64___int64)_`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180034928`

## callees

- `0x180034400`
- `0x180034720`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180034431`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180034431`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18003441b`

## string_xrefs

- `0x180034424`: `atlthunk.dll`

## pseudocode

```c
PVOID GetProcAddressAll___int64____cdecl____cdecl___AtlThunkData_t_____HWND_____unsigned_int_unsigned___int64___int64__()
{
  HMODULE Library; // rax
  HMODULE v2; // rbx
  signed __int32 v3[10]; // [rsp+0h] [rbp-28h] BYREF

  if ( byte_180089D08 )
    return DecodePointer((PVOID)qword_180089CF8);
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
    return DecodePointer((PVOID)qword_180089CF8);
  }
  return 0;
}

```

## disassembly

```asm
0x180034400  push    rbx
0x180034402  sub     rsp, 20h
0x180034406  cmp     cs:byte_180089D08, 0
0x18003440d  jz      short loc_180034422
0x18003440f  mov     rcx, cs:qword_180089CF8
0x180034416  add     rsp, 20h
0x18003441a  pop     rbx
0x18003441b  jmp     cs:__imp_DecodePointer
0x180034422  xor     edx, edx; hFile
0x180034424  lea     rcx, aAtlthunkDll; "atlthunk.dll"
0x18003442b  mov     r8d, 800h; dwFlags
0x180034431  call    cs:__imp_LoadLibraryExA
0x180034437  mov     rbx, rax
0x18003443a  test    rax, rax
0x18003443d  jz      short loc_1800344B8
0x18003443f  lea     r8, qword_180089D10
0x180034446  mov     rcx, rax
0x180034449  lea     rdx, aAtlthunkAlloca; "AtlThunk_AllocateData"
0x180034450  call    GetProcAddressSingle
0x180034455  test    al, al
0x180034457  jz      short loc_1800344B8
0x180034459  lea     r8, qword_180089D00
0x180034460  mov     rcx, rbx
0x180034463  lea     rdx, aAtlthunkInitda; "AtlThunk_InitData"
0x18003446a  call    GetProcAddressSingle
0x18003446f  test    al, al
0x180034471  jz      short loc_1800344B8
0x180034473  lea     r8, qword_180089CF8
0x18003447a  mov     rcx, rbx
0x18003447d  lea     rdx, aAtlthunkDatato; "AtlThunk_DataToCode"
0x180034484  call    GetProcAddressSingle
0x180034489  test    al, al
0x18003448b  jz      short loc_1800344B8
0x18003448d  lea     r8, qword_180089CF0
0x180034494  mov     rcx, rbx
0x180034497  lea     rdx, aAtlthunkFreeda; "AtlThunk_FreeData"
0x18003449e  call    GetProcAddressSingle
0x1800344a3  test    al, al
0x1800344a5  jz      short loc_1800344B8
0x1800344a7  lock or [rsp+28h+var_28], 0
0x1800344ac  mov     cs:byte_180089D08, 1
0x1800344b3  jmp     loc_18003440F
0x1800344b8  xor     eax, eax
0x1800344ba  add     rsp, 20h
0x1800344be  pop     rbx
0x1800344bf  retn
```
