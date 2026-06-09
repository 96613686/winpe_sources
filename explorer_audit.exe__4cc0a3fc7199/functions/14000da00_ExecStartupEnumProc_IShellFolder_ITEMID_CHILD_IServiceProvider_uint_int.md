# ExecStartupEnumProc(IShellFolder *,_ITEMID_CHILD *,IServiceProvider *,uint,int *)

- ea: `0x14000da00`
- end: `0x14000de3b`
- name: `?ExecStartupEnumProc@@YAHPEAUIShellFolder@@PEAU_ITEMID_CHILD@@PEAUIServiceProvider@@IPEAH@Z`
- size: `1083`
- prototype: `int(struct IShellFolder *, struct _ITEMID_CHILD *, struct IServiceProvider *, unsigned int, int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140079e20`

## callees

- `0x14000d750`
- `0x14000d8e4`
- `0x14000da00`
- `0x14000e4a8`
- `0x140075130`
- `0x140081c20`
- `0x14008b9a4`
- `0x1400adbd0`
- `0x1401040e0`
- `0x1401044a0`
- `0x140104ce0`
- `0x1401db010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000dde9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000dde9`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x14000daa9`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x14000daa9`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x14000dc9f`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x14000dd74`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x14000dd96`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x14000ddfb`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x14000dc9f`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x14000dd74`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x14000dd96`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x14000ddfb`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x14000dc83`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x14000dc83`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000dc03`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000dc03`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x14000dc0e`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x14000dc0e`
- `api-ms-win-shell-namespace-l1-1-0!SHBindToParent` at `0x14000dbc9`
- `api-ms-win-shell-namespace-l1-1-0!SHBindToParent` at `0x14000dbc9`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!StrRetToBufW` at `0x14000da88`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!StrRetToBufW` at `0x14000da88`
- `USER32!DestroyMenu` at `0x14000dd9f`
- `USER32!DestroyMenu` at `0x14000dd9f`
- `USER32!GetMenuDefaultItem` at `0x14000dd34`
- `USER32!GetMenuDefaultItem` at `0x14000dd34`
- `USER32!CreatePopupMenu` at `0x14000dcf3`
- `USER32!CreatePopupMenu` at `0x14000dcf3`

## pseudocode

