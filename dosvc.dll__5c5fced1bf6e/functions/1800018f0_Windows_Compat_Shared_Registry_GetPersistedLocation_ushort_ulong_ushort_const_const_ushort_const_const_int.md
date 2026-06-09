# Windows::Compat::Shared::Registry::GetPersistedLocation(ushort *,ulong,ushort const * const,ushort const * const,int)

- ea: `0x1800018f0`
- end: `0x18000199a`
- name: `?GetPersistedLocation@Registry@Shared@Compat@Windows@@SAJPEAGKQEBG1H@Z`
- size: `170`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180001790`

## callees

- `0x1800018f0`
- `0x18000b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180001989`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180001989`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180001911`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180001911`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180001969`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180001969`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001929`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001929`

## string_xrefs

- `0x180001905`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Shared::Registry::GetPersistedLocation(
        unsigned __int16 *a1,
        __int64 a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  HMODULE Library; // rax
  HMODULE v8; // rbx
  FARPROC ProcAddress; // rax
  int v10; // eax
  unsigned int v11; // edi

  Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
  v8 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "RtlGetPersistedStateLocation");
    if ( ProcAddress )
    {
      v10 = ((__int64 (__fastcall *)(const unsigned __int16 *, _QWORD, const unsigned __int16 *, _QWORD, unsigned __int16 *, int, _QWORD))ProcAddress)(
              a3,
              0,
              a4,
              0,
              a1,
              520,
              0);
      v11 = v10 | 0x10000000;
      if ( v10 < 0 )
      {
LABEL_5:
        FreeLibrary(v8);
        return v11;
      }
    }
    else if ( (unsigned int)_o_wcscpy_s(a1, 260, a4) )
    {
      v11 = -2147467259;
      goto LABEL_5;
    }
    v11 = 0;
    goto LABEL_5;
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x1800018f0  push    rbx
0x1800018f2  push    rbp
0x1800018f3  push    rsi
0x1800018f4  push    rdi
0x1800018f5  sub     rsp, 48h
0x1800018f9  mov     rbp, r8
0x1800018fc  mov     rsi, rcx
0x1800018ff  mov     r8d, 800h; dwFlags
0x180001905  lea     rcx, LibFileName; "ntdll.dll"
0x18000190c  xor     edx, edx; hFile
0x18000190e  mov     rdi, r9
0x180001911  call    cs:__imp_LoadLibraryExW
0x180001917  mov     rbx, rax
0x18000191a  test    rax, rax
0x18000191d  jz      short loc_18000197A
0x18000191f  lea     rdx, ProcName; "RtlGetPersistedStateLocation"
0x180001926  mov     rcx, rax; hModule
0x180001929  call    cs:__imp_GetProcAddress
0x18000192f  mov     r8, rdi
0x180001932  test    rax, rax
0x180001935  jz      short loc_180001981
0x180001937  mov     [rsp+68h+var_38], 0
0x180001940  xor     r9d, r9d
0x180001943  mov     [rsp+68h+var_40], 208h
0x18000194b  xor     edx, edx
0x18000194d  mov     rcx, rbp
0x180001950  mov     [rsp+68h+var_48], rsi
0x180001955  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000195a  mov     edi, eax
0x18000195c  or      edi, 10000000h
0x180001962  jl      short loc_180001966
0x180001964  xor     edi, edi
0x180001966  mov     rcx, rbx; hLibModule
0x180001969  call    cs:__imp_FreeLibrary
0x18000196f  mov     eax, edi
0x180001971  add     rsp, 48h
0x180001975  pop     rdi
0x180001976  pop     rsi
0x180001977  pop     rbp
0x180001978  pop     rbx
0x180001979  retn
0x18000197a  mov     eax, 80004005h
0x18000197f  jmp     short loc_180001971
0x180001981  mov     edx, 104h
0x180001986  mov     rcx, rsi
0x180001989  call    cs:__imp__o_wcscpy_s
0x18000198f  test    eax, eax
0x180001991  jz      short loc_180001964
0x180001993  mov     edi, 80004005h
0x180001998  jmp     short loc_180001966
```
