# ExecStartupEnumProc(IShellFolder *,_ITEMID_CHILD *,IServiceProvider *,uint,int *)

- ea: `0x140069b84`
- end: `0x14006a014`
- name: `?ExecStartupEnumProc@@YAHPEAUIShellFolder@@PEAU_ITEMID_CHILD@@PEAUIServiceProvider@@IPEAH@Z`
- size: `1168`
- prototype: `int(struct IShellFolder *, struct _ITEMID_CHILD *, struct IServiceProvider *, unsigned int, int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14007f1e0`

## callees

- `0x14000b9e0`
- `0x140069b84`
- `0x14006a01c`
- `0x14006a720`
- `0x140079b10`
- `0x140087d20`
- `0x140091140`
- `0x1400b3c50`
- `0x14010e160`
- `0x14010e520`
- `0x14010ed90`
- `0x1401d9010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140069fb5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140069fb5`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x140069c33`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x140069c33`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x140069e47`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x140069f2e`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x140069f56`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x140069fcd`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x140069e47`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x140069f2e`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x140069f56`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x140069fcd`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x140069e25`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x140069e25`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140069d99`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140069d99`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x140069daa`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x140069daa`
- `api-ms-win-shell-namespace-l1-1-0!SHBindToParent` at `0x140069d59`
- `api-ms-win-shell-namespace-l1-1-0!SHBindToParent` at `0x140069d59`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!StrRetToBufW` at `0x140069c0c`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!StrRetToBufW` at `0x140069c0c`
- `USER32!DestroyMenu` at `0x140069f65`
- `USER32!DestroyMenu` at `0x140069f65`
- `USER32!GetMenuDefaultItem` at `0x140069ee8`
- `USER32!GetMenuDefaultItem` at `0x140069ee8`
- `USER32!CreatePopupMenu` at `0x140069ea1`
- `USER32!CreatePopupMenu` at `0x140069ea1`

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
      if ( (byte_14024FCC1 & 0x20) != 0 )
        McTemplateU0z_EventWriteTransfer(v8, ShellTraceId_Explorer_ExecutingFromStartupMenu_Start, pszBuf);
      hObject = 0;
      punk = 0;
      v12 = (CExecuteRunAppFilter *)operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v12 )
      {
        v13 = CExecuteRunAppFilter::CExecuteRunAppFilter(v12, &hObject);
        v14 = v13;
        if ( v13 )
        {
          v15 = QISearch(v13, &stru_1401DD140, &GUID_6d5140c1_7436_11ce_8034_00aa006009fa, (void **)&punk);
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
      if ( (byte_14024FCC1 & 0x20) != 0 )
        McTemplateU0z_EventWriteTransfer(v17, ShellTraceId_Explorer_ExecutingFromStartupMenu_Stop, pszBuf);
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
0x140069b84  mov     [rsp-8+arg_18], rbx
0x140069b89  push    rbp
0x140069b8a  push    rsi
0x140069b8b  push    rdi
0x140069b8c  push    r12
0x140069b8e  push    r14
0x140069b90  lea     rbp, [rsp-330h]
0x140069b98  sub     rsp, 430h
0x140069b9f  mov     rax, cs:__security_cookie
0x140069ba6  xor     rax, rsp
0x140069ba9  mov     [rbp+350h+var_30], rax
0x140069bb0  mov     rsi, r8
0x140069bb3  mov     [rsp+450h+var_3E0], rdx
0x140069bb8  mov     rbx, rdx
0x140069bbb  mov     r14, rcx
0x140069bbe  xor     eax, eax
0x140069bc0  lea     rcx, [rbp+350h+pstr]; void *
0x140069bc4  xor     edx, edx; Val
0x140069bc6  mov     [rbp+350h+pszBuf], ax
0x140069bcd  mov     r8d, 110h; Size
0x140069bd3  call    memset_0
0x140069bd8  mov     rax, [r14]
0x140069bdb  lea     r9, [rbp+350h+pstr]
0x140069bdf  mov     r8d, 8001h
0x140069be5  mov     rdx, rbx
0x140069be8  mov     rcx, r14
0x140069beb  mov     rax, [rax+58h]
0x140069bef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140069bf4  test    eax, eax
0x140069bf6  js      short loc_140069C18
0x140069bf8  mov     r9d, 104h; cchBuf
0x140069bfe  lea     r8, [rbp+350h+pszBuf]; pszBuf
0x140069c05  mov     rdx, rbx; pidl
0x140069c08  lea     rcx, [rbp+350h+pstr]; pstr
0x140069c0c  call    cs:__imp_StrRetToBufW
0x140069c13  nop     dword ptr [rax+rax+00h]
0x140069c18  lea     rdx, _GUID_087471a8_0058_4321_9dd3_8289cf523f81; guidService
0x140069c1f  mov     [rsp+450h+ppvOut], 0
0x140069c28  mov     r8, rdx; riid
0x140069c2b  lea     r9, [rsp+450h+ppvOut]; ppvOut
0x140069c30  mov     rcx, rsi; punk
0x140069c33  call    cs:__imp_IUnknown_QueryService
0x140069c3a  nop     dword ptr [rax+rax+00h]
0x140069c3f  mov     r12d, 1
0x140069c45  test    eax, eax
0x140069c47  js      loc_140069FEA
0x140069c4d  mov     rcx, [rsp+450h+ppvOut]
0x140069c52  lea     rdx, [rbp+350h+pszBuf]
0x140069c59  mov     rax, [rcx]
0x140069c5c  mov     rax, [rax+20h]
0x140069c60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140069c65  mov     rdx, [rsp+450h+ppvOut]
0x140069c6a  mov     ebx, eax
0x140069c6c  mov     rcx, [rdx]
0x140069c6f  mov     rax, [rcx+10h]
0x140069c73  mov     rcx, rdx
0x140069c76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140069c7b  test    ebx, ebx
0x140069c7d  jz      loc_140069FEA
0x140069c83  xor     eax, eax
0x140069c85  mov     [rsp+450h+pidl], 0
0x140069c8e  mov     [rbp+350h+pszBuf], ax
0x140069c95  lea     rcx, [rsp+450h+var_3F0]
0x140069c9a  mov     [rsp+450h+var_420], rcx
0x140069c9f  lea     r9, [rsp+450h+var_3E0]
0x140069ca4  mov     [rsp+450h+var_3F0], rax
0x140069ca9  lea     rcx, _GUID_000214f9_0000_0000_c000_000000000046
0x140069cb0  mov     rax, [r14]
0x140069cb3  mov     r8d, r12d
0x140069cb6  mov     [rsp+450h+var_428], 0
0x140069cbf  xor     edx, edx
0x140069cc1  mov     [rsp+450h+var_430], rcx
0x140069cc6  mov     rcx, r14
0x140069cc9  mov     rax, [rax+50h]
0x140069ccd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140069cd2  test    eax, eax
0x140069cd4  js      short loc_140069D04
0x140069cd6  mov     rcx, [rsp+450h+var_3F0]
0x140069cdb  lea     rdx, [rsp+450h+pidl]
0x140069ce0  mov     rax, [rcx]
0x140069ce3  mov     rax, [rax+20h]
0x140069ce7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140069cec  mov     rdx, [rsp+450h+var_3F0]
0x140069cf1  mov     ebx, eax
0x140069cf3  mov     rcx, [rdx]
0x140069cf6  mov     rax, [rcx+10h]
0x140069cfa  mov     rcx, rdx
0x140069cfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140069d02  jmp     short loc_140069D18
0x140069d04  mov     rdx, [rsp+450h+var_3E0]
0x140069d09  lea     r8, [rsp+450h+pidl]
0x140069d0e  mov     rcx, r14
0x140069d11  call    SHFullIDListFromFolderAndRelativeItem
0x140069d16  mov     ebx, eax
0x140069d18  test    ebx, ebx
0x140069d1a  js      loc_140069DB6
0x140069d20  mov     rbx, [rsp+450h+pidl]
0x140069d25  xor     eax, eax
0x140069d27  mov     [rbp+350h+pszBuf], ax
0x140069d2e  call    ?SHCoInitialize@@YAJXZ; SHCoInitialize(void)
0x140069d33  lea     r9, [rbp+350h+ppidlLast]; ppidlLast
0x140069d37  mov     [rsp+450h+ppv], 0
0x140069d40  lea     r8, [rsp+450h+ppv]; ppv
0x140069d45  mov     [rbp+350h+ppidlLast], 0
0x140069d4d  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x140069d54  mov     rcx, rbx; pidl
0x140069d57  mov     edi, eax
0x140069d59  call    cs:__imp_SHBindToParent
0x140069d60  nop     dword ptr [rax+rax+00h]
0x140069d65  test    eax, eax
0x140069d67  js      short loc_140069D95
0x140069d69  mov     rdx, [rbp+350h+ppidlLast]
0x140069d6d  lea     r9, [rbp+350h+pszBuf]
0x140069d74  mov     rcx, [rsp+450h+ppv]
0x140069d79  mov     r8d, 8000h
0x140069d7f  call    DisplayNameOfW
0x140069d84  mov     rcx, [rsp+450h+ppv]
0x140069d89  mov     rax, [rcx]
0x140069d8c  mov     rax, [rax+10h]
0x140069d90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140069d95  test    edi, edi
0x140069d97  jnz     short loc_140069DA5
0x140069d99  call    cs:__imp_CoUninitialize
0x140069da0  nop     dword ptr [rax+rax+00h]
0x140069da5  mov     rcx, [rsp+450h+pidl]; pidl
0x140069daa  call    cs:__imp_ILFree
0x140069db1  nop     dword ptr [rax+rax+00h]
0x140069db6  test    cs:byte_14024FCC1, 20h
0x140069dbd  jz      short loc_140069DD2
0x140069dbf  lea     r8, [rbp+350h+pszBuf]
0x140069dc6  lea     rdx, ShellTraceId_Explorer_ExecutingFromStartupMenu_Start
0x140069dcd  call    McTemplateU0z_EventWriteTransfer
0x140069dd2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140069dd9  mov     [rsp+450h+hObject], 0
0x140069de2  mov     ecx, 30h ; '0'; unsigned __int64
0x140069de7  mov     [rsp+450h+punk], 0
0x140069df0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140069df5  test    rax, rax
0x140069df8  jz      short loc_140069E58
0x140069dfa  lea     rdx, [rsp+450h+hObject]; void **
0x140069dff  mov     rcx, rax; this
0x140069e02  call    ??0CExecuteRunAppFilter@@QEAA@PEAPEAX@Z; CExecuteRunAppFilter::CExecuteRunAppFilter(void * *)
0x140069e07  mov     rdi, rax
0x140069e0a  test    rax, rax
0x140069e0d  jz      short loc_140069E58
0x140069e0f  lea     r9, [rsp+450h+punk]; ppv
0x140069e14  mov     rcx, rax; that
0x140069e17  lea     r8, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa; riid
0x140069e1e  lea     rdx, stru_1401DD140; pqit
0x140069e25  call    cs:__imp_QISearch
0x140069e2c  nop     dword ptr [rax+rax+00h]
0x140069e31  mov     rcx, rdi; this
0x140069e34  mov     ebx, eax
0x140069e36  call    ?Release@CExecuteRunAppFilter@@UEAAKXZ; CExecuteRunAppFilter::Release(void)
0x140069e3b  test    ebx, ebx
0x140069e3d  js      short loc_140069E58
0x140069e3f  mov     rcx, [rsp+450h+punk]; punk
0x140069e44  mov     rdx, rsi; punkSite
0x140069e47  call    cs:__imp_IUnknown_SetSite
0x140069e4e  nop     dword ptr [rax+rax+00h]
0x140069e53  mov     rsi, [rsp+450h+punk]
0x140069e58  mov     rax, [r14]
0x140069e5b  lea     rcx, [rsp+450h+var_410]
0x140069e60  mov     [rsp+450h+var_420], rcx
0x140069e65  lea     r9, [rsp+450h+var_3E0]
0x140069e6a  lea     rcx, _GUID_000214e4_0000_0000_c000_000000000046
0x140069e71  mov     [rsp+450h+var_428], 0
0x140069e7a  mov     [rsp+450h+var_430], rcx
0x140069e7f  mov     r8d, r12d
0x140069e82  mov     rax, [rax+50h]
0x140069e86  mov     rcx, r14
0x140069e89  xor     edx, edx
0x140069e8b  mov     [rsp+450h+var_410], 0
0x140069e94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140069e99  test    eax, eax
0x140069e9b  js      loc_140069F82
0x140069ea1  call    cs:__imp_CreatePopupMenu
0x140069ea8  nop     dword ptr [rax+rax+00h]
0x140069ead  mov     rbx, rax
0x140069eb0  test    rax, rax
0x140069eb3  jz      loc_140069F71
0x140069eb9  mov     rcx, [rsp+450h+var_410]
0x140069ebe  mov     r9d, r12d
0x140069ec1  mov     dword ptr [rsp+450h+var_428], r12d
0x140069ec6  xor     r8d, r8d
0x140069ec9  mov     dword ptr [rsp+450h+var_430], 7FFFh
0x140069ed1  mov     rdx, [rcx]
0x140069ed4  mov     rax, [rdx+18h]
0x140069ed8  mov     rdx, rbx
0x140069edb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140069ee0  xor     r8d, r8d; gmdiFlags
0x140069ee3  xor     edx, edx; fByPos
0x140069ee5  mov     rcx, rbx; hMenu
0x140069ee8  call    cs:__imp_GetMenuDefaultItem
0x140069eef  nop     dword ptr [rax+rax+00h]
0x140069ef4  mov     edi, eax
0x140069ef6  test    eax, eax
0x140069ef8  jz      short loc_140069F62
0x140069efa  xor     edx, edx; Val
0x140069efc  mov     [rbp+350h+var_3C0], 68h ; 'h'
0x140069f03  lea     rcx, [rbp+350h+var_3BC]; void *
0x140069f07  lea     r8d, [rdx+64h]; Size
0x140069f0b  call    memset_0
0x140069f10  mov     rcx, [rsp+450h+var_410]; punk
0x140069f15  sub     di, r12w
0x140069f19  movzx   eax, di
0x140069f1c  mov     rdx, rsi; punkSite
0x140069f1f  mov     [rbp+350h+var_3B0], rax
0x140069f23  mov     [rbp+350h+var_3BC], 400h
0x140069f2a  mov     [rbp+350h+var_398], r12d
0x140069f2e  call    cs:__imp_IUnknown_SetSite
0x140069f35  nop     dword ptr [rax+rax+00h]
0x140069f3a  mov     rcx, [rsp+450h+var_410]
0x140069f3f  lea     rdx, [rbp+350h+var_3C0]
0x140069f43  mov     rax, [rcx]
0x140069f46  mov     rax, [rax+20h]
0x140069f4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140069f4f  mov     rcx, [rsp+450h+var_410]; punk
0x140069f54  xor     edx, edx; punkSite
0x140069f56  call    cs:__imp_IUnknown_SetSite
0x140069f5d  nop     dword ptr [rax+rax+00h]
0x140069f62  mov     rcx, rbx; hMenu
0x140069f65  call    cs:__imp_DestroyMenu
0x140069f6c  nop     dword ptr [rax+rax+00h]
0x140069f71  mov     rcx, [rsp+450h+var_410]
0x140069f76  mov     rax, [rcx]
0x140069f79  mov     rax, [rax+10h]
0x140069f7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140069f82  test    cs:byte_14024FCC1, 20h
0x140069f89  jz      short loc_140069F9E
0x140069f8b  lea     r8, [rbp+350h+pszBuf]
0x140069f92  lea     rdx, ShellTraceId_Explorer_ExecutingFromStartupMenu_Stop
0x140069f99  call    McTemplateU0z_EventWriteTransfer
0x140069f9e  mov     rdx, [rsp+450h+hObject]
0x140069fa3  test    rdx, rdx
0x140069fa6  jz      short loc_140069FC1
0x140069fa8  mov     rcx, rsi
0x140069fab  call    IUnknown_WaitForSteadyState
0x140069fb0  mov     rcx, [rsp+450h+hObject]; hObject
0x140069fb5  call    cs:__imp_CloseHandle
0x140069fbc  nop     dword ptr [rax+rax+00h]
0x140069fc1  mov     rcx, [rsp+450h+punk]; punk
0x140069fc6  test    rcx, rcx
0x140069fc9  jz      short loc_140069FEA
0x140069fcb  xor     edx, edx; punkSite
0x140069fcd  call    cs:__imp_IUnknown_SetSite
0x140069fd4  nop     dword ptr [rax+rax+00h]
0x140069fd9  mov     rcx, [rsp+450h+punk]
0x140069fde  mov     rdx, [rcx]
0x140069fe1  mov     rax, [rdx+10h]
0x140069fe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140069fea  mov     eax, r12d
0x140069fed  mov     rcx, [rbp+350h+var_30]
0x140069ff4  xor     rcx, rsp; StackCookie
0x140069ff7  call    __security_check_cookie
0x140069ffc  mov     rbx, [rsp+450h+arg_18]
0x14006a004  add     rsp, 430h
0x14006a00b  pop     r14
0x14006a00d  pop     r12
0x14006a00f  pop     rdi
0x14006a010  pop     rsi
0x14006a011  pop     rbp
0x14006a012  retn
```
