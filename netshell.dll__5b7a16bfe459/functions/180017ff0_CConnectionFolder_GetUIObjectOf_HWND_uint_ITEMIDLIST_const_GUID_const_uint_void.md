# CConnectionFolder::GetUIObjectOf(HWND__ *,uint,_ITEMIDLIST const * *,_GUID const &,uint *,void * *)

- ea: `0x180017ff0`
- end: `0x1800182fb`
- name: `?GetUIObjectOf@CConnectionFolder@@UEAAJPEAUHWND__@@IPEAPEFBU_ITEMIDLIST@@AEBU_GUID@@PEAIPEAPEAX@Z`
- size: `779`
- prototype: `int(CConnectionFolder *__hidden this, HWND, unsigned int, const struct _ITEMIDLIST **, const struct _GUID *, unsigned int *, void **)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003700`
- `0x180004310`
- `0x180005630`
- `0x180005d80`
- `0x18000a204`
- `0x18001644c`
- `0x180017ff0`
- `0x180019344`
- `0x18001ae14`
- `0x18004e89c`
- `0x180065010`

## import_xrefs

- `SHLWAPI!AssocCreate` at `0x18001813f`
- `SHLWAPI!AssocCreate` at `0x18001813f`
- `SHELL32!__imp_CIDLData_CreateFromIDArray` at `0x18001806f`
- `SHELL32!__imp_CIDLData_CreateFromIDArray` at `0x18001806f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall CConnectionFolder::GetUIObjectOf(
        unsigned __int64 this,
        HWND a2,
        UINT a3,
        const struct _ITEMIDLIST **a4,
        const struct _GUID *a5,
        unsigned int *a6,
        IDataObject **ppdtobj)
{
  int v9; // r15d
  HRESULT ConnectionsFolderPidl; // ebx
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  const struct _GUID *v19; // rcx
  int Instance; // eax
  void *ppv; // [rsp+38h] [rbp-70h] BYREF
  CLSID clsid; // [rsp+40h] [rbp-68h] BYREF

  v9 = (int)a2;
  ConnectionsFolderPidl = -2147467262;
  if ( !a3 )
    goto LABEL_44;
  v12 = *(_QWORD *)&a5->Data1 - *(_QWORD *)&IID_IDataObject.Data1;
  if ( *(_QWORD *)&a5->Data1 == *(_QWORD *)&IID_IDataObject.Data1 )
    v12 = *(_QWORD *)a5->Data4 - *(_QWORD *)IID_IDataObject.Data4;
  if ( !v12 )
  {
    if ( !*(_QWORD *)(this + 88) )
    {
      ConnectionsFolderPidl = HrGetConnectionsFolderPidl(this + 88);
      if ( ConnectionsFolderPidl < 0 )
        goto LABEL_44;
    }
    ConnectionsFolderPidl = CIDLData_CreateFromIDArray(*(LPCITEMIDLIST *)(this + 88), a3, a4, ppdtobj);
    goto LABEL_43;
  }
  v13 = *(_QWORD *)&a5->Data1 - *(_QWORD *)&IID_IContextMenu.Data1;
  if ( *(_QWORD *)&a5->Data1 == *(_QWORD *)&IID_IContextMenu.Data1 )
    v13 = *(_QWORD *)a5->Data4 - *(_QWORD *)IID_IContextMenu.Data4;
  if ( !v13 )
  {
    std::vector<CPConFoldPidl<ConFoldPidl_v3>>::vector<CPConFoldPidl<ConFoldPidl_v3>>(&clsid);
    if ( (int)PConfoldPidlVecFromItemIdListArray(a4, a3, &clsid) < 0 )
      goto LABEL_32;
    Instance = CConnectionFolderContextMenu::CreateInstance(
                 this != 16 ? this : 0,
                 (_DWORD)ppdtobj,
                 1,
                 v9,
                 (__int64)&clsid,
                 this & -(__int64)(this != 16));
    if ( Instance < 0 )
      Instance = -2147467262;
    ConnectionsFolderPidl = Instance;
    goto LABEL_42;
  }
  v14 = *(_QWORD *)&a5->Data1 - *(_QWORD *)&IID_IExtractIconA.Data1;
  if ( *(_QWORD *)&a5->Data1 == *(_QWORD *)&IID_IExtractIconA.Data1 )
    v14 = *(_QWORD *)a5->Data4 - *(_QWORD *)IID_IExtractIconA.Data4;
  if ( !v14 )
    goto LABEL_36;
  v15 = *(_QWORD *)&a5->Data1 - *(_QWORD *)&IID_IExtractIconW.Data1;
  if ( *(_QWORD *)&a5->Data1 == *(_QWORD *)&IID_IExtractIconW.Data1 )
    v15 = *(_QWORD *)a5->Data4 - *(_QWORD *)IID_IExtractIconW.Data4;
  if ( v15 )
  {
    v16 = *(_QWORD *)&a5->Data1 - *(_QWORD *)&IID_IDropTarget.Data1;
    if ( *(_QWORD *)&a5->Data1 == *(_QWORD *)&IID_IDropTarget.Data1 )
      v16 = *(_QWORD *)a5->Data4 - *(_QWORD *)IID_IDropTarget.Data4;
    if ( !v16 )
      goto LABEL_44;
    v17 = *(_QWORD *)&a5->Data1 - *(_QWORD *)&IID_IQueryAssociations.Data1;
    if ( *(_QWORD *)&a5->Data1 == *(_QWORD *)&IID_IQueryAssociations.Data1 )
      v17 = *(_QWORD *)a5->Data4 - *(_QWORD *)IID_IQueryAssociations.Data4;
    if ( !v17 )
    {
      ppv = 0;
      clsid = CLSID_QueryAssociations;
      ConnectionsFolderPidl = AssocCreate(&clsid, &IID_IQueryAssociations, &ppv);
      if ( ConnectionsFolderPidl >= 0 )
      {
        ConnectionsFolderPidl = (*(__int64 (__fastcall **)(void *, _QWORD, const wchar_t *, _QWORD, _QWORD))(*(_QWORD *)ppv + 24LL))(
                                  ppv,
                                  0,
                                  L"NetworkConnections",
                                  0,
                                  0);
        if ( ConnectionsFolderPidl >= 0 )
          ConnectionsFolderPidl = (**(__int64 (__fastcall ***)(void *, GUID *, IDataObject **))ppv)(
                                    ppv,
                                    &IID_IQueryAssociations,
                                    ppdtobj);
      }
      ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>((__int64 *)&ppv);
      goto LABEL_43;
    }
    v18 = *(_QWORD *)&a5->Data1 - *(_QWORD *)&IID_IQueryInfo.Data1;
    if ( *(_QWORD *)&a5->Data1 == *(_QWORD *)&IID_IQueryInfo.Data1 )
      v18 = *(_QWORD *)a5->Data4 - *(_QWORD *)IID_IQueryInfo.Data4;
    if ( v18 )
      goto LABEL_44;
    if ( a3 == 1 )
    {
      std::vector<CPConFoldPidl<ConFoldPidl_v3>>::vector<CPConFoldPidl<ConFoldPidl_v3>>(&clsid);
      if ( (int)PConfoldPidlVecFromItemIdListArray(a4, 1, &clsid) < 0 )
      {
LABEL_32:
        std::vector<CPConFoldPidl<ConFoldPidl_v3>>::~vector<CPConFoldPidl<ConFoldPidl_v3>>((__int64)&clsid);
        return 2147942487LL;
      }
      ConnectionsFolderPidl = CConnectionFolderQueryInfo::CreateInstance(v19, (void **)ppdtobj);
      if ( ConnectionsFolderPidl >= 0 )
      {
        CPConFoldPidl<ConFoldPidl_v3>::operator=(&(*ppdtobj)[8], *(_QWORD *)&clsid.Data1);
        ConnectionsFolderPidl = 0;
      }
LABEL_42:
      std::vector<CPConFoldPidl<ConFoldPidl_v3>>::~vector<CPConFoldPidl<ConFoldPidl_v3>>((__int64)&clsid);
    }
  }
  else
  {
LABEL_36:
    if ( a3 != 1 )
    {
LABEL_44:
      *ppdtobj = 0;
      return (unsigned int)ConnectionsFolderPidl;
    }
    ConnectionsFolderPidl = CConnectionFolderExtractIcon::CreateInstance(*a4, a5, (void **)ppdtobj);
  }
LABEL_43:
  if ( ConnectionsFolderPidl < 0 )
    goto LABEL_44;
  return (unsigned int)ConnectionsFolderPidl;
}

```

