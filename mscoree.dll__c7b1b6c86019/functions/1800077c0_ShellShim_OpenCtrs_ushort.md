# ShellShim_OpenCtrs(ushort *)

- ea: `0x1800077c0`
- end: `0x1800078b6`
- name: `?ShellShim_OpenCtrs@@YAKPEAG@Z`
- size: `246`
- prototype: `unsigned int __fastcall(unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180002a90`
- `0x1800077c0`
- `0x18002b5b8`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180007836`
- `KERNEL32!GetProcAddress` at `0x18000787c`
- `KERNEL32!GetProcAddress` at `0x180007836`
- `KERNEL32!GetProcAddress` at `0x18000787c`

## string_xrefs

- `0x18000782c`: `OpenCtrs_RetAddr`
- `0x180007872`: `OpenCtrs`

## pseudocode

```c
__int64 __fastcall ShellShim_OpenCtrs(unsigned __int16 *a1, int (*a2)(unsigned __int16 *, void *))
{
  HMODULE v2; // rbx
  void *retaddr; // [rsp+28h] [rbp+0h]

  v2 = 0;
  if ( !(_DWORD)g_shimImplStatus )
    InitShimImpl((__int64)a1, a2);
  if ( (_DWORD)g_shimImplStatus == 2 )
    v2 = g_hShimImplInst;
  if ( (_DWORD)g_shimImplStatus == 1 )
    return 2;
  if ( (_DWORD)g_shimImplStatus == 3 )
    return OpenCtrs(a1);
  if ( g_bShimImplDllUninitialized )
    return 2;
  if ( g_pfOpenCtrs_RetAddr == (unsigned int (*)(unsigned __int16 *, void *))-1LL )
    g_pfOpenCtrs_RetAddr = (unsigned int (*)(unsigned __int16 *, void *))GetProcAddress(v2, "OpenCtrs_RetAddr");
  if ( g_pfOpenCtrs_RetAddr )
    return ((__int64 (__fastcall *)(unsigned __int16 *, void *))g_pfOpenCtrs_RetAddr)(a1, retaddr);
  if ( g_pfOpenCtrs == (unsigned int (*)(unsigned __int16 *))-1LL )
    g_pfOpenCtrs = (unsigned int (*)(unsigned __int16 *))GetProcAddress(v2, "OpenCtrs");
  if ( !g_pfOpenCtrs )
    return 2;
  else
    return ((__int64 (__fastcall *)(unsigned __int16 *))g_pfOpenCtrs)(a1);
}

```

## disassembly

```asm
0x1800077c0  mov     [rsp+arg_0], rbx
0x1800077c5  push    rdi
0x1800077c6  sub     rsp, 20h
0x1800077ca  mov     eax, cs:?g_shimImplStatus@@3W4ShimImplStatus@@C; ShimImplStatus volatile g_shimImplStatus
0x1800077d0  xor     ebx, ebx
0x1800077d2  mov     rdi, rcx
0x1800077d5  test    eax, eax
0x1800077d7  jnz     short loc_1800077DE
0x1800077d9  call    ?InitShimImpl@@YAXXZ; InitShimImpl(void)
0x1800077de  mov     eax, cs:?g_shimImplStatus@@3W4ShimImplStatus@@C; ShimImplStatus volatile g_shimImplStatus
0x1800077e4  cmp     eax, 2
0x1800077e7  jnz     short loc_1800077F0
0x1800077e9  mov     rbx, cs:?g_hShimImplInst@@3REAUHINSTANCE__@@EA; HINSTANCE__ * g_hShimImplInst
0x1800077f0  mov     eax, cs:?g_shimImplStatus@@3W4ShimImplStatus@@C; ShimImplStatus volatile g_shimImplStatus
0x1800077f6  cmp     eax, 1
0x1800077f9  jz      loc_1800078A6
0x1800077ff  cmp     eax, 3
0x180007802  jnz     short loc_180007811
0x180007804  mov     rcx, rdi; unsigned __int16 *
0x180007807  call    ?OpenCtrs@@YAKPEAG@Z; OpenCtrs(ushort *)
0x18000780c  jmp     loc_1800078AB
0x180007811  mov     eax, cs:?g_bShimImplDllUninitialized@@3HC; int volatile g_bShimImplDllUninitialized
0x180007817  test    eax, eax
0x180007819  jnz     loc_1800078A6
0x18000781f  mov     rax, cs:?g_pfOpenCtrs_RetAddr@@3R6AKPEAGPEAX@ZEA; ulong (*g_pfOpenCtrs_RetAddr)(ushort *,void *)
0x180007826  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000782a  jnz     short loc_180007843
0x18000782c  lea     rdx, aOpenctrsRetadd; "OpenCtrs_RetAddr"
0x180007833  mov     rcx, rbx; hModule
0x180007836  call    cs:__imp_GetProcAddress
0x18000783c  mov     cs:?g_pfOpenCtrs_RetAddr@@3R6AKPEAGPEAX@ZEA, rax; ulong (*g_pfOpenCtrs_RetAddr)(ushort *,void *)
0x180007843  mov     rax, cs:?g_pfOpenCtrs_RetAddr@@3R6AKPEAGPEAX@ZEA; ulong (*g_pfOpenCtrs_RetAddr)(ushort *,void *)
0x18000784a  test    rax, rax
0x18000784d  jz      short loc_180007865
0x18000784f  mov     rax, cs:?g_pfOpenCtrs_RetAddr@@3R6AKPEAGPEAX@ZEA; ulong (*g_pfOpenCtrs_RetAddr)(ushort *,void *)
0x180007856  mov     rcx, rdi
0x180007859  mov     rdx, [rsp+28h]
0x18000785e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007863  jmp     short loc_1800078AB
0x180007865  mov     rax, cs:?g_pfOpenCtrs@@3R6AKPEAG@ZEA; ulong (*g_pfOpenCtrs)(ushort *)
0x18000786c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180007870  jnz     short loc_180007889
0x180007872  lea     rdx, aOpenctrs_0; "OpenCtrs"
0x180007879  mov     rcx, rbx; hModule
0x18000787c  call    cs:__imp_GetProcAddress
0x180007882  mov     cs:?g_pfOpenCtrs@@3R6AKPEAG@ZEA, rax; ulong (*g_pfOpenCtrs)(ushort *)
0x180007889  mov     rax, cs:?g_pfOpenCtrs@@3R6AKPEAG@ZEA; ulong (*g_pfOpenCtrs)(ushort *)
0x180007890  test    rax, rax
0x180007893  jz      short loc_1800078A6
0x180007895  mov     rax, cs:?g_pfOpenCtrs@@3R6AKPEAG@ZEA; ulong (*g_pfOpenCtrs)(ushort *)
0x18000789c  mov     rcx, rdi
0x18000789f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078a4  jmp     short loc_1800078AB
0x1800078a6  mov     eax, 2
0x1800078ab  mov     rbx, [rsp+28h+arg_0]
0x1800078b0  add     rsp, 20h
0x1800078b4  pop     rdi
0x1800078b5  retn
```
