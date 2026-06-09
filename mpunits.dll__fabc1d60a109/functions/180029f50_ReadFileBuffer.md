# ReadFileBuffer

- ea: `0x180029f50`
- end: `0x18002a15a`
- name: `ReadFileBuffer`
- size: `522`
- prototype: `__int64 __fastcall(MI_Instance **extendedError, wchar_t *FileName)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x180029cc4`

## callees

- `0x180006e64`
- `0x180029f50`
- `0x180042c5c`

## import_xrefs

- `msvcrt!fread` at `0x18002a0ae`
- `msvcrt!fread` at `0x18002a0ae`
- `msvcrt!_wfopen` at `0x180029f75`
- `msvcrt!_wfopen` at `0x180029f75`
- `msvcrt!fseek` at `0x180029fe4`
- `msvcrt!fseek` at `0x18002a080`
- `msvcrt!fseek` at `0x180029fe4`
- `msvcrt!fseek` at `0x18002a080`
- `msvcrt!fclose` at `0x18002a12f`
- `msvcrt!fclose` at `0x18002a143`
- `msvcrt!fclose` at `0x18002a12f`
- `msvcrt!fclose` at `0x18002a143`
- `msvcrt!ferror` at `0x18002a0c1`
- `msvcrt!ferror` at `0x18002a0c1`
- `msvcrt!ftell` at `0x18002a04e`
- `msvcrt!ftell` at `0x18002a04e`
- `msvcrt!malloc` at `0x18002a092`
- `msvcrt!malloc` at `0x18002a092`
- `msvcrt!_errno` at `0x18002a05c`
- `msvcrt!_errno` at `0x18002a05c`
- `msvcrt!free` at `0x18002a126`
- `msvcrt!free` at `0x18002a126`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180029f8a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180029ff5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18002a0d2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180029f8a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180029ff5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18002a0d2`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180029fcd`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002a03b`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002a118`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180029fcd`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002a03b`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002a118`

## string_xrefs

- `0x180029f83`: `mpunits.dll`
- `0x180029fee`: `mpunits.dll`
- `0x18002a0cb`: `mpunits.dll`
- `0x180029fbb`: `BinaryLogReader`
- `0x18002a020`: `BinaryLogReader`
- `0x18002a0fd`: `BinaryLogReader`

## pseudocode

```c
__int64 __fastcall ReadFileBuffer(MI_Instance **extendedError, wchar_t *FileName, _QWORD *a3, _DWORD *a4)
{
  FILE *v8; // rax
  FILE *v9; // rdi
  HMODULE ModuleHandleA; // rax
  void *v11; // rbx
  HMODULE v13; // rax
  void *v14; // rbx
  unsigned int v15; // ebx
  int v16; // eax
  size_t v17; // rbx
  _BYTE *v18; // rax
  _BYTE *v19; // rsi
  int v20; // ebx
  HMODULE v21; // rax
  void *v22; // rbx

  v8 = _wfopen(FileName, L"rb");
  v9 = v8;
  if ( !v8 )
  {
    ModuleHandleA = GetModuleHandleA("mpunits.dll");
    v11 = (void *)Intlstr_FormatString_FormatMessage(ModuleHandleA, 2021, FileName);
    CreateOMIError_shared((int)v11, 100, (int)L"BinaryLogReader", 1, (__int64)&OMI_Error_rtti, extendedError);
    LocalFree(v11);
    return 4;
  }
  if ( fseek(v8, 0, 2) )
    goto LABEL_4;
  v16 = ftell(v9);
  v17 = v16;
  if ( v16 == -1 )
  {
    if ( *_errno() )
      goto LABEL_4;
    goto LABEL_9;
  }
  if ( fseek(v9, 0, 0) )
  {
LABEL_4:
    v13 = GetModuleHandleA("mpunits.dll");
    v14 = (void *)Intlstr_FormatString_FormatMessage(v13, 2022, FileName);
    CreateOMIError_shared((int)v14, 100, (int)L"BinaryLogReader", 6, (__int64)&OMI_Error_rtti, extendedError);
    LocalFree(v14);
    v15 = 4;
LABEL_14:
    fclose(v9);
    return v15;
  }
  v18 = malloc(v17 + 1);
  v19 = v18;
  if ( !v18 )
  {
LABEL_9:
    v15 = 27;
    goto LABEL_14;
  }
  v20 = fread(v18, 1u, v17, v9);
  v19[v20] = 0;
  if ( ferror(v9) )
  {
    v21 = GetModuleHandleA("mpunits.dll");
    v22 = (void *)Intlstr_FormatString_FormatMessage(v21, 2022, FileName);
    CreateOMIError_shared((int)v22, 100, (int)L"BinaryLogReader", 6, (__int64)&OMI_Error_rtti, extendedError);
    LocalFree(v22);
    v15 = 4;
    free(v19);
    goto LABEL_14;
  }
  *a3 = v19;
  *a4 = v20;
  fclose(v9);
  return 0;
}

