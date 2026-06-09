# CCabFolder::GetUIObjectOf(HWND__ *,uint,_ITEMIDLIST const * *,_GUID const &,uint *,void * *)

- ea: `0x18000e910`
- end: `0x18000eb93`
- name: `?GetUIObjectOf@CCabFolder@@UEAAJPEAUHWND__@@IPEAPEFBU_ITEMIDLIST@@AEBU_GUID@@PEAIPEAPEAX@Z`
- size: `643`
- prototype: `int(CCabFolder *__hidden this, HWND, unsigned int, const struct _ITEMIDLIST **, const struct _GUID *, unsigned int *, void **)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180002620`
- `0x18000acec`
- `0x18000d3b0`
- `0x18000e910`
- `0x180011e00`
- `0x180012a74`
- `0x180013010`

## import_xrefs

- `SHELL32!__imp_SHCreateFileExtractIconW` at `0x18000e999`
- `SHELL32!__imp_SHCreateFileExtractIconW` at `0x18000e999`
- `SHLWAPI!PathFindExtensionW` at `0x18000eb14`
- `SHLWAPI!PathFindExtensionW` at `0x18000eb14`
- `SHLWAPI!AssocCreate` at `0x18000eaf8`
- `SHLWAPI!AssocCreate` at `0x18000eaf8`
- `SHLWAPI!PathFindFileNameW` at `0x18000e988`
- `SHLWAPI!PathFindFileNameW` at `0x18000e988`

## pseudocode

```c
__int64 __fastcall CCabFolder::GetUIObjectOf(
        CCabFolder *this,
        HWND a2,
        unsigned int a3,
        const struct _ITEMIDLIST **a4,
        const struct _GUID *Buf1,
        unsigned int *a6,
        void **ppv)
{
  DWORD cb; // ebx
  const WCHAR *FileNameW; // rax
  HRESULT v13; // ebx
  __int64 (__fastcall ***v14)(_QWORD, const struct _GUID *, void **); // rax
  __int64 (__fastcall ***v15)(_QWORD, const struct _GUID *, void **); // rbp
  void *v16; // rcx
  __int64 (__fastcall **v17)(_QWORD, _QWORD, _QWORD); // rax
  CCabObj *v18; // rax
  CCabObj *v19; // rax
  CCabObj *v20; // rsi
  struct _CABITEM *v21; // rsi
  __int64 (__fastcall *v22)(void *, __int64, LPWSTR); // rbx
  LPWSTR ExtensionW; // rax
  CLSID clsid; // [rsp+30h] [rbp-68h] BYREF
  void *v26; // [rsp+40h] [rbp-58h] BYREF

  *ppv = 0;
  if ( !a3 )
    return (unsigned int)-2147024809;
  if ( !memcmp_0(Buf1, &IID_IExtractIconW, 0x10u) )
  {
    if ( a3 == 1 )
    {
      cb = (*a4)[4].mkid.cb;
      FileNameW = PathFindFileNameW((LPCWSTR)((char *)&(*a4)[5].mkid.cb + 1));
      return (unsigned int)SHCreateFileExtractIconW(FileNameW, cb, Buf1, ppv);
    }
    return (unsigned int)-2147024809;
  }
  if ( !memcmp_0(Buf1, &IID_IContextMenu, 0x10u) )
  {
    v13 = -2147024882;
    v14 = (__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **))operator new(0x30u);
    v15 = v14;
    if ( !v14 )
      return (unsigned int)v13;
    *((_DWORD *)v14 + 2) = 1;
    *v14 = (__int64 (__fastcall **)(_QWORD, const struct _GUID *, void **))&CCabItemMenu::`vftable';
    *((_DWORD *)v14 + 8) = 8;
    _InterlockedIncrement(&g_cRefThisDll);
    v14[2] = (__int64 (__fastcall **)(_QWORD, const struct _GUID *, void **))a2;
    v14[3] = (__int64 (__fastcall **)(_QWORD, const struct _GUID *, void **))((char *)this - 8);
    (*(void (__fastcall **)(char *))(*((_QWORD *)this - 1) + 8LL))((char *)this - 8);
    CCabItemList::AddItems((CCabItemList *)(v15 + 4), (struct _CABITEM **)a4, a3);
    v13 = (**v15)(v15, Buf1, ppv);
    v16 = v15;
    v17 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v15;
