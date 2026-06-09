# CDropOperation::_CopyOneHdrop(ushort const *,ushort const *)

- ea: `0x1800142a0`
- end: `0x1800144bb`
- name: `?_CopyOneHdrop@CDropOperation@@IEAAJPEBG0@Z`
- size: `539`
- prototype: `int(CDropOperation *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001465c`

## callees

- `0x180002240`
- `0x180002b60`
- `0x18001168c`
- `0x1800121f0`
- `0x1800142a0`
- `0x18001bd14`
- `0x18001d840`
- `0x180028010`

## import_xrefs

- `SHELL32!SHFileOperationW` at `0x180014463`
- `SHELL32!SHFileOperationW` at `0x180014463`
- `SHELL32!__imp_ILFree` at `0x180014483`
- `SHELL32!__imp_ILFree` at `0x180014483`
- `SHLWAPI!PathFindFileNameW` at `0x1800142dd`
- `SHLWAPI!PathFindFileNameW` at `0x1800142dd`

## pseudocode

```c
__int64 __fastcall CDropOperation::_CopyOneHdrop(
        CDropOperation *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  LPWSTR FileNameW; // rax
  __int64 v6; // rcx
  const unsigned __int16 *v7; // r15
  int *v8; // r14
  int v9; // eax
  __int64 v10; // rcx
  int v11; // edi
  __int64 v12; // rdx
  ITEMIDLIST *v13; // rax
  __int64 v14; // rcx
  ITEMIDLIST *v15; // rcx
  int v17[4]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v18[4]; // [rsp+60h] [rbp-A0h] BYREF
  int v19; // [rsp+80h] [rbp-80h]
  int v20; // [rsp+84h] [rbp-7Ch]
  int v21; // [rsp+88h] [rbp-78h]
  LPITEMIDLIST pidl; // [rsp+90h] [rbp-70h]
  int v23; // [rsp+98h] [rbp-68h]
  __int64 v24; // [rsp+A0h] [rbp-60h]
  __int64 v25; // [rsp+A8h] [rbp-58h]
  __int64 v26; // [rsp+B0h] [rbp-50h]
  _SHFILEOPSTRUCTW FileOp; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v28[528]; // [rsp+110h] [rbp+10h] BYREF

  v17[0] = 1;
  FileNameW = PathFindFileNameW(a3);
  v6 = *((_QWORD *)this + 9);
  v7 = FileNameW;
  if ( v6 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 96LL))(v6, 2);
  v8 = (int *)((char *)this + 44);
  v9 = ConfirmCopy(
         a2,
         v7,
         (CDropOperation *)((char *)this + 44),
         *((HWND *)this + 4),
         *((struct CFtpFolder **)this + 2),
         *((struct CFtpDir **)this + 3),
         0,
         *((_DWORD *)this + 12),
         v17);
  v10 = *((_QWORD *)this + 9);
  v11 = v9;
  if ( v10 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v10 + 96LL))(v10, 3);
  if ( v11 )
  {
    if ( v11 == 1 )
      return 0;
  }
  else
  {
    memset_0(v18, 0, 0x68u);
    v12 = *((_QWORD *)this + 2);
    v18[3] = v28;
    v20 = *v8;
    v18[0] = v12;
    v18[1] = a2;
    v18[2] = v7;
    v19 = 6;
    v21 = 1;
    v13 = FtpCloneServerID((LPCITEMIDLIST)(*(_QWORD *)(v12 + 48) + *(int *)(v12 + 64)));
    v14 = *((_QWORD *)this + 3);
    pidl = v13;
    v23 = v17[0];
    v24 = *((_QWORD *)this + 9);
    v25 = *((_QWORD *)this + 7);
    v26 = *((_QWORD *)this + 8);
    UrlGetAbstractPathFromPidl(*(const struct _ITEMIDLIST **)(v14 + 40), 0, 0, v28, 0x104u);
    v11 = CFtpDir::WithHint(
            *((CFtpDir **)this + 3),
            0,
            *((HWND *)this + 4),
            (int (*)(void *, struct HINTPROCINFO *, void *, int *))CDropOperation::CopyCB,
            v18,
            0,
            *((struct CFtpFolder **)this + 2));
    if ( v11 >= 0 && *((_DWORD *)this + 10) == 2 )
    {
      *(_OWORD *)&FileOp.hwnd = 0;
      FileOp.wFunc = 3;
      memset(&FileOp.pTo, 0, 32);
      FileOp.pFrom = a2;
      FileOp.fFlags = 20;
      SHFileOperationW(&FileOp);
    }
    v15 = pidl;
    *((_QWORD *)this + 7) = v25;
    *((_QWORD *)this + 8) = v26;
    *v8 = v20;
    ILFree(v15);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800142a0  mov     [rsp-8+arg_18], rbx
0x1800142a5  push    rbp
0x1800142a6  push    rsi
0x1800142a7  push    rdi
0x1800142a8  push    r14
0x1800142aa  push    r15
0x1800142ac  lea     rbp, [rsp-230h]
0x1800142b4  sub     rsp, 330h
0x1800142bb  mov     rax, cs:__security_cookie
0x1800142c2  xor     rax, rsp
0x1800142c5  mov     [rbp+250h+var_30], rax
0x1800142cc  mov     rbx, rcx
0x1800142cf  mov     [rsp+350h+var_300], 1
0x1800142d7  mov     rcx, r8; pszPath
0x1800142da  mov     rsi, rdx
0x1800142dd  call    cs:__imp_PathFindFileNameW
0x1800142e3  mov     rcx, [rbx+48h]
0x1800142e7  mov     r15, rax
0x1800142ea  test    rcx, rcx
0x1800142ed  jz      short loc_180014302
0x1800142ef  mov     rdx, [rcx]
0x1800142f2  xor     r8d, r8d
0x1800142f5  mov     rax, [rdx+60h]
0x1800142f9  lea     edx, [r8+2]
0x1800142fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014302  mov     r9, [rbx+20h]; HWND
0x180014306  lea     rax, [rsp+350h+var_300]
0x18001430b  mov     [rsp+350h+var_310], rax; int *
0x180014310  lea     r14, [rbx+2Ch]
0x180014314  mov     eax, [rbx+30h]
0x180014317  mov     r8, r14; enum OPS *
0x18001431a  mov     [rsp+350h+var_318], eax; int
0x18001431e  mov     rdx, r15; unsigned __int16 *
0x180014321  mov     rax, [rbx+18h]
0x180014325  mov     rcx, rsi; lpFileName
0x180014328  mov     [rsp+350h+var_320], 0; unsigned int *
0x180014331  mov     [rsp+350h+var_328], rax; struct CFtpDir *
0x180014336  mov     rax, [rbx+10h]
0x18001433a  mov     [rsp+350h+var_330], rax; struct CFtpFolder *
0x18001433f  call    ?ConfirmCopy@@YAJPEBG0PEAW4OPS@@PEAUHWND__@@PEAVCFtpFolder@@PEAVCFtpDir@@PEAKHPEAH@Z; ConfirmCopy(ushort const *,ushort const *,OPS *,HWND__ *,CFtpFolder *,CFtpDir *,ulong *,int,int *)
0x180014344  mov     rcx, [rbx+48h]
0x180014348  mov     edi, eax
0x18001434a  test    rcx, rcx
0x18001434d  jz      short loc_180014362
0x18001434f  mov     rax, [rcx]
0x180014352  xor     r8d, r8d
0x180014355  mov     rax, [rax+60h]
0x180014359  lea     edx, [r8+3]
0x18001435d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014362  test    edi, edi
0x180014364  jnz     loc_18001448B
0x18001436a  xor     edx, edx; Val
0x18001436c  lea     r8d, [rdi+68h]; Size
0x180014370  lea     rcx, [rsp+350h+var_2F0]; void *
0x180014375  call    memset_0
0x18001437a  mov     rdx, [rbx+10h]
0x18001437e  lea     rax, [rbp+250h+var_240]
0x180014382  mov     [rsp+350h+var_2D8], rax
0x180014387  mov     eax, [r14]
0x18001438a  mov     [rbp+250h+var_2CC], eax
0x18001438d  mov     [rsp+350h+var_2F0], rdx
0x180014392  mov     [rsp+350h+var_2E8], rsi
0x180014397  mov     [rsp+350h+var_2E0], r15
0x18001439c  mov     [rbp+250h+var_2D0], 6
0x1800143a3  mov     [rbp+250h+var_2C8], 1
0x1800143aa  movsxd  rcx, dword ptr [rdx+40h]
0x1800143ae  add     rcx, [rdx+30h]; pidl
0x1800143b2  call    ?FtpCloneServerID@@YAPEFAU_ITEMIDLIST@@PEFBU1@@Z; FtpCloneServerID(_ITEMIDLIST const *)
0x1800143b7  mov     rcx, [rbx+18h]
0x1800143bb  lea     r9, [rbp+250h+var_240]; void *
0x1800143bf  mov     [rbp+250h+pidl], rax
0x1800143c3  xor     r8d, r8d; int
0x1800143c6  mov     eax, [rsp+350h+var_300]
0x1800143ca  xor     edx, edx; int
0x1800143cc  mov     [rbp+250h+var_2B8], eax
0x1800143cf  mov     rax, [rbx+48h]
0x1800143d3  mov     [rbp+250h+var_2B0], rax
0x1800143d7  mov     rax, [rbx+38h]
0x1800143db  mov     [rbp+250h+var_2A8], rax
0x1800143df  mov     rax, [rbx+40h]
0x1800143e3  mov     [rbp+250h+var_2A0], rax
0x1800143e7  mov     rcx, [rcx+28h]; struct _ITEMIDLIST *
0x1800143eb  mov     dword ptr [rsp+350h+var_330], 104h; unsigned int
0x1800143f3  call    ?UrlGetAbstractPathFromPidl@@YAJPEFBU_ITEMIDLIST@@HHPEAXK@Z; UrlGetAbstractPathFromPidl(_ITEMIDLIST const *,int,int,void *,ulong)
0x1800143f8  mov     rax, [rbx+10h]
0x1800143fc  lea     r9, ?CopyCB@CDropOperation@@SAJPEAXPEAUHINTPROCINFO@@0PEAH@Z; int (*)(void *, struct HINTPROCINFO *, void *, int *)
0x180014403  mov     r8, [rbx+20h]; HWND
0x180014407  xor     edx, edx; struct CStatusBar *
0x180014409  mov     rcx, [rbx+18h]; this
0x18001440d  mov     [rsp+350h+var_320], rax; struct CFtpFolder *
0x180014412  lea     rax, [rsp+350h+var_2F0]
0x180014417  mov     [rsp+350h+var_328], 0; struct IUnknown *
0x180014420  mov     [rsp+350h+var_330], rax; void *
0x180014425  call    ?WithHint@CFtpDir@@QEAAJPEAVCStatusBar@@PEAUHWND__@@P6AJPEAXPEAUHINTPROCINFO@@2PEAH@ZPEBXPEAUIUnknown@@PEAVCFtpFolder@@@Z; CFtpDir::WithHint(CStatusBar *,HWND__ *,long (*)(void *,HINTPROCINFO *,void *,int *),void const *,IUnknown *,CFtpFolder *)
0x18001442a  mov     edi, eax
0x18001442c  test    eax, eax
0x18001442e  js      short loc_180014469
0x180014430  cmp     dword ptr [rbx+28h], 2
0x180014434  jnz     short loc_180014469
0x180014436  xorps   xmm0, xmm0
0x180014439  lea     rcx, [rbp+250h+FileOp]; lpFileOp
0x18001443d  xor     eax, eax
0x18001443f  mov     [rbp+250h+FileOp.lpszProgressTitle], rax
0x180014443  mov     eax, 14h
0x180014448  movups  xmmword ptr [rbp+250h+FileOp.hwnd], xmm0
0x18001444c  mov     [rbp+250h+FileOp.wFunc], 3
0x180014453  movups  xmmword ptr [rbp+250h+FileOp.pFrom], xmm0
0x180014457  mov     [rbp+250h+FileOp.pFrom], rsi
0x18001445b  movups  xmmword ptr [rbp+250h+FileOp.fFlags], xmm0
0x18001445f  mov     [rbp+250h+FileOp.fFlags], ax
0x180014463  call    cs:__imp_SHFileOperationW
0x180014469  mov     rax, [rbp+250h+var_2A8]
0x18001446d  mov     rcx, [rbp+250h+pidl]; pidl
0x180014471  mov     [rbx+38h], rax
0x180014475  mov     rax, [rbp+250h+var_2A0]
0x180014479  mov     [rbx+40h], rax
0x18001447d  mov     eax, [rbp+250h+var_2CC]
0x180014480  mov     [r14], eax
0x180014483  call    cs:__imp_ILFree
0x180014489  jmp     short loc_180014493
0x18001448b  xor     eax, eax
0x18001448d  cmp     edi, 1
0x180014490  cmovz   edi, eax
0x180014493  mov     eax, edi
0x180014495  mov     rcx, [rbp+250h+var_30]
0x18001449c  xor     rcx, rsp; StackCookie
0x18001449f  call    __security_check_cookie
0x1800144a4  mov     rbx, [rsp+350h+arg_18]
0x1800144ac  add     rsp, 330h
0x1800144b3  pop     r15
0x1800144b5  pop     r14
0x1800144b7  pop     rdi
0x1800144b8  pop     rsi
0x1800144b9  pop     rbp
0x1800144ba  retn
```
