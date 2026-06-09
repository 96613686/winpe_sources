# GetProcAddressAll___int64_(__cdecl_(__cdecl_)(AtlThunkData_t__))(HWND_____unsigned_int_unsigned___int64___int64)_

- ea: `0x18004f130`
- end: `0x18004f224`
- name: `GetProcAddressAll___int64_(__cdecl_(__cdecl_)(AtlThunkData_t__))(HWND_____unsigned_int_unsigned___int64___int64)_`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18004f6d4`

## callees

- `0x18004f130`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18004f17d`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18004f1a6`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18004f1cb`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18004f1f0`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18004f17d`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18004f1a6`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18004f1cb`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18004f1f0`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x18004f161`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x18004f161`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18004f14b`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18004f18f`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18004f1b4`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18004f1d9`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18004f1fe`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18004f18f`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18004f1b4`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18004f1d9`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18004f1fe`

## string_xrefs

- `0x18004f154`: `atlthunk.dll`

## pseudocode

```c
PVOID GetProcAddressAll___int64____cdecl____cdecl___AtlThunkData_t_____HWND_____unsigned_int_unsigned___int64___int64__()
{
  HMODULE Library; // rax
  HMODULE v2; // rbx
  FARPROC ProcAddress; // rax
  FARPROC v4; // rax
  FARPROC v5; // rax
  FARPROC v6; // rax
  signed __int32 v7[10]; // [rsp+0h] [rbp-28h] BYREF

  if ( byte_180084E90 )
    return DecodePointer((PVOID)qword_180084E80);
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
            return DecodePointer((PVOID)qword_180084E80);
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
0x18004f130  push    rbx
0x18004f132  sub     rsp, 20h
0x18004f136  cmp     cs:byte_180084E90, 0
0x18004f13d  jz      short loc_18004F152
0x18004f13f  mov     rcx, cs:qword_180084E80
0x18004f146  add     rsp, 20h
0x18004f14a  pop     rbx
0x18004f14b  jmp     cs:__imp_DecodePointer
0x18004f152  xor     edx, edx; hFile
0x18004f154  lea     rcx, aAtlthunkDll; "atlthunk.dll"
0x18004f15b  mov     r8d, 800h; dwFlags
0x18004f161  call    cs:__imp_LoadLibraryExA
0x18004f167  mov     rbx, rax
0x18004f16a  test    rax, rax
0x18004f16d  jz      loc_18004F21C
0x18004f173  lea     rdx, aAtlthunkAlloca; "AtlThunk_AllocateData"
0x18004f17a  mov     rcx, rax; hModule
0x18004f17d  call    cs:__imp_GetProcAddress
0x18004f183  test    rax, rax
0x18004f186  jz      loc_18004F21C
0x18004f18c  mov     rcx, rax; Ptr
0x18004f18f  call    cs:__imp_EncodePointer
0x18004f195  lea     rdx, aAtlthunkInitda; "AtlThunk_InitData"
0x18004f19c  mov     rcx, rbx; hModule
0x18004f19f  mov     cs:qword_180084E98, rax
0x18004f1a6  call    cs:__imp_GetProcAddress
0x18004f1ac  test    rax, rax
0x18004f1af  jz      short loc_18004F21C
0x18004f1b1  mov     rcx, rax; Ptr
0x18004f1b4  call    cs:__imp_EncodePointer
0x18004f1ba  lea     rdx, aAtlthunkDatato; "AtlThunk_DataToCode"
0x18004f1c1  mov     rcx, rbx; hModule
0x18004f1c4  mov     cs:qword_180084E88, rax
0x18004f1cb  call    cs:__imp_GetProcAddress
0x18004f1d1  test    rax, rax
0x18004f1d4  jz      short loc_18004F21C
0x18004f1d6  mov     rcx, rax; Ptr
0x18004f1d9  call    cs:__imp_EncodePointer
0x18004f1df  lea     rdx, aAtlthunkFreeda; "AtlThunk_FreeData"
0x18004f1e6  mov     rcx, rbx; hModule
0x18004f1e9  mov     cs:qword_180084E80, rax
0x18004f1f0  call    cs:__imp_GetProcAddress
0x18004f1f6  test    rax, rax
0x18004f1f9  jz      short loc_18004F21C
0x18004f1fb  mov     rcx, rax; Ptr
0x18004f1fe  call    cs:__imp_EncodePointer
0x18004f204  mov     cs:qword_180084E78, rax
0x18004f20b  lock or [rsp+28h+var_28], 0
0x18004f210  mov     cs:byte_180084E90, 1
0x18004f217  jmp     loc_18004F13F
0x18004f21c  xor     eax, eax
0x18004f21e  add     rsp, 20h
0x18004f222  pop     rbx
0x18004f223  retn
```
