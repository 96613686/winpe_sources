# CFtpFolder::_BindToObject(_ITEMIDLIST const *,_ITEMIDLIST const *,IBindCtx *,_GUID const &,void * *)

- ea: `0x180017b8c`
- end: `0x180017e37`
- name: `?_BindToObject@CFtpFolder@@QEAAJPEFBU_ITEMIDLIST@@0PEAUIBindCtx@@AEBU_GUID@@PEAPEAX@Z`
- size: `683`
- prototype: `int(CFtpFolder *__hidden this, const struct _ITEMIDLIST *, const struct _ITEMIDLIST *, struct IBindCtx *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180015f80`

## callees

- `0x180002240`
- `0x1800160e4`
- `0x180016b4c`
- `0x180017b8c`
- `0x180018ee4`
- `0x180020efc`
- `0x180028010`

## import_xrefs

- `SHELL32!__imp_ILCombine` at `0x180017c1e`
- `SHELL32!__imp_ILCombine` at `0x180017c33`
- `SHELL32!__imp_ILCombine` at `0x180017c1e`
- `SHELL32!__imp_ILCombine` at `0x180017c33`
- `SHELL32!__imp_ILFree` at `0x180017cb1`
- `SHELL32!__imp_ILFree` at `0x180017cba`
- `SHELL32!__imp_ILFree` at `0x180017cb1`
- `SHELL32!__imp_ILFree` at `0x180017cba`

## pseudocode

