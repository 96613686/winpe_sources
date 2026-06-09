# CPidlMgr::GetPropertyStoreFromPIDL(_ITEMIDLIST_RELATIVE const *,_GUID const &,void * *)

- ea: `0x1800286a0`
- end: `0x18002877f`
- name: `?GetPropertyStoreFromPIDL@CPidlMgr@@QEAAJPEFBU_ITEMIDLIST_RELATIVE@@AEBU_GUID@@PEAPEAX@Z`
- size: `223`
- prototype: `__int64 __fastcall(CPidlMgr *__hidden this, const struct _ITEMIDLIST_RELATIVE *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001ed10`

## callees

- `0x180005040`
- `0x180005210`
- `0x1800286a0`
- `0x18003d010`

## import_xrefs

- `api-ms-win-shell-shellcom-l1-1-0!SHCoCreateInstance` at `0x18002870b`
- `api-ms-win-shell-shellcom-l1-1-0!SHCoCreateInstance` at `0x18002870b`

## pseudocode

```c
__int64 __fastcall CPidlMgr::GetPropertyStoreFromPIDL(
        CPidlMgr *this,
        const struct _ITEMIDLIST_RELATIVE *a2,
        const struct _GUID *a3,
        void **a4)
{
  HRESULT IsValidSFItem; // ebx
  struct tagSERIALIZEDPROPSTORAGE *v8; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v9; // [rsp+60h] [rbp+20h] BYREF
  int v10; // [rsp+64h] [rbp+24h]
  void *ppv; // [rsp+78h] [rbp+38h] BYREF

  v10 = HIDWORD(this);
  *a4 = 0;
  v8 = 0;
  v9 = 0;
  IsValidSFItem = CPidlMgr::IsValidSFItem(this, a2, &v8, &v9);
  if ( IsValidSFItem >= 0 )
  {
    ppv = 0;
    IsValidSFItem = SHCoCreateInstance(
                      0,
                      &CLSID_InMemoryPropertyStore,
                      0,
                      &GUID_e318ad57_0aa0_450f_aca5_6fab7103d917,
                      &ppv);
    if ( IsValidSFItem >= 0 )
    {
      IsValidSFItem = (*(__int64 (__fastcall **)(void *, struct tagSERIALIZEDPROPSTORAGE *, _QWORD))(*(_QWORD *)ppv + 32LL))(
                        ppv,
                        v8,
                        v9);
      if ( IsValidSFItem >= 0 )
      {
        IsValidSFItem = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 1);
        if ( IsValidSFItem >= 0 )
          IsValidSFItem = (**(__int64 (__fastcall ***)(void *, const struct _GUID *, void **))ppv)(ppv, a3, a4);
      }
    }
    ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(&ppv);
  }
  return (unsigned int)IsValidSFItem;
}

```

## disassembly

```asm
0x1800286a0  mov     [rsp-18h+arg_8], rbx
0x1800286a5  mov     qword ptr [rsp-18h+arg_0], rcx
0x1800286aa  push    rbp
0x1800286ab  push    rsi
0x1800286ac  push    rdi
0x1800286ad  mov     rbp, rsp
0x1800286b0  sub     rsp, 40h
0x1800286b4  mov     rdi, r9
0x1800286b7  mov     rsi, r8
0x1800286ba  mov     qword ptr [r9], 0
0x1800286c1  mov     [rbp+var_10], 0
0x1800286c9  mov     [rbp+arg_0], 0
0x1800286d0  lea     r9, [rbp+arg_0]; unsigned int *
0x1800286d4  lea     r8, [rbp+var_10]; struct tagSERIALIZEDPROPSTORAGE **
0x1800286d8  call    ?IsValidSFItem@CPidlMgr@@AEAAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEFBUtagSERIALIZEDPROPSTORAGE@@PEAK@Z; CPidlMgr::IsValidSFItem(_ITEMIDLIST_RELATIVE const *,tagSERIALIZEDPROPSTORAGE const * *,ulong *)
0x1800286dd  mov     ebx, eax
0x1800286df  test    eax, eax
0x1800286e1  js      loc_180028770
0x1800286e7  mov     [rbp+arg_18], 0
0x1800286ef  lea     rax, [rbp+arg_18]
0x1800286f3  mov     [rsp+40h+ppv], rax; ppv
0x1800286f8  lea     r9, _GUID_e318ad57_0aa0_450f_aca5_6fab7103d917; riid
0x1800286ff  xor     r8d, r8d; pUnkOuter
0x180028702  lea     rdx, CLSID_InMemoryPropertyStore; pclsid
0x180028709  xor     ecx, ecx; pszCLSID
0x18002870b  call    cs:__imp_SHCoCreateInstance
0x180028711  mov     ebx, eax
0x180028713  test    eax, eax
0x180028715  js      short loc_180028767
0x180028717  mov     rcx, [rbp+arg_18]
0x18002871b  mov     rax, [rcx]
0x18002871e  mov     r8d, [rbp+arg_0]
0x180028722  mov     rdx, [rbp+var_10]
0x180028726  mov     rax, [rax+20h]
0x18002872a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002872f  mov     ebx, eax
0x180028731  test    eax, eax
0x180028733  js      short loc_180028767
0x180028735  mov     rcx, [rbp+arg_18]
0x180028739  mov     rax, [rcx]
0x18002873c  mov     edx, 1
0x180028741  mov     rax, [rax+18h]
0x180028745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002874a  mov     ebx, eax
0x18002874c  test    eax, eax
0x18002874e  js      short loc_180028767
0x180028750  mov     rcx, [rbp+arg_18]
0x180028754  mov     rax, [rcx]
0x180028757  mov     r8, rdi
0x18002875a  mov     rdx, rsi
0x18002875d  mov     rax, [rax]
0x180028760  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028765  mov     ebx, eax
0x180028767  lea     rcx, [rbp+arg_18]
0x18002876b  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x180028770  mov     eax, ebx
0x180028772  mov     rbx, [rsp+40h+arg_8]
0x180028777  add     rsp, 40h
0x18002877b  pop     rdi
0x18002877c  pop     rsi
0x18002877d  pop     rbp
0x18002877e  retn
```
