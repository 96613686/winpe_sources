# ShellShim_LoadLibraryWithPolicyShim

- ea: `0x180025e30`
- end: `0x180025f3a`
- name: `ShellShim_LoadLibraryWithPolicyShim`
- size: `266`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x180001c10`
- `0x180025e30`
- `0x18002e4f0`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180025ea3`
- `KERNEL32!GetProcAddress` at `0x180025ef9`
- `KERNEL32!GetProcAddress` at `0x180025ea3`
- `KERNEL32!GetProcAddress` at `0x180025ef9`

## string_xrefs

- `0x180025e9c`: `LoadLibraryWithPolicyShim_RetAddr`
- `0x180025ef2`: `LoadLibraryWithPolicyShim`

## pseudocode

```c
__int64 __fastcall ShellShim_LoadLibraryWithPolicyShim(wchar_t *Source, __int64 a2, unsigned int a3, __int64 a4)
{
  int ShimImpl; // eax
  HMODULE hModule[7]; // [rsp+30h] [rbp-38h] BYREF
  void *retaddr; // [rsp+68h] [rbp+0h]

  hModule[0] = 0;
  ShimImpl = GetShimImpl(hModule);
  if ( ShimImpl == 1 )
    return 2148734721LL;
  if ( ShimImpl == 3 )
    return LoadLibraryWithPolicyShim(Source);
  if ( g_bShimImplDllUninitialized )
    return 2148734721LL;
  if ( g_pfLoadLibraryWithPolicyShim_RetAddr == (int (*)(const unsigned __int16 *, const unsigned __int16 *, int, HINSTANCE *, void *))-1LL )
    g_pfLoadLibraryWithPolicyShim_RetAddr = (int (*)(const unsigned __int16 *, const unsigned __int16 *, int, HINSTANCE *, void *))GetProcAddress(hModule[0], "LoadLibraryWithPolicyShim_RetAddr");
  if ( g_pfLoadLibraryWithPolicyShim_RetAddr )
    return ((__int64 (__fastcall *)(wchar_t *, __int64, _QWORD, __int64, void *))g_pfLoadLibraryWithPolicyShim_RetAddr)(
             Source,
             a2,
             a3,
             a4,
             retaddr);
  if ( g_pfLoadLibraryWithPolicyShim == (int (*)(const unsigned __int16 *, const unsigned __int16 *, int, HINSTANCE *))-1LL )
    g_pfLoadLibraryWithPolicyShim = (int (*)(const unsigned __int16 *, const unsigned __int16 *, int, HINSTANCE *))GetProcAddress(hModule[0], "LoadLibraryWithPolicyShim");
  if ( !g_pfLoadLibraryWithPolicyShim )
    return 2148734721LL;
  else
    return ((__int64 (__fastcall *)(wchar_t *, __int64, _QWORD, __int64))g_pfLoadLibraryWithPolicyShim)(
             Source,
             a2,
             a3,
             a4);
}

```

## disassembly

