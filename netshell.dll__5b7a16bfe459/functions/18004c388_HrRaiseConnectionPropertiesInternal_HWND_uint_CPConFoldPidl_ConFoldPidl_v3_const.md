# HrRaiseConnectionPropertiesInternal(HWND__ *,uint,CPConFoldPidl<ConFoldPidl_v3> const &)

- ea: `0x18004c388`
- end: `0x18004c741`
- name: `?HrRaiseConnectionPropertiesInternal@@YAJPEAUHWND__@@IAEBV?$CPConFoldPidl@VConFoldPidl_v3@@@@@Z`
- size: `953`
- prototype: `__int64 __fastcall(HWND, UINT, __int64)`
- caller_count: `2`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001cb40`
- `0x180045e10`

## callees

- `0x1800020b0`
- `0x180005c8c`
- `0x18001644c`
- `0x180017674`
- `0x180018d74`
- `0x18001d580`
- `0x18001eb7c`
- `0x180040a5c`
- `0x18004c20c`
- `0x18004c388`
- `0x18004c798`
- `0x180060c00`
- `0x180065010`

## import_xrefs

- `USER32!SetForegroundWindow` at `0x18004c6be`
- `USER32!SetForegroundWindow` at `0x18004c6be`
- `USER32!MessageBoxW` at `0x18004c54c`
- `USER32!MessageBoxW` at `0x18004c54c`
- `USER32!GetSystemMetrics` at `0x18004c5cf`
- `USER32!GetSystemMetrics` at `0x18004c5cf`
- `USER32!DestroyIcon` at `0x18004c6d7`
- `USER32!DestroyIcon` at `0x18004c6d7`
- `USER32!LoadIconW` at `0x18004c609`
- `USER32!LoadIconW` at `0x18004c609`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18004c50c`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18004c50c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c557`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c711`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c557`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c711`
- `ole32!CoTaskMemFree` at `0x18004c51c`
- `ole32!CoTaskMemFree` at `0x18004c6e3`
- `ole32!CoTaskMemFree` at `0x18004c51c`
- `ole32!CoTaskMemFree` at `0x18004c6e3`

## pseudocode

