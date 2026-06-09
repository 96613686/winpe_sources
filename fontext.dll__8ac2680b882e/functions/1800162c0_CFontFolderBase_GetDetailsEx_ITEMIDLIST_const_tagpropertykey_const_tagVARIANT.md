# CFontFolderBase::GetDetailsEx(_ITEMIDLIST const *,_tagpropertykey const *,tagVARIANT *)

- ea: `0x1800162c0`
- end: `0x1800164b4`
- name: `?GetDetailsEx@CFontFolderBase@@UEAAJPEFBU_ITEMIDLIST@@PEBU_tagpropertykey@@PEAUtagVARIANT@@@Z`
- size: `500`
- prototype: `int(CFontFolderBase *__hidden this, const struct _ITEMIDLIST *, const struct _tagpropertykey *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x1800162c0`
- `0x1800167b8`
- `0x180016b7c`
- `0x1800225ac`
- `0x18002265c`
- `0x180022810`
- `0x18003104a`
- `0x180031070`

## import_xrefs

- `SHLWAPI!PathStripPathW` at `0x180016470`
- `SHLWAPI!PathStripPathW` at `0x180016470`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800163ba`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800163ba`

## pseudocode

```c
int __fastcall CFontFolderBase::GetDetailsEx(
        CFontFolderBase *this,
        const struct _ITEMIDLIST *a2,
        const struct _tagpropertykey *a3,
        struct tagVARIANT *a4)
{
  DWORD pid; // edx
  __int64 v7; // rcx
  WCHAR *v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  unsigned int ActivationStatus; // ebx
  int result; // eax
  __int64 v13; // rcx
  __int64 v14; // rcx
  WCHAR Buffer[32]; // [rsp+20h] [rbp-268h] BYREF
  WCHAR pszPath[264]; // [rsp+60h] [rbp-228h] BYREF

  pid = a3->pid;
  if ( pid == 3 )
  {
    v7 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_PropList_TileInfo.fmtid.Data1;
    if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_PropList_TileInfo.fmtid.Data1 )
      v7 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_PropList_TileInfo.fmtid.Data4;
    if ( !v7 )
    {
      v8 = L"prop:System.Fonts.Styles;System.Fonts.ActiveStatus";
      return InitVariantFromString(v8, a4);
    }
  }
  else
  {
    if ( pid == 2 )
    {
      v9 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_PropList_FullDetails.fmtid.Data1;
      if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_PropList_FullDetails.fmtid.Data1 )
        v9 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_PropList_FullDetails.fmtid.Data4;
    }
    else
    {
      if ( pid != 8 )
        goto LABEL_14;
      v9 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_PropList_PreviewDetails.fmtid.Data1;
      if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_PropList_PreviewDetails.fmtid.Data1 )
        v9 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_PropList_PreviewDetails.fmtid.Data4;
    }
    if ( !v9 )
    {
      v8 = L"prop:System.Fonts.Styles;System.Fonts.ActiveStatus;System.Fonts.DesignedFor;System.Fonts.Category;System.Font"
            "s.Vendors;System.Fonts.FontEmbeddability";
      return InitVariantFromString(v8, a4);
    }
  }
LABEL_14:
  if ( pid == 100 )
  {
    v10 = *(_QWORD *)&a3->fmtid.Data1 - PKEY_Fonts_ActiveStatus;
    if ( *(_QWORD *)&a3->fmtid.Data1 == PKEY_Fonts_ActiveStatus )
      v10 = *(_QWORD *)a3->fmtid.Data4 - 0x1C896BA9B4F0B8BCLL;
    if ( !v10 )
    {
      ActivationStatus = FID_GetActivationStatus(a2);
      memset_0(Buffer, 0, sizeof(Buffer));
      if ( !LoadStringW(g_hInstance, ActivationStatus + 7000, Buffer, 32) )
        return -2147467259;
LABEL_19:
      v8 = Buffer;
      return InitVariantFromString(v8, a4);
    }
  }
  if ( pid == 100 )
  {
    v13 = *(_QWORD *)&a3->fmtid.Data1 - PKEY_Fonts_FamilyName;
    if ( *(_QWORD *)&a3->fmtid.Data1 == PKEY_Fonts_FamilyName )
      v13 = *(_QWORD *)a3->fmtid.Data4 + 0xE11CE1D76C29475LL;
    if ( !v13 )
    {
      memset_0(Buffer, 0, sizeof(Buffer));
      result = FID_FamilyName(a2, Buffer);
      if ( result < 0 )
        return result;
      goto LABEL_19;
    }
  }
  if ( pid == 100 )
  {
    v14 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_FileName.fmtid.Data1;
    if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_FileName.fmtid.Data1 )
      v14 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_FileName.fmtid.Data4;
    if ( !v14 )
    {
      memset_0(pszPath, 0, 0x208u);
      result = FID_FileName(a2, 0, pszPath);
      if ( result < 0 )
        return result;
      PathStripPathW(pszPath);
      v8 = pszPath;
      return InitVariantFromString(v8, a4);
    }
  }
  return CItemIDFactory<FID,156830041>::GetPropertyFromIDList(&a2->mkid.cb, (__int64)a3, a4);
}

```

