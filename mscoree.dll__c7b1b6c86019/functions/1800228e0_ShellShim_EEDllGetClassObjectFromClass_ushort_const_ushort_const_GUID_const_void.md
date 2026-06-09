# ShellShim_EEDllGetClassObjectFromClass(ushort const *,ushort const *,_GUID const &,void * *)

- ea: `0x1800228e0`
- end: `0x1800229de`
- name: `?ShellShim_EEDllGetClassObjectFromClass@@YAJPEBG0AEBU_GUID@@PEAPEAX@Z`
- size: `254`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180001c10`
- `0x1800228e0`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180022947`
- `KERNEL32!GetProcAddress` at `0x18002299d`
- `KERNEL32!GetProcAddress` at `0x180022947`
- `KERNEL32!GetProcAddress` at `0x18002299d`

## string_xrefs

- `0x180022940`: `EEDllGetClassObjectFromClass_RetAddr`
- `0x180022996`: `EEDllGetClassObjectFromClass`

## pseudocode

```c
__int64 __fastcall ShellShim_EEDllGetClassObjectFromClass(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const struct _GUID *a3,
        void **a4)
{
  int ShimImpl; // eax
  HMODULE hModule[7]; // [rsp+30h] [rbp-38h] BYREF
  void *retaddr; // [rsp+68h] [rbp+0h]

  hModule[0] = 0;
  ShimImpl = GetShimImpl(hModule);
  if ( ShimImpl == 1 )
    return 2148734721LL;
  if ( ShimImpl == 3 )
    return 2147500033LL;
  if ( g_bShimImplDllUninitialized )
    return 2148734721LL;
  if ( g_pfEEDllGetClassObjectFromClass_RetAddr == (int (*)(const unsigned __int16 *, const unsigned __int16 *, const struct _GUID *, void **, void *))-1LL )
    g_pfEEDllGetClassObjectFromClass_RetAddr = (int (*)(const unsigned __int16 *, const unsigned __int16 *, const struct _GUID *, void **, void *))GetProcAddress(hModule[0], "EEDllGetClassObjectFromClass_RetAddr");
  if ( g_pfEEDllGetClassObjectFromClass_RetAddr )
    return ((__int64 (__fastcall *)(const unsigned __int16 *, const unsigned __int16 *, const struct _GUID *, void **, void *))g_pfEEDllGetClassObjectFromClass_RetAddr)(
             a1,
             a2,
             a3,
             a4,
             retaddr);
  if ( g_pfEEDllGetClassObjectFromClass == (int (*)(const unsigned __int16 *, const unsigned __int16 *, const struct _GUID *, void **))-1LL )
    g_pfEEDllGetClassObjectFromClass = (int (*)(const unsigned __int16 *, const unsigned __int16 *, const struct _GUID *, void **))GetProcAddress(hModule[0], "EEDllGetClassObjectFromClass");
  if ( !g_pfEEDllGetClassObjectFromClass )
    return 2148734721LL;
  else
    return ((__int64 (__fastcall *)(const unsigned __int16 *, const unsigned __int16 *, const struct _GUID *, void **))g_pfEEDllGetClassObjectFromClass)(
             a1,
             a2,
             a3,
             a4);
}

```

## disassembly

