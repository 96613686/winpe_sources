# CExtractIcon::Init(IShellFolder2 *,_ITEMID_CHILD const *)

- ea: `0x18001b814`
- end: `0x18001bb38`
- name: `?Init@CExtractIcon@@QEAAJPEAUIShellFolder2@@PEFBU_ITEMID_CHILD@@@Z`
- size: `804`
- prototype: `int(CExtractIcon *__hidden this, struct IShellFolder2 *, const struct _ITEMID_CHILD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180020180`

## callees

- `0x180005210`
- `0x1800193e8`
- `0x18001b814`
- `0x18001c9fc`
- `0x18001ca6c`
- `0x1800284e0`
- `0x18003d010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18001b84d`
- `OLEAUT32!__imp_VariantInit` at `0x18001b9ba`
- `OLEAUT32!__imp_VariantInit` at `0x18001b84d`
- `OLEAUT32!__imp_VariantInit` at `0x18001b9ba`
- `OLEAUT32!__imp_VariantClear` at `0x18001baf7`
- `OLEAUT32!__imp_VariantClear` at `0x18001bb1c`
- `OLEAUT32!__imp_VariantClear` at `0x18001baf7`
- `OLEAUT32!__imp_VariantClear` at `0x18001bb1c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001ba2a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001ba2a`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x18001ba9a`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x18001ba9a`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNIW` at `0x18001b888`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNIW` at `0x18001b8a7`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNIW` at `0x18001b8c6`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNIW` at `0x18001b8e5`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNIW` at `0x18001b904`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNIW` at `0x18001b92b`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNIW` at `0x18001b952`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNIW` at `0x18001b979`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNIW` at `0x18001b9a0`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNIW` at `0x18001b888`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNIW` at `0x18001b8a7`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNIW` at `0x18001b8c6`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNIW` at `0x18001b8e5`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNIW` at `0x18001b904`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNIW` at `0x18001b92b`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNIW` at `0x18001b952`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNIW` at `0x18001b979`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNIW` at `0x18001b9a0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18001ba50`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18001ba50`

## string_xrefs

- `0x18001ba14`: `MAPI/IPM.Note.Read`
- `0x18001b8f9`: `MAPI/IPM.Task`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CExtractIcon::Init(CExtractIcon *this, struct IShellFolder2 *a2, const struct _ITEMID_CHILD *a3)
{
  HRESULT v7; // esi
  unsigned __int16 v8; // r9
  unsigned __int16 v9; // r9
  int v10; // ebx
  int v11; // eax
  LPWSTR ExtensionW; // rax
  const struct _WIN32_FIND_DATAW *v13; // rcx
  const WCHAR *v14; // rbx
  __int64 v15; // [rsp+30h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-38h] BYREF
  VARIANTARG pvargDest; // [rsp+50h] [rbp-20h] BYREF
  void *ppv; // [rsp+B0h] [rbp+40h] BYREF
  IBindCtx *pbc; // [rsp+B8h] [rbp+48h] BYREF

  if ( !a3 )
    return 2147942487LL;
  v7 = 0;
  *((_QWORD *)this + 8) = 0;
  VariantInit(&pvarg);
  if ( (int)GetPropertyDetail(a2, a3, &PKEY_ItemType, v8, &pvarg) < 0 )
  {
    *((_DWORD *)this + 16) = 1;
    goto LABEL_35;
  }
  if ( !StrCmpNIW(pvarg.bstrVal, L"MAPI/IPM.Contact", 16) || !StrCmpNIW(pvarg.bstrVal, L"MAPI/IPM.DistList", 17) )
  {
    *((_DWORD *)this + 16) = 4;
    goto LABEL_35;
  }
  if ( !StrCmpNIW(pvarg.bstrVal, L"MAPI/IPM.Appointment", 20)
    || !StrCmpNIW(pvarg.bstrVal, L"MAPI/IPM.Schedule.Meeting", 25) )
  {
    *((_DWORD *)this + 16) = 5;
    goto LABEL_35;
  }
  if ( StrCmpNIW(pvarg.bstrVal, L"MAPI/IPM.Task", 13) )
  {
    if ( !StrCmpNIW(pvarg.bstrVal, L"MAPI/IPM.StickyNote", 19) )
    {
      *((_DWORD *)this + 16) = 7;
      goto LABEL_35;
    }
    if ( !StrCmpNIW(pvarg.bstrVal, L"MAPI/IPM.Activity", 17) )
    {
      *((_DWORD *)this + 16) = 9;
      goto LABEL_35;
    }
    if ( !StrCmpNIW(pvarg.bstrVal, L"MAPI/Folder", 11) )
    {
      *((_DWORD *)this + 16) = 2;
      goto LABEL_35;
    }
    if ( !StrCmpNIW(pvarg.bstrVal, L"MAPI/IPM.Post.Rss", 17) )
    {
      *((_DWORD *)this + 16) = 10;
      goto LABEL_35;
    }
    VariantInit(&pvargDest);
    if ( (int)GetPropertyDetail(a2, a3, &PKEY_ParsingPath, v9, &pvargDest) >= 0 )
    {
      v10 = IsAttachment(pvargDest.bstrVal);
      v11 = IsFreeDoc(pvargDest.bstrVal, pvarg.bstrVal);
      if ( !v10 && !v11 )
      {
        *((_DWORD *)this + 16) = 3;
        if ( CompareStringW(0x7Fu, 1u, pvarg.bstrVal, -1, L"MAPI/IPM.Note.Read", -1) == 2 )
          *((_DWORD *)this + 17) = 1;
        goto LABEL_31;
      }
      *((_DWORD *)this + 16) = 8;
      ExtensionW = PathFindExtensionW(pvarg.bstrVal);
      v14 = ExtensionW;
      if ( !*ExtensionW )
      {
        v14 = L".";
LABEL_26:
        pbc = 0;
        v7 = CreateFileSysBindCtx(v13, &pbc);
        if ( v7 >= 0 )
        {
          ppv = 0;
          v7 = SHCreateItemFromParsingName(v14, pbc, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
          if ( v7 >= 0 )
          {
            v15 = 0;
            v7 = (*(__int64 (__fastcall **)(void *, _QWORD, const GUID *, GUID *, char *))(*(_QWORD *)ppv + 24LL))(
                   ppv,
                   0,
                   &BHID_SFUIObject,
                   &GUID_000214fa_0000_0000_c000_000000000046,
                   (char *)this + 72);
            ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(&v15);
          }
          ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(&ppv);
        }
        ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(&pbc);
        goto LABEL_31;
      }
      if ( ExtensionW )
        goto LABEL_26;
    }
LABEL_31:
    VariantClear(&pvargDest);
    goto LABEL_35;
  }
  *((_DWORD *)this + 16) = 6;
LABEL_35:
  VariantClear(&pvarg);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001b814  mov     [rsp-28h+arg_0], rbx
0x18001b819  push    rbp
0x18001b81a  push    rsi
0x18001b81b  push    rdi
0x18001b81c  push    r14
0x18001b81e  push    r15
0x18001b820  mov     rbp, rsp
0x18001b823  sub     rsp, 70h
0x18001b827  mov     rbx, r8
0x18001b82a  mov     r14, rdx
0x18001b82d  mov     rdi, rcx
0x18001b830  xor     r15d, r15d
0x18001b833  test    r8, r8
0x18001b836  jnz     short loc_18001B842
0x18001b838  mov     eax, 80070057h
0x18001b83d  jmp     loc_18001BB24
0x18001b842  mov     esi, r15d
0x18001b845  mov     [rcx+40h], r15
0x18001b849  lea     rcx, [rbp+pvarg]; pvarg
0x18001b84d  call    cs:__imp_VariantInit
0x18001b853  nop
0x18001b854  lea     rax, [rbp+pvarg]
0x18001b858  mov     [rsp+70h+lpString2], rax; pvargDest
0x18001b85d  lea     r8, PKEY_ItemType; struct _tagpropertykey *
0x18001b864  mov     rdx, rbx; struct _ITEMID_CHILD *
0x18001b867  mov     rcx, r14; struct IShellFolder2 *
0x18001b86a  call    ?GetPropertyDetail@@YAJPEAUIShellFolder2@@PEFBU_ITEMID_CHILD@@PEBU_tagpropertykey@@GPEAUtagVARIANT@@@Z; GetPropertyDetail(IShellFolder2 *,_ITEMID_CHILD const *,_tagpropertykey const *,ushort,tagVARIANT *)
0x18001b86f  test    eax, eax
0x18001b871  js      loc_18001BB11
0x18001b877  mov     r8d, 10h; nChar
0x18001b87d  lea     rdx, psz2; "MAPI/IPM.Contact"
0x18001b884  mov     rcx, qword ptr [rbp+pvarg+8]; psz1
0x18001b888  call    cs:__imp_StrCmpNIW
0x18001b88e  test    eax, eax
0x18001b890  jz      loc_18001BB08
0x18001b896  mov     r8d, 11h; nChar
0x18001b89c  lea     rdx, aMapiIpmDistlis; "MAPI/IPM.DistList"
0x18001b8a3  mov     rcx, qword ptr [rbp+pvarg+8]; psz1
0x18001b8a7  call    cs:__imp_StrCmpNIW
0x18001b8ad  test    eax, eax
0x18001b8af  jz      loc_18001BB08
0x18001b8b5  mov     r8d, 14h; nChar
0x18001b8bb  lea     rdx, aMapiIpmAppoint; "MAPI/IPM.Appointment"
0x18001b8c2  mov     rcx, qword ptr [rbp+pvarg+8]; psz1
0x18001b8c6  call    cs:__imp_StrCmpNIW
0x18001b8cc  test    eax, eax
0x18001b8ce  jz      loc_18001BAFF
0x18001b8d4  mov     r8d, 19h; nChar
0x18001b8da  lea     rdx, aMapiIpmSchedul; "MAPI/IPM.Schedule.Meeting"
0x18001b8e1  mov     rcx, qword ptr [rbp+pvarg+8]; psz1
0x18001b8e5  call    cs:__imp_StrCmpNIW
0x18001b8eb  test    eax, eax
0x18001b8ed  jz      loc_18001BAFF
0x18001b8f3  mov     r8d, 0Dh; nChar
0x18001b8f9  lea     rdx, aMapiIpmTask; "MAPI/IPM.Task"
0x18001b900  mov     rcx, qword ptr [rbp+pvarg+8]; psz1
0x18001b904  call    cs:__imp_StrCmpNIW
0x18001b90a  test    eax, eax
0x18001b90c  jnz     short loc_18001B91A
0x18001b90e  mov     dword ptr [rdi+40h], 6
0x18001b915  jmp     loc_18001BB18
0x18001b91a  mov     r8d, 13h; nChar
0x18001b920  lea     rdx, aMapiIpmStickyn; "MAPI/IPM.StickyNote"
0x18001b927  mov     rcx, qword ptr [rbp+pvarg+8]; psz1
0x18001b92b  call    cs:__imp_StrCmpNIW
0x18001b931  test    eax, eax
0x18001b933  jnz     short loc_18001B941
0x18001b935  mov     dword ptr [rdi+40h], 7
0x18001b93c  jmp     loc_18001BB18
0x18001b941  mov     r8d, 11h; nChar
0x18001b947  lea     rdx, aMapiIpmActivit; "MAPI/IPM.Activity"
0x18001b94e  mov     rcx, qword ptr [rbp+pvarg+8]; psz1
0x18001b952  call    cs:__imp_StrCmpNIW
0x18001b958  test    eax, eax
0x18001b95a  jnz     short loc_18001B968
0x18001b95c  mov     dword ptr [rdi+40h], 9
0x18001b963  jmp     loc_18001BB18
0x18001b968  mov     r8d, 0Bh; nChar
0x18001b96e  lea     rdx, aMapiFolder; "MAPI/Folder"
0x18001b975  mov     rcx, qword ptr [rbp+pvarg+8]; psz1
0x18001b979  call    cs:__imp_StrCmpNIW
0x18001b97f  test    eax, eax
0x18001b981  jnz     short loc_18001B98F
0x18001b983  mov     dword ptr [rdi+40h], 2
0x18001b98a  jmp     loc_18001BB18
0x18001b98f  mov     r8d, 11h; nChar
0x18001b995  lea     rdx, aMapiIpmPostRss; "MAPI/IPM.Post.Rss"
0x18001b99c  mov     rcx, qword ptr [rbp+pvarg+8]; psz1
0x18001b9a0  call    cs:__imp_StrCmpNIW
0x18001b9a6  test    eax, eax
0x18001b9a8  jnz     short loc_18001B9B6
0x18001b9aa  mov     dword ptr [rdi+40h], 0Ah
0x18001b9b1  jmp     loc_18001BB18
0x18001b9b6  lea     rcx, [rbp+pvargDest]; pvarg
0x18001b9ba  call    cs:__imp_VariantInit
0x18001b9c0  nop
0x18001b9c1  lea     rax, [rbp+pvargDest]
0x18001b9c5  mov     [rsp+70h+lpString2], rax; pvargDest
0x18001b9ca  lea     r8, PKEY_ParsingPath; struct _tagpropertykey *
0x18001b9d1  mov     rdx, rbx; struct _ITEMID_CHILD *
0x18001b9d4  mov     rcx, r14; struct IShellFolder2 *
0x18001b9d7  call    ?GetPropertyDetail@@YAJPEAUIShellFolder2@@PEFBU_ITEMID_CHILD@@PEBU_tagpropertykey@@GPEAUtagVARIANT@@@Z; GetPropertyDetail(IShellFolder2 *,_ITEMID_CHILD const *,_tagpropertykey const *,ushort,tagVARIANT *)
0x18001b9dc  test    eax, eax
0x18001b9de  js      loc_18001BAF3
0x18001b9e4  mov     rcx, qword ptr [rbp+pvargDest+8]; wchar_t *
0x18001b9e8  call    ?IsAttachment@@YAHPEB_W@Z; IsAttachment(wchar_t const *)
0x18001b9ed  mov     ebx, eax
0x18001b9ef  mov     rdx, qword ptr [rbp+pvarg+8]; wchar_t *
0x18001b9f3  mov     rcx, qword ptr [rbp+pvargDest+8]; wchar_t *
0x18001b9f7  call    ?IsFreeDoc@@YAHPEB_W0@Z; IsFreeDoc(wchar_t const *,wchar_t const *)
0x18001b9fc  test    ebx, ebx
0x18001b9fe  jnz     short loc_18001BA45
0x18001ba00  test    eax, eax
0x18001ba02  jnz     short loc_18001BA45
0x18001ba04  mov     dword ptr [rdi+40h], 3
0x18001ba0b  or      r9d, 0FFFFFFFFh; cchCount1
0x18001ba0f  mov     [rsp+70h+cchCount2], r9d; cchCount2
0x18001ba14  lea     rax, aMapiIpmNoteRea; "MAPI/IPM.Note.Read"
0x18001ba1b  mov     [rsp+70h+lpString2], rax; lpString2
0x18001ba20  mov     r8, qword ptr [rbp+pvarg+8]; lpString1
0x18001ba24  lea     edx, [rbx+1]; dwCmpFlags
0x18001ba27  lea     ecx, [rbx+7Fh]; Locale
0x18001ba2a  call    cs:__imp_CompareStringW
0x18001ba30  cmp     eax, 2
0x18001ba33  jnz     loc_18001BAF3
0x18001ba39  mov     dword ptr [rdi+44h], 1
0x18001ba40  jmp     loc_18001BAF3
0x18001ba45  mov     dword ptr [rdi+40h], 8
0x18001ba4c  mov     rcx, qword ptr [rbp+pvarg+8]; pszPath
0x18001ba50  call    cs:__imp_PathFindExtensionW
0x18001ba56  mov     rbx, rax
0x18001ba59  cmp     [rax], r15w
0x18001ba5d  jnz     short loc_18001BA68
0x18001ba5f  lea     rbx, asc_180044C04; "."
0x18001ba66  jmp     short loc_18001BA71
0x18001ba68  test    rax, rax
0x18001ba6b  jz      loc_18001BAF3
0x18001ba71  mov     [rbp+pbc], r15
0x18001ba75  lea     rdx, [rbp+pbc]; struct IBindCtx **
0x18001ba79  call    ?CreateFileSysBindCtx@@YAJPEBU_WIN32_FIND_DATAW@@PEAPEAUIBindCtx@@@Z; CreateFileSysBindCtx(_WIN32_FIND_DATAW const *,IBindCtx * *)
0x18001ba7e  mov     esi, eax
0x18001ba80  test    eax, eax
0x18001ba82  js      short loc_18001BAE9
0x18001ba84  mov     [rbp+ppv], r15
0x18001ba88  lea     r9, [rbp+ppv]; ppv
0x18001ba8c  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18001ba93  mov     rdx, [rbp+pbc]; pbc
0x18001ba97  mov     rcx, rbx; pszPath
0x18001ba9a  call    cs:__imp_SHCreateItemFromParsingName
0x18001baa0  mov     esi, eax
0x18001baa2  test    eax, eax
0x18001baa4  js      short loc_18001BADF
0x18001baa6  mov     [rbp+var_40], r15
0x18001baaa  mov     rcx, [rbp+ppv]
0x18001baae  mov     rax, [rcx]
0x18001bab1  lea     rdx, [rdi+48h]
0x18001bab5  mov     [rsp+70h+lpString2], rdx
0x18001baba  lea     r9, _GUID_000214fa_0000_0000_c000_000000000046
0x18001bac1  lea     r8, BHID_SFUIObject
0x18001bac8  xor     edx, edx
0x18001baca  mov     rax, [rax+18h]
0x18001bace  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bad3  mov     esi, eax
0x18001bad5  lea     rcx, [rbp+var_40]
0x18001bad9  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x18001bade  nop
0x18001badf  lea     rcx, [rbp+ppv]
0x18001bae3  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x18001bae8  nop
0x18001bae9  lea     rcx, [rbp+pbc]
0x18001baed  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x18001baf2  nop
0x18001baf3  lea     rcx, [rbp+pvargDest]; pvarg
0x18001baf7  call    cs:__imp_VariantClear
0x18001bafd  jmp     short loc_18001BB18
0x18001baff  mov     dword ptr [rdi+40h], 5
0x18001bb06  jmp     short loc_18001BB18
0x18001bb08  mov     dword ptr [rdi+40h], 4
0x18001bb0f  jmp     short loc_18001BB18
0x18001bb11  mov     dword ptr [rdi+40h], 1
0x18001bb18  lea     rcx, [rbp+pvarg]; pvarg
0x18001bb1c  call    cs:__imp_VariantClear
0x18001bb22  mov     eax, esi
0x18001bb24  mov     rbx, [rsp+70h+arg_0]
0x18001bb2c  add     rsp, 70h
0x18001bb30  pop     r15
0x18001bb32  pop     r14
0x18001bb34  pop     rdi
0x18001bb35  pop     rsi
0x18001bb36  pop     rbp
0x18001bb37  retn
```
