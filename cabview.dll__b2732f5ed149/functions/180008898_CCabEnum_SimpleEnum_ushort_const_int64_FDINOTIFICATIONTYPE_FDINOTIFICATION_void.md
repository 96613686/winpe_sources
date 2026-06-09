# CCabEnum::SimpleEnum(ushort const *,__int64 (*)(FDINOTIFICATIONTYPE,FDINOTIFICATION *),void *)

- ea: `0x180008898`
- end: `0x18000898b`
- name: `?SimpleEnum@CCabEnum@@IEAAHPEBGP6A_JW4FDINOTIFICATIONTYPE@@PEAUFDINOTIFICATION@@@ZPEAX@Z`
- size: `243`
- prototype: `__int64 __fastcall(CCabEnum *__hidden this, PCWSTR pwszSrc, PFNFDINOTIFY pfnfdin, void *pvUser)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180005658`
- `0x18000eb9c`

## callees

- `0x180002620`
- `0x180008898`
- `0x180008a74`
- `0x180008b8c`

## import_xrefs

- `SHLWAPI!PathFindFileNameA` at `0x1800088f4`
- `SHLWAPI!PathFindFileNameA` at `0x1800088f4`
- `SHLWAPI!__imp_SHUnicodeToAnsi` at `0x1800088d2`
- `SHLWAPI!__imp_SHUnicodeToAnsi` at `0x1800088d2`
- `Cabinet!__imp_FDICopy` at `0x18000894d`
- `Cabinet!__imp_FDICopy` at `0x18000894d`
- `Cabinet!__imp_FDIDestroy` at `0x18000895d`
- `Cabinet!__imp_FDIDestroy` at `0x18000895d`

## pseudocode

```c
__int64 __fastcall CCabEnum::SimpleEnum(CCabEnum *this, PCWSTR pwszSrc, PFNFDINOTIFY pfnfdin, void *pvUser)
{
  const char *FileNameA; // rax
  _BYTE *v8; // r10
  unsigned int v9; // edi
  CHAR pszPath[272]; // [rsp+40h] [rbp-358h] BYREF
  CHAR pszDst[272]; // [rsp+150h] [rbp-248h] BYREF
  CHAR pszCabinet[272]; // [rsp+260h] [rbp-138h] BYREF

  SHUnicodeToAnsi(pwszSrc, pszDst, 260);
  StringCchCopyA(pszPath, 0x104u, pszDst);
  FileNameA = PathFindFileNameA(pszPath);
  if ( !FileNameA )
    return 0;
  StringCchCopyA(pszCabinet, 0x104u, FileNameA);
  *v8 = 0;
  if ( !(unsigned int)CCabEnum::StartEnum(this) )
    return 0;
  v9 = FDICopy(*(HFDI *)this, pszCabinet, pszPath, 0, pfnfdin, 0, pvUser);
  if ( *(_QWORD *)this )
  {
    FDIDestroy(*(HFDI *)this);
    *(_QWORD *)this = 0;
  }
  return v9;
}

```

## disassembly

```asm
0x180008898  push    rbx
0x18000889a  push    rsi
0x18000889b  push    rdi
0x18000889c  sub     rsp, 380h
0x1800088a3  mov     rax, cs:__security_cookie
0x1800088aa  xor     rax, rsp
0x1800088ad  mov     [rsp+398h+var_28], rax
0x1800088b5  mov     rax, rdx
0x1800088b8  mov     rdi, r8
0x1800088bb  mov     rbx, rcx
0x1800088be  lea     rdx, [rsp+398h+pszDst]; pszDst
0x1800088c6  mov     rcx, rax; pwszSrc
0x1800088c9  mov     r8d, 104h; cchBuf
0x1800088cf  mov     rsi, r9
0x1800088d2  call    cs:__imp_SHUnicodeToAnsi
0x1800088d8  lea     r8, [rsp+398h+pszDst]; char *
0x1800088e0  mov     edx, 104h; unsigned __int64
0x1800088e5  lea     rcx, [rsp+398h+pszPath]; char *
0x1800088ea  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800088ef  lea     rcx, [rsp+398h+pszPath]; pszPath
0x1800088f4  call    cs:__imp_PathFindFileNameA
0x1800088fa  mov     r10, rax
0x1800088fd  test    rax, rax
0x180008900  jz      short loc_18000896E
0x180008902  mov     r8, rax; char *
0x180008905  lea     rcx, [rsp+398h+pszCabinet]; char *
0x18000890d  mov     edx, 104h; unsigned __int64
0x180008912  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180008917  mov     rcx, rbx; this
0x18000891a  mov     byte ptr [r10], 0
0x18000891e  call    ?StartEnum@CCabEnum@@IEAAHXZ; CCabEnum::StartEnum(void)
0x180008923  test    eax, eax
0x180008925  jz      short loc_18000896E
0x180008927  mov     rcx, [rbx]; hfdi
0x18000892a  lea     r8, [rsp+398h+pszPath]; pszCabPath
0x18000892f  mov     [rsp+398h+pvUser], rsi; pvUser
0x180008934  lea     rdx, [rsp+398h+pszCabinet]; pszCabinet
0x18000893c  mov     [rsp+398h+pfnfdid], 0; pfnfdid
0x180008945  xor     r9d, r9d; flags
0x180008948  mov     [rsp+398h+pfnfdin], rdi; pfnfdin
0x18000894d  call    cs:__imp_FDICopy
0x180008953  mov     rcx, [rbx]; hfdi
0x180008956  mov     edi, eax
0x180008958  test    rcx, rcx
0x18000895b  jz      short loc_18000896A
0x18000895d  call    cs:__imp_FDIDestroy
0x180008963  mov     qword ptr [rbx], 0
0x18000896a  mov     eax, edi
0x18000896c  jmp     short loc_180008970
0x18000896e  xor     eax, eax
0x180008970  mov     rcx, [rsp+398h+var_28]
0x180008978  xor     rcx, rsp; StackCookie
0x18000897b  call    __security_check_cookie
0x180008980  add     rsp, 380h
0x180008987  pop     rdi
0x180008988  pop     rsi
0x180008989  pop     rbx
0x18000898a  retn
```
