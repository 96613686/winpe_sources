# CNavigateButton::Navigate(ushort const *,ushort const *,IUnknown *,bool)

- ea: `0x1800304e0`
- end: `0x1800306fa`
- name: `?Navigate@CNavigateButton@@SAXPEBG0PEAUIUnknown@@_N@Z`
- size: `538`
- prototype: `void __fastcall(const unsigned __int16 *, const unsigned __int16 *, struct IUnknown *, bool)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180030c24`

## callees

- `0x1800303d0`
- `0x1800304e0`
- `0x180030a28`
- `0x180030ea0`
- `0x180032010`

## import_xrefs

- `SHCORE!IUnknown_QueryService` at `0x180030536`
- `SHCORE!IUnknown_QueryService` at `0x180030536`
- `SHELL32!SHParseDisplayName` at `0x1800305a6`
- `SHELL32!SHParseDisplayName` at `0x1800305a6`
- `SHELL32!SHBindToObject` at `0x1800305e2`
- `SHELL32!SHBindToObject` at `0x1800305e2`
- `SHELL32!__imp_ILClone` at `0x180030675`
- `SHELL32!__imp_ILClone` at `0x180030675`
- `SHELL32!__imp_ILCombine` at `0x180030634`
- `SHELL32!__imp_ILCombine` at `0x180030634`
- `SHELL32!__imp_ILFree` at `0x180030652`
- `SHELL32!__imp_ILFree` at `0x180030697`
- `SHELL32!__imp_ILFree` at `0x1800306c2`
- `SHELL32!__imp_ILFree` at `0x180030652`
- `SHELL32!__imp_ILFree` at `0x180030697`
- `SHELL32!__imp_ILFree` at `0x1800306c2`

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
0x1800304e0  push    rbp
0x1800304e2  push    rbx
0x1800304e3  push    rsi
0x1800304e4  push    rdi
0x1800304e5  push    r12
0x1800304e7  push    r14
0x1800304e9  push    r15
0x1800304eb  lea     rbp, [rsp-180h]
0x1800304f3  sub     rsp, 280h
0x1800304fa  mov     rax, cs:__security_cookie
0x180030501  xor     rax, rsp
0x180030504  mov     [rbp+1B0h+var_40], rax
0x18003050b  mov     rax, r8
0x18003050e  movzx   r15d, r9b
0x180030512  mov     r14, rdx
0x180030515  lea     r9, [rsp+2B0h+ppvOut]; ppvOut
0x18003051a  mov     rbx, rcx
0x18003051d  lea     r8, _GUID_000214e2_0000_0000_c000_000000000046; riid
0x180030524  xor     r12d, r12d
0x180030527  lea     rdx, SID_STopLevelBrowser; guidService
0x18003052e  mov     rcx, rax; punk
0x180030531  mov     [rsp+2B0h+ppvOut], r12
0x180030536  call    cs:__imp_IUnknown_QueryService
0x18003053c  test    eax, eax
0x18003053e  js      loc_1800306D9
0x180030544  mov     [rsp+2B0h+ppidl], r12
0x180030549  test    rbx, rbx
0x18003054c  jz      short loc_180030556
0x18003054e  mov     al, 1
0x180030550  cmp     [rbx], r12w
0x180030554  jnz     short loc_180030559
0x180030556  mov     al, r12b
0x180030559  test    r14, r14
0x18003055c  jz      short loc_180030567
0x18003055e  mov     sil, 1
0x180030561  cmp     [r14], r12w
0x180030565  jnz     short loc_18003056A
0x180030567  mov     sil, r12b
0x18003056a  test    al, al
0x18003056c  jnz     short loc_18003057F
0x18003056e  mov     rcx, [rsp+2B0h+ppvOut]; struct IShellBrowser *
0x180030573  lea     rdx, [rsp+2B0h+ppidl]; struct _ITEMIDLIST **
0x180030578  call    ?GetCplRoot@CNavigateButton@@CAJPEAUIShellBrowser@@PEAPEFAU_ITEMIDLIST@@@Z; CNavigateButton::GetCplRoot(IShellBrowser *,_ITEMIDLIST * *)
0x18003057d  jmp     short loc_1800305AC
0x18003057f  lea     rdx, [rsp+2B0h+pszName]; unsigned __int16 *
0x180030584  mov     rcx, rbx; unsigned __int16 *
0x180030587  call    ?TranslateCplCanonicalName@@YAJPEBGPEAGI@Z; TranslateCplCanonicalName(ushort const *,ushort *,uint)
0x18003058c  mov     ebx, eax
0x18003058e  test    eax, eax
0x180030590  js      short loc_1800305AE
0x180030592  xor     r9d, r9d; sfgaoIn
0x180030595  mov     [rsp+2B0h+psfgaoOut], r12; psfgaoOut
0x18003059a  lea     r8, [rsp+2B0h+ppidl]; ppidl
0x18003059f  xor     edx, edx; pbc
0x1800305a1  lea     rcx, [rsp+2B0h+pszName]; pszName
0x1800305a6  call    cs:__imp_SHParseDisplayName
0x1800305ac  mov     ebx, eax
0x1800305ae  mov     rdi, r12
0x1800305b1  test    ebx, ebx
0x1800305b3  js      loc_180030692
0x1800305b9  test    sil, sil
0x1800305bc  jz      loc_18003066B
0x1800305c2  mov     rdx, [rsp+2B0h+ppidl]; pidl
0x1800305c7  lea     rax, [rsp+2B0h+ppv]
0x1800305cc  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x1800305d3  mov     [rsp+2B0h+psfgaoOut], rax; ppv
0x1800305d8  xor     r8d, r8d; pbc
0x1800305db  mov     [rsp+2B0h+ppv], r12
0x1800305e0  xor     ecx, ecx; psf
0x1800305e2  call    cs:__imp_SHBindToObject
0x1800305e8  mov     ebx, eax
0x1800305ea  test    eax, eax
0x1800305ec  js      loc_180030692
0x1800305f2  mov     rcx, [rsp+2B0h+ppv]
0x1800305f7  lea     rdx, [rsp+2B0h+pidl2]
0x1800305fc  mov     [rsp+2B0h+pidl2], r12
0x180030601  mov     r9, r14
0x180030604  mov     [rsp+2B0h+var_280], r12
0x180030609  xor     r8d, r8d
0x18003060c  mov     [rsp+2B0h+var_288], rdx
0x180030611  xor     edx, edx
0x180030613  mov     rax, [rcx]
0x180030616  mov     [rsp+2B0h+psfgaoOut], r12
0x18003061b  mov     rax, [rax+18h]
0x18003061f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030624  mov     ebx, eax
0x180030626  test    eax, eax
0x180030628  js      short loc_180030658
0x18003062a  mov     rdx, [rsp+2B0h+pidl2]; pidl2
0x18003062f  mov     rcx, [rsp+2B0h+ppidl]; pidl1
0x180030634  call    cs:__imp_ILCombine
0x18003063a  mov     rcx, rax
0x18003063d  mov     rdi, rax
0x180030640  neg     rcx
0x180030643  mov     rcx, [rsp+2B0h+pidl2]; pidl
0x180030648  sbb     ebx, ebx
0x18003064a  not     ebx
0x18003064c  and     ebx, 8007000Eh
0x180030652  call    cs:__imp_ILFree
0x180030658  mov     rcx, [rsp+2B0h+ppv]
0x18003065d  mov     rdx, [rcx]
0x180030660  mov     rax, [rdx+10h]
0x180030664  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030669  jmp     short loc_180030692
0x18003066b  mov     rcx, [rsp+2B0h+ppidl]; pidl
0x180030670  test    rcx, rcx
0x180030673  jz      short loc_18003068D
0x180030675  call    cs:__imp_ILClone
0x18003067b  mov     rdi, rax
0x18003067e  neg     rax
0x180030681  sbb     ebx, ebx
0x180030683  not     ebx
0x180030685  and     ebx, 8007000Eh
0x18003068b  jmp     short loc_180030692
0x18003068d  mov     ebx, 80070057h
0x180030692  mov     rcx, [rsp+2B0h+ppidl]; pidl
0x180030697  call    cs:__imp_ILFree
0x18003069d  test    ebx, ebx
0x18003069f  js      short loc_1800306C8
0x1800306a1  mov     rcx, [rsp+2B0h+ppvOut]
0x1800306a6  mov     r8d, r15d
0x1800306a9  shl     r8d, 1Eh
0x1800306ad  mov     rdx, rdi
0x1800306b0  inc     r8d
0x1800306b3  mov     rax, [rcx]
0x1800306b6  mov     rax, [rax+58h]
0x1800306ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800306bf  mov     rcx, rdi; pidl
0x1800306c2  call    cs:__imp_ILFree
0x1800306c8  mov     rcx, [rsp+2B0h+ppvOut]
0x1800306cd  mov     rax, [rcx]
0x1800306d0  mov     rax, [rax+10h]
0x1800306d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800306d9  mov     rcx, [rbp+1B0h+var_40]
0x1800306e0  xor     rcx, rsp; StackCookie
0x1800306e3  call    __security_check_cookie
0x1800306e8  add     rsp, 280h
0x1800306ef  pop     r15
0x1800306f1  pop     r14
0x1800306f3  pop     r12
0x1800306f5  pop     rdi
0x1800306f6  pop     rsi
0x1800306f7  pop     rbx
0x1800306f8  pop     rbp
0x1800306f9  retn
```
