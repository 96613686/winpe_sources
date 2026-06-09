# GetProcAddressAll_void_(__cdecl_)(AtlThunkData_t___void___unsigned___int64)_

- ea: `0x18004f424`
- end: `0x18004f518`
- name: `GetProcAddressAll_void_(__cdecl_)(AtlThunkData_t___void___unsigned___int64)_`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18004f778`

## callees

- `0x18004f424`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18004f471`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18004f49a`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18004f4bf`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18004f4e4`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18004f471`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18004f49a`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18004f4bf`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18004f4e4`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x18004f455`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x18004f455`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18004f43f`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18004f483`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18004f4a8`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18004f4cd`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18004f4f2`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18004f483`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18004f4a8`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18004f4cd`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18004f4f2`

## string_xrefs

- `0x18004f448`: `atlthunk.dll`

## pseudocode

```c
PVOID GetProcAddressAll_void____cdecl___AtlThunkData_t___void___unsigned___int64__()
{
  HMODULE Library; // rax
  HMODULE v2; // rbx
  FARPROC ProcAddress; // rax
  FARPROC v4; // rax
  FARPROC v5; // rax
  FARPROC v6; // rax
  signed __int32 v7[10]; // [rsp+0h] [rbp-28h] BYREF

  if ( byte_180084E90 )
    return DecodePointer((PVOID)qword_180084E88);
  Library = LoadLibraryExA("atlthunk.dll", 0, 0x800u);
  v2 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "AtlThunk_AllocateData");
    if ( ProcAddress )
    {
      qword_180084E98 = (__int64)EncodePointer(ProcAddress);
      v4 = GetProcAddress(v2, "AtlThunk_InitData");
      if ( v4 )
      {
        qword_180084E88 = (__int64)EncodePointer(v4);
        v5 = GetProcAddress(v2, "AtlThunk_DataToCode");
        if ( v5 )
        {
          qword_180084E80 = (__int64)EncodePointer(v5);
          v6 = GetProcAddress(v2, "AtlThunk_FreeData");
          if ( v6 )
          {
            qword_180084E78 = (__int64)EncodePointer(v6);
            _InterlockedOr(v7, 0);
            byte_180084E90 = 1;
            return DecodePointer((PVOID)qword_180084E88);
          }
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18004f424  push    rbx
0x18004f426  sub     rsp, 20h
0x18004f42a  cmp     cs:byte_180084E90, 0
0x18004f431  jz      short loc_18004F446
0x18004f433  mov     rcx, cs:qword_180084E88
0x18004f43a  add     rsp, 20h
0x18004f43e  pop     rbx
0x18004f43f  jmp     cs:__imp_DecodePointer
0x18004f446  xor     edx, edx; hFile
0x18004f448  lea     rcx, aAtlthunkDll; "atlthunk.dll"
0x18004f44f  mov     r8d, 800h; dwFlags
0x18004f455  call    cs:__imp_LoadLibraryExA
0x18004f45b  mov     rbx, rax
0x18004f45e  test    rax, rax
0x18004f461  jz      loc_18004F510
0x18004f467  lea     rdx, aAtlthunkAlloca; "AtlThunk_AllocateData"
0x18004f46e  mov     rcx, rax; hModule
0x18004f471  call    cs:__imp_GetProcAddress
0x18004f477  test    rax, rax
0x18004f47a  jz      loc_18004F510
0x18004f480  mov     rcx, rax; Ptr
0x18004f483  call    cs:__imp_EncodePointer
0x18004f489  lea     rdx, aAtlthunkInitda; "AtlThunk_InitData"
0x18004f490  mov     rcx, rbx; hModule
0x18004f493  mov     cs:qword_180084E98, rax
0x18004f49a  call    cs:__imp_GetProcAddress
0x18004f4a0  test    rax, rax
0x18004f4a3  jz      short loc_18004F510
0x18004f4a5  mov     rcx, rax; Ptr
0x18004f4a8  call    cs:__imp_EncodePointer
0x18004f4ae  lea     rdx, aAtlthunkDatato; "AtlThunk_DataToCode"
0x18004f4b5  mov     rcx, rbx; hModule
0x18004f4b8  mov     cs:qword_180084E88, rax
0x18004f4bf  call    cs:__imp_GetProcAddress
0x18004f4c5  test    rax, rax
0x18004f4c8  jz      short loc_18004F510
0x18004f4ca  mov     rcx, rax; Ptr
0x18004f4cd  call    cs:__imp_EncodePointer
0x18004f4d3  lea     rdx, aAtlthunkFreeda; "AtlThunk_FreeData"
0x18004f4da  mov     rcx, rbx; hModule
0x18004f4dd  mov     cs:qword_180084E80, rax
0x18004f4e4  call    cs:__imp_GetProcAddress
0x18004f4ea  test    rax, rax
0x18004f4ed  jz      short loc_18004F510
0x18004f4ef  mov     rcx, rax; Ptr
0x18004f4f2  call    cs:__imp_EncodePointer
0x18004f4f8  mov     cs:qword_180084E78, rax
0x18004f4ff  lock or [rsp+28h+var_28], 0
0x18004f504  mov     cs:byte_180084E90, 1
0x18004f50b  jmp     loc_18004F433
0x18004f510  xor     eax, eax
0x18004f512  add     rsp, 20h
0x18004f516  pop     rbx
0x18004f517  retn
```
