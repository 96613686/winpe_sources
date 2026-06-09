# ParseUrlCreateFromPidl(_ITEMIDLIST const *,ushort *,ulong,ulong,int)

- ea: `0x18001d4c0`
- end: `0x18001d6b6`
- name: `?ParseUrlCreateFromPidl@@YAJPEFBU_ITEMIDLIST@@PEAGKKH@Z`
- size: `502`
- prototype: `__int64 __fastcall(const struct _ITEMIDLIST *, unsigned __int16 *, unsigned int, unsigned int, int)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x18001d6bc`

## callees

- `0x180002240`
- `0x180002b60`
- `0x18000958c`
- `0x180009650`
- `0x18001c870`
- `0x18001cad0`
- `0x18001cbd8`
- `0x18001cc1c`
- `0x18001d240`
- `0x18001d32c`
- `0x18001d4c0`
- `0x18001d840`
- `0x180021714`
- `0x1800271f0`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001d60d`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001d60d`

## pseudocode

```c
__int64 __fastcall ParseUrlCreateFromPidl(
        struct _ITEMIDLIST *a1,
        unsigned __int16 *a2,
        DWORD a3,
        unsigned int a4,
        int a5)
{
  unsigned int v9; // r8d
  unsigned int v10; // r8d
  unsigned int v11; // r8d
  __int16 v12; // r11
  const unsigned __int16 *v13; // r8
  const unsigned __int16 *p_sz; // rax
  INTERNET_PORT v15; // di
  struct tagFTPSERVERIDLIST *DataThunk; // rax
  const unsigned __int16 *v18; // [rsp+30h] [rbp-D0h]
  WCHAR sz; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v20[526]; // [rsp+52h] [rbp-AEh] BYREF
  unsigned __int16 v21[128]; // [rsp+260h] [rbp+160h] BYREF
  unsigned __int16 v22[128]; // [rsp+360h] [rbp+260h] BYREF
  unsigned __int16 v23[256]; // [rsp+460h] [rbp+360h] BYREF
  unsigned __int16 v24[264]; // [rsp+660h] [rbp+560h] BYREF
  unsigned __int16 v25[2088]; // [rsp+870h] [rbp+770h] BYREF

  sz = 0;
  memset_0(v20, 0, 0x206u);
  if ( !a1 || !a1->mkid.cb )
    return 2147500037LL;
  FtpPidl_GetServer(a1, v23, v9);
  UrlGetAbstractPathFromPidl(a1, 0, 0, (char *)v25, 0x824u);
  FtpPidl_GetUserName(a1, v22, 0x80u);
  if ( FtpPidl_GetPassword(a1, v21, v10, a5 == 0) < 0 )
    v21[0] = 0;
  FtpPidl_GetFragment(a1, v24, v11);
  sz = 0;
  if ( (FtpServerID_GetTypeID(a1) & 0x800) == 0 )
    goto LABEL_10;
  StringCchCopyW(&sz, 0x104u, L";type=");
  v13 = L"a";
  if ( (v12 & 0x1000) == 0 )
    v13 = L"i";
  StringCchCatW(&sz, 0x104u, v13);
  if ( sz == 47 )
    p_sz = CharNextW(&sz);
  else
LABEL_10:
    p_sz = &sz;
  StringCchCatW(v25, 0x824u, p_sz);
  v15 = 21;
  DataThunk = FtpServerID_GetDataThunk(a1);
  if ( DataThunk )
    v15 = *((_WORD *)DataThunk + 16);
  return UrlCreateEx(v23, v22, v21, v25, v24, v15, v18, a2, a3, a4);
}

```

## disassembly

