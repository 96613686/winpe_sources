# UnLoadInternationalDLL

- ea: `0x100249b2`
- end: `0x100249d7`
- name: `UnLoadInternationalDLL`
- size: `37`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x10024d8e`

## callees

- `0x100249b2`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x100249bc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x100249bc`

## pseudocode

```c
HMODULE UnLoadInternationalDLL()
{
  HMODULE result; // eax

  result = dword_1003AE54;
  if ( dword_1003AE54 )
  {
    result = (HMODULE)FreeLibrary(dword_1003AE54);
    dword_1003AE54 = 0;
    CchLszOfId2 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x100249b2  mov     eax, dword_1003AE54
0x100249b7  test    eax, eax
0x100249b9  jz      short locret_100249D6
0x100249bb  push    eax; hLibModule
0x100249bc  call    ds:__imp__FreeLibrary@4; FreeLibrary(x)
0x100249c2  mov     dword_1003AE54, 0
0x100249cc  mov     CchLszOfId2, 0
0x100249d6  retn
```
