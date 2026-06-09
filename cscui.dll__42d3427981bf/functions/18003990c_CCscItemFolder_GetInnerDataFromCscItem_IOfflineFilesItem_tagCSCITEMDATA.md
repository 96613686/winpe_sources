# CCscItemFolder::_GetInnerDataFromCscItem(IOfflineFilesItem *,tagCSCITEMDATA *)

- ea: `0x18003990c`
- end: `0x180039bc5`
- name: `?_GetInnerDataFromCscItem@CCscItemFolder@@AEAAJPEAUIOfflineFilesItem@@PEAUtagCSCITEMDATA@@@Z`
- size: `697`
- prototype: `__int64 __fastcall(CCscItemFolder *__hidden this, struct IOfflineFilesItem *, struct tagCSCITEMDATA *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800373e8`

## callees

- `0x180003d60`
- `0x180032a30`
- `0x180038a98`
- `0x18003990c`
- `0x18004c636`
- `0x18004c670`
- `0x18004d010`

## import_xrefs

- `SHELL32!__imp_ILFree` at `0x180039b8b`
- `SHELL32!__imp_ILFree` at `0x180039b8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039b96`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039b96`

## pseudocode

```c
__int64 __fastcall CCscItemFolder::_GetInnerDataFromCscItem(
        CCscItemFolder *this,
        struct IOfflineFilesItem *a2,
        struct tagCSCITEMDATA *a3)
{
  struct IOfflineFilesItemVtbl *lpVtbl; // rax
  int v6; // ebx
  struct IOfflineFilesItemVtbl *v7; // rax
  int v8; // eax
  __int64 v9; // rcx
  struct IOfflineFilesItemVtbl *v10; // rax
  IBindCtx *v11; // rcx
  struct _WIN32_FIND_DATAW *v12; // r8
  bool v13; // zf
  const unsigned __int16 *FileName; // rax
  int v15; // eax
  void *v17; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v18; // [rsp+48h] [rbp-B8h] BYREF
  int v19; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-A8h] BYREF
  struct _ITEMID_CHILD *v21; // [rsp+60h] [rbp-A0h] BYREF
  LPITEMIDLIST pidl; // [rsp+68h] [rbp-98h] BYREF
  struct _WIN32_FIND_DATAW v23; // [rsp+70h] [rbp-90h] BYREF

  lpVtbl = a2->lpVtbl;
  v19 = 0;
  v6 = ((__int64 (__fastcall *)(struct IOfflineFilesItem *, int *))lpVtbl->GetItemType)(a2, &v19);
  if ( v6 < 0 )
    return (unsigned int)v6;
  *(_DWORD *)a3 = v19;
  v7 = a2->lpVtbl;
  v18 = 0;
  v8 = ((__int64 (__fastcall *)(struct IOfflineFilesItem *, GUID *, __int64 *))v7->QueryInterface)(
         a2,
         &GUID_bc1a163f_7bfd_4d88_9c66_96ea9a6a3d6b,
         &v18);
  v6 = v8;
  if ( v8 < 0 )
  {
    if ( v8 != -2147467262 )
      return (unsigned int)v6;
LABEL_10:
    v10 = a2->lpVtbl;
    pv = 0;
    v6 = ((__int64 (__fastcall *)(struct IOfflineFilesItem *, LPVOID *))v10->GetPath)(a2, &pv);
    if ( v6 < 0 )
      return (unsigned int)v6;
    memset_0(&v23, 0, sizeof(v23));
    if ( !*(_DWORD *)a3 || (v12 = 0, *(_DWORD *)a3 == 1) )
    {
      v13 = *(_DWORD *)a3 == 3;
      v23.dwFileAttributes = *((_DWORD *)a3 + 2);
      v23.nFileSizeLow = *((_DWORD *)a3 + 3);
      v23.nFileSizeHigh = *((_DWORD *)a3 + 4);
      v23.ftLastWriteTime = *(FILETIME *)((char *)a3 + 20);
      if ( v13 )
        FileName = (const unsigned __int16 *)pv;
      else
        FileName = CscPath_FindFileName((PCWSTR)pv);
      v6 = StringCchCopyW(v23.cFileName, 0x104u, FileName);
      if ( v6 < 0 )
      {
LABEL_23:
        CoTaskMemFree(pv);
        return (unsigned int)v6;
      }
      v12 = &v23;
    }
    v17 = 0;
    pidl = 0;
    v21 = 0;
    v6 = CCscItemFolder::_BindToUncPath(
           v11,
           (const unsigned __int16 *)pv,
           v12,
           &GUID_000214e6_0000_0000_c000_000000000046,
           &v17,
           &pidl,
           (LPCITEMIDLIST *)&v21);
    if ( v6 >= 0 )
    {
      LODWORD(v18) = 1684791297;
      v6 = (*(__int64 (__fastcall **)(void *, __int64, struct _ITEMID_CHILD **, __int64 *))(*(_QWORD *)v17 + 72LL))(
             v17,
             1,
             &v21,
             &v18);
      if ( v6 >= 0 )
      {
        v15 = v18;
        *((_DWORD *)a3 + 1) = v18;
        if ( v19 )
          *((_DWORD *)a3 + 1) = v15 | 0x20000000;
      }
      (*(void (__fastcall **)(void *))(*(_QWORD *)v17 + 16LL))(v17);
      ILFree(pidl);
    }
    goto LABEL_23;
  }
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)v18 + 24LL))(v18, 0, (char *)a3 + 8);
  if ( v6 >= 0 )
  {
    pv = 0;
    v21 = 0;
    pidl = 0;
    v17 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, LPVOID *, void **, struct _ITEMID_CHILD **, LPITEMIDLIST *))(*(_QWORD *)v18 + 32LL))(
           v18,
           0,
           &pv,
           &v17,
           &v21,
           &pidl);
    if ( v6 >= 0 )
    {
      v9 = v18;
      *(_QWORD *)((char *)a3 + 20) = v17;
      v17 = 0;
      v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, void **))(*(_QWORD *)v9 + 40LL))(v9, 0, &v17);
      if ( v6 >= 0 )
        *(_QWORD *)((char *)a3 + 12) = v17;
    }
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  if ( v6 >= 0 )
    goto LABEL_10;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003990c  mov     [rsp-8+arg_0], rbx
