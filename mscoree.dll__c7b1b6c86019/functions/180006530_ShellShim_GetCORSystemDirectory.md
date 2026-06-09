# ShellShim_GetCORSystemDirectory

- ea: `0x180006530`
- end: `0x180006633`
- name: `ShellShim_GetCORSystemDirectory`
- size: `259`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180002a90`
- `0x180006530`
- `0x18002d658`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800065db`
- `KERNEL32!GetProcAddress` at `0x180006601`
- `KERNEL32!GetProcAddress` at `0x1800065db`
- `KERNEL32!GetProcAddress` at `0x180006601`

## string_xrefs

- `0x1800065d1`: `GetCORSystemDirectory_RetAddr`
- `0x1800065f7`: `GetCORSystemDirectory`

## pseudocode

```c
__int64 __fastcall ShellShim_GetCORSystemDirectory(void *a1, int (*a2)(unsigned __int16 *, void *), __int64 a3)
{
  HMODULE v3; // rbx
  unsigned int v5; // esi
  void *retaddr; // [rsp+58h] [rbp+0h]

  v3 = 0;
  v5 = (unsigned int)a2;
  if ( !(_DWORD)g_shimImplStatus )
    InitShimImpl((__int64)a1, a2);
  if ( (_DWORD)g_shimImplStatus == 2 )
    v3 = g_hShimImplInst;
  if ( (_DWORD)g_shimImplStatus == 1 )
    return 2148734721LL;
  if ( (_DWORD)g_shimImplStatus == 3 )
    return GetCORSystemDirectory(a1);
  if ( g_bShimImplDllUninitialized )
    return 2148734721LL;
  if ( g_pfGetCORSystemDirectory_RetAddr == (int (*)(unsigned __int16 *, unsigned int, unsigned int *, void *))-1LL )
    g_pfGetCORSystemDirectory_RetAddr = (int (*)(unsigned __int16 *, unsigned int, unsigned int *, void *))GetProcAddress(v3, "GetCORSystemDirectory_RetAddr");
  if ( g_pfGetCORSystemDirectory_RetAddr )
    return ((__int64 (__fastcall *)(void *, _QWORD, __int64, void *))g_pfGetCORSystemDirectory_RetAddr)(
             a1,
             v5,
             a3,
             retaddr);
  if ( g_pfGetCORSystemDirectory == (int (*)(unsigned __int16 *, unsigned int, unsigned int *))-1LL )
    g_pfGetCORSystemDirectory = (int (*)(unsigned __int16 *, unsigned int, unsigned int *))GetProcAddress(
                                                                                             v3,
                                                                                             "GetCORSystemDirectory");
  if ( !g_pfGetCORSystemDirectory )
    return 2148734721LL;
  return ((__int64 (__fastcall *)(void *, _QWORD, __int64))g_pfGetCORSystemDirectory)(a1, v5, a3);
}

```

## disassembly