```c
__int64 __fastcall ExecStartupEnumProc(struct IShellFolder *a1, const ITEMIDLIST *a2, IUnknown *a3)
{
  int v6; // ebx
  int v7; // ebx
  __int64 v8; // rcx
  const ITEMIDLIST *v9; // rbx
  int v10; // eax
  int v11; // edi
  CExecuteRunAppFilter *v12; // rax
  CExecuteRunAppFilter *v13; // rax
  CExecuteRunAppFilter *v14; // rdi
  HRESULT v15; // ebx
  HRESULT (__stdcall *GetUIObjectOf)(IShellFolder *, HWND, UINT, LPCITEMIDLIST *, const IID *const, UINT *, void **); // rax
  __int64 v17; // rcx
  HMENU PopupMenu; // rbx
  UINT MenuDefaultItem; // eax
  __int16 v20; // di
  IUnknown *v22; // [rsp+40h] [rbp-C0h] BYREF
  IUnknown *punk; // [rsp+48h] [rbp-B8h] BYREF
  LPCITEMIDLIST pidl; // [rsp+50h] [rbp-B0h] BYREF
  void *ppvOut; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v26; // [rsp+60h] [rbp-A0h] BYREF
  void *ppv; // [rsp+68h] [rbp-98h] BYREF
  const ITEMIDLIST *v28; // [rsp+70h] [rbp-90h] BYREF
  HANDLE hObject; // [rsp+78h] [rbp-88h] BYREF
  LPCITEMIDLIST ppidlLast; // [rsp+80h] [rbp-80h] BYREF
  int v31; // [rsp+90h] [rbp-70h] BYREF
  int v32[3]; // [rsp+94h] [rbp-6Ch] BYREF
  __int64 v33; // [rsp+A0h] [rbp-60h]
  int v34; // [rsp+B8h] [rbp-48h]
  STRRET pstr; // [rsp+100h] [rbp+0h] BYREF
  WCHAR pszBuf[264]; // [rsp+210h] [rbp+110h] BYREF

  v28 = a2;
  pszBuf[0] = 0;
  memset_0(&pstr, 0, sizeof(pstr));
  if ( ((int (__fastcall *)(struct IShellFolder *, const ITEMIDLIST *, __int64, STRRET *))a1->lpVtbl->GetDisplayNameOf)(
         a1,
         a2,
         32769,
         &pstr) >= 0 )
    StrRetToBufW(&pstr, a2, pszBuf, 0x104u);
  ppvOut = 0;
  if ( IUnknown_QueryService(
         a3,
         &GUID_087471a8_0058_4321_9dd3_8289cf523f81,
         &GUID_087471a8_0058_4321_9dd3_8289cf523f81,
         &ppvOut) >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(void *, WCHAR *))(*(_QWORD *)ppvOut + 32LL))(ppvOut, pszBuf);
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
    if ( v6 )
    {
      pidl = 0;
      pszBuf[0] = 0;
      v26 = 0;
      if ( ((int (__fastcall *)(struct IShellFolder *, _QWORD, __int64, const ITEMIDLIST **, GUID *, _QWORD, __int64 *))a1->lpVtbl->GetUIObjectOf)(
             a1,
             0,
             1,
             &v28,
             &GUID_000214f9_0000_0000_c000_000000000046,
             0,
             &v26) < 0 )
      {
        v7 = SHFullIDListFromFolderAndRelativeItem(a1, v28, &pidl);
      }
      else
      {
        v7 = (*(__int64 (__fastcall **)(__int64, LPCITEMIDLIST *))(*(_QWORD *)v26 + 32LL))(v26, &pidl);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      }
      if ( v7 >= 0 )
      {
        v9 = pidl;
        pszBuf[0] = 0;
        v10 = SHCoInitialize();
        ppv = 0;
        ppidlLast = 0;
        v11 = v10;
        if ( SHBindToParent(v9, &GUID_000214e6_0000_0000_c000_000000000046, &ppv, &ppidlLast) >= 0 )
        {
          DisplayNameOfW(ppv, ppidlLast, 0x8000, pszBuf);
          (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
        }
        if ( !v11 )
          CoUninitialize();
        ILFree((LPITEMIDLIST)pidl);
      }
      if ( (byte_140253B81 & 0x20) != 0 )
        McTemplateU0z_EventWriteTransfer(v8, &ShellTraceId_Explorer_ExecutingFromStartupMenu_Start, pszBuf);
      hObject = 0;
      punk = 0;
      v12 = (CExecuteRunAppFilter *)operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v12 )
      {
        v13 = CExecuteRunAppFilter::CExecuteRunAppFilter(v12, &hObject);
        v14 = v13;
        if ( v13 )
        {
          v15 = QISearch(v13, &pqit, &GUID_6d5140c1_7436_11ce_8034_00aa006009fa, (void **)&punk);
          CExecuteRunAppFilter::Release(v14);
          if ( v15 >= 0 )
          {
            IUnknown_SetSite(punk, a3);
            a3 = punk;
          }
        }
      }
      GetUIObjectOf = a1->lpVtbl->GetUIObjectOf;
      v22 = 0;
      if ( ((int (__fastcall *)(struct IShellFolder *, _QWORD, __int64, const ITEMIDLIST **, GUID *, _QWORD, IUnknown **))GetUIObjectOf)(
             a1,
             0,
             1,
             &v28,
             &GUID_000214e4_0000_0000_c000_000000000046,
             0,
             &v22) >= 0 )
      {
        PopupMenu = CreatePopupMenu();
        if ( PopupMenu )
        {
          ((void (__fastcall *)(IUnknown *, HMENU, _QWORD, __int64, int, int))v22->lpVtbl[1].QueryInterface)(
            v22,
            PopupMenu,
            0,
            1,
            0x7FFF,
            1);
          MenuDefaultItem = GetMenuDefaultItem(PopupMenu, 0, 0);
          v20 = MenuDefaultItem;
          if ( MenuDefaultItem )
          {
            v31 = 104;
            memset_0(v32, 0, 0x64u);
            v33 = (unsigned __int16)(v20 - 1);
            v32[0] = 1024;
            v34 = 1;
            IUnknown_SetSite(v22, a3);
            ((void (__fastcall *)(IUnknown *, int *))v22->lpVtbl[1].AddRef)(v22, &v31);
            IUnknown_SetSite(v22, 0);
          }
          DestroyMenu(PopupMenu);
        }
        ((void (__fastcall *)(IUnknown *))v22->lpVtbl->Release)(v22);
      }
      if ( (byte_140253B81 & 0x20) != 0 )
        McTemplateU0z_EventWriteTransfer(v17, &ShellTraceId_Explorer_ExecutingFromStartupMenu_Stop, pszBuf);
      if ( hObject )
      {
        IUnknown_WaitForSteadyState(a3, hObject);
        CloseHandle(hObject);
      }
      if ( punk )
      {
        IUnknown_SetSite(punk, 0);
        ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x14000da00  mov     [rsp-8+arg_18], rbx
0x14000da05  push    rbp
0x14000da06  push    rsi
0x14000da07  push    rdi
0x14000da08  push    r12
0x14000da0a  push    r14
0x14000da0c  lea     rbp, [rsp-330h]
0x14000da14  sub     rsp, 430h
0x14000da1b  mov     rax, cs:__security_cookie
0x14000da22  xor     rax, rsp
0x14000da25  mov     [rbp+350h+var_30], rax
0x14000da2c  mov     rsi, r8
0x14000da2f  mov     [rsp+450h+var_3E0], rdx
0x14000da34  mov     rbx, rdx
0x14000da37  mov     r14, rcx
0x14000da3a  xor     eax, eax
0x14000da3c  lea     rcx, [rbp+350h+pstr]; void *
0x14000da40  xor     edx, edx; Val
0x14000da42  mov     [rbp+350h+pszBuf], ax
0x14000da49  mov     r8d, 110h; Size
0x14000da4f  call    memset_0
0x14000da54  mov     rax, [r14]
0x14000da57  lea     r9, [rbp+350h+pstr]
0x14000da5b  mov     r8d, 8001h
0x14000da61  mov     rdx, rbx
0x14000da64  mov     rcx, r14
0x14000da67  mov     rax, [rax+58h]
0x14000da6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000da70  test    eax, eax
0x14000da72  js      short loc_14000DA8E
0x14000da74  mov     r9d, 104h; cchBuf
0x14000da7a  lea     r8, [rbp+350h+pszBuf]; pszBuf
0x14000da81  mov     rdx, rbx; pidl
0x14000da84  lea     rcx, [rbp+350h+pstr]; pstr
0x14000da88  call    cs:__imp_StrRetToBufW
0x14000da8e  lea     rdx, _GUID_087471a8_0058_4321_9dd3_8289cf523f81; guidService
0x14000da95  mov     [rsp+450h+ppvOut], 0
0x14000da9e  mov     r8, rdx; riid
0x14000daa1  lea     r9, [rsp+450h+ppvOut]; ppvOut
0x14000daa6  mov     rcx, rsi; punk
0x14000daa9  call    cs:__imp_IUnknown_QueryService
0x14000daaf  mov     r12d, 1
0x14000dab5  test    eax, eax
0x14000dab7  js      loc_14000DE12
0x14000dabd  mov     rcx, [rsp+450h+ppvOut]
0x14000dac2  lea     rdx, [rbp+350h+pszBuf]
0x14000dac9  mov     rax, [rcx]
0x14000dacc  mov     rax, [rax+20h]
0x14000dad0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dad5  mov     rdx, [rsp+450h+ppvOut]
0x14000dada  mov     ebx, eax
0x14000dadc  mov     rcx, [rdx]
0x14000dadf  mov     rax, [rcx+10h]
0x14000dae3  mov     rcx, rdx
0x14000dae6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000daeb  test    ebx, ebx
0x14000daed  jz      loc_14000DE12
0x14000daf3  xor     eax, eax
0x14000daf5  mov     [rsp+450h+pidl], 0
0x14000dafe  mov     [rbp+350h+pszBuf], ax
0x14000db05  lea     rcx, [rsp+450h+var_3F0]
0x14000db0a  mov     [rsp+450h+var_420], rcx
0x14000db0f  lea     r9, [rsp+450h+var_3E0]
0x14000db14  mov     [rsp+450h+var_3F0], rax
0x14000db19  lea     rcx, _GUID_000214f9_0000_0000_c000_000000000046
0x14000db20  mov     rax, [r14]
0x14000db23  mov     r8d, r12d
0x14000db26  mov     [rsp+450h+var_428], 0
0x14000db2f  xor     edx, edx
0x14000db31  mov     [rsp+450h+var_430], rcx
0x14000db36  mov     rcx, r14
0x14000db39  mov     rax, [rax+50h]
0x14000db3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000db42  test    eax, eax
0x14000db44  js      short loc_14000DB74
0x14000db46  mov     rcx, [rsp+450h+var_3F0]
0x14000db4b  lea     rdx, [rsp+450h+pidl]
0x14000db50  mov     rax, [rcx]
0x14000db53  mov     rax, [rax+20h]
0x14000db57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000db5c  mov     rdx, [rsp+450h+var_3F0]
0x14000db61  mov     ebx, eax
0x14000db63  mov     rcx, [rdx]
0x14000db66  mov     rax, [rcx+10h]
0x14000db6a  mov     rcx, rdx
0x14000db6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000db72  jmp     short loc_14000DB88
0x14000db74  mov     rdx, [rsp+450h+var_3E0]
0x14000db79  lea     r8, [rsp+450h+pidl]
0x14000db7e  mov     rcx, r14
0x14000db81  call    SHFullIDListFromFolderAndRelativeItem
0x14000db86  mov     ebx, eax
0x14000db88  test    ebx, ebx
0x14000db8a  js      loc_14000DC14
0x14000db90  mov     rbx, [rsp+450h+pidl]
0x14000db95  xor     eax, eax
0x14000db97  mov     [rbp+350h+pszBuf], ax
0x14000db9e  call    ?SHCoInitialize@@YAJXZ; SHCoInitialize(void)
0x14000dba3  lea     r9, [rbp+350h+ppidlLast]; ppidlLast
0x14000dba7  mov     [rsp+450h+ppv], 0
0x14000dbb0  lea     r8, [rsp+450h+ppv]; ppv
0x14000dbb5  mov     [rbp+350h+ppidlLast], 0
0x14000dbbd  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x14000dbc4  mov     rcx, rbx; pidl
0x14000dbc7  mov     edi, eax
0x14000dbc9  call    cs:__imp_SHBindToParent
0x14000dbcf  test    eax, eax
0x14000dbd1  js      short loc_14000DBFF
0x14000dbd3  mov     rdx, [rbp+350h+ppidlLast]
0x14000dbd7  lea     r9, [rbp+350h+pszBuf]
0x14000dbde  mov     rcx, [rsp+450h+ppv]
0x14000dbe3  mov     r8d, 8000h
0x14000dbe9  call    DisplayNameOfW
0x14000dbee  mov     rcx, [rsp+450h+ppv]
0x14000dbf3  mov     rax, [rcx]
0x14000dbf6  mov     rax, [rax+10h]
0x14000dbfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dbff  test    edi, edi
0x14000dc01  jnz     short loc_14000DC09
0x14000dc03  call    cs:__imp_CoUninitialize
0x14000dc09  mov     rcx, [rsp+450h+pidl]; pidl
0x14000dc0e  call    cs:__imp_ILFree
0x14000dc14  test    cs:byte_140253B81, 20h
0x14000dc1b  jz      short loc_14000DC30
0x14000dc1d  lea     r8, [rbp+350h+pszBuf]
0x14000dc24  lea     rdx, ShellTraceId_Explorer_ExecutingFromStartupMenu_Start
0x14000dc2b  call    McTemplateU0z_EventWriteTransfer
0x14000dc30  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000dc37  mov     [rsp+450h+hObject], 0
0x14000dc40  mov     ecx, 30h ; '0'; unsigned __int64
0x14000dc45  mov     [rsp+450h+punk], 0
0x14000dc4e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000dc53  test    rax, rax
0x14000dc56  jz      short loc_14000DCAA
0x14000dc58  lea     rdx, [rsp+450h+hObject]; void **
0x14000dc5d  mov     rcx, rax; this
0x14000dc60  call    ??0CExecuteRunAppFilter@@QEAA@PEAPEAX@Z; CExecuteRunAppFilter::CExecuteRunAppFilter(void * *)
0x14000dc65  mov     rdi, rax
0x14000dc68  test    rax, rax
0x14000dc6b  jz      short loc_14000DCAA
0x14000dc6d  lea     r9, [rsp+450h+punk]; ppv
0x14000dc72  mov     rcx, rax; that
0x14000dc75  lea     r8, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa; riid
0x14000dc7c  lea     rdx, pqit; pqit
0x14000dc83  call    cs:__imp_QISearch
0x14000dc89  mov     rcx, rdi; this
0x14000dc8c  mov     ebx, eax
0x14000dc8e  call    ?Release@CExecuteRunAppFilter@@UEAAKXZ; CExecuteRunAppFilter::Release(void)
0x14000dc93  test    ebx, ebx
0x14000dc95  js      short loc_14000DCAA
0x14000dc97  mov     rcx, [rsp+450h+punk]; punk
0x14000dc9c  mov     rdx, rsi; punkSite
0x14000dc9f  call    cs:__imp_IUnknown_SetSite
0x14000dca5  mov     rsi, [rsp+450h+punk]
0x14000dcaa  mov     rax, [r14]
0x14000dcad  lea     rcx, [rsp+450h+var_410]
0x14000dcb2  mov     [rsp+450h+var_420], rcx
0x14000dcb7  lea     r9, [rsp+450h+var_3E0]
0x14000dcbc  lea     rcx, _GUID_000214e4_0000_0000_c000_000000000046
0x14000dcc3  mov     [rsp+450h+var_428], 0
0x14000dccc  mov     [rsp+450h+var_430], rcx
0x14000dcd1  mov     r8d, r12d
0x14000dcd4  mov     rax, [rax+50h]
0x14000dcd8  mov     rcx, r14
0x14000dcdb  xor     edx, edx
0x14000dcdd  mov     [rsp+450h+var_410], 0
0x14000dce6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dceb  test    eax, eax
0x14000dced  js      loc_14000DDB6
0x14000dcf3  call    cs:__imp_CreatePopupMenu
0x14000dcf9  mov     rbx, rax
0x14000dcfc  test    rax, rax
0x14000dcff  jz      loc_14000DDA5
0x14000dd05  mov     rcx, [rsp+450h+var_410]
0x14000dd0a  mov     r9d, r12d
0x14000dd0d  mov     dword ptr [rsp+450h+var_428], r12d
0x14000dd12  xor     r8d, r8d
0x14000dd15  mov     dword ptr [rsp+450h+var_430], 7FFFh
0x14000dd1d  mov     rdx, [rcx]
0x14000dd20  mov     rax, [rdx+18h]
0x14000dd24  mov     rdx, rbx
0x14000dd27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dd2c  xor     r8d, r8d; gmdiFlags
0x14000dd2f  xor     edx, edx; fByPos
0x14000dd31  mov     rcx, rbx; hMenu
0x14000dd34  call    cs:__imp_GetMenuDefaultItem
0x14000dd3a  mov     edi, eax
0x14000dd3c  test    eax, eax
0x14000dd3e  jz      short loc_14000DD9C
0x14000dd40  xor     edx, edx; Val
0x14000dd42  mov     [rbp+350h+var_3C0], 68h ; 'h'
0x14000dd49  lea     rcx, [rbp+350h+var_3BC]; void *
0x14000dd4d  lea     r8d, [rdx+64h]; Size
0x14000dd51  call    memset_0
0x14000dd56  mov     rcx, [rsp+450h+var_410]; punk
0x14000dd5b  sub     di, r12w
0x14000dd5f  movzx   eax, di
0x14000dd62  mov     rdx, rsi; punkSite
0x14000dd65  mov     [rbp+350h+var_3B0], rax
0x14000dd69  mov     [rbp+350h+var_3BC], 400h
0x14000dd70  mov     [rbp+350h+var_398], r12d
0x14000dd74  call    cs:__imp_IUnknown_SetSite
0x14000dd7a  mov     rcx, [rsp+450h+var_410]
0x14000dd7f  lea     rdx, [rbp+350h+var_3C0]
0x14000dd83  mov     rax, [rcx]
0x14000dd86  mov     rax, [rax+20h]
0x14000dd8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dd8f  mov     rcx, [rsp+450h+var_410]; punk
0x14000dd94  xor     edx, edx; punkSite
0x14000dd96  call    cs:__imp_IUnknown_SetSite
0x14000dd9c  mov     rcx, rbx; hMenu
0x14000dd9f  call    cs:__imp_DestroyMenu
0x14000dda5  mov     rcx, [rsp+450h+var_410]
0x14000ddaa  mov     rax, [rcx]
0x14000ddad  mov     rax, [rax+10h]
0x14000ddb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ddb6  test    cs:byte_140253B81, 20h
0x14000ddbd  jz      short loc_14000DDD2
0x14000ddbf  lea     r8, [rbp+350h+pszBuf]
0x14000ddc6  lea     rdx, ShellTraceId_Explorer_ExecutingFromStartupMenu_Stop
0x14000ddcd  call    McTemplateU0z_EventWriteTransfer
0x14000ddd2  mov     rdx, [rsp+450h+hObject]
0x14000ddd7  test    rdx, rdx
0x14000ddda  jz      short loc_14000DDEF
0x14000dddc  mov     rcx, rsi
0x14000dddf  call    IUnknown_WaitForSteadyState
0x14000dde4  mov     rcx, [rsp+450h+hObject]; hObject
0x14000dde9  call    cs:__imp_CloseHandle
0x14000ddef  mov     rcx, [rsp+450h+punk]; punk
0x14000ddf4  test    rcx, rcx
0x14000ddf7  jz      short loc_14000DE12
0x14000ddf9  xor     edx, edx; punkSite
0x14000ddfb  call    cs:__imp_IUnknown_SetSite
0x14000de01  mov     rcx, [rsp+450h+punk]
0x14000de06  mov     rdx, [rcx]
0x14000de09  mov     rax, [rdx+10h]
0x14000de0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000de12  mov     eax, r12d
0x14000de15  mov     rcx, [rbp+350h+var_30]
0x14000de1c  xor     rcx, rsp; StackCookie
0x14000de1f  call    __security_check_cookie
0x14000de24  mov     rbx, [rsp+450h+arg_18]
0x14000de2c  add     rsp, 430h
0x14000de33  pop     r14
0x14000de35  pop     r12
0x14000de37  pop     rdi
0x14000de38  pop     rsi
0x14000de39  pop     rbp
0x14000de3a  retn
```