## disassembly

```asm
0x180017ff0  mov     [rsp+arg_0], rbx
0x180017ff5  mov     [rsp+arg_8], rsi
0x180017ffa  push    rdi
0x180017ffb  push    r14
0x180017ffd  push    r15
0x180017fff  sub     rsp, 90h
0x180018006  mov     r14, r9
0x180018009  mov     esi, r8d
0x18001800c  mov     r15, rdx
0x18001800f  mov     rdi, rcx
0x180018012  mov     ebx, 80004002h
0x180018017  cmp     r8d, 1
0x18001801b  jb      loc_1800182C3
0x180018021  mov     rdx, [rsp+0A8h+arg_20]; struct _GUID *
0x180018029  mov     rax, [rdx]
0x18001802c  sub     rax, qword ptr cs:IID_IDataObject.Data1
0x180018033  jnz     short loc_180018040
0x180018035  mov     rax, [rdx+8]
0x180018039  sub     rax, qword ptr cs:IID_IDataObject.Data4
0x180018040  test    rax, rax
0x180018043  jnz     short loc_18001807C
0x180018045  cmp     [rcx+58h], rax
0x180018049  jnz     short loc_18001805E
0x18001804b  add     rcx, 58h ; 'X'
0x18001804f  call    ?HrGetConnectionsFolderPidl@@YAJAEAV?$CPConFoldPidl@VConFoldPidlFolder@@@@@Z; HrGetConnectionsFolderPidl(CPConFoldPidl<ConFoldPidlFolder> &)
0x180018054  mov     ebx, eax
0x180018056  test    eax, eax
0x180018058  js      loc_1800182C3
0x18001805e  mov     r9, [rsp+0A8h+ppdtobj]; ppdtobj
0x180018066  mov     r8, r14; apidl
0x180018069  mov     edx, esi; cidl
0x18001806b  mov     rcx, [rdi+58h]; pidlFolder
0x18001806f  call    cs:__imp_CIDLData_CreateFromIDArray
0x180018075  mov     ebx, eax
0x180018077  jmp     loc_1800182BF
0x18001807c  mov     rax, [rdx]
0x18001807f  sub     rax, qword ptr cs:IID_IContextMenu.Data1
0x180018086  jnz     short loc_180018093
0x180018088  mov     rax, [rdx+8]
0x18001808c  sub     rax, qword ptr cs:IID_IContextMenu.Data4
0x180018093  test    rax, rax
0x180018096  jz      loc_18001824D
0x18001809c  mov     rax, [rdx]
0x18001809f  sub     rax, qword ptr cs:IID_IExtractIconA.Data1
0x1800180a6  jnz     short loc_1800180B3
0x1800180a8  mov     rax, [rdx+8]
0x1800180ac  sub     rax, qword ptr cs:IID_IExtractIconA.Data4
0x1800180b3  test    rax, rax
0x1800180b6  jz      loc_180018230
0x1800180bc  mov     rax, [rdx]
0x1800180bf  sub     rax, qword ptr cs:IID_IExtractIconW.Data1
0x1800180c6  jnz     short loc_1800180D3
0x1800180c8  mov     rax, [rdx+8]
0x1800180cc  sub     rax, qword ptr cs:IID_IExtractIconW.Data4
0x1800180d3  test    rax, rax
0x1800180d6  jz      loc_180018230
0x1800180dc  mov     rax, [rdx]
0x1800180df  sub     rax, qword ptr cs:IID_IDropTarget.Data1
0x1800180e6  jnz     short loc_1800180F3
0x1800180e8  mov     rax, [rdx+8]
0x1800180ec  sub     rax, qword ptr cs:IID_IDropTarget.Data4
0x1800180f3  test    rax, rax
0x1800180f6  jz      loc_1800182C3
0x1800180fc  mov     rax, [rdx]
0x1800180ff  sub     rax, qword ptr cs:IID_IQueryAssociations.Data1
0x180018106  jnz     short loc_180018113
0x180018108  mov     rax, [rdx+8]
0x18001810c  sub     rax, qword ptr cs:IID_IQueryAssociations.Data4
0x180018113  test    rax, rax
0x180018116  jnz     loc_1800181A7
0x18001811c  mov     [rsp+0A8h+ppv], rax
0x180018121  movups  xmm0, xmmword ptr cs:CLSID_QueryAssociations.Data1
0x180018128  movdqu  xmmword ptr [rsp+0A8h+clsid.Data1], xmm0
0x18001812e  lea     r8, [rsp+0A8h+ppv]; ppv
0x180018133  lea     rdx, IID_IQueryAssociations; riid
0x18001813a  lea     rcx, [rsp+0A8h+clsid]; clsid
0x18001813f  call    cs:__imp_AssocCreate
0x180018145  mov     ebx, eax
0x180018147  test    eax, eax
0x180018149  js      short loc_180018198
0x18001814b  mov     rcx, [rsp+0A8h+ppv]
0x180018150  mov     rax, [rcx]
0x180018153  mov     [rsp+0A8h+var_88], 0
0x18001815c  xor     r9d, r9d
0x18001815f  lea     r8, aNetworkconnect_0; "NetworkConnections"
0x180018166  xor     edx, edx
0x180018168  mov     rax, [rax+18h]
0x18001816c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018171  mov     ebx, eax
0x180018173  test    eax, eax
0x180018175  js      short loc_180018198
0x180018177  mov     rcx, [rsp+0A8h+ppv]
0x18001817c  mov     rax, [rcx]
0x18001817f  mov     r8, [rsp+0A8h+ppdtobj]
0x180018187  lea     rdx, IID_IQueryAssociations
0x18001818e  mov     rax, [rax]
0x180018191  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018196  mov     ebx, eax
0x180018198  lea     rcx, [rsp+0A8h+ppv]
0x18001819d  call    ??1?$CComPtrBase@UIUPnPService@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>(void)
0x1800181a2  jmp     loc_1800182BF
0x1800181a7  mov     rax, [rdx]
0x1800181aa  sub     rax, qword ptr cs:IID_IQueryInfo.Data1
0x1800181b1  jnz     short loc_1800181BE
0x1800181b3  mov     rax, [rdx+8]
0x1800181b7  sub     rax, qword ptr cs:IID_IQueryInfo.Data4
0x1800181be  test    rax, rax
0x1800181c1  jnz     loc_1800182C3
0x1800181c7  cmp     esi, 1
0x1800181ca  jnz     loc_1800182BF
0x1800181d0  lea     rcx, [rsp+0A8h+clsid]
0x1800181d5  call    ??0?$vector@V?$CPConFoldPidl@VConFoldPidl_v3@@@@V?$allocator@V?$CPConFoldPidl@VConFoldPidl_v3@@@@@std@@@std@@QEAA@XZ; std::vector<CPConFoldPidl<ConFoldPidl_v3>>::vector<CPConFoldPidl<ConFoldPidl_v3>>(void)
0x1800181da  nop
0x1800181db  lea     r8, [rsp+0A8h+clsid]
0x1800181e0  mov     edx, esi
0x1800181e2  mov     rcx, r14
0x1800181e5  call    ?PConfoldPidlVecFromItemIdListArray@@YAJPEAPEFBU_ITEMIDLIST@@KAEAV?$vector@V?$CPConFoldPidl@VConFoldPidl_v3@@@@V?$allocator@V?$CPConFoldPidl@VConFoldPidl_v3@@@@@std@@@std@@@Z; PConfoldPidlVecFromItemIdListArray(_ITEMIDLIST const * *,ulong,std::vector<CPConFoldPidl<ConFoldPidl_v3>> &)
0x1800181ea  test    eax, eax
0x1800181ec  jns     short loc_180018202
0x1800181ee  lea     rcx, [rsp+0A8h+clsid]
0x1800181f3  call    ??1?$vector@V?$CPConFoldPidl@VConFoldPidl_v3@@@@V?$allocator@V?$CPConFoldPidl@VConFoldPidl_v3@@@@@std@@@std@@QEAA@XZ; std::vector<CPConFoldPidl<ConFoldPidl_v3>>::~vector<CPConFoldPidl<ConFoldPidl_v3>>(void)
0x1800181f8  mov     eax, 80070057h
0x1800181fd  jmp     loc_1800182E1
0x180018202  mov     rdi, [rsp+0A8h+ppdtobj]
0x18001820a  mov     rdx, rdi; void **
0x18001820d  call    ?CreateInstance@CConnectionFolderQueryInfo@@SAJAEBU_GUID@@PEAPEAX@Z; CConnectionFolderQueryInfo::CreateInstance(_GUID const &,void * *)
0x180018212  mov     ebx, eax
0x180018214  test    eax, eax
0x180018216  js      short loc_18001822B
0x180018218  mov     rcx, [rdi]
0x18001821b  add     rcx, 40h ; '@'
0x18001821f  mov     rdx, qword ptr [rsp+0A8h+clsid.Data1]
0x180018224  call    ??4?$CPConFoldPidl@VConFoldPidl_v3@@@@QEAAAEAV0@AEBV0@@Z; CPConFoldPidl<ConFoldPidl_v3>::operator=(CPConFoldPidl<ConFoldPidl_v3> const &)
0x180018229  xor     ebx, ebx
0x18001822b  jmp     loc_1800182B5
0x180018230  cmp     esi, 1
0x180018233  jnz     loc_1800182C3
0x180018239  mov     r8, [rsp+0A8h+ppdtobj]; void **
0x180018241  mov     rcx, [r9]; struct _ITEMIDLIST *
0x180018244  call    ?CreateInstance@CConnectionFolderExtractIcon@@SAJPEFBU_ITEMIDLIST@@AEBU_GUID@@PEAPEAX@Z; CConnectionFolderExtractIcon::CreateInstance(_ITEMIDLIST const *,_GUID const &,void * *)
0x180018249  mov     ebx, eax
0x18001824b  jmp     short loc_1800182BF
0x18001824d  lea     rcx, [rsp+0A8h+clsid]
0x180018252  call    ??0?$vector@V?$CPConFoldPidl@VConFoldPidl_v3@@@@V?$allocator@V?$CPConFoldPidl@VConFoldPidl_v3@@@@@std@@@std@@QEAA@XZ; std::vector<CPConFoldPidl<ConFoldPidl_v3>>::vector<CPConFoldPidl<ConFoldPidl_v3>>(void)
0x180018257  nop
0x180018258  lea     r8, [rsp+0A8h+clsid]
0x18001825d  mov     edx, esi
0x18001825f  mov     rcx, r14
0x180018262  call    ?PConfoldPidlVecFromItemIdListArray@@YAJPEAPEFBU_ITEMIDLIST@@KAEAV?$vector@V?$CPConFoldPidl@VConFoldPidl_v3@@@@V?$allocator@V?$CPConFoldPidl@VConFoldPidl_v3@@@@@std@@@std@@@Z; PConfoldPidlVecFromItemIdListArray(_ITEMIDLIST const * *,ulong,std::vector<CPConFoldPidl<ConFoldPidl_v3>> &)
0x180018267  test    eax, eax
0x180018269  jns     short loc_18001827C
0x18001826b  lea     rcx, [rsp+0A8h+clsid]
0x180018270  call    ??1?$vector@V?$CPConFoldPidl@VConFoldPidl_v3@@@@V?$allocator@V?$CPConFoldPidl@VConFoldPidl_v3@@@@@std@@@std@@QEAA@XZ; std::vector<CPConFoldPidl<ConFoldPidl_v3>>::~vector<CPConFoldPidl<ConFoldPidl_v3>>(void)
0x180018275  mov     eax, 80070057h
0x18001827a  jmp     short loc_1800182E1
0x18001827c  lea     rax, [rdi-10h]
0x180018280  neg     rax
0x180018283  sbb     rcx, rcx
0x180018286  and     rcx, rdi
0x180018289  mov     [rsp+0A8h+var_80], rcx
0x18001828e  lea     rax, [rsp+0A8h+clsid]
0x180018293  mov     [rsp+0A8h+var_88], rax
0x180018298  mov     r9, r15
0x18001829b  mov     r8d, 1
0x1800182a1  mov     rdx, [rsp+0A8h+ppdtobj]
0x1800182a9  call    ?CreateInstance@CConnectionFolderContextMenu@@SAJAEBU_GUID@@PEAPEAXW4CMENU_TYPE@@PEAUHWND__@@AEBV?$vector@V?$CPConFoldPidl@VConFoldPidl_v3@@@@V?$allocator@V?$CPConFoldPidl@VConFoldPidl_v3@@@@@std@@@std@@PEAUIShellFolder@@@Z; CConnectionFolderContextMenu::CreateInstance(_GUID const &,void * *,CMENU_TYPE,HWND__ *,std::vector<CPConFoldPidl<ConFoldPidl_v3>> const &,IShellFolder *)
0x1800182ae  test    eax, eax
0x1800182b0  cmovs   eax, ebx
0x1800182b3  mov     ebx, eax
0x1800182b5  lea     rcx, [rsp+0A8h+clsid]
0x1800182ba  call    ??1?$vector@V?$CPConFoldPidl@VConFoldPidl_v3@@@@V?$allocator@V?$CPConFoldPidl@VConFoldPidl_v3@@@@@std@@@std@@QEAA@XZ; std::vector<CPConFoldPidl<ConFoldPidl_v3>>::~vector<CPConFoldPidl<ConFoldPidl_v3>>(void)
0x1800182bf  test    ebx, ebx
0x1800182c1  jns     short loc_1800182D2
0x1800182c3  mov     rax, [rsp+0A8h+ppdtobj]
0x1800182cb  mov     qword ptr [rax], 0
0x1800182d2  jmp     short loc_1800182DF
0x1800182d4  jmp     short loc_1800182D8
0x1800182d6  jmp     short $+2
0x1800182d8  mov     ebx, [rsp+0A8h+arg_10]
0x1800182df  mov     eax, ebx
0x1800182e1  lea     r11, [rsp+0A8h+var_18]
0x1800182e9  mov     rbx, [r11+20h]
0x1800182ed  mov     rsi, [r11+28h]
0x1800182f1  mov     rsp, r11
0x1800182f4  pop     r15
0x1800182f6  pop     r14
0x1800182f8  pop     rdi
0x1800182f9  retn
```
