# Js::DaylightTimeHelper::TryLoadLibrary(void)

- ea: `0x180257c8c`
- end: `0x180257d2d`
- name: `?TryLoadLibrary@DaylightTimeHelper@Js@@CAPEAUHINSTANCE__@@XZ`
- size: `161`
- prototype: `HINSTANCE(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180157d70`
- `0x180257c14`

## callees

- `0x180257c8c`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180257cad`
- `KERNEL32!LoadLibraryExW` at `0x180257cf3`
- `KERNEL32!LoadLibraryExW` at `0x180257cad`
- `KERNEL32!LoadLibraryExW` at `0x180257cf3`
- `KERNEL32!FreeLibrary` at `0x180257cce`
- `KERNEL32!FreeLibrary` at `0x180257d14`
- `KERNEL32!FreeLibrary` at `0x180257cce`
- `KERNEL32!FreeLibrary` at `0x180257d14`

## string_xrefs

- `0x180257ca0`: `api-ms-win-core-timezone-l1-1-0.dll`
- `0x180257ce6`: `kernel32.dll`

## pseudocode

```c
__int64 Js::DaylightTimeHelper::TryLoadLibrary(void)
{
  HMODULE Library; // rax
  HMODULE v1; // rax

  if ( !qword_180443968 )
  {
    Library = LoadLibraryExW(L"api-ms-win-core-timezone-l1-1-0.dll", 0, 0x800u);
    if ( Library && _InterlockedCompareExchange64(&qword_180443968, (signed __int64)Library, 0) )
      FreeLibrary(Library);
    if ( !qword_180443968 )
    {
      v1 = LoadLibraryExW(L"kernel32.dll", 0, 0x800u);
      if ( v1 )
      {
        if ( _InterlockedCompareExchange64(&qword_180443968, (signed __int64)v1, 0) )
          FreeLibrary(v1);
      }
    }
  }
  return qword_180443968;
}

```

## disassembly

```asm
0x180257c8c  sub     rsp, 28h
0x180257c90  cmp     cs:qword_180443968, 0
0x180257c98  jnz     loc_180257D20
0x180257c9e  xor     edx, edx; hFile
0x180257ca0  lea     rcx, aApiMsWinCoreTi; "api-ms-win-core-timezone-l1-1-0.dll"
0x180257ca7  mov     r8d, 800h; dwFlags
0x180257cad  call    cs:__imp_LoadLibraryExW
0x180257cb4  nop     dword ptr [rax+rax+00h]
0x180257cb9  mov     rcx, rax; hLibModule
0x180257cbc  test    rax, rax
0x180257cbf  jz      short loc_180257CDA
0x180257cc1  xor     eax, eax
0x180257cc3  lock cmpxchg cs:qword_180443968, rcx
0x180257ccc  jz      short loc_180257CDA
0x180257cce  call    cs:__imp_FreeLibrary
0x180257cd5  nop     dword ptr [rax+rax+00h]
0x180257cda  cmp     cs:qword_180443968, 0
0x180257ce2  jnz     short loc_180257D20
0x180257ce4  xor     edx, edx; hFile
0x180257ce6  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x180257ced  mov     r8d, 800h; dwFlags
0x180257cf3  call    cs:__imp_LoadLibraryExW
0x180257cfa  nop     dword ptr [rax+rax+00h]
0x180257cff  mov     rcx, rax; hLibModule
0x180257d02  test    rax, rax
0x180257d05  jz      short loc_180257D20
0x180257d07  xor     eax, eax
0x180257d09  lock cmpxchg cs:qword_180443968, rcx
0x180257d12  jz      short loc_180257D20
0x180257d14  call    cs:__imp_FreeLibrary
0x180257d1b  nop     dword ptr [rax+rax+00h]
0x180257d20  mov     rax, cs:qword_180443968
0x180257d27  add     rsp, 28h
0x180257d2b  retn
```
