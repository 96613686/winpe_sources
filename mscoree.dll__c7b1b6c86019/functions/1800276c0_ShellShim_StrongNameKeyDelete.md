# ShellShim_StrongNameKeyDelete

- ea: `0x1800276c0`
- end: `0x1800277db`
- name: `ShellShim_StrongNameKeyDelete`
- size: `283`
- prototype: `BOOLEAN __stdcall(LPCWSTR wszKeyContainer)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180001c10`
- `0x1800276c0`
- `0x18002a2e4`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180027722`
- `KERNEL32!GetProcAddress` at `0x18002775f`
- `KERNEL32!GetProcAddress` at `0x1800277aa`
- `KERNEL32!GetProcAddress` at `0x180027722`
- `KERNEL32!GetProcAddress` at `0x18002775f`
- `KERNEL32!GetProcAddress` at `0x1800277aa`

## string_xrefs

- `0x180027758`: `StrongNameKeyDelete_RetAddr`
- `0x18002771b`: `StrongNameKeyDelete`
- `0x1800277a3`: `StrongNameKeyDelete`

## pseudocode

```c
BOOLEAN __stdcall ShellShim_StrongNameKeyDelete(LPCWSTR wszKeyContainer)
{
  int ShimImpl; // eax
  FARPROC ProcAddress; // rax
  void *retaddr; // [rsp+28h] [rbp+0h]
  HMODULE hModule; // [rsp+38h] [rbp+10h] BYREF

  hModule = 0;
  ShimImpl = GetShimImpl(&hModule);
  if ( ShimImpl == 1 )
    return 0;
  if ( ShimImpl == 3 )
  {
    ProcAddress = (FARPROC)g_StrongNameKeyDelete;
    if ( g_StrongNameKeyDelete )
      return ((__int64 (__fastcall *)(LPCWSTR))ProcAddress)(wszKeyContainer);
    hModule = 0;
    if ( (int)GetRealStrongNameDll(&hModule) >= 0 )
    {
      ProcAddress = GetProcAddress(hModule, "StrongNameKeyDelete");
      g_StrongNameKeyDelete = (unsigned __int8 (*)(const unsigned __int16 *))ProcAddress;
      if ( ProcAddress )
        return ((__int64 (__fastcall *)(LPCWSTR))ProcAddress)(wszKeyContainer);
    }
    return 0;
  }
  if ( g_bShimImplDllUninitialized )
    return 0;
  if ( g_pfStrongNameKeyDelete_RetAddr == (unsigned int (*)(const unsigned __int16 *, void *))-1LL )
    g_pfStrongNameKeyDelete_RetAddr = (unsigned int (*)(const unsigned __int16 *, void *))GetProcAddress(
                                                                                            hModule,
                                                                                            "StrongNameKeyDelete_RetAddr");
  if ( g_pfStrongNameKeyDelete_RetAddr )
    return ((__int64 (__fastcall *)(LPCWSTR, void *))g_pfStrongNameKeyDelete_RetAddr)(wszKeyContainer, retaddr);
  if ( g_pfStrongNameKeyDelete == (unsigned int (*)(const unsigned __int16 *))-1LL )
    g_pfStrongNameKeyDelete = (unsigned int (*)(const unsigned __int16 *))GetProcAddress(hModule, "StrongNameKeyDelete");
  if ( !g_pfStrongNameKeyDelete )
    return 0;
  return ((__int64 (__fastcall *)(LPCWSTR))g_pfStrongNameKeyDelete)(wszKeyContainer);
}

