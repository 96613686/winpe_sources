# ShellShim_CorBindToRuntimeByPath

- ea: `0x180023c40`
- end: `0x180023d30`
- name: `ShellShim_CorBindToRuntimeByPath`
- size: `240`
- prototype: `__int64 __fastcall(unsigned __int16 *, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180001c10`
- `0x180023c40`
- `0x18002c468`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180023ca8`
- `KERNEL32!GetProcAddress` at `0x180023cf3`
- `KERNEL32!GetProcAddress` at `0x180023ca8`
- `KERNEL32!GetProcAddress` at `0x180023cf3`

## string_xrefs

- `0x180023ca1`: `CorBindToRuntimeByPath_RetAddr`
- `0x180023cec`: `CorBindToRuntimeByPath`

## pseudocode

```c
__int64 __fastcall ShellShim_CorBindToRuntimeByPath(unsigned __int16 *a1, int *a2)
{
  int ShimImpl; // eax
  void *retaddr; // [rsp+28h] [rbp+0h]
  HMODULE hModule; // [rsp+40h] [rbp+18h] BYREF

  hModule = 0;
  ShimImpl = GetShimImpl(&hModule);
  if ( ShimImpl == 1 )
    return 2148734721LL;
  if ( ShimImpl == 3 )
    return CorBindToRuntimeByPath(a1, a2);
  if ( g_bShimImplDllUninitialized )
    return 2148734721LL;
  if ( g_pfCorBindToRuntimeByPath_RetAddr == (int (*)(const unsigned __int16 *, int *, void *))-1LL )
    g_pfCorBindToRuntimeByPath_RetAddr = (int (*)(const unsigned __int16 *, int *, void *))GetProcAddress(
                                                                                             hModule,
                                                                                             "CorBindToRuntimeByPath_RetAddr");
  if ( g_pfCorBindToRuntimeByPath_RetAddr )
    return ((__int64 (__fastcall *)(unsigned __int16 *, int *, void *))g_pfCorBindToRuntimeByPath_RetAddr)(
             a1,
             a2,
             retaddr);
  if ( g_pfCorBindToRuntimeByPath == (int (*)(const unsigned __int16 *, int *))-1LL )
    g_pfCorBindToRuntimeByPath = (int (*)(const unsigned __int16 *, int *))GetProcAddress(
                                                                             hModule,
                                                                             "CorBindToRuntimeByPath");
  if ( !g_pfCorBindToRuntimeByPath )
    return 2148734721LL;
  else
    return ((__int64 (__fastcall *)(unsigned __int16 *, int *))g_pfCorBindToRuntimeByPath)(a1, a2);
}

```

## disassembly

```asm
0x180023c40  mov     [rsp+arg_0], rbx
0x180023c45  push    rdi
0x180023c46  sub     rsp, 20h
0x180023c4a  mov     rdi, rcx
0x180023c4d  mov     [rsp+28h+hModule], 0
0x180023c56  lea     rcx, [rsp+28h+hModule]
0x180023c5b  mov     rbx, rdx
0x180023c5e  call    ?GetShimImpl@@YA?AW4ShimImplStatus@@PEAPEAUHINSTANCE__@@@Z; GetShimImpl(HINSTANCE__ * *)
0x180023c63  cmp     eax, 1
0x180023c66  jz      loc_180023D20
0x180023c6c  cmp     eax, 3
0x180023c6f  jnz     short loc_180023C81
0x180023c71  mov     rdx, rbx; int *
0x180023c74  mov     rcx, rdi; unsigned __int16 *
0x180023c77  call    CorBindToRuntimeByPath
0x180023c7c  jmp     loc_180023D25
0x180023c81  mov     eax, cs:?g_bShimImplDllUninitialized@@3HC; int volatile g_bShimImplDllUninitialized
0x180023c87  test    eax, eax
0x180023c89  jnz     loc_180023D20
0x180023c8f  mov     rax, cs:?g_pfCorBindToRuntimeByPath_RetAddr@@3R6AJPEBGPEAHPEAX@ZEA; long (*g_pfCorBindToRuntimeByPath_RetAddr)(ushort const *,int *,void *)
0x180023c96  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180023c9a  jnz     short loc_180023CB5
0x180023c9c  mov     rcx, [rsp+28h+hModule]; hModule
0x180023ca1  lea     rdx, aCorbindtorunti_9; "CorBindToRuntimeByPath_RetAddr"
0x180023ca8  call    cs:__imp_GetProcAddress
0x180023cae  mov     cs:?g_pfCorBindToRuntimeByPath_RetAddr@@3R6AJPEBGPEAHPEAX@ZEA, rax; long (*g_pfCorBindToRuntimeByPath_RetAddr)(ushort const *,int *,void *)
0x180023cb5  mov     rax, cs:?g_pfCorBindToRuntimeByPath_RetAddr@@3R6AJPEBGPEAHPEAX@ZEA; long (*g_pfCorBindToRuntimeByPath_RetAddr)(ushort const *,int *,void *)
0x180023cbc  test    rax, rax
0x180023cbf  jz      short loc_180023CDA
0x180023cc1  mov     rax, cs:?g_pfCorBindToRuntimeByPath_RetAddr@@3R6AJPEBGPEAHPEAX@ZEA; long (*g_pfCorBindToRuntimeByPath_RetAddr)(ushort const *,int *,void *)
0x180023cc8  mov     rdx, rbx
0x180023ccb  mov     r8, [rsp+28h]
0x180023cd0  mov     rcx, rdi
0x180023cd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023cd8  jmp     short loc_180023D25
0x180023cda  mov     rax, cs:?g_pfCorBindToRuntimeByPath@@3R6AJPEBGPEAH@ZEA; long (*g_pfCorBindToRuntimeByPath)(ushort const *,int *)
0x180023ce1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180023ce5  jnz     short loc_180023D00
0x180023ce7  mov     rcx, [rsp+28h+hModule]; hModule
0x180023cec  lea     rdx, aCorbindtorunti_14; "CorBindToRuntimeByPath"
0x180023cf3  call    cs:__imp_GetProcAddress
0x180023cf9  mov     cs:?g_pfCorBindToRuntimeByPath@@3R6AJPEBGPEAH@ZEA, rax; long (*g_pfCorBindToRuntimeByPath)(ushort const *,int *)
0x180023d00  mov     rax, cs:?g_pfCorBindToRuntimeByPath@@3R6AJPEBGPEAH@ZEA; long (*g_pfCorBindToRuntimeByPath)(ushort const *,int *)
0x180023d07  test    rax, rax
0x180023d0a  jz      short loc_180023D20
0x180023d0c  mov     rax, cs:?g_pfCorBindToRuntimeByPath@@3R6AJPEBGPEAH@ZEA; long (*g_pfCorBindToRuntimeByPath)(ushort const *,int *)
0x180023d13  mov     rdx, rbx
0x180023d16  mov     rcx, rdi
0x180023d19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023d1e  jmp     short loc_180023D25
0x180023d20  mov     eax, 80131701h
0x180023d25  mov     rbx, [rsp+28h+arg_0]
0x180023d2a  add     rsp, 20h
0x180023d2e  pop     rdi
0x180023d2f  retn
```