```asm
0x18001d4c0  mov     [rsp-8+arg_10], rbx
0x18001d4c5  mov     [rsp-8+arg_18], rsi
0x18001d4ca  push    rbp
0x18001d4cb  push    rdi
0x18001d4cc  push    r12
0x18001d4ce  push    r14
0x18001d4d0  push    r15
0x18001d4d2  lea     rbp, [rsp-17D0h]
0x18001d4da  mov     eax, 18D0h
0x18001d4df  call    _alloca_probe
0x18001d4e4  sub     rsp, rax
0x18001d4e7  mov     rax, cs:__security_cookie
0x18001d4ee  xor     rax, rsp
0x18001d4f1  mov     [rbp+17F0h+var_30], rax
0x18001d4f8  mov     r14d, r8d
0x18001d4fb  mov     r15, rdx
0x18001d4fe  mov     rbx, rcx
0x18001d501  xor     r12d, r12d
0x18001d504  xor     edx, edx; Val
0x18001d506  mov     [rsp+18F0h+sz], r12w
0x18001d50c  mov     r8d, 206h; Size
0x18001d512  lea     rcx, [rsp+18F0h+var_189E]; void *
0x18001d517  mov     esi, r9d
0x18001d51a  call    memset_0
0x18001d51f  test    rbx, rbx
0x18001d522  jz      loc_18001D686
0x18001d528  cmp     [rbx], r12w
0x18001d52c  jz      loc_18001D686
0x18001d532  lea     rdx, [rbp+17F0h+var_1490]; unsigned __int16 *
0x18001d539  mov     rcx, rbx; struct _ITEMIDLIST *
0x18001d53c  call    ?FtpPidl_GetServer@@YAJPEFBU_ITEMIDLIST@@PEAGK@Z; FtpPidl_GetServer(_ITEMIDLIST const *,ushort *,ulong)
0x18001d541  lea     r9, [rbp+17F0h+var_1080]; void *
0x18001d548  mov     dword ptr [rsp+18F0h+var_18D0], 824h; unsigned int
0x18001d550  xor     r8d, r8d; int
0x18001d553  xor     edx, edx; int
0x18001d555  mov     rcx, rbx; struct _ITEMIDLIST *
0x18001d558  call    ?UrlGetAbstractPathFromPidl@@YAJPEFBU_ITEMIDLIST@@HHPEAXK@Z; UrlGetAbstractPathFromPidl(_ITEMIDLIST const *,int,int,void *,ulong)
0x18001d55d  mov     r8d, 80h; unsigned int
0x18001d563  lea     rdx, [rbp+17F0h+var_1590]; unsigned __int16 *
0x18001d56a  mov     rcx, rbx; struct _ITEMIDLIST *
0x18001d56d  call    ?FtpPidl_GetUserName@@YAJPEFBU_ITEMIDLIST@@PEAGK@Z; FtpPidl_GetUserName(_ITEMIDLIST const *,ushort *,ulong)
0x18001d572  cmp     [rbp+17F0h+arg_20], r12d
0x18001d579  lea     rdx, [rbp+17F0h+var_1690]; unsigned __int16 *
0x18001d580  mov     r9d, r12d
0x18001d583  mov     rcx, rbx; struct _ITEMIDLIST *
0x18001d586  setz    r9b; int
0x18001d58a  call    ?FtpPidl_GetPassword@@YAJPEFBU_ITEMIDLIST@@PEAGKH@Z; FtpPidl_GetPassword(_ITEMIDLIST const *,ushort *,ulong,int)
0x18001d58f  test    eax, eax
0x18001d591  jns     short loc_18001D59B
0x18001d593  mov     [rbp+17F0h+var_1690], r12w
0x18001d59b  lea     rdx, [rbp+17F0h+var_1290]; unsigned __int16 *
0x18001d5a2  mov     rcx, rbx; struct _ITEMIDLIST *
0x18001d5a5  call    ?FtpPidl_GetFragment@@YAJPEFBU_ITEMIDLIST@@PEAGK@Z; FtpPidl_GetFragment(_ITEMIDLIST const *,ushort *,ulong)
0x18001d5aa  mov     rcx, rbx; struct _ITEMIDLIST *
0x18001d5ad  call    ?FtpServerID_GetTypeID@@YAKPEFBU_ITEMIDLIST@@@Z; FtpServerID_GetTypeID(_ITEMIDLIST const *)
0x18001d5b2  mov     [rsp+18F0h+sz], r12w
0x18001d5b8  mov     r11d, eax
0x18001d5bb  bt      eax, 0Bh
0x18001d5bf  jnb     short loc_18001D615
0x18001d5c1  mov     edi, 104h
0x18001d5c6  lea     r8, pszSrch; ";type="
0x18001d5cd  mov     edx, edi; unsigned __int64
0x18001d5cf  lea     rcx, [rsp+18F0h+sz]; unsigned __int16 *
0x18001d5d4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001d5d9  bt      r11d, 0Ch
0x18001d5de  lea     rax, aI; "i"
0x18001d5e5  lea     r8, aA; "a"
0x18001d5ec  mov     edx, edi; unsigned __int64
0x18001d5ee  cmovnb  r8, rax; unsigned __int16 *
0x18001d5f2  lea     rcx, [rsp+18F0h+sz]; unsigned __int16 *
0x18001d5f7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001d5fc  mov     eax, 2Fh ; '/'
0x18001d601  cmp     ax, [rsp+18F0h+sz]
0x18001d606  jnz     short loc_18001D615
0x18001d608  lea     rcx, [rsp+18F0h+sz]; lpsz
0x18001d60d  call    cs:__imp_CharNextW
0x18001d613  jmp     short loc_18001D61A
0x18001d615  lea     rax, [rsp+18F0h+sz]
0x18001d61a  mov     r8, rax; unsigned __int16 *
0x18001d61d  lea     rcx, [rbp+17F0h+var_1080]; unsigned __int16 *
0x18001d624  mov     edx, 824h; unsigned __int64
0x18001d629  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001d62e  mov     rcx, rbx; struct _ITEMIDLIST *
0x18001d631  mov     edi, 15h
0x18001d636  call    ?FtpServerID_GetDataThunk@@YAPEFAUtagFTPSERVERIDLIST@@PEFAU_ITEMIDLIST@@@Z; FtpServerID_GetDataThunk(_ITEMIDLIST *)
0x18001d63b  test    rax, rax
0x18001d63e  jz      short loc_18001D644
0x18001d640  movzx   edi, word ptr [rax+20h]
0x18001d644  mov     [rsp+18F0h+var_18A8], esi; unsigned int
0x18001d648  lea     rax, [rbp+17F0h+var_1290]
0x18001d64f  mov     [rsp+18F0h+dwUrlLength], r14d; dwUrlLength
0x18001d654  lea     r9, [rbp+17F0h+var_1080]; unsigned __int16 *
0x18001d65b  mov     [rsp+18F0h+lpszUrl], r15; lpszUrl
0x18001d660  lea     r8, [rbp+17F0h+var_1690]; unsigned __int16 *
0x18001d667  mov     [rsp+18F0h+var_18C8], di; unsigned __int16
0x18001d66c  lea     rdx, [rbp+17F0h+var_1590]; unsigned __int16 *
0x18001d673  lea     rcx, [rbp+17F0h+var_1490]; unsigned __int16 *
0x18001d67a  mov     [rsp+18F0h+var_18D0], rax; unsigned __int16 *
0x18001d67f  call    ?UrlCreateEx@@YAJPEBG0000G0PEAGKK@Z; UrlCreateEx(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort,ushort const *,ushort *,ulong,ulong)
0x18001d684  jmp     short loc_18001D68B
0x18001d686  mov     eax, 80004005h
0x18001d68b  mov     rcx, [rbp+17F0h+var_30]
0x18001d692  xor     rcx, rsp; StackCookie
0x18001d695  call    __security_check_cookie
0x18001d69a  lea     r11, [rsp+18F0h+var_20]
0x18001d6a2  mov     rbx, [r11+40h]
0x18001d6a6  mov     rsi, [r11+48h]
0x18001d6aa  mov     rsp, r11
0x18001d6ad  pop     r15
0x18001d6af  pop     r14
0x18001d6b1  pop     r12
0x18001d6b3  pop     rdi
0x18001d6b4  pop     rbp
0x18001d6b5  retn
```
