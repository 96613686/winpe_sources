# ShellShim_TranslateSecurityAttributes

- ea: `0x180028780`
- end: `0x1800288d8`
- name: `ShellShim_TranslateSecurityAttributes`
- size: `344`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001c10`
- `0x180028780`
- `0x18002eef8`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18002880d`
- `KERNEL32!GetProcAddress` at `0x18002887d`
- `KERNEL32!GetProcAddress` at `0x18002880d`
- `KERNEL32!GetProcAddress` at `0x18002887d`

## string_xrefs

- `0x180028806`: `TranslateSecurityAttributes_RetAddr`
- `0x180028876`: `TranslateSecurityAttributes`

## pseudocode

```c
__int64 __fastcall ShellShim_TranslateSecurityAttributes(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  int ShimImpl; // eax
  HMODULE hModule[7]; // [rsp+40h] [rbp-38h] BYREF
  void *retaddr; // [rsp+78h] [rbp+0h]

  hModule[0] = 0;
  ShimImpl = GetShimImpl(hModule);
  if ( ShimImpl == 1 )
    return 2148734721LL;
  if ( ShimImpl == 3 )
    return TranslateSecurityAttributes(a1, a2, a3, a4, a5, a6);
  if ( g_bShimImplDllUninitialized )
    return 2148734721LL;
  if ( g_pfTranslateSecurityAttributes_RetAddr == (int (*)(struct CORSEC_ATTRSET *, unsigned __int8 **, unsigned int *, unsigned __int8 **, unsigned int *, unsigned int *, void *))-1LL )
    g_pfTranslateSecurityAttributes_RetAddr = (int (*)(struct CORSEC_ATTRSET *, unsigned __int8 **, unsigned int *, unsigned __int8 **, unsigned int *, unsigned int *, void *))GetProcAddress(hModule[0], "TranslateSecurityAttributes_RetAddr");
  if ( g_pfTranslateSecurityAttributes_RetAddr )
    return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64, __int64, __int64, void *))g_pfTranslateSecurityAttributes_RetAddr)(
             a1,
             a2,
             a3,
             a4,
             a5,
             a6,
             retaddr);
  if ( g_pfTranslateSecurityAttributes == (int (*)(struct CORSEC_ATTRSET *, unsigned __int8 **, unsigned int *, unsigned __int8 **, unsigned int *, unsigned int *))-1LL )
    g_pfTranslateSecurityAttributes = (int (*)(struct CORSEC_ATTRSET *, unsigned __int8 **, unsigned int *, unsigned __int8 **, unsigned int *, unsigned int *))GetProcAddress(hModule[0], "TranslateSecurityAttributes");
  if ( !g_pfTranslateSecurityAttributes )
    return 2148734721LL;
  else
    return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64, __int64, __int64))g_pfTranslateSecurityAttributes)(
             a1,
             a2,
             a3,
             a4,
             a5,
             a6);
}

```

## disassembly

