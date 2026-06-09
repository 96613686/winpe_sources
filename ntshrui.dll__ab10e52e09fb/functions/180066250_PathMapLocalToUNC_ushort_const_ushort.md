# PathMapLocalToUNC(ushort const *,ushort * *)

- ea: `0x180066250`
- end: `0x180066382`
- name: `?PathMapLocalToUNC@@YAJPEBGPEAPEAG@Z`
- size: `306`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, reparse_path, registry_config`

## callers

- `0x180066028`
- `0x180066ba4`
- `0x180072bb8`

## callees

- `0x180010fa0`
- `0x180013220`
- `0x18001b5a0`
- `0x1800254e0`
- `0x180066250`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180066329`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180066329`
- `KERNEL32!lstrlenW` at `0x1800662e3`
- `KERNEL32!lstrlenW` at `0x180066312`
- `KERNEL32!lstrlenW` at `0x1800662e3`
- `KERNEL32!lstrlenW` at `0x180066312`
- `SHCORE!__imp_PathIsNetworkPathW` at `0x18006628f`
- `SHCORE!__imp_PathIsNetworkPathW` at `0x18006628f`
- `SHLWAPI!PathRemoveFileSpecW` at `0x1800662ff`
- `SHLWAPI!PathRemoveFileSpecW` at `0x1800662ff`

## pseudocode

```c
__int64 __fastcall PathMapLocalToUNC(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  HRESULT v3; // ebx
  int v4; // eax
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r9
  _DWORD v9[4]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR String[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR pszPath[264]; // [rsp+250h] [rbp+150h] BYREF

  *a2 = 0;
  v3 = -2147467259;
  if ( !PathIsNetworkPathW(a1) && (int)StringCchCopyW(pszPath, 0x104u, a1) >= 0 )
  {
    while ( 1 )
    {
      v9[0] = 0;
      if ( (unsigned int)GetNetResourceFromLocalPathW(pszPath, String, 260, v9) )
      {
        if ( *((_WORD *)&v9[3] + lstrlenW(String) + 1) != 36 )
          break;
      }
      if ( !PathRemoveFileSpecW(pszPath) )
        return (unsigned int)v3;
    }
    v4 = lstrlenW(pszPath);
    v3 = PathCchAppend(String, 0x104u, &a1[v4]);
    if ( v3 >= 0 )
    {
      v7 = -1;
      do
        ++v7;
      while ( String[v7] );
      return (unsigned int)_AllocStringWorker<CTCoAllocPolicy>(v6, v5, String, v7);
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180066250  mov     [rsp-8+arg_10], rbx
0x180066255  mov     [rsp-8+arg_18], rsi
0x18006625a  push    rbp
0x18006625b  push    rdi
0x18006625c  push    r14
0x18006625e  lea     rbp, [rsp-370h]
0x180066266  sub     rsp, 470h
0x18006626d  mov     rax, cs:__security_cookie
0x180066274  xor     rax, rsp
0x180066277  mov     [rbp+380h+var_20], rax
0x18006627e  xor     r14d, r14d
0x180066281  mov     rsi, rdx
0x180066284  mov     [rdx], r14
0x180066287  mov     rdi, rcx
0x18006628a  mov     ebx, 80004005h
0x18006628f  call    cs:__imp_PathIsNetworkPathW
0x180066295  test    eax, eax
0x180066297  jnz     loc_180066359
0x18006629d  mov     r8, rdi; unsigned __int16 *
0x1800662a0  lea     rcx, [rbp+380h+pszPath]; unsigned __int16 *
0x1800662a7  mov     edx, 104h; unsigned __int64
0x1800662ac  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800662b1  test    eax, eax
0x1800662b3  js      loc_180066359
0x1800662b9  lea     r9, [rsp+480h+var_450]
0x1800662be  mov     [rsp+480h+var_450], r14d
0x1800662c3  mov     r8d, 104h
0x1800662c9  lea     rdx, [rsp+480h+String]
0x1800662ce  lea     rcx, [rbp+380h+pszPath]
0x1800662d5  call    GetNetResourceFromLocalPathW
0x1800662da  test    eax, eax
0x1800662dc  jz      short loc_1800662F8
0x1800662de  lea     rcx, [rsp+480h+String]; lpString
0x1800662e3  call    cs:__imp_lstrlenW
0x1800662e9  movsxd  rcx, eax
0x1800662ec  mov     eax, 24h ; '$'
0x1800662f1  cmp     ax, [rsp+rcx*2+480h+var_442]
0x1800662f6  jnz     short loc_18006630B
0x1800662f8  lea     rcx, [rbp+380h+pszPath]; pszPath
0x1800662ff  call    cs:__imp_PathRemoveFileSpecW
0x180066305  test    eax, eax
0x180066307  jnz     short loc_1800662B9
0x180066309  jmp     short loc_180066359
0x18006630b  lea     rcx, [rbp+380h+pszPath]; lpString
0x180066312  call    cs:__imp_lstrlenW
0x180066318  movsxd  rcx, eax
0x18006631b  mov     edx, 104h; cchPath
0x180066320  lea     r8, [rdi+rcx*2]; pszMore
0x180066324  lea     rcx, [rsp+480h+String]; pszPath
0x180066329  call    cs:__imp_PathCchAppend
0x18006632f  mov     ebx, eax
0x180066331  test    eax, eax
0x180066333  js      short loc_180066359
0x180066335  lea     rax, [rsp+480h+String]
0x18006633a  or      r9, 0FFFFFFFFFFFFFFFFh
0x18006633e  inc     r9
0x180066341  cmp     [rax+r9*2], r14w
0x180066346  jnz     short loc_18006633E
0x180066348  lea     r8, [rsp+480h+String]
0x18006634d  mov     [rsp+480h+var_458], rsi
0x180066352  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x180066357  mov     ebx, eax
0x180066359  mov     eax, ebx
0x18006635b  mov     rcx, [rbp+380h+var_20]
0x180066362  xor     rcx, rsp; StackCookie
0x180066365  call    __security_check_cookie
0x18006636a  lea     r11, [rsp+480h+var_10]
0x180066372  mov     rbx, [r11+30h]
0x180066376  mov     rsi, [r11+38h]
0x18006637a  mov     rsp, r11
0x18006637d  pop     r14
0x18006637f  pop     rdi
0x180066380  pop     rbp
0x180066381  retn
```
