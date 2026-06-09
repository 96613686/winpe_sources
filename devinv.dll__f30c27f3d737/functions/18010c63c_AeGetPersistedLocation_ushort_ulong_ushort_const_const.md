# AeGetPersistedLocation(ushort *,ulong,ushort const * const)

- ea: `0x18010c63c`
- end: `0x18010c6e7`
- name: `?AeGetPersistedLocation@@YAJPEAGKQEBG@Z`
- size: `171`
- prototype: `__int64 __fastcall(wchar_t *Destination, unsigned int, const unsigned __int16 *const)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18010c7e8`

## callees

- `0x180006e88`
- `0x18010c63c`
- `0x180116010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18010c660`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18010c660`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18010c67c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18010c67c`

## string_xrefs

- `0x18010c657`: `ntdll.dll`
- `0x18010c690`: `Amcache`

## pseudocode

```c
__int64 __fastcall AeGetPersistedLocation(wchar_t *Destination, __int64 a2, const wchar_t *a3)
{
  HMODULE Library; // rax
  unsigned int v6; // ebx
  FARPROC ProcAddress; // rax
  int v8; // eax

  Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
  if ( Library && (ProcAddress = GetProcAddress(Library, "RtlGetPersistedStateLocation")) != 0 )
  {
    v8 = ((__int64 (__fastcall *)(const unsigned __int16 *, _QWORD, const wchar_t *, __int64, wchar_t *, int, _QWORD))ProcAddress)(
           L"Amcache",
           0,
           a3,
           1,
           Destination,
           522,
           0);
    v6 = v8 | 0x10000000;
    if ( v8 >= 0 )
      return v6;
  }
  else
  {
    v6 = -2147467259;
  }
  if ( !wcscpy_s(Destination, 0x105u, a3) )
    return 0;
  return v6;
}

```

## disassembly

```asm
0x18010c63c  mov     [rsp+arg_0], rbx
0x18010c641  mov     [rsp+arg_8], rsi
0x18010c646  push    rdi
0x18010c647  sub     rsp, 40h
0x18010c64b  mov     rdi, r8
0x18010c64e  mov     rsi, rcx
0x18010c651  mov     r8d, 800h; dwFlags
0x18010c657  lea     rcx, LibFileName; "ntdll.dll"
0x18010c65e  xor     edx, edx; hFile
0x18010c660  call    cs:__imp_LoadLibraryExW
0x18010c666  test    rax, rax
0x18010c669  jnz     short loc_18010C672
0x18010c66b  mov     ebx, 80004005h
0x18010c670  jmp     short loc_18010C6BE
0x18010c672  lea     rdx, aRtlgetpersiste; "RtlGetPersistedStateLocation"
0x18010c679  mov     rcx, rax; hModule
0x18010c67c  call    cs:__imp_GetProcAddress
0x18010c682  test    rax, rax
0x18010c685  jz      short loc_18010C66B
0x18010c687  mov     [rsp+48h+var_18], 0
0x18010c690  lea     rcx, aAmcache; "Amcache"
0x18010c697  mov     [rsp+48h+var_20], 20Ah
0x18010c69f  mov     r9d, 1
0x18010c6a5  mov     r8, rdi
0x18010c6a8  mov     [rsp+48h+var_28], rsi
0x18010c6ad  xor     edx, edx
0x18010c6af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010c6b4  mov     ebx, eax
0x18010c6b6  or      ebx, 10000000h
0x18010c6bc  jge     short loc_18010C6D5
0x18010c6be  mov     r8, rdi; Source
0x18010c6c1  mov     edx, 105h; SizeInWords
0x18010c6c6  mov     rcx, rsi; Destination
0x18010c6c9  call    wcscpy_s
0x18010c6ce  xor     ecx, ecx
0x18010c6d0  test    eax, eax
0x18010c6d2  cmovz   ebx, ecx
0x18010c6d5  mov     rsi, [rsp+48h+arg_8]
0x18010c6da  mov     eax, ebx
0x18010c6dc  mov     rbx, [rsp+48h+arg_0]
0x18010c6e1  add     rsp, 40h
0x18010c6e5  pop     rdi
0x18010c6e6  retn
```