```c
__int64 __fastcall HrRaiseConnectionPropertiesInternal(HWND a1, UINT a2, __int64 a3)
{
  int v6; // ebx
  int v7; // eax
  const unsigned __int16 *Ids; // rax
  const WCHAR *v9; // r8
  int v10; // r14d
  int v11; // esi
  struct IUnknown *v12; // rdi
  int (__fastcall *v13)(struct IUnknown *, _QWORD, LPVOID *); // rbx
  unsigned int SystemMetrics; // eax
  int v15; // ecx
  UINT v16; // edi
  WCHAR Buffer[4]; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-B8h] BYREF
  struct IUnknown *v20; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpCaption; // [rsp+58h] [rbp-A8h] BYREF
  va_list Arguments; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID v23; // [rsp+68h] [rbp-98h]
  struct IUnknown *v24; // [rsp+70h] [rbp-90h] BYREF
  PROPSHEETHEADERW_V2 v25; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v26[208]; // [rsp+E0h] [rbp-20h] BYREF
  struct IUnknown *v27; // [rsp+1D8h] [rbp+D8h] BYREF

  v27 = 0;
  lpCaption = 0;
  v20 = 0;
  CConFoldEntry::CConFoldEntry((CConFoldEntry *)v26);
  v6 = HrNetConFromPidl(a3, &v20, 1);
  if ( v6 < 0 )
    goto LABEL_35;
  SetLUAParent(v20, a1);
  v7 = HrUIInterfaceFromNetCon((struct INetConnection *)v20, &IID_INetConnectionPropertyUi, (void **)&v27);
  v6 = v7;
  if ( v7 == -2147467262 )
  {
    *(_QWORD *)Buffer = 0;
    v6 = HrUIInterfaceFromNetCon((struct INetConnection *)v20, &IID_INetConnectionPropertyUi2, (void **)Buffer);
    if ( v6 >= 0 )
    {
      v27 = *(struct IUnknown **)Buffer;
      goto LABEL_6;
    }
  }
  else if ( v7 >= 0 )
  {
LABEL_6:
    v24 = 0;
    HrGetCaption(0, v20, &lpCaption);
    if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IUnknown **))v27->lpVtbl->QueryInterface)(
           v27,
           &IID_INetConnectionUiLock,
           &v24) >= 0 )
    {
      pv = 0;
      v6 = ((__int64 (__fastcall *)(struct IUnknown *, LPVOID *))v24->lpVtbl[1].QueryInterface)(v24, &pv);
      ReleaseObj(v24);
      if ( v6 == 1 )
      {
        *(_QWORD *)Buffer = 0;
        Arguments = (va_list)pv;
        if ( !pv )
          Arguments = (va_list)SzLoadIds(0x423u);
        Ids = SzLoadIds(0x422u);
        FormatMessageW(0x2500u, Ids, 0, 0, Buffer, 0, &Arguments);
        if ( pv )
          CoTaskMemFree(pv);
        if ( *(_QWORD *)Buffer )
        {
          v9 = &c_szEmpty;
          if ( lpCaption )
            v9 = lpCaption;
          MessageBoxW(a1, *(LPCWSTR *)Buffer, v9, 0x10u);
          LocalFree(*(HLOCAL *)Buffer);
        }
        goto LABEL_31;
      }
      if ( v6 < 0 )
      {
LABEL_31:
        ReleaseObj(0);
        ReleaseObj(v27);
        goto LABEL_32;
      }
    }
    v6 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown *))v27->lpVtbl[1].QueryInterface)(v27, v20);
    if ( v6 >= 0 )
    {
      v10 = 0;
      *(_QWORD *)Buffer = 0;
      pv = 0;
      v11 = 0;
      if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, WCHAR *))v27->lpVtbl->QueryInterface)(
             v27,
             &IID_INetConnectionPropertyUi2,
             Buffer) < 0 )
      {
        pv = LoadIconW(hInst, (LPCWSTR)5);
        v15 = 0;
        if ( pv )
          v15 = 2;
        v11 = v15;
      }
      else
      {
        v12 = *(struct IUnknown **)Buffer;
        v13 = *(int (__fastcall **)(struct IUnknown *, _QWORD, LPVOID *))(**(_QWORD **)Buffer + 40LL);
        SystemMetrics = GetSystemMetrics(49);
        if ( v13(v12, SystemMetrics, &pv) < 0 )
        {
          pv = 0;
        }
        else
        {
          v11 = 2;
          v10 = 1;
        }
      }
      Arguments = 0;
      v23 = 0;
      v6 = ((__int64 (__fastcall *)(struct IUnknown *, HWND, __int64 (__fastcall *)(struct _PSP *, __int64), va_list *))v27->lpVtbl[1].AddRef)(
             v27,
             a1,
             CPropSheetPages::FAddPropSheet,
             &Arguments);
      if ( v6 >= 0 )
      {
        v16 = (unsigned int)Arguments;
        if ( (_DWORD)Arguments )
        {
          memset_0(&v25, 0, sizeof(v25));
          v25.dwSize = 96;
          v25.dwFlags = v11 | 0x2000180;
          v25.hwndParent = a1;
          v25.hInstance = hInst;
          v25.pszCaption = lpCaption;
          v25.nPages = v16;
          v25.ppsp = (LPCPROPSHEETPAGEW)v23;
          v25.hIcon = (HICON)pv;
          v25.nStartPage = a2;
          v25.pfnCallback = (PFNPROPSHEETCALLBACK)HrSetPropertiesTaskbarIcon;
          SetForegroundWindow(a1);
          PropertySheetW(&v25);
        }
      }
      if ( v10 )
        DestroyIcon((HICON)pv);
      CoTaskMemFree(v23);
      ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>(Buffer);
    }
    goto LABEL_31;
  }
LABEL_32:
  if ( lpCaption )
    LocalFree((HLOCAL)lpCaption);
  ReleaseObj(v20);
LABEL_35:
  CConFoldEntry::~CConFoldEntry((CConFoldEntry *)v26);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18004c388  push    rbp
0x18004c38a  push    rbx
0x18004c38b  push    rsi
0x18004c38c  push    rdi
0x18004c38d  push    r12
0x18004c38f  push    r13
0x18004c391  push    r14
0x18004c393  push    r15
0x18004c395  lea     rbp, [rsp-78h]
0x18004c39a  sub     rsp, 178h
0x18004c3a1  mov     rbx, r8
0x18004c3a4  mov     r12d, edx
0x18004c3a7  mov     r15, rcx
0x18004c3aa  xor     r13d, r13d
0x18004c3ad  mov     [rbp+0B0h+arg_18], r13
0x18004c3b4  mov     [rsp+1B0h+lpCaption], r13
0x18004c3b9  mov     [rsp+1B0h+var_160], r13
0x18004c3be  lea     rcx, [rbp+0B0h+var_D0]; this
0x18004c3c2  call    ??0CConFoldEntry@@QEAA@XZ; CConFoldEntry::CConFoldEntry(void)
0x18004c3c7  nop
0x18004c3c8  lea     r8d, [r13+1]
0x18004c3cc  lea     rdx, [rsp+1B0h+var_160]
0x18004c3d1  mov     rcx, rbx
0x18004c3d4  call    ?HrNetConFromPidl@@YAJAEBV?$CPConFoldPidl@VConFoldPidl_v3@@@@PEAPEAUINetConnection@@H@Z; HrNetConFromPidl(CPConFoldPidl<ConFoldPidl_v3> const &,INetConnection * *,int)
0x18004c3d9  mov     ebx, eax
0x18004c3db  test    eax, eax
0x18004c3dd  js      loc_18004C722
0x18004c3e3  mov     rdx, r15; HWND
0x18004c3e6  mov     rcx, [rsp+1B0h+var_160]; struct IUnknown *
0x18004c3eb  call    ?SetLUAParent@@YAXPEAUIUnknown@@PEAUHWND__@@@Z; SetLUAParent(IUnknown *,HWND__ *)
0x18004c3f0  lea     r8, [rbp+0B0h+arg_18]; void **
0x18004c3f7  lea     rdx, IID_INetConnectionPropertyUi; struct _GUID *
0x18004c3fe  mov     rcx, [rsp+1B0h+var_160]; struct INetConnection *
0x18004c403  call    ?HrUIInterfaceFromNetCon@@YAJPEAUINetConnection@@AEBU_GUID@@PEAPEAX@Z; HrUIInterfaceFromNetCon(INetConnection *,_GUID const &,void * *)
0x18004c408  mov     ebx, eax
0x18004c40a  cmp     eax, 80004002h
0x18004c40f  jnz     short loc_18004C444
0x18004c411  mov     qword ptr [rsp+1B0h+Buffer], r13
0x18004c416  lea     r8, [rsp+1B0h+Buffer]; void **
0x18004c41b  lea     rdx, IID_INetConnectionPropertyUi2; struct _GUID *
0x18004c422  mov     rcx, [rsp+1B0h+var_160]; struct INetConnection *
0x18004c427  call    ?HrUIInterfaceFromNetCon@@YAJPEAUINetConnection@@AEBU_GUID@@PEAPEAX@Z; HrUIInterfaceFromNetCon(INetConnection *,_GUID const &,void * *)
0x18004c42c  mov     ebx, eax
0x18004c42e  test    eax, eax
0x18004c430  js      loc_18004C707
0x18004c436  mov     rax, qword ptr [rsp+1B0h+Buffer]
0x18004c43b  mov     [rbp+0B0h+arg_18], rax
0x18004c442  jmp     short loc_18004C44C
0x18004c444  test    eax, eax
0x18004c446  js      loc_18004C707
0x18004c44c  mov     [rsp+1B0h+var_140], r13
0x18004c451  lea     r8, [rsp+1B0h+lpCaption]
0x18004c456  mov     rdx, [rsp+1B0h+var_160]
0x18004c45b  xor     ecx, ecx
0x18004c45d  call    ?HrGetCaption@@YAJW4DIALOG_TYPE@@PEAUINetConnection@@PEAPEAG@Z; HrGetCaption(DIALOG_TYPE,INetConnection *,ushort * *)
0x18004c462  mov     rcx, [rbp+0B0h+arg_18]
0x18004c469  mov     rax, [rcx]
0x18004c46c  lea     r8, [rsp+1B0h+var_140]
0x18004c471  lea     rdx, IID_INetConnectionUiLock
0x18004c478  mov     rax, [rax]
0x18004c47b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c480  test    eax, eax
0x18004c482  js      loc_18004C56A
0x18004c488  mov     [rsp+1B0h+pv], r13
0x18004c48d  mov     rcx, [rsp+1B0h+var_140]
0x18004c492  mov     rax, [rcx]
0x18004c495  lea     rdx, [rsp+1B0h+pv]
0x18004c49a  mov     rax, [rax+18h]
0x18004c49e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c4a3  mov     ebx, eax
0x18004c4a5  mov     rcx, [rsp+1B0h+var_140]; struct IUnknown *
0x18004c4aa  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x18004c4af  cmp     ebx, 1
0x18004c4b2  jnz     loc_18004C562
0x18004c4b8  mov     qword ptr [rsp+1B0h+Buffer], r13
0x18004c4bd  mov     rax, [rsp+1B0h+pv]
0x18004c4c2  mov     [rsp+1B0h+var_150], rax
0x18004c4c7  test    rax, rax
0x18004c4ca  jnz     short loc_18004C4DB
0x18004c4cc  mov     ecx, 423h; unsigned int
0x18004c4d1  call    ?SzLoadIds@@YAPEBGI@Z; SzLoadIds(uint)
0x18004c4d6  mov     [rsp+1B0h+var_150], rax
0x18004c4db  mov     ecx, 422h; unsigned int
0x18004c4e0  call    ?SzLoadIds@@YAPEBGI@Z; SzLoadIds(uint)
0x18004c4e5  mov     rdx, rax; lpSource
0x18004c4e8  lea     rax, [rsp+1B0h+var_150]
0x18004c4ed  mov     [rsp+1B0h+Arguments], rax; Arguments
0x18004c4f2  mov     [rsp+1B0h+nSize], r13d; nSize
0x18004c4f7  lea     rax, [rsp+1B0h+Buffer]
0x18004c4fc  mov     [rsp+1B0h+lpBuffer], rax; lpBuffer
0x18004c501  xor     r9d, r9d; dwLanguageId
0x18004c504  xor     r8d, r8d; dwMessageId
0x18004c507  mov     ecx, 2500h; dwFlags
0x18004c50c  call    cs:__imp_FormatMessageW
0x18004c512  mov     rcx, [rsp+1B0h+pv]; pv
0x18004c517  test    rcx, rcx
0x18004c51a  jz      short loc_18004C522
0x18004c51c  call    cs:__imp_CoTaskMemFree
0x18004c522  mov     rdx, qword ptr [rsp+1B0h+Buffer]; lpText
0x18004c527  test    rdx, rdx
0x18004c52a  jz      loc_18004C6F4
0x18004c530  lea     r8, ?c_szEmpty@@3QBGB; ushort const near * const c_szEmpty
0x18004c537  mov     rax, [rsp+1B0h+lpCaption]
0x18004c53c  test    rax, rax
0x18004c53f  cmovnz  r8, rax; lpCaption
0x18004c543  mov     r9d, 10h; uType
0x18004c549  mov     rcx, r15; hWnd
0x18004c54c  call    cs:__imp_MessageBoxW
0x18004c552  mov     rcx, qword ptr [rsp+1B0h+Buffer]; hMem
0x18004c557  call    cs:__imp_LocalFree
0x18004c55d  jmp     loc_18004C6F4
0x18004c562  test    ebx, ebx
0x18004c564  js      loc_18004C6F4
0x18004c56a  mov     rcx, [rbp+0B0h+arg_18]
0x18004c571  mov     rax, [rcx]
0x18004c574  mov     rdx, [rsp+1B0h+var_160]
0x18004c579  mov     rax, [rax+18h]
0x18004c57d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c582  mov     ebx, eax
0x18004c584  test    eax, eax
0x18004c586  js      loc_18004C6F4
0x18004c58c  mov     r14d, r13d
0x18004c58f  mov     qword ptr [rsp+1B0h+Buffer], r13
0x18004c594  mov     [rsp+1B0h+pv], r13
0x18004c599  mov     esi, r13d
0x18004c59c  mov     rcx, [rbp+0B0h+arg_18]
0x18004c5a3  mov     rax, [rcx]
0x18004c5a6  lea     r8, [rsp+1B0h+Buffer]
0x18004c5ab  lea     rdx, IID_INetConnectionPropertyUi2
0x18004c5b2  mov     rax, [rax]
0x18004c5b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c5ba  test    eax, eax
0x18004c5bc  js      short loc_18004C5FD
0x18004c5be  mov     rdi, qword ptr [rsp+1B0h+Buffer]
0x18004c5c3  mov     rax, [rdi]
0x18004c5c6  mov     rbx, [rax+28h]
0x18004c5ca  mov     ecx, 31h ; '1'; nIndex
0x18004c5cf  call    cs:__imp_GetSystemMetrics
0x18004c5d5  lea     r8, [rsp+1B0h+pv]
0x18004c5da  mov     edx, eax
0x18004c5dc  mov     rcx, rdi
0x18004c5df  mov     rax, rbx
0x18004c5e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c5e7  test    eax, eax
0x18004c5e9  js      short loc_18004C5F6
0x18004c5eb  mov     esi, 2
0x18004c5f0  lea     r14d, [rsi-1]
0x18004c5f4  jmp     short loc_18004C624
0x18004c5f6  mov     [rsp+1B0h+pv], r13
0x18004c5fb  jmp     short loc_18004C624
0x18004c5fd  mov     edx, 5; lpIconName
0x18004c602  mov     rcx, cs:hInst; hInstance
0x18004c609  call    cs:__imp_LoadIconW
0x18004c60f  mov     [rsp+1B0h+pv], rax
0x18004c614  mov     ecx, r13d
0x18004c617  mov     esi, 2
0x18004c61c  test    rax, rax
0x18004c61f  cmovnz  ecx, esi
0x18004c622  mov     esi, ecx
0x18004c624  mov     [rsp+1B0h+var_150], r13
0x18004c629  mov     [rsp+1B0h+var_148], r13
0x18004c62e  mov     rcx, [rbp+0B0h+arg_18]
0x18004c635  mov     rax, [rcx]
0x18004c638  lea     r9, [rsp+1B0h+var_150]
0x18004c63d  lea     r8, ?FAddPropSheet@CPropSheetPages@@SAHPEAU_PSP@@_J@Z; CPropSheetPages::FAddPropSheet(_PSP *,__int64)
0x18004c644  mov     rdx, r15
0x18004c647  mov     rax, [rax+20h]
0x18004c64b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c650  mov     ebx, eax
0x18004c652  test    eax, eax
0x18004c654  js      short loc_18004C6CD
0x18004c656  mov     edi, dword ptr [rsp+1B0h+var_150]
0x18004c65a  test    edi, edi
0x18004c65c  jz      short loc_18004C6CD
0x18004c65e  mov     r13d, 60h ; '`'
0x18004c664  mov     r8d, r13d; Size
0x18004c667  xor     edx, edx; Val
0x18004c669  lea     rcx, [rbp+0B0h+var_130]; void *
0x18004c66d  call    memset_0
0x18004c672  mov     [rbp+0B0h+var_130.dwSize], r13d
0x18004c676  or      esi, 2000180h
0x18004c67c  mov     [rbp+0B0h+var_130.dwFlags], esi
0x18004c67f  mov     [rbp+0B0h+var_130.hwndParent], r15
0x18004c683  mov     rax, cs:hInst
0x18004c68a  mov     [rbp+0B0h+var_130.hInstance], rax
0x18004c68e  mov     rax, [rsp+1B0h+lpCaption]
0x18004c693  mov     [rbp+0B0h+var_130.pszCaption], rax
0x18004c697  mov     [rbp+0B0h+var_130.nPages], edi
0x18004c69a  mov     rax, [rsp+1B0h+var_148]
0x18004c69f  mov     qword ptr [rbp+0B0h+var_130.38h], rax
0x18004c6a3  mov     rax, [rsp+1B0h+pv]
0x18004c6a8  mov     qword ptr [rbp+0B0h+var_130.18h], rax
0x18004c6ac  mov     dword ptr [rbp+0B0h+var_130.30h], r12d
0x18004c6b0  lea     rax, ?HrSetPropertiesTaskbarIcon@@YAHPEAUHWND__@@I_J@Z; HrSetPropertiesTaskbarIcon(HWND__ *,uint,__int64)
0x18004c6b7  mov     [rbp+0B0h+var_130.pfnCallback], rax
0x18004c6bb  mov     rcx, r15; hWnd
0x18004c6be  call    cs:__imp_SetForegroundWindow
0x18004c6c4  lea     rcx, [rbp+0B0h+var_130]; LPCPROPSHEETHEADERW
0x18004c6c8  call    PropertySheetW
0x18004c6cd  test    r14d, r14d
0x18004c6d0  jz      short loc_18004C6DE
0x18004c6d2  mov     rcx, [rsp+1B0h+pv]; hIcon
0x18004c6d7  call    cs:__imp_DestroyIcon
0x18004c6dd  nop
0x18004c6de  mov     rcx, [rsp+1B0h+var_148]; pv
0x18004c6e3  call    cs:__imp_CoTaskMemFree
0x18004c6e9  nop
0x18004c6ea  lea     rcx, [rsp+1B0h+Buffer]
0x18004c6ef  call    ??1?$CComPtrBase@UIUPnPService@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>(void)
0x18004c6f4  xor     ecx, ecx; struct IUnknown *
0x18004c6f6  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x18004c6fb  mov     rcx, [rbp+0B0h+arg_18]; struct IUnknown *
0x18004c702  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x18004c707  mov     rcx, [rsp+1B0h+lpCaption]; hMem
0x18004c70c  test    rcx, rcx
0x18004c70f  jz      short loc_18004C717
0x18004c711  call    cs:__imp_LocalFree
0x18004c717  mov     rcx, [rsp+1B0h+var_160]; struct IUnknown *
0x18004c71c  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x18004c721  nop
0x18004c722  lea     rcx, [rbp+0B0h+var_D0]; this
0x18004c726  call    ??1CConFoldEntry@@QEAA@XZ; CConFoldEntry::~CConFoldEntry(void)
0x18004c72b  mov     eax, ebx
0x18004c72d  add     rsp, 178h
0x18004c734  pop     r15
0x18004c736  pop     r14
0x18004c738  pop     r13
0x18004c73a  pop     r12
0x18004c73c  pop     rdi
0x18004c73d  pop     rsi
0x18004c73e  pop     rbx
0x18004c73f  pop     rbp
0x18004c740  retn
```
