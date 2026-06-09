# FID_QueryAndCreateUnknown(ushort const *,ushort const *,FID_FILEINFO &,_ITEMIDLIST * *)

- ea: `0x180022f20`
- end: `0x1800230f3`
- name: `?FID_QueryAndCreateUnknown@@YAJPEBG0AEAUFID_FILEINFO@@PEAPEFAU_ITEMIDLIST@@@Z`
- size: `467`
- prototype: `__int64 __fastcall(LPCWSTR pszDir, LPCWSTR pszFile, const FILETIME *, struct _ITEMIDLIST **)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180022350`

## callees

- `0x180006668`
- `0x1800220b4`
- `0x180022f20`
- `0x18003104a`
- `0x180031070`

## import_xrefs

- `SHLWAPI!PathCombineW` at `0x180022f5b`
- `SHLWAPI!PathCombineW` at `0x180022f5b`
- `GDI32!AddFontResourceExW` at `0x180022f6d`
- `GDI32!AddFontResourceExW` at `0x180022f6d`
- `GDI32!GetFontResourceInfoW` at `0x180022fa0`
- `GDI32!GetFontResourceInfoW` at `0x180022fe1`
- `GDI32!GetFontResourceInfoW` at `0x180022fa0`
- `GDI32!GetFontResourceInfoW` at `0x180022fe1`
- `GDI32!RemoveFontResourceExW` at `0x1800230d0`
- `GDI32!RemoveFontResourceExW` at `0x1800230d0`

## pseudocode

```c
__int64 __fastcall FID_QueryAndCreateUnknown(
        LPCWSTR pszDir,
        LPCWSTR pszFile,
        const FILETIME *a3,
        struct _ITEMIDLIST **a4)
{
  unsigned int v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // rdx
  unsigned int v8; // eax
  int v10; // [rsp+50h] [rbp-B0h] BYREF
  int v11; // [rsp+54h] [rbp-ACh] BYREF
  unsigned __int16 *v12; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR pszDest[264]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v14[384]; // [rsp+270h] [rbp+170h] BYREF
  unsigned __int16 v15[384]; // [rsp+570h] [rbp+470h] BYREF

  v5 = -2147023266;
  PathCombineW(pszDest, pszDir, pszFile);
  if ( AddFontResourceExW(pszDest, 0x10u, 0) )
  {
    v10 = 4;
    v11 = 0;
    if ( (unsigned int)GetFontResourceInfoW(pszDest, &v10, &v11, 3) )
    {
      memset_0(v14, 0, sizeof(v14));
      v10 = 768;
      if ( (unsigned int)GetFontResourceInfoW(pszDest, &v10, v14, 1) )
      {
        if ( v11 )
        {
          memset_0(v15, 0, sizeof(v15));
          StringCchPrintfW(v15, 0x180u, L"%s (%s)", v14, L"TrueType");
          v12 = pszDest;
          v8 = FID_Create(3u, v7, v15, 0, (unsigned __int16 *)&psz, a3, 1u, (const unsigned __int16 **)&v12);
        }
        else
        {
          v12 = pszDest;
          v8 = FID_Create(1u, v6, v14, &psz, 0, a3, 1u, (const unsigned __int16 **)&v12);
        }
        v5 = v8;
      }
    }
    RemoveFontResourceExW(pszDest, 0x10u, 0);
  }
  return v5;
}

```

## disassembly

