# ShellShim_StrongNameTokenFromAssemblyEx

- ea: `0x180028530`
- end: `0x18002865e`
- name: `ShellShim_StrongNameTokenFromAssemblyEx`
- size: `302`
- prototype: `BOOLEAN __stdcall(LPCWSTR wszFilePath, BYTE **ppbStrongNameToken, ULONG *pcbStrongNameToken, BYTE **ppbPublicKeyBlob, ULONG *pcbPublicKeyBlob)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180001c10`
- `0x180028530`
- `0x18002eda8`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800285b0`
- `KERNEL32!GetProcAddress` at `0x180028613`
- `KERNEL32!GetProcAddress` at `0x1800285b0`
- `KERNEL32!GetProcAddress` at `0x180028613`

## string_xrefs

- `0x1800285a9`: `StrongNameTokenFromAssemblyEx_RetAddr`
- `0x18002860c`: `StrongNameTokenFromAssemblyEx`

## pseudocode

```c
BOOLEAN __stdcall ShellShim_StrongNameTokenFromAssemblyEx(
        LPCWSTR wszFilePath,
        BYTE **ppbStrongNameToken,
        ULONG *pcbStrongNameToken,
        BYTE **ppbPublicKeyBlob,
        ULONG *pcbPublicKeyBlob)
{
  int ShimImpl; // eax
  HMODULE hModule[7]; // [rsp+40h] [rbp-38h] BYREF
  void *retaddr; // [rsp+78h] [rbp+0h]

  hModule[0] = 0;
  ShimImpl = GetShimImpl(hModule);
  if ( ShimImpl == 1 )
    return 0;
  if ( ShimImpl == 3 )
    return StrongNameTokenFromAssemblyEx(
             wszFilePath,
             ppbStrongNameToken,
             pcbStrongNameToken,
             ppbPublicKeyBlob,
             pcbPublicKeyBlob);
  if ( g_bShimImplDllUninitialized )
    return 0;
  if ( g_pfStrongNameTokenFromAssemblyEx_RetAddr == (unsigned int (*)(const unsigned __int16 *, unsigned __int8 **, unsigned int *, unsigned __int8 **, unsigned int *, void *))-1LL )
    g_pfStrongNameTokenFromAssemblyEx_RetAddr = (unsigned int (*)(const unsigned __int16 *, unsigned __int8 **, unsigned int *, unsigned __int8 **, unsigned int *, void *))GetProcAddress(hModule[0], "StrongNameTokenFromAssemblyEx_RetAddr");
  if ( g_pfStrongNameTokenFromAssemblyEx_RetAddr )
    return ((__int64 (__fastcall *)(LPCWSTR, BYTE **, ULONG *, BYTE **, ULONG *, void *))g_pfStrongNameTokenFromAssemblyEx_RetAddr)(
             wszFilePath,
             ppbStrongNameToken,
             pcbStrongNameToken,
             ppbPublicKeyBlob,
             pcbPublicKeyBlob,
             retaddr);
  if ( g_pfStrongNameTokenFromAssemblyEx == (unsigned int (*)(const unsigned __int16 *, unsigned __int8 **, unsigned int *, unsigned __int8 **, unsigned int *))-1LL )
    g_pfStrongNameTokenFromAssemblyEx = (unsigned int (*)(const unsigned __int16 *, unsigned __int8 **, unsigned int *, unsigned __int8 **, unsigned int *))GetProcAddress(hModule[0], "StrongNameTokenFromAssemblyEx");
  if ( !g_pfStrongNameTokenFromAssemblyEx )
    return 0;
  else
    return ((__int64 (__fastcall *)(LPCWSTR, BYTE **, ULONG *, BYTE **, ULONG *))g_pfStrongNameTokenFromAssemblyEx)(
             wszFilePath,
             ppbStrongNameToken,
             pcbStrongNameToken,
             ppbPublicKeyBlob,
             pcbPublicKeyBlob);
}

