# _dynamic_initializer_for__g_pPerfInfo__

- ea: `0x180001390`
- end: `0x1800013e5`
- name: `_dynamic_initializer_for__g_pPerfInfo__`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001390`
- `0x180004b28`

## import_xrefs

- `KERNEL32!EncodeSystemPointer` at `0x1800013c8`
- `KERNEL32!EncodeSystemPointer` at `0x1800013c8`
- `KERNEL32!LoadLibraryExW` at `0x1800013a3`
- `KERNEL32!LoadLibraryExW` at `0x1800013a3`
- `KERNEL32!GetProcAddress` at `0x1800013bf`
- `KERNEL32!GetProcAddress` at `0x1800013bf`

## string_xrefs

- `0x180001396`: `ntdll.dll`

## pseudocode

```c
int dynamic_initializer_for__g_pPerfInfo__()
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax

  Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
  qword_18021C8D8 = (__int64)Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "EtwSetMark");
    g_pPerfInfo = EncodeSystemPointer(ProcAddress);
  }
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__g_pPerfInfo__);
}

```

## disassembly

```asm
0x180001390  sub     rsp, 28h
0x180001394  xor     edx, edx; hFile
0x180001396  lea     rcx, LibFileName; "ntdll.dll"
0x18000139d  mov     r8d, 800h; dwFlags
0x1800013a3  call    cs:__imp_LoadLibraryExW
0x1800013a9  mov     cs:qword_18021C8D8, rax
0x1800013b0  test    rax, rax
0x1800013b3  jz      short loc_1800013D5
0x1800013b5  lea     rdx, ProcName; "EtwSetMark"
0x1800013bc  mov     rcx, rax; hModule
0x1800013bf  call    cs:__imp_GetProcAddress
0x1800013c5  mov     rcx, rax; Ptr
0x1800013c8  call    cs:__imp_EncodeSystemPointer
0x1800013ce  mov     cs:?g_pPerfInfo@@3VCPerfInfo@@A, rax; CPerfInfo g_pPerfInfo
0x1800013d5  lea     rcx, _dynamic_atexit_destructor_for__g_pPerfInfo__
0x1800013dc  add     rsp, 28h
0x1800013e0  jmp     atexit
```
