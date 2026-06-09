# ShellShim_ND_CopyObjSrc

- ea: `0x1800263f0`
- end: `0x1800264ef`
- name: `ShellShim_ND_CopyObjSrc`
- size: `255`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180001c10`
- `0x1800263f0`
- `0x180041ec0`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180026461`
- `KERNEL32!GetProcAddress` at `0x1800264b6`
- `KERNEL32!GetProcAddress` at `0x180026461`
- `KERNEL32!GetProcAddress` at `0x1800264b6`

## string_xrefs

- `0x18002645a`: `ND_CopyObjSrc_RetAddr`
- `0x1800264af`: `ND_CopyObjSrc`

## pseudocode

```c
__int64 __fastcall ShellShim_ND_CopyObjSrc(__int64 a1, int a2, void *a3, int a4)
{
  size_t v5; // rbx
  __int64 v6; // rsi
  __int64 result; // rax
  HMODULE hModule[7]; // [rsp+30h] [rbp-38h] BYREF
  void *retaddr; // [rsp+68h] [rbp+0h]

  v5 = a4;
  v6 = a2;
  hModule[0] = 0;
  result = GetShimImpl(hModule);
  if ( (_DWORD)result == 3 )
    return (__int64)memmove(a3, (const void *)(v6 + a1), v5);
  if ( (_DWORD)result == 2 )
  {
    result = (unsigned int)g_bShimImplDllUninitialized;
    if ( !g_bShimImplDllUninitialized )
    {
      if ( g_pfND_CopyObjSrc_RetAddr == (void (*)(unsigned __int8 *, int, unsigned __int8 *, int, void *))-1LL )
        g_pfND_CopyObjSrc_RetAddr = (void (*)(unsigned __int8 *, int, unsigned __int8 *, int, void *))GetProcAddress(hModule[0], "ND_CopyObjSrc_RetAddr");
      if ( g_pfND_CopyObjSrc_RetAddr )
      {
        return ((__int64 (__fastcall *)(__int64, _QWORD, void *, _QWORD, void *))g_pfND_CopyObjSrc_RetAddr)(
                 a1,
                 (unsigned int)v6,
                 a3,
                 (unsigned int)v5,
                 retaddr);
      }
      else
      {
        if ( g_pfND_CopyObjSrc == (void (*)(unsigned __int8 *, int, unsigned __int8 *, int))-1LL )
          g_pfND_CopyObjSrc = (void (*)(unsigned __int8 *, int, unsigned __int8 *, int))GetProcAddress(
                                                                                          hModule[0],
                                                                                          "ND_CopyObjSrc");
        result = (__int64)g_pfND_CopyObjSrc;
        if ( g_pfND_CopyObjSrc )
          return ((__int64 (__fastcall *)(__int64, _QWORD, void *, _QWORD))g_pfND_CopyObjSrc)(
                   a1,
                   (unsigned int)v6,
                   a3,
                   (unsigned int)v5);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800263f0  push    rbx
0x1800263f2  push    rbp
0x1800263f3  push    rsi
0x1800263f4  push    rdi
0x1800263f5  sub     rsp, 48h
0x1800263f9  mov     rbp, rcx
0x1800263fc  movsxd  rbx, r9d
0x1800263ff  lea     rcx, [rsp+68h+hModule]
0x180026404  movsxd  rsi, edx
0x180026407  mov     rdi, r8
0x18002640a  mov     [rsp+68h+hModule], 0
0x180026413  call    ?GetShimImpl@@YA?AW4ShimImplStatus@@PEAPEAUHINSTANCE__@@@Z; GetShimImpl(HINSTANCE__ * *)
0x180026418  cmp     eax, 3
0x18002641b  jnz     short loc_180026431
0x18002641d  mov     r8, rbx; Size
0x180026420  lea     rdx, [rsi+rbp]; Src
0x180026424  mov     rcx, rdi; void *
0x180026427  call    memmove
0x18002642c  jmp     loc_1800264E6
0x180026431  cmp     eax, 2
0x180026434  jnz     loc_1800264E6
0x18002643a  mov     eax, cs:?g_bShimImplDllUninitialized@@3HC; int volatile g_bShimImplDllUninitialized
0x180026440  test    eax, eax
0x180026442  jnz     loc_1800264E6
0x180026448  mov     rax, cs:?g_pfND_CopyObjSrc_RetAddr@@3R6AXPEAEH0HPEAX@ZEA; void (*g_pfND_CopyObjSrc_RetAddr)(uchar *,int,uchar *,int,void *)
0x18002644f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180026453  jnz     short loc_18002646E
0x180026455  mov     rcx, [rsp+68h+hModule]; hModule
0x18002645a  lea     rdx, aNdCopyobjsrcRe; "ND_CopyObjSrc_RetAddr"
0x180026461  call    cs:__imp_GetProcAddress
0x180026467  mov     cs:?g_pfND_CopyObjSrc_RetAddr@@3R6AXPEAEH0HPEAX@ZEA, rax; void (*g_pfND_CopyObjSrc_RetAddr)(uchar *,int,uchar *,int,void *)
0x18002646e  mov     rax, cs:?g_pfND_CopyObjSrc_RetAddr@@3R6AXPEAEH0HPEAX@ZEA; void (*g_pfND_CopyObjSrc_RetAddr)(uchar *,int,uchar *,int,void *)
0x180026475  test    rax, rax
0x180026478  jz      short loc_18002649D
0x18002647a  mov     rax, cs:?g_pfND_CopyObjSrc_RetAddr@@3R6AXPEAEH0HPEAX@ZEA; void (*g_pfND_CopyObjSrc_RetAddr)(uchar *,int,uchar *,int,void *)
0x180026481  mov     r9d, ebx
0x180026484  mov     rcx, [rsp+68h]
0x180026489  mov     r8, rdi
0x18002648c  mov     [rsp+68h+var_48], rcx
0x180026491  mov     edx, esi
0x180026493  mov     rcx, rbp
0x180026496  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002649b  jmp     short loc_1800264E6
0x18002649d  mov     rax, cs:?g_pfND_CopyObjSrc@@3R6AXPEAEH0H@ZEA; void (*g_pfND_CopyObjSrc)(uchar *,int,uchar *,int)
0x1800264a4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800264a8  jnz     short loc_1800264C3
0x1800264aa  mov     rcx, [rsp+68h+hModule]; hModule
0x1800264af  lea     rdx, aNdCopyobjsrc_0; "ND_CopyObjSrc"
0x1800264b6  call    cs:__imp_GetProcAddress
0x1800264bc  mov     cs:?g_pfND_CopyObjSrc@@3R6AXPEAEH0H@ZEA, rax; void (*g_pfND_CopyObjSrc)(uchar *,int,uchar *,int)
0x1800264c3  mov     rax, cs:?g_pfND_CopyObjSrc@@3R6AXPEAEH0H@ZEA; void (*g_pfND_CopyObjSrc)(uchar *,int,uchar *,int)
0x1800264ca  test    rax, rax
0x1800264cd  jz      short loc_1800264E6
0x1800264cf  mov     rax, cs:?g_pfND_CopyObjSrc@@3R6AXPEAEH0H@ZEA; void (*g_pfND_CopyObjSrc)(uchar *,int,uchar *,int)
0x1800264d6  mov     r9d, ebx
0x1800264d9  mov     r8, rdi
0x1800264dc  mov     edx, esi
0x1800264de  mov     rcx, rbp
0x1800264e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800264e6  add     rsp, 48h
0x1800264ea  pop     rdi
0x1800264eb  pop     rsi
0x1800264ec  pop     rbp
0x1800264ed  pop     rbx
0x1800264ee  retn
```
