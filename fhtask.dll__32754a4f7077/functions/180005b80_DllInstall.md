# DllInstall

- ea: `0x180005b80`
- end: `0x180005bab`
- name: `DllInstall`
- size: `43`
- prototype: `HRESULT __stdcall(BOOL bInstall, PCWSTR pszCmdLine)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callees

- `0x180005b80`
- `0x180005d30`
- `0x180005df0`

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
0x180005b80  push    rbx
0x180005b82  sub     rsp, 20h
0x180005b86  test    ecx, ecx
0x180005b88  jz      short loc_180005B9C
0x180005b8a  call    DllRegisterServer
0x180005b8f  mov     ebx, eax
0x180005b91  test    eax, eax
0x180005b93  jns     short loc_180005BA3
0x180005b95  call    DllUnregisterServer
0x180005b9a  jmp     short loc_180005BA3
0x180005b9c  call    DllUnregisterServer
0x180005ba1  mov     ebx, eax
0x180005ba3  mov     eax, ebx
0x180005ba5  add     rsp, 20h
0x180005ba9  pop     rbx
0x180005baa  retn
```
