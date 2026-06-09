# CFtpMenu::_DownloadThreadProc(CFtpMenu::DOWNLOADTHREADINFO *)

- ea: `0x18000f25c`
- end: `0x18000f5ae`
- name: `?_DownloadThreadProc@CFtpMenu@@IEAAKPEAUDOWNLOADTHREADINFO@1@@Z`
- size: `850`
- prototype: `unsigned int __fastcall(CFtpMenu *__hidden this, struct CFtpMenu::DOWNLOADTHREADINFO *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000e0e0`

## callees

- `0x180002240`
- `0x180002610`
- `0x18000d3f0`
- `0x18000f25c`
- `0x18001d6bc`
- `0x18001e1cc`
- `0x18001fa30`
- `0x18001fc24`
- `0x180023ce4`
- `0x180024134`
- `0x1800271f0`
- `0x180028010`

## import_xrefs

- `SHELL32!SHPathPrepareForWriteW` at `0x18000f352`
- `SHELL32!SHPathPrepareForWriteW` at `0x18000f352`
- `SHELL32!__imp_ILClone` at `0x18000f2b3`
- `SHELL32!__imp_ILClone` at `0x18000f2b3`
- `SHELL32!__imp_ILFree` at `0x18000f561`
- `SHELL32!__imp_ILFree` at `0x18000f561`
- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x18000f3ce`
- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x18000f3ce`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000f41c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000f41c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f459`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f459`
- `WININET!InternetSetStatusCallbackW` at `0x18000f44e`
- `WININET!InternetSetStatusCallbackW` at `0x18000f44e`

## pseudocode

