# GetDestinationItemFromDataObjectHelper(IDataObject *,_GUID const &,void * *)

- ea: `0x140127288`
- end: `0x140127511`
- name: `?GetDestinationItemFromDataObjectHelper@@YAJPEAUIDataObject@@AEBU_GUID@@PEAPEAX@Z`
- size: `649`
- prototype: `__int64 __fastcall(struct IDataObject *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140127270`

## callees

- `0x14000d500`
- `0x140121580`
- `0x140127288`
- `0x14012e568`
- `0x1401b4be4`
- `0x1401d9010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140127471`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14012749a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140127471`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14012749a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14012737d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1401274c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14012737d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1401274c5`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x1401273fe`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x1401274ee`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x1401273fe`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x1401274ee`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromIDList` at `0x1401272df`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromIDList` at `0x1401273e5`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromIDList` at `0x1401272df`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromIDList` at `0x1401273e5`

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
0x140127288  mov     [rsp-28h+arg_0], rbx
0x14012728d  push    rbp
0x14012728e  push    rsi
0x14012728f  push    rdi
0x140127290  push    r14
0x140127292  push    r15
0x140127294  mov     rbp, rsp
0x140127297  sub     rsp, 50h
0x14012729b  mov     r14, r8
0x14012729e  mov     qword ptr [r8], 0
0x1401272a5  mov     r15, rdx
0x1401272a8  mov     [rbp+pidl], 0
0x1401272b0  lea     r8, [rbp+pidl]; struct _ITEMIDLIST_ABSOLUTE **
0x1401272b4  mov     edx, 0Ah; enum DATAOBJ_GET_ITEM_FLAGS
0x1401272b9  call    ?DataObj_GetIDList@@YAJPEAUIDataObject@@W4DATAOBJ_GET_ITEM_FLAGS@@PEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z; DataObj_GetIDList(IDataObject *,DATAOBJ_GET_ITEM_FLAGS,_ITEMIDLIST_ABSOLUTE * *)
0x1401272be  mov     ebx, eax
0x1401272c0  test    eax, eax
0x1401272c2  js      loc_1401274FA
0x1401272c8  mov     rcx, [rbp+pidl]; pidl
0x1401272cc  lea     r8, [rbp+ppv]; ppv
0x1401272d0  lea     rdx, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x1401272d7  mov     [rbp+ppv], 0
0x1401272df  call    cs:__imp_SHCreateItemFromIDList
0x1401272e6  nop     dword ptr [rax+rax+00h]
0x1401272eb  mov     ebx, eax
0x1401272ed  test    eax, eax
0x1401272ef  js      loc_1401274EA
0x1401272f5  mov     rcx, [rbp+ppv]
0x1401272f9  lea     rdx, [rbp+arg_18]
0x1401272fd  mov     [rbp+var_18], 0
0x140127305  lea     r9, _GUID_000214f9_0000_0000_c000_000000000046
0x14012730c  mov     [rbp+arg_18], 0
0x140127314  lea     r8, BHID_SFUIObject
0x14012731b  mov     qword ptr [rsp+50h+bIgnoreCase], rdx
0x140127320  xor     edx, edx
0x140127322  mov     rax, [rcx]
0x140127325  mov     rax, [rax+18h]
0x140127329  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14012732e  test    eax, eax
0x140127330  js      loc_140127423
0x140127336  mov     rcx, [rbp+arg_18]
0x14012733a  lea     r8, [rbp+var_20]
0x14012733e  xor     edi, edi
0x140127340  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x140127347  mov     [rbp+var_20], rdi
0x14012734b  mov     rax, [rcx]
0x14012734e  mov     rax, [rax]
0x140127351  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140127356  test    eax, eax
0x140127358  js      short loc_14012739D
0x14012735a  mov     rcx, [rbp+var_20]
0x14012735e  lea     r8, [rbp+pv]
0x140127362  xor     esi, esi
0x140127364  mov     ebx, 80040F07h
0x140127369  mov     [rbp+pv], rsi
0x14012736d  call    IPropertyStore_GetString
0x140127372  test    eax, eax
0x140127374  js      short loc_140127389
0x140127376  mov     rcx, [rbp+pv]; pv
0x14012737a  lea     esi, [rdi+1]
0x14012737d  call    cs:__imp_CoTaskMemFree
0x140127384  nop     dword ptr [rax+rax+00h]
0x140127389  mov     rcx, [rbp+var_20]
0x14012738d  mov     rax, [rcx]
0x140127390  mov     rax, [rax+10h]
0x140127394  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140127399  test    esi, esi
0x14012739b  jnz     short loc_14012740A
0x14012739d  mov     rcx, [rbp+arg_18]
0x1401273a1  lea     rdx, [rbp+pv]
0x1401273a5  mov     [rbp+pv], rdi
0x1401273a9  mov     rax, [rcx]
0x1401273ac  mov     rax, [rax+20h]
0x1401273b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401273b5  mov     ebx, eax
0x1401273b7  test    eax, eax
0x1401273b9  js      short loc_14012740A
0x1401273bb  mov     rdx, [rbp+pv]; struct _ITEMIDLIST_ABSOLUTE *
0x1401273bf  lea     r8, [rbp+var_20]; struct _ITEMIDLIST_ABSOLUTE **
0x1401273c3  mov     rcx, [rbp+ppv]; struct IShellItem *
0x1401273c7  mov     [rbp+var_20], rdi
0x1401273cb  call    ?_CacheShortcutDisplayName@@YAJPEAUIShellItem@@PEAU_ITEMIDLIST_ABSOLUTE@@PEAPEAU2@@Z; _CacheShortcutDisplayName(IShellItem *,_ITEMIDLIST_ABSOLUTE *,_ITEMIDLIST_ABSOLUTE * *)
0x1401273d0  mov     ebx, eax
0x1401273d2  test    eax, eax
0x1401273d4  js      short loc_14012740A
0x1401273d6  mov     rcx, [rbp+var_20]; pidl
0x1401273da  lea     r8, [rbp+var_18]; ppv
0x1401273de  lea     rdx, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x1401273e5  call    cs:__imp_SHCreateItemFromIDList
0x1401273ec  nop     dword ptr [rax+rax+00h]
0x1401273f1  mov     rcx, [rbp+var_20]; pidl
0x1401273f5  test    eax, eax
0x1401273f7  mov     ebx, eax
0x1401273f9  cmovns  rdi, [rbp+var_18]
0x1401273fe  call    cs:__imp_ILFree
0x140127405  nop     dword ptr [rax+rax+00h]
0x14012740a  mov     rcx, [rbp+arg_18]
0x14012740e  mov     rax, [rcx]
0x140127411  mov     rax, [rax+10h]
0x140127415  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14012741a  test    ebx, ebx
0x14012741c  jns     short loc_140127427
0x14012741e  jmp     loc_1401274D1
0x140127423  mov     rdi, [rbp+ppv]
0x140127427  mov     rax, [rdi]
0x14012742a  lea     r8, [rbp+var_20]
0x14012742e  lea     rdx, PKEY_FileExtension
0x140127435  mov     [rbp+var_20], 0
0x14012743d  mov     rcx, rdi
0x140127440  mov     rax, [rax+88h]
0x140127447  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14012744c  mov     rcx, [rbp+var_20]; lpString1
0x140127450  test    rcx, rcx
0x140127453  jz      short loc_1401274AB
0x140127455  or      esi, 0FFFFFFFFh
0x140127458  mov     [rsp+50h+bIgnoreCase], 1; bIgnoreCase
0x140127460  mov     r9d, esi; cchCount2
0x140127463  lea     r8, aExe; ".EXE"
0x14012746a  mov     edx, esi; cchCount1
0x14012746c  mov     ebx, 80040F07h
0x140127471  call    cs:__imp_CompareStringOrdinal
0x140127478  nop     dword ptr [rax+rax+00h]
0x14012747d  cmp     eax, 2
0x140127480  jz      short loc_1401274C1
0x140127482  mov     rcx, [rbp+var_20]; lpString1
0x140127486  lea     r8, aMsc; ".MSC"
0x14012748d  mov     r9d, esi; cchCount2
0x140127490  mov     [rsp+50h+bIgnoreCase], 1; bIgnoreCase
0x140127498  mov     edx, esi; cchCount1
0x14012749a  call    cs:__imp_CompareStringOrdinal
0x1401274a1  nop     dword ptr [rax+rax+00h]
0x1401274a6  cmp     eax, 2
0x1401274a9  jz      short loc_1401274C1
0x1401274ab  mov     rax, [rdi]
0x1401274ae  mov     r8, r14
0x1401274b1  mov     rdx, r15
0x1401274b4  mov     rcx, rdi
0x1401274b7  mov     rax, [rax]
0x1401274ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401274bf  mov     ebx, eax
0x1401274c1  mov     rcx, [rbp+var_20]; pv
0x1401274c5  call    cs:__imp_CoTaskMemFree
0x1401274cc  nop     dword ptr [rax+rax+00h]
0x1401274d1  lea     rcx, [rbp+var_18]
0x1401274d5  call    ??$SafeRelease@UIShellItem2@@@@YAXPEAPEAUIShellItem2@@@Z; SafeRelease<IShellItem2>(IShellItem2 * *)
0x1401274da  mov     rcx, [rbp+ppv]
0x1401274de  mov     rax, [rcx]
0x1401274e1  mov     rax, [rax+10h]
0x1401274e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401274ea  mov     rcx, [rbp+pidl]; pidl
0x1401274ee  call    cs:__imp_ILFree
0x1401274f5  nop     dword ptr [rax+rax+00h]
0x1401274fa  mov     eax, ebx
0x1401274fc  mov     rbx, [rsp+50h+arg_0]
0x140127504  add     rsp, 50h
0x140127508  pop     r15
0x14012750a  pop     r14
0x14012750c  pop     rdi
0x14012750d  pop     rsi
0x14012750e  pop     rbp
0x14012750f  retn
```
