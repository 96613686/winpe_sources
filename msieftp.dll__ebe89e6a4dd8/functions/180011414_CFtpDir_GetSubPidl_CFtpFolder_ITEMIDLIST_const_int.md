# CFtpDir::GetSubPidl(CFtpFolder *,_ITEMIDLIST const *,int)

- ea: `0x180011414`
- end: `0x1800114a6`
- name: `?GetSubPidl@CFtpDir@@QEAAPEFAU_ITEMIDLIST@@PEAVCFtpFolder@@PEFBU2@H@Z`
- size: `146`
- prototype: `struct _ITEMIDLIST *(CFtpDir *__hidden this, struct CFtpFolder *, const struct _ITEMIDLIST *, int)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800113ac`
- `0x18001237c`
- `0x180014834`
- `0x1800224f0`
- `0x180024378`
- `0x180024638`

## callees

- `0x180011414`

## import_xrefs

- `SHELL32!__imp_ILRemoveLastID` at `0x180011454`
- `SHELL32!__imp_ILRemoveLastID` at `0x180011454`
- `SHELL32!__imp_ILClone` at `0x180011439`
- `SHELL32!__imp_ILClone` at `0x180011439`
- `SHELL32!__imp_ILCombine` at `0x180011466`
- `SHELL32!__imp_ILCombine` at `0x18001147d`
- `SHELL32!__imp_ILCombine` at `0x180011466`
- `SHELL32!__imp_ILCombine` at `0x18001147d`
- `SHELL32!__imp_ILFree` at `0x180011489`
- `SHELL32!__imp_ILFree` at `0x180011492`
- `SHELL32!__imp_ILFree` at `0x180011489`
- `SHELL32!__imp_ILFree` at `0x180011492`

## pseudocode

```c
LPITEMIDLIST __fastcall CFtpDir::GetSubPidl(
        LPCITEMIDLIST *this,
        LPCITEMIDLIST *a2,
        const struct _ITEMIDLIST *a3,
        int a4)
{
  LPITEMIDLIST v7; // rbx
  ITEMIDLIST *v8; // rdi
  const ITEMIDLIST *v9; // rax
  ITEMIDLIST *v10; // rsi
  LPITEMIDLIST v11; // rdi

  if ( a4 && a2 )
  {
    v7 = ILClone(a2[6]);
    v8 = (LPITEMIDLIST)((char *)v7 + *((int *)a2 + 16));
    if ( v8 )
    {
      while ( v8->mkid.cb )
        ILRemoveLastID(v8);
    }
  }
  else
  {
    v7 = 0;
  }
  v9 = ILCombine(v7, this[6]);
  v10 = (ITEMIDLIST *)v9;
  v11 = 0;
  if ( v9 )
  {
    v11 = ILCombine(v9, a3);
    ILFree(v10);
  }
  ILFree(v7);
  return v11;
}

```

## disassembly

```asm
0x180011414  push    rbx
0x180011416  push    rbp
0x180011417  push    rsi
0x180011418  push    rdi
0x180011419  push    r14
0x18001141b  sub     rsp, 20h
0x18001141f  xor     r14d, r14d
0x180011422  mov     rbp, r8
0x180011425  mov     rdi, rdx
0x180011428  mov     rsi, rcx
0x18001142b  test    r9d, r9d
0x18001142e  jz      short loc_18001145C
0x180011430  test    rdx, rdx
0x180011433  jz      short loc_18001145C
0x180011435  mov     rcx, [rdx+30h]; pidl
0x180011439  call    cs:__imp_ILClone
0x18001143f  movsxd  rdi, dword ptr [rdi+40h]
0x180011443  mov     rbx, rax
0x180011446  add     rdi, rax
0x180011449  jz      short loc_18001145F
0x18001144b  cmp     [rdi], r14w
0x18001144f  jz      short loc_18001145F
0x180011451  mov     rcx, rdi; pidl
0x180011454  call    cs:__imp_ILRemoveLastID
0x18001145a  jmp     short loc_18001144B
0x18001145c  mov     rbx, r14
0x18001145f  mov     rdx, [rsi+30h]; pidl2
0x180011463  mov     rcx, rbx; pidl1
0x180011466  call    cs:__imp_ILCombine
0x18001146c  mov     rsi, rax
0x18001146f  mov     rdi, r14
0x180011472  test    rax, rax
0x180011475  jz      short loc_18001148F
0x180011477  mov     rdx, rbp; pidl2
0x18001147a  mov     rcx, rax; pidl1
0x18001147d  call    cs:__imp_ILCombine
0x180011483  mov     rcx, rsi; pidl
0x180011486  mov     rdi, rax
0x180011489  call    cs:__imp_ILFree
0x18001148f  mov     rcx, rbx; pidl
0x180011492  call    cs:__imp_ILFree
0x180011498  mov     rax, rdi
0x18001149b  add     rsp, 20h
0x18001149f  pop     r14
0x1800114a1  pop     rdi
0x1800114a2  pop     rsi
0x1800114a3  pop     rbp
0x1800114a4  pop     rbx
0x1800114a5  retn
```
