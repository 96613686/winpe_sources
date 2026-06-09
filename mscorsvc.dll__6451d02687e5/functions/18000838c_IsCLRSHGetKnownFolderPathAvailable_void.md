# IsCLRSHGetKnownFolderPathAvailable(void)

- ea: `0x18000838c`
- end: `0x1800083de`
- name: `?IsCLRSHGetKnownFolderPathAvailable@@YA_NXZ`
- size: `82`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18002e940`

## callees

- `0x18000838c`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1800083a5`
- `KERNEL32!LoadLibraryExW` at `0x1800083a5`
- `KERNEL32!GetProcAddress` at `0x1800083ba`
- `KERNEL32!GetProcAddress` at `0x1800083ba`

## string_xrefs

- `0x18000839c`: `shell32.dll`
- `0x1800083b0`: `SHGetKnownFolderPath`

## pseudocode

```c
bool IsCLRSHGetKnownFolderPathAvailable(void)
{
  HMODULE Library; // rax

  if ( !bSHGetKnownFolderPathProbed )
  {
    Library = LoadLibraryExW(L"shell32.dll", 0, 0);
    if ( Library )
      qword_18006FFE0 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))GetProcAddress(
                                                                                  Library,
                                                                                  "SHGetKnownFolderPath");
    bSHGetKnownFolderPathProbed = 1;
  }
  return qword_18006FFE0 != 0;
}

```

## disassembly

```asm
0x18000838c  sub     rsp, 28h
0x180008390  cmp     cs:?bSHGetKnownFolderPathProbed@@3_NA, 0; bool bSHGetKnownFolderPathProbed
0x180008397  jnz     short loc_1800083CE
0x180008399  xor     r8d, r8d; dwFlags
0x18000839c  lea     rcx, aShell32Dll; "shell32.dll"
0x1800083a3  xor     edx, edx; hFile
0x1800083a5  call    cs:__imp_LoadLibraryExW
0x1800083ab  test    rax, rax
0x1800083ae  jz      short loc_1800083C7
0x1800083b0  lea     rdx, aShgetknownfold; "SHGetKnownFolderPath"
0x1800083b7  mov     rcx, rax; hModule
0x1800083ba  call    cs:__imp_GetProcAddress
0x1800083c0  mov     cs:qword_18006FFE0, rax
0x1800083c7  mov     cs:?bSHGetKnownFolderPathProbed@@3_NA, 1; bool bSHGetKnownFolderPathProbed
0x1800083ce  cmp     cs:qword_18006FFE0, 0
0x1800083d6  setnz   al
0x1800083d9  add     rsp, 28h
0x1800083dd  retn
```
