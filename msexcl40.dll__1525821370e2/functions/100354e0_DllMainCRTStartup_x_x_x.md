# _DllMainCRTStartup(x,x,x)

- ea: `0x100354e0`
- end: `0x10035505`
- name: `__DllMainCRTStartup@12`
- size: `37`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x10035398`
- `0x100354e0`
- `0x1003597d`

## pseudocode

```c
BOOL __stdcall _DllMainCRTStartup(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
    __security_init_cookie();
  return dllmain_dispatch(hinstDLL, fdwReason, lpReserved);
}

```

## disassembly

```asm
0x100354e0  mov     edi, edi
0x100354e2  push    ebp
0x100354e3  mov     ebp, esp
0x100354e5  cmp     [ebp+fdwReason], 1
0x100354e9  jnz     short loc_100354F0
0x100354eb  call    ___security_init_cookie
0x100354f0  push    [ebp+lpReserved]; lpvReserved
0x100354f3  push    [ebp+fdwReason]; fdwReason
0x100354f6  push    [ebp+hinstDLL]; hinstDLL
0x100354f9  call    dllmain_dispatch
0x100354fe  add     esp, 0Ch
0x10035501  pop     ebp
0x10035502  retn    0Ch
```