```asm
0x1800228e0  push    rbx
0x1800228e2  push    rbp
0x1800228e3  push    rsi
0x1800228e4  push    rdi
0x1800228e5  sub     rsp, 48h
0x1800228e9  mov     rbp, rcx
0x1800228ec  mov     [rsp+68h+hModule], 0
0x1800228f5  lea     rcx, [rsp+68h+hModule]
0x1800228fa  mov     rbx, r9
0x1800228fd  mov     rdi, r8
0x180022900  mov     rsi, rdx
0x180022903  call    ?GetShimImpl@@YA?AW4ShimImplStatus@@PEAPEAUHINSTANCE__@@@Z; GetShimImpl(HINSTANCE__ * *)
0x180022908  cmp     eax, 1
0x18002290b  jz      loc_1800229D0
0x180022911  cmp     eax, 3
0x180022914  jnz     short loc_180022920
0x180022916  mov     eax, 80004001h
0x18002291b  jmp     loc_1800229D5
0x180022920  mov     eax, cs:?g_bShimImplDllUninitialized@@3HC; int volatile g_bShimImplDllUninitialized
0x180022926  test    eax, eax
0x180022928  jnz     loc_1800229D0
0x18002292e  mov     rax, cs:?g_pfEEDllGetClassObjectFromClass_RetAddr@@3R6AJPEBG0AEBU_GUID@@PEAPEAXPEAX@ZEA; long (*g_pfEEDllGetClassObjectFromClass_RetAddr)(ushort const *,ushort const *,_GUID const &,void * *,void *)
0x180022935  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180022939  jnz     short loc_180022954
0x18002293b  mov     rcx, [rsp+68h+hModule]; hModule
0x180022940  lea     rdx, aEedllgetclasso_0; "EEDllGetClassObjectFromClass_RetAddr"
0x180022947  call    cs:__imp_GetProcAddress
0x18002294d  mov     cs:?g_pfEEDllGetClassObjectFromClass_RetAddr@@3R6AJPEBG0AEBU_GUID@@PEAPEAXPEAX@ZEA, rax; long (*g_pfEEDllGetClassObjectFromClass_RetAddr)(ushort const *,ushort const *,_GUID const &,void * *,void *)
0x180022954  mov     rax, cs:?g_pfEEDllGetClassObjectFromClass_RetAddr@@3R6AJPEBG0AEBU_GUID@@PEAPEAXPEAX@ZEA; long (*g_pfEEDllGetClassObjectFromClass_RetAddr)(ushort const *,ushort const *,_GUID const &,void * *,void *)
0x18002295b  test    rax, rax
0x18002295e  jz      short loc_180022984
0x180022960  mov     rax, cs:?g_pfEEDllGetClassObjectFromClass_RetAddr@@3R6AJPEBG0AEBU_GUID@@PEAPEAXPEAX@ZEA; long (*g_pfEEDllGetClassObjectFromClass_RetAddr)(ushort const *,ushort const *,_GUID const &,void * *,void *)
0x180022967  mov     r9, rbx
0x18002296a  mov     rcx, [rsp+68h]
0x18002296f  mov     r8, rdi
0x180022972  mov     [rsp+68h+var_48], rcx
0x180022977  mov     rdx, rsi
0x18002297a  mov     rcx, rbp
0x18002297d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022982  jmp     short loc_1800229D5
0x180022984  mov     rax, cs:?g_pfEEDllGetClassObjectFromClass@@3R6AJPEBG0AEBU_GUID@@PEAPEAX@ZEA; long (*g_pfEEDllGetClassObjectFromClass)(ushort const *,ushort const *,_GUID const &,void * *)
0x18002298b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002298f  jnz     short loc_1800229AA
0x180022991  mov     rcx, [rsp+68h+hModule]; hModule
0x180022996  lea     rdx, aEedllgetclasso_1; "EEDllGetClassObjectFromClass"
0x18002299d  call    cs:__imp_GetProcAddress
0x1800229a3  mov     cs:?g_pfEEDllGetClassObjectFromClass@@3R6AJPEBG0AEBU_GUID@@PEAPEAX@ZEA, rax; long (*g_pfEEDllGetClassObjectFromClass)(ushort const *,ushort const *,_GUID const &,void * *)
0x1800229aa  mov     rax, cs:?g_pfEEDllGetClassObjectFromClass@@3R6AJPEBG0AEBU_GUID@@PEAPEAX@ZEA; long (*g_pfEEDllGetClassObjectFromClass)(ushort const *,ushort const *,_GUID const &,void * *)
0x1800229b1  test    rax, rax
0x1800229b4  jz      short loc_1800229D0
0x1800229b6  mov     rax, cs:?g_pfEEDllGetClassObjectFromClass@@3R6AJPEBG0AEBU_GUID@@PEAPEAX@ZEA; long (*g_pfEEDllGetClassObjectFromClass)(ushort const *,ushort const *,_GUID const &,void * *)
0x1800229bd  mov     r9, rbx
0x1800229c0  mov     r8, rdi
0x1800229c3  mov     rdx, rsi
0x1800229c6  mov     rcx, rbp
0x1800229c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800229ce  jmp     short loc_1800229D5
0x1800229d0  mov     eax, 80131701h
0x1800229d5  add     rsp, 48h
0x1800229d9  pop     rdi
0x1800229da  pop     rsi
0x1800229db  pop     rbp
0x1800229dc  pop     rbx
0x1800229dd  retn
```