```asm
0x180025e30  push    rbx
0x180025e32  push    rbp
0x180025e33  push    rsi
0x180025e34  push    rdi
0x180025e35  sub     rsp, 48h
0x180025e39  mov     rbp, rcx
0x180025e3c  mov     [rsp+68h+hModule], 0
0x180025e45  lea     rcx, [rsp+68h+hModule]
0x180025e4a  mov     rbx, r9
0x180025e4d  mov     edi, r8d
0x180025e50  mov     rsi, rdx
0x180025e53  call    ?GetShimImpl@@YA?AW4ShimImplStatus@@PEAPEAUHINSTANCE__@@@Z; GetShimImpl(HINSTANCE__ * *)
0x180025e58  cmp     eax, 1
0x180025e5b  jz      loc_180025F2C
0x180025e61  cmp     eax, 3
0x180025e64  jnz     short loc_180025E7C
0x180025e66  mov     r9, rbx
0x180025e69  mov     r8d, edi
0x180025e6c  mov     rdx, rsi
0x180025e6f  mov     rcx, rbp; Source
0x180025e72  call    LoadLibraryWithPolicyShim
0x180025e77  jmp     loc_180025F31
0x180025e7c  mov     eax, cs:?g_bShimImplDllUninitialized@@3HC; int volatile g_bShimImplDllUninitialized
0x180025e82  test    eax, eax
0x180025e84  jnz     loc_180025F2C
0x180025e8a  mov     rax, cs:?g_pfLoadLibraryWithPolicyShim_RetAddr@@3R6AJPEBG0HPEAPEAUHINSTANCE__@@PEAX@ZEA; long (*g_pfLoadLibraryWithPolicyShim_RetAddr)(ushort const *,ushort const *,int,HINSTANCE__ * *,void *)
0x180025e91  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180025e95  jnz     short loc_180025EB0
0x180025e97  mov     rcx, [rsp+68h+hModule]; hModule
0x180025e9c  lea     rdx, aLoadlibrarywit_0; "LoadLibraryWithPolicyShim_RetAddr"
0x180025ea3  call    cs:__imp_GetProcAddress
0x180025ea9  mov     cs:?g_pfLoadLibraryWithPolicyShim_RetAddr@@3R6AJPEBG0HPEAPEAUHINSTANCE__@@PEAX@ZEA, rax; long (*g_pfLoadLibraryWithPolicyShim_RetAddr)(ushort const *,ushort const *,int,HINSTANCE__ * *,void *)
0x180025eb0  mov     rax, cs:?g_pfLoadLibraryWithPolicyShim_RetAddr@@3R6AJPEBG0HPEAPEAUHINSTANCE__@@PEAX@ZEA; long (*g_pfLoadLibraryWithPolicyShim_RetAddr)(ushort const *,ushort const *,int,HINSTANCE__ * *,void *)
0x180025eb7  test    rax, rax
0x180025eba  jz      short loc_180025EE0
0x180025ebc  mov     rax, cs:?g_pfLoadLibraryWithPolicyShim_RetAddr@@3R6AJPEBG0HPEAPEAUHINSTANCE__@@PEAX@ZEA; long (*g_pfLoadLibraryWithPolicyShim_RetAddr)(ushort const *,ushort const *,int,HINSTANCE__ * *,void *)
0x180025ec3  mov     r9, rbx
0x180025ec6  mov     rcx, [rsp+68h]
0x180025ecb  mov     r8d, edi
0x180025ece  mov     [rsp+68h+var_48], rcx
0x180025ed3  mov     rdx, rsi
0x180025ed6  mov     rcx, rbp
0x180025ed9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ede  jmp     short loc_180025F31
0x180025ee0  mov     rax, cs:?g_pfLoadLibraryWithPolicyShim@@3R6AJPEBG0HPEAPEAUHINSTANCE__@@@ZEA; long (*g_pfLoadLibraryWithPolicyShim)(ushort const *,ushort const *,int,HINSTANCE__ * *)
0x180025ee7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180025eeb  jnz     short loc_180025F06
0x180025eed  mov     rcx, [rsp+68h+hModule]; hModule
0x180025ef2  lea     rdx, aLoadlibrarywit_1; "LoadLibraryWithPolicyShim"
0x180025ef9  call    cs:__imp_GetProcAddress
0x180025eff  mov     cs:?g_pfLoadLibraryWithPolicyShim@@3R6AJPEBG0HPEAPEAUHINSTANCE__@@@ZEA, rax; long (*g_pfLoadLibraryWithPolicyShim)(ushort const *,ushort const *,int,HINSTANCE__ * *)
0x180025f06  mov     rax, cs:?g_pfLoadLibraryWithPolicyShim@@3R6AJPEBG0HPEAPEAUHINSTANCE__@@@ZEA; long (*g_pfLoadLibraryWithPolicyShim)(ushort const *,ushort const *,int,HINSTANCE__ * *)
0x180025f0d  test    rax, rax
0x180025f10  jz      short loc_180025F2C
0x180025f12  mov     rax, cs:?g_pfLoadLibraryWithPolicyShim@@3R6AJPEBG0HPEAPEAUHINSTANCE__@@@ZEA; long (*g_pfLoadLibraryWithPolicyShim)(ushort const *,ushort const *,int,HINSTANCE__ * *)
0x180025f19  mov     r9, rbx
0x180025f1c  mov     r8d, edi
0x180025f1f  mov     rdx, rsi
0x180025f22  mov     rcx, rbp
0x180025f25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025f2a  jmp     short loc_180025F31
0x180025f2c  mov     eax, 80131701h
0x180025f31  add     rsp, 48h
0x180025f35  pop     rdi
0x180025f36  pop     rsi
0x180025f37  pop     rbp
0x180025f38  pop     rbx
0x180025f39  retn
```
