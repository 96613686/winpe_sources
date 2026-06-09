# DllInstall

- ea: `0x180007510`
- end: `0x18000753b`
- name: `DllInstall`
- size: `43`
- prototype: `HRESULT __stdcall(BOOL bInstall, PCWSTR pszCmdLine)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callees

- `0x180007510`
- `0x180007570`
- `0x1800075f0`

## pseudocode

```c
HRESULT __stdcall DllInstall(BOOL bInstall, PCWSTR pszCmdLine)
{
  int v2; // ebx

  if ( !bInstall )
    return DllUnregisterServer();
  v2 = DllRegisterServer();
  if ( v2 < 0 )
    DllUnregisterServer();
  return v2;
}

```

## disassembly

```asm
0x180007510  push    rbx
0x180007512  sub     rsp, 20h
0x180007516  test    ecx, ecx
0x180007518  jz      short loc_18000752C
0x18000751a  call    DllRegisterServer
0x18000751f  mov     ebx, eax
0x180007521  test    eax, eax
0x180007523  jns     short loc_180007533
0x180007525  call    DllUnregisterServer
0x18000752a  jmp     short loc_180007533
0x18000752c  call    DllUnregisterServer
0x180007531  mov     ebx, eax
0x180007533  mov     eax, ebx
0x180007535  add     rsp, 20h
0x180007539  pop     rbx
0x18000753a  retn
```
