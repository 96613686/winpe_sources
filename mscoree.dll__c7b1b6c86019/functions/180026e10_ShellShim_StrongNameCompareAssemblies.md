# ShellShim_StrongNameCompareAssemblies

- ea: `0x180026e10`
- end: `0x180026f52`
- name: `ShellShim_StrongNameCompareAssemblies`
- size: `322`
- prototype: `BOOLEAN __stdcall(LPCWSTR wszAssembly1, LPCWSTR wszAssembly2, DWORD *pdwResult)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001c10`
- `0x180026e10`
- `0x18002a2e4`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180026e86`
- `KERNEL32!GetProcAddress` at `0x180026ecd`
- `KERNEL32!GetProcAddress` at `0x180026f1b`
- `KERNEL32!GetProcAddress` at `0x180026e86`
- `KERNEL32!GetProcAddress` at `0x180026ecd`
- `KERNEL32!GetProcAddress` at `0x180026f1b`

## string_xrefs

- `0x180026ec6`: `StrongNameCompareAssemblies_RetAddr`
- `0x180026e7f`: `StrongNameCompareAssemblies`
- `0x180026f14`: `StrongNameCompareAssemblies`

## pseudocode

```c
BOOLEAN __stdcall ShellShim_StrongNameCompareAssemblies(LPCWSTR wszAssembly1, LPCWSTR wszAssembly2, DWORD *pdwResult)
{
  int ShimImpl; // eax
  FARPROC ProcAddress; // rax
  void *retaddr; // [rsp+38h] [rbp+0h]
  HMODULE hModule; // [rsp+58h] [rbp+20h] BYREF

  hModule = 0;
  ShimImpl = GetShimImpl(&hModule);
  if ( ShimImpl == 1 )
    return 0;
  if ( ShimImpl == 3 )
  {
    ProcAddress = (FARPROC)g_StrongNameCompareAssemblies;
    if ( g_StrongNameCompareAssemblies )
      return ((__int64 (__fastcall *)(LPCWSTR, LPCWSTR, DWORD *))ProcAddress)(wszAssembly1, wszAssembly2, pdwResult);
    hModule = 0;
    if ( (int)GetRealStrongNameDll(&hModule) >= 0 )
    {
      ProcAddress = GetProcAddress(hModule, "StrongNameCompareAssemblies");
      g_StrongNameCompareAssemblies = (unsigned __int8 (*)(const unsigned __int16 *, const unsigned __int16 *, unsigned int *))ProcAddress;
      if ( ProcAddress )
        return ((__int64 (__fastcall *)(LPCWSTR, LPCWSTR, DWORD *))ProcAddress)(wszAssembly1, wszAssembly2, pdwResult);
    }
    return 0;
  }
  if ( g_bShimImplDllUninitialized )
    return 0;
  if ( g_pfStrongNameCompareAssemblies_RetAddr == (unsigned int (*)(const unsigned __int16 *, const unsigned __int16 *, unsigned int *, void *))-1LL )
    g_pfStrongNameCompareAssemblies_RetAddr = (unsigned int (*)(const unsigned __int16 *, const unsigned __int16 *, unsigned int *, void *))GetProcAddress(hModule, "StrongNameCompareAssemblies_RetAddr");
  if ( g_pfStrongNameCompareAssemblies_RetAddr )
    return ((__int64 (__fastcall *)(LPCWSTR, LPCWSTR, DWORD *, void *))g_pfStrongNameCompareAssemblies_RetAddr)(
             wszAssembly1,
             wszAssembly2,
             pdwResult,
             retaddr);
  if ( g_pfStrongNameCompareAssemblies == (unsigned int (*)(const unsigned __int16 *, const unsigned __int16 *, unsigned int *))-1LL )
    g_pfStrongNameCompareAssemblies = (unsigned int (*)(const unsigned __int16 *, const unsigned __int16 *, unsigned int *))GetProcAddress(hModule, "StrongNameCompareAssemblies");
  if ( !g_pfStrongNameCompareAssemblies )
    return 0;
  return ((__int64 (__fastcall *)(LPCWSTR, LPCWSTR, DWORD *))g_pfStrongNameCompareAssemblies)(
           wszAssembly1,
           wszAssembly2,
           pdwResult);
}

