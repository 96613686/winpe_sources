# CConnectionFolder::ParseDisplayName(HWND__ *,IBindCtx *,ushort *,ulong *,_ITEMIDLIST * *,ulong *)

- ea: `0x180048910`
- end: `0x180048a55`
- name: `?ParseDisplayName@CConnectionFolder@@UEAAJPEAUHWND__@@PEAUIBindCtx@@PEAGPEAKPEAPEFAU_ITEMIDLIST@@3@Z`
- size: `325`
- prototype: `int(CConnectionFolder *__hidden this, HWND, struct IBindCtx *, unsigned __int16 *, unsigned int *, struct _ITEMIDLIST **, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001fd0`
- `0x1800154c8`
- `0x18001e1e0`
- `0x180041fb4`
- `0x180048910`
- `0x180065010`

## import_xrefs

- `SHELL32!__imp_ILClone` at `0x1800489fb`
- `SHELL32!__imp_ILClone` at `0x1800489fb`
- `ole32!CLSIDFromString` at `0x1800489b9`
- `ole32!CLSIDFromString` at `0x1800489b9`

## pseudocode

```c
__int64 __fastcall CConnectionFolder::ParseDisplayName(
        CConnectionFolder *this,
        HWND a2,
        struct IBindCtx *a3,
        unsigned __int16 *a4,
        unsigned int *a5,
        struct _ITEMIDLIST **a6,
        unsigned int *a7)
{
  unsigned __int64 v9; // rax
  __int64 v10; // rcx
  int PidlByGuid; // ebx
  LPCITEMIDLIST pidl; // [rsp+30h] [rbp-38h] BYREF
  GUID pclsid; // [rsp+38h] [rbp-30h] BYREF

  if ( !a6 )
    return 2147500035LL;
  *a6 = 0;
  if ( !a4 )
    return 2147942487LL;
  v9 = -1;
  do
    ++v9;
  while ( a4[v9] );
  if ( v9 < 0x26 )
    return 2147942487LL;
  while ( *a4 == 58 )
    ++a4;
  if ( *a4 != 123 )
    return 2147942487LL;
  pclsid = 0;
  if ( CLSIDFromString(a4, &pclsid) < 0 )
    return 2147500037LL;
  if ( !g_ccl )
    CConnectionList::HrRefreshConManEntries((CConnectionList *)&g_ccl);
  pidl = 0;
  PidlByGuid = CConnectionList::HrFindPidlByGuid(v10, &pclsid, &pidl);
  if ( PidlByGuid )
    PidlByGuid = -2147024894;
  else
    *a6 = ILClone(pidl);
  CPConFoldPidl<ConFoldPidlFolder>::FreePIDLIfRequired(&pidl);
  if ( PidlByGuid >= 0 )
  {
    if ( a7 )
    {
      pidl = *a6;
      return (unsigned int)(*(__int64 (__fastcall **)(CConnectionFolder *, __int64, LPCITEMIDLIST *, unsigned int *))(*(_QWORD *)this + 72LL))(
                             this,
                             1,
                             &pidl,
                             a7);
    }
  }
  return (unsigned int)PidlByGuid;
}

```

## disassembly

