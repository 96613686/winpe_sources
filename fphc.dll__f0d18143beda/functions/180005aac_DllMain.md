# DllMain

- ea: `0x180005aac`
- end: `0x180005ad4`
- name: `DllMain`
- size: `40`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001e64`

## callees

- `0x180005aac`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180005abb`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180005abb`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  BOOL v3; // ebx

  v3 = 1;
  if ( fdwReason == 1 )
  {
    DisableThreadLibraryCalls(hinstDLL);
    return !ATL::CAtlBaseModule::m_bInitFailed;
  }
  return v3;
}

```

## disassembly

```asm
0x180005aac  push    rbx
0x180005aae  sub     rsp, 20h
0x180005ab2  mov     ebx, 1
0x180005ab7  cmp     edx, ebx
0x180005ab9  jnz     short loc_180005ACC
0x180005abb  call    cs:__imp_DisableThreadLibraryCalls
0x180005ac1  cmp     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 0; bool ATL::CAtlBaseModule::m_bInitFailed
0x180005ac8  jz      short loc_180005ACC
0x180005aca  xor     ebx, ebx
0x180005acc  mov     eax, ebx
0x180005ace  add     rsp, 20h
0x180005ad2  pop     rbx
0x180005ad3  retn
```
