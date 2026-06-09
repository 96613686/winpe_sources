# CContextMenuExt::_ResolveSyncConflictOnItem(HWND__ *,ushort const *,int *)

- ea: `0x180016ea0`
- end: `0x1800170b7`
- name: `?_ResolveSyncConflictOnItem@CContextMenuExt@@AEAAJPEAUHWND__@@PEBGPEAH@Z`
- size: `535`
- prototype: `int(CContextMenuExt *__hidden this, HWND, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180016268`

## callees

- `0x180016bd0`
- `0x180016ea0`
- `0x18001c484`
- `0x18004d010`

## import_xrefs

- `SHELL32!SHBindToObject` at `0x180016f13`
- `SHELL32!SHBindToObject` at `0x180016f13`
- `SHELL32!SHGetKnownFolderIDList` at `0x180016ee2`
- `SHELL32!SHGetKnownFolderIDList` at `0x180016ee2`
- `SHELL32!__imp_ILFree` at `0x180017061`
- `SHELL32!__imp_ILFree` at `0x18001709a`
- `SHELL32!__imp_ILFree` at `0x180017061`
- `SHELL32!__imp_ILFree` at `0x18001709a`
- `SHLWAPI!__imp_SHInvokeCommandOnContextMenu` at `0x180017035`
- `SHLWAPI!__imp_SHInvokeCommandOnContextMenu` at `0x180017035`

## pseudocode

```c
__int64 __fastcall CContextMenuExt::_ResolveSyncConflictOnItem(
        CContextMenuExt *this,
        HWND a2,
        const unsigned __int16 *a3,
        int *a4)
{
  int ItemSyncConflictStatus; // ebx
  CContextMenuExt *v8; // rcx
  LPITEMIDLIST v9; // rdi
  __int64 v11; // [rsp+40h] [rbp-20h] BYREF
  LPITEMIDLIST pidl; // [rsp+48h] [rbp-18h] BYREF
  struct ISyncMgrConflict *v13; // [rsp+50h] [rbp-10h] BYREF
  LPITEMIDLIST ppidl; // [rsp+58h] [rbp-8h] BYREF
  CContextMenuExt *v15; // [rsp+80h] [rbp+20h] BYREF
  void *ppv; // [rsp+98h] [rbp+38h] BYREF

  v15 = this;
  *a4 = 0;
  ppidl = 0;
  ItemSyncConflictStatus = SHGetKnownFolderIDList(&FOLDERID_ConflictFolder, 0, 0, &ppidl);
  if ( ItemSyncConflictStatus >= 0 )
  {
    ppv = 0;
    ItemSyncConflictStatus = SHBindToObject(0, ppidl, 0, &GUID_59287f5e_bc81_4fca_a7f1_e5a8ecdb1d69, &ppv);
    if ( ItemSyncConflictStatus >= 0 )
    {
      LODWORD(v15) = 0;
      pidl = 0;
      ItemSyncConflictStatus = CContextMenuExt::_QueryItemSyncConflictStatus(
                                 v8,
                                 a3,
                                 (int *)&v15,
                                 (struct IOfflineFilesSyncConflict **)&pidl);
      if ( ItemSyncConflictStatus >= 0 )
      {
        if ( (_DWORD)v15 )
        {
          v9 = pidl;
          v13 = 0;
          ItemSyncConflictStatus = Conflict_CreateSyncMgrConflictFromCscConflict(
                                     (struct IOfflineFilesSyncConflict *)pidl,
                                     &v13);
          if ( ItemSyncConflictStatus >= 0 )
          {
            pidl = 0;
            ItemSyncConflictStatus = (*(__int64 (__fastcall **)(void *, struct ISyncMgrConflict *, LPITEMIDLIST *))(*(_QWORD *)ppv + 24LL))(
                                       ppv,
                                       v13,
                                       &pidl);
            if ( ItemSyncConflictStatus >= 0 )
            {
              v11 = 0;
              ItemSyncConflictStatus = (**(__int64 (__fastcall ***)(void *, GUID *, __int64 *))ppv)(
                                         ppv,
                                         &GUID_000214e6_0000_0000_c000_000000000046,
                                         &v11);
              if ( ItemSyncConflictStatus >= 0 )
              {
                v15 = 0;
                ItemSyncConflictStatus = (*(__int64 (__fastcall **)(__int64, HWND, __int64, LPITEMIDLIST *, GUID *, _QWORD, CContextMenuExt **))(*(_QWORD *)v11 + 80LL))(
                                           v11,
                                           a2,
                                           1,
                                           &pidl,
                                           &GUID_000214e4_0000_0000_c000_000000000046,
                                           0,
                                           &v15);
                if ( ItemSyncConflictStatus >= 0 )
                {
                  ItemSyncConflictStatus = SHInvokeCommandOnContextMenu(0, 0, v15, 0, "resolve");
                  (*(void (__fastcall **)(CContextMenuExt *))(*(_QWORD *)v15 + 16LL))(v15);
                }
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
              }
              ILFree(pidl);
            }
            ((void (__fastcall *)(struct ISyncMgrConflict *))v13->lpVtbl->Release)(v13);
          }
          (*(void (__fastcall **)(LPITEMIDLIST))(*(_QWORD *)&v9->mkid.cb + 16LL))(v9);
        }
        else
        {
          *a4 = 1;
        }
      }
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    ILFree(ppidl);
  }
  return (unsigned int)ItemSyncConflictStatus;
}

```

