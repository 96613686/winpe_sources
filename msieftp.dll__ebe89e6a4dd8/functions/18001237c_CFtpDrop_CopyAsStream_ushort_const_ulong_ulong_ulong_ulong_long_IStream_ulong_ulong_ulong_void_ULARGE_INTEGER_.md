# CFtpDrop::CopyAsStream(ushort const *,ulong,ulong,ulong,ulong,long (*)(IStream *,ulong,ulong,ulong,void *,_ULARGE_INTEGER *),void *)

- ea: `0x18001237c`
- end: `0x1800125c0`
- name: `?CopyAsStream@CFtpDrop@@IEAAJPEBGKKKKP6AJPEAUIStream@@KKKPEAXPEAT_ULARGE_INTEGER@@@Z2@Z`
- size: `580`
- prototype: `__int64 __usercall@<rax>(CFtpDrop *__hidden this@<rcx>, LPCWSTR lpFileName@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned int, unsigned int, int (*)(struct IStream *, unsigned int, unsigned int, unsigned int, void *, union _ULARGE_INTEGER *), void *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18001262c`

## callees

- `0x180011414`
- `0x1800121f0`
- `0x18001237c`
- `0x180014a4c`
- `0x18001cfc0`
- `0x18001e11c`
- `0x180020efc`
- `0x180024134`
- `0x180028010`

## import_xrefs

- `SHELL32!SHChangeNotify` at `0x180012509`
- `SHELL32!SHChangeNotify` at `0x180012509`
- `SHELL32!__imp_ILCombine` at `0x18001242c`
- `SHELL32!__imp_ILCombine` at `0x18001242c`
- `SHELL32!__imp_ILFree` at `0x180012511`
- `SHELL32!__imp_ILFree` at `0x18001251a`
- `SHELL32!__imp_ILFree` at `0x18001257b`
- `SHELL32!__imp_ILFree` at `0x1800125a0`
- `SHELL32!__imp_ILFree` at `0x180012511`
- `SHELL32!__imp_ILFree` at `0x18001251a`
- `SHELL32!__imp_ILFree` at `0x18001257b`
- `SHELL32!__imp_ILFree` at `0x1800125a0`

## pseudocode

