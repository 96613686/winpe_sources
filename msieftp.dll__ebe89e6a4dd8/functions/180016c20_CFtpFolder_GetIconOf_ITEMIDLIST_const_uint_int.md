# CFtpFolder::GetIconOf(_ITEMIDLIST const *,uint,int *)

- ea: `0x180016c20`
- end: `0x180016cce`
- name: `?GetIconOf@CFtpFolder@@UEAAJPEFBU_ITEMIDLIST@@IPEAH@Z`
- size: `174`
- prototype: `int(CFtpFolder *__hidden this, const struct _ITEMIDLIST *, unsigned int, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180016c20`
- `0x180018d28`
- `0x1800194e0`

## import_xrefs

- `SHELL32!Shell_GetCachedImageIndexW` at `0x180016ca6`
- `SHELL32!Shell_GetCachedImageIndexW` at `0x180016ca6`

## pseudocode

```c
__int64 __fastcall CFtpFolder::GetIconOf(CFtpFolder *this, const struct _ITEMIDLIST *a2, unsigned int a3, int *a4)
{
  __int64 v9; // rdx
  _WORD *v10; // rdx
  int v11; // ecx
  int IconOf; // ebx
  int CachedImageIndexW; // eax
  LPCWSTR pszIconPath; // [rsp+50h] [rbp+8h] BYREF

  if ( !CFtpFolder::_IsValidPidlParameter((CFtpFolder *)((char *)this - 80), a2) )
    return 2147942487LL;
  v9 = *((int *)this - 4);
  pszIconPath = 0;
  v10 = (_WORD *)(*((_QWORD *)this - 4) + v9);
  if ( !v10 || (v11 = 0, !*v10) )
    v11 = 1;
  IconOf = CFtpIcon::GetIconOf(v11, a2, a3, a4, &pszIconPath);
  if ( IconOf >= 0 && pszIconPath != (LPCWSTR)&CFtpIcon::c_szStar )
  {
    CachedImageIndexW = Shell_GetCachedImageIndexW(pszIconPath, *a4, 0);
    *a4 = CachedImageIndexW;
    if ( CachedImageIndexW == -1 )
      return (unsigned int)-2147467259;
  }
  return (unsigned int)IconOf;
}

```

## disassembly

```asm
0x180016c20  mov     [rsp+arg_8], rbx
0x180016c25  mov     [rsp+arg_10], rbp
0x180016c2a  push    rsi
0x180016c2b  push    rdi
0x180016c2c  push    r14
0x180016c2e  sub     rsp, 30h
0x180016c32  mov     rbx, rcx
0x180016c35  mov     rdi, r9
0x180016c38  add     rcx, 0FFFFFFFFFFFFFFB0h; this
0x180016c3c  mov     ebp, r8d
0x180016c3f  mov     rsi, rdx
0x180016c42  call    ?_IsValidPidlParameter@CFtpFolder@@QEAAHPEFBU_ITEMIDLIST@@@Z; CFtpFolder::_IsValidPidlParameter(_ITEMIDLIST const *)
0x180016c47  xor     r14d, r14d
0x180016c4a  test    eax, eax
0x180016c4c  jnz     short loc_180016C55
0x180016c4e  mov     eax, 80070057h
0x180016c53  jmp     short loc_180016CBB
0x180016c55  movsxd  rdx, dword ptr [rbx-10h]
0x180016c59  mov     [rsp+48h+pszIconPath], r14
0x180016c5e  add     rdx, [rbx-20h]
0x180016c62  jz      short loc_180016C6D
0x180016c64  mov     ecx, r14d
0x180016c67  cmp     [rdx], r14w
0x180016c6b  jnz     short loc_180016C72
0x180016c6d  mov     ecx, 1; int
0x180016c72  lea     rax, [rsp+48h+pszIconPath]
0x180016c77  mov     r9, rdi; int *
0x180016c7a  mov     r8d, ebp; unsigned int
0x180016c7d  mov     [rsp+48h+var_28], rax; unsigned __int16 **
0x180016c82  mov     rdx, rsi; struct _ITEMIDLIST *
0x180016c85  call    ?GetIconOf@CFtpIcon@@SAJHPEFBU_ITEMIDLIST@@IPEAHPEAPEBG@Z; CFtpIcon::GetIconOf(int,_ITEMIDLIST const *,uint,int *,ushort const * *)
0x180016c8a  mov     ebx, eax
0x180016c8c  test    eax, eax
0x180016c8e  js      short loc_180016CB9
0x180016c90  mov     rcx, [rsp+48h+pszIconPath]; pszIconPath
0x180016c95  lea     rax, ?c_szStar@CFtpIcon@@2QBGB; ushort const near * const CFtpIcon::c_szStar
0x180016c9c  cmp     rcx, rax
0x180016c9f  jz      short loc_180016CB9
0x180016ca1  mov     edx, [rdi]; iIconIndex
0x180016ca3  xor     r8d, r8d; uIconFlags
0x180016ca6  call    cs:__imp_Shell_GetCachedImageIndexW
0x180016cac  cmp     eax, 0FFFFFFFFh
0x180016caf  mov     [rdi], eax
0x180016cb1  mov     ecx, 80004005h
0x180016cb6  cmovz   ebx, ecx
0x180016cb9  mov     eax, ebx
0x180016cbb  mov     rbx, [rsp+48h+arg_8]
0x180016cc0  mov     rbp, [rsp+48h+arg_10]
0x180016cc5  add     rsp, 30h
0x180016cc9  pop     r14
0x180016ccb  pop     rdi
0x180016ccc  pop     rsi
0x180016ccd  retn
```
