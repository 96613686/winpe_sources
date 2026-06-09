# InternalCopyFileW(ushort const *,ushort const *,ulong)

- ea: `0x180018658`
- end: `0x18001871a`
- name: `?InternalCopyFileW@@YAHPEBG0K@Z`
- size: `194`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x18000e890`
- `0x180018720`

## callees

- `0x180018658`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800186f5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180018702`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800186f5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180018702`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800186ab`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800186ab`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800186c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800186c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018694`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018694`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x180018683`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x180018683`

## string_xrefs

- `0x1800186a2`: `kernel32.dll`
- `0x1800186b9`: `PrivCopyFileExW`

## pseudocode

```c
__int64 __fastcall InternalCopyFileW(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  HMODULE Library; // rax
  HMODULE v6; // rdi
  FARPROC ProcAddress; // rax
  unsigned int v8; // ebx

  if ( CopyFileExW(a1, a2, 0, 0, 0, 0) )
    return 1;
  if ( GetLastError() == 5 )
  {
    Library = LoadLibraryExW(L"kernel32.dll", 0, 0);
    v6 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "PrivCopyFileExW");
      if ( ProcAddress )
      {
        v8 = ((__int64 (__fastcall *)(const unsigned __int16 *, const unsigned __int16 *, _QWORD, _QWORD, _QWORD, int))ProcAddress)(
               a1,
               a2,
               0,
               0,
               0,
               256);
        FreeLibrary(v6);
        return v8;
      }
      FreeLibrary(v6);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180018658  mov     rax, rsp
0x18001865b  mov     [rax+8], rbx
0x18001865f  mov     [rax+10h], rsi
0x180018663  push    rdi
0x180018664  sub     rsp, 40h
0x180018668  mov     dword ptr [rax-20h], 0
0x18001866f  xor     r9d, r9d; lpData
0x180018672  xor     r8d, r8d; lpProgressRoutine
0x180018675  mov     qword ptr [rax-28h], 0
0x18001867d  mov     rbx, rdx
0x180018680  mov     rsi, rcx
0x180018683  call    cs:__imp_CopyFileExW
0x180018689  test    eax, eax
0x18001868b  jz      short loc_180018694
0x18001868d  mov     eax, 1
0x180018692  jmp     short loc_18001870A
0x180018694  call    cs:__imp_GetLastError
0x18001869a  cmp     eax, 5
0x18001869d  jnz     short loc_180018708
0x18001869f  xor     r8d, r8d; dwFlags
0x1800186a2  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x1800186a9  xor     edx, edx; hFile
0x1800186ab  call    cs:__imp_LoadLibraryExW
0x1800186b1  mov     rdi, rax
0x1800186b4  test    rax, rax
0x1800186b7  jz      short loc_180018708
0x1800186b9  lea     rdx, aPrivcopyfileex; "PrivCopyFileExW"
0x1800186c0  mov     rcx, rax; hModule
0x1800186c3  call    cs:__imp_GetProcAddress
0x1800186c9  test    rax, rax
0x1800186cc  jz      short loc_1800186FF
0x1800186ce  mov     [rsp+48h+var_20], 100h
0x1800186d6  xor     r9d, r9d
0x1800186d9  xor     r8d, r8d
0x1800186dc  mov     [rsp+48h+var_28], 0
0x1800186e5  mov     rdx, rbx
0x1800186e8  mov     rcx, rsi
0x1800186eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800186f0  mov     rcx, rdi; hLibModule
0x1800186f3  mov     ebx, eax
0x1800186f5  call    cs:__imp_FreeLibrary
0x1800186fb  mov     eax, ebx
0x1800186fd  jmp     short loc_18001870A
0x1800186ff  mov     rcx, rdi; hLibModule
0x180018702  call    cs:__imp_FreeLibrary
0x180018708  xor     eax, eax
0x18001870a  mov     rbx, [rsp+48h+arg_0]
0x18001870f  mov     rsi, [rsp+48h+arg_8]
0x180018714  add     rsp, 40h
0x180018718  pop     rdi
0x180018719  retn
```
