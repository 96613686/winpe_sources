# ShellShim_CorBindToRuntimeByPathEx

- ea: `0x180023d40`
- end: `0x180023e45`
- name: `ShellShim_CorBindToRuntimeByPathEx`
- size: `261`
- prototype: `__int64 __fastcall(unsigned __int16 *, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180001c10`
- `0x180023d40`
- `0x18002c748`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180023db2`
- `KERNEL32!GetProcAddress` at `0x180023e00`
- `KERNEL32!GetProcAddress` at `0x180023db2`
- `KERNEL32!GetProcAddress` at `0x180023e00`

## string_xrefs

- `0x180023dab`: `CorBindToRuntimeByPathEx_RetAddr`
- `0x180023df9`: `CorBindToRuntimeByPathEx`

## pseudocode

```c
__int64 __fastcall ShellShim_CorBindToRuntimeByPathEx(unsigned __int16 *a1, int *a2, unsigned int a3)
{
  int ShimImpl; // eax
  void *retaddr; // [rsp+38h] [rbp+0h]
  HMODULE hModule; // [rsp+58h] [rbp+20h] BYREF

  hModule = 0;
  ShimImpl = GetShimImpl(&hModule);
  if ( ShimImpl == 1 )
    return 2148734721LL;
  if ( ShimImpl == 3 )
    return CorBindToRuntimeByPathEx(a1, a2);
  if ( g_bShimImplDllUninitialized )
    return 2148734721LL;
  if ( g_pfCorBindToRuntimeByPathEx_RetAddr == (int (*)(const unsigned __int16 *, int *, unsigned int, void *))-1LL )
    g_pfCorBindToRuntimeByPathEx_RetAddr = (int (*)(const unsigned __int16 *, int *, unsigned int, void *))GetProcAddress(hModule, "CorBindToRuntimeByPathEx_RetAddr");
  if ( g_pfCorBindToRuntimeByPathEx_RetAddr )
    return ((__int64 (__fastcall *)(unsigned __int16 *, int *, _QWORD, void *))g_pfCorBindToRuntimeByPathEx_RetAddr)(
             a1,
             a2,
             a3,
             retaddr);
  if ( g_pfCorBindToRuntimeByPathEx == (int (*)(const unsigned __int16 *, int *, unsigned int))-1LL )
    g_pfCorBindToRuntimeByPathEx = (int (*)(const unsigned __int16 *, int *, unsigned int))GetProcAddress(
                                                                                             hModule,
                                                                                             "CorBindToRuntimeByPathEx");
  if ( !g_pfCorBindToRuntimeByPathEx )
    return 2148734721LL;
  else
    return ((__int64 (__fastcall *)(unsigned __int16 *, int *, _QWORD))g_pfCorBindToRuntimeByPathEx)(a1, a2, a3);
}

