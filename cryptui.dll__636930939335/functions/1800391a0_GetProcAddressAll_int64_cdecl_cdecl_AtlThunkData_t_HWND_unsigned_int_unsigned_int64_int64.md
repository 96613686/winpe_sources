# GetProcAddressAll___int64_(__cdecl_(__cdecl_)(AtlThunkData_t__))(HWND_____unsigned_int_unsigned___int64___int64)_

- ea: `0x1800391a0`
- end: `0x180039260`
- name: `GetProcAddressAll___int64_(__cdecl_(__cdecl_)(AtlThunkData_t__))(HWND_____unsigned_int_unsigned___int64___int64)_`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800396c8`

## callees

- `0x1800391a0`
- `0x1800394c0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800391d1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800391d1`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800391bb`

## string_xrefs

- `0x1800391c4`: `atlthunk.dll`

## pseudocode

```c
PVOID GetProcAddressAll___int64____cdecl____cdecl___AtlThunkData_t_____HWND_____unsigned_int_unsigned___int64___int64__()
{
  HMODULE Library; // rax
  HMODULE v2; // rbx
  signed __int32 v3[10]; // [rsp+0h] [rbp-28h] BYREF

  if ( byte_180050D68 )
    return DecodePointer((PVOID)qword_180050D58);
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
    return DecodePointer((PVOID)qword_180050D58);
  }
  return 0;
}

```

## disassembly

```asm
0x1800391a0  push    rbx
0x1800391a2  sub     rsp, 20h
0x1800391a6  cmp     cs:byte_180050D68, 0
0x1800391ad  jz      short loc_1800391C2
0x1800391af  mov     rcx, cs:qword_180050D58
0x1800391b6  add     rsp, 20h
0x1800391ba  pop     rbx
0x1800391bb  jmp     cs:__imp_DecodePointer
0x1800391c2  xor     edx, edx; hFile
0x1800391c4  lea     rcx, aAtlthunkDll; "atlthunk.dll"
0x1800391cb  mov     r8d, 800h; dwFlags
0x1800391d1  call    cs:__imp_LoadLibraryExA
0x1800391d7  mov     rbx, rax
0x1800391da  test    rax, rax
0x1800391dd  jz      short loc_180039258
0x1800391df  lea     r8, qword_180050D70
0x1800391e6  mov     rcx, rax
0x1800391e9  lea     rdx, aAtlthunkAlloca; "AtlThunk_AllocateData"
0x1800391f0  call    GetProcAddressSingle
0x1800391f5  test    al, al
0x1800391f7  jz      short loc_180039258
0x1800391f9  lea     r8, qword_180050D60
0x180039200  mov     rcx, rbx
0x180039203  lea     rdx, aAtlthunkInitda; "AtlThunk_InitData"
0x18003920a  call    GetProcAddressSingle
0x18003920f  test    al, al
0x180039211  jz      short loc_180039258
0x180039213  lea     r8, qword_180050D58
0x18003921a  mov     rcx, rbx
0x18003921d  lea     rdx, aAtlthunkDatato; "AtlThunk_DataToCode"
0x180039224  call    GetProcAddressSingle
0x180039229  test    al, al
0x18003922b  jz      short loc_180039258
0x18003922d  lea     r8, qword_180050D50
0x180039234  mov     rcx, rbx
0x180039237  lea     rdx, aAtlthunkFreeda; "AtlThunk_FreeData"
0x18003923e  call    GetProcAddressSingle
0x180039243  test    al, al
0x180039245  jz      short loc_180039258
0x180039247  lock or [rsp+28h+var_28], 0
0x18003924c  mov     cs:byte_180050D68, 1
0x180039253  jmp     loc_1800391AF
0x180039258  xor     eax, eax
0x18003925a  add     rsp, 20h
0x18003925e  pop     rbx
0x18003925f  retn
```
