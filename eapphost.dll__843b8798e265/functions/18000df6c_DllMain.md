# DllMain

- ea: `0x18000df6c`
- end: `0x18000dfbd`
- name: `DllMain`
- size: `81`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180002964`

## callees

- `0x18000df6c`
- `0x180030724`
- `0x180030770`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000df7f`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000df7f`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  BOOL v3; // ebx

  v3 = 1;
  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      DisableThreadLibraryCalls(hinstDLL);
      return (int)RunTimeInitializer::OnAttach(RunTimeInitializer::initTermFns, 3) >= 0;
    }
  }
  else
  {
    RunTimeInitializer::OnDetach(RunTimeInitializer::initTermFns, 3, lpvReserved);
  }
  return v3;
}

```

## disassembly

```asm
0x18000df6c  push    rbx
0x18000df6e  sub     rsp, 20h
0x18000df72  mov     ebx, 1
0x18000df77  test    edx, edx
0x18000df79  jz      short loc_18000DFA3
0x18000df7b  cmp     edx, ebx
0x18000df7d  jnz     short loc_18000DFB4
0x18000df7f  call    cs:__imp_DisableThreadLibraryCalls
0x18000df86  nop     dword ptr [rax+rax+00h]
0x18000df8b  lea     edx, [rbx+2]
0x18000df8e  lea     rcx, ?initTermFns@RunTimeInitializer@@0QBQ6AJ_N@_EB
0x18000df95  call    ?OnAttach@RunTimeInitializer@@CAJPEBQ6AJ_N@_E_K@Z; RunTimeInitializer::OnAttach(long (*const *)(bool),...)
0x18000df9a  mov     ebx, eax
0x18000df9c  not     ebx
0x18000df9e  shr     ebx, 1Fh
0x18000dfa1  jmp     short loc_18000DFB4
0x18000dfa3  mov     edx, 3
0x18000dfa8  lea     rcx, ?initTermFns@RunTimeInitializer@@0QBQ6AJ_N@_EB
0x18000dfaf  call    ?OnDetach@RunTimeInitializer@@CAXPEBQ6AJ_N@_E_K@Z; RunTimeInitializer::OnDetach(long (*const *)(bool),...)
0x18000dfb4  mov     eax, ebx
0x18000dfb6  add     rsp, 20h
0x18000dfba  pop     rbx
0x18000dfbb  retn
```