```asm
0x180006530  push    rbx
0x180006532  push    rbp
0x180006533  push    rsi
0x180006534  push    rdi
0x180006535  sub     rsp, 38h
0x180006539  mov     eax, cs:?g_shimImplStatus@@3W4ShimImplStatus@@C; ShimImplStatus volatile g_shimImplStatus
0x18000653f  xor     ebx, ebx
0x180006541  mov     rdi, r8
0x180006544  mov     esi, edx
0x180006546  mov     rbp, rcx
0x180006549  test    eax, eax
0x18000654b  jz      short loc_1800065BB
0x18000654d  mov     eax, cs:?g_shimImplStatus@@3W4ShimImplStatus@@C; ShimImplStatus volatile g_shimImplStatus
0x180006553  cmp     eax, 2
0x180006556  jnz     short loc_18000655F
0x180006558  mov     rbx, cs:?g_hShimImplInst@@3REAUHINSTANCE__@@EA; HINSTANCE__ * g_hShimImplInst
0x18000655f  mov     eax, cs:?g_shimImplStatus@@3W4ShimImplStatus@@C; ShimImplStatus volatile g_shimImplStatus
0x180006565  cmp     eax, 1
0x180006568  jz      short loc_1800065B4
0x18000656a  cmp     eax, 3
0x18000656d  jz      short loc_1800065C2
0x18000656f  mov     eax, cs:?g_bShimImplDllUninitialized@@3HC; int volatile g_bShimImplDllUninitialized
0x180006575  test    eax, eax
0x180006577  jnz     short loc_1800065B4
0x180006579  mov     rax, cs:?g_pfGetCORSystemDirectory_RetAddr@@3R6AJPEAGKPEAKPEAX@ZEA; long (*g_pfGetCORSystemDirectory_RetAddr)(ushort *,ulong,ulong *,void *)
0x180006580  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180006584  jz      short loc_1800065D1
0x180006586  mov     rax, cs:?g_pfGetCORSystemDirectory_RetAddr@@3R6AJPEAGKPEAKPEAX@ZEA; long (*g_pfGetCORSystemDirectory_RetAddr)(ushort *,ulong,ulong *,void *)
0x18000658d  test    rax, rax
0x180006590  jz      short loc_1800065EA
0x180006592  mov     rax, cs:?g_pfGetCORSystemDirectory_RetAddr@@3R6AJPEAGKPEAKPEAX@ZEA; long (*g_pfGetCORSystemDirectory_RetAddr)(ushort *,ulong,ulong *,void *)
0x180006599  mov     r8, rdi
0x18000659c  mov     r9, [rsp+58h]
0x1800065a1  mov     edx, esi
0x1800065a3  mov     rcx, rbp
0x1800065a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065ab  add     rsp, 38h
0x1800065af  pop     rdi
0x1800065b0  pop     rsi
0x1800065b1  pop     rbp
0x1800065b2  pop     rbx
0x1800065b3  retn
0x1800065b4  mov     eax, 80131701h
0x1800065b9  jmp     short loc_1800065AB
0x1800065bb  call    ?InitShimImpl@@YAXXZ; InitShimImpl(void)
0x1800065c0  jmp     short loc_18000654D
0x1800065c2  mov     r8, rdi
0x1800065c5  mov     edx, esi
0x1800065c7  mov     rcx, rbp; void *
0x1800065ca  call    GetCORSystemDirectory
0x1800065cf  jmp     short loc_1800065AB
0x1800065d1  lea     rdx, aGetcorsystemdi_0; "GetCORSystemDirectory_RetAddr"
0x1800065d8  mov     rcx, rbx; hModule
0x1800065db  call    cs:__imp_GetProcAddress
0x1800065e1  mov     cs:?g_pfGetCORSystemDirectory_RetAddr@@3R6AJPEAGKPEAKPEAX@ZEA, rax; long (*g_pfGetCORSystemDirectory_RetAddr)(ushort *,ulong,ulong *,void *)
0x1800065e8  jmp     short loc_180006586
0x1800065ea  mov     rax, cs:?g_pfGetCORSystemDirectory@@3R6AJPEAGKPEAK@ZEA; long (*g_pfGetCORSystemDirectory)(ushort *,ulong,ulong *)
0x1800065f1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800065f5  jnz     short loc_18000660E
0x1800065f7  lea     rdx, aGetcorsystemdi_1; "GetCORSystemDirectory"
0x1800065fe  mov     rcx, rbx; hModule
0x180006601  call    cs:__imp_GetProcAddress
0x180006607  mov     cs:?g_pfGetCORSystemDirectory@@3R6AJPEAGKPEAK@ZEA, rax; long (*g_pfGetCORSystemDirectory)(ushort *,ulong,ulong *)
0x18000660e  mov     rax, cs:?g_pfGetCORSystemDirectory@@3R6AJPEAGKPEAK@ZEA; long (*g_pfGetCORSystemDirectory)(ushort *,ulong,ulong *)
0x180006615  test    rax, rax
0x180006618  jz      short loc_1800065B4
0x18000661a  mov     rax, cs:?g_pfGetCORSystemDirectory@@3R6AJPEAGKPEAK@ZEA; long (*g_pfGetCORSystemDirectory)(ushort *,ulong,ulong *)
0x180006621  mov     r8, rdi
0x180006624  mov     edx, esi
0x180006626  mov     rcx, rbp
0x180006629  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000662e  jmp     loc_1800065AB
```
