# GetProcAddressAll_void_(__cdecl_)(AtlThunkData_t___void___unsigned___int64)_

- ea: `0x1800393f8`
- end: `0x1800394b8`
- name: `GetProcAddressAll_void_(__cdecl_)(AtlThunkData_t___void___unsigned___int64)_`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180039764`

## callees

- `0x1800393f8`
- `0x1800394c0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180039429`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180039429`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180039413`

## string_xrefs

- `0x18003941c`: `atlthunk.dll`

## pseudocode

```c
PVOID GetProcAddressAll_void____cdecl___AtlThunkData_t___void___unsigned___int64__()
{
  HMODULE Library; // rax
  HMODULE v2; // rbx
  signed __int32 v3[10]; // [rsp+0h] [rbp-28h] BYREF

  if ( byte_180050D68 )
    return DecodePointer((PVOID)qword_180050D60);
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
    return DecodePointer((PVOID)qword_180050D60);
  }
  return 0;
}

```

## disassembly

```asm
0x1800393f8  push    rbx
0x1800393fa  sub     rsp, 20h
0x1800393fe  cmp     cs:byte_180050D68, 0
0x180039405  jz      short loc_18003941A
0x180039407  mov     rcx, cs:qword_180050D60
0x18003940e  add     rsp, 20h
0x180039412  pop     rbx
0x180039413  jmp     cs:__imp_DecodePointer
0x18003941a  xor     edx, edx; hFile
0x18003941c  lea     rcx, aAtlthunkDll; "atlthunk.dll"
0x180039423  mov     r8d, 800h; dwFlags
0x180039429  call    cs:__imp_LoadLibraryExA
0x18003942f  mov     rbx, rax
0x180039432  test    rax, rax
0x180039435  jz      short loc_1800394B0
0x180039437  lea     r8, qword_180050D70
0x18003943e  mov     rcx, rax
0x180039441  lea     rdx, aAtlthunkAlloca; "AtlThunk_AllocateData"
0x180039448  call    GetProcAddressSingle
0x18003944d  test    al, al
0x18003944f  jz      short loc_1800394B0
0x180039451  lea     r8, qword_180050D60
0x180039458  mov     rcx, rbx
0x18003945b  lea     rdx, aAtlthunkInitda; "AtlThunk_InitData"
0x180039462  call    GetProcAddressSingle
0x180039467  test    al, al
0x180039469  jz      short loc_1800394B0
0x18003946b  lea     r8, qword_180050D58
0x180039472  mov     rcx, rbx
0x180039475  lea     rdx, aAtlthunkDatato; "AtlThunk_DataToCode"
0x18003947c  call    GetProcAddressSingle
0x180039481  test    al, al
0x180039483  jz      short loc_1800394B0
0x180039485  lea     r8, qword_180050D50
0x18003948c  mov     rcx, rbx
0x18003948f  lea     rdx, aAtlthunkFreeda; "AtlThunk_FreeData"
0x180039496  call    GetProcAddressSingle
0x18003949b  test    al, al
0x18003949d  jz      short loc_1800394B0
0x18003949f  lock or [rsp+28h+var_28], 0
0x1800394a4  mov     cs:byte_180050D68, 1
0x1800394ab  jmp     loc_180039407
0x1800394b0  xor     eax, eax
0x1800394b2  add     rsp, 20h
0x1800394b6  pop     rbx
0x1800394b7  retn
```