```

## disassembly

```asm
0x180026e10  mov     rax, rsp
0x180026e13  mov     [rax+8], rbx
0x180026e17  mov     [rax+10h], rsi
0x180026e1b  push    rdi
0x180026e1c  sub     rsp, 30h
0x180026e20  mov     rsi, rcx
0x180026e23  mov     qword ptr [rax+20h], 0
0x180026e2b  lea     rcx, [rax+20h]
0x180026e2f  mov     rbx, r8
0x180026e32  mov     rdi, rdx
0x180026e35  call    ?GetShimImpl@@YA?AW4ShimImplStatus@@PEAPEAUHINSTANCE__@@@Z; GetShimImpl(HINSTANCE__ * *)
0x180026e3a  cmp     eax, 1
0x180026e3d  jz      short loc_180026E98
0x180026e3f  cmp     eax, 3
0x180026e42  jnz     short loc_180026EAA
0x180026e44  mov     rax, cs:?g_StrongNameCompareAssemblies@@3P6AEPEBG0PEAK@ZEA; uchar (*g_StrongNameCompareAssemblies)(ushort const *,ushort const *,ulong *)
0x180026e4b  test    rax, rax
0x180026e4e  jz      short loc_180026E63
0x180026e50  mov     r8, rbx
0x180026e53  mov     rdx, rdi
0x180026e56  mov     rcx, rsi
0x180026e59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e5e  movzx   eax, al
0x180026e61  jmp     short loc_180026E9A
0x180026e63  lea     rcx, [rsp+38h+hModule]; HINSTANCE *
0x180026e68  mov     [rsp+38h+hModule], 0
0x180026e71  call    ?GetRealStrongNameDll@@YAJPEAPEAUHINSTANCE__@@@Z; GetRealStrongNameDll(HINSTANCE__ * *)
0x180026e76  test    eax, eax
0x180026e78  js      short loc_180026E98
0x180026e7a  mov     rcx, [rsp+38h+hModule]; hModule
0x180026e7f  lea     rdx, aStrongnamecomp_0; "StrongNameCompareAssemblies"
0x180026e86  call    cs:__imp_GetProcAddress
0x180026e8c  mov     cs:?g_StrongNameCompareAssemblies@@3P6AEPEBG0PEAK@ZEA, rax; uchar (*g_StrongNameCompareAssemblies)(ushort const *,ushort const *,ulong *)
0x180026e93  test    rax, rax
0x180026e96  jnz     short loc_180026E50
0x180026e98  xor     eax, eax
0x180026e9a  mov     rbx, [rsp+38h+arg_0]
0x180026e9f  mov     rsi, [rsp+38h+arg_8]
0x180026ea4  add     rsp, 30h
0x180026ea8  pop     rdi
0x180026ea9  retn
0x180026eaa  mov     eax, cs:?g_bShimImplDllUninitialized@@3HC; int volatile g_bShimImplDllUninitialized
0x180026eb0  test    eax, eax
0x180026eb2  jnz     short loc_180026E98
0x180026eb4  mov     rax, cs:?g_pfStrongNameCompareAssemblies_RetAddr@@3R6AKPEBG0PEAKPEAX@ZEA; ulong (*g_pfStrongNameCompareAssemblies_RetAddr)(ushort const *,ushort const *,ulong *,void *)
0x180026ebb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180026ebf  jnz     short loc_180026EDA
0x180026ec1  mov     rcx, [rsp+38h+hModule]; hModule
0x180026ec6  lea     rdx, aStrongnamecomp_1; "StrongNameCompareAssemblies_RetAddr"
0x180026ecd  call    cs:__imp_GetProcAddress
0x180026ed3  mov     cs:?g_pfStrongNameCompareAssemblies_RetAddr@@3R6AKPEBG0PEAKPEAX@ZEA, rax; ulong (*g_pfStrongNameCompareAssemblies_RetAddr)(ushort const *,ushort const *,ulong *,void *)
0x180026eda  mov     rax, cs:?g_pfStrongNameCompareAssemblies_RetAddr@@3R6AKPEBG0PEAKPEAX@ZEA; ulong (*g_pfStrongNameCompareAssemblies_RetAddr)(ushort const *,ushort const *,ulong *,void *)
0x180026ee1  test    rax, rax
0x180026ee4  jz      short loc_180026F02
0x180026ee6  mov     rax, cs:?g_pfStrongNameCompareAssemblies_RetAddr@@3R6AKPEBG0PEAKPEAX@ZEA; ulong (*g_pfStrongNameCompareAssemblies_RetAddr)(ushort const *,ushort const *,ulong *,void *)
0x180026eed  mov     r8, rbx
0x180026ef0  mov     r9, [rsp+38h]
0x180026ef5  mov     rdx, rdi
0x180026ef8  mov     rcx, rsi
0x180026efb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026f00  jmp     short loc_180026E9A
0x180026f02  mov     rax, cs:?g_pfStrongNameCompareAssemblies@@3R6AKPEBG0PEAK@ZEA; ulong (*g_pfStrongNameCompareAssemblies)(ushort const *,ushort const *,ulong *)
0x180026f09  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180026f0d  jnz     short loc_180026F28
0x180026f0f  mov     rcx, [rsp+38h+hModule]; hModule
0x180026f14  lea     rdx, aStrongnamecomp_0; "StrongNameCompareAssemblies"
0x180026f1b  call    cs:__imp_GetProcAddress
0x180026f21  mov     cs:?g_pfStrongNameCompareAssemblies@@3R6AKPEBG0PEAK@ZEA, rax; ulong (*g_pfStrongNameCompareAssemblies)(ushort const *,ushort const *,ulong *)
0x180026f28  mov     rax, cs:?g_pfStrongNameCompareAssemblies@@3R6AKPEBG0PEAK@ZEA; ulong (*g_pfStrongNameCompareAssemblies)(ushort const *,ushort const *,ulong *)
0x180026f2f  test    rax, rax
0x180026f32  jz      loc_180026E98
0x180026f38  mov     rax, cs:?g_pfStrongNameCompareAssemblies@@3R6AKPEBG0PEAK@ZEA; ulong (*g_pfStrongNameCompareAssemblies)(ushort const *,ushort const *,ulong *)
0x180026f3f  mov     r8, rbx
0x180026f42  mov     rdx, rdi
0x180026f45  mov     rcx, rsi
0x180026f48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026f4d  jmp     loc_180026E9A
```
