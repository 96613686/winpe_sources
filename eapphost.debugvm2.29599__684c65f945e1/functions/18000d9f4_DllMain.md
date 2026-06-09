# DllMain

- ea: `0x18000d9f4`
- end: `0x18000da3e`
- name: `DllMain`
- size: `74`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180002904`

## callees

- `0x18000d9f4`
- `0x18002f594`
- `0x18002f5e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000da07`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000da07`

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
0x18000d9f4  push    rbx
0x18000d9f6  sub     rsp, 20h
0x18000d9fa  mov     ebx, 1
0x18000d9ff  test    edx, edx
0x18000da01  jz      short loc_18000DA25
0x18000da03  cmp     edx, ebx
0x18000da05  jnz     short loc_18000DA36
0x18000da07  call    cs:__imp_DisableThreadLibraryCalls
0x18000da0d  lea     edx, [rbx+2]
0x18000da10  lea     rcx, ?initTermFns@RunTimeInitializer@@0QBQ6AJ_N@_EB
0x18000da17  call    ?OnAttach@RunTimeInitializer@@CAJPEBQ6AJ_N@_E_K@Z; RunTimeInitializer::OnAttach(long (*const *)(bool),...)
0x18000da1c  mov     ebx, eax
0x18000da1e  not     ebx
0x18000da20  shr     ebx, 1Fh
0x18000da23  jmp     short loc_18000DA36
0x18000da25  mov     edx, 3
0x18000da2a  lea     rcx, ?initTermFns@RunTimeInitializer@@0QBQ6AJ_N@_EB
0x18000da31  call    ?OnDetach@RunTimeInitializer@@CAXPEBQ6AJ_N@_E_K@Z; RunTimeInitializer::OnDetach(long (*const *)(bool),...)
0x18000da36  mov     eax, ebx
0x18000da38  add     rsp, 20h
0x18000da3c  pop     rbx
0x18000da3d  retn
```
