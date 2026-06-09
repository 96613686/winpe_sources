# ShellShim_DllRegisterServer

- ea: `0x180024200`
- end: `0x1800242cf`
- name: `ShellShim_DllRegisterServer`
- size: `207`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180001c10`
- `0x180024200`
- `0x18002d2a8`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180024255`
- `KERNEL32!GetProcAddress` at `0x18002429c`
- `KERNEL32!GetProcAddress` at `0x180024255`
- `KERNEL32!GetProcAddress` at `0x18002429c`

## string_xrefs

- `0x18002424e`: `DllRegisterServer_RetAddr`
- `0x180024295`: `DllRegisterServer`

## pseudocode

```c
HRESULT __stdcall ShellShim_DllRegisterServer()
{
  int ShimImpl; // eax
  void *retaddr; // [rsp+28h] [rbp+0h]
  HMODULE hModule; // [rsp+30h] [rbp+8h] BYREF

  hModule = 0;
  ShimImpl = GetShimImpl(&hModule);
  if ( ShimImpl == 1 )
    return -2146232575;
  if ( ShimImpl == 3 )
    return DllRegisterServer();
  if ( g_bShimImplDllUninitialized )
    return -2146232575;
  if ( g_pfDllRegisterServer_RetAddr == (int (*)(void *))-1LL )
    g_pfDllRegisterServer_RetAddr = (int (*)(void *))GetProcAddress(hModule, "DllRegisterServer_RetAddr");
  if ( g_pfDllRegisterServer_RetAddr )
    return ((__int64 (__fastcall *)(void *))g_pfDllRegisterServer_RetAddr)(retaddr);
  if ( g_pfDllRegisterServer == (int (*)(void))-1LL )
    g_pfDllRegisterServer = (int (*)(void))GetProcAddress(hModule, "DllRegisterServer");
  if ( !g_pfDllRegisterServer )
    return -2146232575;
  else
    return g_pfDllRegisterServer();
}

```

## disassembly

```asm
0x180024200  sub     rsp, 28h
0x180024204  lea     rcx, [rsp+28h+hModule]
0x180024209  mov     [rsp+28h+hModule], 0
0x180024212  call    ?GetShimImpl@@YA?AW4ShimImplStatus@@PEAPEAUHINSTANCE__@@@Z; GetShimImpl(HINSTANCE__ * *)
0x180024217  cmp     eax, 1
0x18002421a  jz      loc_1800242C5
0x180024220  cmp     eax, 3
0x180024223  jnz     short loc_18002422E
0x180024225  add     rsp, 28h
0x180024229  jmp     DllRegisterServer
0x18002422e  mov     eax, cs:?g_bShimImplDllUninitialized@@3HC; int volatile g_bShimImplDllUninitialized
0x180024234  test    eax, eax
0x180024236  jnz     loc_1800242C5
0x18002423c  mov     rax, cs:?g_pfDllRegisterServer_RetAddr@@3R6AJPEAX@ZEA; long (*g_pfDllRegisterServer_RetAddr)(void *)
0x180024243  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180024247  jnz     short loc_180024262
0x180024249  mov     rcx, [rsp+28h+hModule]; hModule
0x18002424e  lea     rdx, aDllregisterser_2; "DllRegisterServer_RetAddr"
0x180024255  call    cs:__imp_GetProcAddress
0x18002425b  mov     cs:?g_pfDllRegisterServer_RetAddr@@3R6AJPEAX@ZEA, rax; long (*g_pfDllRegisterServer_RetAddr)(void *)
0x180024262  mov     rax, cs:?g_pfDllRegisterServer_RetAddr@@3R6AJPEAX@ZEA; long (*g_pfDllRegisterServer_RetAddr)(void *)
0x180024269  test    rax, rax
0x18002426c  jz      short loc_180024283
0x18002426e  mov     rax, cs:?g_pfDllRegisterServer_RetAddr@@3R6AJPEAX@ZEA; long (*g_pfDllRegisterServer_RetAddr)(void *)
0x180024275  mov     rcx, [rsp+28h]
0x18002427a  add     rsp, 28h
0x18002427e  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180024283  mov     rax, cs:?g_pfDllRegisterServer@@3R6AJXZEA; long (*g_pfDllRegisterServer)(void)
0x18002428a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002428e  jnz     short loc_1800242A9
0x180024290  mov     rcx, [rsp+28h+hModule]; hModule
0x180024295  lea     rdx, aDllregisterser_1; "DllRegisterServer"
0x18002429c  call    cs:__imp_GetProcAddress
0x1800242a2  mov     cs:?g_pfDllRegisterServer@@3R6AJXZEA, rax; long (*g_pfDllRegisterServer)(void)
0x1800242a9  mov     rax, cs:?g_pfDllRegisterServer@@3R6AJXZEA; long (*g_pfDllRegisterServer)(void)
0x1800242b0  test    rax, rax
0x1800242b3  jz      short loc_1800242C5
0x1800242b5  mov     rax, cs:?g_pfDllRegisterServer@@3R6AJXZEA; long (*g_pfDllRegisterServer)(void)
0x1800242bc  add     rsp, 28h
0x1800242c0  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1800242c5  mov     eax, 80131701h
0x1800242ca  add     rsp, 28h
0x1800242ce  retn
```