```c
__int64 __fastcall CFtpMenu::_DownloadThreadProc(CFtpMenu *this, struct CFtpMenu::DOWNLOADTHREADINFO *a2)
{
  __int64 v3; // rcx
  const ITEMIDLIST *v5; // rcx
  LPITEMIDLIST v6; // rax
  __int64 v7; // rdx
  unsigned int v8; // r9d
  __int64 v9; // r8
  struct _ITEMIDLIST *v10; // r15
  int v11; // ebx
  __int64 v12; // rcx
  struct CFtpFolder *v13; // rax
  CFtpSite *v14; // rcx
  HWND v15; // r14
  unsigned int v16; // edx
  IUnknown *v17; // rcx
  HWND v18; // rdx
  int v19; // eax
  struct IProgressDialog *v20; // rcx
  int v21; // eax
  struct GLOBALTIMEOUTINFO **v22; // rcx
  unsigned int v24; // [rsp+28h] [rbp-D8h]
  unsigned int v25; // [rsp+30h] [rbp-D0h]
  HWND phwnd[2]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v27[6]; // [rsp+50h] [rbp-B0h] BYREF
  struct IProgressDialog *Instance; // [rsp+80h] [rbp-80h]
  __int64 v29; // [rsp+88h] [rbp-78h]
  __int64 v30; // [rsp+90h] [rbp-70h]
  __int128 v31; // [rsp+98h] [rbp-68h]
  struct IProgressDialog *v32; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v33; // [rsp+B8h] [rbp-48h]
  __int64 v34; // [rsp+C0h] [rbp-40h]
  __int128 v35; // [rsp+C8h] [rbp-38h]
  WCHAR Buffer[264]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v37[2088]; // [rsp+2F0h] [rbp+1F0h] BYREF

  v3 = *((_QWORD *)this + 6);
  if ( v3 )
  {
    v5 = *(const ITEMIDLIST **)(v3 + 48);
    phwnd[0] = 0;
    v6 = ILClone(v5);
    v9 = *((_QWORD *)this + 6);
    v10 = v6;
    v27[0] = *((_QWORD *)a2 + 2);
    v11 = -2147012867;
    v12 = *((_QWORD *)this + 7);
    v27[1] = v6;
    v13 = (struct CFtpFolder *)*((_QWORD *)this + 5);
    v27[2] = v12;
    v27[3] = 0;
    v27[4] = v13;
    v27[5] = v9;
    Instance = 0;
    v29 = 0;
    v30 = 0;
    v31 = 0;
    v14 = *(CFtpSite **)(v9 + 16);
    if ( !v14
      || (CFtpSite::GetHint(
            v14,
            0,
            *(const struct _ITEMIDLIST **)(v9 + 40),
            0,
            (void **)phwnd,
            *((struct IUnknown **)this + 2),
            v13),
          (v15 = phwnd[0]) == 0) )
    {
LABEL_27:
      DisplayWininetError(*((HWND *)this + 7), v7, v11, v8, 0x1A2u, v24, v25, 0);
LABEL_28:
      ILFree(v10);
      goto LABEL_29;
    }
    if ( SHPathPrepareForWriteW(*((HWND *)this + 7), 0, *((LPCWSTR *)a2 + 2), 1u) < 0 )
    {
      v11 = -2147023673;
    }
    else
    {
      v11 = UrlCreateFromPidl(v10, 0x8000u, v37, 0x824u, 0xC0000000, 0);
      if ( v11 >= 0 )
      {
        v32 = 0;
        v33 = 0;
        v35 = 0;
        v34 = 0;
        *((_QWORD *)&v31 + 1) = v15;
        Instance = CProgressDialog_CreateInstance(0x4Au, v16);
        if ( Instance )
        {
          v17 = (IUnknown *)*((_QWORD *)this + 2);
          phwnd[0] = 0;
          IUnknown_GetWindow(v17, phwnd);
          v18 = phwnd[0];
          if ( !phwnd[0] )
          {
            v18 = (HWND)*((_QWORD *)this + 7);
            phwnd[0] = v18;
          }
          ((void (__fastcall *)(struct IProgressDialog *, HWND, _QWORD, __int64, _QWORD))Instance->lpVtbl->SetAnimation)(
            Instance,
            v18,
            0,
            2,
            0);
          if ( LoadStringW(g_hinst, 0x122u, Buffer, 260) )
            ((void (__fastcall *)(struct IProgressDialog *, __int64, WCHAR *, _QWORD, _QWORD))Instance->lpVtbl[1].StartProgressDialog)(
              Instance,
              2,
              Buffer,
              0,
              0);
          if ( !InternetSetStatusCallbackW(v15, FtpProgressInternetStatusCB) )
            GetLastError();
          v32 = Instance;
        }
        v19 = CFtpPidlList::RecursiveEnum(*((CFtpPidlList **)a2 + 1), v10, FileSizeCountItemCB, v15, &v32);
        v20 = Instance;
        v11 = v19;
        if ( Instance )
        {
          ((void (__fastcall *)(struct IProgressDialog *, __int64))Instance->lpVtbl[1].SetTitle)(Instance, 1);
          v20 = Instance;
        }
        if ( v11 >= 0 )
        {
          v29 = v33;
          v30 = v34;
          *(_DWORD *)(*((_QWORD *)a2 + 1) + 28LL) = 0;
          v21 = CFtpPidlList::RecursiveEnum(
                  *((CFtpPidlList **)a2 + 1),
                  v10,
                  (int (*)(void *, void *, const struct _ITEMIDLIST *, int *, void *))DownloadItemCB,
                  v15,
                  v27);
          v20 = Instance;
          v11 = v21;
        }
        if ( v20 )
        {
          ((void (__fastcall *)(struct IProgressDialog *))v20->lpVtbl->HasUserCancelled)(v20);
          ((void (__fastcall *)(struct IProgressDialog *))Instance->lpVtbl->SetTitle)(Instance);
        }
        if ( !*((_QWORD *)&v31 + 1) )
        {
LABEL_25:
          if ( (int)(v11 + 0x80000000) < 0 || v11 == -2147023673 )
            goto LABEL_28;
          goto LABEL_27;
        }
      }
    }
    v7 = *((_QWORD *)this + 6);
    v22 = *(struct GLOBALTIMEOUTINFO ***)(v7 + 16);
    if ( v22 )
      CFtpSite::ReleaseHint(v22, *(const struct _ITEMIDLIST **)(v7 + 40), (struct GLOBALTIMEOUTINFO *)v15);
    goto LABEL_25;
  }
LABEL_29:
  if ( a2 )
  {
    CFtpMenu::DOWNLOADTHREADINFO::~DOWNLOADTHREADINFO(a2);
    operator delete(a2, 0x20u);
  }
  return 0;
}

```

## disassembly

