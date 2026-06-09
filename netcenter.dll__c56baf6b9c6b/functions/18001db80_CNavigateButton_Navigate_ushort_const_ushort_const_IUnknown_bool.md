# CNavigateButton::Navigate(ushort const *,ushort const *,IUnknown *,bool)

- ea: `0x18001db80`
- end: `0x18001dd9a`
- name: `?Navigate@CNavigateButton@@SAXPEBG0PEAUIUnknown@@_N@Z`
- size: `538`
- prototype: `void __fastcall(const unsigned __int16 *, const unsigned __int16 *, struct IUnknown *, bool)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001e2c4`

## callees

- `0x180002270`
- `0x18001da70`
- `0x18001db80`
- `0x18001e0c8`
- `0x180023010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18001dbd6`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18001dbd6`
- `SHELL32!SHParseDisplayName` at `0x18001dc46`
- `SHELL32!SHParseDisplayName` at `0x18001dc46`
- `SHELL32!SHBindToObject` at `0x18001dc82`
- `SHELL32!SHBindToObject` at `0x18001dc82`
- `SHELL32!__imp_ILClone` at `0x18001dd15`
- `SHELL32!__imp_ILClone` at `0x18001dd15`
- `SHELL32!__imp_ILCombine` at `0x18001dcd4`
- `SHELL32!__imp_ILCombine` at `0x18001dcd4`
- `SHELL32!__imp_ILFree` at `0x18001dcf2`
- `SHELL32!__imp_ILFree` at `0x18001dd37`
- `SHELL32!__imp_ILFree` at `0x18001dd62`
- `SHELL32!__imp_ILFree` at `0x18001dcf2`
- `SHELL32!__imp_ILFree` at `0x18001dd37`
- `SHELL32!__imp_ILFree` at `0x18001dd62`

## pseudocode

```c
void __fastcall CNavigateButton::Navigate(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        struct IUnknown *a3,
        unsigned __int8 a4)
{
  int v4; // r15d
  unsigned int v7; // r8d
  char v8; // al
  char v9; // si
  HRESULT CplRoot; // eax
  HRESULT v11; // ebx
  ITEMIDLIST *v12; // rdi
  LPITEMIDLIST ppidl; // [rsp+40h] [rbp-C0h] BYREF
  void *ppvOut; // [rsp+48h] [rbp-B8h] BYREF
  LPCITEMIDLIST pidl2; // [rsp+50h] [rbp-B0h] BYREF
  void *ppv; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR pszName[264]; // [rsp+60h] [rbp-A0h] BYREF

  v4 = a4;
  ppvOut = 0;
  if ( IUnknown_QueryService(
         a3,
         (const GUID *const)&SID_STopLevelBrowser,
         &GUID_000214e2_0000_0000_c000_000000000046,
         &ppvOut) < 0 )
    return;
  ppidl = 0;
  if ( !a1 || (v8 = 1, !*a1) )
    v8 = 0;
  if ( !a2 || (v9 = 1, !*a2) )
    v9 = 0;
  if ( !v8 )
  {
    CplRoot = CNavigateButton::GetCplRoot((struct IShellBrowser *)ppvOut, &ppidl);
LABEL_12:
    v11 = CplRoot;
    goto LABEL_13;
  }
  v11 = TranslateCplCanonicalName(a1, pszName, v7);
  if ( v11 >= 0 )
  {
    CplRoot = SHParseDisplayName(pszName, 0, &ppidl, 0, 0);
    goto LABEL_12;
  }
LABEL_13:
  v12 = 0;
  if ( v11 >= 0 )
  {
    if ( v9 )
    {
      ppv = 0;
      v11 = SHBindToObject(0, ppidl, 0, &GUID_000214e6_0000_0000_c000_000000000046, &ppv);
      if ( v11 >= 0 )
      {
        pidl2 = 0;
        v11 = (*(__int64 (__fastcall **)(void *, _QWORD, _QWORD, const unsigned __int16 *, _QWORD, LPCITEMIDLIST *, _QWORD))(*(_QWORD *)ppv + 24LL))(
                ppv,
                0,
                0,
                a2,
                0,
                &pidl2,
                0);
        if ( v11 >= 0 )
        {
          v12 = ILCombine(ppidl, pidl2);
          v11 = v12 == 0 ? 0x8007000E : 0;
          ILFree((LPITEMIDLIST)pidl2);
        }
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
      }
    }
    else if ( ppidl )
    {
      v12 = ILClone(ppidl);
      v11 = v12 == 0 ? 0x8007000E : 0;
    }
    else
    {
      v11 = -2147024809;
    }
  }
  ILFree(ppidl);
  if ( v11 >= 0 )
  {
    (*(void (__fastcall **)(void *, ITEMIDLIST *, _QWORD))(*(_QWORD *)ppvOut + 88LL))(
      ppvOut,
      v12,
      (unsigned int)((v4 << 30) + 1));
    ILFree(v12);
  }
  (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
}

```

## disassembly

```asm
0x18001db80  push    rbp
0x18001db82  push    rbx
0x18001db83  push    rsi
0x18001db84  push    rdi
0x18001db85  push    r12
0x18001db87  push    r14
0x18001db89  push    r15
0x18001db8b  lea     rbp, [rsp-180h]
0x18001db93  sub     rsp, 280h
0x18001db9a  mov     rax, cs:__security_cookie
0x18001dba1  xor     rax, rsp
0x18001dba4  mov     [rbp+1B0h+var_40], rax
0x18001dbab  mov     rax, r8
0x18001dbae  movzx   r15d, r9b
0x18001dbb2  mov     r14, rdx
0x18001dbb5  lea     r9, [rsp+2B0h+ppvOut]; ppvOut
0x18001dbba  mov     rbx, rcx
0x18001dbbd  lea     r8, _GUID_000214e2_0000_0000_c000_000000000046; riid
0x18001dbc4  xor     r12d, r12d
0x18001dbc7  lea     rdx, SID_STopLevelBrowser; guidService
0x18001dbce  mov     rcx, rax; punk
0x18001dbd1  mov     [rsp+2B0h+ppvOut], r12
0x18001dbd6  call    cs:__imp_IUnknown_QueryService
0x18001dbdc  test    eax, eax
0x18001dbde  js      loc_18001DD79
0x18001dbe4  mov     [rsp+2B0h+ppidl], r12
0x18001dbe9  test    rbx, rbx
0x18001dbec  jz      short loc_18001DBF6
0x18001dbee  mov     al, 1
0x18001dbf0  cmp     [rbx], r12w
0x18001dbf4  jnz     short loc_18001DBF9
0x18001dbf6  mov     al, r12b
0x18001dbf9  test    r14, r14
0x18001dbfc  jz      short loc_18001DC07
0x18001dbfe  mov     sil, 1
0x18001dc01  cmp     [r14], r12w
0x18001dc05  jnz     short loc_18001DC0A
0x18001dc07  mov     sil, r12b
0x18001dc0a  test    al, al
0x18001dc0c  jnz     short loc_18001DC1F
0x18001dc0e  mov     rcx, [rsp+2B0h+ppvOut]; struct IShellBrowser *
0x18001dc13  lea     rdx, [rsp+2B0h+ppidl]; struct _ITEMIDLIST **
0x18001dc18  call    ?GetCplRoot@CNavigateButton@@CAJPEAUIShellBrowser@@PEAPEFAU_ITEMIDLIST@@@Z; CNavigateButton::GetCplRoot(IShellBrowser *,_ITEMIDLIST * *)
0x18001dc1d  jmp     short loc_18001DC4C
0x18001dc1f  lea     rdx, [rsp+2B0h+pszName]; unsigned __int16 *
0x18001dc24  mov     rcx, rbx; unsigned __int16 *
0x18001dc27  call    ?TranslateCplCanonicalName@@YAJPEBGPEAGI@Z; TranslateCplCanonicalName(ushort const *,ushort *,uint)
0x18001dc2c  mov     ebx, eax
0x18001dc2e  test    eax, eax
0x18001dc30  js      short loc_18001DC4E
0x18001dc32  xor     r9d, r9d; sfgaoIn
0x18001dc35  mov     [rsp+2B0h+psfgaoOut], r12; psfgaoOut
0x18001dc3a  lea     r8, [rsp+2B0h+ppidl]; ppidl
0x18001dc3f  xor     edx, edx; pbc
0x18001dc41  lea     rcx, [rsp+2B0h+pszName]; pszName
0x18001dc46  call    cs:__imp_SHParseDisplayName
0x18001dc4c  mov     ebx, eax
0x18001dc4e  mov     rdi, r12
0x18001dc51  test    ebx, ebx
0x18001dc53  js      loc_18001DD32
0x18001dc59  test    sil, sil
0x18001dc5c  jz      loc_18001DD0B
0x18001dc62  mov     rdx, [rsp+2B0h+ppidl]; pidl
0x18001dc67  lea     rax, [rsp+2B0h+ppv]
0x18001dc6c  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x18001dc73  mov     [rsp+2B0h+psfgaoOut], rax; ppv
0x18001dc78  xor     r8d, r8d; pbc
0x18001dc7b  mov     [rsp+2B0h+ppv], r12
0x18001dc80  xor     ecx, ecx; psf
0x18001dc82  call    cs:__imp_SHBindToObject
0x18001dc88  mov     ebx, eax
0x18001dc8a  test    eax, eax
0x18001dc8c  js      loc_18001DD32
0x18001dc92  mov     rcx, [rsp+2B0h+ppv]
0x18001dc97  lea     rdx, [rsp+2B0h+pidl2]
0x18001dc9c  mov     [rsp+2B0h+pidl2], r12
0x18001dca1  mov     r9, r14
0x18001dca4  mov     [rsp+2B0h+var_280], r12
0x18001dca9  xor     r8d, r8d
0x18001dcac  mov     [rsp+2B0h+var_288], rdx
0x18001dcb1  xor     edx, edx
0x18001dcb3  mov     rax, [rcx]
0x18001dcb6  mov     [rsp+2B0h+psfgaoOut], r12
0x18001dcbb  mov     rax, [rax+18h]
0x18001dcbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dcc4  mov     ebx, eax
0x18001dcc6  test    eax, eax
0x18001dcc8  js      short loc_18001DCF8
0x18001dcca  mov     rdx, [rsp+2B0h+pidl2]; pidl2
0x18001dccf  mov     rcx, [rsp+2B0h+ppidl]; pidl1
0x18001dcd4  call    cs:__imp_ILCombine
0x18001dcda  mov     rcx, rax
0x18001dcdd  mov     rdi, rax
0x18001dce0  neg     rcx
0x18001dce3  mov     rcx, [rsp+2B0h+pidl2]; pidl
0x18001dce8  sbb     ebx, ebx
0x18001dcea  not     ebx
0x18001dcec  and     ebx, 8007000Eh
0x18001dcf2  call    cs:__imp_ILFree
0x18001dcf8  mov     rcx, [rsp+2B0h+ppv]
0x18001dcfd  mov     rdx, [rcx]
0x18001dd00  mov     rax, [rdx+10h]
0x18001dd04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd09  jmp     short loc_18001DD32
0x18001dd0b  mov     rcx, [rsp+2B0h+ppidl]; pidl
0x18001dd10  test    rcx, rcx
0x18001dd13  jz      short loc_18001DD2D
0x18001dd15  call    cs:__imp_ILClone
0x18001dd1b  mov     rdi, rax
0x18001dd1e  neg     rax
0x18001dd21  sbb     ebx, ebx
0x18001dd23  not     ebx
0x18001dd25  and     ebx, 8007000Eh
0x18001dd2b  jmp     short loc_18001DD32
0x18001dd2d  mov     ebx, 80070057h
0x18001dd32  mov     rcx, [rsp+2B0h+ppidl]; pidl
0x18001dd37  call    cs:__imp_ILFree
0x18001dd3d  test    ebx, ebx
0x18001dd3f  js      short loc_18001DD68
0x18001dd41  mov     rcx, [rsp+2B0h+ppvOut]
0x18001dd46  mov     r8d, r15d
0x18001dd49  shl     r8d, 1Eh
0x18001dd4d  mov     rdx, rdi
0x18001dd50  inc     r8d
0x18001dd53  mov     rax, [rcx]
0x18001dd56  mov     rax, [rax+58h]
0x18001dd5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd5f  mov     rcx, rdi; pidl
0x18001dd62  call    cs:__imp_ILFree
0x18001dd68  mov     rcx, [rsp+2B0h+ppvOut]
0x18001dd6d  mov     rax, [rcx]
0x18001dd70  mov     rax, [rax+10h]
0x18001dd74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd79  mov     rcx, [rbp+1B0h+var_40]
0x18001dd80  xor     rcx, rsp; StackCookie
0x18001dd83  call    __security_check_cookie
0x18001dd88  add     rsp, 280h
0x18001dd8f  pop     r15
0x18001dd91  pop     r14
0x18001dd93  pop     r12
0x18001dd95  pop     rdi
0x18001dd96  pop     rsi
0x18001dd97  pop     rbx
0x18001dd98  pop     rbp
0x18001dd99  retn
```