## disassembly

```asm
0x180016ea0  mov     [rsp-18h+arg_8], rbx
0x180016ea5  mov     [rsp-18h+arg_10], rsi
0x180016eaa  mov     [rsp-18h+arg_0], rcx
0x180016eaf  push    rbp
0x180016eb0  push    rdi
0x180016eb1  push    r14
0x180016eb3  mov     rbp, rsp
0x180016eb6  sub     rsp, 60h
0x180016eba  mov     rdi, r9
0x180016ebd  mov     dword ptr [r9], 0
0x180016ec4  mov     rsi, r8
0x180016ec7  mov     [rbp+ppidl], 0
0x180016ecf  mov     r14, rdx
0x180016ed2  lea     r9, [rbp+ppidl]; ppidl
0x180016ed6  xor     r8d, r8d; hToken
0x180016ed9  lea     rcx, FOLDERID_ConflictFolder; rfid
0x180016ee0  xor     edx, edx; dwFlags
0x180016ee2  call    cs:__imp_SHGetKnownFolderIDList
0x180016ee8  mov     ebx, eax
0x180016eea  test    eax, eax
0x180016eec  js      loc_1800170A0
0x180016ef2  mov     rdx, [rbp+ppidl]; pidl
0x180016ef6  lea     rax, [rbp+arg_18]
0x180016efa  lea     r9, _GUID_59287f5e_bc81_4fca_a7f1_e5a8ecdb1d69; riid
0x180016f01  mov     [rsp+60h+ppv], rax; ppv
0x180016f06  xor     r8d, r8d; pbc
0x180016f09  mov     [rbp+arg_18], 0
0x180016f11  xor     ecx, ecx; psf
0x180016f13  call    cs:__imp_SHBindToObject
0x180016f19  mov     ebx, eax
0x180016f1b  test    eax, eax
0x180016f1d  js      loc_180017096
0x180016f23  lea     r9, [rbp+pidl]; struct IOfflineFilesSyncConflict **
0x180016f27  mov     dword ptr [rbp+arg_0], 0
0x180016f2e  lea     r8, [rbp+arg_0]; int *
0x180016f32  mov     [rbp+pidl], 0
0x180016f3a  mov     rdx, rsi; unsigned __int16 *
0x180016f3d  call    ?_QueryItemSyncConflictStatus@CContextMenuExt@@AEAAJPEBGPEAHPEAPEAUIOfflineFilesSyncConflict@@@Z; CContextMenuExt::_QueryItemSyncConflictStatus(ushort const *,int *,IOfflineFilesSyncConflict * *)
0x180016f42  mov     ebx, eax
0x180016f44  test    eax, eax
0x180016f46  js      loc_180017086
0x180016f4c  cmp     dword ptr [rbp+arg_0], 0
0x180016f50  jnz     short loc_180016F5D
0x180016f52  mov     dword ptr [rdi], 1
0x180016f58  jmp     loc_180017086
0x180016f5d  mov     rdi, [rbp+pidl]
0x180016f61  lea     rdx, [rbp+var_10]; struct ISyncMgrConflict **
0x180016f65  mov     rcx, rdi; struct IOfflineFilesSyncConflict *
0x180016f68  mov     [rbp+var_10], 0
0x180016f70  call    ?Conflict_CreateSyncMgrConflictFromCscConflict@@YAJPEAUIOfflineFilesSyncConflict@@PEAPEAUISyncMgrConflict@@@Z; Conflict_CreateSyncMgrConflictFromCscConflict(IOfflineFilesSyncConflict *,ISyncMgrConflict * *)
0x180016f75  mov     ebx, eax
0x180016f77  test    eax, eax
0x180016f79  js      loc_180017077
0x180016f7f  mov     rcx, [rbp+arg_18]
0x180016f83  lea     r8, [rbp+pidl]
0x180016f87  mov     rdx, [rbp+var_10]
0x180016f8b  mov     [rbp+pidl], 0
0x180016f93  mov     rax, [rcx]
0x180016f96  mov     rax, [rax+18h]
0x180016f9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f9f  mov     ebx, eax
0x180016fa1  test    eax, eax
0x180016fa3  js      loc_180017067
0x180016fa9  mov     rcx, [rbp+arg_18]
0x180016fad  lea     r8, [rbp+var_20]
0x180016fb1  mov     [rbp+var_20], 0
0x180016fb9  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046
0x180016fc0  mov     rax, [rcx]
0x180016fc3  mov     rax, [rax]
0x180016fc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fcb  mov     ebx, eax
0x180016fcd  test    eax, eax
0x180016fcf  js      loc_18001705D
0x180016fd5  mov     rcx, [rbp+var_20]
0x180016fd9  lea     rdx, [rbp+arg_0]
0x180016fdd  mov     [rsp+60h+var_30], rdx
0x180016fe2  lea     r9, [rbp+pidl]
0x180016fe6  mov     [rbp+arg_0], 0
0x180016fee  lea     rdx, _GUID_000214e4_0000_0000_c000_000000000046
0x180016ff5  mov     [rsp+60h+var_38], 0
0x180016ffe  mov     r8d, 1
0x180017004  mov     rax, [rcx]
0x180017007  mov     [rsp+60h+ppv], rdx
0x18001700c  mov     rdx, r14
0x18001700f  mov     rax, [rax+50h]
0x180017013  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017018  mov     ebx, eax
0x18001701a  test    eax, eax
0x18001701c  js      short loc_18001704D
0x18001701e  mov     r8, [rbp+arg_0]
0x180017022  lea     rax, aResolve; "resolve"
0x180017029  xor     r9d, r9d
0x18001702c  mov     [rsp+60h+ppv], rax
0x180017031  xor     edx, edx
0x180017033  xor     ecx, ecx
0x180017035  call    cs:__imp_SHInvokeCommandOnContextMenu
0x18001703b  mov     rcx, [rbp+arg_0]
0x18001703f  mov     ebx, eax
0x180017041  mov     rax, [rcx]
0x180017044  mov     rax, [rax+10h]
0x180017048  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001704d  mov     rcx, [rbp+var_20]
0x180017051  mov     rax, [rcx]
0x180017054  mov     rax, [rax+10h]
0x180017058  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001705d  mov     rcx, [rbp+pidl]; pidl
0x180017061  call    cs:__imp_ILFree
0x180017067  mov     rcx, [rbp+var_10]
0x18001706b  mov     rax, [rcx]
0x18001706e  mov     rax, [rax+10h]
0x180017072  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017077  mov     rax, [rdi]
0x18001707a  mov     rcx, rdi
0x18001707d  mov     rax, [rax+10h]
0x180017081  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017086  mov     rcx, [rbp+arg_18]
0x18001708a  mov     rax, [rcx]
0x18001708d  mov     rax, [rax+10h]
0x180017091  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017096  mov     rcx, [rbp+ppidl]; pidl
0x18001709a  call    cs:__imp_ILFree
0x1800170a0  lea     r11, [rsp+60h+var_s0]
0x1800170a5  mov     eax, ebx
0x1800170a7  mov     rbx, [r11+28h]
0x1800170ab  mov     rsi, [r11+30h]
0x1800170af  mov     rsp, r11
0x1800170b2  pop     r14
0x1800170b4  pop     rdi
0x1800170b5  pop     rbp
0x1800170b6  retn
```
