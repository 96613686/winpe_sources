# PathMapUNCToLocal(ushort const *,ushort * *)

- ea: `0x1800572e4`
- end: `0x18005740d`
- name: `?PathMapUNCToLocal@@YAJPEBGPEAPEAG@Z`
- size: `297`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, registry_config`

## callers

- `0x18005bb88`

## callees

- `0x180013220`
- `0x1800144b0`
- `0x18001b5a0`
- `0x1800254e0`
- `0x1800572e4`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800573b2`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800573b2`
- `KERNEL32!lstrlenW` at `0x180057388`
- `KERNEL32!lstrlenW` at `0x180057388`
- `SHCORE!__imp_PathIsNetworkPathW` at `0x180057315`
- `SHCORE!__imp_PathIsNetworkPathW` at `0x180057315`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180057377`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180057377`

## pseudocode

```c
__int64 __fastcall PathMapUNCToLocal(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  HRESULT v3; // ebx
  const unsigned __int16 *v4; // rax
  const WCHAR *v5; // r8
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r9
  _DWORD v10[4]; // [rsp+30h] [rbp-458h] BYREF
  WCHAR pszPath[264]; // [rsp+40h] [rbp-448h] BYREF
  WCHAR v12[264]; // [rsp+250h] [rbp-238h] BYREF

  *a2 = 0;
  v3 = -2147467259;
  if ( PathIsNetworkPathW(a1) && (int)StringCchCopyW(pszPath, 0x104u, a1) >= 0 )
  {
    while ( 1 )
    {
      v10[0] = 0;
      if ( (unsigned int)GetLocalPathFromNetResourceW(pszPath, 0x20000, v12, 260, v10) )
      {
        if ( v10[0] )
          break;
      }
      if ( !PathRemoveFileSpecW(pszPath) )
        return (unsigned int)v3;
    }
    v4 = &a1[lstrlenW(pszPath)];
    v5 = v4 + 1;
    if ( *v4 != 92 )
      v5 = v4;
    v3 = PathCchAppend(v12, 0x104u, v5);
    if ( v3 >= 0 )
    {
      v8 = -1;
      do
        ++v8;
      while ( v12[v8] );
      return (unsigned int)_AllocStringWorker<CTCoAllocPolicy>(v7, v6, v12, v8);
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800572e4  mov     [rsp+arg_10], rbx
0x1800572e9  push    rbp
0x1800572ea  push    rsi
0x1800572eb  push    rdi
0x1800572ec  sub     rsp, 470h
0x1800572f3  mov     rax, cs:__security_cookie
0x1800572fa  xor     rax, rsp
0x1800572fd  mov     [rsp+488h+var_28], rax
0x180057305  xor     ebp, ebp
0x180057307  mov     rsi, rdx
0x18005730a  mov     [rdx], rbp
0x18005730d  mov     rdi, rcx
0x180057310  mov     ebx, 80004005h
0x180057315  call    cs:__imp_PathIsNetworkPathW
0x18005731b  test    eax, eax
0x18005731d  jz      loc_1800573E8
0x180057323  mov     r8, rdi; unsigned __int16 *
0x180057326  lea     rcx, [rsp+488h+pszPath]; unsigned __int16 *
0x18005732b  mov     edx, 104h; unsigned __int64
0x180057330  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180057335  test    eax, eax
0x180057337  js      loc_1800573E8
0x18005733d  lea     rax, [rsp+488h+var_458]
0x180057342  mov     [rsp+488h+var_458], ebp
0x180057346  mov     r9d, 104h
0x18005734c  mov     [rsp+488h+var_468], rax
0x180057351  lea     r8, [rsp+488h+var_238]
0x180057359  mov     edx, 20000h
0x18005735e  lea     rcx, [rsp+488h+pszPath]
0x180057363  call    GetLocalPathFromNetResourceW
0x180057368  test    eax, eax
0x18005736a  jz      short loc_180057372
0x18005736c  cmp     [rsp+488h+var_458], ebp
0x180057370  jnz     short loc_180057383
0x180057372  lea     rcx, [rsp+488h+pszPath]; pszPath
0x180057377  call    cs:__imp_PathRemoveFileSpecW
0x18005737d  test    eax, eax
0x18005737f  jnz     short loc_18005733D
0x180057381  jmp     short loc_1800573E8
0x180057383  lea     rcx, [rsp+488h+pszPath]; lpString
0x180057388  call    cs:__imp_lstrlenW
0x18005738e  movsxd  rcx, eax
0x180057391  mov     edx, 104h; cchPath
0x180057396  lea     rax, [rdi+rcx*2]
0x18005739a  mov     ecx, 5Ch ; '\'
0x18005739f  cmp     cx, [rax]
0x1800573a2  lea     r8, [rax+2]
0x1800573a6  lea     rcx, [rsp+488h+var_238]; pszPath
0x1800573ae  cmovnz  r8, rax; pszMore
0x1800573b2  call    cs:__imp_PathCchAppend
0x1800573b8  mov     ebx, eax
0x1800573ba  test    eax, eax
0x1800573bc  js      short loc_1800573E8
0x1800573be  lea     rax, [rsp+488h+var_238]
0x1800573c6  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800573ca  inc     r9
0x1800573cd  cmp     [rax+r9*2], bp
0x1800573d2  jnz     short loc_1800573CA
0x1800573d4  lea     r8, [rsp+488h+var_238]
0x1800573dc  mov     [rsp+488h+var_460], rsi
0x1800573e1  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x1800573e6  mov     ebx, eax
0x1800573e8  mov     eax, ebx
0x1800573ea  mov     rcx, [rsp+488h+var_28]
0x1800573f2  xor     rcx, rsp; StackCookie
0x1800573f5  call    __security_check_cookie
0x1800573fa  mov     rbx, [rsp+488h+arg_10]
0x180057402  add     rsp, 470h
0x180057409  pop     rdi
0x18005740a  pop     rsi
0x18005740b  pop     rbp
0x18005740c  retn
```
