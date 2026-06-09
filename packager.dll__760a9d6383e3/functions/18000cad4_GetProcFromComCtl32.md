# _GetProcFromComCtl32

- ea: `0x18000cad4`
- end: `0x18000cb12`
- name: `_GetProcFromComCtl32`
- size: `62`
- prototype: `FARPROC()`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ca58`

## callees

- `0x18000ca08`
- `0x18000cad4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000cb00`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000cb00`

## pseudocode

```c
FARPROC GetProcFromComCtl32()
{
  HMODULE v0; // rcx
  FARPROC result; // rax

  v0 = g_hinstCC;
  if ( g_hinstCC || (DelayLoadCC(), (v0 = g_hinstCC) != 0) )
    result = GetProcAddress(v0, "PropertySheetW");
  else
    result = 0;
  qword_1800140E0 = (__int64)result;
  return result;
}

```

## disassembly

```asm
0x18000cad4  sub     rsp, 28h
0x18000cad8  mov     rcx, cs:g_hinstCC; hModule
0x18000cadf  test    rcx, rcx
0x18000cae2  jnz     short loc_18000CAF9
0x18000cae4  call    DelayLoadCC
0x18000cae9  mov     rcx, cs:g_hinstCC
0x18000caf0  test    rcx, rcx
0x18000caf3  jnz     short loc_18000CAF9
0x18000caf5  xor     eax, eax
0x18000caf7  jmp     short loc_18000CB06
0x18000caf9  lea     rdx, aPropertysheetw; "PropertySheetW"
0x18000cb00  call    cs:__imp_GetProcAddress
0x18000cb06  mov     cs:qword_1800140E0, rax
0x18000cb0d  add     rsp, 28h
0x18000cb11  retn
```
