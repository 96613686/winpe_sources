# CFtpDialogTemplate::OnClose(HWND__ *,HWND__ *,CFtpFolder *,CFtpPidlList *)

- ea: `0x180010728`
- end: `0x1800108dd`
- name: `?OnClose@CFtpDialogTemplate@@QEAAHPEAUHWND__@@0PEAVCFtpFolder@@PEAVCFtpPidlList@@@Z`
- size: `437`
- prototype: `int(CFtpDialogTemplate *__hidden this, HWND, HWND, struct CFtpFolder *, struct CFtpPidlList *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18001e668`

## callees

- `0x180002240`
- `0x18001027c`
- `0x180010728`
- `0x18001bd78`
- `0x1800269f4`
- `0x180028010`

## import_xrefs

- `SHELL32!SHBindToObject` at `0x180010825`
- `SHELL32!SHBindToObject` at `0x180010825`
- `SHELL32!__imp_ILRemoveLastID` at `0x1800107f6`
- `SHELL32!__imp_ILRemoveLastID` at `0x1800107f6`
- `SHELL32!__imp_ILClone` at `0x1800107e5`
- `SHELL32!__imp_ILClone` at `0x1800107e5`
- `SHELL32!__imp_ILFree` at `0x18001082e`
- `SHELL32!__imp_ILFree` at `0x18001082e`
- `SHLWAPI!StrCmpW` at `0x1800107bb`
- `SHLWAPI!StrCmpW` at `0x1800107bb`
- `USER32!GetDlgItem` at `0x180010764`
- `USER32!GetDlgItem` at `0x180010794`
- `USER32!GetDlgItem` at `0x180010764`
- `USER32!GetDlgItem` at `0x180010794`
- `USER32!GetWindowTextW` at `0x1800107a8`
- `USER32!GetWindowTextW` at `0x1800107a8`
- `USER32!IsWindowVisible` at `0x18001076d`
- `USER32!IsWindowVisible` at `0x18001076d`

## pseudocode

