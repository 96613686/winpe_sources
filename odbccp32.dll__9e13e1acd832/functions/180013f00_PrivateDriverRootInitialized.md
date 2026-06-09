# PrivateDriverRootInitialized

- ea: `0x180013f00`
- end: `0x180013fa1`
- name: `PrivateDriverRootInitialized`
- size: `161`
- prototype: `__int64 __fastcall(HMODULE)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180001010`
- `0x180002f80`
- `0x180007394`
- `0x18000d0f0`
- `0x18000ea9c`
- `0x180013c7c`
- `0x18001418c`

## callees

- `0x180013f00`

## import_xrefs

- `msvcrt!_snwprintf_s` at `0x180013f78`
- `msvcrt!_snwprintf_s` at `0x180013f78`
- `msvcrt!wcsrchr` at `0x180013f40`
- `msvcrt!wcsrchr` at `0x180013f40`
- `KERNEL32!GetModuleFileNameW` at `0x180013f29`
- `KERNEL32!GetModuleFileNameW` at `0x180013f29`

## pseudocode

```c
__int64 __fastcall PrivateDriverRootInitialized(HMODULE a1)
{
  char v1; // al
  unsigned int v2; // ebx
  signed int ModuleFileNameW; // eax
  wchar_t *v4; // rax

  v1 = PrivateDriverRootInitialized;
  v2 = 1;
  if ( !PrivateDriverRootInitialized )
  {
    ModuleFileNameW = GetModuleFileNameW(a1, &szODBCDriverModuleRoot, 0x104u);
    if ( ModuleFileNameW >= 1 && (unsigned int)ModuleFileNameW <= 0x104 )
    {
      v4 = wcsrchr(&szODBCDriverModuleRoot, 0x5Cu);
      if ( v4 )
        *v4 = 0;
      _snwprintf_s(
        &szODBCPrivateDriverRoot,
        0x104u,
        0xFFFFFFFFFFFFFFFFuLL,
        L"%ls\\%ls",
        &szODBCDriverModuleRoot,
        L"ODBC Drivers");
      PrivateDriverRootInitialized = 1;
      return v2;
    }
    v1 = 2;
    PrivateDriverRootInitialized = 2;
  }
  if ( v1 != 1 )
    return 0;
  return v2;
}

```

## disassembly

```asm
0x180013f00  mov     [rsp+arg_0], rbx
0x180013f05  push    rsi
0x180013f06  sub     rsp, 30h
0x180013f0a  mov     al, cs:_PrivateDriverRootInitialized
0x180013f10  mov     ebx, 1
0x180013f15  test    al, al
0x180013f17  jnz     short loc_180013F8E
0x180013f19  lea     rsi, szODBCDriverModuleRoot
0x180013f20  mov     r8d, 104h; nSize
0x180013f26  mov     rdx, rsi; lpFilename
0x180013f29  call    cs:__imp_GetModuleFileNameW
0x180013f2f  cmp     eax, ebx
0x180013f31  jl      short loc_180013F86
0x180013f33  cmp     eax, 104h
0x180013f38  ja      short loc_180013F86
0x180013f3a  lea     edx, [rbx+5Bh]; Ch
0x180013f3d  mov     rcx, rsi; Str
0x180013f40  call    cs:__imp_wcsrchr
0x180013f46  test    rax, rax
0x180013f49  jz      short loc_180013F50
0x180013f4b  xor     ecx, ecx
0x180013f4d  mov     [rax], cx
0x180013f50  lea     rax, aOdbcDrivers; "ODBC Drivers"
0x180013f57  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180013f5b  mov     [rsp+38h+var_10], rax
0x180013f60  lea     r9, aLsLs; "%ls\\%ls"
0x180013f67  mov     edx, 104h; BufferCount
0x180013f6c  mov     [rsp+38h+var_18], rsi
0x180013f71  lea     rcx, szODBCPrivateDriverRoot; Buffer
0x180013f78  call    cs:__imp__snwprintf_s
0x180013f7e  mov     cs:_PrivateDriverRootInitialized, bl
0x180013f84  jmp     short loc_180013F94
0x180013f86  mov     al, 2
0x180013f88  mov     cs:_PrivateDriverRootInitialized, al
0x180013f8e  cmp     al, bl
0x180013f90  jz      short loc_180013F94
0x180013f92  xor     ebx, ebx
0x180013f94  mov     eax, ebx
0x180013f96  mov     rbx, [rsp+38h+arg_0]
0x180013f9b  add     rsp, 30h
0x180013f9f  pop     rsi
0x180013fa0  retn
```
