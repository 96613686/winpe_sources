# ShellShim_LoadLibraryShim

- ea: `0x180025d20`
- end: `0x180025e27`
- name: `ShellShim_LoadLibraryShim`
- size: `263`
- prototype: `__int64 __fastcall(wchar_t *Source, wchar_t *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180001c10`
- `0x180002710`
- `0x180025d20`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180025d90`
- `KERNEL32!GetProcAddress` at `0x180025de6`
- `KERNEL32!GetProcAddress` at `0x180025d90`
- `KERNEL32!GetProcAddress` at `0x180025de6`

## string_xrefs

- `0x180025d89`: `LoadLibraryShim_RetAddr`
- `0x180025ddf`: `LoadLibraryShim`

## pseudocode

```c
__int64 __fastcall ShellShim_LoadLibraryShim(wchar_t *Source, wchar_t *a2, __int64 a3, HMODULE *a4)
{
  int ShimImpl; // eax
  __int64 v9; // r8
  HMODULE hModule[7]; // [rsp+30h] [rbp-38h] BYREF
  void *retaddr; // [rsp+68h] [rbp+0h]

  hModule[0] = 0;
  ShimImpl = GetShimImpl(hModule);
  if ( ShimImpl == 1 )
    return 2148734721LL;
  if ( ShimImpl == 3 )
    return LoadLibraryShim_0(Source, a2, v9, a4);
  if ( g_bShimImplDllUninitialized )
    return 2148734721LL;
  if ( g_pfLoadLibraryShim_RetAddr == (int (*)(const unsigned __int16 *, const unsigned __int16 *, void *, HINSTANCE *, void *))-1LL )
    g_pfLoadLibraryShim_RetAddr = (int (*)(const unsigned __int16 *, const unsigned __int16 *, void *, HINSTANCE *, void *))GetProcAddress(hModule[0], "LoadLibraryShim_RetAddr");
  if ( g_pfLoadLibraryShim_RetAddr )
    return ((__int64 (__fastcall *)(wchar_t *, wchar_t *, __int64, HMODULE *, void *))g_pfLoadLibraryShim_RetAddr)(
             Source,
             a2,
             a3,
             a4,
             retaddr);
  if ( g_pfLoadLibraryShim == (int (*)(const unsigned __int16 *, const unsigned __int16 *, void *, HINSTANCE *))-1LL )
    g_pfLoadLibraryShim = (int (*)(const unsigned __int16 *, const unsigned __int16 *, void *, HINSTANCE *))GetProcAddress(hModule[0], "LoadLibraryShim");
  if ( !g_pfLoadLibraryShim )
    return 2148734721LL;
  else
    return ((__int64 (__fastcall *)(wchar_t *, wchar_t *, __int64, HMODULE *))g_pfLoadLibraryShim)(Source, a2, a3, a4);
}

