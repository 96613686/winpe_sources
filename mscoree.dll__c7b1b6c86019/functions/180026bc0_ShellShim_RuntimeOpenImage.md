# ShellShim_RuntimeOpenImage

- ea: `0x180026bc0`
- end: `0x180026ce8`
- name: `ShellShim_RuntimeOpenImage`
- size: `296`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180001c10`
- `0x180026bc0`
- `0x18002a230`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180026c20`
- `KERNEL32!GetProcAddress` at `0x180026c69`
- `KERNEL32!GetProcAddress` at `0x180026cb4`
- `KERNEL32!GetProcAddress` at `0x180026c20`
- `KERNEL32!GetProcAddress` at `0x180026c69`
- `KERNEL32!GetProcAddress` at `0x180026cb4`

## string_xrefs

- `0x180026c62`: `RuntimeOpenImage_RetAddr`
- `0x180026c19`: `RuntimeOpenImage`
- `0x180026cad`: `RuntimeOpenImage`

## pseudocode

```c
__int64 __fastcall ShellShim_RuntimeOpenImage(__int64 a1, __int64 a2)
{
  int ShimImpl; // eax
  FARPROC ProcAddress; // rax
  __int64 result; // rax
  void *retaddr; // [rsp+28h] [rbp+0h]
  HMODULE hModule; // [rsp+40h] [rbp+18h] BYREF

  hModule = 0;
  ShimImpl = GetShimImpl(&hModule);
  if ( ShimImpl == 1 )
    return 2148734721LL;
  if ( ShimImpl != 3 )
  {
    if ( g_bShimImplDllUninitialized )
      return 2148734721LL;
    if ( g_pfRuntimeOpenImage_RetAddr == (int (*)(const unsigned __int16 *, struct _dummyCOR **, void *))-1LL )
      g_pfRuntimeOpenImage_RetAddr = (int (*)(const unsigned __int16 *, struct _dummyCOR **, void *))GetProcAddress(hModule, "RuntimeOpenImage_RetAddr");
    if ( g_pfRuntimeOpenImage_RetAddr )
      return ((__int64 (__fastcall *)(__int64, __int64, void *))g_pfRuntimeOpenImage_RetAddr)(a1, a2, retaddr);
    if ( g_pfRuntimeOpenImage == (int (*)(const unsigned __int16 *, struct _dummyCOR **))-1LL )
      g_pfRuntimeOpenImage = (int (*)(const unsigned __int16 *, struct _dummyCOR **))GetProcAddress(
                                                                                       hModule,
                                                                                       "RuntimeOpenImage");
    if ( !g_pfRuntimeOpenImage )
      return 2148734721LL;
    ProcAddress = (FARPROC)g_pfRuntimeOpenImage;
    return ((__int64 (__fastcall *)(__int64, __int64))ProcAddress)(a1, a2);
  }
  ProcAddress = (FARPROC)g_RuntimeOpenImage;
  if ( g_RuntimeOpenImage )
    return ((__int64 (__fastcall *)(__int64, __int64))ProcAddress)(a1, a2);
  hModule = 0;
  result = GetRealDll(&hModule, 1);
  if ( (int)result < 0 )
    return result;
  ProcAddress = GetProcAddress(hModule, "RuntimeOpenImage");
  g_RuntimeOpenImage = (int (*)(const unsigned __int16 *, struct _dummyCOR **))ProcAddress;
  if ( ProcAddress )
    return ((__int64 (__fastcall *)(_QWORD, _QWORD))ProcAddress)(a1, a2);
  return 2148734721LL;
}

```

## disassembly

