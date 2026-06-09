# ShellShim_CoEEShutDownCOM

- ea: `0x180023550`
- end: `0x18002365e`
- name: `ShellShim_CoEEShutDownCOM`
- size: `270`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001c10`
- `0x180023550`
- `0x18002a230`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800235a2`
- `KERNEL32!GetProcAddress` at `0x1800235ed`
- `KERNEL32!GetProcAddress` at `0x180023634`
- `KERNEL32!GetProcAddress` at `0x1800235a2`
- `KERNEL32!GetProcAddress` at `0x1800235ed`
- `KERNEL32!GetProcAddress` at `0x180023634`

## string_xrefs

- `0x1800235e6`: `CoEEShutDownCOM_RetAddr`
- `0x18002359b`: `CoEEShutDownCOM`
- `0x18002362d`: `CoEEShutDownCOM`

## pseudocode

```c
__int64 ShellShim_CoEEShutDownCOM()
{
  __int64 result; // rax
  void *retaddr; // [rsp+28h] [rbp+0h]
  HMODULE hModule; // [rsp+30h] [rbp+8h] BYREF

  hModule = 0;
  result = GetShimImpl(&hModule);
  if ( (_DWORD)result == 3 )
  {
    result = (__int64)g_CoEEShutDownCOM;
    if ( g_CoEEShutDownCOM )
      return ((__int64 (*)(void))result)();
    hModule = 0;
    result = GetRealDll(&hModule, 1);
    if ( (int)result >= 0 )
    {
      result = (__int64)GetProcAddress(hModule, "CoEEShutDownCOM");
      g_CoEEShutDownCOM = (void (*)(void))result;
      if ( result )
        return ((__int64 (*)(void))result)();
    }
  }
  else if ( (_DWORD)result == 2 )
  {
    result = (unsigned int)g_bShimImplDllUninitialized;
    if ( !g_bShimImplDllUninitialized )
    {
      if ( g_pfCoEEShutDownCOM_RetAddr == (void (*)(void *))-1LL )
        g_pfCoEEShutDownCOM_RetAddr = (void (*)(void *))GetProcAddress(hModule, "CoEEShutDownCOM_RetAddr");
      if ( g_pfCoEEShutDownCOM_RetAddr )
        return ((__int64 (__fastcall *)(void *))g_pfCoEEShutDownCOM_RetAddr)(retaddr);
      if ( g_pfCoEEShutDownCOM == (void (*)(void))-1LL )
        g_pfCoEEShutDownCOM = (void (*)(void))GetProcAddress(hModule, "CoEEShutDownCOM");
      result = (__int64)g_pfCoEEShutDownCOM;
      if ( g_pfCoEEShutDownCOM )
      {
        result = (__int64)g_pfCoEEShutDownCOM;
        return ((__int64 (*)(void))result)();
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180023550  sub     rsp, 28h
0x180023554  lea     rcx, [rsp+28h+hModule]
0x180023559  mov     [rsp+28h+hModule], 0
0x180023562  call    ?GetShimImpl@@YA?AW4ShimImplStatus@@PEAPEAUHINSTANCE__@@@Z; GetShimImpl(HINSTANCE__ * *)
0x180023567  cmp     eax, 3
0x18002356a  jnz     short loc_1800235BD
0x18002356c  mov     rax, cs:?g_CoEEShutDownCOM@@3P6AXXZEA; void (*g_CoEEShutDownCOM)(void)
0x180023573  test    rax, rax
0x180023576  jnz     loc_180023654
0x18002357c  lea     edx, [rax+1]; int
0x18002357f  mov     [rsp+28h+hModule], rax
0x180023584  lea     rcx, [rsp+28h+hModule]; HINSTANCE *
0x180023589  call    ?GetRealDll@@YAJPEAPEAUHINSTANCE__@@H@Z; GetRealDll(HINSTANCE__ * *,int)
0x18002358e  test    eax, eax
0x180023590  js      loc_180023659
0x180023596  mov     rcx, [rsp+28h+hModule]; hModule
0x18002359b  lea     rdx, aCoeeshutdownco_0; "CoEEShutDownCOM"
0x1800235a2  call    cs:__imp_GetProcAddress
0x1800235a8  mov     cs:?g_CoEEShutDownCOM@@3P6AXXZEA, rax; void (*g_CoEEShutDownCOM)(void)
0x1800235af  test    rax, rax
0x1800235b2  jz      loc_180023659
0x1800235b8  jmp     loc_180023654
0x1800235bd  cmp     eax, 2
0x1800235c0  jnz     loc_180023659
0x1800235c6  mov     eax, cs:?g_bShimImplDllUninitialized@@3HC; int volatile g_bShimImplDllUninitialized
0x1800235cc  test    eax, eax
0x1800235ce  jnz     loc_180023659
0x1800235d4  mov     rax, cs:?g_pfCoEEShutDownCOM_RetAddr@@3R6AXPEAX@ZEA; void (*g_pfCoEEShutDownCOM_RetAddr)(void *)
0x1800235db  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800235df  jnz     short loc_1800235FA
0x1800235e1  mov     rcx, [rsp+28h+hModule]; hModule
0x1800235e6  lea     rdx, aCoeeshutdownco_1; "CoEEShutDownCOM_RetAddr"
0x1800235ed  call    cs:__imp_GetProcAddress
0x1800235f3  mov     cs:?g_pfCoEEShutDownCOM_RetAddr@@3R6AXPEAX@ZEA, rax; void (*g_pfCoEEShutDownCOM_RetAddr)(void *)
0x1800235fa  mov     rax, cs:?g_pfCoEEShutDownCOM_RetAddr@@3R6AXPEAX@ZEA; void (*g_pfCoEEShutDownCOM_RetAddr)(void *)
0x180023601  test    rax, rax
0x180023604  jz      short loc_18002361B
0x180023606  mov     rax, cs:?g_pfCoEEShutDownCOM_RetAddr@@3R6AXPEAX@ZEA; void (*g_pfCoEEShutDownCOM_RetAddr)(void *)
0x18002360d  mov     rcx, [rsp+28h]
0x180023612  add     rsp, 28h
0x180023616  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18002361b  mov     rax, cs:?g_pfCoEEShutDownCOM@@3R6AXXZEA; void (*g_pfCoEEShutDownCOM)(void)
0x180023622  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180023626  jnz     short loc_180023641
0x180023628  mov     rcx, [rsp+28h+hModule]; hModule
0x18002362d  lea     rdx, aCoeeshutdownco_0; "CoEEShutDownCOM"
0x180023634  call    cs:__imp_GetProcAddress
0x18002363a  mov     cs:?g_pfCoEEShutDownCOM@@3R6AXXZEA, rax; void (*g_pfCoEEShutDownCOM)(void)
0x180023641  mov     rax, cs:?g_pfCoEEShutDownCOM@@3R6AXXZEA; void (*g_pfCoEEShutDownCOM)(void)
0x180023648  test    rax, rax
0x18002364b  jz      short loc_180023659
0x18002364d  mov     rax, cs:?g_pfCoEEShutDownCOM@@3R6AXXZEA; void (*g_pfCoEEShutDownCOM)(void)
0x180023654  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023659  add     rsp, 28h
0x18002365d  retn
```
