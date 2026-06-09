# Microsoft::Diagnostics::UtcApiWrapper::Initialize(ulong)

- ea: `0x1800801a4`
- end: `0x180080217`
- name: `?Initialize@UtcApiWrapper@Diagnostics@Microsoft@@QEAAJK@Z`
- size: `115`
- prototype: `__int64 __fastcall(Microsoft::Diagnostics::UtcApiWrapper *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002b418`
- `0x1800800ac`

## callees

- `0x180047550`
- `0x1800801a4`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800801f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800801f1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800801b7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800801b7`

## string_xrefs

- `0x1800801aa`: `utcapi.dll`
- `0x1800801e7`: `UtcCreateSessionHandle`

## pseudocode

```c
__int64 __fastcall Microsoft::Diagnostics::UtcApiWrapper::Initialize(Microsoft::Diagnostics::UtcApiWrapper *this)
{
  HMODULE Library; // rax
  const char *v2; // r9
  __int64 v3; // rdx
  FARPROC ProcAddress; // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  Library = LoadLibraryExW(L"utcapi.dll", 0, 0x800u);
  hModule = Library;
  if ( !Library )
  {
    v3 = 88;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v3,
             (unsigned int)"onecore\\internal\\base\\inc\\utcapiwrapperex.h",
             v2);
  }
  ProcAddress = GetProcAddress(Library, "UtcCreateSessionHandle");
  if ( !ProcAddress )
  {
    v3 = 91;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v3,
             (unsigned int)"onecore\\internal\\base\\inc\\utcapiwrapperex.h",
             v2);
  }
  return ((__int64 (__fastcall *)(__int64 *))ProcAddress)(&g_utcApiWrapper);
}

```

## disassembly

```asm
0x1800801a4  sub     rsp, 28h
0x1800801a8  xor     edx, edx; hFile
0x1800801aa  lea     rcx, aUtcapiDll; "utcapi.dll"
0x1800801b1  mov     r8d, 800h; dwFlags
0x1800801b7  call    cs:__imp_LoadLibraryExW
0x1800801be  nop     dword ptr [rax+rax+00h]
0x1800801c3  mov     cs:hModule, rax
0x1800801ca  test    rax, rax
0x1800801cd  jnz     short loc_1800801E7
0x1800801cf  lea     edx, [rax+58h]; void *
0x1800801d2  mov     rcx, [rsp+28h]; this
0x1800801d7  lea     r8, aOnecoreInterna; "onecore\\internal\\base\\inc\\utcapiwra"...
0x1800801de  add     rsp, 28h
0x1800801e2  jmp     ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800801e7  lea     rdx, aUtccreatesessi; "UtcCreateSessionHandle"
0x1800801ee  mov     rcx, rax; hModule
0x1800801f1  call    cs:__imp_GetProcAddress
0x1800801f8  nop     dword ptr [rax+rax+00h]
0x1800801fd  test    rax, rax
0x180080200  jnz     short loc_180080207
0x180080202  lea     edx, [rax+5Bh]
0x180080205  jmp     short loc_1800801D2
0x180080207  lea     rcx, ?g_utcApiWrapper@@3VUtcApiWrapper@Diagnostics@Microsoft@@A; Microsoft::Diagnostics::UtcApiWrapper g_utcApiWrapper
0x18008020e  add     rsp, 28h
0x180080212  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