```asm
0x180026bc0  mov     [rsp+arg_0], rbx
0x180026bc5  push    rdi
0x180026bc6  sub     rsp, 20h
0x180026bca  mov     rdi, rcx
0x180026bcd  mov     [rsp+28h+hModule], 0
0x180026bd6  lea     rcx, [rsp+28h+hModule]
0x180026bdb  mov     rbx, rdx
0x180026bde  call    ?GetShimImpl@@YA?AW4ShimImplStatus@@PEAPEAUHINSTANCE__@@@Z; GetShimImpl(HINSTANCE__ * *)
0x180026be3  mov     edx, 1; int
0x180026be8  cmp     eax, edx
0x180026bea  jz      short loc_180026C36
0x180026bec  cmp     eax, 3
0x180026bef  jnz     short loc_180026C46
0x180026bf1  mov     rax, cs:?g_RuntimeOpenImage@@3P6AJPEBGPEAPEAU_dummyCOR@@@ZEA; long (*g_RuntimeOpenImage)(ushort const *,_dummyCOR * *)
0x180026bf8  test    rax, rax
0x180026bfb  jnz     loc_180026CD8
0x180026c01  lea     rcx, [rsp+28h+hModule]; HINSTANCE *
0x180026c06  mov     [rsp+28h+hModule], rax
0x180026c0b  call    ?GetRealDll@@YAJPEAPEAUHINSTANCE__@@H@Z; GetRealDll(HINSTANCE__ * *,int)
0x180026c10  test    eax, eax
0x180026c12  js      short loc_180026C3B
0x180026c14  mov     rcx, [rsp+28h+hModule]; hModule
0x180026c19  lea     rdx, aRuntimeopenima_0; "RuntimeOpenImage"
0x180026c20  call    cs:__imp_GetProcAddress
0x180026c26  mov     cs:?g_RuntimeOpenImage@@3P6AJPEBGPEAPEAU_dummyCOR@@@ZEA, rax; long (*g_RuntimeOpenImage)(ushort const *,_dummyCOR * *)
0x180026c2d  test    rax, rax
0x180026c30  jnz     loc_180026CD8
0x180026c36  mov     eax, 80131701h
0x180026c3b  mov     rbx, [rsp+28h+arg_0]
0x180026c40  add     rsp, 20h
0x180026c44  pop     rdi
0x180026c45  retn
0x180026c46  mov     eax, cs:?g_bShimImplDllUninitialized@@3HC; int volatile g_bShimImplDllUninitialized
0x180026c4c  test    eax, eax
0x180026c4e  jnz     short loc_180026C36
0x180026c50  mov     rax, cs:?g_pfRuntimeOpenImage_RetAddr@@3R6AJPEBGPEAPEAU_dummyCOR@@PEAX@ZEA; long (*g_pfRuntimeOpenImage_RetAddr)(ushort const *,_dummyCOR * *,void *)
0x180026c57  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180026c5b  jnz     short loc_180026C76
0x180026c5d  mov     rcx, [rsp+28h+hModule]; hModule
0x180026c62  lea     rdx, aRuntimeopenima_1; "RuntimeOpenImage_RetAddr"
0x180026c69  call    cs:__imp_GetProcAddress
0x180026c6f  mov     cs:?g_pfRuntimeOpenImage_RetAddr@@3R6AJPEBGPEAPEAU_dummyCOR@@PEAX@ZEA, rax; long (*g_pfRuntimeOpenImage_RetAddr)(ushort const *,_dummyCOR * *,void *)
0x180026c76  mov     rax, cs:?g_pfRuntimeOpenImage_RetAddr@@3R6AJPEBGPEAPEAU_dummyCOR@@PEAX@ZEA; long (*g_pfRuntimeOpenImage_RetAddr)(ushort const *,_dummyCOR * *,void *)
0x180026c7d  test    rax, rax
0x180026c80  jz      short loc_180026C9B
0x180026c82  mov     rax, cs:?g_pfRuntimeOpenImage_RetAddr@@3R6AJPEBGPEAPEAU_dummyCOR@@PEAX@ZEA; long (*g_pfRuntimeOpenImage_RetAddr)(ushort const *,_dummyCOR * *,void *)
0x180026c89  mov     rdx, rbx
0x180026c8c  mov     r8, [rsp+28h]
0x180026c91  mov     rcx, rdi
0x180026c94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c99  jmp     short loc_180026C3B
0x180026c9b  mov     rax, cs:?g_pfRuntimeOpenImage@@3R6AJPEBGPEAPEAU_dummyCOR@@@ZEA; long (*g_pfRuntimeOpenImage)(ushort const *,_dummyCOR * *)
0x180026ca2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180026ca6  jnz     short loc_180026CC1
0x180026ca8  mov     rcx, [rsp+28h+hModule]; hModule
0x180026cad  lea     rdx, aRuntimeopenima_0; "RuntimeOpenImage"
0x180026cb4  call    cs:__imp_GetProcAddress
0x180026cba  mov     cs:?g_pfRuntimeOpenImage@@3R6AJPEBGPEAPEAU_dummyCOR@@@ZEA, rax; long (*g_pfRuntimeOpenImage)(ushort const *,_dummyCOR * *)
0x180026cc1  mov     rax, cs:?g_pfRuntimeOpenImage@@3R6AJPEBGPEAPEAU_dummyCOR@@@ZEA; long (*g_pfRuntimeOpenImage)(ushort const *,_dummyCOR * *)
0x180026cc8  test    rax, rax
0x180026ccb  jz      loc_180026C36
0x180026cd1  mov     rax, cs:?g_pfRuntimeOpenImage@@3R6AJPEBGPEAPEAU_dummyCOR@@@ZEA; long (*g_pfRuntimeOpenImage)(ushort const *,_dummyCOR * *)
0x180026cd8  mov     rdx, rbx
0x180026cdb  mov     rcx, rdi
0x180026cde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026ce3  jmp     loc_180026C3B
```
