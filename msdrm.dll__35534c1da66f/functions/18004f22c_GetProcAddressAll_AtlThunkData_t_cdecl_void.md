# GetProcAddressAll_AtlThunkData_t___(__cdecl_)(void)_

- ea: `0x18004f22c`
- end: `0x18004f320`
- name: `GetProcAddressAll_AtlThunkData_t___(__cdecl_)(void)_`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18004f65c`

## callees

- `0x18004f22c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18004f279`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18004f2a2`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18004f2c7`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18004f2ec`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18004f279`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18004f2a2`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18004f2c7`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18004f2ec`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x18004f25d`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x18004f25d`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18004f247`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18004f28b`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18004f2b0`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18004f2d5`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18004f2fa`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18004f28b`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18004f2b0`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18004f2d5`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18004f2fa`

## string_xrefs

- `0x18004f250`: `atlthunk.dll`

## pseudocode

```c
PVOID GetProcAddressAll_AtlThunkData_t______cdecl___void__()
{
  HMODULE Library; // rax
  HMODULE v2; // rbx
  FARPROC ProcAddress; // rax
  FARPROC v4; // rax
  FARPROC v5; // rax
  FARPROC v6; // rax
  signed __int32 v7[10]; // [rsp+0h] [rbp-28h] BYREF

  if ( byte_180084E90 )
    return DecodePointer((PVOID)qword_180084E98);
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
            return DecodePointer((PVOID)qword_180084E98);
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
0x18004f22c  push    rbx
0x18004f22e  sub     rsp, 20h
0x18004f232  cmp     cs:byte_180084E90, 0
0x18004f239  jz      short loc_18004F24E
0x18004f23b  mov     rcx, cs:qword_180084E98
0x18004f242  add     rsp, 20h
0x18004f246  pop     rbx
0x18004f247  jmp     cs:__imp_DecodePointer
0x18004f24e  xor     edx, edx; hFile
0x18004f250  lea     rcx, aAtlthunkDll; "atlthunk.dll"
0x18004f257  mov     r8d, 800h; dwFlags
0x18004f25d  call    cs:__imp_LoadLibraryExA
0x18004f263  mov     rbx, rax
0x18004f266  test    rax, rax
0x18004f269  jz      loc_18004F318
0x18004f26f  lea     rdx, aAtlthunkAlloca; "AtlThunk_AllocateData"
0x18004f276  mov     rcx, rax; hModule
0x18004f279  call    cs:__imp_GetProcAddress
0x18004f27f  test    rax, rax
0x18004f282  jz      loc_18004F318
0x18004f288  mov     rcx, rax; Ptr
0x18004f28b  call    cs:__imp_EncodePointer
0x18004f291  lea     rdx, aAtlthunkInitda; "AtlThunk_InitData"
0x18004f298  mov     rcx, rbx; hModule
0x18004f29b  mov     cs:qword_180084E98, rax
0x18004f2a2  call    cs:__imp_GetProcAddress
0x18004f2a8  test    rax, rax
0x18004f2ab  jz      short loc_18004F318
0x18004f2ad  mov     rcx, rax; Ptr
0x18004f2b0  call    cs:__imp_EncodePointer
0x18004f2b6  lea     rdx, aAtlthunkDatato; "AtlThunk_DataToCode"
0x18004f2bd  mov     rcx, rbx; hModule
0x18004f2c0  mov     cs:qword_180084E88, rax
0x18004f2c7  call    cs:__imp_GetProcAddress
0x18004f2cd  test    rax, rax
0x18004f2d0  jz      short loc_18004F318
0x18004f2d2  mov     rcx, rax; Ptr
0x18004f2d5  call    cs:__imp_EncodePointer
0x18004f2db  lea     rdx, aAtlthunkFreeda; "AtlThunk_FreeData"
0x18004f2e2  mov     rcx, rbx; hModule
0x18004f2e5  mov     cs:qword_180084E80, rax
0x18004f2ec  call    cs:__imp_GetProcAddress
0x18004f2f2  test    rax, rax
0x18004f2f5  jz      short loc_18004F318
0x18004f2f7  mov     rcx, rax; Ptr
0x18004f2fa  call    cs:__imp_EncodePointer
0x18004f300  mov     cs:qword_180084E78, rax
0x18004f307  lock or [rsp+28h+var_28], 0
0x18004f30c  mov     cs:byte_180084E90, 1
0x18004f313  jmp     loc_18004F23B
0x18004f318  xor     eax, eax
0x18004f31a  add     rsp, 20h
0x18004f31e  pop     rbx
0x18004f31f  retn
```
