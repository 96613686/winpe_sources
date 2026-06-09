# GetDestinationItemFromDataObjectHelper(IDataObject *,_GUID const &,void * *)

- ea: `0x14011c1b8`
- end: `0x14011c410`
- name: `?GetDestinationItemFromDataObjectHelper@@YAJPEAUIDataObject@@AEBU_GUID@@PEAPEAX@Z`
- size: `600`
- prototype: `__int64 __fastcall(struct IDataObject *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14011c1a0`

## callees

- `0x14000c61c`
- `0x140116bac`
- `0x14011c1b8`
- `0x140122f40`
- `0x1401b68a0`
- `0x1401db010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14011c389`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14011c3ac`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14011c389`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14011c3ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14011c2a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14011c3d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14011c2a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14011c3d1`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x14011c31c`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x14011c3f4`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x14011c31c`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x14011c3f4`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromIDList` at `0x14011c20f`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromIDList` at `0x14011c309`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromIDList` at `0x14011c20f`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromIDList` at `0x14011c309`

## pseudocode

```c
__int64 __fastcall GetDestinationItemFromDataObjectHelper(struct IDataObject *a1, const struct _GUID *a2, void **a3)
{
  HRESULT IDList; // ebx
  _QWORD *v6; // rdi
  __int64 v7; // rdx
  int v8; // esi
  __int64 (__fastcall **v9)(_QWORD *, const struct _GUID *, void **); // rax
  LPCITEMIDLIST v11; // [rsp+30h] [rbp-20h] BYREF
  void *v12; // [rsp+38h] [rbp-18h] BYREF
  LPCITEMIDLIST pidl; // [rsp+40h] [rbp-10h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-8h] BYREF
  void *ppv; // [rsp+90h] [rbp+40h] BYREF
  __int64 v16; // [rsp+98h] [rbp+48h] BYREF

  *a3 = 0;
  pidl = 0;
  IDList = DataObj_GetIDList(a1, DOGIF_ONLY_IF_ONE|DOGIF_NO_HDROP, (struct _ITEMIDLIST_ABSOLUTE **)&pidl);
  if ( IDList >= 0 )
  {
    ppv = 0;
    IDList = SHCreateItemFromIDList(pidl, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, &ppv);
    if ( IDList < 0 )
    {
LABEL_22:
      ILFree((LPITEMIDLIST)pidl);
      return (unsigned int)IDList;
    }
    v12 = 0;
    v16 = 0;
    if ( (*(int (__fastcall **)(void *, _QWORD, const GUID *, GUID *, __int64 *))(*(_QWORD *)ppv + 24LL))(
           ppv,
           0,
           &BHID_SFUIObject,
           &GUID_000214f9_0000_0000_c000_000000000046,
           &v16) < 0 )
    {
      v6 = ppv;
    }
    else
    {
      v6 = 0;
      v11 = 0;
      if ( (**(int (__fastcall ***)(__int64, GUID *, LPCITEMIDLIST *))v16)(
             v16,
             &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
             &v11) < 0 )
        goto LABEL_8;
      v8 = 0;
      IDList = -2147217657;
      pv = 0;
      if ( (int)IPropertyStore_GetString(v11, v7, &pv) >= 0 )
      {
        v8 = 1;
        CoTaskMemFree(pv);
      }
      (*(void (__fastcall **)(LPCITEMIDLIST))(*(_QWORD *)&v11->mkid.cb + 16LL))(v11);
      if ( !v8 )
      {
LABEL_8:
        pv = 0;
        IDList = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v16 + 32LL))(v16, &pv);
        if ( IDList >= 0 )
        {
          v11 = 0;
          IDList = _CacheShortcutDisplayName(
                     (struct IShellItem *)ppv,
                     (struct _ITEMIDLIST_ABSOLUTE *)pv,
                     (struct _ITEMIDLIST_ABSOLUTE **)&v11);
          if ( IDList >= 0 )
          {
            IDList = SHCreateItemFromIDList(v11, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, &v12);
            if ( IDList >= 0 )
              v6 = v12;
            ILFree((LPITEMIDLIST)v11);
          }
        }
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      if ( IDList < 0 )
        goto LABEL_21;
    }
    v9 = (__int64 (__fastcall **)(_QWORD *, const struct _GUID *, void **))*v6;
    v11 = 0;
    v9[17](v6, &PKEY_FileExtension.fmtid, (void **)&v11);
    if ( !v11
      || (IDList = -2147217657, CompareStringOrdinal(&v11->mkid.cb, -1, L".EXE", -1, 1) != 2)
      && CompareStringOrdinal(&v11->mkid.cb, -1, L".MSC", -1, 1) != 2 )
    {
      IDList = (*(__int64 (__fastcall **)(_QWORD *, const struct _GUID *, void **))*v6)(v6, a2, a3);
    }
    CoTaskMemFree((LPVOID)v11);
LABEL_21:
    SafeRelease<IShellItem2>(&v12);
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
    goto LABEL_22;
  }
  return (unsigned int)IDList;
}

