# CFtpFolder::BindToObject(_ITEMIDLIST const *,IBindCtx *,_GUID const &,void * *)

- ea: `0x180015f80`
- end: `0x180016022`
- name: `?BindToObject@CFtpFolder@@UEAAJPEFBU_ITEMIDLIST@@PEAUIBindCtx@@AEBU_GUID@@PEAPEAX@Z`
- size: `162`
- prototype: `int(CFtpFolder *__hidden this, const struct _ITEMIDLIST *, struct IBindCtx *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180015f80`
- `0x180017b8c`
- `0x180018d28`

## import_xrefs

- `SHELL32!__imp_ILCombine` at `0x180015fd4`
- `SHELL32!__imp_ILCombine` at `0x180015fd4`
- `SHELL32!__imp_ILFree` at `0x180016002`
- `SHELL32!__imp_ILFree` at `0x180016002`

## pseudocode

```c
__int64 __fastcall CFtpFolder::BindToObject(
        CFtpFolder *this,
        const struct _ITEMIDLIST *a2,
        struct IBindCtx *a3,
        const struct _GUID *a4,
        void **a5)
{
  unsigned int v9; // edi
  const struct _ITEMIDLIST *v10; // rax
  ITEMIDLIST *v11; // rbp

  if ( a5 )
    *a5 = 0;
  if ( a2 && a2->mkid.cb && CFtpFolder::_IsValidPidlParameter(this, a2) )
  {
    v9 = -2147023673;
    v10 = ILCombine((LPCITEMIDLIST)(*((_QWORD *)this + 6) + *((int *)this + 16)), a2);
    v11 = (ITEMIDLIST *)v10;
    if ( v10 )
    {
      v9 = CFtpFolder::_BindToObject(this, a2, v10, a3, a4, a5);
      ILFree(v11);
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v9;
}

```

## disassembly

```asm
0x180015f80  push    rbx
0x180015f82  push    rbp
0x180015f83  push    rsi
0x180015f84  push    rdi
0x180015f85  push    r12
0x180015f87  push    r13
0x180015f89  push    r14
0x180015f8b  push    r15
0x180015f8d  sub     rsp, 38h
0x180015f91  mov     r14, [rsp+78h+arg_20]
0x180015f99  xor     r13d, r13d
0x180015f9c  mov     r15, r9
0x180015f9f  mov     r12, r8
0x180015fa2  mov     rbx, rdx
0x180015fa5  mov     rsi, rcx
0x180015fa8  test    r14, r14
0x180015fab  jz      short loc_180015FB0
0x180015fad  mov     [r14], r13
0x180015fb0  test    rbx, rbx
0x180015fb3  jz      short loc_18001600A
0x180015fb5  cmp     [rdx], r13w
0x180015fb9  jz      short loc_18001600A
0x180015fbb  call    ?_IsValidPidlParameter@CFtpFolder@@QEAAHPEFBU_ITEMIDLIST@@@Z; CFtpFolder::_IsValidPidlParameter(_ITEMIDLIST const *)
0x180015fc0  test    eax, eax
0x180015fc2  jz      short loc_18001600A
0x180015fc4  movsxd  rcx, dword ptr [rsi+40h]
0x180015fc8  mov     rdx, rbx; pidl2
0x180015fcb  add     rcx, [rsi+30h]; pidl1
0x180015fcf  mov     edi, 800704C7h
0x180015fd4  call    cs:__imp_ILCombine
0x180015fda  mov     rbp, rax
0x180015fdd  test    rax, rax
0x180015fe0  jz      short loc_18001600F
0x180015fe2  mov     [rsp+78h+var_50], r14; void **
0x180015fe7  mov     r9, r12; struct IBindCtx *
0x180015fea  mov     r8, rax; struct _ITEMIDLIST *
0x180015fed  mov     [rsp+78h+var_58], r15; struct _GUID *
0x180015ff2  mov     rdx, rbx; struct _ITEMIDLIST *
0x180015ff5  mov     rcx, rsi; this
0x180015ff8  call    ?_BindToObject@CFtpFolder@@QEAAJPEFBU_ITEMIDLIST@@0PEAUIBindCtx@@AEBU_GUID@@PEAPEAX@Z; CFtpFolder::_BindToObject(_ITEMIDLIST const *,_ITEMIDLIST const *,IBindCtx *,_GUID const &,void * *)
0x180015ffd  mov     rcx, rbp; pidl
0x180016000  mov     edi, eax
0x180016002  call    cs:__imp_ILFree
0x180016008  jmp     short loc_18001600F
0x18001600a  mov     edi, 80070057h
0x18001600f  mov     eax, edi
0x180016011  add     rsp, 38h
0x180016015  pop     r15
0x180016017  pop     r14
0x180016019  pop     r13
0x18001601b  pop     r12
0x18001601d  pop     rdi
0x18001601e  pop     rsi
0x18001601f  pop     rbp
0x180016020  pop     rbx
0x180016021  retn
```
