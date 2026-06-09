# ShellShim_ND_CopyObjDst

- ea: `0x1800262e0`
- end: `0x1800263e1`
- name: `ShellShim_ND_CopyObjDst`
- size: `257`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180001c10`
- `0x1800262e0`
- `0x180041ec0`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180026351`
- `KERNEL32!GetProcAddress` at `0x1800263a7`
- `KERNEL32!GetProcAddress` at `0x180026351`
- `KERNEL32!GetProcAddress` at `0x1800263a7`

## string_xrefs

- `0x18002634a`: `ND_CopyObjDst_RetAddr`
- `0x1800263a0`: `ND_CopyObjDst`

## pseudocode

```c
__int64 __fastcall ShellShim_ND_CopyObjDst(void *Src, __int64 a2, int a3, int a4)
{
  size_t v5; // rbx
  __int64 v6; // rdi
  __int64 result; // rax
  HMODULE hModule[7]; // [rsp+30h] [rbp-38h] BYREF
  void *retaddr; // [rsp+68h] [rbp+0h]

  v5 = a4;
  v6 = a3;
  hModule[0] = 0;
  result = GetShimImpl(hModule);
  if ( (_DWORD)result == 3 )
    return (__int64)memmove((void *)(a2 + v6), Src, v5);
  if ( (_DWORD)result == 2 )
  {
    result = (unsigned int)g_bShimImplDllUninitialized;
    if ( !g_bShimImplDllUninitialized )
    {
      if ( g_pfND_CopyObjDst_RetAddr == (void (*)(unsigned __int8 *, unsigned __int8 *, int, int, void *))-1LL )
        g_pfND_CopyObjDst_RetAddr = (void (*)(unsigned __int8 *, unsigned __int8 *, int, int, void *))GetProcAddress(hModule[0], "ND_CopyObjDst_RetAddr");
      if ( g_pfND_CopyObjDst_RetAddr )
      {
        return ((__int64 (__fastcall *)(void *, __int64, _QWORD, _QWORD, void *))g_pfND_CopyObjDst_RetAddr)(
                 Src,
                 a2,
                 (unsigned int)v6,
                 (unsigned int)v5,
                 retaddr);
      }
      else
      {
        if ( g_pfND_CopyObjDst == (void (*)(unsigned __int8 *, unsigned __int8 *, int, int))-1LL )
          g_pfND_CopyObjDst = (void (*)(unsigned __int8 *, unsigned __int8 *, int, int))GetProcAddress(
                                                                                          hModule[0],
                                                                                          "ND_CopyObjDst");
        result = (__int64)g_pfND_CopyObjDst;
        if ( g_pfND_CopyObjDst )
          return ((__int64 (__fastcall *)(void *, __int64, _QWORD, _QWORD))g_pfND_CopyObjDst)(
                   Src,
                   a2,
                   (unsigned int)v6,
                   (unsigned int)v5);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800262e0  push    rbx
0x1800262e2  push    rbp
0x1800262e3  push    rsi
0x1800262e4  push    rdi
0x1800262e5  sub     rsp, 48h
0x1800262e9  mov     rbp, rcx
0x1800262ec  movsxd  rbx, r9d
0x1800262ef  lea     rcx, [rsp+68h+hModule]
0x1800262f4  movsxd  rdi, r8d
0x1800262f7  mov     rsi, rdx
0x1800262fa  mov     [rsp+68h+hModule], 0
0x180026303  call    ?GetShimImpl@@YA?AW4ShimImplStatus@@PEAPEAUHINSTANCE__@@@Z; GetShimImpl(HINSTANCE__ * *)
0x180026308  cmp     eax, 3
0x18002630b  jnz     short loc_180026321
0x18002630d  mov     r8, rbx; Size
0x180026310  lea     rcx, [rsi+rdi]; void *
0x180026314  mov     rdx, rbp; Src
0x180026317  call    memmove
0x18002631c  jmp     loc_1800263D8
0x180026321  cmp     eax, 2
0x180026324  jnz     loc_1800263D8
0x18002632a  mov     eax, cs:?g_bShimImplDllUninitialized@@3HC; int volatile g_bShimImplDllUninitialized
0x180026330  test    eax, eax
0x180026332  jnz     loc_1800263D8
0x180026338  mov     rax, cs:?g_pfND_CopyObjDst_RetAddr@@3R6AXPEAE0HHPEAX@ZEA; void (*g_pfND_CopyObjDst_RetAddr)(uchar *,uchar *,int,int,void *)
0x18002633f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180026343  jnz     short loc_18002635E
0x180026345  mov     rcx, [rsp+68h+hModule]; hModule
0x18002634a  lea     rdx, aNdCopyobjdstRe; "ND_CopyObjDst_RetAddr"
0x180026351  call    cs:__imp_GetProcAddress
0x180026357  mov     cs:?g_pfND_CopyObjDst_RetAddr@@3R6AXPEAE0HHPEAX@ZEA, rax; void (*g_pfND_CopyObjDst_RetAddr)(uchar *,uchar *,int,int,void *)
0x18002635e  mov     rax, cs:?g_pfND_CopyObjDst_RetAddr@@3R6AXPEAE0HHPEAX@ZEA; void (*g_pfND_CopyObjDst_RetAddr)(uchar *,uchar *,int,int,void *)
0x180026365  test    rax, rax
0x180026368  jz      short loc_18002638E
0x18002636a  mov     rax, cs:?g_pfND_CopyObjDst_RetAddr@@3R6AXPEAE0HHPEAX@ZEA; void (*g_pfND_CopyObjDst_RetAddr)(uchar *,uchar *,int,int,void *)
0x180026371  mov     r9d, ebx
0x180026374  mov     rcx, [rsp+68h]
0x180026379  mov     r8d, edi
0x18002637c  mov     [rsp+68h+var_48], rcx
0x180026381  mov     rdx, rsi
0x180026384  mov     rcx, rbp
0x180026387  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002638c  jmp     short loc_1800263D8
0x18002638e  mov     rax, cs:?g_pfND_CopyObjDst@@3R6AXPEAE0HH@ZEA; void (*g_pfND_CopyObjDst)(uchar *,uchar *,int,int)
0x180026395  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180026399  jnz     short loc_1800263B4
0x18002639b  mov     rcx, [rsp+68h+hModule]; hModule
0x1800263a0  lea     rdx, aNdCopyobjdst_0; "ND_CopyObjDst"
0x1800263a7  call    cs:__imp_GetProcAddress
0x1800263ad  mov     cs:?g_pfND_CopyObjDst@@3R6AXPEAE0HH@ZEA, rax; void (*g_pfND_CopyObjDst)(uchar *,uchar *,int,int)
0x1800263b4  mov     rax, cs:?g_pfND_CopyObjDst@@3R6AXPEAE0HH@ZEA; void (*g_pfND_CopyObjDst)(uchar *,uchar *,int,int)
0x1800263bb  test    rax, rax
0x1800263be  jz      short loc_1800263D8
0x1800263c0  mov     rax, cs:?g_pfND_CopyObjDst@@3R6AXPEAE0HH@ZEA; void (*g_pfND_CopyObjDst)(uchar *,uchar *,int,int)
0x1800263c7  mov     r9d, ebx
0x1800263ca  mov     r8d, edi
0x1800263cd  mov     rdx, rsi
0x1800263d0  mov     rcx, rbp
0x1800263d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800263d8  add     rsp, 48h
0x1800263dc  pop     rdi
0x1800263dd  pop     rsi
0x1800263de  pop     rbp
0x1800263df  pop     rbx
0x1800263e0  retn
```
