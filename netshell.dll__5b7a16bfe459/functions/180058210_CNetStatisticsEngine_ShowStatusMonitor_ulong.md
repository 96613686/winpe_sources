# CNetStatisticsEngine::ShowStatusMonitor(ulong)

- ea: `0x180058210`
- end: `0x180058440`
- name: `?ShowStatusMonitor@CNetStatisticsEngine@@UEAAJK@Z`
- size: `560`
- prototype: `__int64 __fastcall(CNetStatisticsEngine *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `15`
- tags: `service_task`

## callees

- `0x180002010`
- `0x180018d74`
- `0x18001eb7c`
- `0x18002a7a0`
- `0x18002bf6c`
- `0x180034ba0`
- `0x180040790`
- `0x180041dc8`
- `0x180042850`
- `0x18004c20c`
- `0x180057bec`
- `0x180058210`
- `0x1800594dc`
- `0x180060c00`
- `0x180065010`

## import_xrefs

- `USER32!GetSystemMetrics` at `0x1800582a2`
- `USER32!GetSystemMetrics` at `0x1800582a2`
- `USER32!DestroyIcon` at `0x180058413`
- `USER32!DestroyIcon` at `0x180058413`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180058405`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180058405`
- `ole32!CoTaskMemFree` at `0x18005842a`
- `ole32!CoTaskMemFree` at `0x18005842a`

## pseudocode

```c
__int64 __fastcall CNetStatisticsEngine::ShowStatusMonitor(CNetStatisticsEngine *this, int a2)
{
  HICON v2; // rbx
  CWaitCursor *v5; // rsi
  __int64 v6; // rax
  int IconFromMediaType; // edi
  int v8; // ebx
  int v9; // edi
  int SystemMetrics; // eax
  CConnectionList *v11; // rcx
  unsigned int v12; // edx
  DWORD v13; // ecx
  CPspStatusMonitorGen *v14; // rcx
  unsigned int v15; // edx
  __int64 v17; // [rsp+30h] [rbp-39h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-31h]
  PROPSHEETHEADERW_V2 v19; // [rsp+40h] [rbp-29h] BYREF
  struct IUnknown v20; // [rsp+D0h] [rbp+67h] BYREF
  HICON v21; // [rsp+E0h] [rbp+77h] BYREF
  HLOCAL hMem; // [rsp+E8h] [rbp+7Fh] BYREF

  v2 = 0;
  v21 = 0;
  v17 = 0;
  pv = 0;
  v20.lpVtbl = 0;
  hMem = 0;
  v5 = (CWaitCursor *)MemAlloc(8u);
  if ( v5 )
    *(_QWORD *)v5 = BeginWaitCursor();
  else
    v5 = 0;
  v6 = *(_QWORD *)this;
  *((_DWORD *)this + 47) = a2;
  IconFromMediaType = (*(__int64 (__fastcall **)(CNetStatisticsEngine *, _QWORD, __int64 (__fastcall *)(struct _PSP *, __int64), __int64 *))(v6 + 112))(
                        this,
                        0,
                        CPropSheetPages::FAddPropSheet,
                        &v17);
  if ( IconFromMediaType >= 0 )
  {
    *(_DWORD *)(*((_QWORD *)this + 9) + 144LL) = 1;
    v8 = *((_DWORD *)this + 31);
    v9 = *((_DWORD *)this + 30);
    SystemMetrics = GetSystemMetrics(49);
    IconFromMediaType = HrGetIconFromMediaType(SystemMetrics, v9, v8, 7, 0, (__int64)&v21);
    if ( IconFromMediaType < 0 )
    {
      v2 = v21;
    }
    else
    {
      if ( (int)HrGetConnectionFromPersistData(
                  (const struct _GUID *)((char *)this + 148),
                  *((const unsigned __int8 **)this + 17),
                  *((_DWORD *)this + 36),
                  &IID_INetConnection,
                  &v20,
                  1) >= 0 )
      {
        HrGetCaption(1, v20.lpVtbl, &hMem);
        ReleaseObj((struct IUnknown *)v20.lpVtbl);
        v20.lpVtbl = 0;
      }
      v2 = v21;
      if ( (_DWORD)v17 )
      {
        CConnectionList::AddNotificationIfPossible(v11);
        memset_0(&v19, 0, sizeof(v19));
        v13 = 33554816;
        v19.hInstance = hInst;
        v19.pszCaption = (LPCWSTR)hMem;
        v19.nPages = v17;
        v19.ppsp = (LPCPROPSHEETPAGEW)pv;
        v19.nStartPage = *((_DWORD *)this + 47);
        v19.pfnCallback = (PFNPROPSHEETCALLBACK)CNetStatisticsEngine::PshCallback;
        if ( v2 )
          v13 = 33554818;
        v19.dwSize = 96;
        v19.dwFlags = v13;
        v19.hwndParent = 0;
        v19.hIcon = v2;
        if ( v5 )
          CWaitCursor::`scalar deleting destructor'(v5, v12);
        v5 = 0;
        if ( !PropertySheetW(&v19) )
          IconFromMediaType = HrFromLastWin32Error();
        v14 = (CPspStatusMonitorGen *)*((_QWORD *)this + 9);
        if ( v14 )
        {
          CPspStatusMonitorGen::HrCleanupGenPage(v14);
          ReleaseObj((struct IUnknown *)((*((_QWORD *)this + 9) + 16LL) & -(__int64)(*((_QWORD *)this + 9) != 0)));
          *((_QWORD *)this + 9) = 0;
        }
        CConnectionList::RemoveNotificationIfPossible(v14);
      }
    }
  }
  LocalFree(hMem);
  if ( v2 )
    DestroyIcon(v2);
  if ( v5 )
    CWaitCursor::`scalar deleting destructor'(v5, v15);
  CoTaskMemFree(pv);
  return (unsigned int)IconFromMediaType;
}

```

## disassembly

```asm
0x180058210  push    rbp
0x180058212  push    rbx
0x180058213  push    rsi
0x180058214  push    rdi
0x180058215  push    r14
0x180058217  lea     rbp, [rsp-37h]
0x18005821c  sub     rsp, 0A0h
0x180058223  xor     ebx, ebx
0x180058225  mov     r14, rcx
0x180058228  mov     edi, edx
0x18005822a  mov     [rbp+57h+arg_10], rbx
0x18005822e  mov     [rbp+57h+var_90], rbx
0x180058232  mov     [rbp+57h+pv], rbx
0x180058236  lea     ecx, [rbx+8]; unsigned __int64
0x180058239  mov     [rbp+57h+arg_0.lpVtbl], rbx
0x18005823d  mov     [rbp+57h+hMem], rbx
0x180058241  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x180058246  mov     rsi, rax
0x180058249  test    rax, rax
0x18005824c  jz      short loc_180058258
0x18005824e  call    ?BeginWaitCursor@@YAPEAUHICON__@@XZ; BeginWaitCursor(void)
0x180058253  mov     [rsi], rax
0x180058256  jmp     short loc_18005825A
0x180058258  xor     esi, esi
0x18005825a  mov     rax, [r14]
0x18005825d  lea     r9, [rbp+57h+var_90]
0x180058261  lea     r8, ?FAddPropSheet@CPropSheetPages@@SAHPEAU_PSP@@_J@Z; CPropSheetPages::FAddPropSheet(_PSP *,__int64)
0x180058268  mov     [r14+0BCh], edi
0x18005826f  xor     edx, edx
0x180058271  mov     rcx, r14
0x180058274  mov     rax, [rax+70h]
0x180058278  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005827d  mov     edi, eax
0x18005827f  test    eax, eax
0x180058281  js      loc_180058401
0x180058287  mov     rax, [r14+48h]
0x18005828b  mov     ecx, 31h ; '1'; nIndex
0x180058290  mov     dword ptr [rax+90h], 1
0x18005829a  mov     ebx, [r14+7Ch]
0x18005829e  mov     edi, [r14+78h]
0x1800582a2  call    cs:__imp_GetSystemMetrics
0x1800582a8  lea     rcx, [rbp+57h+arg_10]
0x1800582ac  mov     r9d, 7
0x1800582b2  mov     qword ptr [rsp+0C0h+var_98], rcx
0x1800582b7  mov     r8d, ebx
0x1800582ba  mov     ecx, eax
0x1800582bc  mov     dword ptr [rsp+0C0h+var_A0], 0
0x1800582c4  mov     edx, edi
0x1800582c6  call    HrGetIconFromMediaType
0x1800582cb  mov     edi, eax
0x1800582cd  test    eax, eax
0x1800582cf  js      loc_1800583FD
0x1800582d5  mov     r8d, [r14+90h]; unsigned int
0x1800582dc  lea     rax, [rbp+57h+arg_0]
0x1800582e0  mov     rdx, [r14+88h]; unsigned __int8 *
0x1800582e7  lea     rcx, [r14+94h]; struct _GUID *
0x1800582ee  mov     [rsp+0C0h+var_98], 1; int
0x1800582f6  lea     r9, IID_INetConnection; struct _GUID *
0x1800582fd  mov     [rsp+0C0h+var_A0], rax; struct IUnknown *
0x180058302  call    ?HrGetConnectionFromPersistData@@YAJAEBU_GUID@@PEBEK0PEAPEAXH@Z; HrGetConnectionFromPersistData(_GUID const &,uchar const *,ulong,_GUID const &,void * *,int)
0x180058307  test    eax, eax
0x180058309  js      short loc_18005832E
0x18005830b  mov     rdx, [rbp+57h+arg_0.lpVtbl]
0x18005830f  lea     r8, [rbp+57h+hMem]
0x180058313  mov     ecx, 1
0x180058318  call    ?HrGetCaption@@YAJW4DIALOG_TYPE@@PEAUINetConnection@@PEAPEAG@Z; HrGetCaption(DIALOG_TYPE,INetConnection *,ushort * *)
0x18005831d  mov     rcx, [rbp+57h+arg_0.lpVtbl]; struct IUnknown *
0x180058321  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x180058326  mov     [rbp+57h+arg_0.lpVtbl], 0
0x18005832e  cmp     dword ptr [rbp+57h+var_90], 0
0x180058332  mov     rbx, [rbp+57h+arg_10]
0x180058336  jz      loc_180058401
0x18005833c  call    ?AddNotificationIfPossible@CConnectionList@@QEAAHXZ; CConnectionList::AddNotificationIfPossible(void)
0x180058341  xor     edx, edx; Val
0x180058343  lea     rcx, [rbp+57h+var_80]; void *
0x180058347  lea     r8d, [rdx+60h]; Size
0x18005834b  call    memset_0
0x180058350  mov     rax, cs:hInst
0x180058357  mov     ecx, 2000180h
0x18005835c  mov     [rbp+57h+var_80.hInstance], rax
0x180058360  test    rbx, rbx
0x180058363  mov     rax, [rbp+57h+hMem]
0x180058367  mov     [rbp+57h+var_80.pszCaption], rax
0x18005836b  mov     eax, dword ptr [rbp+57h+var_90]
0x18005836e  mov     [rbp+57h+var_80.nPages], eax
0x180058371  mov     rax, [rbp+57h+pv]
0x180058375  mov     qword ptr [rbp+57h+var_80.38h], rax
0x180058379  mov     eax, [r14+0BCh]
0x180058380  mov     dword ptr [rbp+57h+var_80.30h], eax
0x180058383  lea     rax, ?PshCallback@CNetStatisticsEngine@@SAHPEAUHWND__@@I_J@Z; CNetStatisticsEngine::PshCallback(HWND__ *,uint,__int64)
0x18005838a  mov     [rbp+57h+var_80.pfnCallback], rax
0x18005838e  lea     eax, [rcx+2]
0x180058391  cmovnz  ecx, eax
0x180058394  mov     [rbp+57h+var_80.dwSize], 60h ; '`'
0x18005839b  mov     [rbp+57h+var_80.dwFlags], ecx
0x18005839e  mov     [rbp+57h+var_80.hwndParent], 0
0x1800583a6  mov     qword ptr [rbp+57h+var_80.18h], rbx
0x1800583aa  test    rsi, rsi
0x1800583ad  jz      short loc_1800583B7
0x1800583af  mov     rcx, rsi; this
0x1800583b2  call    ??_GCWaitCursor@@QEAAPEAXI@Z; CWaitCursor::`scalar deleting destructor'(uint)
0x1800583b7  lea     rcx, [rbp+57h+var_80]; LPCPROPSHEETHEADERW
0x1800583bb  xor     esi, esi
0x1800583bd  call    PropertySheetW
0x1800583c2  test    rax, rax
0x1800583c5  jnz     short loc_1800583CE
0x1800583c7  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x1800583cc  mov     edi, eax
0x1800583ce  mov     rcx, [r14+48h]; this
0x1800583d2  test    rcx, rcx
0x1800583d5  jz      short loc_1800583F6
0x1800583d7  call    ?HrCleanupGenPage@CPspStatusMonitorGen@@QEAAJXZ; CPspStatusMonitorGen::HrCleanupGenPage(void)
0x1800583dc  mov     rax, [r14+48h]
0x1800583e0  lea     rdx, [rax+10h]
0x1800583e4  neg     rax
0x1800583e7  sbb     rcx, rcx
0x1800583ea  and     rcx, rdx; struct IUnknown *
0x1800583ed  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x1800583f2  mov     [r14+48h], rsi
0x1800583f6  call    ?RemoveNotificationIfPossible@CConnectionList@@QEAAHXZ; CConnectionList::RemoveNotificationIfPossible(void)
0x1800583fb  jmp     short loc_180058401
0x1800583fd  mov     rbx, [rbp+57h+arg_10]
0x180058401  mov     rcx, [rbp+57h+hMem]; hMem
0x180058405  call    cs:__imp_LocalFree
0x18005840b  test    rbx, rbx
0x18005840e  jz      short loc_180058419
0x180058410  mov     rcx, rbx; hIcon
0x180058413  call    cs:__imp_DestroyIcon
0x180058419  test    rsi, rsi
0x18005841c  jz      short loc_180058426
0x18005841e  mov     rcx, rsi; this
0x180058421  call    ??_GCWaitCursor@@QEAAPEAXI@Z; CWaitCursor::`scalar deleting destructor'(uint)
0x180058426  mov     rcx, [rbp+57h+pv]; pv
0x18005842a  call    cs:__imp_CoTaskMemFree
0x180058430  mov     eax, edi
0x180058432  add     rsp, 0A0h
0x180058439  pop     r14
0x18005843b  pop     rdi
0x18005843c  pop     rsi
0x18005843d  pop     rbx
0x18005843e  pop     rbp
0x18005843f  retn
```