```

## disassembly

```asm
0x180025d20  push    rbx
0x180025d22  push    rbp
0x180025d23  push    rsi
0x180025d24  push    rdi
0x180025d25  sub     rsp, 48h
0x180025d29  mov     rsi, rcx
0x180025d2c  mov     [rsp+68h+hModule], 0
0x180025d35  lea     rcx, [rsp+68h+hModule]
0x180025d3a  mov     rbx, r9
0x180025d3d  mov     rbp, r8
0x180025d40  mov     rdi, rdx
0x180025d43  call    ?GetShimImpl@@YA?AW4ShimImplStatus@@PEAPEAUHINSTANCE__@@@Z; GetShimImpl(HINSTANCE__ * *)
0x180025d48  cmp     eax, 1
0x180025d4b  jz      loc_180025E19
0x180025d51  cmp     eax, 3
0x180025d54  jnz     short loc_180025D69
0x180025d56  mov     r9, rbx
0x180025d59  mov     rdx, rdi; wchar_t *
0x180025d5c  mov     rcx, rsi; Source
0x180025d5f  call    LoadLibraryShim_0
0x180025d64  jmp     loc_180025E1E
0x180025d69  mov     eax, cs:?g_bShimImplDllUninitialized@@3HC; int volatile g_bShimImplDllUninitialized
0x180025d6f  test    eax, eax
0x180025d71  jnz     loc_180025E19
0x180025d77  mov     rax, cs:?g_pfLoadLibraryShim_RetAddr@@3R6AJPEBG0PEAXPEAPEAUHINSTANCE__@@1@ZEA; long (*g_pfLoadLibraryShim_RetAddr)(ushort const *,ushort const *,void *,HINSTANCE__ * *,void *)
0x180025d7e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180025d82  jnz     short loc_180025D9D
0x180025d84  mov     rcx, [rsp+68h+hModule]; hModule
0x180025d89  lea     rdx, aLoadlibraryshi_1; "LoadLibraryShim_RetAddr"
0x180025d90  call    cs:__imp_GetProcAddress
0x180025d96  mov     cs:?g_pfLoadLibraryShim_RetAddr@@3R6AJPEBG0PEAXPEAPEAUHINSTANCE__@@1@ZEA, rax; long (*g_pfLoadLibraryShim_RetAddr)(ushort const *,ushort const *,void *,HINSTANCE__ * *,void *)
0x180025d9d  mov     rax, cs:?g_pfLoadLibraryShim_RetAddr@@3R6AJPEBG0PEAXPEAPEAUHINSTANCE__@@1@ZEA; long (*g_pfLoadLibraryShim_RetAddr)(ushort const *,ushort const *,void *,HINSTANCE__ * *,void *)
0x180025da4  test    rax, rax
0x180025da7  jz      short loc_180025DCD
0x180025da9  mov     rax, cs:?g_pfLoadLibraryShim_RetAddr@@3R6AJPEBG0PEAXPEAPEAUHINSTANCE__@@1@ZEA; long (*g_pfLoadLibraryShim_RetAddr)(ushort const *,ushort const *,void *,HINSTANCE__ * *,void *)
0x180025db0  mov     r9, rbx
0x180025db3  mov     rcx, [rsp+68h]
0x180025db8  mov     r8, rbp
0x180025dbb  mov     [rsp+68h+var_48], rcx
0x180025dc0  mov     rdx, rdi
0x180025dc3  mov     rcx, rsi
0x180025dc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025dcb  jmp     short loc_180025E1E
0x180025dcd  mov     rax, cs:?g_pfLoadLibraryShim@@3R6AJPEBG0PEAXPEAPEAUHINSTANCE__@@@ZEA; long (*g_pfLoadLibraryShim)(ushort const *,ushort const *,void *,HINSTANCE__ * *)
0x180025dd4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180025dd8  jnz     short loc_180025DF3
0x180025dda  mov     rcx, [rsp+68h+hModule]; hModule
0x180025ddf  lea     rdx, aLoadlibraryshi_0; "LoadLibraryShim"
0x180025de6  call    cs:__imp_GetProcAddress
0x180025dec  mov     cs:?g_pfLoadLibraryShim@@3R6AJPEBG0PEAXPEAPEAUHINSTANCE__@@@ZEA, rax; long (*g_pfLoadLibraryShim)(ushort const *,ushort const *,void *,HINSTANCE__ * *)
0x180025df3  mov     rax, cs:?g_pfLoadLibraryShim@@3R6AJPEBG0PEAXPEAPEAUHINSTANCE__@@@ZEA; long (*g_pfLoadLibraryShim)(ushort const *,ushort const *,void *,HINSTANCE__ * *)
0x180025dfa  test    rax, rax
0x180025dfd  jz      short loc_180025E19
0x180025dff  mov     rax, cs:?g_pfLoadLibraryShim@@3R6AJPEBG0PEAXPEAPEAUHINSTANCE__@@@ZEA; long (*g_pfLoadLibraryShim)(ushort const *,ushort const *,void *,HINSTANCE__ * *)
0x180025e06  mov     r9, rbx
0x180025e09  mov     r8, rbp
0x180025e0c  mov     rdx, rdi
0x180025e0f  mov     rcx, rsi
0x180025e12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025e17  jmp     short loc_180025E1E
0x180025e19  mov     eax, 80131701h
0x180025e1e  add     rsp, 48h
0x180025e22  pop     rdi
0x180025e23  pop     rsi
0x180025e24  pop     rbp
0x180025e25  pop     rbx
0x180025e26  retn
```
