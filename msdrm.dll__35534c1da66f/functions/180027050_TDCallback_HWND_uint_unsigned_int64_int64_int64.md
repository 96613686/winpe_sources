# TDCallback(HWND__ *,uint,unsigned __int64,__int64,__int64)

- ea: `0x180027050`
- end: `0x1800270d5`
- name: `?TDCallback@@YAJPEAUHWND__@@I_K_J2@Z`
- size: `133`
- prototype: `__int64 __fastcall(HWND, unsigned int, unsigned __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180027050`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180027089`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180027089`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800270bd`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800270bd`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryA` at `0x180027071`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryA` at `0x180027071`

## string_xrefs

- `0x18002706a`: `shell32.dll`

## pseudocode

```c
__int64 __fastcall TDCallback(HWND a1, int a2, __int64 a3, __int64 a4)
{
  HMODULE LibraryA; // rax
  HMODULE v7; // rbx
  FARPROC ProcAddress; // rax

  if ( a2 == 3 )
  {
    LibraryA = LoadLibraryA("shell32.dll");
    v7 = LibraryA;
    if ( LibraryA )
    {
      ProcAddress = GetProcAddress(LibraryA, "ShellExecuteW");
      if ( ProcAddress )
        ((void (__fastcall *)(HWND, const wchar_t *, __int64, _QWORD, _QWORD, int))ProcAddress)(
          a1,
          L"open",
          a4,
          0,
          0,
          5);
      FreeLibrary(v7);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180027050  mov     [rsp+arg_0], rbx
0x180027055  mov     [rsp+arg_8], rsi
0x18002705a  push    rdi
0x18002705b  sub     rsp, 40h
0x18002705f  mov     rdi, r9
0x180027062  mov     rsi, rcx
0x180027065  cmp     edx, 3
0x180027068  jnz     short loc_1800270C3
0x18002706a  lea     rcx, aShell32Dll; "shell32.dll"
0x180027071  call    cs:__imp_LoadLibraryA
0x180027077  mov     rbx, rax
0x18002707a  test    rax, rax
0x18002707d  jz      short loc_1800270C3
0x18002707f  lea     rdx, aShellexecutew; "ShellExecuteW"
0x180027086  mov     rcx, rax; hModule
0x180027089  call    cs:__imp_GetProcAddress
0x18002708f  test    rax, rax
0x180027092  jz      short loc_1800270BA
0x180027094  mov     [rsp+48h+var_20], 5
0x18002709c  lea     rdx, aOpen; "open"
0x1800270a3  xor     r9d, r9d
0x1800270a6  mov     [rsp+48h+var_28], 0
0x1800270af  mov     r8, rdi
0x1800270b2  mov     rcx, rsi
0x1800270b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800270ba  mov     rcx, rbx; hLibModule
0x1800270bd  call    cs:__imp_FreeLibrary
0x1800270c3  mov     rbx, [rsp+48h+arg_0]
0x1800270c8  xor     eax, eax
0x1800270ca  mov     rsi, [rsp+48h+arg_8]
0x1800270cf  add     rsp, 40h
0x1800270d3  pop     rdi
0x1800270d4  retn
```
