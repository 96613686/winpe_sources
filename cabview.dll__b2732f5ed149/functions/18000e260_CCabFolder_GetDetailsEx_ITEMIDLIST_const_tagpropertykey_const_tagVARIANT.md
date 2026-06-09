# CCabFolder::GetDetailsEx(_ITEMIDLIST const *,_tagpropertykey const *,tagVARIANT *)

- ea: `0x18000e260`
- end: `0x18000e4ea`
- name: `?GetDetailsEx@CCabFolder@@UEAAJPEFBU_ITEMIDLIST@@PEBU_tagpropertykey@@PEAUtagVARIANT@@@Z`
- size: `650`
- prototype: `__int64 __fastcall(CCabFolder *__hidden this, const struct _ITEMIDLIST *, const struct _tagpropertykey *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting`

## callees

- `0x180002620`
- `0x18000e260`
- `0x18000e7a4`
- `0x18000e864`
- `0x18000ecb0`
- `0x18000f3c4`
- `0x18000f6a0`
- `0x18001245c`

## import_xrefs

- `SHELL32!AssocGetDetailsOfPropKey` at `0x18000e4c6`
- `SHELL32!AssocGetDetailsOfPropKey` at `0x18000e4c6`
- `SHLWAPI!PathFindExtensionW` at `0x18000e397`
- `SHLWAPI!PathFindExtensionW` at `0x18000e397`
- `api-ms-win-core-file-l1-1-0!LocalFileTimeToFileTime` at `0x18000e434`
- `api-ms-win-core-file-l1-1-0!LocalFileTimeToFileTime` at `0x18000e434`
- `KERNEL32!DosDateTimeToFileTime` at `0x18000e41c`
- `KERNEL32!DosDateTimeToFileTime` at `0x18000e41c`
- `PROPSYS!InitVariantFromFileTime` at `0x18000e44a`
- `PROPSYS!InitVariantFromFileTime` at `0x18000e44a`

## pseudocode

