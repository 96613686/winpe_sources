# Js::DaylightTimeHelper::TryLoadLibrary(void)

- ea: `0x1802535d4`
- end: `0x180253658`
- name: `?TryLoadLibrary@DaylightTimeHelper@Js@@CAPEAUHINSTANCE__@@XZ`
- size: `132`
- prototype: `HINSTANCE(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180154ed0`
- `0x180253560`

## callees

- `0x1802535d4`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1802535f1`
- `KERNEL32!LoadLibraryExW` at `0x18025362b`
- `KERNEL32!LoadLibraryExW` at `0x1802535f1`
- `KERNEL32!LoadLibraryExW` at `0x18025362b`
- `KERNEL32!FreeLibrary` at `0x18025360c`
- `KERNEL32!FreeLibrary` at `0x180253646`
- `KERNEL32!FreeLibrary` at `0x18025360c`
- `KERNEL32!FreeLibrary` at `0x180253646`

## string_xrefs

- `0x1802535e4`: `api-ms-win-core-timezone-l1-1-0.dll`
- `0x18025361e`: `kernel32.dll`

## pseudocode

```c
__int64 Js::DaylightTimeHelper::TryLoadLibrary(void)
{
  HMODULE Library; // rax
  HMODULE v1; // rax

  if ( !qword_18043D968 )
  {
    Library = LoadLibraryExW(L"api-ms-win-core-timezone-l1-1-0.dll", 0, 0x800u);
    if ( Library && _InterlockedCompareExchange64(&qword_18043D968, (signed __int64)Library, 0) )
      FreeLibrary(Library);
    if ( !qword_18043D968 )
    {
      v1 = LoadLibraryExW(L"kernel32.dll", 0, 0x800u);
      if ( v1 )
      {
        if ( _InterlockedCompareExchange64(&qword_18043D968, (signed __int64)v1, 0) )
          FreeLibrary(v1);
      }
    }
  }
  return qword_18043D968;
}

```

## disassembly

```asm
0x1802535d4  sub     rsp, 28h
0x1802535d8  cmp     cs:qword_18043D968, 0
0x1802535e0  jnz     short loc_18025364C
0x1802535e2  xor     edx, edx; hFile
0x1802535e4  lea     rcx, aApiMsWinCoreTi; "api-ms-win-core-timezone-l1-1-0.dll"
0x1802535eb  mov     r8d, 800h; dwFlags
0x1802535f1  call    cs:__imp_LoadLibraryExW
0x1802535f7  mov     rcx, rax; hLibModule
0x1802535fa  test    rax, rax
0x1802535fd  jz      short loc_180253612
0x1802535ff  xor     eax, eax
0x180253601  lock cmpxchg cs:qword_18043D968, rcx
0x18025360a  jz      short loc_180253612
0x18025360c  call    cs:__imp_FreeLibrary
0x180253612  cmp     cs:qword_18043D968, 0
0x18025361a  jnz     short loc_18025364C
0x18025361c  xor     edx, edx; hFile
0x18025361e  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x180253625  mov     r8d, 800h; dwFlags
0x18025362b  call    cs:__imp_LoadLibraryExW
0x180253631  mov     rcx, rax; hLibModule
0x180253634  test    rax, rax
0x180253637  jz      short loc_18025364C
0x180253639  xor     eax, eax
0x18025363b  lock cmpxchg cs:qword_18043D968, rcx
0x180253644  jz      short loc_18025364C
0x180253646  call    cs:__imp_FreeLibrary
0x18025364c  mov     rax, cs:qword_18043D968
0x180253653  add     rsp, 28h
0x180253657  retn
```
