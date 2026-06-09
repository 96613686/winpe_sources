# GetProcAddressAll_void_(__cdecl_)(AtlThunkData_t___void___unsigned___int64)_

- ea: `0x14000f268`
- end: `0x14000f35c`
- name: `GetProcAddressAll_void_(__cdecl_)(AtlThunkData_t___void___unsigned___int64)_`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14000f5bc`

## callees

- `0x14000f268`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000f2b5`
- `KERNEL32!GetProcAddress` at `0x14000f2de`
- `KERNEL32!GetProcAddress` at `0x14000f303`
- `KERNEL32!GetProcAddress` at `0x14000f328`
- `KERNEL32!GetProcAddress` at `0x14000f2b5`
- `KERNEL32!GetProcAddress` at `0x14000f2de`
- `KERNEL32!GetProcAddress` at `0x14000f303`
- `KERNEL32!GetProcAddress` at `0x14000f328`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x14000f299`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x14000f299`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x14000f2c7`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x14000f2ec`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x14000f311`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x14000f336`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x14000f2c7`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x14000f2ec`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x14000f311`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x14000f336`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x14000f283`

## string_xrefs

- `0x14000f28c`: `atlthunk.dll`

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

  if ( byte_140016868 )
    return DecodePointer((PVOID)qword_140016860);
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
            return DecodePointer((PVOID)qword_140016860);
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
0x14000f268  push    rbx
0x14000f26a  sub     rsp, 20h
0x14000f26e  cmp     cs:byte_140016868, 0
0x14000f275  jz      short loc_14000F28A
0x14000f277  mov     rcx, cs:qword_140016860
0x14000f27e  add     rsp, 20h
0x14000f282  pop     rbx
0x14000f283  jmp     cs:__imp_DecodePointer
0x14000f28a  xor     edx, edx; hFile
0x14000f28c  lea     rcx, aAtlthunkDll; "atlthunk.dll"
0x14000f293  mov     r8d, 800h; dwFlags
0x14000f299  call    cs:__imp_LoadLibraryExA
0x14000f29f  mov     rbx, rax
0x14000f2a2  test    rax, rax
0x14000f2a5  jz      loc_14000F354
0x14000f2ab  lea     rdx, aAtlthunkAlloca; "AtlThunk_AllocateData"
0x14000f2b2  mov     rcx, rax; hModule
0x14000f2b5  call    cs:__imp_GetProcAddress
0x14000f2bb  test    rax, rax
0x14000f2be  jz      loc_14000F354
0x14000f2c4  mov     rcx, rax; Ptr
0x14000f2c7  call    cs:__imp_EncodePointer
0x14000f2cd  lea     rdx, aAtlthunkInitda; "AtlThunk_InitData"
0x14000f2d4  mov     rcx, rbx; hModule
0x14000f2d7  mov     cs:qword_140016870, rax
0x14000f2de  call    cs:__imp_GetProcAddress
0x14000f2e4  test    rax, rax
0x14000f2e7  jz      short loc_14000F354
0x14000f2e9  mov     rcx, rax; Ptr
0x14000f2ec  call    cs:__imp_EncodePointer
0x14000f2f2  lea     rdx, aAtlthunkDatato; "AtlThunk_DataToCode"
0x14000f2f9  mov     rcx, rbx; hModule
0x14000f2fc  mov     cs:qword_140016860, rax
0x14000f303  call    cs:__imp_GetProcAddress
0x14000f309  test    rax, rax
0x14000f30c  jz      short loc_14000F354
0x14000f30e  mov     rcx, rax; Ptr
0x14000f311  call    cs:__imp_EncodePointer
0x14000f317  lea     rdx, aAtlthunkFreeda; "AtlThunk_FreeData"
0x14000f31e  mov     rcx, rbx; hModule
0x14000f321  mov     cs:qword_140016858, rax
0x14000f328  call    cs:__imp_GetProcAddress
0x14000f32e  test    rax, rax
0x14000f331  jz      short loc_14000F354
0x14000f333  mov     rcx, rax; Ptr
0x14000f336  call    cs:__imp_EncodePointer
0x14000f33c  mov     cs:qword_140016850, rax
0x14000f343  lock or [rsp+28h+var_28], 0
0x14000f348  mov     cs:byte_140016868, 1
0x14000f34f  jmp     loc_14000F277
0x14000f354  xor     eax, eax
0x14000f356  add     rsp, 20h
0x14000f35a  pop     rbx
0x14000f35b  retn
```