```c
_BOOL8 __fastcall CFtpDialogTemplate::OnClose(
        CFtpDialogTemplate *this,
        HWND a2,
        HWND a3,
        LPCITEMIDLIST *a4,
        struct CFtpPidlList *a5)
{
  BOOL v6; // ebp
  HWND DlgItem; // rax
  unsigned int v10; // r9d
  HWND v11; // rax
  PVOID Ptr; // rax
  struct _DPA *v13; // rcx
  const struct _ITEMIDLIST *LastIDReferense; // rbx
  ITEMIDLIST *v15; // rax
  ITEMIDLIST *v16; // rsi
  void *v17; // r10
  int v18; // eax
  void *ppv[2]; // [rsp+40h] [rbp-468h] BYREF
  WCHAR String[264]; // [rsp+50h] [rbp-458h] BYREF
  WCHAR psz1[264]; // [rsp+260h] [rbp-248h] BYREF

  v6 = 1;
  DlgItem = GetDlgItem(a2, 111);
  if ( IsWindowVisible(DlgItem) )
  {
    GetNameFromPidlList((struct CFtpFolder *)a4, a5, psz1, v10);
    v11 = GetDlgItem(a2, 111);
    GetWindowTextW(v11, String, 260);
    if ( StrCmpW(psz1, String) )
    {
      Ptr = (PVOID)*((_QWORD *)a5 + 2);
      ppv[0] = 0;
      v13 = (struct _DPA *)*((_QWORD *)Ptr + 2);
      if ( *(_DWORD *)v13 )
      {
        if ( Ptr )
          Ptr = DPA_GetPtr(v13, 0);
        LastIDReferense = FtpID_GetLastIDReferense((const struct _ITEMIDLIST *)Ptr);
        (*(void (__fastcall **)(LPCITEMIDLIST *, GUID *, void **))&(*a4)->mkid.cb)(a4, &IID_IShellFolder, ppv);
      }
      else
      {
        LastIDReferense = 0;
        v15 = ILClone(a4[6]);
        v16 = v15;
        if ( v15 )
        {
          ILRemoveLastID(v15);
          LastIDReferense = FtpID_GetLastIDReferense((LPCITEMIDLIST)((char *)a4[6] + *((int *)a4 + 16)));
          SHBindToObject(0, v16, 0, &GUID_000214e6_0000_0000_c000_000000000046, ppv);
          ILFree(v16);
        }
      }
      v17 = ppv[0];
      if ( ppv[0] )
      {
        if ( LastIDReferense )
        {
          v18 = (*(__int64 (__fastcall **)(void *, HWND, const struct _ITEMIDLIST *, WCHAR *, _DWORD, _QWORD))(*(_QWORD *)ppv[0] + 96LL))(
                  ppv[0],
                  a3,
                  LastIDReferense,
                  String,
                  0,
                  0);
          v17 = ppv[0];
          v6 = v18 == 0;
        }
        (*(void (__fastcall **)(void *))(*(_QWORD *)v17 + 16LL))(v17);
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180010728  push    rbx
0x18001072a  push    rbp
0x18001072b  push    rsi
0x18001072c  push    rdi
0x18001072d  push    r14
0x18001072f  sub     rsp, 480h
0x180010736  mov     rax, cs:__security_cookie
0x18001073d  xor     rax, rsp
0x180010740  mov     [rsp+4A8h+var_38], rax
0x180010748  mov     rbx, [rsp+4A8h+arg_20]
0x180010750  mov     rsi, rdx
0x180010753  mov     ebp, 1
0x180010758  mov     rcx, rsi; hDlg
0x18001075b  mov     rdi, r9
0x18001075e  mov     r14, r8
0x180010761  lea     edx, [rbp+6Eh]; nIDDlgItem
0x180010764  call    cs:__imp_GetDlgItem
0x18001076a  mov     rcx, rax; hWnd
0x18001076d  call    cs:__imp_IsWindowVisible
0x180010773  test    eax, eax
0x180010775  jz      loc_1800108BD
0x18001077b  lea     r8, [rsp+4A8h+psz1]; unsigned __int16 *
0x180010783  mov     rdx, rbx; struct CFtpPidlList *
0x180010786  mov     rcx, rdi; struct CFtpFolder *
0x180010789  call    ?GetNameFromPidlList@@YAXPEAVCFtpFolder@@PEAVCFtpPidlList@@PEAGK@Z; GetNameFromPidlList(CFtpFolder *,CFtpPidlList *,ushort *,ulong)
0x18001078e  lea     edx, [rbp+6Eh]; nIDDlgItem
0x180010791  mov     rcx, rsi; hDlg
0x180010794  call    cs:__imp_GetDlgItem
0x18001079a  mov     r8d, 104h; nMaxCount
0x1800107a0  lea     rdx, [rsp+4A8h+String]; lpString
0x1800107a5  mov     rcx, rax; hWnd
0x1800107a8  call    cs:__imp_GetWindowTextW
0x1800107ae  lea     rdx, [rsp+4A8h+String]; psz2
0x1800107b3  lea     rcx, [rsp+4A8h+psz1]; psz1
0x1800107bb  call    cs:__imp_StrCmpW
0x1800107c1  test    eax, eax
0x1800107c3  jz      loc_1800108BD
0x1800107c9  mov     rax, [rbx+10h]
0x1800107cd  mov     [rsp+4A8h+var_468], 0
0x1800107d6  mov     rcx, [rax+10h]; hdpa
0x1800107da  cmp     dword ptr [rcx], 0
0x1800107dd  jnz     short loc_180010836
0x1800107df  mov     rcx, [rdi+30h]; pidl
0x1800107e3  xor     ebx, ebx
0x1800107e5  call    cs:__imp_ILClone
0x1800107eb  mov     rsi, rax
0x1800107ee  test    rax, rax
0x1800107f1  jz      short loc_180010867
0x1800107f3  mov     rcx, rax; pidl
0x1800107f6  call    cs:__imp_ILRemoveLastID
0x1800107fc  movsxd  rcx, dword ptr [rdi+40h]
0x180010800  add     rcx, [rdi+30h]; struct _ITEMIDLIST *
0x180010804  call    ?FtpID_GetLastIDReferense@@YAPEFBU_ITEMIDLIST@@PEFBU1@@Z; FtpID_GetLastIDReferense(_ITEMIDLIST const *)
0x180010809  mov     rbx, rax
0x18001080c  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x180010813  lea     rax, [rsp+4A8h+var_468]
0x180010818  xor     r8d, r8d; pbc
0x18001081b  mov     rdx, rsi; pidl
0x18001081e  mov     [rsp+4A8h+ppv], rax; ppv
0x180010823  xor     ecx, ecx; psf
0x180010825  call    cs:__imp_SHBindToObject
0x18001082b  mov     rcx, rsi; pidl
0x18001082e  call    cs:__imp_ILFree
0x180010834  jmp     short loc_180010867
0x180010836  test    rax, rax
0x180010839  jz      short loc_180010842
0x18001083b  xor     edx, edx; i
0x18001083d  call    DPA_GetPtr
0x180010842  mov     rcx, rax; struct _ITEMIDLIST *
0x180010845  call    ?FtpID_GetLastIDReferense@@YAPEFBU_ITEMIDLIST@@PEFBU1@@Z; FtpID_GetLastIDReferense(_ITEMIDLIST const *)
0x18001084a  mov     rbx, rax
0x18001084d  lea     r8, [rsp+4A8h+var_468]
0x180010852  mov     rax, [rdi]
0x180010855  lea     rdx, IID_IShellFolder
0x18001085c  mov     rcx, rdi
0x18001085f  mov     rax, [rax]
0x180010862  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010867  mov     r10, [rsp+4A8h+var_468]
0x18001086c  test    r10, r10
0x18001086f  jz      short loc_1800108BD
0x180010871  test    rbx, rbx
0x180010874  jz      short loc_1800108AE
0x180010876  mov     rax, [r10]
0x180010879  lea     r9, [rsp+4A8h+String]
0x18001087e  mov     [rsp+4A8h+var_480], 0
0x180010887  mov     r8, rbx
0x18001088a  mov     rdx, r14
0x18001088d  mov     dword ptr [rsp+4A8h+ppv], 0
0x180010895  mov     rcx, r10
0x180010898  mov     rax, [rax+60h]
0x18001089c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108a1  mov     r10, [rsp+4A8h+var_468]
0x1800108a6  xor     ebp, ebp
0x1800108a8  test    eax, eax
0x1800108aa  setz    bpl
0x1800108ae  mov     rcx, [r10]
0x1800108b1  mov     rax, [rcx+10h]
0x1800108b5  mov     rcx, r10
0x1800108b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108bd  mov     eax, ebp
0x1800108bf  mov     rcx, [rsp+4A8h+var_38]
0x1800108c7  xor     rcx, rsp; StackCookie
0x1800108ca  call    __security_check_cookie
0x1800108cf  add     rsp, 480h
0x1800108d6  pop     r14
0x1800108d8  pop     rdi
0x1800108d9  pop     rsi
0x1800108da  pop     rbp
0x1800108db  pop     rbx
0x1800108dc  retn
```