## disassembly

```asm
0x1800162c0  mov     [rsp+arg_0], rbx
0x1800162c5  push    rdi
0x1800162c6  sub     rsp, 280h
0x1800162cd  mov     rax, cs:__security_cookie
0x1800162d4  xor     rax, rsp
0x1800162d7  mov     [rsp+288h+var_18], rax
0x1800162df  mov     rbx, rdx
0x1800162e2  mov     rdi, r9
0x1800162e5  mov     edx, [r8+10h]
0x1800162e9  mov     rax, r8
0x1800162ec  cmp     edx, 3
0x1800162ef  jnz     short loc_180016319
0x1800162f1  mov     rcx, [r8]
0x1800162f4  sub     rcx, qword ptr cs:PKEY_PropList_TileInfo.fmtid.Data1
0x1800162fb  jnz     short loc_180016308
0x1800162fd  mov     rcx, [r8+8]
0x180016301  sub     rcx, qword ptr cs:PKEY_PropList_TileInfo.fmtid.Data4
0x180016308  test    rcx, rcx
0x18001630b  jnz     short loc_180016364
0x18001630d  lea     rcx, aPropSystemFont; "prop:System.Fonts.Styles;System.Fonts.A"...
0x180016314  jmp     loc_18001647B
0x180016319  cmp     edx, 2
0x18001631c  jnz     short loc_180016346
0x18001631e  mov     rcx, [r8]
0x180016321  sub     rcx, qword ptr cs:PKEY_PropList_FullDetails.fmtid.Data1
0x180016328  jnz     short loc_180016335
0x18001632a  mov     rcx, [r8+8]
0x18001632e  sub     rcx, qword ptr cs:PKEY_PropList_FullDetails.fmtid.Data4
0x180016335  test    rcx, rcx
0x180016338  jnz     short loc_180016364
0x18001633a  lea     rcx, aPropSystemFont_0; "prop:System.Fonts.Styles;System.Fonts.A"...
0x180016341  jmp     loc_18001647B
0x180016346  cmp     edx, 8
0x180016349  jnz     short loc_180016364
0x18001634b  mov     rcx, [r8]
0x18001634e  sub     rcx, qword ptr cs:PKEY_PropList_PreviewDetails.fmtid.Data1
0x180016355  jnz     short loc_180016335
0x180016357  mov     rcx, [r8+8]
0x18001635b  sub     rcx, qword ptr cs:PKEY_PropList_PreviewDetails.fmtid.Data4
0x180016362  jmp     short loc_180016335
0x180016364  cmp     edx, cs:dword_180037350
0x18001636a  jnz     short loc_1800163D8
0x18001636c  mov     rcx, [r8]
0x18001636f  sub     rcx, cs:PKEY_Fonts_ActiveStatus
0x180016376  jnz     short loc_180016383
0x180016378  mov     rcx, [r8+8]
0x18001637c  sub     rcx, cs:qword_180037348
0x180016383  test    rcx, rcx
0x180016386  jnz     short loc_1800163D8
0x180016388  mov     rcx, rbx; struct _ITEMIDLIST *
0x18001638b  call    ?FID_GetActivationStatus@@YAKPEFBU_ITEMIDLIST@@@Z; FID_GetActivationStatus(_ITEMIDLIST const *)
0x180016390  xor     edx, edx; Val
0x180016392  lea     rcx, [rsp+288h+Buffer]; void *
0x180016397  mov     ebx, eax
0x180016399  lea     r8d, [rdx+40h]; Size
0x18001639d  call    memset_0
0x1800163a2  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x1800163a9  lea     edx, [rbx+1B58h]; uID
0x1800163af  mov     r9d, 20h ; ' '; cchBufferMax
0x1800163b5  lea     r8, [rsp+288h+Buffer]; lpBuffer
0x1800163ba  call    cs:__imp_LoadStringW
0x1800163c0  test    eax, eax
0x1800163c2  jz      short loc_1800163CE
0x1800163c4  lea     rcx, [rsp+288h+Buffer]
0x1800163c9  jmp     loc_18001647B
0x1800163ce  mov     eax, 80004005h
0x1800163d3  jmp     loc_180016493
0x1800163d8  cmp     edx, cs:dword_1800373B0
0x1800163de  jnz     short loc_180016425
0x1800163e0  mov     rcx, [r8]
0x1800163e3  sub     rcx, cs:PKEY_Fonts_FamilyName
0x1800163ea  jnz     short loc_1800163F7
0x1800163ec  mov     rcx, [r8+8]
0x1800163f0  sub     rcx, cs:qword_1800373A8
0x1800163f7  test    rcx, rcx
0x1800163fa  jnz     short loc_180016425
0x1800163fc  lea     r8d, [rcx+40h]; Size
0x180016400  xor     edx, edx; Val
0x180016402  lea     rcx, [rsp+288h+Buffer]; void *
0x180016407  call    memset_0
0x18001640c  mov     r8d, 20h ; ' '; unsigned __int64
0x180016412  lea     rdx, [rsp+288h+Buffer]; unsigned __int16 *
0x180016417  mov     rcx, rbx; struct _ITEMIDLIST *
0x18001641a  call    ?FID_FamilyName@@YAJPEFBU_ITEMIDLIST@@PEAG_K@Z; FID_FamilyName(_ITEMIDLIST const *,ushort *,unsigned __int64)
0x18001641f  test    eax, eax
0x180016421  js      short loc_180016493
0x180016423  jmp     short loc_1800163C4
0x180016425  cmp     edx, 64h ; 'd'
0x180016428  jnz     short loc_180016485
0x18001642a  mov     rcx, [r8]
0x18001642d  sub     rcx, qword ptr cs:PKEY_FileName.fmtid.Data1
0x180016434  jnz     short loc_180016441
0x180016436  mov     rcx, [r8+8]
0x18001643a  sub     rcx, qword ptr cs:PKEY_FileName.fmtid.Data4
0x180016441  test    rcx, rcx
0x180016444  jnz     short loc_180016485
0x180016446  xor     edx, edx; Val
0x180016448  lea     rcx, [rsp+288h+pszPath]; void *
0x18001644d  mov     r8d, 208h; Size
0x180016453  call    memset_0
0x180016458  lea     r8, [rsp+288h+pszPath]; unsigned __int16 *
0x18001645d  xor     edx, edx; unsigned int
0x18001645f  mov     rcx, rbx; struct _ITEMIDLIST *
0x180016462  call    ?FID_FileName@@YAJPEFBU_ITEMIDLIST@@IPEAGI@Z; FID_FileName(_ITEMIDLIST const *,uint,ushort *,uint)
0x180016467  test    eax, eax
0x180016469  js      short loc_180016493
0x18001646b  lea     rcx, [rsp+288h+pszPath]; pszPath
0x180016470  call    cs:__imp_PathStripPathW
0x180016476  lea     rcx, [rsp+288h+pszPath]; unsigned __int16 *
0x18001647b  mov     rdx, rdi; struct tagVARIANT *
0x18001647e  call    ?InitVariantFromString@@YAJPEBGPEAUtagVARIANT@@@Z; InitVariantFromString(ushort const *,tagVARIANT *)
0x180016483  jmp     short loc_180016493
0x180016485  mov     r8, rdi
0x180016488  mov     rdx, rax
0x18001648b  mov     rcx, rbx
0x18001648e  call    ?GetPropertyFromIDList@?$CItemIDFactory@UFID@@$0JFJAJFJ@@@SAJPEFBU_ITEMIDLIST@@AEBU_tagpropertykey@@PEAUtagVARIANT@@@Z; CItemIDFactory<FID,156830041>::GetPropertyFromIDList(_ITEMIDLIST const *,_tagpropertykey const &,tagVARIANT *)
0x180016493  mov     rcx, [rsp+288h+var_18]
0x18001649b  xor     rcx, rsp; StackCookie
0x18001649e  call    __security_check_cookie
0x1800164a3  mov     rbx, [rsp+288h+arg_0]
0x1800164ab  add     rsp, 280h
0x1800164b2  pop     rdi
0x1800164b3  retn
```
