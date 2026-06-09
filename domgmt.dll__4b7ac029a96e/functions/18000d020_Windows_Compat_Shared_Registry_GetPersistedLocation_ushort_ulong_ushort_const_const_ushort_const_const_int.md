# Windows::Compat::Shared::Registry::GetPersistedLocation(ushort *,ulong,ushort const * const,ushort const * const,int)

- ea: `0x18000d020`
- end: `0x18000d0ca`
- name: `?GetPersistedLocation@Registry@Shared@Compat@Windows@@SAJPEAGKQEBG1H@Z`
- size: `170`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000ce20`

## callees

- `0x18000d020`
- `0x18000e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000d076`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000d076`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d060`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d060`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000d0b9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000d0b9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000d041`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000d041`

## string_xrefs

- `0x18000d035`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Shared::Registry::GetPersistedLocation(
        unsigned __int16 *a1,
        __int64 a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  HMODULE Library; // rax
  HMODULE v8; // rdi
  unsigned int v9; // ebx
  FARPROC ProcAddress; // rax
  int v11; // eax

  Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
  v8 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "RtlGetPersistedStateLocation");
    if ( ProcAddress )
    {
      v11 = ((__int64 (__fastcall *)(const unsigned __int16 *, _QWORD, const unsigned __int16 *, _QWORD, unsigned __int16 *, int, _QWORD))ProcAddress)(
              a3,
              0,
              a4,
              0,
              a1,
              520,
              0);
      v9 = v11 | 0x10000000;
      if ( v11 < 0 )
        goto LABEL_8;
    }
    else if ( (unsigned int)_o_wcscpy_s(a1, 260, a4) )
    {
      v9 = -2147467259;
LABEL_8:
      FreeLibrary(v8);
      return v9;
    }
    v9 = 0;
    goto LABEL_8;
  }
  return (unsigned int)-2147467259;
}

```

## disassembly

```asm
0x18000d020  push    rbx
0x18000d022  push    rbp
0x18000d023  push    rsi
0x18000d024  push    rdi
0x18000d025  sub     rsp, 48h
0x18000d029  mov     rbp, r8
0x18000d02c  mov     rsi, rcx
0x18000d02f  mov     r8d, 800h; dwFlags
0x18000d035  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000d03c  xor     edx, edx; hFile
0x18000d03e  mov     rbx, r9
0x18000d041  call    cs:__imp_LoadLibraryExW
0x18000d047  mov     rdi, rax
0x18000d04a  test    rax, rax
0x18000d04d  jnz     short loc_18000D056
0x18000d04f  mov     ebx, 80004005h
0x18000d054  jmp     short loc_18000D0BF
0x18000d056  lea     rdx, aRtlgetpersiste; "RtlGetPersistedStateLocation"
0x18000d05d  mov     rcx, rdi; hModule
0x18000d060  call    cs:__imp_GetProcAddress
0x18000d066  mov     r8, rbx
0x18000d069  test    rax, rax
0x18000d06c  jnz     short loc_18000D087
0x18000d06e  mov     edx, 104h
0x18000d073  mov     rcx, rsi
0x18000d076  call    cs:__imp__o_wcscpy_s
0x18000d07c  test    eax, eax
0x18000d07e  jz      short loc_18000D0B4
0x18000d080  mov     ebx, 80004005h
0x18000d085  jmp     short loc_18000D0B6
0x18000d087  mov     [rsp+68h+var_38], 0
0x18000d090  xor     r9d, r9d
0x18000d093  mov     [rsp+68h+var_40], 208h
0x18000d09b  xor     edx, edx
0x18000d09d  mov     rcx, rbp
0x18000d0a0  mov     [rsp+68h+var_48], rsi
0x18000d0a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d0aa  mov     ebx, eax
0x18000d0ac  or      ebx, 10000000h
0x18000d0b2  jl      short loc_18000D0B6
0x18000d0b4  xor     ebx, ebx
0x18000d0b6  mov     rcx, rdi; hLibModule
0x18000d0b9  call    cs:__imp_FreeLibrary
0x18000d0bf  mov     eax, ebx
0x18000d0c1  add     rsp, 48h
0x18000d0c5  pop     rdi
0x18000d0c6  pop     rsi
0x18000d0c7  pop     rbp
0x18000d0c8  pop     rbx
0x18000d0c9  retn
```
