# CNavigateButton::Navigate(ushort const *,ushort const *,IUnknown *,bool)

- ea: `0x1800300b0`
- end: `0x1800302b6`
- name: `?Navigate@CNavigateButton@@SAXPEBG0PEAUIUnknown@@_N@Z`
- size: `518`
- prototype: `void __fastcall(const unsigned __int16 *, const unsigned __int16 *, struct IUnknown *, bool)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800307dc`

## callees

- `0x180013090`
- `0x180018dcc`
- `0x18002ffa0`
- `0x1800300b0`
- `0x1800305e0`
- `0x180031070`
- `0x180032010`

## import_xrefs

- `SHELL32!SHParseDisplayName` at `0x180030176`
- `SHELL32!SHParseDisplayName` at `0x180030176`
- `SHELL32!SHBindToObject` at `0x1800301b7`
- `SHELL32!SHBindToObject` at `0x1800301b7`
- `SHELL32!__imp_ILFree` at `0x18003021a`
- `SHELL32!__imp_ILFree` at `0x180030253`
- `SHELL32!__imp_ILFree` at `0x18003027e`
- `SHELL32!__imp_ILFree` at `0x18003021a`
- `SHELL32!__imp_ILFree` at `0x180030253`
- `SHELL32!__imp_ILFree` at `0x18003027e`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180030106`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180030106`

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
  HRESULT v13; // eax
  LPITEMIDLIST ppidl; // [rsp+40h] [rbp-C0h] BYREF
  struct _ITEMIDLIST *v15; // [rsp+48h] [rbp-B8h] BYREF
  void *ppvOut; // [rsp+50h] [rbp-B0h] BYREF
  LPITEMIDLIST pidl; // [rsp+58h] [rbp-A8h] BYREF
  void *ppv; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR pszName[264]; // [rsp+70h] [rbp-90h] BYREF

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
  v15 = 0;
  v12 = 0;
  if ( v11 >= 0 )
  {
    if ( v9 )
    {
      ppv = 0;
      v11 = SHBindToObject(0, ppidl, 0, &GUID_000214e6_0000_0000_c000_000000000046, &ppv);
      if ( v11 >= 0 )
      {
        pidl = 0;
        v11 = (*(__int64 (__fastcall **)(void *, _QWORD, _QWORD, const unsigned __int16 *, _QWORD, LPITEMIDLIST *, _QWORD))(*(_QWORD *)ppv + 24LL))(
                ppv,
                0,
                0,
                a2,
                0,
                &pidl,
                0);
        if ( v11 >= 0 )
        {
          v11 = SHILCombine(ppidl, pidl, &v15);
          ILFree(pidl);
          v12 = v15;
        }
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
      }
    }
    else
    {
      v13 = SHILClone((const struct _ITEMIDLIST_RELATIVE *)ppidl, (struct _ITEMIDLIST_RELATIVE **)&v15);
      v12 = v15;
      v11 = v13;
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
0x1800300b0  push    rbp
0x1800300b2  push    rbx
0x1800300b3  push    rsi
0x1800300b4  push    rdi
0x1800300b5  push    r12
0x1800300b7  push    r14
0x1800300b9  push    r15
0x1800300bb  lea     rbp, [rsp-190h]
0x1800300c3  sub     rsp, 290h
0x1800300ca  mov     rax, cs:__security_cookie
0x1800300d1  xor     rax, rsp
0x1800300d4  mov     [rbp+1C0h+var_40], rax
0x1800300db  mov     rax, r8
0x1800300de  movzx   r15d, r9b
0x1800300e2  mov     r14, rdx
0x1800300e5  lea     r9, [rsp+2C0h+ppvOut]; ppvOut
0x1800300ea  mov     rbx, rcx
0x1800300ed  lea     r8, _GUID_000214e2_0000_0000_c000_000000000046; riid
0x1800300f4  xor     r12d, r12d
0x1800300f7  lea     rdx, SID_STopLevelBrowser; guidService
0x1800300fe  mov     rcx, rax; punk
0x180030101  mov     [rsp+2C0h+ppvOut], r12
0x180030106  call    cs:__imp_IUnknown_QueryService
0x18003010c  test    eax, eax
0x18003010e  js      loc_180030295
0x180030114  mov     [rsp+2C0h+ppidl], r12
0x180030119  test    rbx, rbx
0x18003011c  jz      short loc_180030126
0x18003011e  mov     al, 1
0x180030120  cmp     [rbx], r12w
0x180030124  jnz     short loc_180030129
0x180030126  mov     al, r12b
0x180030129  test    r14, r14
0x18003012c  jz      short loc_180030137
0x18003012e  mov     sil, 1
0x180030131  cmp     [r14], r12w
0x180030135  jnz     short loc_18003013A
0x180030137  mov     sil, r12b
0x18003013a  test    al, al
0x18003013c  jnz     short loc_18003014F
0x18003013e  mov     rcx, [rsp+2C0h+ppvOut]; struct IShellBrowser *
0x180030143  lea     rdx, [rsp+2C0h+ppidl]; struct _ITEMIDLIST **
0x180030148  call    ?GetCplRoot@CNavigateButton@@CAJPEAUIShellBrowser@@PEAPEFAU_ITEMIDLIST@@@Z; CNavigateButton::GetCplRoot(IShellBrowser *,_ITEMIDLIST * *)
0x18003014d  jmp     short loc_18003017C
0x18003014f  lea     rdx, [rsp+2C0h+pszName]; unsigned __int16 *
0x180030154  mov     rcx, rbx; unsigned __int16 *
0x180030157  call    ?TranslateCplCanonicalName@@YAJPEBGPEAGI@Z; TranslateCplCanonicalName(ushort const *,ushort *,uint)
0x18003015c  mov     ebx, eax
0x18003015e  test    eax, eax
0x180030160  js      short loc_18003017E
0x180030162  xor     r9d, r9d; sfgaoIn
0x180030165  mov     [rsp+2C0h+psfgaoOut], r12; psfgaoOut
0x18003016a  lea     r8, [rsp+2C0h+ppidl]; ppidl
0x18003016f  xor     edx, edx; pbc
0x180030171  lea     rcx, [rsp+2C0h+pszName]; pszName
0x180030176  call    cs:__imp_SHParseDisplayName
0x18003017c  mov     ebx, eax
0x18003017e  mov     [rsp+2C0h+var_278], r12
0x180030183  mov     rdi, r12
0x180030186  test    ebx, ebx
0x180030188  js      loc_18003024E
0x18003018e  test    sil, sil
0x180030191  jz      loc_180030238
0x180030197  mov     rdx, [rsp+2C0h+ppidl]; pidl
0x18003019c  lea     rax, [rsp+2C0h+ppv]
0x1800301a1  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x1800301a8  mov     [rsp+2C0h+psfgaoOut], rax; ppv
0x1800301ad  xor     r8d, r8d; pbc
0x1800301b0  mov     [rsp+2C0h+ppv], r12
0x1800301b5  xor     ecx, ecx; psf
0x1800301b7  call    cs:__imp_SHBindToObject
0x1800301bd  mov     ebx, eax
0x1800301bf  test    eax, eax
0x1800301c1  js      loc_18003024E
0x1800301c7  mov     rcx, [rsp+2C0h+ppv]
0x1800301cc  lea     rdx, [rsp+2C0h+pidl]
0x1800301d1  mov     [rsp+2C0h+pidl], r12
0x1800301d6  mov     r9, r14
0x1800301d9  mov     [rsp+2C0h+var_290], r12
0x1800301de  xor     r8d, r8d
0x1800301e1  mov     [rsp+2C0h+var_298], rdx
0x1800301e6  xor     edx, edx
0x1800301e8  mov     rax, [rcx]
0x1800301eb  mov     [rsp+2C0h+psfgaoOut], r12
0x1800301f0  mov     rax, [rax+18h]
0x1800301f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800301f9  mov     ebx, eax
0x1800301fb  test    eax, eax
0x1800301fd  js      short loc_180030225
0x1800301ff  mov     rdx, [rsp+2C0h+pidl]; struct _ITEMIDLIST *
0x180030204  lea     r8, [rsp+2C0h+var_278]; struct _ITEMIDLIST **
0x180030209  mov     rcx, [rsp+2C0h+ppidl]; struct _ITEMIDLIST *
0x18003020e  call    ?SHILCombine@@YAJPEFBU_ITEMIDLIST@@0PEAPEFAU1@@Z; SHILCombine(_ITEMIDLIST const *,_ITEMIDLIST const *,_ITEMIDLIST * *)
0x180030213  mov     rcx, [rsp+2C0h+pidl]; pidl
0x180030218  mov     ebx, eax
0x18003021a  call    cs:__imp_ILFree
0x180030220  mov     rdi, [rsp+2C0h+var_278]
0x180030225  mov     rcx, [rsp+2C0h+ppv]
0x18003022a  mov     rax, [rcx]
0x18003022d  mov     rax, [rax+10h]
0x180030231  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030236  jmp     short loc_18003024E
0x180030238  mov     rcx, [rsp+2C0h+ppidl]; struct _ITEMIDLIST_RELATIVE *
0x18003023d  lea     rdx, [rsp+2C0h+var_278]; struct _ITEMIDLIST_RELATIVE **
0x180030242  call    ?SHILClone@@YAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAU1@@Z; SHILClone(_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_RELATIVE * *)
0x180030247  mov     rdi, [rsp+2C0h+var_278]
0x18003024c  mov     ebx, eax
0x18003024e  mov     rcx, [rsp+2C0h+ppidl]; pidl
0x180030253  call    cs:__imp_ILFree
0x180030259  test    ebx, ebx
0x18003025b  js      short loc_180030284
0x18003025d  mov     rcx, [rsp+2C0h+ppvOut]
0x180030262  mov     r8d, r15d
0x180030265  shl     r8d, 1Eh
0x180030269  mov     rdx, rdi
0x18003026c  inc     r8d
0x18003026f  mov     rax, [rcx]
0x180030272  mov     rax, [rax+58h]
0x180030276  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003027b  mov     rcx, rdi; pidl
0x18003027e  call    cs:__imp_ILFree
0x180030284  mov     rcx, [rsp+2C0h+ppvOut]
0x180030289  mov     rax, [rcx]
0x18003028c  mov     rax, [rax+10h]
0x180030290  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030295  mov     rcx, [rbp+1C0h+var_40]
0x18003029c  xor     rcx, rsp; StackCookie
0x18003029f  call    __security_check_cookie
0x1800302a4  add     rsp, 290h
0x1800302ab  pop     r15
0x1800302ad  pop     r14
0x1800302af  pop     r12
0x1800302b1  pop     rdi
0x1800302b2  pop     rsi
0x1800302b3  pop     rbx
0x1800302b4  pop     rbp
0x1800302b5  retn
```