```c
__int64 __fastcall CFtpDrop::CopyAsStream(
        CFtpDrop *this,
        LPCWSTR lpFileName,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        int (*a7)(struct IStream *, unsigned int, unsigned int, unsigned int, void *, union _ULARGE_INTEGER *),
        void *a8)
{
  int v12; // ebx
  unsigned int v13; // r15d
  unsigned int v14; // ebx
  struct CFtpDir *RelativePidl; // rax
  struct CFtpDir *v16; // rdi
  ITEMIDLIST *v17; // r14
  const struct _ITEMIDLIST *v18; // rax
  ITEMIDLIST *v19; // r12
  int v20; // eax
  int v21; // edx
  unsigned int v22; // r9d
  int v23; // eax
  int v24; // edx
  unsigned int v25; // r9d
  CFtpPidlList *v26; // rcx
  LPCITEMIDLIST *v27; // r15
  LPITEMIDLIST SubPidl; // rax
  ITEMIDLIST *v29; // r15
  unsigned int v31; // [rsp+28h] [rbp-40h]
  unsigned int v32; // [rsp+30h] [rbp-38h]
  unsigned int v33[2]; // [rsp+50h] [rbp-18h] BYREF
  LPCITEMIDLIST pidl2[2]; // [rsp+58h] [rbp-10h] BYREF
  int v35; // [rsp+B0h] [rbp+48h] BYREF

  v35 = 0;
  v12 = ConfirmCopy(
          lpFileName,
          lpFileName,
          (CFtpDrop *)((char *)this + 64),
          *((HWND *)this + 4),
          *((struct CFtpFolder **)this + 2),
          *((struct CFtpDir **)this + 3),
          *((unsigned int **)this + 7),
          *((_DWORD *)this + 17),
          &v35);
  if ( v12 >= 0 )
  {
    v13 = a5;
    v14 = a6;
    pidl2[0] = 0;
    RelativePidl = CFtpDrop::_GetRelativePidl(this, lpFileName, a3, a5, a6, (struct _ITEMIDLIST **)pidl2);
    v16 = RelativePidl;
    if ( RelativePidl )
    {
      v17 = (ITEMIDLIST *)pidl2[0];
      v18 = ILCombine(*((LPCITEMIDLIST *)RelativePidl + 6), pidl2[0]);
      v19 = (ITEMIDLIST *)v18;
      if ( v18 )
      {
        pidl2[0] = 0;
        *(_QWORD *)v33 = 0;
        v20 = CFtpStm_Create((const struct _ITEMIDLIST **)v16, v18, 0x40000000, (struct IStream **)pidl2, 0, 0, 0, 0);
        if ( v20 < 0 )
        {
          DisplayWininetError(*((HWND *)this + 4), v21, v20, v22, 0x19Du, v31, v32, 0);
          v12 = -2147023673;
        }
        else
        {
          v33[0] = v14;
          v33[1] = v13;
          v23 = ((__int64 (__fastcall *)(LPCITEMIDLIST, _QWORD, _QWORD, _QWORD, void *))a7)(pidl2[0], a4, v13, v14, a8);
          v12 = v23;
          if ( v23 < 0 )
          {
            DisplayWininetError(*((HWND *)this + 4), v24, v23, v25, 0x19Du, (unsigned int)v33, v32, 0);
            v12 = -2147023673;
          }
          else if ( v35 )
          {
            FtpPidl_SetFileSize(v17, v33[1], v33[0]);
            v26 = (CFtpPidlList *)*((_QWORD *)v16 + 3);
            v27 = (LPCITEMIDLIST *)*((_QWORD *)this + 2);
            if ( v26 )
              CFtpPidlList::InsertSorted(v26, v17);
            SubPidl = CFtpDir::GetSubPidl((LPCITEMIDLIST *)v16, v27, v17, 1);
            v29 = SubPidl;
            if ( SubPidl )
            {
              SHChangeNotify(2, 0x1000u, SubPidl, 0);
              ILFree(0);
              ILFree(v29);
            }
          }
          (*(void (__fastcall **)(LPCITEMIDLIST))(*(_QWORD *)pidl2[0] + 16LL))(pidl2[0]);
        }
        ILFree(v19);
      }
      else
      {
        v12 = -2147024882;
      }
      if ( v16 != *((struct CFtpDir **)this + 3) )
        (*(void (__fastcall **)(struct CFtpDir *))(*(_QWORD *)v16 + 16LL))(v16);
      ILFree(v17);
    }
    else
    {
      return (unsigned int)-2147467259;
    }
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18001237c  push    rbp
0x18001237e  push    rbx
0x18001237f  push    rsi
0x180012380  push    rdi
0x180012381  push    r12
0x180012383  push    r13
0x180012385  push    r14
0x180012387  push    r15
0x180012389  mov     rbp, rsp
0x18001238c  sub     rsp, 68h
0x180012390  lea     rax, [rbp+arg_0]
0x180012394  mov     [rbp+arg_0], 0
0x18001239b  mov     [rsp+68h+var_28], rax; int *
0x1800123a0  mov     r13d, r9d
0x1800123a3  mov     eax, [rcx+44h]
0x1800123a6  mov     r14d, r8d
0x1800123a9  mov     r9, [rcx+20h]; HWND
0x1800123ad  lea     r8, [rcx+40h]; enum OPS *
0x1800123b1  mov     dword ptr [rsp+68h+var_30], eax; int
0x1800123b5  mov     rsi, rcx
0x1800123b8  mov     rax, [rcx+38h]
0x1800123bc  mov     rdi, rdx
0x1800123bf  mov     [rsp+68h+var_38], rax; unsigned int *
0x1800123c4  mov     rax, [rcx+18h]
0x1800123c8  mov     qword ptr [rsp+68h+var_40], rax; struct CFtpDir *
0x1800123cd  mov     rax, [rcx+10h]
0x1800123d1  mov     rcx, rdx; lpFileName
0x1800123d4  mov     qword ptr [rsp+68h+var_48], rax; struct CFtpFolder *
0x1800123d9  call    ?ConfirmCopy@@YAJPEBG0PEAW4OPS@@PEAUHWND__@@PEAVCFtpFolder@@PEAVCFtpDir@@PEAKHPEAH@Z; ConfirmCopy(ushort const *,ushort const *,OPS *,HWND__ *,CFtpFolder *,CFtpDir *,ulong *,int,int *)
0x1800123de  mov     ebx, eax
0x1800123e0  test    eax, eax
0x1800123e2  js      loc_1800125AD
0x1800123e8  mov     r15d, [rbp+arg_20]
0x1800123ec  lea     rax, [rbp+pidl2]
0x1800123f0  mov     ebx, [rbp+arg_28]
0x1800123f3  mov     r9d, r15d; unsigned int
0x1800123f6  mov     qword ptr [rsp+68h+var_40], rax; struct _ITEMIDLIST **
0x1800123fb  mov     r8d, r14d; unsigned int
0x1800123fe  mov     rdx, rdi; unsigned __int16 *
0x180012401  mov     dword ptr [rsp+68h+var_48], ebx; unsigned int
0x180012405  mov     rcx, rsi; this
0x180012408  mov     [rbp+pidl2], 0
0x180012410  call    ?_GetRelativePidl@CFtpDrop@@AEAAPEAVCFtpDir@@PEBGKKKPEAPEFAU_ITEMIDLIST@@@Z; CFtpDrop::_GetRelativePidl(ushort const *,ulong,ulong,ulong,_ITEMIDLIST * *)
0x180012415  mov     rdi, rax
0x180012418  test    rax, rax
0x18001241b  jz      loc_1800125A8
0x180012421  mov     r14, [rbp+pidl2]
0x180012425  mov     rcx, [rax+30h]; pidl1
0x180012429  mov     rdx, r14; pidl2
0x18001242c  call    cs:__imp_ILCombine
0x180012432  xor     ecx, ecx
0x180012434  mov     r12, rax
0x180012437  test    rax, rax
0x18001243a  jz      loc_180012583
0x180012440  mov     dword ptr [rsp+68h+var_30], ecx; int
0x180012444  lea     r9, [rbp+pidl2]; struct IStream **
0x180012448  mov     [rsp+68h+var_38], rcx; unsigned int
0x18001244d  mov     r8d, 40000000h; unsigned int
0x180012453  mov     qword ptr [rsp+68h+var_40], rcx; unsigned int
0x180012458  mov     rdx, rax; struct _ITEMIDLIST *
0x18001245b  mov     qword ptr [rsp+68h+var_48], rcx; union _ULARGE_INTEGER
0x180012460  mov     [rbp+pidl2], rcx
0x180012464  mov     qword ptr [rbp+var_18], rcx
0x180012468  mov     rcx, rdi; struct CFtpDir *
0x18001246b  call    ?CFtpStm_Create@@YAJPEAVCFtpDir@@PEFBU_ITEMIDLIST@@KPEAPEAUIStream@@T_ULARGE_INTEGER@@3PEAUIProgressDialog@@H@Z; CFtpStm_Create(CFtpDir *,_ITEMIDLIST const *,ulong,IStream * *,_ULARGE_INTEGER,_ULARGE_INTEGER,IProgressDialog *,int)
0x180012470  test    eax, eax
0x180012472  js      loc_180012556
0x180012478  mov     rcx, [rbp+arg_38]
0x18001247f  lea     rax, [rbp+var_18]
0x180012483  mov     qword ptr [rsp+68h+var_40], rax; unsigned int
0x180012488  mov     r9d, ebx
0x18001248b  mov     rax, [rbp+arg_30]
0x18001248f  mov     r8d, r15d
0x180012492  mov     qword ptr [rsp+68h+var_48], rcx
0x180012497  mov     edx, r13d
0x18001249a  mov     rcx, [rbp+pidl2]
0x18001249e  mov     [rbp+var_18], ebx
0x1800124a1  mov     [rbp+var_18+4], r15d
0x1800124a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800124aa  mov     ebx, eax
0x1800124ac  test    eax, eax
0x1800124ae  js      short loc_180012522
0x1800124b0  cmp     [rbp+arg_0], 0
0x1800124b4  jz      loc_180012544
0x1800124ba  mov     r8d, [rbp+var_18]; unsigned int
0x1800124be  mov     rcx, r14; struct _ITEMIDLIST *
0x1800124c1  mov     edx, [rbp+var_18+4]; unsigned int
0x1800124c4  call    ?FtpPidl_SetFileSize@@YAJPEFAU_ITEMIDLIST@@KK@Z; FtpPidl_SetFileSize(_ITEMIDLIST *,ulong,ulong)
0x1800124c9  mov     rcx, [rdi+18h]; this
0x1800124cd  mov     r15, [rsi+10h]
0x1800124d1  test    rcx, rcx
0x1800124d4  jz      short loc_1800124DE
0x1800124d6  mov     rdx, r14; struct _ITEMIDLIST *
0x1800124d9  call    ?InsertSorted@CFtpPidlList@@QEAAJPEFBU_ITEMIDLIST@@@Z; CFtpPidlList::InsertSorted(_ITEMIDLIST const *)
0x1800124de  mov     r9d, 1; int
0x1800124e4  mov     r8, r14; struct _ITEMIDLIST *
0x1800124e7  mov     rdx, r15; struct CFtpFolder *
0x1800124ea  mov     rcx, rdi; this
0x1800124ed  call    ?GetSubPidl@CFtpDir@@QEAAPEFAU_ITEMIDLIST@@PEAVCFtpFolder@@PEFBU2@H@Z; CFtpDir::GetSubPidl(CFtpFolder *,_ITEMIDLIST const *,int)
0x1800124f2  mov     r15, rax
0x1800124f5  test    rax, rax
0x1800124f8  jz      short loc_180012544
0x1800124fa  xor     r9d, r9d; dwItem2
0x1800124fd  mov     r8, rax; dwItem1
0x180012500  mov     edx, 1000h; uFlags
0x180012505  lea     ecx, [r9+2]; wEventId
0x180012509  call    cs:__imp_SHChangeNotify
0x18001250f  xor     ecx, ecx; pidl
0x180012511  call    cs:__imp_ILFree
0x180012517  mov     rcx, r15; pidl
0x18001251a  call    cs:__imp_ILFree
0x180012520  jmp     short loc_180012544
0x180012522  mov     rcx, [rsi+20h]; HWND
0x180012526  mov     r8d, eax; int
0x180012529  mov     [rsp+68h+var_30], 0; struct IProgressDialog *
0x180012532  mov     dword ptr [rsp+68h+var_48], 19Dh; unsigned int
0x18001253a  call    ?DisplayWininetError@@YAHPEAUHWND__@@HJIIIIPEAUIProgressDialog@@@Z; DisplayWininetError(HWND__ *,int,long,uint,uint,uint,uint,IProgressDialog *)
0x18001253f  mov     ebx, 800704C7h
0x180012544  mov     rcx, [rbp+pidl2]
0x180012548  mov     rax, [rcx]
0x18001254b  mov     rax, [rax+10h]
0x18001254f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012554  jmp     short loc_180012578
0x180012556  mov     rcx, [rsi+20h]; HWND
0x18001255a  mov     r8d, eax; int
0x18001255d  mov     [rsp+68h+var_30], 0; struct IProgressDialog *
0x180012566  mov     dword ptr [rsp+68h+var_48], 19Dh; unsigned int
0x18001256e  call    ?DisplayWininetError@@YAHPEAUHWND__@@HJIIIIPEAUIProgressDialog@@@Z; DisplayWininetError(HWND__ *,int,long,uint,uint,uint,uint,IProgressDialog *)
0x180012573  mov     ebx, 800704C7h
0x180012578  mov     rcx, r12; pidl
0x18001257b  call    cs:__imp_ILFree
0x180012581  jmp     short loc_180012588
0x180012583  mov     ebx, 8007000Eh
0x180012588  cmp     rdi, [rsi+18h]
0x18001258c  jz      short loc_18001259D
0x18001258e  mov     rax, [rdi]
0x180012591  mov     rcx, rdi
0x180012594  mov     rax, [rax+10h]
0x180012598  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001259d  mov     rcx, r14; pidl
0x1800125a0  call    cs:__imp_ILFree
0x1800125a6  jmp     short loc_1800125AD
0x1800125a8  mov     ebx, 80004005h
0x1800125ad  mov     eax, ebx
0x1800125af  add     rsp, 68h
0x1800125b3  pop     r15
0x1800125b5  pop     r14
0x1800125b7  pop     r13
0x1800125b9  pop     r12
0x1800125bb  pop     rdi
0x1800125bc  pop     rsi
0x1800125bd  pop     rbx
0x1800125be  pop     rbp
0x1800125bf  retn
```