```

## disassembly

```asm
0x180023d40  mov     rax, rsp
0x180023d43  mov     [rax+8], rbx
0x180023d47  mov     [rax+10h], rsi
0x180023d4b  push    rdi
0x180023d4c  sub     rsp, 30h
0x180023d50  mov     rsi, rcx
0x180023d53  mov     qword ptr [rax+20h], 0
0x180023d5b  lea     rcx, [rax+20h]
0x180023d5f  mov     ebx, r8d
0x180023d62  mov     rdi, rdx
0x180023d65  call    ?GetShimImpl@@YA?AW4ShimImplStatus@@PEAPEAUHINSTANCE__@@@Z; GetShimImpl(HINSTANCE__ * *)
0x180023d6a  cmp     eax, 1
0x180023d6d  jz      loc_180023E30
0x180023d73  cmp     eax, 3
0x180023d76  jnz     short loc_180023D8B
0x180023d78  mov     r8d, ebx
0x180023d7b  mov     rdx, rdi; int *
0x180023d7e  mov     rcx, rsi; unsigned __int16 *
0x180023d81  call    CorBindToRuntimeByPathEx
0x180023d86  jmp     loc_180023E35
0x180023d8b  mov     eax, cs:?g_bShimImplDllUninitialized@@3HC; int volatile g_bShimImplDllUninitialized
0x180023d91  test    eax, eax
0x180023d93  jnz     loc_180023E30
0x180023d99  mov     rax, cs:?g_pfCorBindToRuntimeByPathEx_RetAddr@@3R6AJPEBGPEAHKPEAX@ZEA; long (*g_pfCorBindToRuntimeByPathEx_RetAddr)(ushort const *,int *,ulong,void *)
0x180023da0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180023da4  jnz     short loc_180023DBF
0x180023da6  mov     rcx, [rsp+38h+hModule]; hModule
0x180023dab  lea     rdx, aCorbindtorunti_8; "CorBindToRuntimeByPathEx_RetAddr"
0x180023db2  call    cs:__imp_GetProcAddress
0x180023db8  mov     cs:?g_pfCorBindToRuntimeByPathEx_RetAddr@@3R6AJPEBGPEAHKPEAX@ZEA, rax; long (*g_pfCorBindToRuntimeByPathEx_RetAddr)(ushort const *,int *,ulong,void *)
0x180023dbf  mov     rax, cs:?g_pfCorBindToRuntimeByPathEx_RetAddr@@3R6AJPEBGPEAHKPEAX@ZEA; long (*g_pfCorBindToRuntimeByPathEx_RetAddr)(ushort const *,int *,ulong,void *)
0x180023dc6  test    rax, rax
0x180023dc9  jz      short loc_180023DE7
0x180023dcb  mov     rax, cs:?g_pfCorBindToRuntimeByPathEx_RetAddr@@3R6AJPEBGPEAHKPEAX@ZEA; long (*g_pfCorBindToRuntimeByPathEx_RetAddr)(ushort const *,int *,ulong,void *)
0x180023dd2  mov     r8d, ebx
0x180023dd5  mov     r9, [rsp+38h]
0x180023dda  mov     rdx, rdi
0x180023ddd  mov     rcx, rsi
0x180023de0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023de5  jmp     short loc_180023E35
0x180023de7  mov     rax, cs:?g_pfCorBindToRuntimeByPathEx@@3R6AJPEBGPEAHK@ZEA; long (*g_pfCorBindToRuntimeByPathEx)(ushort const *,int *,ulong)
0x180023dee  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180023df2  jnz     short loc_180023E0D
0x180023df4  mov     rcx, [rsp+38h+hModule]; hModule
0x180023df9  lea     rdx, aCorbindtorunti_15; "CorBindToRuntimeByPathEx"
0x180023e00  call    cs:__imp_GetProcAddress
0x180023e06  mov     cs:?g_pfCorBindToRuntimeByPathEx@@3R6AJPEBGPEAHK@ZEA, rax; long (*g_pfCorBindToRuntimeByPathEx)(ushort const *,int *,ulong)
0x180023e0d  mov     rax, cs:?g_pfCorBindToRuntimeByPathEx@@3R6AJPEBGPEAHK@ZEA; long (*g_pfCorBindToRuntimeByPathEx)(ushort const *,int *,ulong)
0x180023e14  test    rax, rax
0x180023e17  jz      short loc_180023E30
0x180023e19  mov     rax, cs:?g_pfCorBindToRuntimeByPathEx@@3R6AJPEBGPEAHK@ZEA; long (*g_pfCorBindToRuntimeByPathEx)(ushort const *,int *,ulong)
0x180023e20  mov     r8d, ebx
0x180023e23  mov     rdx, rdi
0x180023e26  mov     rcx, rsi
0x180023e29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e2e  jmp     short loc_180023E35
0x180023e30  mov     eax, 80131701h
0x180023e35  mov     rbx, [rsp+38h+arg_0]
0x180023e3a  mov     rsi, [rsp+38h+arg_8]
0x180023e3f  add     rsp, 30h
0x180023e43  pop     rdi
0x180023e44  retn
```
