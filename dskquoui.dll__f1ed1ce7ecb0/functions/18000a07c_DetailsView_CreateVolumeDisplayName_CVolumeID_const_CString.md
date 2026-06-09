# DetailsView::CreateVolumeDisplayName(CVolumeID const &,CString *)

- ea: `0x18000a07c`
- end: `0x18000a470`
- name: `?CreateVolumeDisplayName@DetailsView@@SAJAEBVCVolumeID@@PEAVCString@@@Z`
- size: `1012`
- prototype: `static int(const struct CVolumeID *, struct CString *)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000c224`
- `0x1800190e4`

## callees

- `0x180001510`
- `0x1800022b4`
- `0x18000a07c`
- `0x180010d24`
- `0x180019f38`
- `0x18001a5f0`
- `0x18001a73c`
- `0x18001f010`

## import_xrefs

- `SHELL32!SHGetSpecialFolderLocation` at `0x18000a12b`
- `SHELL32!SHGetSpecialFolderLocation` at `0x18000a12b`
- `SHELL32!SHGetDesktopFolder` at `0x18000a0ee`
- `SHELL32!SHGetDesktopFolder` at `0x18000a0ee`
- `SHLWAPI!StrRetToBufW` at `0x18000a2b9`
- `SHLWAPI!StrRetToBufW` at `0x18000a347`
- `SHLWAPI!StrRetToBufW` at `0x18000a2b9`
- `SHLWAPI!StrRetToBufW` at `0x18000a347`
- `SHLWAPI!PathIsUNCW` at `0x18000a2c6`
- `SHLWAPI!PathIsUNCW` at `0x18000a2c6`
- `SHLWAPI!PathIsRootW` at `0x18000a2d7`
- `SHLWAPI!PathIsRootW` at `0x18000a2d7`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall DetailsView::CreateVolumeDisplayName(const struct CVolumeID *a1, struct CString *a2)
{
  HRESULT v4; // ebx
  int *v5; // rsi
  struct IShellFolderVtbl *lpVtbl; // rax
  __int64 v7; // rax
  _WORD *v8; // r12
  __int64 v9; // r15
  unsigned int (__fastcall *v10)(__int64, __int64, char *, _DWORD *); // r13
  char *v11; // rdi
  WCHAR *Buffer; // rax
  _DWORD v14[2]; // [rsp+30h] [rbp-D0h] BYREF
  _DWORD v15[4]; // [rsp+38h] [rbp-C8h] BYREF
  LPCITEMIDLIST pidl; // [rsp+48h] [rbp-B8h] BYREF
  int v17; // [rsp+50h] [rbp-B0h]
  __int64 v18; // [rsp+58h] [rbp-A8h]
  void **v19; // [rsp+60h] [rbp-A0h]
  int v20; // [rsp+68h] [rbp-98h]
  __int64 *v21; // [rsp+70h] [rbp-90h] BYREF
  void **v22; // [rsp+78h] [rbp-88h]
  int v23; // [rsp+80h] [rbp-80h]
  __int64 v24; // [rsp+88h] [rbp-78h] BYREF
  _DWORD v25[4]; // [rsp+90h] [rbp-70h]
  void **v26; // [rsp+A0h] [rbp-60h] BYREF
  int v27; // [rsp+A8h] [rbp-58h]
  LPITEMIDLIST ppidl; // [rsp+B0h] [rbp-50h] BYREF
  void **v29; // [rsp+B8h] [rbp-48h]
  int v30; // [rsp+C0h] [rbp-40h]
  IShellFolder *ppshf; // [rsp+C8h] [rbp-38h] BYREF
  STRRET pstr; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR pszBuf[264]; // [rsp+1E0h] [rbp+E0h] BYREF

  if ( *((_BYTE *)a1 + 48) )
  {
    v4 = -2147467259;
    CString::operator=(a2, (char *)a1 + 16);
  }
  else
  {
    v29 = &com_autoptr<IDiskQuotaControl>::`vftable';
    ppshf = 0;
    v30 = 1;
    v4 = SHGetDesktopFolder(&ppshf);
    if ( v4 >= 0 )
    {
      v5 = &sh_autoptr<_ITEMIDLIST>::`vbtable';
      *(_QWORD *)v25 = &sh_autoptr<_ITEMIDLIST>::`vbtable';
      v26 = &sh_autoptr<_ITEMIDLIST>::`vftable';
      v25[3] = 0;
      ppidl = 0;
      v27 = 1;
      v4 = SHGetSpecialFolderLocation(0, 17, &ppidl);
      if ( v4 >= 0 )
      {
        v20 = 0;
        v21 = 0;
        v19 = &com_autoptr<IDiskQuotaControl>::`vftable';
        lpVtbl = ppshf->lpVtbl;
        v21 = 0;
        v20 = 1;
        v4 = ((__int64 (__fastcall *)(IShellFolder *, _QWORD, _QWORD, GUID *, __int64 **))lpVtbl->BindToObject)(
               ppshf,
               *(void ***)((char *)&v26 + *(int *)(*(_QWORD *)v25 + 4LL)),
               0,
               &IID_IShellFolder,
               &v21);
        if ( v4 >= 0 )
        {
          v23 = 0;
          v24 = 0;
          v22 = &com_autoptr<IDiskQuotaControl>::`vftable';
          v7 = *v21;
          v24 = 0;
          v23 = 1;
          v4 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, __int64 *))(v7 + 32))(v21, 0, 32, &v24);
          if ( v4 >= 0 )
          {
            *(_QWORD *)v15 = &sh_autoptr<_ITEMIDLIST>::`vbtable';
            v17 = 0;
            v18 = 0;
            pidl = (LPCITEMIDLIST)&sh_autoptr<_ITEMIDLIST>::`vftable';
            v15[3] = 0;
            v14[0] = 0;
            v8 = (_WORD *)**((_QWORD **)a1 + 1);
            while ( 1 )
            {
              v9 = v24;
              v10 = *(unsigned int (__fastcall **)(__int64, __int64, char *, _DWORD *))(*(_QWORD *)v24 + 24LL);
              v11 = (char *)v15 + v5[1];
              if ( *((_DWORD *)v11 + 2) )
                (**(void (__fastcall ***)(char *))v11)((char *)v15 + v5[1]);
              *((_QWORD *)v11 + 2) = 0;
              *((_DWORD *)v11 + 2) = 1;
              if ( v10(v9, 1, v11 + 16, v14) )
                break;
              memset_0(&pstr, 0, sizeof(pstr));
              v4 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, STRRET *))(*v21 + 88))(
                     v21,
                     *(LPCITEMIDLIST *)((char *)&pidl + *(int *)(*(_QWORD *)v15 + 4LL)),
                     0x8000,
                     &pstr);
              if ( v4 >= 0 )
              {
                StrRetToBufW(&pstr, *(LPCITEMIDLIST *)((char *)&pidl + *(int *)(*(_QWORD *)v15 + 4LL)), pszBuf, 0x104u);
                if ( !PathIsUNCW(pszBuf) && PathIsRootW(pszBuf) && *v8 == pszBuf[0] )
                {
                  v4 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, STRRET *))(*v21 + 88))(
                         v21,
                         *(LPCITEMIDLIST *)((char *)&pidl + *(int *)(*(_QWORD *)v15 + 4LL)),
                         0,
                         &pstr);
                  if ( v4 >= 0 )
                  {
                    Buffer = CString::GetBuffer(a2, 260);
                    StrRetToBufW(
                      &pstr,
                      *(LPCITEMIDLIST *)((char *)&pidl + *(int *)(*(_QWORD *)v15 + 4LL)),
                      Buffer,
                      0x104u);
                    CString::ReleaseBuffer(a2);
                  }
                  break;
                }
              }
              v5 = *(int **)v15;
            }
            *(_QWORD *)((char *)v15 + *(int *)(*(_QWORD *)v15 + 4LL)) = &sh_autoptr<_ITEMIDLIST>::`vftable';
            *(_DWORD *)((char *)&v14[1] + *(int *)(*(_QWORD *)v15 + 4LL)) = *(_DWORD *)(*(_QWORD *)v15 + 4LL) - 16;
            if ( *(_DWORD *)((char *)&v15[2] + *(int *)(*(_QWORD *)v15 + 4LL)) )
              sh_autoptr<_ITEMIDLIST>::nukeit(&pidl);
          }
          v22 = &com_autoptr<IDiskQuotaControl>::`vftable';
          if ( v23 && v24 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
        }
        v19 = &com_autoptr<IDiskQuotaControl>::`vftable';
        if ( v20 && v21 )
          (*(void (__fastcall **)(__int64 *))(*v21 + 16))(v21);
      }
      *(_QWORD *)((char *)v25 + *(int *)(*(_QWORD *)v25 + 4LL)) = &sh_autoptr<_ITEMIDLIST>::`vftable';
      *(_DWORD *)((char *)&v25[-1] + *(int *)(*(_QWORD *)v25 + 4LL)) = *(_DWORD *)(*(_QWORD *)v25 + 4LL) - 16;
      if ( *(_DWORD *)((char *)&v25[2] + *(int *)(*(_QWORD *)v25 + 4LL)) )
        sh_autoptr<_ITEMIDLIST>::nukeit(&v26);
    }
    v29 = &com_autoptr<IDiskQuotaControl>::`vftable';
    if ( v30 && ppshf )
      ((void (__fastcall *)(IShellFolder *))ppshf->lpVtbl->Release)(ppshf);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000a07c  mov     [rsp-8+arg_10], rbx
0x18000a081  push    rbp
0x18000a082  push    rsi
0x18000a083  push    rdi
0x18000a084  push    r12
0x18000a086  push    r13
0x18000a088  push    r14
0x18000a08a  push    r15
0x18000a08c  lea     rbp, [rsp-300h]
0x18000a094  sub     rsp, 400h
0x18000a09b  mov     rax, cs:__security_cookie
0x18000a0a2  xor     rax, rsp
0x18000a0a5  mov     [rbp+330h+var_40], rax
0x18000a0ac  mov     r14, rdx
0x18000a0af  mov     rdi, rcx
0x18000a0b2  xor     r15d, r15d
0x18000a0b5  cmp     [rcx+30h], r15b
0x18000a0b9  jz      short loc_18000A0D1
0x18000a0bb  mov     ebx, 80004005h
0x18000a0c0  lea     rdx, [rcx+10h]
0x18000a0c4  mov     rcx, r14
0x18000a0c7  call    ??4CString@@QEAAAEAV0@AEBV0@@Z; CString::operator=(CString const &)
0x18000a0cc  jmp     loc_18000A444
0x18000a0d1  lea     r13, ??_7?$com_autoptr@UIDiskQuotaControl@@@@6B@; const com_autoptr<IDiskQuotaControl>::`vftable'
0x18000a0d8  mov     [rbp+330h+var_378], r13
0x18000a0dc  mov     [rbp+330h+ppshf], r15
0x18000a0e0  mov     r12d, 1
0x18000a0e6  mov     [rbp+330h+var_370], r12d
0x18000a0ea  lea     rcx, [rbp+330h+ppshf]; ppshf
0x18000a0ee  call    cs:__imp_SHGetDesktopFolder
0x18000a0f4  mov     ebx, eax
0x18000a0f6  test    eax, eax
0x18000a0f8  js      loc_18000A424
0x18000a0fe  lea     rsi, ??_8?$sh_autoptr@U_ITEMIDLIST@@@@7B@; const sh_autoptr<_ITEMIDLIST>::`vbtable'
0x18000a105  mov     [rbp+330h+var_3A0], rsi
0x18000a109  lea     rax, ??_7?$sh_autoptr@U_ITEMIDLIST@@@@6B@; const sh_autoptr<_ITEMIDLIST>::`vftable'
0x18000a110  mov     [rbp+330h+var_390], rax
0x18000a114  mov     [rbp+330h+var_394], r15d
0x18000a118  mov     [rbp+330h+ppidl], r15
0x18000a11c  mov     [rbp+330h+var_388], r12d
0x18000a120  lea     r8, [rbp+330h+ppidl]; ppidl
0x18000a124  lea     edx, [r12+10h]; csidl
0x18000a129  xor     ecx, ecx; hwnd
0x18000a12b  call    cs:__imp_SHGetSpecialFolderLocation
0x18000a131  mov     ebx, eax
0x18000a133  test    eax, eax
0x18000a135  js      loc_18000A3E8
0x18000a13b  mov     [rsp+430h+var_3C8], r15d
0x18000a140  mov     [rsp+430h+var_3C0], r15
0x18000a145  mov     [rsp+430h+var_3D0], r13
0x18000a14a  mov     rcx, [rbp+330h+ppshf]
0x18000a14e  mov     rax, [rcx]
0x18000a151  mov     [rsp+430h+var_3C0], r15
0x18000a156  mov     [rsp+430h+var_3C8], r12d
0x18000a15b  mov     rdx, [rbp+330h+var_3A0]
0x18000a15f  movsxd  rdx, dword ptr [rdx+4]
0x18000a163  lea     r8, [rsp+430h+var_3C0]
0x18000a168  mov     [rsp+430h+var_410], r8
0x18000a16d  lea     r9, IID_IShellFolder
0x18000a174  xor     r8d, r8d
0x18000a177  mov     rdx, [rbp+rdx+330h+var_390]
0x18000a17c  mov     rax, [rax+28h]
0x18000a180  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a185  mov     ebx, eax
0x18000a187  test    eax, eax
0x18000a189  js      loc_18000A3C5
0x18000a18f  mov     [rbp+330h+var_3B0], r15d
0x18000a193  mov     [rbp+330h+var_3A8], r15
0x18000a197  lea     rax, ??_7?$com_autoptr@UIDiskQuotaControl@@@@6B@; const com_autoptr<IDiskQuotaControl>::`vftable'
0x18000a19e  mov     [rsp+430h+var_3B8], rax
0x18000a1a3  mov     rcx, [rsp+430h+var_3C0]
0x18000a1a8  mov     rax, [rcx]
0x18000a1ab  mov     [rbp+330h+var_3A8], r15
0x18000a1af  mov     [rbp+330h+var_3B0], r12d
0x18000a1b3  lea     r9, [rbp+330h+var_3A8]
0x18000a1b7  xor     edx, edx
0x18000a1b9  lea     r8d, [r12+1Fh]
0x18000a1be  mov     rax, [rax+20h]
0x18000a1c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1c7  mov     ebx, eax
0x18000a1c9  test    eax, eax
0x18000a1cb  js      loc_18000A39D
0x18000a1d1  mov     [rsp+430h+var_3F8], rsi
0x18000a1d6  mov     [rsp+430h+var_3E0], r15d
0x18000a1db  mov     [rsp+430h+var_3D8], r15
0x18000a1e0  lea     rax, ??_7?$sh_autoptr@U_ITEMIDLIST@@@@6B@; const sh_autoptr<_ITEMIDLIST>::`vftable'
0x18000a1e7  mov     [rsp+430h+pidl], rax
0x18000a1ec  mov     [rsp+430h+var_3EC], r15d
0x18000a1f1  mov     [rsp+430h+var_400], r15d
0x18000a1f6  mov     rax, [rdi+8]
0x18000a1fa  mov     r12, [rax]
0x18000a1fd  mov     r15, [rbp+330h+var_3A8]
0x18000a201  mov     rax, [r15]
0x18000a204  mov     r13, [rax+18h]
0x18000a208  movsxd  rax, dword ptr [rsi+4]
0x18000a20c  lea     rdi, [rsp+430h+var_3F8]
0x18000a211  add     rdi, rax
0x18000a214  cmp     dword ptr [rdi+8], 0
0x18000a218  jz      short loc_18000A228
0x18000a21a  mov     rax, [rdi]
0x18000a21d  mov     rcx, rdi
0x18000a220  mov     rax, [rax]
0x18000a223  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a228  lea     r8, [rdi+10h]
0x18000a22c  mov     qword ptr [r8], 0
0x18000a233  mov     eax, 1
0x18000a238  mov     [rdi+8], eax
0x18000a23b  lea     r9, [rsp+430h+var_400]
0x18000a240  mov     edx, eax
0x18000a242  mov     rcx, r15
0x18000a245  mov     rax, r13
0x18000a248  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a24d  xor     r15d, r15d
0x18000a250  test    eax, eax
0x18000a252  jnz     loc_18000A356
0x18000a258  xor     edx, edx; Val
0x18000a25a  mov     r8d, 110h; Size
0x18000a260  lea     rcx, [rbp+330h+pstr]; void *
0x18000a264  call    memset_0
0x18000a269  mov     rcx, [rsp+430h+var_3C0]
0x18000a26e  mov     r8, [rcx]
0x18000a271  mov     rax, [rsp+430h+var_3F8]
0x18000a276  movsxd  rdx, dword ptr [rax+4]
0x18000a27a  mov     rax, [r8+58h]
0x18000a27e  lea     r9, [rbp+330h+pstr]
0x18000a282  mov     r8d, 8000h
0x18000a288  mov     rdx, [rsp+rdx+430h+pidl]
0x18000a28d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a292  mov     ebx, eax
0x18000a294  test    eax, eax
0x18000a296  js      short loc_18000A2EF
0x18000a298  mov     rax, [rsp+430h+var_3F8]
0x18000a29d  movsxd  rdx, dword ptr [rax+4]
0x18000a2a1  mov     edi, 104h
0x18000a2a6  mov     r9d, edi; cchBuf
0x18000a2a9  lea     r8, [rbp+330h+pszBuf]; pszBuf
0x18000a2b0  mov     rdx, [rsp+rdx+430h+pidl]; pidl
0x18000a2b5  lea     rcx, [rbp+330h+pstr]; pstr
0x18000a2b9  call    cs:__imp_StrRetToBufW
0x18000a2bf  lea     rcx, [rbp+330h+pszBuf]; pszPath
0x18000a2c6  call    cs:__imp_PathIsUNCW
0x18000a2cc  test    eax, eax
0x18000a2ce  jnz     short loc_18000A2EF
0x18000a2d0  lea     rcx, [rbp+330h+pszBuf]; pszPath
0x18000a2d7  call    cs:__imp_PathIsRootW
0x18000a2dd  test    eax, eax
0x18000a2df  jz      short loc_18000A2EF
0x18000a2e1  movzx   eax, [rbp+330h+pszBuf]
0x18000a2e8  cmp     [r12], ax
0x18000a2ed  jz      short loc_18000A2F9
0x18000a2ef  mov     rsi, [rsp+430h+var_3F8]
0x18000a2f4  jmp     loc_18000A1FD
0x18000a2f9  mov     rcx, [rsp+430h+var_3C0]
0x18000a2fe  mov     r8, [rcx]
0x18000a301  mov     rax, [rsp+430h+var_3F8]
0x18000a306  movsxd  rdx, dword ptr [rax+4]
0x18000a30a  mov     rax, [r8+58h]
0x18000a30e  lea     r9, [rbp+330h+pstr]
0x18000a312  xor     r8d, r8d
0x18000a315  mov     rdx, [rsp+rdx+430h+pidl]
0x18000a31a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a31f  mov     ebx, eax
0x18000a321  test    eax, eax
0x18000a323  js      short loc_18000A356
0x18000a325  mov     edx, edi; int
0x18000a327  mov     rcx, r14; this
0x18000a32a  call    ?GetBuffer@CString@@QEAAPEAGH@Z; CString::GetBuffer(int)
0x18000a32f  mov     rcx, [rsp+430h+var_3F8]
0x18000a334  movsxd  rdx, dword ptr [rcx+4]
0x18000a338  mov     r9d, edi; cchBuf
0x18000a33b  mov     r8, rax; pszBuf
0x18000a33e  mov     rdx, [rsp+rdx+430h+pidl]; pidl
0x18000a343  lea     rcx, [rbp+330h+pstr]; pstr
0x18000a347  call    cs:__imp_StrRetToBufW
0x18000a34d  mov     rcx, r14; this
0x18000a350  call    ?ReleaseBuffer@CString@@QEAAXXZ; CString::ReleaseBuffer(void)
0x18000a355  nop
0x18000a356  mov     rax, [rsp+430h+var_3F8]
0x18000a35b  movsxd  rcx, dword ptr [rax+4]
0x18000a35f  lea     rax, ??_7?$sh_autoptr@U_ITEMIDLIST@@@@6B@; const sh_autoptr<_ITEMIDLIST>::`vftable'
0x18000a366  mov     [rsp+rcx+430h+var_3F8], rax
0x18000a36b  mov     rax, [rsp+430h+var_3F8]
0x18000a370  movsxd  rcx, dword ptr [rax+4]
0x18000a374  lea     edx, [rcx-10h]
0x18000a377  mov     [rsp+rcx+430h+var_3FC], edx
0x18000a37b  mov     rax, [rsp+430h+var_3F8]
0x18000a380  movsxd  rcx, dword ptr [rax+4]
0x18000a384  cmp     [rsp+rcx+430h+var_3F0], r15d
0x18000a389  jz      short loc_18000A396
0x18000a38b  lea     rcx, [rsp+430h+pidl]
0x18000a390  call    ?nukeit@?$sh_autoptr@U_ITEMIDLIST@@@@EEAAXXZ; sh_autoptr<_ITEMIDLIST>::nukeit(void)
0x18000a395  nop
0x18000a396  lea     r13, ??_7?$com_autoptr@UIDiskQuotaControl@@@@6B@; const com_autoptr<IDiskQuotaControl>::`vftable'
0x18000a39d  lea     rax, ??_7?$com_autoptr@UIDiskQuotaControl@@@@6B@; const com_autoptr<IDiskQuotaControl>::`vftable'
0x18000a3a4  mov     [rsp+430h+var_3B8], rax
0x18000a3a9  cmp     [rbp+330h+var_3B0], r15d
0x18000a3ad  jz      short loc_18000A3C5
0x18000a3af  mov     rcx, [rbp+330h+var_3A8]
0x18000a3b3  test    rcx, rcx
0x18000a3b6  jz      short loc_18000A3C5
0x18000a3b8  mov     rax, [rcx]
0x18000a3bb  mov     rax, [rax+10h]
0x18000a3bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3c4  nop
0x18000a3c5  mov     [rsp+430h+var_3D0], r13
0x18000a3ca  cmp     [rsp+430h+var_3C8], r15d
0x18000a3cf  jz      short loc_18000A3E8
0x18000a3d1  mov     rcx, [rsp+430h+var_3C0]
0x18000a3d6  test    rcx, rcx
0x18000a3d9  jz      short loc_18000A3E8
0x18000a3db  mov     rax, [rcx]
0x18000a3de  mov     rax, [rax+10h]
0x18000a3e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3e7  nop
0x18000a3e8  mov     rax, [rbp+330h+var_3A0]
0x18000a3ec  movsxd  rcx, dword ptr [rax+4]
0x18000a3f0  lea     rax, ??_7?$sh_autoptr@U_ITEMIDLIST@@@@6B@; const sh_autoptr<_ITEMIDLIST>::`vftable'
0x18000a3f7  mov     [rbp+rcx+330h+var_3A0], rax
0x18000a3fc  mov     rax, [rbp+330h+var_3A0]
0x18000a400  movsxd  rcx, dword ptr [rax+4]
0x18000a404  lea     edx, [rcx-10h]
0x18000a407  mov     dword ptr [rbp+rcx+330h+var_3A8+4], edx
0x18000a40b  mov     rax, [rbp+330h+var_3A0]
0x18000a40f  movsxd  rcx, dword ptr [rax+4]
0x18000a413  cmp     [rbp+rcx+330h+var_398], r15d
0x18000a418  jz      short loc_18000A424
0x18000a41a  lea     rcx, [rbp+330h+var_390]
0x18000a41e  call    ?nukeit@?$sh_autoptr@U_ITEMIDLIST@@@@EEAAXXZ; sh_autoptr<_ITEMIDLIST>::nukeit(void)
0x18000a423  nop
0x18000a424  mov     [rbp+330h+var_378], r13
0x18000a428  cmp     [rbp+330h+var_370], r15d
0x18000a42c  jz      short loc_18000A444
0x18000a42e  mov     rcx, [rbp+330h+ppshf]
0x18000a432  test    rcx, rcx
0x18000a435  jz      short loc_18000A444
0x18000a437  mov     rax, [rcx]
0x18000a43a  mov     rax, [rax+10h]
0x18000a43e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a443  nop
0x18000a444  mov     eax, ebx
0x18000a446  mov     rcx, [rbp+330h+var_40]
0x18000a44d  xor     rcx, rsp; StackCookie
0x18000a450  call    __security_check_cookie
0x18000a455  mov     rbx, [rsp+430h+arg_10]
0x18000a45d  add     rsp, 400h
0x18000a464  pop     r15
0x18000a466  pop     r14
0x18000a468  pop     r13
0x18000a46a  pop     r12
0x18000a46c  pop     rdi
0x18000a46d  pop     rsi
0x18000a46e  pop     rbp
0x18000a46f  retn
```
