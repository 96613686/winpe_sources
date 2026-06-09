# FID_QueryAndCreateTrueType(ushort const *,ushort const *,FID_FILEINFO &,_ITEMIDLIST * *)

- ea: `0x180022d00`
- end: `0x180022e15`
- name: `?FID_QueryAndCreateTrueType@@YAJPEBG0AEAUFID_FILEINFO@@PEAPEFAU_ITEMIDLIST@@@Z`
- size: `277`
- prototype: `__int64 __fastcall(LPCWSTR pszDir, LPCWSTR pszFile, const FILETIME *, struct _ITEMIDLIST **)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180022350`

## callees

- `0x1800220b4`
- `0x180022d00`
- `0x180028b24`
- `0x18003104a`
- `0x180031070`

## import_xrefs

- `SHLWAPI!PathCombineW` at `0x180022d5f`
- `SHLWAPI!PathCombineW` at `0x180022d5f`

## pseudocode

```c
__int64 __fastcall FID_QueryAndCreateTrueType(
        LPCWSTR pszDir,
        LPCWSTR pszFile,
        const FILETIME *a3,
        struct _ITEMIDLIST **a4)
{
  unsigned int v7; // esi
  unsigned int v8; // r9d
  __int64 v9; // rdx
  unsigned int v10; // ecx
  unsigned __int16 *v12; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v13; // [rsp+58h] [rbp-A8h] BYREF
  int v14; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR pszDest[260]; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned __int16 v16[384]; // [rsp+26Ch] [rbp+16Ch] BYREF
  unsigned __int16 v17[58]; // [rsp+56Ch] [rbp+46Ch] BYREF

  LODWORD(v12) = 0;
  v7 = -2147023266;
  memset_0(&v14, 0, 0x580u);
  PathCombineW(pszDest, pszDir, pszFile);
  v13 = 16;
  v14 = 3;
  if ( (unsigned int)TrueType::IsTrueTypeFontFile((struct FONTDESCINFO *)&v14, &v13, (unsigned int *)&v12, v8) )
  {
    if ( (v13 & 0x20) != 0 )
    {
      v10 = 5;
    }
    else if ( (v13 & 0x40) != 0 )
    {
      v10 = 4;
    }
    else
    {
      v10 = 5;
      if ( (v13 & 0x10) == 0 )
        v10 = 3;
    }
    v12 = pszDest;
    return (unsigned int)FID_Create(v10, v9, v16, 0, v17, a3, 1u, (const unsigned __int16 **)&v12);
  }
  return v7;
}

```

## disassembly

```asm
0x180022d00  push    rbp
0x180022d02  push    rbx
0x180022d03  push    rsi
0x180022d04  push    rdi
0x180022d05  push    r14
0x180022d07  push    r15
0x180022d09  lea     rbp, [rsp-4F8h]
0x180022d11  sub     rsp, 5F8h
0x180022d18  mov     rax, cs:__security_cookie
0x180022d1f  xor     rax, rsp
0x180022d22  mov     [rbp+520h+var_40], rax
0x180022d29  mov     r14, r8
0x180022d2c  mov     dword ptr [rsp+620h+var_5D0], 0
0x180022d34  mov     rdi, rdx
0x180022d37  mov     rbx, rcx
0x180022d3a  xor     edx, edx; Val
0x180022d3c  lea     rcx, [rsp+620h+var_5C0]; void *
0x180022d41  mov     r8d, 580h; Size
0x180022d47  mov     r15, r9
0x180022d4a  mov     esi, 8007065Eh
0x180022d4f  call    memset_0
0x180022d54  mov     r8, rdi; pszFile
0x180022d57  lea     rcx, [rsp+620h+pszDest]; pszDest
0x180022d5c  mov     rdx, rbx; pszDir
0x180022d5f  call    cs:__imp_PathCombineW
0x180022d65  mov     ebx, 3
0x180022d6a  mov     [rsp+620h+var_5C8], 10h
0x180022d72  lea     r8, [rsp+620h+var_5D0]; unsigned int *
0x180022d77  mov     [rsp+620h+var_5C0], ebx
0x180022d7b  lea     rdx, [rsp+620h+var_5C8]; unsigned int *
0x180022d80  lea     rcx, [rsp+620h+var_5C0]; struct FONTDESCINFO *
0x180022d85  call    ?IsTrueTypeFontFile@TrueType@@SAHPEAUFONTDESCINFO@@PEAK1@Z; TrueType::IsTrueTypeFontFile(FONTDESCINFO *,ulong *,ulong *)
0x180022d8a  test    eax, eax
0x180022d8c  jz      short loc_180022DF4
0x180022d8e  mov     eax, [rsp+620h+var_5C8]
0x180022d92  test    al, 20h
0x180022d94  jz      short loc_180022D9B
0x180022d96  lea     ecx, [rbx+2]
0x180022d99  jmp     short loc_180022DB1
0x180022d9b  test    al, 40h
0x180022d9d  jz      short loc_180022DA6
0x180022d9f  mov     ecx, 4
0x180022da4  jmp     short loc_180022DB1
0x180022da6  mov     ecx, 5
0x180022dab  test    al, 10h
0x180022dad  jnz     short loc_180022DB1
0x180022daf  mov     ecx, ebx; unsigned int
0x180022db1  mov     [rsp+620h+var_5E0], r15; struct _ITEMIDLIST **
0x180022db6  lea     rax, [rsp+620h+pszDest]
0x180022dbb  mov     [rsp+620h+var_5D0], rax
0x180022dc0  lea     r8, [rbp+520h+var_3B4]; unsigned __int16 *
0x180022dc7  lea     rax, [rsp+620h+var_5D0]
0x180022dcc  xor     r9d, r9d; unsigned __int16 *
0x180022dcf  mov     [rsp+620h+var_5E8], rax; unsigned __int16 **
0x180022dd4  lea     rax, [rbp+520h+var_B4]
0x180022ddb  mov     [rsp+620h+var_5F0], 1; unsigned int
0x180022de3  mov     [rsp+620h+var_5F8], r14; struct FID_FILEINFO *
0x180022de8  mov     [rsp+620h+var_600], rax; unsigned __int16 *
0x180022ded  call    ?FID_Create@@YAJKKPEBG00AEAUFID_FILEINFO@@IPEAPEBGPEAPEFAU_ITEMIDLIST@@@Z; FID_Create(ulong,ulong,ushort const *,ushort const *,ushort const *,FID_FILEINFO &,uint,ushort const * *,_ITEMIDLIST * *)
0x180022df2  mov     esi, eax
0x180022df4  mov     eax, esi
0x180022df6  mov     rcx, [rbp+520h+var_40]
0x180022dfd  xor     rcx, rsp; StackCookie
0x180022e00  call    __security_check_cookie
0x180022e05  add     rsp, 5F8h
0x180022e0c  pop     r15
0x180022e0e  pop     r14
0x180022e10  pop     rdi
0x180022e11  pop     rsi
0x180022e12  pop     rbx
0x180022e13  pop     rbp
0x180022e14  retn
```
