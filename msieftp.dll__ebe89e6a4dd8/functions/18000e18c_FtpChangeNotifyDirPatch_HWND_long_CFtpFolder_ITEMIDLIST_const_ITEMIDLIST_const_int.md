# FtpChangeNotifyDirPatch(HWND__ *,long,CFtpFolder *,_ITEMIDLIST const *,_ITEMIDLIST const *,int)

- ea: `0x18000e18c`
- end: `0x18000e217`
- name: `?FtpChangeNotifyDirPatch@@YAJPEAUHWND__@@JPEAVCFtpFolder@@PEFBU_ITEMIDLIST@@2H@Z`
- size: `139`
- prototype: `int(HWND, int, struct CFtpFolder *, const struct _ITEMIDLIST *, const struct _ITEMIDLIST *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18000d920`

## callees

- `0x18000e18c`
- `0x180016b9c`
- `0x180024378`
- `0x180028010`

## import_xrefs

- `SHELL32!__imp_ILFindLastID` at `0x18000e1d0`
- `SHELL32!__imp_ILFindLastID` at `0x18000e1d0`
- `SHELL32!__imp_ILRemoveLastID` at `0x18000e1b4`
- `SHELL32!__imp_ILRemoveLastID` at `0x18000e1b4`
- `SHELL32!__imp_ILClone` at `0x18000e1a3`
- `SHELL32!__imp_ILClone` at `0x18000e1a3`
- `SHELL32!__imp_ILFree` at `0x18000e204`
- `SHELL32!__imp_ILFree` at `0x18000e204`

## pseudocode

```c
__int64 __fastcall FtpChangeNotifyDirPatch(HWND a1, int a2, struct CFtpFolder *a3, const struct _ITEMIDLIST *a4)
{
  ITEMIDLIST *v7; // rax
  ITEMIDLIST *v8; // rbx
  struct CFtpDir *FtpDirFromPidl; // rdi
  const struct _ITEMIDLIST *ID; // rax
  HWND v11; // rcx
  int v13; // [rsp+30h] [rbp-38h]

  v7 = ILClone(a4);
  v8 = v7;
  if ( v7 )
  {
    ILRemoveLastID(v7);
    FtpDirFromPidl = CFtpFolder::GetFtpDirFromPidl(a3, v8);
    if ( FtpDirFromPidl )
    {
      ID = ILFindLastID(a4);
      FtpChangeNotify(v11, a2, a3, FtpDirFromPidl, ID, 0, v13);
      (*(void (__fastcall **)(struct CFtpDir *))(*(_QWORD *)FtpDirFromPidl + 16LL))(FtpDirFromPidl);
    }
    ILFree(v8);
  }
  return 0;
}

```

## disassembly

```asm
0x18000e18c  push    rbx
0x18000e18e  push    rbp
0x18000e18f  push    rsi
0x18000e190  push    rdi
0x18000e191  push    r14
0x18000e193  sub     rsp, 40h
0x18000e197  mov     rcx, r9; pidl
0x18000e19a  mov     rbp, r9
0x18000e19d  mov     rsi, r8
0x18000e1a0  mov     r14d, edx
0x18000e1a3  call    cs:__imp_ILClone
0x18000e1a9  mov     rbx, rax
0x18000e1ac  test    rax, rax
0x18000e1af  jz      short loc_18000E20A
0x18000e1b1  mov     rcx, rax; pidl
0x18000e1b4  call    cs:__imp_ILRemoveLastID
0x18000e1ba  mov     rdx, rbx; struct _ITEMIDLIST *
0x18000e1bd  mov     rcx, rsi; this
0x18000e1c0  call    ?GetFtpDirFromPidl@CFtpFolder@@QEAAPEAVCFtpDir@@PEFBU_ITEMIDLIST@@@Z; CFtpFolder::GetFtpDirFromPidl(_ITEMIDLIST const *)
0x18000e1c5  mov     rdi, rax
0x18000e1c8  test    rax, rax
0x18000e1cb  jz      short loc_18000E201
0x18000e1cd  mov     rcx, rbp; pidl
0x18000e1d0  call    cs:__imp_ILFindLastID
0x18000e1d6  mov     r9, rdi; struct CFtpDir *
0x18000e1d9  mov     [rsp+68h+var_40], 0; struct _ITEMIDLIST *
0x18000e1e2  mov     r8, rsi; struct CFtpFolder *
0x18000e1e5  mov     [rsp+68h+var_48], rax; struct _ITEMIDLIST *
0x18000e1ea  mov     edx, r14d; int
0x18000e1ed  call    ?FtpChangeNotify@@YAXPEAUHWND__@@JPEAVCFtpFolder@@PEAVCFtpDir@@PEFBU_ITEMIDLIST@@3H@Z; FtpChangeNotify(HWND__ *,long,CFtpFolder *,CFtpDir *,_ITEMIDLIST const *,_ITEMIDLIST const *,int)
0x18000e1f2  mov     rcx, [rdi]
0x18000e1f5  mov     rax, [rcx+10h]
0x18000e1f9  mov     rcx, rdi
0x18000e1fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e201  mov     rcx, rbx; pidl
0x18000e204  call    cs:__imp_ILFree
0x18000e20a  xor     eax, eax
0x18000e20c  add     rsp, 40h
0x18000e210  pop     r14
0x18000e212  pop     rdi
0x18000e213  pop     rsi
0x18000e214  pop     rbp
0x18000e215  pop     rbx
0x18000e216  retn
```
