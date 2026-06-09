# Windows::Compat::Shared::Registry::GetPersistedLocation(ushort *,ulong,ushort const * const,ushort const * const,int)

- ea: `0x180011428`
- end: `0x1800114de`
- name: `?GetPersistedLocation@Registry@Shared@Compat@Windows@@SAJPEAGKQEBG1H@Z`
- size: `182`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int, const unsigned __int16 *const, const unsigned __int16 *const, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180012d3c`
- `0x18002e1f8`

## callees

- `0x180011428`
- `0x180116010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18001147e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18001147e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180011449`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180011449`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800114cd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800114cd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011468`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011468`

## string_xrefs

- `0x18001143d`: `ntdll.dll`

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
0x180011428  push    rbx
0x18001142a  push    rbp
0x18001142b  push    rsi
0x18001142c  push    rdi
0x18001142d  sub     rsp, 48h
0x180011431  mov     rbp, r8
0x180011434  mov     rsi, rcx
0x180011437  mov     r8d, 800h; dwFlags
0x18001143d  lea     rcx, LibFileName; "ntdll.dll"
0x180011444  xor     edx, edx; hFile
0x180011446  mov     rbx, r9
0x180011449  call    cs:__imp_LoadLibraryExW
0x18001144f  mov     rdi, rax
0x180011452  test    rax, rax
0x180011455  jnz     short loc_18001145E
0x180011457  mov     ebx, 80004005h
0x18001145c  jmp     short loc_1800114D3
0x18001145e  lea     rdx, aRtlgetpersiste; "RtlGetPersistedStateLocation"
0x180011465  mov     rcx, rdi; hModule
0x180011468  call    cs:__imp_GetProcAddress
0x18001146e  mov     r8, rbx
0x180011471  test    rax, rax
0x180011474  jnz     short loc_18001148F
0x180011476  mov     edx, 104h
0x18001147b  mov     rcx, rsi
0x18001147e  call    cs:__imp__o_wcscpy_s
0x180011484  test    eax, eax
0x180011486  jz      short loc_1800114C8
0x180011488  mov     ebx, 80004005h
0x18001148d  jmp     short loc_1800114CA
0x18001148f  xor     r9d, r9d
0x180011492  mov     [rsp+68h+var_38], 0
0x18001149b  cmp     [rsp+68h+arg_20], r9d
0x1800114a3  mov     rcx, rbp
0x1800114a6  mov     [rsp+68h+var_40], 208h
0x1800114ae  setz    r9b
0x1800114b2  mov     [rsp+68h+var_48], rsi
0x1800114b7  xor     edx, edx
0x1800114b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800114be  mov     ebx, eax
0x1800114c0  or      ebx, 10000000h
0x1800114c6  jl      short loc_1800114CA
0x1800114c8  xor     ebx, ebx
0x1800114ca  mov     rcx, rdi; hLibModule
0x1800114cd  call    cs:__imp_FreeLibrary
0x1800114d3  mov     eax, ebx
0x1800114d5  add     rsp, 48h
0x1800114d9  pop     rdi
0x1800114da  pop     rsi
0x1800114db  pop     rbp
0x1800114dc  pop     rbx
0x1800114dd  retn
```