```asm
0x18000f25c  mov     [rsp-8+arg_10], rbx
0x18000f261  mov     [rsp-8+arg_18], rsi
0x18000f266  push    rbp
0x18000f267  push    rdi
0x18000f268  push    r12
0x18000f26a  push    r14
0x18000f26c  push    r15
0x18000f26e  lea     rbp, [rsp-1250h]
0x18000f276  mov     eax, 1350h
0x18000f27b  call    _alloca_probe
0x18000f280  sub     rsp, rax
0x18000f283  mov     rax, cs:__security_cookie
0x18000f28a  xor     rax, rsp
0x18000f28d  mov     [rbp+1270h+var_30], rax
0x18000f294  mov     rdi, rcx
0x18000f297  xor     r12d, r12d
0x18000f29a  mov     rcx, [rcx+30h]
0x18000f29e  mov     rsi, rdx
0x18000f2a1  test    rcx, rcx
0x18000f2a4  jz      loc_18000F567
0x18000f2aa  mov     rcx, [rcx+30h]; pidl
0x18000f2ae  mov     [rsp+1370h+phwnd], r12
0x18000f2b3  call    cs:__imp_ILClone
0x18000f2b9  mov     rcx, [rsi+10h]
0x18000f2bd  xorps   xmm0, xmm0
0x18000f2c0  mov     r8, [rdi+30h]
0x18000f2c4  mov     r15, rax
0x18000f2c7  mov     [rsp+1370h+var_1320], rcx
0x18000f2cc  mov     ebx, 80072EFDh
0x18000f2d1  mov     rcx, [rdi+38h]
0x18000f2d5  mov     [rsp+1370h+var_1318], rax
0x18000f2da  mov     rax, [rdi+28h]
0x18000f2de  mov     [rsp+1370h+var_1310], rcx
0x18000f2e3  mov     [rsp+1370h+var_1308], r12
0x18000f2e8  mov     [rsp+1370h+var_1300], rax
0x18000f2ed  mov     [rsp+1370h+var_12F8], r8
0x18000f2f2  mov     [rbp+1270h+var_12F0], r12
0x18000f2f6  mov     [rbp+1270h+var_12E8], r12
0x18000f2fa  mov     [rbp+1270h+var_12E0], r12
0x18000f2fe  movups  [rbp+1270h+var_12D8], xmm0
0x18000f302  mov     rcx, [r8+10h]; this
0x18000f306  test    rcx, rcx
0x18000f309  jz      loc_18000F545
0x18000f30f  mov     r8, [r8+28h]; struct _ITEMIDLIST *
0x18000f313  xor     r9d, r9d; struct CStatusBar *
0x18000f316  mov     [rsp+1370h+var_1340], rax; unsigned int
0x18000f31b  xor     edx, edx; HWND
0x18000f31d  mov     rax, [rdi+10h]
0x18000f321  mov     [rsp+1370h+var_1348], rax; unsigned int
0x18000f326  lea     rax, [rsp+1370h+phwnd]
0x18000f32b  mov     [rsp+1370h+var_1350], rax; void **
0x18000f330  call    ?GetHint@CFtpSite@@QEAAJPEAUHWND__@@PEFBU_ITEMIDLIST@@PEAVCStatusBar@@PEAPEAXPEAUIUnknown@@PEAVCFtpFolder@@@Z; CFtpSite::GetHint(HWND__ *,_ITEMIDLIST const *,CStatusBar *,void * *,IUnknown *,CFtpFolder *)
0x18000f335  mov     r14, [rsp+1370h+phwnd]
0x18000f33a  test    r14, r14
0x18000f33d  jz      loc_18000F545
0x18000f343  mov     r8, [rsi+10h]; pszPath
0x18000f347  lea     r9d, [r12+1]; dwFlags
0x18000f34c  mov     rcx, [rdi+38h]; hwnd
0x18000f350  xor     edx, edx; punkEnableModless
0x18000f352  call    cs:__imp_SHPathPrepareForWriteW
0x18000f358  test    eax, eax
0x18000f35a  js      loc_18000F513
0x18000f360  mov     dword ptr [rsp+1370h+var_1348], r12d; int
0x18000f365  lea     r8, [rbp+1270h+var_1080]; unsigned __int16 *
0x18000f36c  mov     r9d, 824h; unsigned int
0x18000f372  mov     dword ptr [rsp+1370h+var_1350], 0C0000000h; unsigned int
0x18000f37a  mov     edx, 8000h; unsigned int
0x18000f37f  mov     rcx, r15; struct _ITEMIDLIST *
0x18000f382  call    ?UrlCreateFromPidl@@YAJPEFBU_ITEMIDLIST@@KPEAGKKH@Z; UrlCreateFromPidl(_ITEMIDLIST const *,ulong,ushort *,ulong,ulong,int)
0x18000f387  mov     ebx, eax
0x18000f389  test    eax, eax
0x18000f38b  js      loc_18000F518
0x18000f391  xorps   xmm0, xmm0
0x18000f394  mov     [rbp+1270h+var_12C0], r12
0x18000f398  lea     ecx, [r12+4Ah]; uID
0x18000f39d  mov     [rbp+1270h+var_12B8], r12
0x18000f3a1  movdqu  [rbp+1270h+var_12A8], xmm0
0x18000f3a6  mov     [rbp+1270h+var_12B0], r12
0x18000f3aa  mov     qword ptr [rbp+1270h+var_12D8+8], r14
0x18000f3ae  call    ?CProgressDialog_CreateInstance@@YAPEAUIProgressDialog@@II@Z; CProgressDialog_CreateInstance(uint,uint)
0x18000f3b3  mov     [rbp+1270h+var_12F0], rax
0x18000f3b7  test    rax, rax
0x18000f3ba  jz      loc_18000F467
0x18000f3c0  mov     rcx, [rdi+10h]; punk
0x18000f3c4  lea     rdx, [rsp+1370h+phwnd]; phwnd
0x18000f3c9  mov     [rsp+1370h+phwnd], r12
0x18000f3ce  call    cs:__imp_IUnknown_GetWindow
0x18000f3d4  mov     rdx, [rsp+1370h+phwnd]
0x18000f3d9  test    rdx, rdx
0x18000f3dc  jnz     short loc_18000F3E7
0x18000f3de  mov     rdx, [rdi+38h]
0x18000f3e2  mov     [rsp+1370h+phwnd], rdx
0x18000f3e7  mov     rcx, [rbp+1270h+var_12F0]
0x18000f3eb  mov     ebx, 2
0x18000f3f0  mov     r9d, ebx
0x18000f3f3  mov     [rsp+1370h+var_1350], r12
0x18000f3f8  xor     r8d, r8d
0x18000f3fb  mov     rax, [rcx]
0x18000f3fe  mov     rax, [rax+18h]
0x18000f402  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f407  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hInstance
0x18000f40e  lea     r8, [rbp+1270h+Buffer]; lpBuffer
0x18000f412  mov     r9d, 104h; cchBufferMax
0x18000f418  lea     edx, [r9+1Eh]; uID
0x18000f41c  call    cs:__imp_LoadStringW
0x18000f422  test    eax, eax
0x18000f424  jz      short loc_18000F444
0x18000f426  mov     rcx, [rbp+1270h+var_12F0]
0x18000f42a  lea     r8, [rbp+1270h+Buffer]
0x18000f42e  xor     r9d, r9d
0x18000f431  mov     [rsp+1370h+var_1350], r12
0x18000f436  mov     edx, ebx
0x18000f438  mov     rax, [rcx]
0x18000f43b  mov     rax, [rax+50h]
0x18000f43f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f444  lea     rdx, ?FtpProgressInternetStatusCB@@YAXPEAX_KK0K@Z; lpfnInternetCallback
0x18000f44b  mov     rcx, r14; hInternet
0x18000f44e  call    cs:__imp_InternetSetStatusCallbackW
0x18000f454  test    rax, rax
0x18000f457  jnz     short loc_18000F45F
0x18000f459  call    cs:__imp_GetLastError
0x18000f45f  mov     rax, [rbp+1270h+var_12F0]
0x18000f463  mov     [rbp+1270h+var_12C0], rax
0x18000f467  mov     rcx, [rsi+8]; this
0x18000f46b  lea     rax, [rbp+1270h+var_12C0]
0x18000f46f  mov     r9, r14; void *
0x18000f472  mov     [rsp+1370h+var_1350], rax; void *
0x18000f477  lea     r8, ?FileSizeCountItemCB@@YAJPEAX0PEFBU_ITEMIDLIST@@PEAH0@Z; int (*)(void *, void *, const struct _ITEMIDLIST *, int *, void *)
0x18000f47e  mov     rdx, r15; struct _ITEMIDLIST *
0x18000f481  call    ?RecursiveEnum@CFtpPidlList@@QEAAJPEFBU_ITEMIDLIST@@P6AJPEAX10PEAH1@Z11@Z; CFtpPidlList::RecursiveEnum(_ITEMIDLIST const *,long (*)(void *,void *,_ITEMIDLIST const *,int *,void *),void *,void *)
0x18000f486  mov     rcx, [rbp+1270h+var_12F0]
0x18000f48a  mov     ebx, eax
0x18000f48c  test    rcx, rcx
0x18000f48f  jz      short loc_18000F4A8
0x18000f491  mov     rax, [rcx]
0x18000f494  xor     r8d, r8d
0x18000f497  mov     rax, [rax+60h]
0x18000f49b  lea     edx, [r8+1]
0x18000f49f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4a4  mov     rcx, [rbp+1270h+var_12F0]
0x18000f4a8  test    ebx, ebx
0x18000f4aa  js      short loc_18000F4EA
0x18000f4ac  mov     rax, [rbp+1270h+var_12B8]
0x18000f4b0  lea     r8, ?DownloadItemCB@@YAJPEAX0PEFBU_ITEMIDLIST@@PEAH0@Z; int (*)(void *, void *, const struct _ITEMIDLIST *, int *, void *)
0x18000f4b7  mov     [rbp+1270h+var_12E8], rax
0x18000f4bb  mov     r9, r14; void *
0x18000f4be  mov     rax, [rbp+1270h+var_12B0]
0x18000f4c2  mov     rdx, r15; struct _ITEMIDLIST *
0x18000f4c5  mov     [rbp+1270h+var_12E0], rax
0x18000f4c9  mov     rax, [rsi+8]
0x18000f4cd  mov     [rax+1Ch], r12d
0x18000f4d1  lea     rax, [rsp+1370h+var_1320]
0x18000f4d6  mov     rcx, [rsi+8]; this
0x18000f4da  mov     [rsp+1370h+var_1350], rax; void *
0x18000f4df  call    ?RecursiveEnum@CFtpPidlList@@QEAAJPEFBU_ITEMIDLIST@@P6AJPEAX10PEAH1@Z11@Z; CFtpPidlList::RecursiveEnum(_ITEMIDLIST const *,long (*)(void *,void *,_ITEMIDLIST const *,int *,void *),void *,void *)
0x18000f4e4  mov     rcx, [rbp+1270h+var_12F0]
0x18000f4e8  mov     ebx, eax
0x18000f4ea  test    rcx, rcx
0x18000f4ed  jz      short loc_18000F50B
0x18000f4ef  mov     rax, [rcx]
0x18000f4f2  mov     rax, [rax+20h]
0x18000f4f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4fb  mov     rcx, [rbp+1270h+var_12F0]
0x18000f4ff  mov     rax, [rcx]
0x18000f502  mov     rax, [rax+10h]
0x18000f506  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f50b  cmp     qword ptr [rbp+1270h+var_12D8+8], r12
0x18000f50f  jnz     short loc_18000F518
0x18000f511  jmp     short loc_18000F531
0x18000f513  mov     ebx, 800704C7h
0x18000f518  mov     rdx, [rdi+30h]
0x18000f51c  mov     rcx, [rdx+10h]; this
0x18000f520  test    rcx, rcx
0x18000f523  jz      short loc_18000F531
0x18000f525  mov     rdx, [rdx+28h]; struct _ITEMIDLIST *
0x18000f529  mov     r8, r14; void *
0x18000f52c  call    ?ReleaseHint@CFtpSite@@QEAAXPEFBU_ITEMIDLIST@@PEAX@Z; CFtpSite::ReleaseHint(_ITEMIDLIST const *,void *)
0x18000f531  mov     ecx, 80000000h
0x18000f536  lea     eax, [rbx+rcx]
0x18000f539  test    ecx, eax
0x18000f53b  jnz     short loc_18000F55E
0x18000f53d  cmp     ebx, 800704C7h
0x18000f543  jz      short loc_18000F55E
0x18000f545  mov     rcx, [rdi+38h]; HWND
0x18000f549  mov     r8d, ebx; int
0x18000f54c  mov     [rsp+1370h+var_1338], r12; struct IProgressDialog *
0x18000f551  mov     dword ptr [rsp+1370h+var_1350], 1A2h; unsigned int
0x18000f559  call    ?DisplayWininetError@@YAHPEAUHWND__@@HJIIIIPEAUIProgressDialog@@@Z; DisplayWininetError(HWND__ *,int,long,uint,uint,uint,uint,IProgressDialog *)
0x18000f55e  mov     rcx, r15; pidl
0x18000f561  call    cs:__imp_ILFree
0x18000f567  test    rsi, rsi
0x18000f56a  jz      short loc_18000F581
0x18000f56c  mov     rcx, rsi; this
0x18000f56f  call    ??1DOWNLOADTHREADINFO@CFtpMenu@@QEAA@XZ; CFtpMenu::DOWNLOADTHREADINFO::~DOWNLOADTHREADINFO(void)
0x18000f574  mov     edx, 20h ; ' '; unsigned __int64
0x18000f579  mov     rcx, rsi; void *
0x18000f57c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f581  xor     eax, eax
0x18000f583  mov     rcx, [rbp+1270h+var_30]
0x18000f58a  xor     rcx, rsp; StackCookie
0x18000f58d  call    __security_check_cookie
0x18000f592  lea     r11, [rsp+1370h+var_20]
0x18000f59a  mov     rbx, [r11+40h]
0x18000f59e  mov     rsi, [r11+48h]
0x18000f5a2  mov     rsp, r11
0x18000f5a5  pop     r15
0x18000f5a7  pop     r14
0x18000f5a9  pop     r12
0x18000f5ab  pop     rdi
0x18000f5ac  pop     rbp
0x18000f5ad  retn
```
