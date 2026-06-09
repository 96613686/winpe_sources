# Windows::Compat::Shared::Registry::GetPersistedLocation(ushort *,ulong,ushort const * const,ushort const * const,int)

- ea: `0x180028858`
- end: `0x180028917`
- name: `?GetPersistedLocation@Registry@Shared@Compat@Windows@@SAJPEAGKQEBG1H@Z`
- size: `191`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `17`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180026428`
- `0x18002f440`
- `0x18002f7c0`
- `0x180048808`
- `0x18004f8b0`
- `0x180061180`
- `0x180061750`
- `0x180093ee0`
- `0x1800942e0`
- `0x1800977a0`
- `0x1800a5398`
- `0x1800b79f0`
- `0x1800bd5e0`
- `0x1800c0940`
- `0x1800d29b8`
- `0x1800d6f20`
- `0x1800d9150`

## callees

- `0x180028858`
- `0x18018e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800288b3`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800288b3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002887d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002887d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180028904`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180028904`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002889c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002889c`

## string_xrefs

- `0x180028873`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Compat::Shared::Registry::GetPersistedLocation(
        unsigned __int16 *a1,
        unsigned int a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int a5)
{
  __int64 v6; // rsi
  HMODULE Library; // rax
  HMODULE v10; // rdi
  unsigned int v11; // ebx
  FARPROC ProcAddress; // rax
  int v13; // eax

  v6 = a2;
  Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
  v10 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "RtlGetPersistedStateLocation");
    if ( ProcAddress )
    {
      v13 = ((__int64 (__fastcall *)(const unsigned __int16 *, _QWORD, const unsigned __int16 *, bool, unsigned __int16 *, int, _QWORD))ProcAddress)(
              a3,
              0,
              a4,
              a5 == 0,
              a1,
              2 * (int)v6,
              0);
      v11 = v13 | 0x10000000;
      if ( v13 < 0 )
        goto LABEL_8;
    }
    else if ( (unsigned int)_o_wcscpy_s(a1, v6, a4) )
    {
      v11 = -2147467259;
LABEL_8:
      FreeLibrary(v10);
      return v11;
    }
    v11 = 0;
    goto LABEL_8;
  }
  return (unsigned int)-2147467259;
}

```

## disassembly

```asm
0x180028858  push    rbx
0x18002885a  push    rbp
0x18002885b  push    rsi
0x18002885c  push    rdi
0x18002885d  push    r14
0x18002885f  sub     rsp, 40h
0x180028863  mov     r14, r8
0x180028866  mov     esi, edx
0x180028868  mov     rbp, rcx
0x18002886b  xor     edx, edx; hFile
0x18002886d  mov     r8d, 800h; dwFlags
0x180028873  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18002887a  mov     rbx, r9
0x18002887d  call    cs:__imp_LoadLibraryExW
0x180028883  mov     rdi, rax
0x180028886  test    rax, rax
0x180028889  jnz     short loc_180028892
0x18002888b  mov     ebx, 80004005h
0x180028890  jmp     short loc_18002890A
0x180028892  lea     rdx, aRtlgetpersiste; "RtlGetPersistedStateLocation"
0x180028899  mov     rcx, rdi; hModule
0x18002889c  call    cs:__imp_GetProcAddress
0x1800288a2  mov     r10, rax
0x1800288a5  mov     r8, rbx
0x1800288a8  test    rax, rax
0x1800288ab  jnz     short loc_1800288C4
0x1800288ad  mov     rdx, rsi
0x1800288b0  mov     rcx, rbp
0x1800288b3  call    cs:__imp__o_wcscpy_s
0x1800288b9  test    eax, eax
0x1800288bb  jz      short loc_1800288FF
0x1800288bd  mov     ebx, 80004005h
0x1800288c2  jmp     short loc_180028901
0x1800288c4  xor     r9d, r9d
0x1800288c7  mov     [rsp+68h+var_38], 0
0x1800288d0  cmp     [rsp+68h+arg_20], r9d
0x1800288d8  lea     eax, [rsi+rsi]
0x1800288db  mov     [rsp+68h+var_40], eax
0x1800288df  mov     rcx, r14
0x1800288e2  setz    r9b
0x1800288e6  mov     [rsp+68h+var_48], rbp
0x1800288eb  xor     edx, edx
0x1800288ed  mov     rax, r10
0x1800288f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800288f5  mov     ebx, eax
0x1800288f7  or      ebx, 10000000h
0x1800288fd  jl      short loc_180028901
0x1800288ff  xor     ebx, ebx
0x180028901  mov     rcx, rdi; hLibModule
0x180028904  call    cs:__imp_FreeLibrary
0x18002890a  mov     eax, ebx
0x18002890c  add     rsp, 40h
0x180028910  pop     r14
0x180028912  pop     rdi
0x180028913  pop     rsi
0x180028914  pop     rbp
0x180028915  pop     rbx
0x180028916  retn
```