```c
__int64 __fastcall CFtpFolder::_BindToObject(
        CFtpFolder *this,
        const struct _ITEMIDLIST *a2,
        const struct _ITEMIDLIST *a3,
        struct IBindCtx *a4,
        const struct _GUID *a5,
        void **a6)
{
  LPITEMIDLIST v10; // rax
  const ITEMIDLIST *v11; // rcx
  ITEMIDLIST *v12; // r12
  LPITEMIDLIST v13; // r14
  int v14; // edi
  __int64 (__fastcall ***v15)(void *, GUID *, _BYTE *); // rcx
  struct CFtpDir *FtpDir; // rsi
  char v17; // bl
  struct IBindCtxVtbl *lpVtbl; // rdx
  struct CFtpDir *v19; // rcx
  __int64 v20; // rax
  LPCITEMIDLIST v21; // rax
  int v22; // eax
  _BYTE v24[12]; // [rsp+40h] [rbp-20h] BYREF
  int v25; // [rsp+4Ch] [rbp-14h]

  *a6 = 0;
  if ( *(_OWORD *)a5 == *(_OWORD *)&IID_IShellFolder
    || *(_QWORD *)&a5->Data1 == *(_QWORD *)&IID_IShellFolder2.Data1
    && *(_QWORD *)a5->Data4 == *(_QWORD *)IID_IShellFolder2.Data4
    || *(_QWORD *)&a5->Data1 == *(_QWORD *)&IID_IBrowserFrameOptions.Data1
    && *(_QWORD *)a5->Data4 == *(_QWORD *)IID_IBrowserFrameOptions.Data4 )
  {
    v10 = ILCombine(*((LPCITEMIDLIST *)this + 6), a2);
    v11 = (const ITEMIDLIST *)*((_QWORD *)this + 7);
    v12 = v10;
    if ( v11 )
      v13 = ILCombine(v11, a2);
    else
      v13 = 0;
    v14 = CFtpFolder_Create(v12, v13, *((_DWORD *)this + 16), a5, a6);
    if ( v14 >= 0 )
    {
      v15 = (__int64 (__fastcall ***)(void *, GUID *, _BYTE *))*a6;
      *(_QWORD *)v24 = 0;
      v14 = (**v15)(v15, &IID_IDelegateFolder, v24);
      if ( v14 >= 0 )
      {
        v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)v24 + 24LL))(
                *(_QWORD *)v24,
                *((_QWORD *)this + 16));
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v24 + 16LL))(*(_QWORD *)v24);
      }
    }
    ILFree(v12);
    ILFree(v13);
    return (unsigned int)v14;
  }
  if ( *(_QWORD *)&a5->Data1 == *(_QWORD *)&IID_IMoniker.Data1 && *(_QWORD *)a5->Data4 == *(_QWORD *)IID_IMoniker.Data4 )
    return (unsigned int)CFtpFolder::_PidlToMoniker(this, a3, (struct IMoniker **)a6);
  if ( *(_QWORD *)&a5->Data1 == *(_QWORD *)&IID_IStream.Data1 && *(_QWORD *)a5->Data4 == *(_QWORD *)IID_IStream.Data4 )
  {
    v14 = -2147024882;
    FtpDir = CFtpFolder::GetFtpDir(this);
    if ( !FtpDir )
      return (unsigned int)v14;
    v17 = 0;
    if ( a4 )
    {
      lpVtbl = a4->lpVtbl;
      *(_QWORD *)&v24[4] = 0;
      v25 = 0;
      *(_DWORD *)v24 = 16;
      if ( ((int (__fastcall *)(struct IBindCtx *, _BYTE *))lpVtbl->GetBindOptions)(a4, v24) >= 0 )
        v17 = v24[8];
    }
    *(_QWORD *)v24 = 0;
    v14 = CFtpStm_Create(FtpDir, a3, ((unsigned int)((v17 & 1) == 0) + 1) << 30, (struct IStream **)a6, 0, 0, 0, 0);
    v19 = FtpDir;
    v20 = *(_QWORD *)FtpDir;
LABEL_27:
    (*(void (__fastcall **)(struct CFtpDir *))(v20 + 16))(v19);
    return (unsigned int)v14;
  }
  if ( *(_QWORD *)&a5->Data1 != *(_QWORD *)&IID_CFtpFolder.Data1
    || *(_QWORD *)a5->Data4 != *(_QWORD *)IID_CFtpFolder.Data4 )
  {
    return (unsigned int)-2147467262;
  }
  v21 = *(LPCITEMIDLIST *)this;
  *(_QWORD *)v24 = 0;
  v14 = (*(__int64 (__fastcall **)(CFtpFolder *, const struct _ITEMIDLIST *, struct IBindCtx *, GUID *, _BYTE *))((char *)&v21[13].mkid.cb + 1))(
          this,
          a2,
          a4,
          &IID_IShellFolder,
          v24);
  if ( v14 >= 0 )
  {
    v22 = (***(__int64 (__fastcall ****)(_QWORD, const struct _GUID *, void **))v24)(*(_QWORD *)v24, a5, a6);
    v19 = *(struct CFtpDir **)v24;
    v14 = v22;
    v20 = **(_QWORD **)v24;
    goto LABEL_27;
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180017b8c  push    rbp
0x180017b8e  push    rbx
0x180017b8f  push    rsi
0x180017b90  push    rdi
0x180017b91  push    r12
0x180017b93  push    r14
0x180017b95  push    r15
0x180017b97  mov     rbp, rsp
0x180017b9a  sub     rsp, 60h
0x180017b9e  mov     rax, cs:__security_cookie
0x180017ba5  xor     rax, rsp
0x180017ba8  mov     [rbp+var_10], rax
0x180017bac  mov     r15, [rbp+arg_28]
0x180017bb0  mov     r14, r9
0x180017bb3  mov     rbx, [rbp+arg_20]
0x180017bb7  mov     r12, r8
0x180017bba  mov     rdi, rdx
0x180017bbd  mov     rsi, rcx
0x180017bc0  mov     qword ptr [r15], 0
0x180017bc7  mov     rax, [rbx]
0x180017bca  cmp     rax, qword ptr cs:IID_IShellFolder.Data1
0x180017bd1  jnz     short loc_180017BE0
0x180017bd3  mov     rax, [rbx+8]
0x180017bd7  cmp     rax, qword ptr cs:IID_IShellFolder.Data4
0x180017bde  jz      short loc_180017C1A
0x180017be0  mov     rax, [rbx]
0x180017be3  cmp     rax, qword ptr cs:IID_IShellFolder2.Data1
0x180017bea  jnz     short loc_180017BF9
0x180017bec  mov     rax, [rbx+8]
0x180017bf0  cmp     rax, qword ptr cs:IID_IShellFolder2.Data4
0x180017bf7  jz      short loc_180017C1A
0x180017bf9  mov     rax, [rbx]
0x180017bfc  cmp     rax, qword ptr cs:IID_IBrowserFrameOptions.Data1
0x180017c03  jnz     loc_180017CC5
0x180017c09  mov     rax, [rbx+8]
0x180017c0d  cmp     rax, qword ptr cs:IID_IBrowserFrameOptions.Data4
0x180017c14  jnz     loc_180017CC5
0x180017c1a  mov     rcx, [rcx+30h]; pidl1
0x180017c1e  call    cs:__imp_ILCombine
0x180017c24  mov     rcx, [rsi+38h]; pidl1
0x180017c28  mov     r12, rax
0x180017c2b  test    rcx, rcx
0x180017c2e  jz      short loc_180017C3E
0x180017c30  mov     rdx, rdi; pidl2
0x180017c33  call    cs:__imp_ILCombine
0x180017c39  mov     r14, rax
0x180017c3c  jmp     short loc_180017C41
0x180017c3e  xor     r14d, r14d
0x180017c41  mov     r8d, [rsi+40h]; int
0x180017c45  mov     r9, rbx; struct _GUID *
0x180017c48  mov     rdx, r14; struct _ITEMIDLIST *
0x180017c4b  mov     qword ptr [rsp+60h+var_40], r15; void **
0x180017c50  mov     rcx, r12; struct _ITEMIDLIST *
0x180017c53  call    ?CFtpFolder_Create@@YAJPEFBU_ITEMIDLIST@@0HAEBU_GUID@@PEAPEAX@Z; CFtpFolder_Create(_ITEMIDLIST const *,_ITEMIDLIST const *,int,_GUID const &,void * *)
0x180017c58  mov     edi, eax
0x180017c5a  test    eax, eax
0x180017c5c  js      short loc_180017CAE
0x180017c5e  mov     rcx, [r15]
0x180017c61  lea     r8, [rbp+var_20]
0x180017c65  mov     qword ptr [rbp+var_20], 0
0x180017c6d  lea     rdx, IID_IDelegateFolder
0x180017c74  mov     rax, [rcx]
0x180017c77  mov     rax, [rax]
0x180017c7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c7f  mov     edi, eax
0x180017c81  test    eax, eax
0x180017c83  js      short loc_180017CAE
0x180017c85  mov     rcx, qword ptr [rbp+var_20]
0x180017c89  mov     rdx, [rsi+80h]
0x180017c90  mov     rax, [rcx]
0x180017c93  mov     rax, [rax+18h]
0x180017c97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c9c  mov     rcx, qword ptr [rbp+var_20]
0x180017ca0  mov     edi, eax
0x180017ca2  mov     rax, [rcx]
0x180017ca5  mov     rax, [rax+10h]
0x180017ca9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017cae  mov     rcx, r12; pidl
0x180017cb1  call    cs:__imp_ILFree
0x180017cb7  mov     rcx, r14; pidl
0x180017cba  call    cs:__imp_ILFree
0x180017cc0  jmp     loc_180017E1A
0x180017cc5  mov     rax, [rbx]
0x180017cc8  cmp     rax, qword ptr cs:IID_IMoniker.Data1
0x180017ccf  jnz     short loc_180017CF0
0x180017cd1  mov     rax, [rbx+8]
0x180017cd5  cmp     rax, qword ptr cs:IID_IMoniker.Data4
0x180017cdc  jnz     short loc_180017CF0
0x180017cde  mov     r8, r15; struct IMoniker **
0x180017ce1  mov     rdx, r12; struct _ITEMIDLIST *
0x180017ce4  call    ?_PidlToMoniker@CFtpFolder@@QEAAJPEFBU_ITEMIDLIST@@PEAPEAUIMoniker@@@Z; CFtpFolder::_PidlToMoniker(_ITEMIDLIST const *,IMoniker * *)
0x180017ce9  mov     edi, eax
0x180017ceb  jmp     loc_180017E1A
0x180017cf0  mov     rax, [rbx]
0x180017cf3  cmp     rax, qword ptr cs:IID_IStream.Data1
0x180017cfa  jnz     loc_180017DA3
0x180017d00  mov     rax, [rbx+8]
0x180017d04  cmp     rax, qword ptr cs:IID_IStream.Data4
0x180017d0b  jnz     loc_180017DA3
0x180017d11  mov     edi, 8007000Eh
0x180017d16  call    ?GetFtpDir@CFtpFolder@@QEAAPEAVCFtpDir@@XZ; CFtpFolder::GetFtpDir(void)
0x180017d1b  mov     rsi, rax
0x180017d1e  test    rax, rax
0x180017d21  jz      loc_180017E1A
0x180017d27  xor     ebx, ebx
0x180017d29  test    r14, r14
0x180017d2c  jz      short loc_180017D57
0x180017d2e  mov     rdx, [r14]
0x180017d31  xor     eax, eax
0x180017d33  mov     qword ptr [rbp+var_20+4], rax
0x180017d37  mov     rcx, r14
0x180017d3a  mov     [rbp+var_14], eax
0x180017d3d  mov     dword ptr [rbp+var_20], 10h
0x180017d44  mov     rax, [rdx+38h]
0x180017d48  lea     rdx, [rbp+var_20]
0x180017d4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d51  test    eax, eax
0x180017d53  cmovns  ebx, [rbp+var_18]
0x180017d57  mov     [rsp+60h+var_28], 0; int
0x180017d5f  not     ebx
0x180017d61  and     ebx, 1
0x180017d64  mov     [rsp+60h+var_30], 0; struct IProgressDialog *
0x180017d6d  mov     qword ptr [rbp+var_20], 0
0x180017d75  mov     r9, r15; struct IStream **
0x180017d78  mov     rax, qword ptr [rbp+var_20]
0x180017d7c  mov     rdx, r12; struct _ITEMIDLIST *
0x180017d7f  mov     qword ptr [rsp+60h+var_38], rax; union _ULARGE_INTEGER
0x180017d84  mov     rcx, rsi; struct CFtpDir *
0x180017d87  lea     r8d, [rbx+1]
0x180017d8b  mov     qword ptr [rsp+60h+var_40], rax; union _ULARGE_INTEGER
0x180017d90  shl     r8d, 1Eh; unsigned int
0x180017d94  call    ?CFtpStm_Create@@YAJPEAVCFtpDir@@PEFBU_ITEMIDLIST@@KPEAPEAUIStream@@T_ULARGE_INTEGER@@3PEAUIProgressDialog@@H@Z; CFtpStm_Create(CFtpDir *,_ITEMIDLIST const *,ulong,IStream * *,_ULARGE_INTEGER,_ULARGE_INTEGER,IProgressDialog *,int)
0x180017d99  mov     edi, eax
0x180017d9b  mov     rcx, rsi
0x180017d9e  mov     rax, [rsi]
0x180017da1  jmp     short loc_180017E0A
0x180017da3  mov     rax, [rbx]
0x180017da6  cmp     rax, qword ptr cs:?IID_CFtpFolder@@3U_GUID@@B.Data1; _GUID const IID_CFtpFolder ...
0x180017dad  jnz     short loc_180017E15
0x180017daf  mov     rax, [rbx+8]
0x180017db3  cmp     rax, qword ptr cs:?IID_CFtpFolder@@3U_GUID@@B.Data4; _GUID const IID_CFtpFolder ...
0x180017dba  jnz     short loc_180017E15
0x180017dbc  mov     rax, [rcx]
0x180017dbf  lea     r9, IID_IShellFolder
0x180017dc6  lea     rcx, [rbp+var_20]
0x180017dca  mov     qword ptr [rbp+var_20], 0
0x180017dd2  mov     qword ptr [rsp+60h+var_40], rcx
0x180017dd7  mov     r8, r14
0x180017dda  mov     rcx, rsi
0x180017ddd  mov     rax, [rax+28h]
0x180017de1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017de6  mov     edi, eax
0x180017de8  test    eax, eax
0x180017dea  js      short loc_180017E1A
0x180017dec  mov     rcx, qword ptr [rbp+var_20]
0x180017df0  mov     r8, r15
0x180017df3  mov     rdx, rbx
0x180017df6  mov     rax, [rcx]
0x180017df9  mov     rax, [rax]
0x180017dfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e01  mov     rcx, qword ptr [rbp+var_20]
0x180017e05  mov     edi, eax
0x180017e07  mov     rax, [rcx]
0x180017e0a  mov     rax, [rax+10h]
0x180017e0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e13  jmp     short loc_180017E1A
0x180017e15  mov     edi, 80004002h
0x180017e1a  mov     eax, edi
0x180017e1c  mov     rcx, [rbp+var_10]
0x180017e20  xor     rcx, rsp; StackCookie
0x180017e23  call    __security_check_cookie
0x180017e28  add     rsp, 60h
0x180017e2c  pop     r15
0x180017e2e  pop     r14
0x180017e30  pop     r12
0x180017e32  pop     rdi
0x180017e33  pop     rsi
0x180017e34  pop     rbx
0x180017e35  pop     rbp
0x180017e36  retn
```
