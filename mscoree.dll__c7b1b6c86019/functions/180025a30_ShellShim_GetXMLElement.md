# ShellShim_GetXMLElement

- ea: `0x180025a30`
- end: `0x180025b1a`
- name: `ShellShim_GetXMLElement`
- size: `234`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callees

- `0x180001c10`
- `0x180025a30`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180025a92`
- `KERNEL32!GetProcAddress` at `0x180025add`
- `KERNEL32!GetProcAddress` at `0x180025a92`
- `KERNEL32!GetProcAddress` at `0x180025add`

## string_xrefs

- `0x180025a8b`: `GetXMLElement_RetAddr`
- `0x180025ad6`: `GetXMLElement`

## pseudocode

```c
__int64 __fastcall ShellShim_GetXMLElement(__int64 a1, __int64 a2)
{
  int ShimImpl; // eax
  void *retaddr; // [rsp+28h] [rbp+0h]
  HMODULE hModule; // [rsp+40h] [rbp+18h] BYREF

  hModule = 0;
  ShimImpl = GetShimImpl(&hModule);
  if ( ShimImpl == 1 )
    return 2148734721LL;
  if ( ShimImpl == 3 )
    return 2147500037LL;
  if ( g_bShimImplDllUninitialized )
    return 2148734721LL;
  if ( g_pfGetXMLElement_RetAddr == (int (*)(const unsigned __int16 *, const unsigned __int16 *, void *))-1LL )
    g_pfGetXMLElement_RetAddr = (int (*)(const unsigned __int16 *, const unsigned __int16 *, void *))GetProcAddress(hModule, "GetXMLElement_RetAddr");
  if ( g_pfGetXMLElement_RetAddr )
    return ((__int64 (__fastcall *)(__int64, __int64, void *))g_pfGetXMLElement_RetAddr)(a1, a2, retaddr);
  if ( g_pfGetXMLElement == (int (*)(const unsigned __int16 *, const unsigned __int16 *))-1LL )
    g_pfGetXMLElement = (int (*)(const unsigned __int16 *, const unsigned __int16 *))GetProcAddress(
                                                                                       hModule,
                                                                                       "GetXMLElement");
  if ( !g_pfGetXMLElement )
    return 2148734721LL;
  else
    return ((__int64 (__fastcall *)(__int64, __int64))g_pfGetXMLElement)(a1, a2);
}

```

## disassembly

```asm
0x180025a30  mov     [rsp+arg_0], rbx
0x180025a35  push    rdi
0x180025a36  sub     rsp, 20h
0x180025a3a  mov     rdi, rcx
0x180025a3d  mov     [rsp+28h+hModule], 0
0x180025a46  lea     rcx, [rsp+28h+hModule]
0x180025a4b  mov     rbx, rdx
0x180025a4e  call    ?GetShimImpl@@YA?AW4ShimImplStatus@@PEAPEAUHINSTANCE__@@@Z; GetShimImpl(HINSTANCE__ * *)
0x180025a53  cmp     eax, 1
0x180025a56  jz      loc_180025B0A
0x180025a5c  cmp     eax, 3
0x180025a5f  jnz     short loc_180025A6B
0x180025a61  mov     eax, 80004005h
0x180025a66  jmp     loc_180025B0F
0x180025a6b  mov     eax, cs:?g_bShimImplDllUninitialized@@3HC; int volatile g_bShimImplDllUninitialized
0x180025a71  test    eax, eax
0x180025a73  jnz     loc_180025B0A
0x180025a79  mov     rax, cs:?g_pfGetXMLElement_RetAddr@@3R6AJPEBG0PEAX@ZEA; long (*g_pfGetXMLElement_RetAddr)(ushort const *,ushort const *,void *)
0x180025a80  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180025a84  jnz     short loc_180025A9F
0x180025a86  mov     rcx, [rsp+28h+hModule]; hModule
0x180025a8b  lea     rdx, aGetxmlelementR; "GetXMLElement_RetAddr"
0x180025a92  call    cs:__imp_GetProcAddress
0x180025a98  mov     cs:?g_pfGetXMLElement_RetAddr@@3R6AJPEBG0PEAX@ZEA, rax; long (*g_pfGetXMLElement_RetAddr)(ushort const *,ushort const *,void *)
0x180025a9f  mov     rax, cs:?g_pfGetXMLElement_RetAddr@@3R6AJPEBG0PEAX@ZEA; long (*g_pfGetXMLElement_RetAddr)(ushort const *,ushort const *,void *)
0x180025aa6  test    rax, rax
0x180025aa9  jz      short loc_180025AC4
0x180025aab  mov     rax, cs:?g_pfGetXMLElement_RetAddr@@3R6AJPEBG0PEAX@ZEA; long (*g_pfGetXMLElement_RetAddr)(ushort const *,ushort const *,void *)
0x180025ab2  mov     rdx, rbx
0x180025ab5  mov     r8, [rsp+28h]
0x180025aba  mov     rcx, rdi
0x180025abd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ac2  jmp     short loc_180025B0F
0x180025ac4  mov     rax, cs:?g_pfGetXMLElement@@3R6AJPEBG0@ZEA; long (*g_pfGetXMLElement)(ushort const *,ushort const *)
0x180025acb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180025acf  jnz     short loc_180025AEA
0x180025ad1  mov     rcx, [rsp+28h+hModule]; hModule
0x180025ad6  lea     rdx, aGetxmlelement_0; "GetXMLElement"
0x180025add  call    cs:__imp_GetProcAddress
0x180025ae3  mov     cs:?g_pfGetXMLElement@@3R6AJPEBG0@ZEA, rax; long (*g_pfGetXMLElement)(ushort const *,ushort const *)
0x180025aea  mov     rax, cs:?g_pfGetXMLElement@@3R6AJPEBG0@ZEA; long (*g_pfGetXMLElement)(ushort const *,ushort const *)
0x180025af1  test    rax, rax
0x180025af4  jz      short loc_180025B0A
0x180025af6  mov     rax, cs:?g_pfGetXMLElement@@3R6AJPEBG0@ZEA; long (*g_pfGetXMLElement)(ushort const *,ushort const *)
0x180025afd  mov     rdx, rbx
0x180025b00  mov     rcx, rdi
0x180025b03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025b08  jmp     short loc_180025B0F
0x180025b0a  mov     eax, 80131701h
0x180025b0f  mov     rbx, [rsp+28h+arg_0]
0x180025b14  add     rsp, 20h
0x180025b18  pop     rdi
0x180025b19  retn
```