```

## disassembly

```asm
0x1800276c0  push    rbx
0x1800276c2  sub     rsp, 20h
0x1800276c6  mov     rbx, rcx
0x1800276c9  mov     [rsp+28h+hModule], 0
0x1800276d2  lea     rcx, [rsp+28h+hModule]
0x1800276d7  call    ?GetShimImpl@@YA?AW4ShimImplStatus@@PEAPEAUHINSTANCE__@@@Z; GetShimImpl(HINSTANCE__ * *)
0x1800276dc  cmp     eax, 1
0x1800276df  jz      short loc_180027734
0x1800276e1  cmp     eax, 3
0x1800276e4  jnz     short loc_18002773C
0x1800276e6  mov     rax, cs:?g_StrongNameKeyDelete@@3P6AEPEBG@ZEA; uchar (*g_StrongNameKeyDelete)(ushort const *)
0x1800276ed  test    rax, rax
0x1800276f0  jz      short loc_1800276FF
0x1800276f2  mov     rcx, rbx
0x1800276f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800276fa  movzx   eax, al
0x1800276fd  jmp     short loc_180027736
0x1800276ff  lea     rcx, [rsp+28h+hModule]; HINSTANCE *
0x180027704  mov     [rsp+28h+hModule], 0
0x18002770d  call    ?GetRealStrongNameDll@@YAJPEAPEAUHINSTANCE__@@@Z; GetRealStrongNameDll(HINSTANCE__ * *)
0x180027712  test    eax, eax
0x180027714  js      short loc_180027734
0x180027716  mov     rcx, [rsp+28h+hModule]; hModule
0x18002771b  lea     rdx, aStrongnamekeyd_0; "StrongNameKeyDelete"
0x180027722  call    cs:__imp_GetProcAddress
0x180027728  mov     cs:?g_StrongNameKeyDelete@@3P6AEPEBG@ZEA, rax; uchar (*g_StrongNameKeyDelete)(ushort const *)
0x18002772f  test    rax, rax
0x180027732  jnz     short loc_1800276F2
0x180027734  xor     eax, eax
0x180027736  add     rsp, 20h
0x18002773a  pop     rbx
0x18002773b  retn
0x18002773c  mov     eax, cs:?g_bShimImplDllUninitialized@@3HC; int volatile g_bShimImplDllUninitialized
0x180027742  test    eax, eax
0x180027744  jnz     short loc_180027734
0x180027746  mov     rax, cs:?g_pfStrongNameKeyDelete_RetAddr@@3R6AKPEBGPEAX@ZEA; ulong (*g_pfStrongNameKeyDelete_RetAddr)(ushort const *,void *)
0x18002774d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180027751  jnz     short loc_18002776C
0x180027753  mov     rcx, [rsp+28h+hModule]; hModule
0x180027758  lea     rdx, aStrongnamekeyd_1; "StrongNameKeyDelete_RetAddr"
0x18002775f  call    cs:__imp_GetProcAddress
0x180027765  mov     cs:?g_pfStrongNameKeyDelete_RetAddr@@3R6AKPEBGPEAX@ZEA, rax; ulong (*g_pfStrongNameKeyDelete_RetAddr)(ushort const *,void *)
0x18002776c  mov     rax, cs:?g_pfStrongNameKeyDelete_RetAddr@@3R6AKPEBGPEAX@ZEA; ulong (*g_pfStrongNameKeyDelete_RetAddr)(ushort const *,void *)
0x180027773  test    rax, rax
0x180027776  jz      short loc_180027791
0x180027778  mov     rax, cs:?g_pfStrongNameKeyDelete_RetAddr@@3R6AKPEBGPEAX@ZEA; ulong (*g_pfStrongNameKeyDelete_RetAddr)(ushort const *,void *)
0x18002777f  mov     rcx, rbx
0x180027782  mov     rdx, [rsp+28h]
0x180027787  add     rsp, 20h
0x18002778b  pop     rbx
0x18002778c  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180027791  mov     rax, cs:?g_pfStrongNameKeyDelete@@3R6AKPEBG@ZEA; ulong (*g_pfStrongNameKeyDelete)(ushort const *)
0x180027798  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002779c  jnz     short loc_1800277B7
0x18002779e  mov     rcx, [rsp+28h+hModule]; hModule
0x1800277a3  lea     rdx, aStrongnamekeyd_0; "StrongNameKeyDelete"
0x1800277aa  call    cs:__imp_GetProcAddress
0x1800277b0  mov     cs:?g_pfStrongNameKeyDelete@@3R6AKPEBG@ZEA, rax; ulong (*g_pfStrongNameKeyDelete)(ushort const *)
0x1800277b7  mov     rax, cs:?g_pfStrongNameKeyDelete@@3R6AKPEBG@ZEA; ulong (*g_pfStrongNameKeyDelete)(ushort const *)
0x1800277be  test    rax, rax
0x1800277c1  jz      loc_180027734
0x1800277c7  mov     rax, cs:?g_pfStrongNameKeyDelete@@3R6AKPEBG@ZEA; ulong (*g_pfStrongNameKeyDelete)(ushort const *)
0x1800277ce  mov     rcx, rbx
0x1800277d1  add     rsp, 20h
0x1800277d5  pop     rbx
0x1800277d6  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
