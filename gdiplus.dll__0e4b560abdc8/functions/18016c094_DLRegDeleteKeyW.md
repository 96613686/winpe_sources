# DLRegDeleteKeyW

- ea: `0x18016c094`
- end: `0x18016c16c`
- name: `DLRegDeleteKeyW`
- size: `216`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180150974`

## callees

- `0x1800b7bb8`
- `0x18016c094`
- `0x180175010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18016c0db`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18016c104`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18016c0db`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18016c104`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18016c131`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18016c131`

## string_xrefs

- `0x18016c0fd`: `RegDeleteKeyW`
- `0x18016c0d4`: `RegDeleteKeyExW`

## pseudocode

```c
DWORD __fastcall DLRegDeleteKeyW(__int64 a1, __int64 a2)
{
  int (*v2)(HKEY, const unsigned __int16 *, unsigned int, unsigned int); // r10
  FARPROC ProcAddress; // rax
  DWORD result; // eax

  v2 = g_pfnRegDeleteKeyExW;
  if ( !g_pfnRegDeleteKeyExW )
  {
    ProcAddress = (FARPROC)qword_1801B3D68;
    if ( qword_1801B3D68 )
      return ((__int64 (__fastcall *)(__int64, __int64))ProcAddress)(a1, a2);
    result = DLpLoadRegistryDll();
    if ( result )
      return result;
    g_pfnRegDeleteKeyExW = (int (*)(HKEY, const unsigned __int16 *, unsigned int, unsigned int))GetProcAddress(
                                                                                                  g_hInstRegistryDLL,
                                                                                                  "RegDeleteKeyExW");
    v2 = g_pfnRegDeleteKeyExW;
    if ( g_pfnRegDeleteKeyExW )
    {
      ProcAddress = (FARPROC)qword_1801B3D68;
    }
    else
    {
      ProcAddress = GetProcAddress(g_hInstRegistryDLL, "RegDeleteKeyW");
      v2 = g_pfnRegDeleteKeyExW;
      qword_1801B3D68 = (__int64)ProcAddress;
    }
    if ( !v2 )
    {
      if ( !ProcAddress )
        return GetLastError();
      return ((__int64 (__fastcall *)(__int64, __int64))ProcAddress)(a1, a2);
    }
  }
  return ((__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD))v2)(a1, a2, 0, 0);
}

```

## disassembly

```asm
0x18016c094  mov     [rsp+arg_0], rbx
0x18016c099  push    rdi
0x18016c09a  sub     rsp, 30h
0x18016c09e  mov     r10, cs:?g_pfnRegDeleteKeyExW@@3P6AJPEAUHKEY__@@PEBGKK@ZEA; long (*g_pfnRegDeleteKeyExW)(HKEY__ *,ushort const *,ulong,ulong)
0x18016c0a5  mov     rbx, rdx
0x18016c0a8  mov     rdi, rcx
0x18016c0ab  test    r10, r10
0x18016c0ae  jnz     loc_18016C14C
0x18016c0b4  mov     rax, cs:qword_1801B3D68
0x18016c0bb  test    rax, rax
0x18016c0be  jnz     short loc_18016C13F
0x18016c0c0  call    ?DLpLoadRegistryDll@@YAKXZ; DLpLoadRegistryDll(void)
0x18016c0c5  test    eax, eax
0x18016c0c7  jnz     loc_18016C160
0x18016c0cd  mov     rcx, cs:?g_hInstRegistryDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18016c0d4  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x18016c0db  call    cs:__imp_GetProcAddress
0x18016c0e2  nop     dword ptr [rax+rax+00h]
0x18016c0e7  mov     cs:?g_pfnRegDeleteKeyExW@@3P6AJPEAUHKEY__@@PEBGKK@ZEA, rax; long (*g_pfnRegDeleteKeyExW)(HKEY__ *,ushort const *,ulong,ulong)
0x18016c0ee  mov     r10, rax
0x18016c0f1  test    rax, rax
0x18016c0f4  jnz     short loc_18016C120
0x18016c0f6  mov     rcx, cs:?g_hInstRegistryDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18016c0fd  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x18016c104  call    cs:__imp_GetProcAddress
0x18016c10b  nop     dword ptr [rax+rax+00h]
0x18016c110  mov     r10, cs:?g_pfnRegDeleteKeyExW@@3P6AJPEAUHKEY__@@PEBGKK@ZEA; long (*g_pfnRegDeleteKeyExW)(HKEY__ *,ushort const *,ulong,ulong)
0x18016c117  mov     cs:qword_1801B3D68, rax
0x18016c11e  jmp     short loc_18016C127
0x18016c120  mov     rax, cs:qword_1801B3D68
0x18016c127  test    r10, r10
0x18016c12a  jnz     short loc_18016C14C
0x18016c12c  test    rax, rax
0x18016c12f  jnz     short loc_18016C13F
0x18016c131  call    cs:__imp_GetLastError
0x18016c138  nop     dword ptr [rax+rax+00h]
0x18016c13d  jmp     short loc_18016C160
0x18016c13f  mov     rdx, rbx
0x18016c142  mov     rcx, rdi
0x18016c145  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016c14a  jmp     short loc_18016C160
0x18016c14c  xor     r9d, r9d
0x18016c14f  xor     r8d, r8d
0x18016c152  mov     rdx, rbx
0x18016c155  mov     rcx, rdi
0x18016c158  mov     rax, r10
0x18016c15b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016c160  mov     rbx, [rsp+38h+arg_0]
0x18016c165  add     rsp, 30h
0x18016c169  pop     rdi
0x18016c16a  retn
```
