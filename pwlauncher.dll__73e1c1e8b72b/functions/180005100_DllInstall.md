# DllInstall

- ea: `0x180005100`
- end: `0x18000512b`
- name: `DllInstall`
- size: `43`
- prototype: `HRESULT __stdcall(BOOL bInstall, PCWSTR pszCmdLine)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callees

- `0x180005100`
- `0x1800052b0`
- `0x1800053e0`

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
0x180005100  push    rbx
0x180005102  sub     rsp, 20h
0x180005106  test    ecx, ecx
0x180005108  jz      short loc_18000511C
0x18000510a  call    DllRegisterServer
0x18000510f  mov     ebx, eax
0x180005111  test    eax, eax
0x180005113  jns     short loc_180005123
0x180005115  call    DllUnregisterServer
0x18000511a  jmp     short loc_180005123
0x18000511c  call    DllUnregisterServer
0x180005121  mov     ebx, eax
0x180005123  mov     eax, ebx
0x180005125  add     rsp, 20h
0x180005129  pop     rbx
0x18000512a  retn
```
