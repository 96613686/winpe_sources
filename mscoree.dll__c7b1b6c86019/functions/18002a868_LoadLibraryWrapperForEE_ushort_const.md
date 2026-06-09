# LoadLibraryWrapperForEE(ushort const *)

- ea: `0x18002a868`
- end: `0x18002a8ad`
- name: `?LoadLibraryWrapperForEE@@YAPEAUHINSTANCE__@@PEBG@Z`
- size: `69`
- prototype: `HINSTANCE __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180029b70`

## callees

- `0x180005250`
- `0x18002a868`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18002a874`
- `KERNEL32!LoadLibraryExW` at `0x18002a874`

## pseudocode

```c
HINSTANCE __fastcall LoadLibraryWrapperForEE(const unsigned __int16 *a1)
{
  HMODULE Library; // rax
  HMODULE v2; // rbx
  struct ModuleList *i; // rcx

  Library = LoadLibraryExW(a1, 0, 8u);
  v2 = Library;
  if ( Library )
  {
    for ( i = g_pLoadedModules; i; i = (struct ModuleList *)*((_QWORD *)i + 1) )
    {
      if ( *(HMODULE *)i == Library )
        return v2;
    }
    AddModule(Library, g_pLoadedModules);
  }
  return v2;
}

```

## disassembly

```asm
0x18002a868  push    rbx
0x18002a86a  sub     rsp, 20h
0x18002a86e  xor     edx, edx; hFile
0x18002a870  lea     r8d, [rdx+8]; dwFlags
0x18002a874  call    cs:__imp_LoadLibraryExW
0x18002a87a  mov     rbx, rax
0x18002a87d  test    rax, rax
0x18002a880  jz      short loc_18002A8A4
0x18002a882  mov     rdx, cs:?g_pLoadedModules@@3PEAUModuleList@@EA; struct ModuleList *
0x18002a889  mov     rcx, rdx
0x18002a88c  test    rcx, rcx
0x18002a88f  jz      short loc_18002A89C
0x18002a891  cmp     [rcx], rbx
0x18002a894  jz      short loc_18002A8A4
0x18002a896  mov     rcx, [rcx+8]
0x18002a89a  jmp     short loc_18002A88C
0x18002a89c  mov     rcx, rbx; HINSTANCE
0x18002a89f  call    ?AddModule@@YAJPEAUHINSTANCE__@@PEAUModuleList@@@Z; AddModule(HINSTANCE__ *,ModuleList *)
0x18002a8a4  mov     rax, rbx
0x18002a8a7  add     rsp, 20h
0x18002a8ab  pop     rbx
0x18002a8ac  retn
```