```asm
0x180048910  mov     [rsp+arg_8], rbx
0x180048915  mov     [rsp+arg_10], rbp
0x18004891a  push    rsi
0x18004891b  push    rdi
0x18004891c  push    r14
0x18004891e  sub     rsp, 50h
0x180048922  mov     rax, cs:__security_cookie
0x180048929  xor     rax, rsp
0x18004892c  mov     [rsp+68h+var_20], rax
0x180048931  mov     rdi, [rsp+68h+arg_28]
0x180048939  xor     ebp, ebp
0x18004893b  mov     rsi, [rsp+68h+arg_30]
0x180048943  mov     r14, rcx
0x180048946  test    rdi, rdi
0x180048949  jnz     short loc_180048952
0x18004894b  mov     eax, 80004003h
0x180048950  jmp     short loc_180048973
0x180048952  mov     [rdi], rbp
0x180048955  test    r9, r9
0x180048958  jz      short loc_18004896E
0x18004895a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004895e  inc     rax
0x180048961  cmp     [r9+rax*2], bp
0x180048966  jnz     short loc_18004895E
0x180048968  cmp     rax, 26h ; '&'
0x18004896c  jnb     short loc_180048999
0x18004896e  mov     eax, 80070057h
0x180048973  mov     rcx, [rsp+68h+var_20]
0x180048978  xor     rcx, rsp; StackCookie
0x18004897b  call    __security_check_cookie
0x180048980  lea     r11, [rsp+68h+var_18]
0x180048985  mov     rbx, [r11+28h]
0x180048989  mov     rbp, [r11+30h]
0x18004898d  mov     rsp, r11
0x180048990  pop     r14
0x180048992  pop     rdi
0x180048993  pop     rsi
0x180048994  retn
0x180048995  add     r9, 2
0x180048999  movzx   eax, word ptr [r9]
0x18004899d  cmp     ax, 3Ah ; ':'
0x1800489a1  jz      short loc_180048995
0x1800489a3  cmp     ax, 7Bh ; '{'
0x1800489a7  jnz     short loc_18004896E
0x1800489a9  xorps   xmm0, xmm0
0x1800489ac  lea     rdx, [rsp+68h+pclsid]; pclsid
0x1800489b1  mov     rcx, r9; lpsz
0x1800489b4  movups  xmmword ptr [rsp+68h+pclsid.Data1], xmm0
0x1800489b9  call    cs:__imp_CLSIDFromString
0x1800489bf  test    eax, eax
0x1800489c1  js      loc_180048A4B
0x1800489c7  cmp     cs:?g_ccl@@3VCConnectionList@@A, rbp; CConnectionList g_ccl
0x1800489ce  jnz     short loc_1800489DC
0x1800489d0  lea     rcx, ?g_ccl@@3VCConnectionList@@A; this
0x1800489d7  call    ?HrRefreshConManEntries@CConnectionList@@QEAAJXZ; CConnectionList::HrRefreshConManEntries(void)
0x1800489dc  lea     r8, [rsp+68h+pidl]
0x1800489e1  mov     [rsp+68h+pidl], rbp
0x1800489e6  lea     rdx, [rsp+68h+pclsid]
0x1800489eb  call    ?HrFindPidlByGuid@CConnectionList@@QEAAJPEBU_GUID@@AEAV?$CPConFoldPidl@VConFoldPidl_v3@@@@@Z; CConnectionList::HrFindPidlByGuid(_GUID const *,CPConFoldPidl<ConFoldPidl_v3> &)
0x1800489f0  mov     ebx, eax
0x1800489f2  test    eax, eax
0x1800489f4  jnz     short loc_180048A06
0x1800489f6  mov     rcx, [rsp+68h+pidl]; pidl
0x1800489fb  call    cs:__imp_ILClone
0x180048a01  mov     [rdi], rax
0x180048a04  jmp     short loc_180048A0B
0x180048a06  mov     ebx, 80070002h
0x180048a0b  lea     rcx, [rsp+68h+pidl]
0x180048a10  call    ?FreePIDLIfRequired@?$CPConFoldPidl@VConFoldPidlFolder@@@@AEAAJXZ; CPConFoldPidl<ConFoldPidlFolder>::FreePIDLIfRequired(void)
0x180048a15  test    ebx, ebx
0x180048a17  js      short loc_180048A44
0x180048a19  test    rsi, rsi
0x180048a1c  jz      short loc_180048A44
0x180048a1e  mov     rax, [rdi]
0x180048a21  lea     r8, [rsp+68h+pidl]
0x180048a26  mov     [rsp+68h+pidl], rax
0x180048a2b  mov     r9, rsi
0x180048a2e  mov     rax, [r14]
0x180048a31  mov     edx, 1
0x180048a36  mov     rcx, r14
0x180048a39  mov     rax, [rax+48h]
0x180048a3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048a42  mov     ebx, eax
0x180048a44  mov     eax, ebx
0x180048a46  jmp     loc_180048973
0x180048a4b  mov     eax, 80004005h
0x180048a50  jmp     loc_180048973
```
