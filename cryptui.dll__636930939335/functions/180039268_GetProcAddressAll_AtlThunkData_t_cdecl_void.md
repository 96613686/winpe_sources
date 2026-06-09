# GetProcAddressAll_AtlThunkData_t___(__cdecl_)(void)_

- ea: `0x180039268`
- end: `0x180039328`
- name: `GetProcAddressAll_AtlThunkData_t___(__cdecl_)(void)_`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180039650`

## callees

- `0x180039268`
- `0x1800394c0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180039299`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180039299`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180039283`

## string_xrefs

- `0x18003928c`: `atlthunk.dll`

## pseudocode

```c
PVOID GetProcAddressAll_AtlThunkData_t______cdecl___void__()
{
  HMODULE Library; // rax
  HMODULE v2; // rbx
  signed __int32 v3[10]; // [rsp+0h] [rbp-28h] BYREF

  if ( byte_180050D68 )
    return DecodePointer((PVOID)qword_180050D70);
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
    return DecodePointer((PVOID)qword_180050D70);
  }
  return 0;
}

```

## disassembly

```asm
0x180039268  push    rbx
0x18003926a  sub     rsp, 20h
0x18003926e  cmp     cs:byte_180050D68, 0
0x180039275  jz      short loc_18003928A
0x180039277  mov     rcx, cs:qword_180050D70
0x18003927e  add     rsp, 20h
0x180039282  pop     rbx
0x180039283  jmp     cs:__imp_DecodePointer
0x18003928a  xor     edx, edx; hFile
0x18003928c  lea     rcx, aAtlthunkDll; "atlthunk.dll"
0x180039293  mov     r8d, 800h; dwFlags
0x180039299  call    cs:__imp_LoadLibraryExA
0x18003929f  mov     rbx, rax
0x1800392a2  test    rax, rax
0x1800392a5  jz      short loc_180039320
0x1800392a7  lea     r8, qword_180050D70
0x1800392ae  mov     rcx, rax
0x1800392b1  lea     rdx, aAtlthunkAlloca; "AtlThunk_AllocateData"
0x1800392b8  call    GetProcAddressSingle
0x1800392bd  test    al, al
0x1800392bf  jz      short loc_180039320
0x1800392c1  lea     r8, qword_180050D60
0x1800392c8  mov     rcx, rbx
0x1800392cb  lea     rdx, aAtlthunkInitda; "AtlThunk_InitData"
0x1800392d2  call    GetProcAddressSingle
0x1800392d7  test    al, al
0x1800392d9  jz      short loc_180039320
0x1800392db  lea     r8, qword_180050D58
0x1800392e2  mov     rcx, rbx
0x1800392e5  lea     rdx, aAtlthunkDatato; "AtlThunk_DataToCode"
0x1800392ec  call    GetProcAddressSingle
0x1800392f1  test    al, al
0x1800392f3  jz      short loc_180039320
0x1800392f5  lea     r8, qword_180050D50
0x1800392fc  mov     rcx, rbx
0x1800392ff  lea     rdx, aAtlthunkFreeda; "AtlThunk_FreeData"
0x180039306  call    GetProcAddressSingle
0x18003930b  test    al, al
0x18003930d  jz      short loc_180039320
0x18003930f  lock or [rsp+28h+var_28], 0
0x180039314  mov     cs:byte_180050D68, 1
0x18003931b  jmp     loc_180039277
0x180039320  xor     eax, eax
0x180039322  add     rsp, 20h
0x180039326  pop     rbx
0x180039327  retn
```
