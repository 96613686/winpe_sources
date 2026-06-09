# COfflinePropSheetExt::_ResolveSyncConflictOnItem(void)

- ea: `0x180021664`
- end: `0x180021863`
- name: `?_ResolveSyncConflictOnItem@COfflinePropSheetExt@@AEAAJXZ`
- size: `511`
- prototype: `__int64 __fastcall(COfflinePropSheetExt *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180020630`
- `0x1800212fc`

## callees

- `0x18001c484`
- `0x180021398`
- `0x18002151c`
- `0x180021664`
- `0x18004d010`

## import_xrefs

- `SHELL32!SHBindToObject` at `0x1800216bf`
- `SHELL32!SHBindToObject` at `0x1800216bf`
- `SHELL32!SHGetKnownFolderIDList` at `0x18002168e`
- `SHELL32!SHGetKnownFolderIDList` at `0x18002168e`
- `SHELL32!__imp_ILFree` at `0x180021812`
- `SHELL32!__imp_ILFree` at `0x18002184b`
- `SHELL32!__imp_ILFree` at `0x180021812`
- `SHELL32!__imp_ILFree` at `0x18002184b`
- `SHLWAPI!__imp_SHInvokeCommandOnContextMenu` at `0x1800217e6`
- `SHLWAPI!__imp_SHInvokeCommandOnContextMenu` at `0x1800217e6`

## pseudocode

```c
__int64 __fastcall COfflinePropSheetExt::_ResolveSyncConflictOnItem(COfflinePropSheetExt *this)
{
  int refreshed; // ebx
  struct IOfflineFilesSyncConflict *v3; // rdi
  LPITEMIDLIST pidl; // [rsp+40h] [rbp-20h] BYREF
  struct ISyncMgrConflict *v6; // [rsp+48h] [rbp-18h] BYREF
  LPITEMIDLIST ppidl; // [rsp+50h] [rbp-10h] BYREF
  __int64 v8; // [rsp+88h] [rbp+28h] BYREF
  void *ppv; // [rsp+90h] [rbp+30h] BYREF
  struct IOfflineFilesSyncConflict *v10; // [rsp+98h] [rbp+38h] BYREF

  ppidl = 0;
  refreshed = SHGetKnownFolderIDList(&FOLDERID_ConflictFolder, 0, 0, &ppidl);
  if ( refreshed >= 0 )
  {
    ppv = 0;
    refreshed = SHBindToObject(0, ppidl, 0, &GUID_59287f5e_bc81_4fca_a7f1_e5a8ecdb1d69, &ppv);
    if ( refreshed >= 0 )
    {
      LODWORD(v8) = 0;
      v10 = 0;
      refreshed = COfflinePropSheetExt::_QueryItemSyncConflictStatus(this, (int *)&v8, &v10);
      if ( refreshed >= 0 )
      {
        if ( (_DWORD)v8 )
        {
          v3 = v10;
          v6 = 0;
          refreshed = Conflict_CreateSyncMgrConflictFromCscConflict(v10, &v6);
          if ( refreshed >= 0 )
          {
            pidl = 0;
            refreshed = (*(__int64 (__fastcall **)(void *, struct ISyncMgrConflict *, LPITEMIDLIST *))(*(_QWORD *)ppv + 24LL))(
                          ppv,
                          v6,
                          &pidl);
            if ( refreshed >= 0 )
            {
              v10 = 0;
              refreshed = (**(__int64 (__fastcall ***)(void *, GUID *, struct IOfflineFilesSyncConflict **))ppv)(
                            ppv,
                            &GUID_000214e6_0000_0000_c000_000000000046,
                            &v10);
              if ( refreshed >= 0 )
              {
                v8 = 0;
                refreshed = (*(__int64 (__fastcall **)(struct IOfflineFilesSyncConflict *, _QWORD, __int64, LPITEMIDLIST *, GUID *, _QWORD, __int64 *))(*(_QWORD *)v10 + 80LL))(
                              v10,
                              *((_QWORD *)this + 5),
                              1,
                              &pidl,
                              &GUID_000214e4_0000_0000_c000_000000000046,
                              0,
                              &v8);
                if ( refreshed >= 0 )
                {
                  refreshed = SHInvokeCommandOnContextMenu(0, 0, v8, 0, "resolve");
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
                }
                (*(void (__fastcall **)(struct IOfflineFilesSyncConflict *))(*(_QWORD *)v10 + 16LL))(v10);
              }
              ILFree(pidl);
            }
            ((void (__fastcall *)(struct ISyncMgrConflict *))v6->lpVtbl->Release)(v6);
          }
          (*(void (__fastcall **)(struct IOfflineFilesSyncConflict *))(*(_QWORD *)v3 + 16LL))(v3);
        }
        else
        {
          refreshed = COfflinePropSheetExt::_RefreshPropPage(this);
        }
      }
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    ILFree(ppidl);
  }
  return (unsigned int)refreshed;
}

```