```

## disassembly

```asm
0x180028530  push    rbx
0x180028532  push    rbp
0x180028533  push    rsi
0x180028534  push    rdi
0x180028535  sub     rsp, 58h
0x180028539  mov     rbp, rcx
0x18002853c  mov     [rsp+78h+hModule], 0
0x180028545  lea     rcx, [rsp+78h+hModule]
0x18002854a  mov     rbx, r9
0x18002854d  mov     rdi, r8
0x180028550  mov     rsi, rdx
0x180028553  call    ?GetShimImpl@@YA?AW4ShimImplStatus@@PEAPEAUHINSTANCE__@@@Z; GetShimImpl(HINSTANCE__ * *)
0x180028558  cmp     eax, 1
0x18002855b  jz      loc_180028653
0x180028561  cmp     eax, 3
0x180028564  jnz     short loc_180028589
0x180028566  mov     rax, [rsp+78h+pcbPublicKeyBlob]
0x18002856e  mov     r9, rbx; ppbPublicKeyBlob
0x180028571  mov     r8, rdi; pcbStrongNameToken
0x180028574  mov     [rsp+78h+var_58], rax; pcbPublicKeyBlob
0x180028579  mov     rdx, rsi; ppbStrongNameToken
0x18002857c  mov     rcx, rbp; wszFilePath
0x18002857f  call    StrongNameTokenFromAssemblyEx
0x180028584  jmp     loc_180028655
0x180028589  mov     eax, cs:?g_bShimImplDllUninitialized@@3HC; int volatile g_bShimImplDllUninitialized
0x18002858f  test    eax, eax
0x180028591  jnz     loc_180028653
0x180028597  mov     rax, cs:?g_pfStrongNameTokenFromAssemblyEx_RetAddr@@3R6AKPEBGPEAPEAEPEAK12PEAX@ZEA; ulong (*g_pfStrongNameTokenFromAssemblyEx_RetAddr)(ushort const *,uchar * *,ulong *,uchar * *,ulong *,void *)
0x18002859e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800285a2  jnz     short loc_1800285BD
0x1800285a4  mov     rcx, [rsp+78h+hModule]; hModule
0x1800285a9  lea     rdx, aStrongnametoke_5; "StrongNameTokenFromAssemblyEx_RetAddr"
0x1800285b0  call    cs:__imp_GetProcAddress
0x1800285b6  mov     cs:?g_pfStrongNameTokenFromAssemblyEx_RetAddr@@3R6AKPEBGPEAPEAEPEAK12PEAX@ZEA, rax; ulong (*g_pfStrongNameTokenFromAssemblyEx_RetAddr)(ushort const *,uchar * *,ulong *,uchar * *,ulong *,void *)
0x1800285bd  mov     rax, cs:?g_pfStrongNameTokenFromAssemblyEx_RetAddr@@3R6AKPEBGPEAPEAEPEAK12PEAX@ZEA; ulong (*g_pfStrongNameTokenFromAssemblyEx_RetAddr)(ushort const *,uchar * *,ulong *,uchar * *,ulong *,void *)
0x1800285c4  test    rax, rax
0x1800285c7  jz      short loc_1800285FA
0x1800285c9  mov     rax, cs:?g_pfStrongNameTokenFromAssemblyEx_RetAddr@@3R6AKPEBGPEAPEAEPEAK12PEAX@ZEA; ulong (*g_pfStrongNameTokenFromAssemblyEx_RetAddr)(ushort const *,uchar * *,ulong *,uchar * *,ulong *,void *)
0x1800285d0  mov     r9, rbx
0x1800285d3  mov     rcx, [rsp+78h]
0x1800285d8  mov     r8, rdi
0x1800285db  mov     [rsp+78h+var_50], rcx
0x1800285e0  mov     rdx, rsi
0x1800285e3  mov     rcx, [rsp+78h+pcbPublicKeyBlob]
0x1800285eb  mov     [rsp+78h+var_58], rcx
0x1800285f0  mov     rcx, rbp
0x1800285f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800285f8  jmp     short loc_180028655
0x1800285fa  mov     rax, cs:?g_pfStrongNameTokenFromAssemblyEx@@3R6AKPEBGPEAPEAEPEAK12@ZEA; ulong (*g_pfStrongNameTokenFromAssemblyEx)(ushort const *,uchar * *,ulong *,uchar * *,ulong *)
0x180028601  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180028605  jnz     short loc_180028620
0x180028607  mov     rcx, [rsp+78h+hModule]; hModule
0x18002860c  lea     rdx, aStrongnametoke_4; "StrongNameTokenFromAssemblyEx"
0x180028613  call    cs:__imp_GetProcAddress
0x180028619  mov     cs:?g_pfStrongNameTokenFromAssemblyEx@@3R6AKPEBGPEAPEAEPEAK12@ZEA, rax; ulong (*g_pfStrongNameTokenFromAssemblyEx)(ushort const *,uchar * *,ulong *,uchar * *,ulong *)
0x180028620  mov     rax, cs:?g_pfStrongNameTokenFromAssemblyEx@@3R6AKPEBGPEAPEAEPEAK12@ZEA; ulong (*g_pfStrongNameTokenFromAssemblyEx)(ushort const *,uchar * *,ulong *,uchar * *,ulong *)
0x180028627  test    rax, rax
0x18002862a  jz      short loc_180028653
0x18002862c  mov     rcx, [rsp+78h+pcbPublicKeyBlob]
0x180028634  mov     r9, rbx
0x180028637  mov     rax, cs:?g_pfStrongNameTokenFromAssemblyEx@@3R6AKPEBGPEAPEAEPEAK12@ZEA; ulong (*g_pfStrongNameTokenFromAssemblyEx)(ushort const *,uchar * *,ulong *,uchar * *,ulong *)
0x18002863e  mov     r8, rdi
0x180028641  mov     [rsp+78h+var_58], rcx
0x180028646  mov     rdx, rsi
0x180028649  mov     rcx, rbp
0x18002864c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028651  jmp     short loc_180028655
0x180028653  xor     eax, eax
0x180028655  add     rsp, 58h
0x180028659  pop     rdi
0x18002865a  pop     rsi
0x18002865b  pop     rbp
0x18002865c  pop     rbx
0x18002865d  retn
```
