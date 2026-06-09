# ShellShim_CorMarkThreadInThreadPool

- ea: `0x180023f50`
- end: `0x180024008`
- name: `ShellShim_CorMarkThreadInThreadPool`
- size: `184`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180001c10`
- `0x180023f50`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180023f97`
- `KERNEL32!GetProcAddress` at `0x180023fde`
- `KERNEL32!GetProcAddress` at `0x180023f97`
- `KERNEL32!GetProcAddress` at `0x180023fde`

## string_xrefs

- `0x180023f90`: `CorMarkThreadInThreadPool_RetAddr`
- `0x180023fd7`: `CorMarkThreadInThreadPool`

## pseudocode

```c
__int64 ShellShim_CorMarkThreadInThreadPool()
{
  __int64 result; // rax
  void *retaddr; // [rsp+28h] [rbp+0h]
  HMODULE hModule; // [rsp+30h] [rbp+8h] BYREF

  hModule = 0;
  result = GetShimImpl(&hModule);
  if ( (_DWORD)result == 2 )
  {
    result = (unsigned int)g_bShimImplDllUninitialized;
    if ( !g_bShimImplDllUninitialized )
    {
      if ( g_pfCorMarkThreadInThreadPool_RetAddr == (void (*)(void *))-1LL )
        g_pfCorMarkThreadInThreadPool_RetAddr = (void (*)(void *))GetProcAddress(
                                                                    hModule,
                                                                    "CorMarkThreadInThreadPool_RetAddr");
      if ( g_pfCorMarkThreadInThreadPool_RetAddr )
      {
        return ((__int64 (__fastcall *)(void *))g_pfCorMarkThreadInThreadPool_RetAddr)(retaddr);
      }
      else
      {
        if ( g_pfCorMarkThreadInThreadPool == (void (*)(void))-1LL )
          g_pfCorMarkThreadInThreadPool = (void (*)(void))GetProcAddress(hModule, "CorMarkThreadInThreadPool");
        result = (__int64)g_pfCorMarkThreadInThreadPool;
        if ( g_pfCorMarkThreadInThreadPool )
          return ((__int64 (*)(void))g_pfCorMarkThreadInThreadPool)();
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180023f50  sub     rsp, 28h
0x180023f54  lea     rcx, [rsp+28h+hModule]
0x180023f59  mov     [rsp+28h+hModule], 0
0x180023f62  call    ?GetShimImpl@@YA?AW4ShimImplStatus@@PEAPEAUHINSTANCE__@@@Z; GetShimImpl(HINSTANCE__ * *)
0x180023f67  cmp     eax, 2
0x180023f6a  jnz     loc_180024003
0x180023f70  mov     eax, cs:?g_bShimImplDllUninitialized@@3HC; int volatile g_bShimImplDllUninitialized
0x180023f76  test    eax, eax
0x180023f78  jnz     loc_180024003
0x180023f7e  mov     rax, cs:?g_pfCorMarkThreadInThreadPool_RetAddr@@3R6AXPEAX@ZEA; void (*g_pfCorMarkThreadInThreadPool_RetAddr)(void *)
0x180023f85  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180023f89  jnz     short loc_180023FA4
0x180023f8b  mov     rcx, [rsp+28h+hModule]; hModule
0x180023f90  lea     rdx, aCormarkthreadi_0; "CorMarkThreadInThreadPool_RetAddr"
0x180023f97  call    cs:__imp_GetProcAddress
0x180023f9d  mov     cs:?g_pfCorMarkThreadInThreadPool_RetAddr@@3R6AXPEAX@ZEA, rax; void (*g_pfCorMarkThreadInThreadPool_RetAddr)(void *)
0x180023fa4  mov     rax, cs:?g_pfCorMarkThreadInThreadPool_RetAddr@@3R6AXPEAX@ZEA; void (*g_pfCorMarkThreadInThreadPool_RetAddr)(void *)
0x180023fab  test    rax, rax
0x180023fae  jz      short loc_180023FC5
0x180023fb0  mov     rax, cs:?g_pfCorMarkThreadInThreadPool_RetAddr@@3R6AXPEAX@ZEA; void (*g_pfCorMarkThreadInThreadPool_RetAddr)(void *)
0x180023fb7  mov     rcx, [rsp+28h]
0x180023fbc  add     rsp, 28h
0x180023fc0  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180023fc5  mov     rax, cs:?g_pfCorMarkThreadInThreadPool@@3R6AXXZEA; void (*g_pfCorMarkThreadInThreadPool)(void)
0x180023fcc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180023fd0  jnz     short loc_180023FEB
0x180023fd2  mov     rcx, [rsp+28h+hModule]; hModule
0x180023fd7  lea     rdx, aCormarkthreadi_1; "CorMarkThreadInThreadPool"
0x180023fde  call    cs:__imp_GetProcAddress
0x180023fe4  mov     cs:?g_pfCorMarkThreadInThreadPool@@3R6AXXZEA, rax; void (*g_pfCorMarkThreadInThreadPool)(void)
0x180023feb  mov     rax, cs:?g_pfCorMarkThreadInThreadPool@@3R6AXXZEA; void (*g_pfCorMarkThreadInThreadPool)(void)
0x180023ff2  test    rax, rax
0x180023ff5  jz      short loc_180024003
0x180023ff7  mov     rax, cs:?g_pfCorMarkThreadInThreadPool@@3R6AXXZEA; void (*g_pfCorMarkThreadInThreadPool)(void)
0x180023ffe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024003  add     rsp, 28h
0x180024007  retn
```
