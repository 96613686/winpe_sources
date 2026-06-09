# DllMain

- ea: `0x18000a5dc`
- end: `0x18000a605`
- name: `DllMain`
- size: `41`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180004654`

## callees

- `0x180002a80`
- `0x180002bb0`
- `0x18000a5dc`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  if ( fdwReason )
  {
    if ( fdwReason == 1 )
      return (unsigned __int8)CModule::Init((CModule *)hinstDLL, hinstDLL);
  }
  else
  {
    CModule::Uninit((CModule *)hinstDLL);
  }
  return 1;
}

```

## disassembly

```asm
0x18000a5dc  sub     rsp, 28h
0x18000a5e0  test    edx, edx
0x18000a5e2  jz      short loc_18000A5F6
0x18000a5e4  cmp     edx, 1
0x18000a5e7  jnz     short loc_18000A5FB
0x18000a5e9  mov     rdx, rcx; HINSTANCE
0x18000a5ec  call    ?Init@CModule@@QEAA_NPEAUHINSTANCE__@@@Z; CModule::Init(HINSTANCE__ *)
0x18000a5f1  movzx   eax, al
0x18000a5f4  jmp     short loc_18000A600
0x18000a5f6  call    ?Uninit@CModule@@QEAAXXZ; CModule::Uninit(void)
0x18000a5fb  mov     eax, 1
0x18000a600  add     rsp, 28h
0x18000a604  retn
```
