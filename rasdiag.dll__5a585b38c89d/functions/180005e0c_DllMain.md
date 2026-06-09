# DllMain

- ea: `0x180005e0c`
- end: `0x180005e3b`
- name: `DllMain`
- size: `47`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001df4`

## callees

- `0x180005e0c`

## import_xrefs

- `KERNEL32!DisableThreadLibraryCalls` at `0x180005e1b`
- `KERNEL32!DisableThreadLibraryCalls` at `0x180005e1b`

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
0x180005e0c  push    rbx
0x180005e0e  sub     rsp, 20h
0x180005e12  mov     ebx, 1
0x180005e17  cmp     edx, ebx
0x180005e19  jnz     short loc_180005E32
0x180005e1b  call    cs:__imp_DisableThreadLibraryCalls
0x180005e22  nop     dword ptr [rax+rax+00h]
0x180005e27  cmp     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 0; bool ATL::CAtlBaseModule::m_bInitFailed
0x180005e2e  jz      short loc_180005E32
0x180005e30  xor     ebx, ebx
0x180005e32  mov     eax, ebx
0x180005e34  add     rsp, 20h
0x180005e38  pop     rbx
0x180005e39  retn
```