LABEL_17:
    ((void (__fastcall *)(void *))v17[2])(v16);
    return (unsigned int)v13;
  }
  if ( !memcmp_0(Buf1, &IID_IDataObject, 0x10u) )
  {
    v13 = -2147024882;
    v18 = (CCabObj *)operator new(0x268u);
    if ( v18 )
    {
      v19 = CCabObj::CCabObj(v18, a2, (CCabFolder *)((char *)this - 8), (struct _CABITEM **)a4, a3);
      v20 = v19;
      if ( v19 )
      {
        v13 = (**(__int64 (__fastcall ***)(CCabObj *, const struct _GUID *, void **))v19)(v19, Buf1, ppv);
        (*(void (__fastcall **)(CCabObj *))(*(_QWORD *)v20 + 16LL))(v20);
      }
    }
  }
  else
  {
    if ( memcmp_0(Buf1, &IID_IQueryAssociations, 0x10u) )
      return (unsigned int)-2147467262;
    v21 = (struct _CABITEM *)*a4;
    v26 = 0;
    clsid = CLSID_QueryAssociations;
    v13 = AssocCreate(&clsid, &GUID_c46ca590_3c3f_11d2_bee6_0000f805ca57, &v26);
    if ( v13 >= 0 )
    {
      v22 = *(__int64 (__fastcall **)(void *, __int64, LPWSTR))(*(_QWORD *)v26 + 24LL);
      ExtensionW = PathFindExtensionW((LPCWSTR)v21 + 8);
      v13 = v22(v26, 4, ExtensionW);
      if ( v13 >= 0 )
        v13 = (**(__int64 (__fastcall ***)(void *, const struct _GUID *, void **))v26)(v26, Buf1, ppv);
      v16 = v26;
      v17 = *(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v26;
      goto LABEL_17;
    }
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18000e910  push    rbx
0x18000e912  push    rbp
0x18000e913  push    rsi
0x18000e914  push    rdi
0x18000e915  push    r12
0x18000e917  push    r13
0x18000e919  push    r14
0x18000e91b  push    r15
0x18000e91d  sub     rsp, 58h
0x18000e921  mov     rax, cs:__security_cookie
0x18000e928  xor     rax, rsp
0x18000e92b  mov     [rsp+98h+var_50], rax
0x18000e930  mov     r14, [rsp+98h+ppv]
0x18000e938  xor     ebp, ebp
0x18000e93a  mov     rdi, [rsp+98h+Buf1]
0x18000e942  mov     r15, r9
0x18000e945  mov     esi, r8d
0x18000e948  mov     r12, rdx
0x18000e94b  mov     r13, rcx
0x18000e94e  mov     [r14], rbp
0x18000e951  cmp     r8d, 1
0x18000e955  jb      loc_18000EB6E
0x18000e95b  lea     ebx, [rbp+10h]
0x18000e95e  mov     rcx, rdi; Buf1
0x18000e961  mov     r8d, ebx; Size
0x18000e964  lea     rdx, IID_IExtractIconW; Buf2
0x18000e96b  call    memcmp_0
0x18000e970  test    eax, eax
0x18000e972  jnz     short loc_18000E9A6
0x18000e974  cmp     esi, 1
0x18000e977  jnz     loc_18000EB6E
0x18000e97d  mov     rcx, [r15]
0x18000e980  movzx   ebx, word ptr [rcx+0Ch]
0x18000e984  add     rcx, 10h; pszPath
0x18000e988  call    cs:__imp_PathFindFileNameW
0x18000e98e  mov     r9, r14; ppv
0x18000e991  mov     r8, rdi; riid
0x18000e994  mov     rcx, rax; pszFile
0x18000e997  mov     edx, ebx; dwFileAttributes
0x18000e999  call    cs:__imp_SHCreateFileExtractIconW
0x18000e99f  mov     ebx, eax
0x18000e9a1  jmp     loc_18000EB73
0x18000e9a6  mov     r8, rbx; Size
0x18000e9a9  lea     rdx, IID_IContextMenu; Buf2
0x18000e9b0  mov     rcx, rdi; Buf1
0x18000e9b3  call    memcmp_0
0x18000e9b8  test    eax, eax
0x18000e9ba  jnz     loc_18000EA43
0x18000e9c0  lea     ecx, [rax+30h]; unsigned __int64
0x18000e9c3  mov     ebx, 8007000Eh
0x18000e9c8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e9cd  mov     rbp, rax
0x18000e9d0  test    rax, rax
0x18000e9d3  jz      loc_18000EB73
0x18000e9d9  lea     rax, ??_7CCabItemMenu@@6B@; const CCabItemMenu::`vftable'
0x18000e9e0  mov     dword ptr [rbp+8], 1
0x18000e9e7  mov     [rbp+0], rax
0x18000e9eb  lea     rcx, [r13-8]
0x18000e9ef  mov     dword ptr [rbp+20h], 8
0x18000e9f6  lock inc cs:?g_cRefThisDll@@3JA; long g_cRefThisDll
0x18000e9fd  mov     [rbp+10h], r12
0x18000ea01  mov     [rbp+18h], rcx
0x18000ea05  mov     rdx, [rcx]
0x18000ea08  mov     rax, [rdx+8]
0x18000ea0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea11  mov     r8d, esi; unsigned int
0x18000ea14  lea     rcx, [rbp+20h]; this
0x18000ea18  mov     rdx, r15; struct _CABITEM **
0x18000ea1b  call    ?AddItems@CCabItemList@@QEAAHPEAPEFAU_CABITEM@@I@Z; CCabItemList::AddItems(_CABITEM * *,uint)
0x18000ea20  mov     rax, [rbp+0]
0x18000ea24  mov     r8, r14
0x18000ea27  mov     rdx, rdi
0x18000ea2a  mov     rcx, rbp
0x18000ea2d  mov     rax, [rax]
0x18000ea30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea35  mov     ebx, eax
0x18000ea37  mov     rcx, rbp
0x18000ea3a  mov     rax, [rbp+0]
0x18000ea3e  jmp     loc_18000EB5C
0x18000ea43  mov     r8, rbx; Size
0x18000ea46  lea     rdx, IID_IDataObject; Buf2
0x18000ea4d  mov     rcx, rdi; Buf1
0x18000ea50  call    memcmp_0
0x18000ea55  test    eax, eax
0x18000ea57  jnz     short loc_18000EAB8
0x18000ea59  mov     ecx, 268h; unsigned __int64
0x18000ea5e  mov     ebx, 8007000Eh
0x18000ea63  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ea68  test    rax, rax
0x18000ea6b  jz      loc_18000EB73
0x18000ea71  lea     r8, [r13-8]; struct CCabFolder *
0x18000ea75  mov     [rsp+98h+var_78], esi; unsigned int
0x18000ea79  mov     r9, r15; struct _CABITEM **
0x18000ea7c  mov     rdx, r12; HWND
0x18000ea7f  mov     rcx, rax; this
0x18000ea82  call    ??0CCabObj@@QEAA@PEAUHWND__@@PEAVCCabFolder@@PEAPEFAU_CABITEM@@I@Z; CCabObj::CCabObj(HWND__ *,CCabFolder *,_CABITEM * *,uint)
0x18000ea87  mov     rsi, rax
0x18000ea8a  test    rax, rax
0x18000ea8d  jz      loc_18000EB73
0x18000ea93  mov     rcx, [rax]
0x18000ea96  mov     r8, r14
0x18000ea99  mov     rdx, rdi
0x18000ea9c  mov     rax, [rcx]
0x18000ea9f  mov     rcx, rsi
0x18000eaa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eaa7  mov     rcx, [rsi]
0x18000eaaa  mov     ebx, eax
0x18000eaac  mov     rax, [rcx+10h]
0x18000eab0  mov     rcx, rsi
0x18000eab3  jmp     loc_18000EB60
0x18000eab8  mov     r8, rbx; Size
0x18000eabb  lea     rdx, IID_IQueryAssociations; Buf2
0x18000eac2  mov     rcx, rdi; Buf1
0x18000eac5  call    memcmp_0
0x18000eaca  test    eax, eax
0x18000eacc  jnz     loc_18000EB67
0x18000ead2  movups  xmm0, xmmword ptr cs:CLSID_QueryAssociations.Data1
0x18000ead9  mov     rsi, [r15]
0x18000eadc  lea     r8, [rsp+98h+var_58]; ppv
0x18000eae1  lea     rdx, _GUID_c46ca590_3c3f_11d2_bee6_0000f805ca57; riid
0x18000eae8  mov     [rsp+98h+var_58], rbp
0x18000eaed  lea     rcx, [rsp+98h+clsid]; clsid
0x18000eaf2  movdqu  xmmword ptr [rsp+98h+clsid.Data1], xmm0
0x18000eaf8  call    cs:__imp_AssocCreate
0x18000eafe  mov     ebx, eax
0x18000eb00  test    eax, eax
0x18000eb02  js      short loc_18000EB73
0x18000eb04  mov     rax, [rsp+98h+var_58]
0x18000eb09  mov     rcx, [rax]
0x18000eb0c  mov     rbx, [rcx+18h]
0x18000eb10  lea     rcx, [rsi+10h]; pszPath
0x18000eb14  call    cs:__imp_PathFindExtensionW
0x18000eb1a  mov     rcx, [rsp+98h+var_58]
0x18000eb1f  xor     r9d, r9d
0x18000eb22  mov     r8, rax
0x18000eb25  mov     qword ptr [rsp+98h+var_78], rbp
0x18000eb2a  mov     rax, rbx
0x18000eb2d  lea     edx, [r9+4]
0x18000eb31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb36  mov     ebx, eax
0x18000eb38  test    eax, eax
0x18000eb3a  js      short loc_18000EB54
0x18000eb3c  mov     rcx, [rsp+98h+var_58]
0x18000eb41  mov     r8, r14
0x18000eb44  mov     rdx, rdi
0x18000eb47  mov     rax, [rcx]
0x18000eb4a  mov     rax, [rax]
0x18000eb4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb52  mov     ebx, eax
0x18000eb54  mov     rcx, [rsp+98h+var_58]
0x18000eb59  mov     rax, [rcx]
0x18000eb5c  mov     rax, [rax+10h]
0x18000eb60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb65  jmp     short loc_18000EB73
0x18000eb67  mov     ebx, 80004002h
0x18000eb6c  jmp     short loc_18000EB73
0x18000eb6e  mov     ebx, 80070057h
0x18000eb73  mov     eax, ebx
0x18000eb75  mov     rcx, [rsp+98h+var_50]
0x18000eb7a  xor     rcx, rsp; StackCookie
0x18000eb7d  call    __security_check_cookie
0x18000eb82  add     rsp, 58h
0x18000eb86  pop     r15
0x18000eb88  pop     r14
0x18000eb8a  pop     r13
0x18000eb8c  pop     r12
0x18000eb8e  pop     rdi
0x18000eb8f  pop     rsi
0x18000eb90  pop     rbp
0x18000eb91  pop     rbx
0x18000eb92  retn
```
