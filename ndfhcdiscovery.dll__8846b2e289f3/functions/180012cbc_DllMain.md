# DllMain

- ea: `0x180012cbc`
- end: `0x180012d12`
- name: `DllMain`
- size: `86`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180001834`

## callees

- `0x180012cbc`
- `0x180013058`
- `0x180013098`

## import_xrefs

- `KERNEL32!DisableThreadLibraryCalls` at `0x180012ce6`
- `KERNEL32!DisableThreadLibraryCalls` at `0x180012ce6`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  BOOL v4; // ebx

  v4 = 1;
  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      McGenEventRegister_EventRegister(hinstDLL, 1, lpvReserved);
      DisableThreadLibraryCalls(hinstDLL);
      return !ATL::CAtlBaseModule::m_bInitFailed;
    }
  }
  else
  {
    McGenEventUnregister_EventUnregister(hinstDLL, 0, lpvReserved);
  }
  return v4;
}

```

## disassembly

```asm
0x180012cbc  mov     [rsp+arg_0], rbx
0x180012cc1  push    rdi
0x180012cc2  sub     rsp, 20h
0x180012cc6  mov     rdi, rcx
0x180012cc9  mov     eax, edx
0x180012ccb  mov     ebx, 1
0x180012cd0  test    edx, edx
0x180012cd2  jz      short loc_180012CFF
0x180012cd4  cmp     eax, ebx
0x180012cd6  jz      short loc_180012CDE
0x180012cd8  cmp     edx, ebx
0x180012cda  jnz     short loc_180012D04
0x180012cdc  jmp     short loc_180012CF2
0x180012cde  call    McGenEventRegister_EventRegister
0x180012ce3  mov     rcx, rdi; hLibModule
0x180012ce6  call    cs:__imp_DisableThreadLibraryCalls
0x180012ced  nop     dword ptr [rax+rax+00h]
0x180012cf2  cmp     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 0; bool ATL::CAtlBaseModule::m_bInitFailed
0x180012cf9  jz      short loc_180012D04
0x180012cfb  xor     ebx, ebx
0x180012cfd  jmp     short loc_180012D04
0x180012cff  call    McGenEventUnregister_EventUnregister
0x180012d04  mov     eax, ebx
0x180012d06  mov     rbx, [rsp+28h+arg_0]
0x180012d0b  add     rsp, 20h
0x180012d0f  pop     rdi
0x180012d10  retn
```
