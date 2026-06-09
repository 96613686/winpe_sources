# SHGetNameAndFlagsW(_ITEMIDLIST_ABSOLUTE const *,ulong,ushort *,uint,ulong *)

- ea: `0x180007f00`
- end: `0x18000802d`
- name: `?SHGetNameAndFlagsW@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@KPEAGIPEAK@Z`
- size: `301`
- prototype: `__int64 __usercall@<rax>(LPCITEMIDLIST pidl@<rcx>, unsigned int@<edx>, unsigned __int16 *@<r8>, unsigned int@<r9d>, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180032ed4`

## callees

- `0x180007398`
- `0x180007f00`
- `0x180008034`
- `0x180011de8`
- `0x18004d010`

## import_xrefs

- `SHELL32!SHBindToParent` at `0x180007f5a`
- `SHELL32!SHBindToParent` at `0x180007f5a`
- `SHLWAPI!__imp_SHGetObjectCompatFlags` at `0x180007fe3`
- `SHLWAPI!__imp_SHGetObjectCompatFlags` at `0x180007fe3`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000800e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000800e`

## pseudocode

```c
__int64 __fastcall SHGetNameAndFlagsW(
        LPCITEMIDLIST pidl,
        unsigned int a2,
        unsigned __int16 *a3,
        int a4,
        unsigned int *a5)
{
  int v9; // r12d
  HRESULT v10; // esi
  struct IBindCtx *v11; // r8
  unsigned int *v12; // rdi
  void *v13; // r15
  unsigned int v14; // r14d
  unsigned int v15; // r9d
  int AttributesFromFolderAndIDList; // eax
  unsigned int v17; // ebx
  void *ppv; // [rsp+30h] [rbp-10h] BYREF
  LPCITEMIDLIST ppidlLast; // [rsp+38h] [rbp-8h] BYREF
  unsigned int v21; // [rsp+80h] [rbp+40h] BYREF

  if ( a3 )
    *a3 = 0;
  ppv = 0;
  ppidlLast = 0;
  v9 = SHCoInitialize();
  v10 = SHBindToParent(pidl, &GUID_000214e6_0000_0000_c000_000000000046, &ppv, &ppidlLast);
  if ( v10 >= 0 )
  {
    if ( !a3 || (v10 = DisplayNameOfW(ppv, ppidlLast, a2, a3, a4), v10 >= 0) )
    {
      v12 = a5;
      if ( a5 )
      {
        v13 = ppv;
        v14 = *a5;
        v15 = *a5;
        v21 = 0;
        AttributesFromFolderAndIDList = _GetAttributesFromFolderAndIDList(
                                          (struct IShellFolder *)ppv,
                                          (const struct _ITEMIDLIST_RELATIVE *)ppidlLast,
                                          v11,
                                          v15,
                                          &v21);
        v17 = v21;
        if ( AttributesFromFolderAndIDList >= 0
          && (v21 & 0x20C00000) == 541065216
          && (v14 & 0x800000) != 0
          && (SHGetObjectCompatFlags(v13, 0) & 0x200) != 0 )
        {
          v17 = v17 & 0xFF3FFFFF | 0x800000;
        }
        *v12 = v17;
      }
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  if ( !v9 )
    CoUninitialize();
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180007f00  mov     [rsp-28h+arg_0], rbx
0x180007f05  mov     [rsp-28h+arg_8], rsi
0x180007f0a  push    rbp
0x180007f0b  push    rdi
0x180007f0c  push    r12
0x180007f0e  push    r14
0x180007f10  push    r15
0x180007f12  mov     rbp, rsp
0x180007f15  sub     rsp, 40h
0x180007f19  mov     r14d, r9d
0x180007f1c  mov     rbx, r8
0x180007f1f  mov     r15d, edx
0x180007f22  mov     rdi, rcx
0x180007f25  test    r8, r8
0x180007f28  jz      short loc_180007F30
0x180007f2a  xor     eax, eax
0x180007f2c  mov     [r8], ax
0x180007f30  call    ?SHCoInitialize@@YAJXZ; SHCoInitialize(void)
0x180007f35  lea     r9, [rbp+ppidlLast]; ppidlLast
0x180007f39  mov     [rbp+ppv], 0
0x180007f41  lea     r8, [rbp+ppv]; ppv
0x180007f45  mov     [rbp+ppidlLast], 0
0x180007f4d  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x180007f54  mov     rcx, rdi; pidl
0x180007f57  mov     r12d, eax
0x180007f5a  call    cs:__imp_SHBindToParent
0x180007f60  mov     esi, eax
0x180007f62  test    eax, eax
0x180007f64  js      loc_180008009
0x180007f6a  test    rbx, rbx
0x180007f6d  jz      short loc_180007F8D
0x180007f6f  mov     rdx, [rbp+ppidlLast]
0x180007f73  mov     r9, rbx
0x180007f76  mov     rcx, [rbp+ppv]
0x180007f7a  mov     r8d, r15d
0x180007f7d  mov     dword ptr [rsp+40h+var_20], r14d
0x180007f82  call    DisplayNameOfW
0x180007f87  mov     esi, eax
0x180007f89  test    eax, eax
0x180007f8b  js      short loc_180007FF9
0x180007f8d  mov     rdi, [rbp+arg_20]
0x180007f91  test    rdi, rdi
0x180007f94  jz      short loc_180007FF9
0x180007f96  mov     r15, [rbp+ppv]
0x180007f9a  lea     rax, [rbp+arg_10]
0x180007f9e  mov     r14d, [rdi]
0x180007fa1  mov     rcx, r15; struct IShellFolder *
0x180007fa4  mov     rdx, [rbp+ppidlLast]; struct _ITEMIDLIST_RELATIVE *
0x180007fa8  mov     r9d, r14d; unsigned int
0x180007fab  mov     [rbp+arg_10], 0
0x180007fb2  mov     [rsp+40h+var_20], rax; unsigned int *
0x180007fb7  call    ?_GetAttributesFromFolderAndIDList@@YAJPEAUIShellFolder@@PEFBU_ITEMIDLIST_RELATIVE@@PEAUIBindCtx@@KPEAK@Z; _GetAttributesFromFolderAndIDList(IShellFolder *,_ITEMIDLIST_RELATIVE const *,IBindCtx *,ulong,ulong *)
0x180007fbc  mov     ebx, [rbp+arg_10]
0x180007fbf  test    eax, eax
0x180007fc1  js      short loc_180007FF7
0x180007fc3  mov     eax, ebx
0x180007fc5  and     eax, 20C00000h
0x180007fca  cmp     eax, 20400000h
0x180007fcf  setz    dl
0x180007fd2  bt      r14d, 17h
0x180007fd7  setb    al
0x180007fda  test    al, dl
0x180007fdc  jz      short loc_180007FF7
0x180007fde  xor     edx, edx
0x180007fe0  mov     rcx, r15
0x180007fe3  call    cs:__imp_SHGetObjectCompatFlags
0x180007fe9  bt      eax, 9
0x180007fed  jnb     short loc_180007FF7
0x180007fef  btr     ebx, 16h
0x180007ff3  bts     ebx, 17h
0x180007ff7  mov     [rdi], ebx
0x180007ff9  mov     rcx, [rbp+ppv]
0x180007ffd  mov     rax, [rcx]
0x180008000  mov     rax, [rax+10h]
0x180008004  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008009  test    r12d, r12d
0x18000800c  jnz     short loc_180008014
0x18000800e  call    cs:__imp_CoUninitialize
0x180008014  mov     rbx, [rsp+40h+arg_0]
0x180008019  mov     eax, esi
0x18000801b  mov     rsi, [rsp+40h+arg_8]
0x180008020  add     rsp, 40h
0x180008024  pop     r15
0x180008026  pop     r14
0x180008028  pop     r12
0x18000802a  pop     rdi
0x18000802b  pop     rbp
0x18000802c  retn
```