0x180039911  mov     [rsp-8+arg_18], rsi
0x180039916  push    rbp
0x180039917  push    rdi
0x180039918  push    r14
0x18003991a  lea     rbp, [rsp-1D0h]
0x180039922  sub     rsp, 2D0h
0x180039929  mov     rax, cs:__security_cookie
0x180039930  xor     rax, rsp
0x180039933  mov     [rbp+1E0h+var_20], rax
0x18003993a  mov     rax, [rdx]
0x18003993d  mov     rsi, rdx
0x180039940  xor     r14d, r14d
0x180039943  lea     rdx, [rsp+2E0h+var_290]
0x180039948  mov     rcx, rsi
0x18003994b  mov     [rsp+2E0h+var_290], r14d
0x180039950  mov     rdi, r8
0x180039953  mov     rax, [rax+18h]
0x180039957  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003995c  mov     ebx, eax
0x18003995e  test    eax, eax
0x180039960  js      loc_180039B9C
0x180039966  mov     eax, [rsp+2E0h+var_290]
0x18003996a  lea     r8, [rsp+2E0h+var_298]
0x18003996f  mov     [rdi], eax
0x180039971  lea     rdx, _GUID_bc1a163f_7bfd_4d88_9c66_96ea9a6a3d6b
0x180039978  mov     rax, [rsi]
0x18003997b  mov     rcx, rsi
0x18003997e  mov     [rsp+2E0h+var_298], r14
0x180039983  mov     rax, [rax]
0x180039986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003998b  mov     ebx, eax
0x18003998d  test    eax, eax
0x18003998f  js      loc_180039A50
0x180039995  mov     rcx, [rsp+2E0h+var_298]
0x18003999a  lea     r8, [rdi+8]
0x18003999e  xor     edx, edx
0x1800399a0  mov     rax, [rcx]
0x1800399a3  mov     rax, [rax+18h]
0x1800399a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800399ac  mov     ebx, eax
0x1800399ae  test    eax, eax
0x1800399b0  js      loc_180039A36
0x1800399b6  mov     rcx, [rsp+2E0h+var_298]
0x1800399bb  lea     rdx, [rsp+2E0h+pidl]
0x1800399c0  mov     [rsp+2E0h+var_2B8], rdx
0x1800399c5  lea     r9, [rsp+2E0h+var_2A0]
0x1800399ca  lea     rdx, [rsp+2E0h+var_280]
0x1800399cf  mov     [rsp+2E0h+pv], r14
0x1800399d4  mov     [rsp+2E0h+var_280], r14
0x1800399d9  lea     r8, [rsp+2E0h+pv]
0x1800399de  mov     [rsp+2E0h+pidl], r14
0x1800399e3  mov     [rsp+2E0h+var_2A0], r14
0x1800399e8  mov     rax, [rcx]
0x1800399eb  mov     [rsp+2E0h+var_2C0], rdx
0x1800399f0  xor     edx, edx
0x1800399f2  mov     rax, [rax+20h]
0x1800399f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800399fb  mov     ebx, eax
0x1800399fd  test    eax, eax
0x1800399ff  js      short loc_180039A36
0x180039a01  mov     rax, [rsp+2E0h+var_2A0]
0x180039a06  lea     r8, [rsp+2E0h+var_2A0]
0x180039a0b  mov     rcx, [rsp+2E0h+var_298]
0x180039a10  xor     edx, edx
0x180039a12  mov     [rdi+14h], rax
0x180039a16  mov     [rsp+2E0h+var_2A0], r14
0x180039a1b  mov     rax, [rcx]
0x180039a1e  mov     rax, [rax+28h]
0x180039a22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039a27  mov     ebx, eax
0x180039a29  test    eax, eax
0x180039a2b  js      short loc_180039A36
0x180039a2d  mov     rax, [rsp+2E0h+var_2A0]
0x180039a32  mov     [rdi+0Ch], rax
0x180039a36  mov     rcx, [rsp+2E0h+var_298]
0x180039a3b  mov     rax, [rcx]
0x180039a3e  mov     rax, [rax+10h]
0x180039a42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039a47  test    ebx, ebx
0x180039a49  jns     short loc_180039A5B
0x180039a4b  jmp     loc_180039B9C
0x180039a50  cmp     eax, 80004002h
0x180039a55  jnz     loc_180039B9C
0x180039a5b  mov     rax, [rsi]
0x180039a5e  lea     rdx, [rsp+2E0h+pv]
0x180039a63  mov     rcx, rsi
0x180039a66  mov     [rsp+2E0h+pv], r14
0x180039a6b  mov     rax, [rax+20h]
0x180039a6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039a74  mov     ebx, eax
0x180039a76  test    eax, eax
0x180039a78  js      loc_180039B9C
0x180039a7e  xor     edx, edx; Val
0x180039a80  lea     rcx, [rsp+2E0h+var_270]; void *
0x180039a85  mov     r8d, 250h; Size
0x180039a8b  call    memset_0
0x180039a90  cmp     [rdi], r14d
0x180039a93  jz      short loc_180039A9D
0x180039a95  cmp     dword ptr [rdi], 1
0x180039a98  mov     r8, r14
0x180039a9b  jnz     short loc_180039AEE
0x180039a9d  cmp     dword ptr [rdi], 3
0x180039aa0  mov     eax, [rdi+8]
0x180039aa3  mov     [rsp+2E0h+var_270.dwFileAttributes], eax
0x180039aa7  mov     eax, [rdi+0Ch]
0x180039aaa  mov     [rbp+1E0h+var_270.nFileSizeLow], eax
0x180039aad  mov     eax, [rdi+10h]
0x180039ab0  mov     [rbp+1E0h+var_270.nFileSizeHigh], eax
0x180039ab3  mov     rax, [rdi+14h]
0x180039ab7  mov     qword ptr [rbp+1E0h+var_270.ftLastWriteTime.dwLowDateTime], rax
0x180039abb  jnz     short loc_180039AC4
0x180039abd  mov     rax, [rsp+2E0h+pv]
0x180039ac2  jmp     short loc_180039ACE
0x180039ac4  mov     rcx, [rsp+2E0h+pv]; SourceString
0x180039ac9  call    ?CscPath_FindFileName@@YAPEBGPEBG@Z; CscPath_FindFileName(ushort const *)
0x180039ace  mov     r8, rax; unsigned __int16 *
0x180039ad1  lea     rcx, [rbp+1E0h+var_270.cFileName]; unsigned __int16 *
0x180039ad5  mov     edx, 104h; unsigned __int64
0x180039ada  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180039adf  mov     ebx, eax
0x180039ae1  test    eax, eax
0x180039ae3  js      loc_180039B91
0x180039ae9  lea     r8, [rsp+2E0h+var_270]; struct _WIN32_FIND_DATAW *
0x180039aee  mov     rdx, [rsp+2E0h+pv]; unsigned __int16 *
0x180039af3  lea     rax, [rsp+2E0h+var_280]
0x180039af8  mov     [rsp+2E0h+var_2B0], rax; struct _ITEMID_CHILD **
0x180039afd  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046; struct _GUID *
0x180039b04  lea     rax, [rsp+2E0h+pidl]
0x180039b09  mov     [rsp+2E0h+var_2A0], r14
0x180039b0e  mov     [rsp+2E0h+var_2B8], rax; struct _ITEMIDLIST_ABSOLUTE **
0x180039b13  lea     rax, [rsp+2E0h+var_2A0]
0x180039b18  mov     [rsp+2E0h+var_2C0], rax; void **
0x180039b1d  mov     [rsp+2E0h+pidl], r14
0x180039b22  mov     [rsp+2E0h+var_280], r14
0x180039b27  call    ?_BindToUncPath@CCscItemFolder@@AEAAJPEBGPEBU_WIN32_FIND_DATAW@@AEBU_GUID@@PEAPEAXPEAPEAU_ITEMIDLIST_ABSOLUTE@@PEAPEFBU_ITEMID_CHILD@@@Z; CCscItemFolder::_BindToUncPath(ushort const *,_WIN32_FIND_DATAW const *,_GUID const &,void * *,_ITEMIDLIST_ABSOLUTE * *,_ITEMID_CHILD const * *)
0x180039b2c  mov     ebx, eax
0x180039b2e  test    eax, eax
0x180039b30  js      short loc_180039B91
0x180039b32  mov     rcx, [rsp+2E0h+var_2A0]
0x180039b37  lea     r9, [rsp+2E0h+var_298]
0x180039b3c  mov     dword ptr [rsp+2E0h+var_298], 646BE001h
0x180039b44  lea     r8, [rsp+2E0h+var_280]
0x180039b49  mov     edx, 1
0x180039b4e  mov     rax, [rcx]
0x180039b51  mov     rax, [rax+48h]
0x180039b55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039b5a  mov     ebx, eax
0x180039b5c  test    eax, eax
0x180039b5e  js      short loc_180039B75
0x180039b60  mov     eax, dword ptr [rsp+2E0h+var_298]
0x180039b64  mov     [rdi+4], eax
0x180039b67  cmp     [rsp+2E0h+var_290], r14d
0x180039b6c  jz      short loc_180039B75
0x180039b6e  bts     eax, 1Dh
0x180039b72  mov     [rdi+4], eax
0x180039b75  mov     rcx, [rsp+2E0h+var_2A0]
0x180039b7a  mov     rax, [rcx]
0x180039b7d  mov     rax, [rax+10h]
0x180039b81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039b86  mov     rcx, [rsp+2E0h+pidl]; pidl
0x180039b8b  call    cs:__imp_ILFree
0x180039b91  mov     rcx, [rsp+2E0h+pv]; pv
0x180039b96  call    cs:__imp_CoTaskMemFree
0x180039b9c  mov     eax, ebx
0x180039b9e  mov     rcx, [rbp+1E0h+var_20]
0x180039ba5  xor     rcx, rsp; StackCookie
0x180039ba8  call    __security_check_cookie
0x180039bad  lea     r11, [rsp+2E0h+var_10]
0x180039bb5  mov     rbx, [r11+20h]
0x180039bb9  mov     rsi, [r11+38h]
0x180039bbd  mov     rsp, r11
0x180039bc0  pop     r14
0x180039bc2  pop     rdi
0x180039bc3  pop     rbp
0x180039bc4  retn
```
