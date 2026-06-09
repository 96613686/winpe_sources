# FID_QueryAndCreateType1(ushort const *,ushort const *,FID_FILEINFO &,_ITEMIDLIST * *)

- ea: `0x180022e1c`
- end: `0x180022f18`
- name: `?FID_QueryAndCreateType1@@YAJPEBG0AEAUFID_FILEINFO@@PEAPEFAU_ITEMIDLIST@@@Z`
- size: `252`
- prototype: `__int64 __fastcall(LPCWSTR pszDir, LPCWSTR pszFile, const FILETIME *, struct _ITEMIDLIST **)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180022350`

## callees

- `0x1800220b4`
- `0x180022e1c`
- `0x180029440`
- `0x180031070`

## import_xrefs

- `SHLWAPI!PathCombineW` at `0x180022e67`
- `SHLWAPI!PathCombineW` at `0x180022e67`

## pseudocode

```c
__int64 __fastcall FID_QueryAndCreateType1(
        LPCWSTR pszDir,
        LPCWSTR pszFile,
        const FILETIME *a3,
        struct _ITEMIDLIST **a4)
{
  unsigned int v5; // ebx
  __int64 v6; // r8
  __int64 v7; // rdx
  unsigned int v9; // [rsp+20h] [rbp-E0h]
  unsigned int v10; // [rsp+30h] [rbp-D0h]
  unsigned int v11; // [rsp+50h] [rbp-B0h] BYREF
  int v12; // [rsp+54h] [rbp-ACh] BYREF
  unsigned __int16 *v13[3]; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR pszDest[264]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v15[264]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR v16[264]; // [rsp+490h] [rbp+390h] BYREF
  WCHAR v17[384]; // [rsp+6A0h] [rbp+5A0h] BYREF

  v12 = 0;
  v11 = 0;
  v5 = -2147023266;
  PathCombineW(pszDest, pszDir, pszFile);
  if ( (unsigned int)Type1::IsType1FontFile(pszDest, v17, v6, v15, v9, v16, v10, &v12, &v11) )
  {
    v13[0] = v15;
    v13[1] = v16;
    return (unsigned int)FID_Create(2u, v7, v17, 0, (unsigned __int16 *)&psz, a3, 2u, (const unsigned __int16 **)v13);
  }
  return v5;
}

```

## disassembly

```asm
0x180022e1c  push    rbp
0x180022e1e  push    rbx
0x180022e1f  push    rsi
0x180022e20  push    rdi
0x180022e21  lea     rbp, [rsp-8B8h]
0x180022e29  sub     rsp, 9B8h
0x180022e30  mov     rax, cs:__security_cookie
0x180022e37  xor     rax, rsp
0x180022e3a  mov     [rbp+8D0h+var_30], rax
0x180022e41  mov     rdi, r8
0x180022e44  mov     [rsp+9D0h+var_97C], 0
0x180022e4c  mov     r8, rdx; pszFile
0x180022e4f  mov     [rsp+9D0h+var_980], 0
0x180022e57  mov     rdx, rcx; pszDir
0x180022e5a  mov     rsi, r9
0x180022e5d  lea     rcx, [rsp+9D0h+pszDest]; pszDest
0x180022e62  mov     ebx, 8007065Eh
0x180022e67  call    cs:__imp_PathCombineW
0x180022e6d  lea     rax, [rsp+9D0h+var_980]
0x180022e72  mov     [rsp+9D0h+var_990], rax; unsigned int *
0x180022e77  lea     r9, [rbp+8D0h+var_750]; unsigned __int16 *
0x180022e7e  lea     rax, [rsp+9D0h+var_97C]
0x180022e83  mov     [rsp+9D0h+var_998], rax; int *
0x180022e88  lea     rdx, [rbp+8D0h+var_330]; LPWSTR
0x180022e8f  lea     rax, [rbp+8D0h+var_540]
0x180022e96  lea     rcx, [rsp+9D0h+pszDest]; lpWideCharStr
0x180022e9b  mov     [rsp+9D0h+var_9A8], rax; LPWSTR
0x180022ea0  call    ?IsType1FontFile@Type1@@SAHPEBGPEAGI1I1IPEAHPEAK@Z; Type1::IsType1FontFile(ushort const *,ushort *,uint,ushort *,uint,ushort *,uint,int *,ulong *)
0x180022ea5  test    eax, eax
0x180022ea7  jz      short loc_180022EFB
0x180022ea9  mov     [rsp+9D0h+var_990], rsi; struct _ITEMIDLIST **
0x180022eae  lea     rax, [rbp+8D0h+var_750]
0x180022eb5  mov     [rsp+9D0h+var_978], rax
0x180022eba  lea     r8, [rbp+8D0h+var_330]; unsigned __int16 *
0x180022ec1  lea     rax, [rbp+8D0h+var_540]
0x180022ec8  mov     ecx, 2; unsigned int
0x180022ecd  mov     [rsp+9D0h+var_970], rax
0x180022ed2  xor     r9d, r9d; unsigned __int16 *
0x180022ed5  lea     rax, [rsp+9D0h+var_978]
0x180022eda  mov     [rsp+9D0h+var_998], rax; unsigned __int16 **
0x180022edf  lea     rax, psz
0x180022ee6  mov     [rsp+9D0h+var_9A0], ecx; unsigned int
0x180022eea  mov     [rsp+9D0h+var_9A8], rdi; struct FID_FILEINFO *
0x180022eef  mov     [rsp+9D0h+var_9B0], rax; unsigned __int16 *
0x180022ef4  call    ?FID_Create@@YAJKKPEBG00AEAUFID_FILEINFO@@IPEAPEBGPEAPEFAU_ITEMIDLIST@@@Z; FID_Create(ulong,ulong,ushort const *,ushort const *,ushort const *,FID_FILEINFO &,uint,ushort const * *,_ITEMIDLIST * *)
0x180022ef9  mov     ebx, eax
0x180022efb  mov     eax, ebx
0x180022efd  mov     rcx, [rbp+8D0h+var_30]
0x180022f04  xor     rcx, rsp; StackCookie
0x180022f07  call    __security_check_cookie
0x180022f0c  add     rsp, 9B8h
0x180022f13  pop     rdi
0x180022f14  pop     rsi
0x180022f15  pop     rbx
0x180022f16  pop     rbp
0x180022f17  retn
```
