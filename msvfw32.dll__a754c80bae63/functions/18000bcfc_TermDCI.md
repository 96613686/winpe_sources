# TermDCI

- ea: `0x18000bcfc`
- end: `0x18000bd7b`
- name: `TermDCI`
- size: `127`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180001010`
- `0x180009b30`
- `0x18000ab84`

## callees

- `0x18000bcfc`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000bd5b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000bd5b`

## pseudocode

```c
int TermDCI()
{
  int result; // eax

  if ( pdci )
  {
    result = ((__int64 (*)(void))pfnDCIDestroy)();
    pdci = 0;
  }
  if ( hdcDCI )
  {
    result = ((__int64 (*)(void))pfnDCICloseProvider)();
    hdcDCI = 0;
  }
  if ( hLibModule )
  {
    if ( !--dword_180023DA8 )
    {
      result = FreeLibrary(hLibModule);
      dword_180023D94 = 0;
      hLibModule = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000bcfc  sub     rsp, 28h
0x18000bd00  mov     rcx, cs:pdci
0x18000bd07  test    rcx, rcx
0x18000bd0a  jz      short loc_18000BD23
0x18000bd0c  mov     rax, cs:pfnDCIDestroy
0x18000bd13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd18  mov     cs:pdci, 0
0x18000bd23  mov     rcx, cs:hdcDCI
0x18000bd2a  test    rcx, rcx
0x18000bd2d  jz      short loc_18000BD46
0x18000bd2f  mov     rax, cs:pfnDCICloseProvider
0x18000bd36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd3b  mov     cs:hdcDCI, 0
0x18000bd46  mov     rcx, cs:hLibModule; hLibModule
0x18000bd4d  test    rcx, rcx
0x18000bd50  jz      short loc_18000BD76
0x18000bd52  add     cs:dword_180023DA8, 0FFFFFFFFh
0x18000bd59  jnz     short loc_18000BD76
0x18000bd5b  call    cs:__imp_FreeLibrary
0x18000bd61  mov     cs:dword_180023D94, 0
0x18000bd6b  mov     cs:hLibModule, 0
0x18000bd76  add     rsp, 28h
0x18000bd7a  retn
```
