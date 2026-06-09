# CFtpFolder::_GetUIObjectOf(HWND__ *,uint,_ITEMIDLIST const * *,_GUID const &,uint *,void * *,int)

- ea: `0x180018980`
- end: `0x180018a54`
- name: `?_GetUIObjectOf@CFtpFolder@@UEAAJPEAUHWND__@@IPEAPEFBU_ITEMIDLIST@@AEBU_GUID@@PEAIPEAPEAXH@Z`
- size: `212`
- prototype: `__int64 __fastcall(CFtpFolder *__hidden this, HWND, unsigned int, const struct _ITEMIDLIST **, const struct _GUID *, unsigned int *, void **, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180016e20`
- `0x180018980`
- `0x180018a5c`
- `0x18001ddf4`
- `0x180028010`

## import_xrefs

- `SHELL32!__imp_ILClone` at `0x1800189bb`
- `SHELL32!__imp_ILClone` at `0x1800189bb`
- `SHELL32!__imp_ILCombine` at `0x1800189b3`
- `SHELL32!__imp_ILCombine` at `0x1800189b3`
- `SHELL32!__imp_ILFree` at `0x180018a3f`
- `SHELL32!__imp_ILFree` at `0x180018a3f`

## pseudocode

```c
__int64 __fastcall CFtpFolder::_GetUIObjectOf(
        CFtpFolder *this,
        HWND a2,
        int a3,
        const struct _ITEMIDLIST **a4,
        const struct _GUID *a5,
        unsigned int *a6,
        void **a7,
        int a8)
{
  const ITEMIDLIST *v12; // rcx
  LPITEMIDLIST v13; // rax
  void **v14; // rbx
  ITEMIDLIST *v15; // rsi
  int UIObjectOfHfpl; // ebp
  struct CFtpPidlList *v17; // rbx
  void **v19; // [rsp+20h] [rbp-48h]
  struct CFtpPidlList *v20; // [rsp+88h] [rbp+20h] BYREF

  v20 = 0;
  v12 = (const ITEMIDLIST *)(*((_QWORD *)this + 6) + *((int *)this + 16));
  if ( a4 )
    v13 = ILCombine(v12, *a4);
  else
    v13 = ILClone(v12);
  v14 = a7;
  v15 = v13;
  if ( a7 )
    *a7 = 0;
  UIObjectOfHfpl = CFtpPidlList_Create(a3, a4, &v20);
  if ( UIObjectOfHfpl >= 0 )
  {
    CFtpFolder::_InitFtpSite(this);
    v19 = v14;
    v17 = v20;
    UIObjectOfHfpl = CFtpFolder::GetUIObjectOfHfpl(this, a2, v20, a5, v19, a8);
    (*(void (__fastcall **)(struct CFtpPidlList *))(*(_QWORD *)v17 + 16LL))(v17);
  }
  if ( v15 )
    ILFree(v15);
  return (unsigned int)UIObjectOfHfpl;
}

```

## disassembly

```asm
0x180018980  mov     rax, rsp
0x180018983  push    rbx
0x180018984  push    rbp
0x180018985  push    rsi
0x180018986  push    rdi
0x180018987  push    r14
0x180018989  push    r15
0x18001898b  sub     rsp, 38h
0x18001898f  mov     rdi, rcx
0x180018992  mov     qword ptr [rax+20h], 0
0x18001899a  movsxd  rcx, dword ptr [rcx+40h]
0x18001899e  mov     r14, r9
0x1800189a1  mov     ebp, r8d
0x1800189a4  mov     r15, rdx
0x1800189a7  add     rcx, [rdi+30h]; pidl
0x1800189ab  test    r9, r9
0x1800189ae  jz      short loc_1800189BB
0x1800189b0  mov     rdx, [r9]; pidl2
0x1800189b3  call    cs:__imp_ILCombine
0x1800189b9  jmp     short loc_1800189C1
0x1800189bb  call    cs:__imp_ILClone
0x1800189c1  mov     rbx, [rsp+68h+arg_30]
0x1800189c9  mov     rsi, rax
0x1800189cc  test    rbx, rbx
0x1800189cf  jz      short loc_1800189D8
0x1800189d1  mov     qword ptr [rbx], 0
0x1800189d8  lea     r8, [rsp+68h+arg_18]; struct CFtpPidlList **
0x1800189e0  mov     rdx, r14; struct _ITEMIDLIST **
0x1800189e3  mov     ecx, ebp; int
0x1800189e5  call    ?CFtpPidlList_Create@@YAJHQEAPEFBU_ITEMIDLIST@@PEAPEAVCFtpPidlList@@@Z; CFtpPidlList_Create(int,_ITEMIDLIST const * * const,CFtpPidlList * *)
0x1800189ea  mov     ebp, eax
0x1800189ec  test    eax, eax
0x1800189ee  js      short loc_180018A37
0x1800189f0  mov     rcx, rdi; this
0x1800189f3  call    ?_InitFtpSite@CFtpFolder@@QEAAJXZ; CFtpFolder::_InitFtpSite(void)
0x1800189f8  mov     eax, [rsp+68h+arg_38]
0x1800189ff  mov     rdx, r15; HWND
0x180018a02  mov     r9, [rsp+68h+arg_20]; struct _GUID *
0x180018a0a  mov     rcx, rdi; this
0x180018a0d  mov     [rsp+68h+var_40], eax; int
0x180018a11  mov     [rsp+68h+var_48], rbx; void **
0x180018a16  mov     rbx, [rsp+68h+arg_18]
0x180018a1e  mov     r8, rbx; struct CFtpPidlList *
0x180018a21  call    ?GetUIObjectOfHfpl@CFtpFolder@@QEAAJPEAUHWND__@@PEAVCFtpPidlList@@AEBU_GUID@@PEAPEAXH@Z; CFtpFolder::GetUIObjectOfHfpl(HWND__ *,CFtpPidlList *,_GUID const &,void * *,int)
0x180018a26  mov     ebp, eax
0x180018a28  mov     rcx, rbx
0x180018a2b  mov     rax, [rbx]
0x180018a2e  mov     rax, [rax+10h]
0x180018a32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a37  test    rsi, rsi
0x180018a3a  jz      short loc_180018A45
0x180018a3c  mov     rcx, rsi; pidl
0x180018a3f  call    cs:__imp_ILFree
0x180018a45  mov     eax, ebp
0x180018a47  add     rsp, 38h
0x180018a4b  pop     r15
0x180018a4d  pop     r14
0x180018a4f  pop     rdi
0x180018a50  pop     rsi
0x180018a51  pop     rbp
0x180018a52  pop     rbx
0x180018a53  retn
```
