# DllInstall

- ea: `0x180002ac0`
- end: `0x180002aeb`
- name: `DllInstall`
- size: `43`
- prototype: `HRESULT __stdcall(BOOL bInstall, PCWSTR pszCmdLine)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callees

- `0x180002ac0`
- `0x180002c70`
- `0x180002d30`

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
0x180002ac0  push    rbx
0x180002ac2  sub     rsp, 20h
0x180002ac6  test    ecx, ecx
0x180002ac8  jz      short loc_180002ADC
0x180002aca  call    DllRegisterServer
0x180002acf  mov     ebx, eax
0x180002ad1  test    eax, eax
0x180002ad3  jns     short loc_180002AE3
0x180002ad5  call    DllUnregisterServer
0x180002ada  jmp     short loc_180002AE3
0x180002adc  call    DllUnregisterServer
0x180002ae1  mov     ebx, eax
0x180002ae3  mov     eax, ebx
0x180002ae5  add     rsp, 20h
0x180002ae9  pop     rbx
0x180002aea  retn
```