```asm
0x180028780  push    rbx
0x180028782  push    rbp
0x180028783  push    rsi
0x180028784  push    rdi
0x180028785  sub     rsp, 58h
0x180028789  mov     rbp, rcx
0x18002878c  mov     [rsp+78h+hModule], 0
0x180028795  lea     rcx, [rsp+78h+hModule]
0x18002879a  mov     rbx, r9
0x18002879d  mov     rdi, r8
0x1800287a0  mov     rsi, rdx
0x1800287a3  call    ?GetShimImpl@@YA?AW4ShimImplStatus@@PEAPEAUHINSTANCE__@@@Z; GetShimImpl(HINSTANCE__ * *)
0x1800287a8  cmp     eax, 1
0x1800287ab  jz      loc_1800288CA
0x1800287b1  cmp     eax, 3
0x1800287b4  jnz     short loc_1800287E6
0x1800287b6  mov     rax, [rsp+78h+arg_28]
0x1800287be  mov     r9, rbx
0x1800287c1  mov     [rsp+78h+var_50], rax
0x1800287c6  mov     r8, rdi
0x1800287c9  mov     rax, [rsp+78h+arg_20]
0x1800287d1  mov     rdx, rsi
0x1800287d4  mov     rcx, rbp
0x1800287d7  mov     [rsp+78h+var_58], rax
0x1800287dc  call    TranslateSecurityAttributes
0x1800287e1  jmp     loc_1800288CF
0x1800287e6  mov     eax, cs:?g_bShimImplDllUninitialized@@3HC; int volatile g_bShimImplDllUninitialized
0x1800287ec  test    eax, eax
0x1800287ee  jnz     loc_1800288CA
0x1800287f4  mov     rax, cs:?g_pfTranslateSecurityAttributes_RetAddr@@3R6AJPEAVCORSEC_ATTRSET@@PEAPEAEPEAK122PEAX@ZEA; long (*g_pfTranslateSecurityAttributes_RetAddr)(CORSEC_ATTRSET *,uchar * *,ulong *,uchar * *,ulong *,ulong *,void *)
0x1800287fb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800287ff  jnz     short loc_18002881A
0x180028801  mov     rcx, [rsp+78h+hModule]; hModule
0x180028806  lea     rdx, aTranslatesecur_0; "TranslateSecurityAttributes_RetAddr"
0x18002880d  call    cs:__imp_GetProcAddress
0x180028813  mov     cs:?g_pfTranslateSecurityAttributes_RetAddr@@3R6AJPEAVCORSEC_ATTRSET@@PEAPEAEPEAK122PEAX@ZEA, rax; long (*g_pfTranslateSecurityAttributes_RetAddr)(CORSEC_ATTRSET *,uchar * *,ulong *,uchar * *,ulong *,ulong *,void *)
0x18002881a  mov     rax, cs:?g_pfTranslateSecurityAttributes_RetAddr@@3R6AJPEAVCORSEC_ATTRSET@@PEAPEAEPEAK122PEAX@ZEA; long (*g_pfTranslateSecurityAttributes_RetAddr)(CORSEC_ATTRSET *,uchar * *,ulong *,uchar * *,ulong *,ulong *,void *)
0x180028821  test    rax, rax
0x180028824  jz      short loc_180028864
0x180028826  mov     rax, cs:?g_pfTranslateSecurityAttributes_RetAddr@@3R6AJPEAVCORSEC_ATTRSET@@PEAPEAEPEAK122PEAX@ZEA; long (*g_pfTranslateSecurityAttributes_RetAddr)(CORSEC_ATTRSET *,uchar * *,ulong *,uchar * *,ulong *,ulong *,void *)
0x18002882d  mov     r9, rbx
0x180028830  mov     rcx, [rsp+78h]
0x180028835  mov     r8, rdi
0x180028838  mov     [rsp+78h+var_48], rcx
0x18002883d  mov     rdx, rsi
0x180028840  mov     rcx, [rsp+78h+arg_28]
0x180028848  mov     [rsp+78h+var_50], rcx
0x18002884d  mov     rcx, [rsp+78h+arg_20]
0x180028855  mov     [rsp+78h+var_58], rcx
0x18002885a  mov     rcx, rbp
0x18002885d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028862  jmp     short loc_1800288CF
0x180028864  mov     rax, cs:?g_pfTranslateSecurityAttributes@@3R6AJPEAVCORSEC_ATTRSET@@PEAPEAEPEAK122@ZEA; long (*g_pfTranslateSecurityAttributes)(CORSEC_ATTRSET *,uchar * *,ulong *,uchar * *,ulong *,ulong *)
0x18002886b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002886f  jnz     short loc_18002888A
0x180028871  mov     rcx, [rsp+78h+hModule]; hModule
0x180028876  lea     rdx, aTranslatesecur_1; "TranslateSecurityAttributes"
0x18002887d  call    cs:__imp_GetProcAddress
0x180028883  mov     cs:?g_pfTranslateSecurityAttributes@@3R6AJPEAVCORSEC_ATTRSET@@PEAPEAEPEAK122@ZEA, rax; long (*g_pfTranslateSecurityAttributes)(CORSEC_ATTRSET *,uchar * *,ulong *,uchar * *,ulong *,ulong *)
0x18002888a  mov     rax, cs:?g_pfTranslateSecurityAttributes@@3R6AJPEAVCORSEC_ATTRSET@@PEAPEAEPEAK122@ZEA; long (*g_pfTranslateSecurityAttributes)(CORSEC_ATTRSET *,uchar * *,ulong *,uchar * *,ulong *,ulong *)
0x180028891  test    rax, rax
0x180028894  jz      short loc_1800288CA
0x180028896  mov     rcx, [rsp+78h+arg_28]
0x18002889e  mov     r9, rbx
0x1800288a1  mov     rax, cs:?g_pfTranslateSecurityAttributes@@3R6AJPEAVCORSEC_ATTRSET@@PEAPEAEPEAK122@ZEA; long (*g_pfTranslateSecurityAttributes)(CORSEC_ATTRSET *,uchar * *,ulong *,uchar * *,ulong *,ulong *)
0x1800288a8  mov     r8, rdi
0x1800288ab  mov     [rsp+78h+var_50], rcx
0x1800288b0  mov     rdx, rsi
0x1800288b3  mov     rcx, [rsp+78h+arg_20]
0x1800288bb  mov     [rsp+78h+var_58], rcx
0x1800288c0  mov     rcx, rbp
0x1800288c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800288c8  jmp     short loc_1800288CF
0x1800288ca  mov     eax, 80131701h
0x1800288cf  add     rsp, 58h
0x1800288d3  pop     rdi
0x1800288d4  pop     rsi
0x1800288d5  pop     rbp
0x1800288d6  pop     rbx
0x1800288d7  retn
```
