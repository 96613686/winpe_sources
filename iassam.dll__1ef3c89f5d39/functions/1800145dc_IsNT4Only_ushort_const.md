# IsNT4Only(ushort const *)

- ea: `0x1800145dc`
- end: `0x1800145ff`
- name: `?IsNT4Only@@YA?B_NPEBG@Z`
- size: `35`
- prototype: `bool __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001224c`
- `0x180012c74`

## callees

- `0x1800145b0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800145ef`
- `msvcrt!_wcsicmp` at `0x1800145ef`

## string_xrefs

- `0x1800145e8`: `AUTHSAM.DLL`

## pseudocode

```c
bool __fastcall IsNT4Only(const unsigned __int16 *a1)
{
  const wchar_t *FileNameFromPath; // rax

  FileNameFromPath = ExtractFileNameFromPath(a1);
  return _wcsicmp(FileNameFromPath, L"AUTHSAM.DLL") == 0;
}

```

## disassembly

```asm
0x1800145dc  sub     rsp, 28h
0x1800145e0  call    ?ExtractFileNameFromPath@@YAPEBGPEBG@Z; ExtractFileNameFromPath(ushort const *)
0x1800145e5  mov     rcx, rax; String1
0x1800145e8  lea     rdx, aAuthsamDll; "AUTHSAM.DLL"
0x1800145ef  call    cs:__imp__wcsicmp
0x1800145f5  test    eax, eax
0x1800145f7  setz    al
0x1800145fa  add     rsp, 28h
0x1800145fe  retn
```
