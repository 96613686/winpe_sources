# CNavigateButton::Navigate(ushort const *,ushort const *,IUnknown *,bool)

- ea: `0x180017e00`
- end: `0x18001801a`
- name: `?Navigate@CNavigateButton@@SAXPEBG0PEAUIUnknown@@_N@Z`
- size: `538`
- prototype: `void __fastcall(const unsigned __int16 *, const unsigned __int16 *, struct IUnknown *, bool)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001853c`

## callees

- `0x180017cf0`
- `0x180017e00`
- `0x180018340`
- `0x180018a80`
- `0x18001a010`

## import_xrefs

- `SHELL32!SHParseDisplayName` at `0x180017ec6`
- `SHELL32!SHParseDisplayName` at `0x180017ec6`
- `SHELL32!SHBindToObject` at `0x180017f02`
- `SHELL32!SHBindToObject` at `0x180017f02`
- `SHELL32!__imp_ILClone` at `0x180017f95`
- `SHELL32!__imp_ILClone` at `0x180017f95`
- `SHELL32!__imp_ILCombine` at `0x180017f54`
- `SHELL32!__imp_ILCombine` at `0x180017f54`
- `SHELL32!__imp_ILFree` at `0x180017f72`
- `SHELL32!__imp_ILFree` at `0x180017fb7`
- `SHELL32!__imp_ILFree` at `0x180017fe2`
- `SHELL32!__imp_ILFree` at `0x180017f72`
- `SHELL32!__imp_ILFree` at `0x180017fb7`
- `SHELL32!__imp_ILFree` at `0x180017fe2`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180017e56`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180017e56`

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
0x180017e00  push    rbp
0x180017e02  push    rbx
0x180017e03  push    rsi
0x180017e04  push    rdi
0x180017e05  push    r12
0x180017e07  push    r14
0x180017e09  push    r15
0x180017e0b  lea     rbp, [rsp-180h]
0x180017e13  sub     rsp, 280h
0x180017e1a  mov     rax, cs:__security_cookie
0x180017e21  xor     rax, rsp
0x180017e24  mov     [rbp+1B0h+var_40], rax
0x180017e2b  mov     rax, r8
0x180017e2e  movzx   r15d, r9b
0x180017e32  mov     r14, rdx
0x180017e35  lea     r9, [rsp+2B0h+ppvOut]; ppvOut
0x180017e3a  mov     rbx, rcx
0x180017e3d  lea     r8, _GUID_000214e2_0000_0000_c000_000000000046; riid
0x180017e44  xor     r12d, r12d
0x180017e47  lea     rdx, SID_STopLevelBrowser; guidService
0x180017e4e  mov     rcx, rax; punk
0x180017e51  mov     [rsp+2B0h+ppvOut], r12
0x180017e56  call    cs:__imp_IUnknown_QueryService
0x180017e5c  test    eax, eax
0x180017e5e  js      loc_180017FF9
0x180017e64  mov     [rsp+2B0h+ppidl], r12
0x180017e69  test    rbx, rbx
0x180017e6c  jz      short loc_180017E76
0x180017e6e  mov     al, 1
0x180017e70  cmp     [rbx], r12w
0x180017e74  jnz     short loc_180017E79
0x180017e76  mov     al, r12b
0x180017e79  test    r14, r14
0x180017e7c  jz      short loc_180017E87
0x180017e7e  mov     sil, 1
0x180017e81  cmp     [r14], r12w
0x180017e85  jnz     short loc_180017E8A
0x180017e87  mov     sil, r12b
0x180017e8a  test    al, al
0x180017e8c  jnz     short loc_180017E9F
0x180017e8e  mov     rcx, [rsp+2B0h+ppvOut]; struct IShellBrowser *
0x180017e93  lea     rdx, [rsp+2B0h+ppidl]; struct _ITEMIDLIST **
0x180017e98  call    ?GetCplRoot@CNavigateButton@@CAJPEAUIShellBrowser@@PEAPEFAU_ITEMIDLIST@@@Z; CNavigateButton::GetCplRoot(IShellBrowser *,_ITEMIDLIST * *)
0x180017e9d  jmp     short loc_180017ECC
0x180017e9f  lea     rdx, [rsp+2B0h+pszName]; unsigned __int16 *
0x180017ea4  mov     rcx, rbx; unsigned __int16 *
0x180017ea7  call    ?TranslateCplCanonicalName@@YAJPEBGPEAGI@Z; TranslateCplCanonicalName(ushort const *,ushort *,uint)
0x180017eac  mov     ebx, eax
0x180017eae  test    eax, eax
0x180017eb0  js      short loc_180017ECE
0x180017eb2  xor     r9d, r9d; sfgaoIn
0x180017eb5  mov     [rsp+2B0h+psfgaoOut], r12; psfgaoOut
0x180017eba  lea     r8, [rsp+2B0h+ppidl]; ppidl
0x180017ebf  xor     edx, edx; pbc
0x180017ec1  lea     rcx, [rsp+2B0h+pszName]; pszName
0x180017ec6  call    cs:__imp_SHParseDisplayName
0x180017ecc  mov     ebx, eax
0x180017ece  mov     rdi, r12
0x180017ed1  test    ebx, ebx
0x180017ed3  js      loc_180017FB2
0x180017ed9  test    sil, sil
0x180017edc  jz      loc_180017F8B
0x180017ee2  mov     rdx, [rsp+2B0h+ppidl]; pidl
0x180017ee7  lea     rax, [rsp+2B0h+ppv]
0x180017eec  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x180017ef3  mov     [rsp+2B0h+psfgaoOut], rax; ppv
0x180017ef8  xor     r8d, r8d; pbc
0x180017efb  mov     [rsp+2B0h+ppv], r12
0x180017f00  xor     ecx, ecx; psf
0x180017f02  call    cs:__imp_SHBindToObject
0x180017f08  mov     ebx, eax
0x180017f0a  test    eax, eax
0x180017f0c  js      loc_180017FB2
0x180017f12  mov     rcx, [rsp+2B0h+ppv]
0x180017f17  lea     rdx, [rsp+2B0h+pidl2]
0x180017f1c  mov     [rsp+2B0h+pidl2], r12
0x180017f21  mov     r9, r14
0x180017f24  mov     [rsp+2B0h+var_280], r12
0x180017f29  xor     r8d, r8d
0x180017f2c  mov     [rsp+2B0h+var_288], rdx
0x180017f31  xor     edx, edx
0x180017f33  mov     rax, [rcx]
0x180017f36  mov     [rsp+2B0h+psfgaoOut], r12
0x180017f3b  mov     rax, [rax+18h]
0x180017f3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f44  mov     ebx, eax
0x180017f46  test    eax, eax
0x180017f48  js      short loc_180017F78
0x180017f4a  mov     rdx, [rsp+2B0h+pidl2]; pidl2
0x180017f4f  mov     rcx, [rsp+2B0h+ppidl]; pidl1
0x180017f54  call    cs:__imp_ILCombine
0x180017f5a  mov     rcx, rax
0x180017f5d  mov     rdi, rax
0x180017f60  neg     rcx
0x180017f63  mov     rcx, [rsp+2B0h+pidl2]; pidl
0x180017f68  sbb     ebx, ebx
0x180017f6a  not     ebx
0x180017f6c  and     ebx, 8007000Eh
0x180017f72  call    cs:__imp_ILFree
0x180017f78  mov     rcx, [rsp+2B0h+ppv]
0x180017f7d  mov     rdx, [rcx]
0x180017f80  mov     rax, [rdx+10h]
0x180017f84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f89  jmp     short loc_180017FB2
0x180017f8b  mov     rcx, [rsp+2B0h+ppidl]; pidl
0x180017f90  test    rcx, rcx
0x180017f93  jz      short loc_180017FAD
0x180017f95  call    cs:__imp_ILClone
0x180017f9b  mov     rdi, rax
0x180017f9e  neg     rax
0x180017fa1  sbb     ebx, ebx
0x180017fa3  not     ebx
0x180017fa5  and     ebx, 8007000Eh
0x180017fab  jmp     short loc_180017FB2
0x180017fad  mov     ebx, 80070057h
0x180017fb2  mov     rcx, [rsp+2B0h+ppidl]; pidl
0x180017fb7  call    cs:__imp_ILFree
0x180017fbd  test    ebx, ebx
0x180017fbf  js      short loc_180017FE8
0x180017fc1  mov     rcx, [rsp+2B0h+ppvOut]
0x180017fc6  mov     r8d, r15d
0x180017fc9  shl     r8d, 1Eh
0x180017fcd  mov     rdx, rdi
0x180017fd0  inc     r8d
0x180017fd3  mov     rax, [rcx]
0x180017fd6  mov     rax, [rax+58h]
0x180017fda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017fdf  mov     rcx, rdi; pidl
0x180017fe2  call    cs:__imp_ILFree
0x180017fe8  mov     rcx, [rsp+2B0h+ppvOut]
0x180017fed  mov     rax, [rcx]
0x180017ff0  mov     rax, [rax+10h]
0x180017ff4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ff9  mov     rcx, [rbp+1B0h+var_40]
0x180018000  xor     rcx, rsp; StackCookie
0x180018003  call    __security_check_cookie
0x180018008  add     rsp, 280h
0x18001800f  pop     r15
0x180018011  pop     r14
0x180018013  pop     r12
0x180018015  pop     rdi
0x180018016  pop     rsi
0x180018017  pop     rbx
0x180018018  pop     rbp
0x180018019  retn
```
