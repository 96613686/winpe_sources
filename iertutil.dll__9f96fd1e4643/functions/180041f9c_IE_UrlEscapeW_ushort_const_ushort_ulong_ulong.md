# IE_UrlEscapeW(ushort const *,ushort *,ulong *,ulong)

- ea: `0x180041f9c`
- end: `0x180042058`
- name: `?IE_UrlEscapeW@@YAJPEBGPEAGPEAKK@Z`
- size: `188`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *, unsigned int *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180041dc0`

## callees

- `0x180041f9c`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180042050`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180042050`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004202a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004202a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180041ffc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180041ffc`

## string_xrefs

- `0x180041ff3`: `API-MS-WIN-CORE-URL-L1-1-0.DLL`

## pseudocode

```c
__int64 __fastcall IE_UrlEscapeW(const unsigned __int16 *a1, unsigned __int16 *a2, unsigned int *a3)
{
  FARPROC ProcAddress; // rax
  HMODULE v8; // rcx
  HMODULE Library; // rax

  ProcAddress = (FARPROC)qword_180298160;
  if ( qword_180298160 )
    return ((__int64 (__fastcall *)(const unsigned __int16 *, unsigned __int16 *, unsigned int *, __int64))ProcAddress)(
             a1,
             a2,
             a3,
             794624);
  v8 = qword_180298158;
  if ( qword_180298158 )
    goto LABEL_8;
  Library = LoadLibraryExW(L"API-MS-WIN-CORE-URL-L1-1-0.DLL", 0, 0);
  if ( Library )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&qword_180298158, (signed __int64)Library, 0) )
      FreeLibrary(Library);
  }
  v8 = qword_180298158;
  if ( qword_180298158 )
  {
LABEL_8:
    ProcAddress = GetProcAddress(v8, "UrlEscapeW");
    qword_180298160 = (__int64)ProcAddress;
    if ( ProcAddress )
      return ((__int64 (__fastcall *)(const unsigned __int16 *, unsigned __int16 *, unsigned int *, __int64))ProcAddress)(
               a1,
               a2,
               a3,
               794624);
  }
  else
  {
    qword_180298160 = 0;
  }
  return 2147500033LL;
}

```

## disassembly

```asm
0x180041f9c  mov     [rsp+arg_0], rbx
0x180041fa1  mov     [rsp+arg_8], rsi
0x180041fa6  push    rdi
0x180041fa7  sub     rsp, 30h
0x180041fab  mov     rax, cs:qword_180298160
0x180041fb2  mov     rbx, r8
0x180041fb5  mov     rdi, rdx
0x180041fb8  mov     rsi, rcx
0x180041fbb  test    rax, rax
0x180041fbe  jz      short loc_180041FE4
0x180041fc0  mov     r9d, 0C2000h
0x180041fc6  mov     r8, rbx
0x180041fc9  mov     rdx, rdi
0x180041fcc  mov     rcx, rsi
0x180041fcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041fd4  mov     rbx, [rsp+38h+arg_0]
0x180041fd9  mov     rsi, [rsp+38h+arg_8]
0x180041fde  add     rsp, 30h
0x180041fe2  pop     rdi
0x180041fe3  retn
0x180041fe4  mov     rcx, cs:qword_180298158
0x180041feb  test    rcx, rcx
0x180041fee  jnz     short loc_180042023
0x180041ff0  xor     r8d, r8d; dwFlags
0x180041ff3  lea     rcx, aApiMsWinCoreUr; "API-MS-WIN-CORE-URL-L1-1-0.DLL"
0x180041ffa  xor     edx, edx; hFile
0x180041ffc  call    cs:__imp_LoadLibraryExW
0x180042002  mov     rcx, rax; hLibModule
0x180042005  test    rax, rax
0x180042008  jz      short loc_180042017
0x18004200a  xor     eax, eax
0x18004200c  lock cmpxchg cs:qword_180298158, rcx
0x180042015  jnz     short loc_180042050
0x180042017  mov     rcx, cs:qword_180298158; hModule
0x18004201e  test    rcx, rcx
0x180042021  jz      short loc_180042043
0x180042023  lea     rdx, aUrlescapew; "UrlEscapeW"
0x18004202a  call    cs:__imp_GetProcAddress
0x180042030  mov     cs:qword_180298160, rax
0x180042037  test    rax, rax
0x18004203a  jnz     short loc_180041FC0
0x18004203c  mov     eax, 80004001h
0x180042041  jmp     short loc_180041FD4
0x180042043  mov     cs:qword_180298160, 0
0x18004204e  jmp     short loc_18004203C
0x180042050  call    cs:__imp_FreeLibrary
0x180042056  jmp     short loc_180042017
```
