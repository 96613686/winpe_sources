# ShellShim_GetCompileInfo

- ea: `0x180024820`
- end: `0x180024928`
- name: `ShellShim_GetCompileInfo`
- size: `264`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001c10`
- `0x180024820`
- `0x18002a230`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180024874`
- `KERNEL32!GetProcAddress` at `0x1800248b4`
- `KERNEL32!GetProcAddress` at `0x1800248fb`
- `KERNEL32!GetProcAddress` at `0x180024874`
- `KERNEL32!GetProcAddress` at `0x1800248b4`
- `KERNEL32!GetProcAddress` at `0x1800248fb`

## string_xrefs

- `0x1800248ad`: `GetCompileInfo_RetAddr`
- `0x18002486d`: `GetCompileInfo`
- `0x1800248f4`: `GetCompileInfo`

## pseudocode

```c
__int64 ShellShim_GetCompileInfo()
{
  int ShimImpl; // eax
  struct ICorCompileInfo *(*ProcAddress)(void); // rax
  void *retaddr; // [rsp+28h] [rbp+0h]
  HMODULE hModule; // [rsp+30h] [rbp+8h] BYREF

  hModule = 0;
  ShimImpl = GetShimImpl(&hModule);
  if ( ShimImpl == 1 )
    return 0;
  if ( ShimImpl == 3 )
  {
    ProcAddress = g_GetCompileInfo;
    if ( !g_GetCompileInfo )
    {
      hModule = 0;
      if ( (int)GetRealDll(&hModule, 1) < 0 )
        return 0;
      ProcAddress = (struct ICorCompileInfo *(*)(void))GetProcAddress(hModule, "GetCompileInfo");
      g_GetCompileInfo = ProcAddress;
      if ( !ProcAddress )
        return 0;
    }
  }
  else
  {
    if ( g_bShimImplDllUninitialized )
      return 0;
    if ( g_pfGetCompileInfo_RetAddr == (struct ICorCompileInfo *(*)(void *))-1LL )
      g_pfGetCompileInfo_RetAddr = (struct ICorCompileInfo *(*)(void *))GetProcAddress(
                                                                          hModule,
                                                                          "GetCompileInfo_RetAddr");
    if ( g_pfGetCompileInfo_RetAddr )
      return ((__int64 (__fastcall *)(void *))g_pfGetCompileInfo_RetAddr)(retaddr);
    if ( g_pfGetCompileInfo == (struct ICorCompileInfo *(*)(void))-1LL )
      g_pfGetCompileInfo = (struct ICorCompileInfo *(*)(void))GetProcAddress(hModule, "GetCompileInfo");
    if ( !g_pfGetCompileInfo )
      return 0;
    ProcAddress = g_pfGetCompileInfo;
  }
  return (__int64)ProcAddress();
}

```

## disassembly

```asm
0x180024820  sub     rsp, 28h
0x180024824  lea     rcx, [rsp+28h+hModule]
0x180024829  mov     [rsp+28h+hModule], 0
0x180024832  call    ?GetShimImpl@@YA?AW4ShimImplStatus@@PEAPEAUHINSTANCE__@@@Z; GetShimImpl(HINSTANCE__ * *)
0x180024837  mov     edx, 1; int
0x18002483c  cmp     eax, edx
0x18002483e  jz      short loc_18002488A
0x180024840  cmp     eax, 3
0x180024843  jnz     short loc_180024891
0x180024845  mov     rax, cs:?g_GetCompileInfo@@3P6APEAVICorCompileInfo@@XZEA; ICorCompileInfo * (*g_GetCompileInfo)(void)
0x18002484c  test    rax, rax
0x18002484f  jnz     loc_18002491F
0x180024855  lea     rcx, [rsp+28h+hModule]; HINSTANCE *
0x18002485a  mov     [rsp+28h+hModule], rax
0x18002485f  call    ?GetRealDll@@YAJPEAPEAUHINSTANCE__@@H@Z; GetRealDll(HINSTANCE__ * *,int)
0x180024864  test    eax, eax
0x180024866  js      short loc_18002488A
0x180024868  mov     rcx, [rsp+28h+hModule]; hModule
0x18002486d  lea     rdx, aGetcompileinfo_0; "GetCompileInfo"
0x180024874  call    cs:__imp_GetProcAddress
0x18002487a  mov     cs:?g_GetCompileInfo@@3P6APEAVICorCompileInfo@@XZEA, rax; ICorCompileInfo * (*g_GetCompileInfo)(void)
0x180024881  test    rax, rax
0x180024884  jnz     loc_18002491F
0x18002488a  xor     eax, eax
0x18002488c  add     rsp, 28h
0x180024890  retn
0x180024891  mov     eax, cs:?g_bShimImplDllUninitialized@@3HC; int volatile g_bShimImplDllUninitialized
0x180024897  test    eax, eax
0x180024899  jnz     short loc_18002488A
0x18002489b  mov     rax, cs:?g_pfGetCompileInfo_RetAddr@@3R6APEAVICorCompileInfo@@PEAX@ZEA; ICorCompileInfo * (*g_pfGetCompileInfo_RetAddr)(void *)
0x1800248a2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800248a6  jnz     short loc_1800248C1
0x1800248a8  mov     rcx, [rsp+28h+hModule]; hModule
0x1800248ad  lea     rdx, aGetcompileinfo_1; "GetCompileInfo_RetAddr"
0x1800248b4  call    cs:__imp_GetProcAddress
0x1800248ba  mov     cs:?g_pfGetCompileInfo_RetAddr@@3R6APEAVICorCompileInfo@@PEAX@ZEA, rax; ICorCompileInfo * (*g_pfGetCompileInfo_RetAddr)(void *)
0x1800248c1  mov     rax, cs:?g_pfGetCompileInfo_RetAddr@@3R6APEAVICorCompileInfo@@PEAX@ZEA; ICorCompileInfo * (*g_pfGetCompileInfo_RetAddr)(void *)
0x1800248c8  test    rax, rax
0x1800248cb  jz      short loc_1800248E2
0x1800248cd  mov     rax, cs:?g_pfGetCompileInfo_RetAddr@@3R6APEAVICorCompileInfo@@PEAX@ZEA; ICorCompileInfo * (*g_pfGetCompileInfo_RetAddr)(void *)
0x1800248d4  mov     rcx, [rsp+28h]
0x1800248d9  add     rsp, 28h
0x1800248dd  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1800248e2  mov     rax, cs:?g_pfGetCompileInfo@@3R6APEAVICorCompileInfo@@XZEA; ICorCompileInfo * (*g_pfGetCompileInfo)(void)
0x1800248e9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800248ed  jnz     short loc_180024908
0x1800248ef  mov     rcx, [rsp+28h+hModule]; hModule
0x1800248f4  lea     rdx, aGetcompileinfo_0; "GetCompileInfo"
0x1800248fb  call    cs:__imp_GetProcAddress
0x180024901  mov     cs:?g_pfGetCompileInfo@@3R6APEAVICorCompileInfo@@XZEA, rax; ICorCompileInfo * (*g_pfGetCompileInfo)(void)
0x180024908  mov     rax, cs:?g_pfGetCompileInfo@@3R6APEAVICorCompileInfo@@XZEA; ICorCompileInfo * (*g_pfGetCompileInfo)(void)
0x18002490f  test    rax, rax
0x180024912  jz      loc_18002488A
0x180024918  mov     rax, cs:?g_pfGetCompileInfo@@3R6APEAVICorCompileInfo@@XZEA; ICorCompileInfo * (*g_pfGetCompileInfo)(void)
0x18002491f  add     rsp, 28h
0x180024923  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
