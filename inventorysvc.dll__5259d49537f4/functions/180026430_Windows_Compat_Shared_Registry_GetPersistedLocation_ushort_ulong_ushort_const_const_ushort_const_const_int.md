# Windows::Compat::Shared::Registry::GetPersistedLocation(ushort *,ulong,ushort const * const,ushort const * const,int)

- ea: `0x180026430`
- end: `0x1800264e6`
- name: `?GetPersistedLocation@Registry@Shared@Compat@Windows@@SAJPEAGKQEBG1H@Z`
- size: `182`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180027f6c`
- `0x180028c48`
- `0x18002c3ec`
- `0x1800be82c`
- `0x1800c8940`

## callees

- `0x180026430`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180026486`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180026486`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180026470`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180026470`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180026451`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180026451`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800264d5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800264d5`

## string_xrefs

- `0x180026445`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Shared::Registry::GetPersistedLocation(
        unsigned __int16 *a1,
        __int64 a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int a5)
{
  HMODULE Library; // rax
  HMODULE v9; // rdi
  unsigned int v10; // ebx
  FARPROC ProcAddress; // rax
  int v12; // eax

  Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
  v9 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "RtlGetPersistedStateLocation");
    if ( ProcAddress )
    {
      v12 = ((__int64 (__fastcall *)(const unsigned __int16 *, _QWORD, const unsigned __int16 *, bool, unsigned __int16 *, int, _QWORD))ProcAddress)(
              a3,
              0,
              a4,
              a5 == 0,
              a1,
              520,
              0);
      v10 = v12 | 0x10000000;
      if ( v12 < 0 )
        goto LABEL_8;
    }
    else if ( (unsigned int)_o_wcscpy_s(a1, 260, a4) )
    {
      v10 = -2147467259;
LABEL_8:
      FreeLibrary(v9);
      return v10;
    }
    v10 = 0;
    goto LABEL_8;
  }
  return (unsigned int)-2147467259;
}

```

## disassembly

```asm
0x180026430  push    rbx
0x180026432  push    rbp
0x180026433  push    rsi
0x180026434  push    rdi
0x180026435  sub     rsp, 48h
0x180026439  mov     rbp, r8
0x18002643c  mov     rsi, rcx
0x18002643f  mov     r8d, 800h; dwFlags
0x180026445  lea     rcx, LibFileName; "ntdll.dll"
0x18002644c  xor     edx, edx; hFile
0x18002644e  mov     rbx, r9
0x180026451  call    cs:__imp_LoadLibraryExW
0x180026457  mov     rdi, rax
0x18002645a  test    rax, rax
0x18002645d  jnz     short loc_180026466
0x18002645f  mov     ebx, 80004005h
0x180026464  jmp     short loc_1800264DB
0x180026466  lea     rdx, aRtlgetpersiste; "RtlGetPersistedStateLocation"
0x18002646d  mov     rcx, rdi; hModule
0x180026470  call    cs:__imp_GetProcAddress
0x180026476  mov     r8, rbx
0x180026479  test    rax, rax
0x18002647c  jnz     short loc_180026497
0x18002647e  mov     edx, 104h
0x180026483  mov     rcx, rsi
0x180026486  call    cs:__imp__o_wcscpy_s
0x18002648c  test    eax, eax
0x18002648e  jz      short loc_1800264D0
0x180026490  mov     ebx, 80004005h
0x180026495  jmp     short loc_1800264D2
0x180026497  xor     r9d, r9d
0x18002649a  mov     [rsp+68h+var_38], 0
0x1800264a3  cmp     [rsp+68h+arg_20], r9d
0x1800264ab  mov     rcx, rbp
0x1800264ae  mov     [rsp+68h+var_40], 208h
0x1800264b6  setz    r9b
0x1800264ba  mov     [rsp+68h+var_48], rsi
0x1800264bf  xor     edx, edx
0x1800264c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800264c6  mov     ebx, eax
0x1800264c8  or      ebx, 10000000h
0x1800264ce  jl      short loc_1800264D2
0x1800264d0  xor     ebx, ebx
0x1800264d2  mov     rcx, rdi; hLibModule
0x1800264d5  call    cs:__imp_FreeLibrary
0x1800264db  mov     eax, ebx
0x1800264dd  add     rsp, 48h
0x1800264e1  pop     rdi
0x1800264e2  pop     rsi
0x1800264e3  pop     rbp
0x1800264e4  pop     rbx
0x1800264e5  retn
```
