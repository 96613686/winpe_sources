# GetProcAddressAll_void_(__cdecl_)(AtlThunkData_t__)_

- ea: `0x180039330`
- end: `0x1800393f0`
- name: `GetProcAddressAll_void_(__cdecl_)(AtlThunkData_t__)_`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18003970c`

## callees

- `0x180039330`
- `0x1800394c0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180039361`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180039361`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18003934b`

## string_xrefs

- `0x180039354`: `atlthunk.dll`

## pseudocode

```c
PVOID GetProcAddressAll_void____cdecl___AtlThunkData_t____()
{
  HMODULE Library; // rax
  HMODULE v2; // rbx
  signed __int32 v3[10]; // [rsp+0h] [rbp-28h] BYREF

  if ( byte_180050D68 )
    return DecodePointer((PVOID)qword_180050D50);
  Library = LoadLibraryExA("atlthunk.dll", 0, 0x800u);
  v2 = Library;
  if ( Library
    && (unsigned __int8)GetProcAddressSingle(Library, "AtlThunk_AllocateData", &qword_180050D70)
    && (unsigned __int8)GetProcAddressSingle(v2, "AtlThunk_InitData", &qword_180050D60)
    && (unsigned __int8)GetProcAddressSingle(v2, "AtlThunk_DataToCode", &qword_180050D58)
    && (unsigned __int8)GetProcAddressSingle(v2, "AtlThunk_FreeData", &qword_180050D50) )
  {
    _InterlockedOr(v3, 0);
    byte_180050D68 = 1;
    return DecodePointer((PVOID)qword_180050D50);
  }
  return 0;
}

```

## disassembly

```asm
0x180039330  push    rbx
0x180039332  sub     rsp, 20h
0x180039336  cmp     cs:byte_180050D68, 0
0x18003933d  jz      short loc_180039352
0x18003933f  mov     rcx, cs:qword_180050D50
0x180039346  add     rsp, 20h
0x18003934a  pop     rbx
0x18003934b  jmp     cs:__imp_DecodePointer
0x180039352  xor     edx, edx; hFile
0x180039354  lea     rcx, aAtlthunkDll; "atlthunk.dll"
0x18003935b  mov     r8d, 800h; dwFlags
0x180039361  call    cs:__imp_LoadLibraryExA
0x180039367  mov     rbx, rax
0x18003936a  test    rax, rax
0x18003936d  jz      short loc_1800393E8
0x18003936f  lea     r8, qword_180050D70
0x180039376  mov     rcx, rax
0x180039379  lea     rdx, aAtlthunkAlloca; "AtlThunk_AllocateData"
0x180039380  call    GetProcAddressSingle
0x180039385  test    al, al
0x180039387  jz      short loc_1800393E8
0x180039389  lea     r8, qword_180050D60
0x180039390  mov     rcx, rbx
0x180039393  lea     rdx, aAtlthunkInitda; "AtlThunk_InitData"
0x18003939a  call    GetProcAddressSingle
0x18003939f  test    al, al
0x1800393a1  jz      short loc_1800393E8
0x1800393a3  lea     r8, qword_180050D58
0x1800393aa  mov     rcx, rbx
0x1800393ad  lea     rdx, aAtlthunkDatato; "AtlThunk_DataToCode"
0x1800393b4  call    GetProcAddressSingle
0x1800393b9  test    al, al
0x1800393bb  jz      short loc_1800393E8
0x1800393bd  lea     r8, qword_180050D50
0x1800393c4  mov     rcx, rbx
0x1800393c7  lea     rdx, aAtlthunkFreeda; "AtlThunk_FreeData"
0x1800393ce  call    GetProcAddressSingle
0x1800393d3  test    al, al
0x1800393d5  jz      short loc_1800393E8
0x1800393d7  lock or [rsp+28h+var_28], 0
0x1800393dc  mov     cs:byte_180050D68, 1
0x1800393e3  jmp     loc_18003933F
0x1800393e8  xor     eax, eax
0x1800393ea  add     rsp, 20h
0x1800393ee  pop     rbx
0x1800393ef  retn
```