```asm
0x180022f20  push    rbp
0x180022f22  push    rbx
0x180022f23  push    rsi
0x180022f24  push    rdi
0x180022f25  lea     rbp, [rsp-788h]
0x180022f2d  sub     rsp, 888h
0x180022f34  mov     rax, cs:__security_cookie
0x180022f3b  xor     rax, rsp
0x180022f3e  mov     [rbp+7A0h+var_30], rax
0x180022f45  mov     rdi, r8
0x180022f48  mov     rsi, r9
0x180022f4b  mov     r8, rdx; pszFile
0x180022f4e  mov     ebx, 8007065Eh
0x180022f53  mov     rdx, rcx; pszDir
0x180022f56  lea     rcx, [rsp+8A0h+pszDest]; pszDest
0x180022f5b  call    cs:__imp_PathCombineW
0x180022f61  xor     r8d, r8d; res
0x180022f64  lea     rcx, [rsp+8A0h+pszDest]; name
0x180022f69  lea     edx, [r8+10h]; fl
0x180022f6d  call    cs:__imp_AddFontResourceExW
0x180022f73  test    eax, eax
0x180022f75  jz      loc_1800230D6
0x180022f7b  mov     r9d, 3
0x180022f81  mov     [rsp+8A0h+var_850], 4
0x180022f89  lea     r8, [rsp+8A0h+var_84C]
0x180022f8e  mov     [rsp+8A0h+var_84C], 0
0x180022f96  lea     rdx, [rsp+8A0h+var_850]
0x180022f9b  lea     rcx, [rsp+8A0h+pszDest]
0x180022fa0  call    cs:__imp_GetFontResourceInfoW
0x180022fa6  test    eax, eax
0x180022fa8  jz      loc_1800230C4
0x180022fae  xor     edx, edx; Val
0x180022fb0  lea     rcx, [rbp+7A0h+var_630]; void *
0x180022fb7  mov     r8d, 300h; Size
0x180022fbd  call    memset_0
0x180022fc2  mov     r9d, 1
0x180022fc8  mov     [rsp+8A0h+var_850], 300h
0x180022fd0  lea     r8, [rbp+7A0h+var_630]
0x180022fd7  lea     rdx, [rsp+8A0h+var_850]
0x180022fdc  lea     rcx, [rsp+8A0h+pszDest]
0x180022fe1  call    cs:__imp_GetFontResourceInfoW
0x180022fe7  test    eax, eax
0x180022fe9  jz      loc_1800230C4
0x180022fef  cmp     [rsp+8A0h+var_84C], 0
0x180022ff4  jz      loc_18002307B
0x180022ffa  xor     edx, edx; Val
0x180022ffc  lea     rcx, [rbp+7A0h+var_330]; void *
0x180023003  mov     r8d, 300h; Size
0x180023009  call    memset_0
0x18002300e  lea     rax, c_szTrueType; "TrueType"
0x180023015  mov     edx, 180h; unsigned __int64
0x18002301a  lea     r9, [rbp+7A0h+var_630]
0x180023021  mov     [rsp+8A0h+var_880], rax
0x180023026  lea     r8, c_szDescFormat; "%s (%s)"
0x18002302d  lea     rcx, [rbp+7A0h+var_330]; unsigned __int16 *
0x180023034  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180023039  mov     [rsp+8A0h+var_860], rsi
0x18002303e  lea     rax, [rsp+8A0h+pszDest]
0x180023043  lea     r9, psz
0x18002304a  mov     [rsp+8A0h+var_848], rax
0x18002304f  lea     rax, [rsp+8A0h+var_848]
0x180023054  mov     [rsp+8A0h+var_868], rax
0x180023059  lea     r8, [rbp+7A0h+var_330]
0x180023060  mov     [rsp+8A0h+var_870], 1
0x180023068  mov     [rsp+8A0h+var_878], rdi
0x18002306d  mov     [rsp+8A0h+var_880], r9
0x180023072  xor     r9d, r9d
0x180023075  lea     ecx, [r9+3]
0x180023079  jmp     short loc_1800230BD
0x18002307b  mov     [rsp+8A0h+var_860], rsi; struct _ITEMIDLIST **
0x180023080  lea     rax, [rsp+8A0h+pszDest]
0x180023085  mov     [rsp+8A0h+var_848], rax
0x18002308a  lea     r9, psz; unsigned __int16 *
0x180023091  lea     rax, [rsp+8A0h+var_848]
0x180023096  mov     ecx, 1; unsigned int
0x18002309b  mov     [rsp+8A0h+var_868], rax; unsigned __int16 **
0x1800230a0  lea     r8, [rbp+7A0h+var_630]; unsigned __int16 *
0x1800230a7  mov     [rsp+8A0h+var_870], 1; unsigned int
0x1800230af  mov     [rsp+8A0h+var_878], rdi; struct FID_FILEINFO *
0x1800230b4  mov     [rsp+8A0h+var_880], 0; unsigned __int16 *
0x1800230bd  call    ?FID_Create@@YAJKKPEBG00AEAUFID_FILEINFO@@IPEAPEBGPEAPEFAU_ITEMIDLIST@@@Z; FID_Create(ulong,ulong,ushort const *,ushort const *,ushort const *,FID_FILEINFO &,uint,ushort const * *,_ITEMIDLIST * *)
0x1800230c2  mov     ebx, eax
0x1800230c4  xor     r8d, r8d; pdv
0x1800230c7  lea     rcx, [rsp+8A0h+pszDest]; name
0x1800230cc  lea     edx, [r8+10h]; fl
0x1800230d0  call    cs:__imp_RemoveFontResourceExW
0x1800230d6  mov     eax, ebx
0x1800230d8  mov     rcx, [rbp+7A0h+var_30]
0x1800230df  xor     rcx, rsp; StackCookie
0x1800230e2  call    __security_check_cookie
0x1800230e7  add     rsp, 888h
0x1800230ee  pop     rdi
0x1800230ef  pop     rsi
0x1800230f0  pop     rbx
0x1800230f1  pop     rbp
0x1800230f2  retn
```
