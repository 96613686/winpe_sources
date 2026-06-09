# ShellShim_GetXMLElementAttribute

- ea: `0x180025b20`
- end: `0x180025c1e`
- name: `ShellShim_GetXMLElementAttribute`
- size: `254`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callees

- `0x180001c10`
- `0x180025b20`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180025b87`
- `KERNEL32!GetProcAddress` at `0x180025bdd`
- `KERNEL32!GetProcAddress` at `0x180025b87`
- `KERNEL32!GetProcAddress` at `0x180025bdd`

## string_xrefs

- `0x180025b80`: `GetXMLElementAttribute_RetAddr`
- `0x180025bd6`: `GetXMLElementAttribute`

## pseudocode

```c
__int64 __fastcall ShellShim_GetXMLElementAttribute(__int64 a1, __int64 a2, unsigned int a3, __int64 a4)
{
  int ShimImpl; // eax
  HMODULE hModule[7]; // [rsp+30h] [rbp-38h] BYREF
  void *retaddr; // [rsp+68h] [rbp+0h]

  hModule[0] = 0;
  ShimImpl = GetShimImpl(hModule);
  if ( ShimImpl == 1 )
    return 2148734721LL;
  if ( ShimImpl == 3 )
    return 2147500037LL;
  if ( g_bShimImplDllUninitialized )
    return 2148734721LL;
  if ( g_pfGetXMLElementAttribute_RetAddr == (int (*)(const unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int *, void *))-1LL )
    g_pfGetXMLElementAttribute_RetAddr = (int (*)(const unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int *, void *))GetProcAddress(hModule[0], "GetXMLElementAttribute_RetAddr");
  if ( g_pfGetXMLElementAttribute_RetAddr )
    return ((__int64 (__fastcall *)(__int64, __int64, _QWORD, __int64, void *))g_pfGetXMLElementAttribute_RetAddr)(
             a1,
             a2,
             a3,
             a4,
             retaddr);
  if ( g_pfGetXMLElementAttribute == (int (*)(const unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int *))-1LL )
    g_pfGetXMLElementAttribute = (int (*)(const unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int *))GetProcAddress(hModule[0], "GetXMLElementAttribute");
  if ( !g_pfGetXMLElementAttribute )
    return 2148734721LL;
  else
    return ((__int64 (__fastcall *)(__int64, __int64, _QWORD, __int64))g_pfGetXMLElementAttribute)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180025b20  push    rbx
0x180025b22  push    rbp
0x180025b23  push    rsi
0x180025b24  push    rdi
0x180025b25  sub     rsp, 48h
0x180025b29  mov     rbp, rcx
0x180025b2c  mov     [rsp+68h+hModule], 0
0x180025b35  lea     rcx, [rsp+68h+hModule]
0x180025b3a  mov     rbx, r9
0x180025b3d  mov     edi, r8d
0x180025b40  mov     rsi, rdx
0x180025b43  call    ?GetShimImpl@@YA?AW4ShimImplStatus@@PEAPEAUHINSTANCE__@@@Z; GetShimImpl(HINSTANCE__ * *)
0x180025b48  cmp     eax, 1
0x180025b4b  jz      loc_180025C10
0x180025b51  cmp     eax, 3
0x180025b54  jnz     short loc_180025B60
0x180025b56  mov     eax, 80004005h
0x180025b5b  jmp     loc_180025C15
0x180025b60  mov     eax, cs:?g_bShimImplDllUninitialized@@3HC; int volatile g_bShimImplDllUninitialized
0x180025b66  test    eax, eax
0x180025b68  jnz     loc_180025C10
0x180025b6e  mov     rax, cs:?g_pfGetXMLElementAttribute_RetAddr@@3R6AJPEBGPEAGKPEAKPEAX@ZEA; long (*g_pfGetXMLElementAttribute_RetAddr)(ushort const *,ushort *,ulong,ulong *,void *)
0x180025b75  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180025b79  jnz     short loc_180025B94
0x180025b7b  mov     rcx, [rsp+68h+hModule]; hModule
0x180025b80  lea     rdx, aGetxmlelementa_1; "GetXMLElementAttribute_RetAddr"
0x180025b87  call    cs:__imp_GetProcAddress
0x180025b8d  mov     cs:?g_pfGetXMLElementAttribute_RetAddr@@3R6AJPEBGPEAGKPEAKPEAX@ZEA, rax; long (*g_pfGetXMLElementAttribute_RetAddr)(ushort const *,ushort *,ulong,ulong *,void *)
0x180025b94  mov     rax, cs:?g_pfGetXMLElementAttribute_RetAddr@@3R6AJPEBGPEAGKPEAKPEAX@ZEA; long (*g_pfGetXMLElementAttribute_RetAddr)(ushort const *,ushort *,ulong,ulong *,void *)
0x180025b9b  test    rax, rax
0x180025b9e  jz      short loc_180025BC4
0x180025ba0  mov     rax, cs:?g_pfGetXMLElementAttribute_RetAddr@@3R6AJPEBGPEAGKPEAKPEAX@ZEA; long (*g_pfGetXMLElementAttribute_RetAddr)(ushort const *,ushort *,ulong,ulong *,void *)
0x180025ba7  mov     r9, rbx
0x180025baa  mov     rcx, [rsp+68h]
0x180025baf  mov     r8d, edi
0x180025bb2  mov     [rsp+68h+var_48], rcx
0x180025bb7  mov     rdx, rsi
0x180025bba  mov     rcx, rbp
0x180025bbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025bc2  jmp     short loc_180025C15
0x180025bc4  mov     rax, cs:?g_pfGetXMLElementAttribute@@3R6AJPEBGPEAGKPEAK@ZEA; long (*g_pfGetXMLElementAttribute)(ushort const *,ushort *,ulong,ulong *)
0x180025bcb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180025bcf  jnz     short loc_180025BEA
0x180025bd1  mov     rcx, [rsp+68h+hModule]; hModule
0x180025bd6  lea     rdx, aGetxmlelementa_0; "GetXMLElementAttribute"
0x180025bdd  call    cs:__imp_GetProcAddress
0x180025be3  mov     cs:?g_pfGetXMLElementAttribute@@3R6AJPEBGPEAGKPEAK@ZEA, rax; long (*g_pfGetXMLElementAttribute)(ushort const *,ushort *,ulong,ulong *)
0x180025bea  mov     rax, cs:?g_pfGetXMLElementAttribute@@3R6AJPEBGPEAGKPEAK@ZEA; long (*g_pfGetXMLElementAttribute)(ushort const *,ushort *,ulong,ulong *)
0x180025bf1  test    rax, rax
0x180025bf4  jz      short loc_180025C10
0x180025bf6  mov     rax, cs:?g_pfGetXMLElementAttribute@@3R6AJPEBGPEAGKPEAK@ZEA; long (*g_pfGetXMLElementAttribute)(ushort const *,ushort *,ulong,ulong *)
0x180025bfd  mov     r9, rbx
0x180025c00  mov     r8d, edi
0x180025c03  mov     rdx, rsi
0x180025c06  mov     rcx, rbp
0x180025c09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c0e  jmp     short loc_180025C15
0x180025c10  mov     eax, 80131701h
0x180025c15  add     rsp, 48h
0x180025c19  pop     rdi
0x180025c1a  pop     rsi
0x180025c1b  pop     rbp
0x180025c1c  pop     rbx
0x180025c1d  retn
```
