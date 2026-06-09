# ShellShim_DllUnregisterServer

- ea: `0x1800242e0`
- end: `0x1800243af`
- name: `ShellShim_DllUnregisterServer`
- size: `207`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180001c10`
- `0x1800242e0`
- `0x18002d34c`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180024335`
- `KERNEL32!GetProcAddress` at `0x18002437c`
- `KERNEL32!GetProcAddress` at `0x180024335`
- `KERNEL32!GetProcAddress` at `0x18002437c`

## string_xrefs

- `0x18002432e`: `DllUnregisterServer_RetAddr`
- `0x180024375`: `DllUnregisterServer`

## pseudocode

```c
HRESULT __stdcall ShellShim_DllUnregisterServer()
{
  int ShimImpl; // eax
  void *retaddr; // [rsp+28h] [rbp+0h]
  HMODULE hModule; // [rsp+30h] [rbp+8h] BYREF

  hModule = 0;
  ShimImpl = GetShimImpl(&hModule);
  if ( ShimImpl == 1 )
    return -2146232575;
  if ( ShimImpl == 3 )
    return DllUnregisterServer();
  if ( g_bShimImplDllUninitialized )
    return -2146232575;
  if ( g_pfDllUnregisterServer_RetAddr == (int (*)(void *))-1LL )
    g_pfDllUnregisterServer_RetAddr = (int (*)(void *))GetProcAddress(hModule, "DllUnregisterServer_RetAddr");
  if ( g_pfDllUnregisterServer_RetAddr )
    return ((__int64 (__fastcall *)(void *))g_pfDllUnregisterServer_RetAddr)(retaddr);
  if ( g_pfDllUnregisterServer == (int (*)(void))-1LL )
    g_pfDllUnregisterServer = (int (*)(void))GetProcAddress(hModule, "DllUnregisterServer");
  if ( !g_pfDllUnregisterServer )
    return -2146232575;
  else
    return g_pfDllUnregisterServer();
}

```

## disassembly

```asm
0x1800242e0  sub     rsp, 28h
0x1800242e4  lea     rcx, [rsp+28h+hModule]
0x1800242e9  mov     [rsp+28h+hModule], 0
0x1800242f2  call    ?GetShimImpl@@YA?AW4ShimImplStatus@@PEAPEAUHINSTANCE__@@@Z; GetShimImpl(HINSTANCE__ * *)
0x1800242f7  cmp     eax, 1
0x1800242fa  jz      loc_1800243A5
0x180024300  cmp     eax, 3
0x180024303  jnz     short loc_18002430E
0x180024305  add     rsp, 28h
0x180024309  jmp     DllUnregisterServer
0x18002430e  mov     eax, cs:?g_bShimImplDllUninitialized@@3HC; int volatile g_bShimImplDllUninitialized
0x180024314  test    eax, eax
0x180024316  jnz     loc_1800243A5
0x18002431c  mov     rax, cs:?g_pfDllUnregisterServer_RetAddr@@3R6AJPEAX@ZEA; long (*g_pfDllUnregisterServer_RetAddr)(void *)
0x180024323  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180024327  jnz     short loc_180024342
0x180024329  mov     rcx, [rsp+28h+hModule]; hModule
0x18002432e  lea     rdx, aDllunregisters_0; "DllUnregisterServer_RetAddr"
0x180024335  call    cs:__imp_GetProcAddress
0x18002433b  mov     cs:?g_pfDllUnregisterServer_RetAddr@@3R6AJPEAX@ZEA, rax; long (*g_pfDllUnregisterServer_RetAddr)(void *)
0x180024342  mov     rax, cs:?g_pfDllUnregisterServer_RetAddr@@3R6AJPEAX@ZEA; long (*g_pfDllUnregisterServer_RetAddr)(void *)
0x180024349  test    rax, rax
0x18002434c  jz      short loc_180024363
0x18002434e  mov     rax, cs:?g_pfDllUnregisterServer_RetAddr@@3R6AJPEAX@ZEA; long (*g_pfDllUnregisterServer_RetAddr)(void *)
0x180024355  mov     rcx, [rsp+28h]
0x18002435a  add     rsp, 28h
0x18002435e  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180024363  mov     rax, cs:?g_pfDllUnregisterServer@@3R6AJXZEA; long (*g_pfDllUnregisterServer)(void)
0x18002436a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002436e  jnz     short loc_180024389
0x180024370  mov     rcx, [rsp+28h+hModule]; hModule
0x180024375  lea     rdx, aDllunregisters_2; "DllUnregisterServer"
0x18002437c  call    cs:__imp_GetProcAddress
0x180024382  mov     cs:?g_pfDllUnregisterServer@@3R6AJXZEA, rax; long (*g_pfDllUnregisterServer)(void)
0x180024389  mov     rax, cs:?g_pfDllUnregisterServer@@3R6AJXZEA; long (*g_pfDllUnregisterServer)(void)
0x180024390  test    rax, rax
0x180024393  jz      short loc_1800243A5
0x180024395  mov     rax, cs:?g_pfDllUnregisterServer@@3R6AJXZEA; long (*g_pfDllUnregisterServer)(void)
0x18002439c  add     rsp, 28h
0x1800243a0  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1800243a5  mov     eax, 80131701h
0x1800243aa  add     rsp, 28h
0x1800243ae  retn
```