```

## disassembly

```asm
0x14011c1b8  mov     [rsp-28h+arg_0], rbx
0x14011c1bd  push    rbp
0x14011c1be  push    rsi
0x14011c1bf  push    rdi
0x14011c1c0  push    r14
0x14011c1c2  push    r15
0x14011c1c4  mov     rbp, rsp
0x14011c1c7  sub     rsp, 50h
0x14011c1cb  mov     r14, r8
0x14011c1ce  mov     qword ptr [r8], 0
0x14011c1d5  mov     r15, rdx
0x14011c1d8  mov     [rbp+pidl], 0
0x14011c1e0  lea     r8, [rbp+pidl]; struct _ITEMIDLIST_ABSOLUTE **
0x14011c1e4  mov     edx, 0Ah; enum DATAOBJ_GET_ITEM_FLAGS
0x14011c1e9  call    ?DataObj_GetIDList@@YAJPEAUIDataObject@@W4DATAOBJ_GET_ITEM_FLAGS@@PEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z; DataObj_GetIDList(IDataObject *,DATAOBJ_GET_ITEM_FLAGS,_ITEMIDLIST_ABSOLUTE * *)
0x14011c1ee  mov     ebx, eax
0x14011c1f0  test    eax, eax
0x14011c1f2  js      loc_14011C3FA
0x14011c1f8  mov     rcx, [rbp+pidl]; pidl
0x14011c1fc  lea     r8, [rbp+ppv]; ppv
0x14011c200  lea     rdx, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x14011c207  mov     [rbp+ppv], 0
0x14011c20f  call    cs:__imp_SHCreateItemFromIDList
0x14011c215  mov     ebx, eax
0x14011c217  test    eax, eax
0x14011c219  js      loc_14011C3F0
0x14011c21f  mov     rcx, [rbp+ppv]
0x14011c223  lea     rdx, [rbp+arg_18]
0x14011c227  mov     [rbp+var_18], 0
0x14011c22f  lea     r9, _GUID_000214f9_0000_0000_c000_000000000046
0x14011c236  mov     [rbp+arg_18], 0
0x14011c23e  lea     r8, BHID_SFUIObject
0x14011c245  mov     qword ptr [rsp+50h+bIgnoreCase], rdx
0x14011c24a  xor     edx, edx
0x14011c24c  mov     rax, [rcx]
0x14011c24f  mov     rax, [rax+18h]
0x14011c253  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14011c258  test    eax, eax
0x14011c25a  js      loc_14011C33B
0x14011c260  mov     rcx, [rbp+arg_18]
0x14011c264  lea     r8, [rbp+var_20]
0x14011c268  xor     edi, edi
0x14011c26a  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x14011c271  mov     [rbp+var_20], rdi
0x14011c275  mov     rax, [rcx]
0x14011c278  mov     rax, [rax]
0x14011c27b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14011c280  test    eax, eax
0x14011c282  js      short loc_14011C2C1
0x14011c284  mov     rcx, [rbp+var_20]
0x14011c288  lea     r8, [rbp+pv]
0x14011c28c  xor     esi, esi
0x14011c28e  mov     ebx, 80040F07h
0x14011c293  mov     [rbp+pv], rsi
0x14011c297  call    IPropertyStore_GetString
0x14011c29c  test    eax, eax
0x14011c29e  js      short loc_14011C2AD
0x14011c2a0  mov     rcx, [rbp+pv]; pv
0x14011c2a4  lea     esi, [rdi+1]
0x14011c2a7  call    cs:__imp_CoTaskMemFree
0x14011c2ad  mov     rcx, [rbp+var_20]
0x14011c2b1  mov     rax, [rcx]
0x14011c2b4  mov     rax, [rax+10h]
0x14011c2b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14011c2bd  test    esi, esi
0x14011c2bf  jnz     short loc_14011C322
0x14011c2c1  mov     rcx, [rbp+arg_18]
0x14011c2c5  lea     rdx, [rbp+pv]
0x14011c2c9  mov     [rbp+pv], rdi
0x14011c2cd  mov     rax, [rcx]
0x14011c2d0  mov     rax, [rax+20h]
0x14011c2d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14011c2d9  mov     ebx, eax
0x14011c2db  test    eax, eax
0x14011c2dd  js      short loc_14011C322
0x14011c2df  mov     rdx, [rbp+pv]; struct _ITEMIDLIST_ABSOLUTE *
0x14011c2e3  lea     r8, [rbp+var_20]; struct _ITEMIDLIST_ABSOLUTE **
0x14011c2e7  mov     rcx, [rbp+ppv]; struct IShellItem *
0x14011c2eb  mov     [rbp+var_20], rdi
0x14011c2ef  call    ?_CacheShortcutDisplayName@@YAJPEAUIShellItem@@PEAU_ITEMIDLIST_ABSOLUTE@@PEAPEAU2@@Z; _CacheShortcutDisplayName(IShellItem *,_ITEMIDLIST_ABSOLUTE *,_ITEMIDLIST_ABSOLUTE * *)
0x14011c2f4  mov     ebx, eax
0x14011c2f6  test    eax, eax
0x14011c2f8  js      short loc_14011C322
0x14011c2fa  mov     rcx, [rbp+var_20]; pidl
0x14011c2fe  lea     r8, [rbp+var_18]; ppv
0x14011c302  lea     rdx, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x14011c309  call    cs:__imp_SHCreateItemFromIDList
0x14011c30f  mov     rcx, [rbp+var_20]; pidl
0x14011c313  test    eax, eax
0x14011c315  mov     ebx, eax
0x14011c317  cmovns  rdi, [rbp+var_18]
0x14011c31c  call    cs:__imp_ILFree
0x14011c322  mov     rcx, [rbp+arg_18]
0x14011c326  mov     rax, [rcx]
0x14011c329  mov     rax, [rax+10h]
0x14011c32d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14011c332  test    ebx, ebx
0x14011c334  jns     short loc_14011C33F
0x14011c336  jmp     loc_14011C3D7
0x14011c33b  mov     rdi, [rbp+ppv]
0x14011c33f  mov     rax, [rdi]
0x14011c342  lea     r8, [rbp+var_20]
0x14011c346  lea     rdx, PKEY_FileExtension
0x14011c34d  mov     [rbp+var_20], 0
0x14011c355  mov     rcx, rdi
0x14011c358  mov     rax, [rax+88h]
0x14011c35f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14011c364  mov     rcx, [rbp+var_20]; lpString1
0x14011c368  test    rcx, rcx
0x14011c36b  jz      short loc_14011C3B7
0x14011c36d  or      esi, 0FFFFFFFFh
0x14011c370  mov     [rsp+50h+bIgnoreCase], 1; bIgnoreCase
0x14011c378  mov     r9d, esi; cchCount2
0x14011c37b  lea     r8, aExe; ".EXE"
0x14011c382  mov     edx, esi; cchCount1
0x14011c384  mov     ebx, 80040F07h
0x14011c389  call    cs:__imp_CompareStringOrdinal
0x14011c38f  cmp     eax, 2
0x14011c392  jz      short loc_14011C3CD
0x14011c394  mov     rcx, [rbp+var_20]; lpString1
0x14011c398  lea     r8, aMsc; ".MSC"
0x14011c39f  mov     r9d, esi; cchCount2
0x14011c3a2  mov     [rsp+50h+bIgnoreCase], 1; bIgnoreCase
0x14011c3aa  mov     edx, esi; cchCount1
0x14011c3ac  call    cs:__imp_CompareStringOrdinal
0x14011c3b2  cmp     eax, 2
0x14011c3b5  jz      short loc_14011C3CD
0x14011c3b7  mov     rax, [rdi]
0x14011c3ba  mov     r8, r14
0x14011c3bd  mov     rdx, r15
0x14011c3c0  mov     rcx, rdi
0x14011c3c3  mov     rax, [rax]
0x14011c3c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14011c3cb  mov     ebx, eax
0x14011c3cd  mov     rcx, [rbp+var_20]; pv
0x14011c3d1  call    cs:__imp_CoTaskMemFree
0x14011c3d7  lea     rcx, [rbp+var_18]
0x14011c3db  call    ??$SafeRelease@UIShellItem2@@@@YAXPEAPEAUIShellItem2@@@Z; SafeRelease<IShellItem2>(IShellItem2 * *)
0x14011c3e0  mov     rcx, [rbp+ppv]
0x14011c3e4  mov     rax, [rcx]
0x14011c3e7  mov     rax, [rax+10h]
0x14011c3eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14011c3f0  mov     rcx, [rbp+pidl]; pidl
0x14011c3f4  call    cs:__imp_ILFree
0x14011c3fa  mov     eax, ebx
0x14011c3fc  mov     rbx, [rsp+50h+arg_0]
0x14011c404  add     rsp, 50h
0x14011c408  pop     r15
0x14011c40a  pop     r14
0x14011c40c  pop     rdi
0x14011c40d  pop     rsi
0x14011c40e  pop     rbp
0x14011c40f  retn
```
