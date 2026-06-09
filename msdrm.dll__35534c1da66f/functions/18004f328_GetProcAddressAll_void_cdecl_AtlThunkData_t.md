# GetProcAddressAll_void_(__cdecl_)(AtlThunkData_t__)_

- ea: `0x18004f328`
- end: `0x18004f41c`
- name: `GetProcAddressAll_void_(__cdecl_)(AtlThunkData_t__)_`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18004f718`

## callees

- `0x18004f328`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18004f375`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18004f39e`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18004f3c3`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18004f3e8`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18004f375`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18004f39e`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18004f3c3`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18004f3e8`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x18004f359`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x18004f359`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18004f343`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18004f387`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18004f3ac`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18004f3d1`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18004f3f6`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18004f387`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18004f3ac`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18004f3d1`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18004f3f6`

## string_xrefs

- `0x18004f34c`: `atlthunk.dll`

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

  if ( byte_180084E90 )
    return DecodePointer((PVOID)qword_180084E78);
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
            return DecodePointer((PVOID)qword_180084E78);
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
0x18004f328  push    rbx
0x18004f32a  sub     rsp, 20h
0x18004f32e  cmp     cs:byte_180084E90, 0
0x18004f335  jz      short loc_18004F34A
0x18004f337  mov     rcx, cs:qword_180084E78
0x18004f33e  add     rsp, 20h
0x18004f342  pop     rbx
0x18004f343  jmp     cs:__imp_DecodePointer
0x18004f34a  xor     edx, edx; hFile
0x18004f34c  lea     rcx, aAtlthunkDll; "atlthunk.dll"
0x18004f353  mov     r8d, 800h; dwFlags
0x18004f359  call    cs:__imp_LoadLibraryExA
0x18004f35f  mov     rbx, rax
0x18004f362  test    rax, rax
0x18004f365  jz      loc_18004F414
0x18004f36b  lea     rdx, aAtlthunkAlloca; "AtlThunk_AllocateData"
0x18004f372  mov     rcx, rax; hModule
0x18004f375  call    cs:__imp_GetProcAddress
0x18004f37b  test    rax, rax
0x18004f37e  jz      loc_18004F414
0x18004f384  mov     rcx, rax; Ptr
0x18004f387  call    cs:__imp_EncodePointer
0x18004f38d  lea     rdx, aAtlthunkInitda; "AtlThunk_InitData"
0x18004f394  mov     rcx, rbx; hModule
0x18004f397  mov     cs:qword_180084E98, rax
0x18004f39e  call    cs:__imp_GetProcAddress
0x18004f3a4  test    rax, rax
0x18004f3a7  jz      short loc_18004F414
0x18004f3a9  mov     rcx, rax; Ptr
0x18004f3ac  call    cs:__imp_EncodePointer
0x18004f3b2  lea     rdx, aAtlthunkDatato; "AtlThunk_DataToCode"
0x18004f3b9  mov     rcx, rbx; hModule
0x18004f3bc  mov     cs:qword_180084E88, rax
0x18004f3c3  call    cs:__imp_GetProcAddress
0x18004f3c9  test    rax, rax
0x18004f3cc  jz      short loc_18004F414
0x18004f3ce  mov     rcx, rax; Ptr
0x18004f3d1  call    cs:__imp_EncodePointer
0x18004f3d7  lea     rdx, aAtlthunkFreeda; "AtlThunk_FreeData"
0x18004f3de  mov     rcx, rbx; hModule
0x18004f3e1  mov     cs:qword_180084E80, rax
0x18004f3e8  call    cs:__imp_GetProcAddress
0x18004f3ee  test    rax, rax
0x18004f3f1  jz      short loc_18004F414
0x18004f3f3  mov     rcx, rax; Ptr
0x18004f3f6  call    cs:__imp_EncodePointer
0x18004f3fc  mov     cs:qword_180084E78, rax
0x18004f403  lock or [rsp+28h+var_28], 0
0x18004f408  mov     cs:byte_180084E90, 1
0x18004f40f  jmp     loc_18004F337
0x18004f414  xor     eax, eax
0x18004f416  add     rsp, 20h
0x18004f41a  pop     rbx
0x18004f41b  retn
```