```

## disassembly

```asm
0x180029f50  push    rbx
0x180029f52  push    rbp
0x180029f53  push    rsi
0x180029f54  push    rdi
0x180029f55  push    r12
0x180029f57  push    r14
0x180029f59  push    r15
0x180029f5b  sub     rsp, 30h
0x180029f5f  mov     rbp, rdx
0x180029f62  mov     r14, rcx
0x180029f65  mov     rcx, rbp; FileName
0x180029f68  lea     rdx, aRb; "rb"
0x180029f6f  mov     r15, r9
0x180029f72  mov     r12, r8
0x180029f75  call    cs:__imp__wfopen
0x180029f7b  mov     rdi, rax
0x180029f7e  test    rax, rax
0x180029f81  jnz     short loc_180029FDB
0x180029f83  lea     rcx, ModuleName; "mpunits.dll"
0x180029f8a  call    cs:__imp_GetModuleHandleA
0x180029f90  mov     r8, rbp
0x180029f93  mov     edx, 7E5h
0x180029f98  mov     rcx, rax
0x180029f9b  call    _Intlstr_FormatString_FormatMessage
0x180029fa0  mov     rbx, rax
0x180029fa3  mov     [rsp+68h+extendedError], r14; extendedError
0x180029fa8  lea     rax, OMI_Error_rtti
0x180029faf  mov     rcx, rbx; int
0x180029fb2  lea     r9d, [rdi+1]; int
0x180029fb6  mov     [rsp+68h+var_48], rax; __int64
0x180029fbb  lea     r8, aBinarylogreade_1; "BinaryLogReader"
0x180029fc2  lea     edx, [rdi+64h]; int
0x180029fc5  call    CreateOMIError_shared
0x180029fca  mov     rcx, rbx; hMem
0x180029fcd  call    cs:__imp_LocalFree
0x180029fd3  lea     eax, [rdi+4]
0x180029fd6  jmp     loc_18002A14B
0x180029fdb  xor     edx, edx; Offset
0x180029fdd  mov     rcx, rdi; Stream
0x180029fe0  lea     r8d, [rdx+2]; Origin
0x180029fe4  call    cs:__imp_fseek
0x180029fea  test    eax, eax
0x180029fec  jz      short loc_18002A04B
0x180029fee  lea     rcx, ModuleName; "mpunits.dll"
0x180029ff5  call    cs:__imp_GetModuleHandleA
0x180029ffb  mov     r8, rbp
0x180029ffe  mov     edx, 7E6h
0x18002a003  mov     rcx, rax
0x18002a006  call    _Intlstr_FormatString_FormatMessage
0x18002a00b  mov     rbx, rax
0x18002a00e  mov     [rsp+68h+extendedError], r14; extendedError
0x18002a013  mov     r9d, 6; int
0x18002a019  lea     rax, OMI_Error_rtti
0x18002a020  lea     r8, aBinarylogreade_1; "BinaryLogReader"
0x18002a027  mov     [rsp+68h+var_48], rax; __int64
0x18002a02c  mov     rcx, rbx; int
0x18002a02f  lea     edx, [r9+5Eh]; int
0x18002a033  call    CreateOMIError_shared
0x18002a038  mov     rcx, rbx; hMem
0x18002a03b  call    cs:__imp_LocalFree
0x18002a041  mov     ebx, 4
0x18002a046  jmp     loc_18002A12C
0x18002a04b  mov     rcx, rdi; Stream
0x18002a04e  call    cs:__imp_ftell
0x18002a054  movsxd  rbx, eax
0x18002a057  cmp     ebx, 0FFFFFFFFh
0x18002a05a  jnz     short loc_18002A069
0x18002a05c  call    cs:__imp__errno
0x18002a062  cmp     dword ptr [rax], 0
0x18002a065  jz      short loc_18002A06E
0x18002a067  jmp     short loc_180029FEE
0x18002a069  cmp     ebx, 0FFFFFFFEh
0x18002a06c  jbe     short loc_18002A078
0x18002a06e  mov     ebx, 1Bh
0x18002a073  jmp     loc_18002A12C
0x18002a078  xor     r8d, r8d; Origin
0x18002a07b  xor     edx, edx; Offset
0x18002a07d  mov     rcx, rdi; Stream
0x18002a080  call    cs:__imp_fseek
0x18002a086  test    eax, eax
0x18002a088  jnz     loc_180029FEE
0x18002a08e  lea     rcx, [rbx+1]; Size
0x18002a092  call    cs:__imp_malloc
0x18002a098  mov     rsi, rax
0x18002a09b  test    rax, rax
0x18002a09e  jz      short loc_18002A06E
0x18002a0a0  mov     r9, rdi; Stream
0x18002a0a3  mov     r8, rbx; ElementCount
0x18002a0a6  mov     edx, 1; ElementSize
0x18002a0ab  mov     rcx, rax; Buffer
0x18002a0ae  call    cs:__imp_fread
0x18002a0b4  movsxd  rcx, eax
0x18002a0b7  mov     rbx, rax
0x18002a0ba  mov     byte ptr [rcx+rsi], 0
0x18002a0be  mov     rcx, rdi; Stream
0x18002a0c1  call    cs:__imp_ferror
0x18002a0c7  test    eax, eax
0x18002a0c9  jz      short loc_18002A139
0x18002a0cb  lea     rcx, ModuleName; "mpunits.dll"
0x18002a0d2  call    cs:__imp_GetModuleHandleA
0x18002a0d8  mov     r8, rbp
0x18002a0db  mov     edx, 7E6h
0x18002a0e0  mov     rcx, rax
0x18002a0e3  call    _Intlstr_FormatString_FormatMessage
0x18002a0e8  mov     rbx, rax
0x18002a0eb  mov     [rsp+68h+extendedError], r14; extendedError
0x18002a0f0  mov     r9d, 6; int
0x18002a0f6  lea     rax, OMI_Error_rtti
0x18002a0fd  lea     r8, aBinarylogreade_1; "BinaryLogReader"
0x18002a104  mov     [rsp+68h+var_48], rax; __int64
0x18002a109  mov     rcx, rbx; int
0x18002a10c  lea     edx, [r9+5Eh]; int
0x18002a110  call    CreateOMIError_shared
0x18002a115  mov     rcx, rbx; hMem
0x18002a118  call    cs:__imp_LocalFree
0x18002a11e  mov     ebx, 4
0x18002a123  mov     rcx, rsi; Block
0x18002a126  call    cs:__imp_free
0x18002a12c  mov     rcx, rdi; Stream
0x18002a12f  call    cs:__imp_fclose
0x18002a135  mov     eax, ebx
0x18002a137  jmp     short loc_18002A14B
0x18002a139  mov     [r12], rsi
0x18002a13d  mov     rcx, rdi; Stream
0x18002a140  mov     [r15], ebx
0x18002a143  call    cs:__imp_fclose
0x18002a149  xor     eax, eax
0x18002a14b  add     rsp, 30h
0x18002a14f  pop     r15
0x18002a151  pop     r14
0x18002a153  pop     r12
0x18002a155  pop     rdi
0x18002a156  pop     rsi
0x18002a157  pop     rbp
0x18002a158  pop     rbx
0x18002a159  retn
```
