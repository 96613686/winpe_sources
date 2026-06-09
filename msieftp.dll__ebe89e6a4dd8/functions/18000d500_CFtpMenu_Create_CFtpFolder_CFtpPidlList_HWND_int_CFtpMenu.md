# CFtpMenu_Create(CFtpFolder *,CFtpPidlList *,HWND__ *,int,CFtpMenu * *)

- ea: `0x18000d500`
- end: `0x18000d6cb`
- name: `?CFtpMenu_Create@@YAJPEAVCFtpFolder@@PEAVCFtpPidlList@@PEAUHWND__@@HPEAPEAVCFtpMenu@@@Z`
- size: `459`
- prototype: `__int64 __usercall@<rax>(struct CFtpFolder *@<rcx>, struct CFtpPidlList *@<rdx>, HWND@<r8>, int@<r9d>, struct CFtpMenu **)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180016e20`

## callees

- `0x18000d500`
- `0x180016b9c`
- `0x18001bd78`
- `0x18001bda4`
- `0x18001e0a0`
- `0x180023adc`
- `0x180024ac8`
- `0x1800269f4`
- `0x180028010`

## import_xrefs

- `SHELL32!__imp_ILCombine` at `0x18000d609`
- `SHELL32!__imp_ILCombine` at `0x18000d609`
- `SHELL32!__imp_ILFree` at `0x18000d627`
- `SHELL32!__imp_ILFree` at `0x18000d627`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d67e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d67e`

## pseudocode

```c
__int64 __fastcall CFtpMenu_Create(
        struct CFtpFolder *a1,
        struct CFtpPidlList *a2,
        HWND a3,
        int a4,
        struct CFtpMenu **a5)
{
  const struct _ITEMIDLIST *v9; // rdx
  struct CFtpDir *FtpDirFromPidl; // rsi
  void *v11; // rax
  int v12; // ebp
  __int64 v13; // r8
  struct _DPA *v14; // rcx
  const ITEMIDLIST *v15; // rbx
  const ITEMIDLIST *Ptr; // rax
  LPITEMIDLIST v17; // rdi
  const struct _ITEMIDLIST *LastIDReferense; // rax
  int IsServerItemID; // ebx
  CFtpPidlList *v20; // rcx
  const struct _ITEMIDLIST **PidlList; // rax
  const struct _ITEMIDLIST **v22; // rbx

  v9 = (const struct _ITEMIDLIST *)(*((_QWORD *)a1 + 6) + *((int *)a1 + 16));
  if ( v9 && v9->mkid.cb )
    FtpDirFromPidl = CFtpFolder::GetFtpDirFromPidl(a1, v9);
  else
    FtpDirFromPidl = 0;
  v11 = operator new(0x58u);
  if ( v11 )
  {
    *((_QWORD *)v11 + 2) = 0;
    *(_QWORD *)v11 = &CFtpMenu::`vftable'{for `IContextMenu'};
    *((_QWORD *)v11 + 1) = &CFtpMenu::`vftable'{for `CObjectWithSite'};
    *((_DWORD *)v11 + 20) = 1;
    _InterlockedIncrement((volatile signed __int32 *)&g_cRef);
    *((_QWORD *)v11 + 4) = 0;
    *((_QWORD *)v11 + 5) = 0;
    v12 = -2147467259;
    *((_QWORD *)v11 + 6) = 0;
    *a5 = (struct CFtpMenu *)v11;
    IUnknown_Set((struct CFtpDir **)v11 + 5, a1);
    IUnknown_Set((struct CFtpDir **)*a5 + 4, a2);
    IUnknown_Set((struct CFtpDir **)*a5 + 6, FtpDirFromPidl);
    *((_DWORD *)*a5 + 6) = 536871287;
    *((_QWORD *)*a5 + 7) = a3;
    *((_DWORD *)*a5 + 19) = a4;
    v13 = *((_QWORD *)a2 + 2);
    v14 = *(struct _DPA **)(v13 + 16);
    if ( !*(_DWORD *)v14
      || *(_DWORD *)v14 == 1
      && ((v15 = (const ITEMIDLIST *)(*((int *)a1 + 16) + *((_QWORD *)a1 + 6)), !v13)
        ? (Ptr = 0)
        : (Ptr = (const ITEMIDLIST *)DPA_GetPtr(v14, 0)),
          v17 = ILCombine(v15, Ptr),
          LastIDReferense = FtpID_GetLastIDReferense(v17),
          IsServerItemID = FtpID_IsServerItemID(LastIDReferense),
          ILFree(v17),
          IsServerItemID) )
    {
      *((_DWORD *)*a5 + 6) &= 0xFFFFFFCF;
    }
    v20 = (CFtpPidlList *)*((_QWORD *)*a5 + 4);
    if ( !v20
      || (PidlList = CFtpPidlList::GetPidlList(v20), (v22 = PidlList) == 0)
      || (v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const struct _ITEMIDLIST **, char *))(**((_QWORD **)*a5 + 5)
                                                                                               + 72LL))(
                  *((_QWORD *)*a5 + 5),
                  **(unsigned int **)(*(_QWORD *)(*((_QWORD *)*a5 + 4) + 16LL) + 16LL),
                  PidlList,
                  (char *)*a5 + 24),
          LocalFree(v22),
          v12 < 0) )
    {
      IUnknown_Set(a5, 0);
    }
  }
  else
  {
    v12 = -2147024882;
    *a5 = 0;
  }
  if ( FtpDirFromPidl )
    (*(void (__fastcall **)(struct CFtpDir *))(*(_QWORD *)FtpDirFromPidl + 16LL))(FtpDirFromPidl);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000d500  push    rbx
