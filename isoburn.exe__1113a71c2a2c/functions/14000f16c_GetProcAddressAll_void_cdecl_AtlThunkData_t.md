# GetProcAddressAll_void_(__cdecl_)(AtlThunkData_t__)_

- ea: `0x14000f16c`
- end: `0x14000f260`
- name: `GetProcAddressAll_void_(__cdecl_)(AtlThunkData_t__)_`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14000f55c`

## callees

- `0x14000f16c`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000f1b9`
- `KERNEL32!GetProcAddress` at `0x14000f1e2`
- `KERNEL32!GetProcAddress` at `0x14000f207`
- `KERNEL32!GetProcAddress` at `0x14000f22c`
- `KERNEL32!GetProcAddress` at `0x14000f1b9`
- `KERNEL32!GetProcAddress` at `0x14000f1e2`
- `KERNEL32!GetProcAddress` at `0x14000f207`
- `KERNEL32!GetProcAddress` at `0x14000f22c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x14000f19d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x14000f19d`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x14000f1cb`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x14000f1f0`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x14000f215`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x14000f23a`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x14000f1cb`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x14000f1f0`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x14000f215`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x14000f23a`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x14000f187`

## string_xrefs

- `0x14000f190`: `atlthunk.dll`

## pseudocode

```c
PVOID GetProcAddressAll_void____cdecl___AtlThunkData_t____()
{
  HMODULE Library; // rax
  HMODULE v2; // rbx
  FARPROC ProcAddress; // rax
  FARPROC v4; // rax
  FARPROC v5; // rax
  FARPROC v6; // rax
  signed __int32 v7[10]; // [rsp+0h] [rbp-28h] BYREF

  if ( byte_140016868 )
    return DecodePointer((PVOID)qword_140016850);
  Library = LoadLibraryExA("atlthunk.dll", 0, 0x800u);
  v2 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "AtlThunk_AllocateData");
    if ( ProcAddress )
    {
      qword_140016870 = (__int64)EncodePointer(ProcAddress);
      v4 = GetProcAddress(v2, "AtlThunk_InitData");
      if ( v4 )
      {
        qword_140016860 = (__int64)EncodePointer(v4);
        v5 = GetProcAddress(v2, "AtlThunk_DataToCode");
        if ( v5 )
        {
          qword_140016858 = (__int64)EncodePointer(v5);
          v6 = GetProcAddress(v2, "AtlThunk_FreeData");
          if ( v6 )
          {
            qword_140016850 = (__int64)EncodePointer(v6);
            _InterlockedOr(v7, 0);
            byte_140016868 = 1;
            return DecodePointer((PVOID)qword_140016850);
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
0x14000f16c  push    rbx
0x14000f16e  sub     rsp, 20h
0x14000f172  cmp     cs:byte_140016868, 0
0x14000f179  jz      short loc_14000F18E
0x14000f17b  mov     rcx, cs:qword_140016850
0x14000f182  add     rsp, 20h
0x14000f186  pop     rbx
0x14000f187  jmp     cs:__imp_DecodePointer
0x14000f18e  xor     edx, edx; hFile
0x14000f190  lea     rcx, aAtlthunkDll; "atlthunk.dll"
0x14000f197  mov     r8d, 800h; dwFlags
0x14000f19d  call    cs:__imp_LoadLibraryExA
0x14000f1a3  mov     rbx, rax
0x14000f1a6  test    rax, rax
0x14000f1a9  jz      loc_14000F258
0x14000f1af  lea     rdx, aAtlthunkAlloca; "AtlThunk_AllocateData"
0x14000f1b6  mov     rcx, rax; hModule
0x14000f1b9  call    cs:__imp_GetProcAddress
0x14000f1bf  test    rax, rax
0x14000f1c2  jz      loc_14000F258
0x14000f1c8  mov     rcx, rax; Ptr
0x14000f1cb  call    cs:__imp_EncodePointer
0x14000f1d1  lea     rdx, aAtlthunkInitda; "AtlThunk_InitData"
0x14000f1d8  mov     rcx, rbx; hModule
0x14000f1db  mov     cs:qword_140016870, rax
0x14000f1e2  call    cs:__imp_GetProcAddress
0x14000f1e8  test    rax, rax
0x14000f1eb  jz      short loc_14000F258
0x14000f1ed  mov     rcx, rax; Ptr
0x14000f1f0  call    cs:__imp_EncodePointer
0x14000f1f6  lea     rdx, aAtlthunkDatato; "AtlThunk_DataToCode"
0x14000f1fd  mov     rcx, rbx; hModule
0x14000f200  mov     cs:qword_140016860, rax
0x14000f207  call    cs:__imp_GetProcAddress
0x14000f20d  test    rax, rax
0x14000f210  jz      short loc_14000F258
0x14000f212  mov     rcx, rax; Ptr
0x14000f215  call    cs:__imp_EncodePointer
0x14000f21b  lea     rdx, aAtlthunkFreeda; "AtlThunk_FreeData"
0x14000f222  mov     rcx, rbx; hModule
0x14000f225  mov     cs:qword_140016858, rax
0x14000f22c  call    cs:__imp_GetProcAddress
0x14000f232  test    rax, rax
0x14000f235  jz      short loc_14000F258
0x14000f237  mov     rcx, rax; Ptr
0x14000f23a  call    cs:__imp_EncodePointer
0x14000f240  mov     cs:qword_140016850, rax
0x14000f247  lock or [rsp+28h+var_28], 0
0x14000f24c  mov     cs:byte_140016868, 1
0x14000f253  jmp     loc_14000F17B
0x14000f258  xor     eax, eax
0x14000f25a  add     rsp, 20h
0x14000f25e  pop     rbx
0x14000f25f  retn
```
