# GetProcAddressAll___int64_(__cdecl_(__cdecl_)(AtlThunkData_t__))(HWND_____unsigned_int_unsigned___int64___int64)_

- ea: `0x14000ef74`
- end: `0x14000f068`
- name: `GetProcAddressAll___int64_(__cdecl_(__cdecl_)(AtlThunkData_t__))(HWND_____unsigned_int_unsigned___int64___int64)_`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14000f518`

## callees

- `0x14000ef74`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000efc1`
- `KERNEL32!GetProcAddress` at `0x14000efea`
- `KERNEL32!GetProcAddress` at `0x14000f00f`
- `KERNEL32!GetProcAddress` at `0x14000f034`
- `KERNEL32!GetProcAddress` at `0x14000efc1`
- `KERNEL32!GetProcAddress` at `0x14000efea`
- `KERNEL32!GetProcAddress` at `0x14000f00f`
- `KERNEL32!GetProcAddress` at `0x14000f034`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x14000efa5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x14000efa5`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x14000efd3`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x14000eff8`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x14000f01d`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x14000f042`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x14000efd3`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x14000eff8`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x14000f01d`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x14000f042`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x14000ef8f`

## string_xrefs

- `0x14000ef98`: `atlthunk.dll`

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

  if ( byte_140016868 )
    return DecodePointer((PVOID)qword_140016858);
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
            return DecodePointer((PVOID)qword_140016858);
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
0x14000ef74  push    rbx
0x14000ef76  sub     rsp, 20h
0x14000ef7a  cmp     cs:byte_140016868, 0
0x14000ef81  jz      short loc_14000EF96
0x14000ef83  mov     rcx, cs:qword_140016858
0x14000ef8a  add     rsp, 20h
0x14000ef8e  pop     rbx
0x14000ef8f  jmp     cs:__imp_DecodePointer
0x14000ef96  xor     edx, edx; hFile
0x14000ef98  lea     rcx, aAtlthunkDll; "atlthunk.dll"
0x14000ef9f  mov     r8d, 800h; dwFlags
0x14000efa5  call    cs:__imp_LoadLibraryExA
0x14000efab  mov     rbx, rax
0x14000efae  test    rax, rax
0x14000efb1  jz      loc_14000F060
0x14000efb7  lea     rdx, aAtlthunkAlloca; "AtlThunk_AllocateData"
0x14000efbe  mov     rcx, rax; hModule
0x14000efc1  call    cs:__imp_GetProcAddress
0x14000efc7  test    rax, rax
0x14000efca  jz      loc_14000F060
0x14000efd0  mov     rcx, rax; Ptr
0x14000efd3  call    cs:__imp_EncodePointer
0x14000efd9  lea     rdx, aAtlthunkInitda; "AtlThunk_InitData"
0x14000efe0  mov     rcx, rbx; hModule
0x14000efe3  mov     cs:qword_140016870, rax
0x14000efea  call    cs:__imp_GetProcAddress
0x14000eff0  test    rax, rax
0x14000eff3  jz      short loc_14000F060
0x14000eff5  mov     rcx, rax; Ptr
0x14000eff8  call    cs:__imp_EncodePointer
0x14000effe  lea     rdx, aAtlthunkDatato; "AtlThunk_DataToCode"
0x14000f005  mov     rcx, rbx; hModule
0x14000f008  mov     cs:qword_140016860, rax
0x14000f00f  call    cs:__imp_GetProcAddress
0x14000f015  test    rax, rax
0x14000f018  jz      short loc_14000F060
0x14000f01a  mov     rcx, rax; Ptr
0x14000f01d  call    cs:__imp_EncodePointer
0x14000f023  lea     rdx, aAtlthunkFreeda; "AtlThunk_FreeData"
0x14000f02a  mov     rcx, rbx; hModule
0x14000f02d  mov     cs:qword_140016858, rax
0x14000f034  call    cs:__imp_GetProcAddress
0x14000f03a  test    rax, rax
0x14000f03d  jz      short loc_14000F060
0x14000f03f  mov     rcx, rax; Ptr
0x14000f042  call    cs:__imp_EncodePointer
0x14000f048  mov     cs:qword_140016850, rax
0x14000f04f  lock or [rsp+28h+var_28], 0
0x14000f054  mov     cs:byte_140016868, 1
0x14000f05b  jmp     loc_14000EF83
0x14000f060  xor     eax, eax
0x14000f062  add     rsp, 20h
0x14000f066  pop     rbx
0x14000f067  retn
```
