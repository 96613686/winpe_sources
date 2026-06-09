# GetProcAddressAll_AtlThunkData_t___(__cdecl_)(void)_

- ea: `0x14000f070`
- end: `0x14000f164`
- name: `GetProcAddressAll_AtlThunkData_t___(__cdecl_)(void)_`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14000f4a0`

## callees

- `0x14000f070`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000f0bd`
- `KERNEL32!GetProcAddress` at `0x14000f0e6`
- `KERNEL32!GetProcAddress` at `0x14000f10b`
- `KERNEL32!GetProcAddress` at `0x14000f130`
- `KERNEL32!GetProcAddress` at `0x14000f0bd`
- `KERNEL32!GetProcAddress` at `0x14000f0e6`
- `KERNEL32!GetProcAddress` at `0x14000f10b`
- `KERNEL32!GetProcAddress` at `0x14000f130`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x14000f0a1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x14000f0a1`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x14000f0cf`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x14000f0f4`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x14000f119`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x14000f13e`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x14000f0cf`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x14000f0f4`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x14000f119`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x14000f13e`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x14000f08b`

## string_xrefs

- `0x14000f094`: `atlthunk.dll`

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

  if ( byte_140016868 )
    return DecodePointer((PVOID)qword_140016870);
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
            return DecodePointer((PVOID)qword_140016870);
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
0x14000f070  push    rbx
0x14000f072  sub     rsp, 20h
0x14000f076  cmp     cs:byte_140016868, 0
0x14000f07d  jz      short loc_14000F092
0x14000f07f  mov     rcx, cs:qword_140016870
0x14000f086  add     rsp, 20h
0x14000f08a  pop     rbx
0x14000f08b  jmp     cs:__imp_DecodePointer
0x14000f092  xor     edx, edx; hFile
0x14000f094  lea     rcx, aAtlthunkDll; "atlthunk.dll"
0x14000f09b  mov     r8d, 800h; dwFlags
0x14000f0a1  call    cs:__imp_LoadLibraryExA
0x14000f0a7  mov     rbx, rax
0x14000f0aa  test    rax, rax
0x14000f0ad  jz      loc_14000F15C
0x14000f0b3  lea     rdx, aAtlthunkAlloca; "AtlThunk_AllocateData"
0x14000f0ba  mov     rcx, rax; hModule
0x14000f0bd  call    cs:__imp_GetProcAddress
0x14000f0c3  test    rax, rax
0x14000f0c6  jz      loc_14000F15C
0x14000f0cc  mov     rcx, rax; Ptr
0x14000f0cf  call    cs:__imp_EncodePointer
0x14000f0d5  lea     rdx, aAtlthunkInitda; "AtlThunk_InitData"
0x14000f0dc  mov     rcx, rbx; hModule
0x14000f0df  mov     cs:qword_140016870, rax
0x14000f0e6  call    cs:__imp_GetProcAddress
0x14000f0ec  test    rax, rax
0x14000f0ef  jz      short loc_14000F15C
0x14000f0f1  mov     rcx, rax; Ptr
0x14000f0f4  call    cs:__imp_EncodePointer
0x14000f0fa  lea     rdx, aAtlthunkDatato; "AtlThunk_DataToCode"
0x14000f101  mov     rcx, rbx; hModule
0x14000f104  mov     cs:qword_140016860, rax
0x14000f10b  call    cs:__imp_GetProcAddress
0x14000f111  test    rax, rax
0x14000f114  jz      short loc_14000F15C
0x14000f116  mov     rcx, rax; Ptr
0x14000f119  call    cs:__imp_EncodePointer
0x14000f11f  lea     rdx, aAtlthunkFreeda; "AtlThunk_FreeData"
0x14000f126  mov     rcx, rbx; hModule
0x14000f129  mov     cs:qword_140016858, rax
0x14000f130  call    cs:__imp_GetProcAddress
0x14000f136  test    rax, rax
0x14000f139  jz      short loc_14000F15C
0x14000f13b  mov     rcx, rax; Ptr
0x14000f13e  call    cs:__imp_EncodePointer
0x14000f144  mov     cs:qword_140016850, rax
0x14000f14b  lock or [rsp+28h+var_28], 0
0x14000f150  mov     cs:byte_140016868, 1
0x14000f157  jmp     loc_14000F07F
0x14000f15c  xor     eax, eax
0x14000f15e  add     rsp, 20h
0x14000f162  pop     rbx
0x14000f163  retn
```