0x18000d502  push    rbp
0x18000d503  push    rsi
0x18000d504  push    rdi
0x18000d505  push    r12
0x18000d507  push    r13
0x18000d509  push    r14
0x18000d50b  push    r15
0x18000d50d  sub     rsp, 38h
0x18000d511  mov     rdi, rdx
0x18000d514  xor     r13d, r13d
0x18000d517  movsxd  rdx, dword ptr [rcx+40h]
0x18000d51b  mov     r15d, r9d
0x18000d51e  mov     r12, r8
0x18000d521  mov     rbx, rcx
0x18000d524  add     rdx, [rcx+30h]; struct _ITEMIDLIST *
0x18000d528  jz      short loc_18000D53A
0x18000d52a  cmp     [rdx], r13w
0x18000d52e  jz      short loc_18000D53A
0x18000d530  call    ?GetFtpDirFromPidl@CFtpFolder@@QEAAPEAVCFtpDir@@PEFBU_ITEMIDLIST@@@Z; CFtpFolder::GetFtpDirFromPidl(_ITEMIDLIST const *)
0x18000d535  mov     rsi, rax
0x18000d538  jmp     short loc_18000D53D
0x18000d53a  mov     rsi, r13
0x18000d53d  mov     ecx, 58h ; 'X'; unsigned __int64
0x18000d542  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d547  test    rax, rax
0x18000d54a  jz      loc_18000D694
0x18000d550  lea     rcx, ??_7CFtpMenu@@6BIContextMenu@@@; const CFtpMenu::`vftable'{for `IContextMenu'}
0x18000d557  mov     [rax+10h], r13
0x18000d55b  mov     [rax], rcx
0x18000d55e  lea     rcx, ??_7CFtpMenu@@6BCObjectWithSite@@@; const CFtpMenu::`vftable'{for `CObjectWithSite'}
0x18000d565  mov     [rax+8], rcx
0x18000d569  mov     dword ptr [rax+50h], 1
0x18000d570  lock inc cs:?g_cRef@@3KA; ulong g_cRef
0x18000d577  mov     r14, [rsp+78h+arg_20]
0x18000d57f  lea     rcx, [rax+28h]; struct CFtpDir **
0x18000d583  mov     [rax+20h], r13
0x18000d587  mov     rdx, rbx; struct CFtpDir *
0x18000d58a  mov     [rax+28h], r13
0x18000d58e  mov     ebp, 80004005h
0x18000d593  mov     [rax+30h], r13
0x18000d597  mov     [r14], rax
0x18000d59a  call    ?IUnknown_Set@@YAXPEAPEAVCFtpDir@@PEAV1@@Z; IUnknown_Set(CFtpDir * *,CFtpDir *)
0x18000d59f  mov     rcx, [r14]
0x18000d5a2  mov     rdx, rdi; struct CFtpDir *
0x18000d5a5  add     rcx, 20h ; ' '; struct CFtpDir **
0x18000d5a9  call    ?IUnknown_Set@@YAXPEAPEAVCFtpDir@@PEAV1@@Z; IUnknown_Set(CFtpDir * *,CFtpDir *)
0x18000d5ae  mov     rcx, [r14]
0x18000d5b1  mov     rdx, rsi; struct CFtpDir *
0x18000d5b4  add     rcx, 30h ; '0'; struct CFtpDir **
0x18000d5b8  call    ?IUnknown_Set@@YAXPEAPEAVCFtpDir@@PEAV1@@Z; IUnknown_Set(CFtpDir * *,CFtpDir *)
0x18000d5bd  mov     rax, [r14]
0x18000d5c0  mov     dword ptr [rax+18h], 20000177h
0x18000d5c7  mov     rax, [r14]
0x18000d5ca  mov     [rax+38h], r12
0x18000d5ce  mov     rax, [r14]
0x18000d5d1  mov     [rax+4Ch], r15d
0x18000d5d5  mov     r8, [rdi+10h]
0x18000d5d9  mov     rcx, [r8+10h]; hdpa
0x18000d5dd  cmp     [rcx], r13d
0x18000d5e0  jz      short loc_18000D631
0x18000d5e2  cmp     dword ptr [rcx], 1
0x18000d5e5  jnz     short loc_18000D638
0x18000d5e7  movsxd  rdx, dword ptr [rbx+40h]
0x18000d5eb  mov     rbx, [rbx+30h]
0x18000d5ef  add     rbx, rdx
0x18000d5f2  test    r8, r8
0x18000d5f5  jz      short loc_18000D600
0x18000d5f7  xor     edx, edx; i
0x18000d5f9  call    DPA_GetPtr
0x18000d5fe  jmp     short loc_18000D603
0x18000d600  mov     rax, r13
0x18000d603  mov     rdx, rax; pidl2
0x18000d606  mov     rcx, rbx; pidl1
0x18000d609  call    cs:__imp_ILCombine
0x18000d60f  mov     rcx, rax; struct _ITEMIDLIST *
0x18000d612  mov     rdi, rax
0x18000d615  call    ?FtpID_GetLastIDReferense@@YAPEFBU_ITEMIDLIST@@PEFBU1@@Z; FtpID_GetLastIDReferense(_ITEMIDLIST const *)
0x18000d61a  mov     rcx, rax; struct _ITEMIDLIST *
0x18000d61d  call    ?FtpID_IsServerItemID@@YAHPEFBU_ITEMIDLIST@@@Z; FtpID_IsServerItemID(_ITEMIDLIST const *)
0x18000d622  mov     rcx, rdi; pidl
0x18000d625  mov     ebx, eax
0x18000d627  call    cs:__imp_ILFree
0x18000d62d  test    ebx, ebx
0x18000d62f  jz      short loc_18000D638
0x18000d631  mov     rax, [r14]
0x18000d634  and     dword ptr [rax+18h], 0FFFFFFCFh
0x18000d638  mov     rax, [r14]
0x18000d63b  mov     rcx, [rax+20h]; this
0x18000d63f  test    rcx, rcx
0x18000d642  jz      short loc_18000D688
0x18000d644  call    ?GetPidlList@CFtpPidlList@@QEAAPEAPEFBU_ITEMIDLIST@@XZ; CFtpPidlList::GetPidlList(void)
0x18000d649  mov     rbx, rax
0x18000d64c  test    rax, rax
0x18000d64f  jz      short loc_18000D688
0x18000d651  mov     rdx, [r14]
0x18000d654  mov     rcx, [rdx+28h]
0x18000d658  lea     r9, [rdx+18h]
0x18000d65c  mov     rdx, [rdx+20h]
0x18000d660  mov     r10, [rcx]
0x18000d663  mov     r8, [rdx+10h]
0x18000d667  mov     rdx, [r8+10h]
0x18000d66b  mov     r8, rax
0x18000d66e  mov     rax, [r10+48h]
0x18000d672  mov     edx, [rdx]
0x18000d674  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d679  mov     rcx, rbx; hMem
0x18000d67c  mov     ebp, eax
0x18000d67e  call    cs:__imp_LocalFree
0x18000d684  test    ebp, ebp
0x18000d686  jns     short loc_18000D6A4
0x18000d688  xor     edx, edx; struct CFtpDir *
0x18000d68a  mov     rcx, r14; struct CFtpDir **
0x18000d68d  call    ?IUnknown_Set@@YAXPEAPEAVCFtpDir@@PEAV1@@Z; IUnknown_Set(CFtpDir * *,CFtpDir *)
0x18000d692  jmp     short loc_18000D6A4
0x18000d694  mov     rax, [rsp+78h+arg_20]
0x18000d69c  mov     ebp, 8007000Eh
0x18000d6a1  mov     [rax], r13
0x18000d6a4  test    rsi, rsi
0x18000d6a7  jz      short loc_18000D6B8
0x18000d6a9  mov     rax, [rsi]
0x18000d6ac  mov     rcx, rsi
0x18000d6af  mov     rax, [rax+10h]
0x18000d6b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6b8  mov     eax, ebp
0x18000d6ba  add     rsp, 38h
0x18000d6be  pop     r15
0x18000d6c0  pop     r14
0x18000d6c2  pop     r13
0x18000d6c4  pop     r12
0x18000d6c6  pop     rdi
0x18000d6c7  pop     rsi
0x18000d6c8  pop     rbp
0x18000d6c9  pop     rbx
0x18000d6ca  retn
```
