# ShellShim_ClrCreateManagedInstance

- ea: `0x180023440`
- end: `0x180023545`
- name: `ShellShim_ClrCreateManagedInstance`
- size: `261`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180001c10`
- `0x180023440`
- `0x18002c0d0`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800234b2`
- `KERNEL32!GetProcAddress` at `0x180023500`
- `KERNEL32!GetProcAddress` at `0x1800234b2`
- `KERNEL32!GetProcAddress` at `0x180023500`

## string_xrefs

- `0x1800234ab`: `ClrCreateManagedInstance_RetAddr`
- `0x1800234f9`: `ClrCreateManagedInstance`

## pseudocode

```c
__int64 __fastcall ShellShim_ClrCreateManagedInstance(__int64 a1, __int64 a2, __int64 a3)
{
  int ShimImpl; // eax
  void *retaddr; // [rsp+38h] [rbp+0h]
  HMODULE hModule; // [rsp+58h] [rbp+20h] BYREF

  hModule = 0;
  ShimImpl = GetShimImpl(&hModule);
  if ( ShimImpl == 1 )
    return 2148734721LL;
  if ( ShimImpl == 3 )
    return ClrCreateManagedInstance(a1, a2, a3);
  if ( g_bShimImplDllUninitialized )
    return 2148734721LL;
  if ( g_pfClrCreateManagedInstance_RetAddr == (int (*)(const unsigned __int16 *, const struct _GUID *, void **, void *))-1LL )
    g_pfClrCreateManagedInstance_RetAddr = (int (*)(const unsigned __int16 *, const struct _GUID *, void **, void *))GetProcAddress(hModule, "ClrCreateManagedInstance_RetAddr");
  if ( g_pfClrCreateManagedInstance_RetAddr )
    return ((__int64 (__fastcall *)(__int64, __int64, __int64, void *))g_pfClrCreateManagedInstance_RetAddr)(
             a1,
             a2,
             a3,
             retaddr);
  if ( g_pfClrCreateManagedInstance == (int (*)(const unsigned __int16 *, const struct _GUID *, void **))-1LL )
    g_pfClrCreateManagedInstance = (int (*)(const unsigned __int16 *, const struct _GUID *, void **))GetProcAddress(hModule, "ClrCreateManagedInstance");
  if ( !g_pfClrCreateManagedInstance )
    return 2148734721LL;
  else
    return ((__int64 (__fastcall *)(__int64, __int64, __int64))g_pfClrCreateManagedInstance)(a1, a2, a3);
}

```

## disassembly

```asm
0x180023440  mov     rax, rsp
0x180023443  mov     [rax+8], rbx
0x180023447  mov     [rax+10h], rsi
0x18002344b  push    rdi
0x18002344c  sub     rsp, 30h
0x180023450  mov     rsi, rcx
0x180023453  mov     qword ptr [rax+20h], 0
0x18002345b  lea     rcx, [rax+20h]
0x18002345f  mov     rbx, r8
0x180023462  mov     rdi, rdx
0x180023465  call    ?GetShimImpl@@YA?AW4ShimImplStatus@@PEAPEAUHINSTANCE__@@@Z; GetShimImpl(HINSTANCE__ * *)
0x18002346a  cmp     eax, 1
0x18002346d  jz      loc_180023530
0x180023473  cmp     eax, 3
0x180023476  jnz     short loc_18002348B
0x180023478  mov     r8, rbx
0x18002347b  mov     rdx, rdi
0x18002347e  mov     rcx, rsi
0x180023481  call    ClrCreateManagedInstance
0x180023486  jmp     loc_180023535
0x18002348b  mov     eax, cs:?g_bShimImplDllUninitialized@@3HC; int volatile g_bShimImplDllUninitialized
0x180023491  test    eax, eax
0x180023493  jnz     loc_180023530
0x180023499  mov     rax, cs:?g_pfClrCreateManagedInstance_RetAddr@@3R6AJPEBGAEBU_GUID@@PEAPEAXPEAX@ZEA; long (*g_pfClrCreateManagedInstance_RetAddr)(ushort const *,_GUID const &,void * *,void *)
0x1800234a0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800234a4  jnz     short loc_1800234BF
0x1800234a6  mov     rcx, [rsp+38h+hModule]; hModule
0x1800234ab  lea     rdx, aClrcreatemanag_0; "ClrCreateManagedInstance_RetAddr"
0x1800234b2  call    cs:__imp_GetProcAddress
0x1800234b8  mov     cs:?g_pfClrCreateManagedInstance_RetAddr@@3R6AJPEBGAEBU_GUID@@PEAPEAXPEAX@ZEA, rax; long (*g_pfClrCreateManagedInstance_RetAddr)(ushort const *,_GUID const &,void * *,void *)
0x1800234bf  mov     rax, cs:?g_pfClrCreateManagedInstance_RetAddr@@3R6AJPEBGAEBU_GUID@@PEAPEAXPEAX@ZEA; long (*g_pfClrCreateManagedInstance_RetAddr)(ushort const *,_GUID const &,void * *,void *)
0x1800234c6  test    rax, rax
0x1800234c9  jz      short loc_1800234E7
0x1800234cb  mov     rax, cs:?g_pfClrCreateManagedInstance_RetAddr@@3R6AJPEBGAEBU_GUID@@PEAPEAXPEAX@ZEA; long (*g_pfClrCreateManagedInstance_RetAddr)(ushort const *,_GUID const &,void * *,void *)
0x1800234d2  mov     r8, rbx
0x1800234d5  mov     r9, [rsp+38h]
0x1800234da  mov     rdx, rdi
0x1800234dd  mov     rcx, rsi
0x1800234e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800234e5  jmp     short loc_180023535
0x1800234e7  mov     rax, cs:?g_pfClrCreateManagedInstance@@3R6AJPEBGAEBU_GUID@@PEAPEAX@ZEA; long (*g_pfClrCreateManagedInstance)(ushort const *,_GUID const &,void * *)
0x1800234ee  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800234f2  jnz     short loc_18002350D
0x1800234f4  mov     rcx, [rsp+38h+hModule]; hModule
0x1800234f9  lea     rdx, aClrcreatemanag_1; "ClrCreateManagedInstance"
0x180023500  call    cs:__imp_GetProcAddress
0x180023506  mov     cs:?g_pfClrCreateManagedInstance@@3R6AJPEBGAEBU_GUID@@PEAPEAX@ZEA, rax; long (*g_pfClrCreateManagedInstance)(ushort const *,_GUID const &,void * *)
0x18002350d  mov     rax, cs:?g_pfClrCreateManagedInstance@@3R6AJPEBGAEBU_GUID@@PEAPEAX@ZEA; long (*g_pfClrCreateManagedInstance)(ushort const *,_GUID const &,void * *)
0x180023514  test    rax, rax
0x180023517  jz      short loc_180023530
0x180023519  mov     rax, cs:?g_pfClrCreateManagedInstance@@3R6AJPEBGAEBU_GUID@@PEAPEAX@ZEA; long (*g_pfClrCreateManagedInstance)(ushort const *,_GUID const &,void * *)
0x180023520  mov     r8, rbx
0x180023523  mov     rdx, rdi
0x180023526  mov     rcx, rsi
0x180023529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002352e  jmp     short loc_180023535
0x180023530  mov     eax, 80131701h
0x180023535  mov     rbx, [rsp+38h+arg_0]
0x18002353a  mov     rsi, [rsp+38h+arg_8]
0x18002353f  add     rsp, 30h
0x180023543  pop     rdi
0x180023544  retn
```
