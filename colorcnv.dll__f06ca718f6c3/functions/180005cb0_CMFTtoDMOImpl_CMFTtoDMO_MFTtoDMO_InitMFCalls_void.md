# CMFTtoDMOImpl<CMFTtoDMO>::MFTtoDMO_InitMFCalls(void)

- ea: `0x180005cb0`
- end: `0x180005d4f`
- name: `?MFTtoDMO_InitMFCalls@?$CMFTtoDMOImpl@VCMFTtoDMO@@@@AEAAJXZ`
- size: `159`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005300`
- `0x180005480`
- `0x1800056a0`
- `0x180005ba0`
- `0x18000d890`
- `0x18000da60`

## callees

- `0x180005cb0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005cf8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005d12`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005cf8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005d12`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180005d32`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180005d32`

## string_xrefs

- `0x180005cee`: `MFCreateMediaTypeFromRepresentation`
- `0x180005d0b`: `MFCreateLegacyMediaBufferOnMFMediaBuffer`
- `0x180005d25`: `MFPLAT.DLL`

## pseudocode

```c
__int64 __fastcall CMFTtoDMOImpl<CMFTtoDMO>::MFTtoDMO_InitMFCalls(__int64 a1)
{
  unsigned int v1; // ebx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  FARPROC v6; // rax

  v1 = 0;
  if ( *(_QWORD *)(a1 + 16) )
    return v1;
  Library = *(HMODULE *)(a1 + 8);
  if ( Library == (HMODULE)-1LL )
    return (unsigned int)-2147467259;
  if ( !Library && (Library = LoadLibraryExA("MFPLAT.DLL", 0, 0x800u), (*(_QWORD *)(a1 + 8) = Library) == 0)
    || (ProcAddress = GetProcAddress(Library, "MFCreateMediaTypeFromRepresentation"),
        (*(_QWORD *)(a1 + 16) = ProcAddress) == 0)
    || (v6 = GetProcAddress(*(HMODULE *)(a1 + 8), "MFCreateLegacyMediaBufferOnMFMediaBuffer"),
        (*(_QWORD *)(a1 + 24) = v6) == 0) )
  {
    *(_QWORD *)(a1 + 8) = -1;
    return (unsigned int)-2147467259;
  }
  return v1;
}

```

## disassembly

```asm
0x180005cb0  mov     [rsp+arg_0], rbx
0x180005cb5  mov     [rsp+arg_8], rsi
0x180005cba  push    rdi
0x180005cbb  sub     rsp, 20h
0x180005cbf  xor     ebx, ebx
0x180005cc1  mov     rdi, rcx
0x180005cc4  cmp     [rcx+10h], rbx
0x180005cc8  jz      short loc_180005CDC
0x180005cca  mov     rsi, [rsp+28h+arg_8]
0x180005ccf  mov     eax, ebx
0x180005cd1  mov     rbx, [rsp+28h+arg_0]
0x180005cd6  add     rsp, 20h
0x180005cda  pop     rdi
0x180005cdb  retn
0x180005cdc  mov     rax, [rcx+8]
0x180005ce0  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180005ce4  cmp     rax, rsi
0x180005ce7  jz      short loc_180005D45
0x180005ce9  test    rax, rax
0x180005cec  jz      short loc_180005D23
0x180005cee  lea     rdx, ProcName; "MFCreateMediaTypeFromRepresentation"
0x180005cf5  mov     rcx, rax; hModule
0x180005cf8  call    cs:__imp_GetProcAddress
0x180005cfe  mov     [rdi+10h], rax
0x180005d02  test    rax, rax
0x180005d05  jz      short loc_180005D41
0x180005d07  mov     rcx, [rdi+8]; hModule
0x180005d0b  lea     rdx, aMfcreatelegacy; "MFCreateLegacyMediaBufferOnMFMediaBuffe"...
0x180005d12  call    cs:__imp_GetProcAddress
0x180005d18  mov     [rdi+18h], rax
0x180005d1c  test    rax, rax
0x180005d1f  jnz     short loc_180005CCA
0x180005d21  jmp     short loc_180005D41
0x180005d23  xor     edx, edx; hFile
0x180005d25  lea     rcx, LibFileName; "MFPLAT.DLL"
0x180005d2c  mov     r8d, 800h; dwFlags
0x180005d32  call    cs:__imp_LoadLibraryExA
0x180005d38  mov     [rdi+8], rax
0x180005d3c  test    rax, rax
0x180005d3f  jnz     short loc_180005CEE
0x180005d41  mov     [rdi+8], rsi
0x180005d45  mov     ebx, 80004005h
0x180005d4a  jmp     loc_180005CCA
```