```c
__int64 __fastcall CCabFolder::GetDetailsEx(
        unsigned __int64 this,
        struct _ITEMIDLIST *a2,
        const struct _tagpropertykey *a3,
        struct tagVARIANT *a4)
{
  DWORD pid; // eax
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v11; // rax
  int v12; // ebx
  WCHAR *ExtensionW; // rcx
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  WORD v17; // dx
  WORD v18; // cx
  __int64 v19; // rax
  __int64 v20; // rax
  unsigned int *pfFoundPropKey; // [rsp+20h] [rbp-258h]
  struct _FILETIME FileTime; // [rsp+30h] [rbp-248h] BYREF
  FILETIME pft; // [rsp+38h] [rbp-240h] BYREF
  WCHAR pszPath[264]; // [rsp+40h] [rbp-238h] BYREF

  pid = a3->pid;
  if ( pid == 10 )
  {
    v8 = *(_QWORD *)&PKEY_ItemNameDisplay.fmtid.Data1 - *(_QWORD *)&a3->fmtid.Data1;
    if ( *(_QWORD *)&PKEY_ItemNameDisplay.fmtid.Data1 == *(_QWORD *)&a3->fmtid.Data1 )
      v8 = *(_QWORD *)PKEY_ItemNameDisplay.fmtid.Data4 - *(_QWORD *)a3->fmtid.Data4;
    if ( !v8 )
      return (unsigned int)GetNameDetails(this & -(__int64)(this != 8), a3, a2, a4);
  }
  switch ( pid )
  {
    case 0x18u:
      v9 = *(_QWORD *)&PKEY_ParsingName.fmtid.Data1 - *(_QWORD *)&a3->fmtid.Data1;
      if ( *(_QWORD *)&PKEY_ParsingName.fmtid.Data1 == *(_QWORD *)&a3->fmtid.Data1 )
        v9 = *(_QWORD *)PKEY_ParsingName.fmtid.Data4 - *(_QWORD *)a3->fmtid.Data4;
      if ( !v9 )
        return (unsigned int)GetNameDetails(this & -(__int64)(this != 8), a3, a2, a4);
      return (unsigned int)AssocGetDetailsOfPropKey((IShellFolder *)(this & -(__int64)(this != 8)), a2, a3, a4, 0);
    case 6u:
      v11 = *(_QWORD *)&PKEY_ItemFolderPathDisplay.fmtid.Data1 - *(_QWORD *)&a3->fmtid.Data1;
      if ( *(_QWORD *)&PKEY_ItemFolderPathDisplay.fmtid.Data1 == *(_QWORD *)&a3->fmtid.Data1 )
        v11 = *(_QWORD *)PKEY_ItemFolderPathDisplay.fmtid.Data4 - *(_QWORD *)a3->fmtid.Data4;
      if ( v11 )
        return (unsigned int)AssocGetDetailsOfPropKey((IShellFolder *)(this & -(__int64)(this != 8)), a2, a3, a4, 0);
      v12 = SHGetNameAndFlagsW(*(LPCITEMIDLIST *)(this + 40), 0x8000u, pszPath, this, pfFoundPropKey);
      if ( v12 >= 0 )
      {
        ExtensionW = pszPath;
        return (unsigned int)InitVariantFromString(ExtensionW, a4);
      }
      break;
    case 0xBu:
      v14 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_ItemType.fmtid.Data1;
      if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_ItemType.fmtid.Data1 )
        v14 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_ItemType.fmtid.Data4;
      if ( v14 )
        return (unsigned int)AssocGetDetailsOfPropKey((IShellFolder *)(this & -(__int64)(this != 8)), a2, a3, a4, 0);
      v12 = DisplayNameOfW(this & -(__int64)(this != 8), a2, 0x8000, pszPath);
      if ( v12 >= 0 )
      {
        ExtensionW = PathFindExtensionW(pszPath);
        return (unsigned int)InitVariantFromString(ExtensionW, a4);
      }
      break;
    case 0xCu:
      v15 = *(_QWORD *)&PKEY_Size.fmtid.Data1 - *(_QWORD *)&a3->fmtid.Data1;
      if ( *(_QWORD *)&PKEY_Size.fmtid.Data1 == *(_QWORD *)&a3->fmtid.Data1 )
        v15 = *(_QWORD *)PKEY_Size.fmtid.Data4 - *(_QWORD *)a3->fmtid.Data4;
      if ( v15 )
        return (unsigned int)AssocGetDetailsOfPropKey((IShellFolder *)(this & -(__int64)(this != 8)), a2, a3, a4, 0);
      v12 = 0;
      a4->llVal = *(unsigned int *)((char *)&a2[1].mkid.cb + 1);
      a4->vt = 21;
      break;
    case 0xEu:
      v16 = *(_QWORD *)&PKEY_DateModified.fmtid.Data1 - *(_QWORD *)&a3->fmtid.Data1;
      if ( *(_QWORD *)&PKEY_DateModified.fmtid.Data1 == *(_QWORD *)&a3->fmtid.Data1 )
        v16 = *(_QWORD *)PKEY_DateModified.fmtid.Data4 - *(_QWORD *)a3->fmtid.Data4;
      if ( v16 )
        return (unsigned int)AssocGetDetailsOfPropKey((IShellFolder *)(this & -(__int64)(this != 8)), a2, a3, a4, 0);
      v17 = *(USHORT *)((char *)&a2[3].mkid.cb + 1);
      v18 = *(_WORD *)a2[2].mkid.abID;
      v12 = -2147467259;
      FileTime = 0;
      pft = 0;
      if ( DosDateTimeToFileTime(v18, v17, &FileTime) && LocalFileTimeToFileTime(&FileTime, &pft) )
        return (unsigned int)InitVariantFromFileTime(&pft, a4);
      break;
    default:
      if ( pid )
      {
        if ( pid == 4 )
        {
          v20 = *(_QWORD *)&PKEY_ItemTypeText.fmtid.Data1 - *(_QWORD *)&a3->fmtid.Data1;
          if ( *(_QWORD *)&PKEY_ItemTypeText.fmtid.Data1 == *(_QWORD *)&a3->fmtid.Data1 )
            v20 = *(_QWORD *)PKEY_ItemTypeText.fmtid.Data4 - *(_QWORD *)a3->fmtid.Data4;
          if ( !v20 )
            return (unsigned int)CCabFolder::GetTypeOf((struct _CABITEM *)a2, a4);
        }
      }
      else
      {
        v19 = 0x11CE9F370CD7A5C0LL - *(_QWORD *)&a3->fmtid.Data1;
        if ( *(_QWORD *)&a3->fmtid.Data1 == 0x11CE9F370CD7A5C0LL )
          v19 = 0x62122E2B000865AELL - *(_QWORD *)a3->fmtid.Data4;
        if ( !v19 )
          return (unsigned int)CCabFolder::GetPathOf((struct _CABITEM *)a2, a4);
      }
      return (unsigned int)AssocGetDetailsOfPropKey((IShellFolder *)(this & -(__int64)(this != 8)), a2, a3, a4, 0);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000e260  push    rbx
0x18000e262  push    rdi
0x18000e263  sub     rsp, 268h
0x18000e26a  mov     rax, cs:__security_cookie
0x18000e271  xor     rax, rsp
0x18000e274  mov     [rsp+278h+var_28], rax
0x18000e27c  mov     eax, [r8+10h]
0x18000e280  mov     rdi, r9
0x18000e283  mov     r10, r8
0x18000e286  mov     r11, rdx
0x18000e289  mov     r9, rcx; unsigned int
0x18000e28c  cmp     eax, 0Ah
0x18000e28f  jnz     short loc_18000E2AD
0x18000e291  mov     rcx, qword ptr cs:PKEY_ItemNameDisplay.fmtid.Data1
0x18000e298  sub     rcx, [r8]
0x18000e29b  jnz     short loc_18000E2A8
0x18000e29d  mov     rcx, qword ptr cs:PKEY_ItemNameDisplay.fmtid.Data4
0x18000e2a4  sub     rcx, [r8+8]
0x18000e2a8  test    rcx, rcx
0x18000e2ab  jz      short loc_18000E2D2
0x18000e2ad  cmp     eax, 18h
0x18000e2b0  jnz     short loc_18000E2F2
0x18000e2b2  mov     rax, qword ptr cs:PKEY_ParsingName.fmtid.Data1
0x18000e2b9  sub     rax, [r8]
0x18000e2bc  jnz     short loc_18000E2C9
0x18000e2be  mov     rax, qword ptr cs:PKEY_ParsingName.fmtid.Data4
0x18000e2c5  sub     rax, [r8+8]
0x18000e2c9  test    rax, rax
0x18000e2cc  jnz     loc_18000E4AD
0x18000e2d2  lea     rax, [r9-8]
0x18000e2d6  mov     r8, r11
0x18000e2d9  neg     rax
0x18000e2dc  mov     rdx, r10
0x18000e2df  sbb     rcx, rcx
0x18000e2e2  and     rcx, r9
0x18000e2e5  mov     r9, rdi
0x18000e2e8  call    GetNameDetails
0x18000e2ed  jmp     loc_18000E4CC
0x18000e2f2  cmp     eax, 6
0x18000e2f5  jnz     short loc_18000E346
0x18000e2f7  mov     rax, qword ptr cs:PKEY_ItemFolderPathDisplay.fmtid.Data1
0x18000e2fe  sub     rax, [r8]
0x18000e301  jnz     short loc_18000E30E
0x18000e303  mov     rax, qword ptr cs:PKEY_ItemFolderPathDisplay.fmtid.Data4
0x18000e30a  sub     rax, [r8+8]
0x18000e30e  test    rax, rax
0x18000e311  jnz     loc_18000E4AD
0x18000e317  mov     rcx, [r9+28h]; pidl
0x18000e31b  lea     r8, [rsp+278h+pszPath]; unsigned __int16 *
0x18000e320  mov     edx, 8000h; unsigned int
0x18000e325  call    ?SHGetNameAndFlagsW@@YAJPEFBU_ITEMIDLIST@@KPEAGIPEAK@Z; SHGetNameAndFlagsW(_ITEMIDLIST const *,ulong,ushort *,uint,ulong *)
0x18000e32a  mov     ebx, eax
0x18000e32c  test    eax, eax
0x18000e32e  js      loc_18000E4CE
0x18000e334  lea     rcx, [rsp+278h+pszPath]; unsigned __int16 *
0x18000e339  mov     rdx, rdi; struct tagVARIANT *
0x18000e33c  call    ?InitVariantFromString@@YAJPEBGPEAUtagVARIANT@@@Z; InitVariantFromString(ushort const *,tagVARIANT *)
0x18000e341  jmp     loc_18000E4CC
0x18000e346  cmp     eax, 0Bh
0x18000e349  jnz     short loc_18000E3A2
0x18000e34b  mov     rax, [r8]
0x18000e34e  sub     rax, qword ptr cs:PKEY_ItemType.fmtid.Data1
0x18000e355  jnz     short loc_18000E362
0x18000e357  mov     rax, [r8+8]
0x18000e35b  sub     rax, qword ptr cs:PKEY_ItemType.fmtid.Data4
0x18000e362  test    rax, rax
0x18000e365  jnz     loc_18000E4AD
0x18000e36b  lea     rax, [r9-8]
0x18000e36f  mov     r8d, 8000h
0x18000e375  neg     rax
0x18000e378  sbb     rcx, rcx
0x18000e37b  and     rcx, r9
0x18000e37e  lea     r9, [rsp+278h+pszPath]
0x18000e383  call    DisplayNameOfW
0x18000e388  mov     ebx, eax
0x18000e38a  test    eax, eax
0x18000e38c  js      loc_18000E4CE
0x18000e392  lea     rcx, [rsp+278h+pszPath]; pszPath
0x18000e397  call    cs:__imp_PathFindExtensionW
0x18000e39d  mov     rcx, rax
0x18000e3a0  jmp     short loc_18000E339
0x18000e3a2  cmp     eax, 0Ch
0x18000e3a5  jnz     short loc_18000E3DA
0x18000e3a7  mov     rax, qword ptr cs:PKEY_Size.fmtid.Data1
0x18000e3ae  sub     rax, [r8]
0x18000e3b1  jnz     short loc_18000E3BE
0x18000e3b3  mov     rax, qword ptr cs:PKEY_Size.fmtid.Data4
0x18000e3ba  sub     rax, [r8+8]
0x18000e3be  test    rax, rax
0x18000e3c1  jnz     loc_18000E4AD
0x18000e3c7  mov     eax, [rdx+4]
0x18000e3ca  xor     ebx, ebx
0x18000e3cc  mov     [rdi+8], rax
0x18000e3d0  mov     word ptr [rdi], 15h
0x18000e3d5  jmp     loc_18000E4CE
0x18000e3da  cmp     eax, 0Eh
0x18000e3dd  jnz     short loc_18000E452
0x18000e3df  mov     rax, qword ptr cs:PKEY_DateModified.fmtid.Data1
0x18000e3e6  sub     rax, [r8]
0x18000e3e9  jnz     short loc_18000E3F6
0x18000e3eb  mov     rax, qword ptr cs:PKEY_DateModified.fmtid.Data4
0x18000e3f2  sub     rax, [r8+8]
0x18000e3f6  test    rax, rax
0x18000e3f9  jnz     loc_18000E4AD
0x18000e3ff  movzx   edx, word ptr [rdx+0Ah]; wFatTime
0x18000e403  lea     r8, [rsp+278h+FileTime]; lpFileTime
0x18000e408  movzx   ecx, word ptr [r11+8]; wFatDate
0x18000e40d  mov     ebx, 80004005h
0x18000e412  mov     qword ptr [rsp+278h+FileTime.dwLowDateTime], rax
0x18000e417  mov     qword ptr [rsp+278h+pft.dwLowDateTime], rax
0x18000e41c  call    cs:__imp_DosDateTimeToFileTime
0x18000e422  test    eax, eax
0x18000e424  jz      loc_18000E4CE
0x18000e42a  lea     rdx, [rsp+278h+pft]; lpFileTime
0x18000e42f  lea     rcx, [rsp+278h+FileTime]; lpLocalFileTime
0x18000e434  call    cs:__imp_LocalFileTimeToFileTime
0x18000e43a  test    eax, eax
0x18000e43c  jz      loc_18000E4CE
0x18000e442  mov     rdx, rdi; pvar
0x18000e445  lea     rcx, [rsp+278h+pft]; pft
0x18000e44a  call    cs:__imp_InitVariantFromFileTime
0x18000e450  jmp     short loc_18000E4CC
0x18000e452  test    eax, eax
0x18000e454  jnz     short loc_18000E47F
0x18000e456  mov     rax, cs:qword_180015A10
0x18000e45d  sub     rax, [r8]
0x18000e460  jnz     short loc_18000E46D
0x18000e462  mov     rax, cs:qword_180015A18
0x18000e469  sub     rax, [r8+8]
0x18000e46d  test    rax, rax
0x18000e470  jnz     short loc_18000E4AD
0x18000e472  mov     rdx, rdi; struct tagVARIANT *
0x18000e475  mov     rcx, r11; struct _CABITEM *
0x18000e478  call    ?GetPathOf@CCabFolder@@SAJPEFAU_CABITEM@@PEAUtagVARIANT@@@Z; CCabFolder::GetPathOf(_CABITEM *,tagVARIANT *)
0x18000e47d  jmp     short loc_18000E4CC
0x18000e47f  cmp     eax, 4
0x18000e482  jnz     short loc_18000E4AD
0x18000e484  mov     rax, qword ptr cs:PKEY_ItemTypeText.fmtid.Data1
0x18000e48b  sub     rax, [r8]
0x18000e48e  jnz     short loc_18000E49B
0x18000e490  mov     rax, qword ptr cs:PKEY_ItemTypeText.fmtid.Data4
0x18000e497  sub     rax, [r8+8]
0x18000e49b  test    rax, rax
0x18000e49e  jnz     short loc_18000E4AD
0x18000e4a0  mov     rdx, rdi; struct tagVARIANT *
0x18000e4a3  mov     rcx, r11; struct _CABITEM *
0x18000e4a6  call    ?GetTypeOf@CCabFolder@@SAJPEFAU_CABITEM@@PEAUtagVARIANT@@@Z; CCabFolder::GetTypeOf(_CABITEM *,tagVARIANT *)
0x18000e4ab  jmp     short loc_18000E4CC
0x18000e4ad  lea     rax, [r9-8]
0x18000e4b1  mov     [rsp+278h+pfFoundPropKey], 0; pfFoundPropKey
0x18000e4ba  neg     rax
0x18000e4bd  sbb     rcx, rcx
0x18000e4c0  and     rcx, r9; psf
0x18000e4c3  mov     r9, rdi; pv
0x18000e4c6  call    cs:__imp_AssocGetDetailsOfPropKey
0x18000e4cc  mov     ebx, eax
0x18000e4ce  mov     eax, ebx
0x18000e4d0  mov     rcx, [rsp+278h+var_28]
0x18000e4d8  xor     rcx, rsp; StackCookie
0x18000e4db  call    __security_check_cookie
0x18000e4e0  add     rsp, 268h
0x18000e4e7  pop     rdi
0x18000e4e8  pop     rbx
0x18000e4e9  retn
```