## disassembly

```asm
0x180021664  mov     [rsp-18h+arg_0], rbx
0x180021669  push    rbp
0x18002166a  push    rsi
0x18002166b  push    rdi
0x18002166c  mov     rbp, rsp
0x18002166f  sub     rsp, 60h
0x180021673  mov     rsi, rcx
0x180021676  mov     [rbp+ppidl], 0
0x18002167e  lea     rcx, FOLDERID_ConflictFolder; rfid
0x180021685  xor     r8d, r8d; hToken
0x180021688  lea     r9, [rbp+ppidl]; ppidl
0x18002168c  xor     edx, edx; dwFlags
0x18002168e  call    cs:__imp_SHGetKnownFolderIDList
0x180021694  mov     ebx, eax
0x180021696  test    eax, eax
0x180021698  js      loc_180021851
0x18002169e  mov     rdx, [rbp+ppidl]; pidl
0x1800216a2  lea     rax, [rbp+arg_10]
0x1800216a6  lea     r9, _GUID_59287f5e_bc81_4fca_a7f1_e5a8ecdb1d69; riid
0x1800216ad  mov     [rsp+60h+ppv], rax; ppv
0x1800216b2  xor     r8d, r8d; pbc
0x1800216b5  mov     [rbp+arg_10], 0
0x1800216bd  xor     ecx, ecx; psf
0x1800216bf  call    cs:__imp_SHBindToObject
0x1800216c5  mov     ebx, eax
0x1800216c7  test    eax, eax
0x1800216c9  js      loc_180021847
0x1800216cf  lea     r8, [rbp+arg_18]; struct IOfflineFilesSyncConflict **
0x1800216d3  mov     dword ptr [rbp+arg_8], 0
0x1800216da  lea     rdx, [rbp+arg_8]; int *
0x1800216de  mov     [rbp+arg_18], 0
0x1800216e6  mov     rcx, rsi; this
0x1800216e9  call    ?_QueryItemSyncConflictStatus@COfflinePropSheetExt@@AEAAJPEAHPEAPEAUIOfflineFilesSyncConflict@@@Z; COfflinePropSheetExt::_QueryItemSyncConflictStatus(int *,IOfflineFilesSyncConflict * *)
0x1800216ee  mov     ebx, eax
0x1800216f0  test    eax, eax
0x1800216f2  js      loc_180021837
0x1800216f8  cmp     dword ptr [rbp+arg_8], 0
0x1800216fc  jnz     short loc_18002170D
0x1800216fe  mov     rcx, rsi; this
0x180021701  call    ?_RefreshPropPage@COfflinePropSheetExt@@AEAAJXZ; COfflinePropSheetExt::_RefreshPropPage(void)
0x180021706  mov     ebx, eax
0x180021708  jmp     loc_180021837
0x18002170d  mov     rdi, [rbp+arg_18]
0x180021711  lea     rdx, [rbp+var_18]; struct ISyncMgrConflict **
0x180021715  mov     rcx, rdi; struct IOfflineFilesSyncConflict *
0x180021718  mov     [rbp+var_18], 0
0x180021720  call    ?Conflict_CreateSyncMgrConflictFromCscConflict@@YAJPEAUIOfflineFilesSyncConflict@@PEAPEAUISyncMgrConflict@@@Z; Conflict_CreateSyncMgrConflictFromCscConflict(IOfflineFilesSyncConflict *,ISyncMgrConflict * *)
0x180021725  mov     ebx, eax
0x180021727  test    eax, eax
0x180021729  js      loc_180021828
0x18002172f  mov     rcx, [rbp+arg_10]
0x180021733  lea     r8, [rbp+pidl]
0x180021737  mov     rdx, [rbp+var_18]
0x18002173b  mov     [rbp+pidl], 0
0x180021743  mov     rax, [rcx]
0x180021746  mov     rax, [rax+18h]
0x18002174a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002174f  mov     ebx, eax
0x180021751  test    eax, eax
0x180021753  js      loc_180021818
0x180021759  mov     rcx, [rbp+arg_10]
0x18002175d  lea     r8, [rbp+arg_18]
0x180021761  mov     [rbp+arg_18], 0
0x180021769  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046
0x180021770  mov     rax, [rcx]
0x180021773  mov     rax, [rax]
0x180021776  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002177b  mov     ebx, eax
0x18002177d  test    eax, eax
0x18002177f  js      loc_18002180E
0x180021785  mov     rcx, [rbp+arg_18]
0x180021789  lea     rdx, [rbp+arg_8]
0x18002178d  mov     [rsp+60h+var_30], rdx
0x180021792  lea     r9, [rbp+pidl]
0x180021796  mov     [rbp+arg_8], 0
0x18002179e  lea     rdx, _GUID_000214e4_0000_0000_c000_000000000046
0x1800217a5  mov     [rsp+60h+var_38], 0
0x1800217ae  mov     r8d, 1
0x1800217b4  mov     rax, [rcx]
0x1800217b7  mov     [rsp+60h+ppv], rdx
0x1800217bc  mov     rdx, [rsi+28h]
0x1800217c0  mov     rax, [rax+50h]
0x1800217c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800217c9  mov     ebx, eax
0x1800217cb  test    eax, eax
0x1800217cd  js      short loc_1800217FE
0x1800217cf  mov     r8, [rbp+arg_8]
0x1800217d3  lea     rax, aResolve; "resolve"
0x1800217da  xor     r9d, r9d
0x1800217dd  mov     [rsp+60h+ppv], rax
0x1800217e2  xor     edx, edx
0x1800217e4  xor     ecx, ecx
0x1800217e6  call    cs:__imp_SHInvokeCommandOnContextMenu
0x1800217ec  mov     rcx, [rbp+arg_8]
0x1800217f0  mov     ebx, eax
0x1800217f2  mov     rax, [rcx]
0x1800217f5  mov     rax, [rax+10h]
0x1800217f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800217fe  mov     rcx, [rbp+arg_18]
0x180021802  mov     rax, [rcx]
0x180021805  mov     rax, [rax+10h]
0x180021809  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002180e  mov     rcx, [rbp+pidl]; pidl
0x180021812  call    cs:__imp_ILFree
0x180021818  mov     rcx, [rbp+var_18]
0x18002181c  mov     rax, [rcx]
0x18002181f  mov     rax, [rax+10h]
0x180021823  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021828  mov     rax, [rdi]
0x18002182b  mov     rcx, rdi
0x18002182e  mov     rax, [rax+10h]
0x180021832  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021837  mov     rcx, [rbp+arg_10]
0x18002183b  mov     rax, [rcx]
0x18002183e  mov     rax, [rax+10h]
0x180021842  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021847  mov     rcx, [rbp+ppidl]; pidl
0x18002184b  call    cs:__imp_ILFree
0x180021851  mov     eax, ebx
0x180021853  mov     rbx, [rsp+60h+arg_0]
0x18002185b  add     rsp, 60h
0x18002185f  pop     rdi
0x180021860  pop     rsi
0x180021861  pop     rbp
0x180021862  retn
```
