# UnifiedFrameAware_AcquireModalDialogLockAndParent

- ea: `0x180292eb4`
- end: `0x18029350f`
- name: `UnifiedFrameAware_AcquireModalDialogLockAndParent`
- size: `1627`
- prototype: `__int64 __fastcall(HWND hwnd)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1802477c0`

## callees

- `0x1800c5d04`
- `0x1800c5df0`
- `0x1800c6168`
- `0x1800cc2e4`
- `0x1802925e4`
- `0x180292634`
- `0x180292c3c`
- `0x180292d58`
- `0x180292eb4`
- `0x1803ec600`
- `0x1804e7a7c`
- `0x180550010`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180293422`
- `KERNEL32!GetCurrentProcessId` at `0x180293422`
- `KERNEL32!GetCurrentThreadId` at `0x180292f2f`
- `KERNEL32!GetCurrentThreadId` at `0x180292f2f`
- `USER32!IsWindow` at `0x180293418`
- `USER32!IsWindow` at `0x180293418`
- `USER32!DestroyWindow` at `0x1802933cc`
- `USER32!DestroyWindow` at `0x1802933cc`
- `USER32!GetPropW` at `0x180293043`
- `USER32!GetPropW` at `0x180293043`
- `USER32!SetPropW` at `0x18029305d`
- `USER32!SetPropW` at `0x180293396`
- `USER32!SetPropW` at `0x1802933a9`
- `USER32!SetPropW` at `0x18029305d`
- `USER32!SetPropW` at `0x180293396`
- `USER32!SetPropW` at `0x1802933a9`
- `USER32!GetWindowThreadProcessId` at `0x18029319d`
- `USER32!GetWindowThreadProcessId` at `0x180293434`
- `USER32!GetWindowThreadProcessId` at `0x18029319d`
- `USER32!GetWindowThreadProcessId` at `0x180293434`
- `USER32!EnableWindow` at `0x18029331b`
- `USER32!EnableWindow` at `0x180293376`
- `USER32!EnableWindow` at `0x18029331b`
- `USER32!EnableWindow` at `0x180293376`
- `USER32!GetAncestor` at `0x180293308`
- `USER32!GetAncestor` at `0x180293308`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18029321a`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18029345a`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18029321a`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18029345a`
- `iertutil!__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z` at `0x1802930d2`
- `iertutil!__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z` at `0x1802931b9`
- `iertutil!__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z` at `0x1802930d2`
- `iertutil!__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z` at `0x1802931b9`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeEx` at `0x180292f08`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeEx` at `0x180292f08`
- `api-ms-win-downlevel-ole32-l1-1-0!CoUninitialize` at `0x1802933e6`
- `api-ms-win-downlevel-ole32-l1-1-0!CoUninitialize` at `0x1802933e6`

## pseudocode

```c
__int64 __fastcall UnifiedFrameAware_AcquireModalDialogLockAndParent(HWND hwnd, _QWORD *a2, HWND *a3, bool *a4)
{
  bool *v4; // rsi
  int ModalDialogParentWindow; // ebx
  HRESULT v8; // r14d
  DWORD CurrentThreadId; // eax
  DWORD v10; // r13d
  int TabThreadFromAssociatedThread; // r12d
  __int64 v12; // rbx
  HWND v13; // rbx
  char *PropW; // rax
  HWND v15; // rsi
  int v16; // eax
  HWND v17; // rcx
  DWORD WindowThreadProcessId; // eax
  GUID *v19; // rdx
  HWND v20; // r14
  HWND Ancestor; // rax
  DWORD CurrentProcessId; // eax
  DWORD v24; // ebx
  DWORD v25; // eax
  int v26; // ebx
  bool v27; // [rsp+38h] [rbp-49h] BYREF
  HWND hWndParent; // [rsp+40h] [rbp-41h] BYREF
  HWND hwnda; // [rsp+48h] [rbp-39h] BYREF
  int v30; // [rsp+50h] [rbp-31h] BYREF
  struct IEUserBroker *v31; // [rsp+58h] [rbp-29h] BYREF
  unsigned int v32; // [rsp+60h] [rbp-21h] BYREF
  __int128 v33; // [rsp+68h] [rbp-19h] BYREF
  __int128 v34; // [rsp+78h] [rbp-9h]
  int v35; // [rsp+88h] [rbp+7h]
  __int64 v36; // [rsp+90h] [rbp+Fh]
  HWND *dwProcessId; // [rsp+F8h] [rbp+77h] BYREF
  bool *v39; // [rsp+100h] [rbp+7Fh]

  v39 = a4;
  dwProcessId = a3;
  v27 = 0;
  v4 = a4;
  ModalDialogParentWindow = -2147024809;
  if ( !a3 || !a4 )
    return (unsigned int)ModalDialogParentWindow;
  v8 = CoInitializeEx(0, 2u);
  if ( v8 < 0 )
  {
    ModalDialogParentWindow = v8;
    if ( v8 != -2147417850 )
      goto LABEL_55;
  }
  *v4 = v8 != -2147417850;
  CurrentThreadId = GetCurrentThreadId();
  v32 = 0;
  v30 = -1;
  v10 = CurrentThreadId;
  TabThreadFromAssociatedThread = FindTabThreadFromAssociatedThread(CurrentThreadId, &v32, &v30);
  ModalDialogParentWindow = ReparentRequired(hwnd);
  if ( ModalDialogParentWindow < 0 )
    goto LABEL_55;
  if ( v27 )
  {
    v27 = 0;
    ModalDialogParentWindow = IsBrowserTabOrBrowserTabDescendant(hwnd, &v27, 0);
    if ( ModalDialogParentWindow < 0 )
      goto LABEL_55;
    if ( !v27 )
    {
      hWndParent = 0;
      if ( (int)IsFrameOrFrameDescendant(hwnd) < 0 )
        goto LABEL_53;
      if ( !hWndParent )
        goto LABEL_53;
      hwnda = 0;
      if ( (int)FindActiveChildByClass(hWndParent, L"Frame Tab") < 0
        || (int)FindActiveChildByClass(hwnda, L"TabWindowClass") < 0 )
      {
        goto LABEL_53;
      }
      hwnd = hwnda;
    }
    if ( hwnd )
    {
      v12 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 16LL);
      if ( v12 )
      {
        v13 = *(HWND *)(v12 + 160);
        hwnda = v13;
        if ( v13 )
        {
          PropW = (char *)GetPropW(v13, L"FakeModalRefCount");
          SetPropW(v13, L"FakeModalRefCount", PropW + 1);
          *a2 = 1;
          *dwProcessId = v13;
          ModalDialogParentWindow = 0;
          goto LABEL_54;
        }
      }
      else
      {
        hwnda = 0;
      }
      ModalDialogParentWindow = CreateModalDialogParentWindow(hwnd);
      if ( ModalDialogParentWindow >= 0 )
      {
        v15 = hwnda;
        if ( v8 == -2147417850 )
        {
          v35 = 0;
          v36 = 0;
          v33 = 0;
          v34 = 0;
          v20 = 0;
          ModalDialogParentWindow = CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBroker,&_GUID const IID_AsyncIShdocvwBroker>::Init(&v33);
          if ( v15 )
          {
            Ancestor = GetAncestor(v15, 2u);
            v20 = Ancestor;
            if ( Ancestor )
              EnableWindow(Ancestor, 0);
          }
          if ( ModalDialogParentWindow >= 0 )
          {
            ModalDialogParentWindow = (*(__int64 (__fastcall **)(_QWORD, HWND, _QWORD))(**((_QWORD **)&v34 + 1) + 1528LL))(
                                        *((_QWORD *)&v34 + 1),
                                        v15,
                                        (unsigned int)v30);
            if ( ModalDialogParentWindow >= 0 )
            {
              ModalDialogParentWindow = CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBroker,&_GUID const IID_AsyncIShdocvwBroker>::WaitForCallComplete(
                                          &v33,
                                          0);
              if ( ModalDialogParentWindow >= 0 )
                ModalDialogParentWindow = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)&v34 + 1) + 1536LL))(*((_QWORD *)&v34 + 1));
            }
          }
          if ( v20 )
            EnableWindow(v20, 1);
          CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBrokerNoFrameAffinity,&_GUID const IID_AsyncIShdocvwBroker>::~CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBrokerNoFrameAffinity,&_GUID const IID_AsyncIShdocvwBroker>(&v33);
LABEL_50:
          if ( ModalDialogParentWindow >= 0 )
          {
            SetPropW(v15, L"FakeModalRefCount", HANDLE_FLAG_INHERIT);
            SetPropW(v15, L"FakeModalEffectiveParent", hwnd);
            TLSSetFakeModalWindow(v15);
            ModalDialogParentWindow = 0;
            *a2 = 1;
            *dwProcessId = v15;
            return (unsigned int)ModalDialogParentWindow;
          }
          goto LABEL_52;
        }
        if ( TabThreadFromAssociatedThread >= 0 && v10 != v32 )
        {
          hWndParent = 0;
          v31 = 0;
          ModalDialogParentWindow = CoCreateUserBrokerForThread(v32, &v31);
          if ( ModalDialogParentWindow >= 0 )
          {
            hwnda = 0;
            ModalDialogParentWindow = (*(__int64 (__fastcall **)(struct IEUserBroker *, GUID *, GUID *, HWND *))(*(_QWORD *)v31 + 48LL))(
                                        v31,
                                        &CLSID_CShdocvwBroker,
                                        &IID_IUnknown,
                                        &hwnda);
            if ( ModalDialogParentWindow >= 0 )
            {
              ModalDialogParentWindow = (**(__int64 (__fastcall ***)(HWND, GUID *, HWND *))hwnda)(
                                          hwnda,
                                          &IID_IShdocvwBroker,
                                          &hWndParent);
              (*(void (__fastcall **)(HWND))(*(_QWORD *)hwnda + 16LL))(hwnda);
            }
            (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v31 + 16LL))(v31);
            if ( ModalDialogParentWindow >= 0 )
            {
              v16 = (*(__int64 (__fastcall **)(HWND, HWND, _QWORD))(*(_QWORD *)hWndParent + 776LL))(
                      hWndParent,
                      v15,
                      (unsigned int)v30);
              v17 = hWndParent;
LABEL_39:
              ModalDialogParentWindow = v16;
              (*(void (__fastcall **)(HWND))(*(_QWORD *)v17 + 16LL))(v17);
              goto LABEL_50;
            }
          }
          goto LABEL_52;
        }
        hWndParent = 0;
        if ( (int)IsFrameOrFrameDescendant(hwnd) >= 0 && hWndParent )
        {
          WindowThreadProcessId = GetWindowThreadProcessId(hwnd, 0);
          hwnda = 0;
          v31 = 0;
          ModalDialogParentWindow = CoCreateUserBrokerForThread(WindowThreadProcessId, &v31);
          if ( ModalDialogParentWindow < 0 )
            goto LABEL_52;
          hWndParent = 0;
          ModalDialogParentWindow = (*(__int64 (__fastcall **)(struct IEUserBroker *, GUID *, GUID *, HWND *))(*(_QWORD *)v31 + 48LL))(
                                      v31,
                                      &CLSID_CShdocvwBroker,
                                      &IID_IUnknown,
                                      &hWndParent);
          if ( ModalDialogParentWindow < 0 )
            goto LABEL_37;
          v19 = &IID_IShdocvwBroker;
        }
        else
        {
          hwnda = 0;
          v31 = 0;
          ModalDialogParentWindow = CoCreateUserBroker(&v31);
          if ( ModalDialogParentWindow < 0 )
            goto LABEL_52;
          hWndParent = 0;
          ModalDialogParentWindow = (*(__int64 (__fastcall **)(struct IEUserBroker *, GUID *, GUID *, HWND *))(*(_QWORD *)v31 + 48LL))(
                                      v31,
                                      &CLSID_CShdocvwBroker,
                                      &IID_IUnknown,
                                      &hWndParent);
          if ( ModalDialogParentWindow < 0 )
            goto LABEL_37;
          v19 = &GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42;
        }
        ModalDialogParentWindow = (**(__int64 (__fastcall ***)(HWND, GUID *, HWND *))hWndParent)(
                                    hWndParent,
                                    v19,
                                    &hwnda);
        (*(void (__fastcall **)(HWND))(*(_QWORD *)hWndParent + 16LL))(hWndParent);
LABEL_37:
        (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v31 + 16LL))(v31);
        if ( ModalDialogParentWindow >= 0 )
        {
          v16 = (*(__int64 (__fastcall **)(HWND, HWND, _QWORD))(*(_QWORD *)hwnda + 776LL))(
                  hwnda,
                  v15,
                  (unsigned int)v30);
          v17 = hwnda;
          goto LABEL_39;
        }
LABEL_52:
        DestroyWindow(v15);
        v4 = v39;
        goto LABEL_54;
      }
LABEL_55:
      if ( *v4 )
        CoUninitialize();
      return (unsigned int)ModalDialogParentWindow;
    }
LABEL_53:
    ModalDialogParentWindow = -2147467263;
LABEL_54:
    if ( ModalDialogParentWindow >= 0 )
      return (unsigned int)ModalDialogParentWindow;
    goto LABEL_55;
  }
  if ( TabThreadFromAssociatedThread < 0 )
  {
    if ( hwnd )
    {
      if ( IsWindow(hwnd) )
      {
        CurrentProcessId = GetCurrentProcessId();
        LODWORD(dwProcessId) = 0;
        v24 = CurrentProcessId;
        v25 = GetWindowThreadProcessId(hwnd, (LPDWORD)&dwProcessId);
        if ( v24 == (_DWORD)dwProcessId )
          FindTabThreadFromAssociatedThread(v25, &v32, &v30);
      }
    }
  }
  v31 = 0;
  hWndParent = 0;
  if ( (int)CoCreateUserBroker((struct IEUserBroker **)&hWndParent) >= 0 )
  {
    dwProcessId = 0;
    v26 = (*(__int64 (__fastcall **)(HWND, GUID *, GUID *, HWND **))(*(_QWORD *)hWndParent + 48LL))(
            hWndParent,
            &CLSID_CShdocvwBroker,
            &IID_IUnknown,
            &dwProcessId);
    if ( v26 >= 0 )
    {
      v26 = (*(__int64 (__fastcall **)(HWND *, GUID *, struct IEUserBroker **))*dwProcessId)(
              dwProcessId,
              &GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42,
              &v31);
      (*((void (__fastcall **)(HWND *))*dwProcessId + 2))(dwProcessId);
    }
    (*(void (__fastcall **)(HWND))(*(_QWORD *)hWndParent + 16LL))(hWndParent);
    if ( v26 >= 0 )
    {
      (*(void (__fastcall **)(struct IEUserBroker *, _QWORD))(*(_QWORD *)v31 + 928LL))(v31, (unsigned int)v30);
      (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v31 + 16LL))(v31);
    }
  }
  ModalDialogParentWindow = 0;
  *a3 = hwnd;
  *a2 = 2;
  return (unsigned int)ModalDialogParentWindow;
}

```

## disassembly

```asm
0x180292eb4  mov     rax, rsp
0x180292eb7  mov     [rax+8], rbx
0x180292ebb  mov     [rax+20h], r9
0x180292ebf  mov     [rax+18h], r8
0x180292ec3  mov     [rax+10h], rdx
0x180292ec7  push    rbp
0x180292ec8  push    rsi
0x180292ec9  push    rdi
0x180292eca  push    r12
0x180292ecc  push    r13
0x180292ece  push    r14
0x180292ed0  push    r15
0x180292ed2  lea     rbp, [rax-5Fh]
0x180292ed6  sub     rsp, 0A0h
0x180292edd  mov     [rbp+57h+var_A0], 0
0x180292ee1  mov     rsi, r9
0x180292ee4  mov     r15, r8
0x180292ee7  mov     rdi, rcx
0x180292eea  mov     ebx, 80070057h
0x180292eef  test    r8, r8
0x180292ef2  jz      loc_1802933EC
0x180292ef8  test    r9, r9
0x180292efb  jz      loc_1802933EC
0x180292f01  mov     edx, 2; dwCoInit
0x180292f06  xor     ecx, ecx; pvReserved
0x180292f08  call    cs:__imp_CoInitializeEx
0x180292f0e  mov     r14d, eax
0x180292f11  mov     eax, 80010106h
0x180292f16  test    r14d, r14d
0x180292f19  jns     short loc_180292F27
0x180292f1b  mov     ebx, r14d
0x180292f1e  cmp     r14d, eax
0x180292f21  jnz     loc_1802933E1
0x180292f27  cmp     r14d, eax
0x180292f2a  setnz   al
0x180292f2d  mov     [rsi], al
0x180292f2f  call    cs:__imp_GetCurrentThreadId
0x180292f35  lea     r8, [rbp+57h+var_88]; int *
0x180292f39  mov     [rbp+57h+var_78], 0
0x180292f40  mov     ecx, eax; unsigned int
0x180292f42  mov     [rbp+57h+var_88], 0FFFFFFFFh
0x180292f49  lea     rdx, [rbp+57h+var_78]; unsigned int *
0x180292f4d  mov     r13d, eax
0x180292f50  call    ?FindTabThreadFromAssociatedThread@@YAJKPEAKPEAJ@Z; FindTabThreadFromAssociatedThread(ulong,ulong *,long *)
0x180292f55  lea     rdx, [rbp+57h+var_A0]
0x180292f59  mov     rcx, rdi; hwnd
0x180292f5c  mov     r12d, eax
0x180292f5f  call    ReparentRequired
0x180292f64  mov     ebx, eax
0x180292f66  test    eax, eax
0x180292f68  js      loc_1802933E1
0x180292f6e  cmp     [rbp+57h+var_A0], 0
0x180292f72  jz      loc_180293409
0x180292f78  xor     r15d, r15d
0x180292f7b  lea     rdx, [rbp+57h+var_A0]; bool *
0x180292f7f  xor     r8d, r8d; HWND *
0x180292f82  mov     [rbp+57h+var_A0], r15b
0x180292f86  mov     rcx, rdi; HWND
0x180292f89  call    ?IsBrowserTabOrBrowserTabDescendant@@YAJPEAUHWND__@@PEA_NPEAPEAU1@@Z; IsBrowserTabOrBrowserTabDescendant(HWND__ *,bool *,HWND__ * *)
0x180292f8e  mov     ebx, eax
0x180292f90  test    eax, eax
0x180292f92  js      loc_1802933E1
0x180292f98  cmp     [rbp+57h+var_A0], r15b
0x180292f9c  jnz     short loc_180292FFF
0x180292f9e  lea     rdx, [rbp+57h+hWndParent]
0x180292fa2  mov     [rbp+57h+hWndParent], r15
0x180292fa6  mov     rcx, rdi; hWndParent
0x180292fa9  call    _IsFrameOrFrameDescendant
0x180292fae  test    eax, eax
0x180292fb0  js      loc_1802933D8
0x180292fb6  mov     rcx, [rbp+57h+hWndParent]; hWndParent
0x180292fba  test    rcx, rcx
0x180292fbd  jz      loc_1802933D8
0x180292fc3  lea     r8, [rbp+57h+hwnd]
0x180292fc7  mov     [rbp+57h+hwnd], r15
0x180292fcb  lea     rdx, aFrameTab; "Frame Tab"
0x180292fd2  call    _FindActiveChildByClass
0x180292fd7  test    eax, eax
0x180292fd9  js      loc_1802933D8
0x180292fdf  mov     rcx, [rbp+57h+hwnd]; hWndParent
0x180292fe3  lea     r8, [rbp+57h+hwnd]
0x180292fe7  lea     rdx, aTabwindowclass; "TabWindowClass"
0x180292fee  call    _FindActiveChildByClass
0x180292ff3  test    eax, eax
0x180292ff5  js      loc_1802933D8
0x180292ffb  mov     rdi, [rbp+57h+hwnd]
0x180292fff  test    rdi, rdi
0x180293002  jz      loc_1802933D8
0x180293008  mov     ecx, cs:_tls_index
0x18029300e  mov     rax, gs:58h
0x180293017  mov     ebx, 10h
0x18029301c  mov     rax, [rax+rcx*8]
0x180293020  mov     rbx, [rbx+rax]
0x180293024  test    rbx, rbx
0x180293027  jz      short loc_180293078
0x180293029  mov     rbx, [rbx+0A0h]
0x180293030  mov     [rbp+57h+hwnd], rbx
0x180293034  test    rbx, rbx
0x180293037  jz      short loc_18029307C
0x180293039  lea     rdx, aFakemodalrefco; "FakeModalRefCount"
0x180293040  mov     rcx, rbx; hWnd
0x180293043  call    cs:__imp_GetPropW
0x180293049  mov     r15d, 1
0x18029304f  lea     rdx, aFakemodalrefco; "FakeModalRefCount"
0x180293056  mov     rcx, rbx; hWnd
0x180293059  lea     r8, [r15+rax]; hData
0x18029305d  call    cs:__imp_SetPropW
0x180293063  mov     rax, [rbp+57h+arg_8]
0x180293067  mov     [rax], r15
0x18029306a  mov     rax, [rbp+57h+dwProcessId]
0x18029306e  mov     [rax], rbx
0x180293071  xor     ebx, ebx
0x180293073  jmp     loc_1802933DD
0x180293078  mov     [rbp+57h+hwnd], r15
0x18029307c  lea     rdx, [rbp+57h+hwnd]
0x180293080  mov     rcx, rdi; hwnd
0x180293083  call    _CreateModalDialogParentWindow
0x180293088  mov     ebx, eax
0x18029308a  test    eax, eax
0x18029308c  js      loc_1802933E1
0x180293092  mov     rsi, [rbp+57h+hwnd]
0x180293096  mov     r15d, 1
0x18029309c  cmp     r14d, 80010106h
0x1802930a3  jz      loc_1802932CF
0x1802930a9  test    r12d, r12d
0x1802930ac  js      loc_180293179
0x1802930b2  mov     ecx, [rbp+57h+var_78]
0x1802930b5  cmp     r13d, ecx
0x1802930b8  jz      loc_180293179
0x1802930be  lea     rdx, [rbp+57h+var_80]
0x1802930c2  mov     [rbp+57h+hWndParent], 0
0x1802930ca  mov     [rbp+57h+var_80], 0
0x1802930d2  call    cs:__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z; CoCreateUserBrokerForThread(ulong,IEUserBroker * *)
0x1802930d8  mov     ebx, eax
0x1802930da  test    eax, eax
0x1802930dc  js      loc_1802933C9
0x1802930e2  mov     rcx, [rbp+57h+var_80]
0x1802930e6  lea     r9, [rbp+57h+hwnd]
0x1802930ea  mov     [rbp+57h+hwnd], 0
0x1802930f2  lea     r8, IID_IUnknown
0x1802930f9  lea     rdx, CLSID_CShdocvwBroker
0x180293100  mov     rax, [rcx]
0x180293103  mov     rax, [rax+30h]
0x180293107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029310c  mov     ebx, eax
0x18029310e  test    eax, eax
0x180293110  js      short loc_18029313E
0x180293112  mov     rcx, [rbp+57h+hwnd]
0x180293116  lea     r8, [rbp+57h+hWndParent]
0x18029311a  lea     rdx, IID_IShdocvwBroker
0x180293121  mov     rax, [rcx]
0x180293124  mov     rax, [rax]
0x180293127  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029312c  mov     rcx, [rbp+57h+hwnd]
0x180293130  mov     ebx, eax
0x180293132  mov     rax, [rcx]
0x180293135  mov     rax, [rax+10h]
0x180293139  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029313e  mov     rcx, [rbp+57h+var_80]
0x180293142  mov     rax, [rcx]
0x180293145  mov     rax, [rax+10h]
0x180293149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029314e  test    ebx, ebx
0x180293150  js      loc_1802933C9
0x180293156  mov     rcx, [rbp+57h+hWndParent]
0x18029315a  mov     rdx, rsi
0x18029315d  mov     r8d, [rbp+57h+var_88]
0x180293161  mov     rax, [rcx]
0x180293164  mov     rax, [rax+308h]
0x18029316b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180293170  mov     rcx, [rbp+57h+hWndParent]
0x180293174  jmp     loc_1802932BC
0x180293179  lea     rdx, [rbp+57h+hWndParent]
0x18029317d  mov     [rbp+57h+hWndParent], 0
0x180293185  mov     rcx, rdi; hWndParent
0x180293188  call    _IsFrameOrFrameDescendant
0x18029318d  test    eax, eax
0x18029318f  js      short loc_180293206
0x180293191  cmp     [rbp+57h+hWndParent], 0
0x180293196  jz      short loc_180293206
0x180293198  xor     edx, edx; lpdwProcessId
0x18029319a  mov     rcx, rdi; hWnd
0x18029319d  call    cs:__imp_GetWindowThreadProcessId
0x1802931a3  lea     rdx, [rbp+57h+var_80]
0x1802931a7  mov     [rbp+57h+hwnd], 0
0x1802931af  mov     ecx, eax
0x1802931b1  mov     [rbp+57h+var_80], 0
0x1802931b9  call    cs:__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z; CoCreateUserBrokerForThread(ulong,IEUserBroker * *)
0x1802931bf  mov     ebx, eax
0x1802931c1  test    eax, eax
0x1802931c3  js      loc_1802933C9
0x1802931c9  mov     rcx, [rbp+57h+var_80]
0x1802931cd  lea     r9, [rbp+57h+hWndParent]
0x1802931d1  mov     [rbp+57h+hWndParent], 0
0x1802931d9  lea     r8, IID_IUnknown
0x1802931e0  lea     rdx, CLSID_CShdocvwBroker
0x1802931e7  mov     rax, [rcx]
0x1802931ea  mov     rax, [rax+30h]
0x1802931ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802931f3  mov     ebx, eax
0x1802931f5  test    eax, eax
0x1802931f7  js      loc_180293286
0x1802931fd  lea     rdx, IID_IShdocvwBroker
0x180293204  jmp     short loc_180293261
0x180293206  lea     rcx, [rbp+57h+var_80]
0x18029320a  mov     [rbp+57h+hwnd], 0
0x180293212  mov     [rbp+57h+var_80], 0
0x18029321a  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x180293220  mov     ebx, eax
0x180293222  test    eax, eax
0x180293224  js      loc_1802933C9
0x18029322a  mov     rcx, [rbp+57h+var_80]
0x18029322e  lea     r9, [rbp+57h+hWndParent]
0x180293232  mov     [rbp+57h+hWndParent], 0
0x18029323a  lea     r8, IID_IUnknown
0x180293241  lea     rdx, CLSID_CShdocvwBroker
0x180293248  mov     rax, [rcx]
0x18029324b  mov     rax, [rax+30h]
0x18029324f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180293254  mov     ebx, eax
0x180293256  test    eax, eax
0x180293258  js      short loc_180293286
0x18029325a  lea     rdx, _GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42
0x180293261  mov     rcx, [rbp+57h+hWndParent]
0x180293265  lea     r8, [rbp+57h+hwnd]
0x180293269  mov     rax, [rcx]
0x18029326c  mov     rax, [rax]
0x18029326f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180293274  mov     rcx, [rbp+57h+hWndParent]
0x180293278  mov     ebx, eax
0x18029327a  mov     rax, [rcx]
0x18029327d  mov     rax, [rax+10h]
0x180293281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180293286  mov     rcx, [rbp+57h+var_80]
0x18029328a  mov     rax, [rcx]
0x18029328d  mov     rax, [rax+10h]
0x180293291  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180293296  test    ebx, ebx
0x180293298  js      loc_1802933C9
0x18029329e  mov     rcx, [rbp+57h+hwnd]
0x1802932a2  mov     rdx, rsi
0x1802932a5  mov     r8d, [rbp+57h+var_88]
0x1802932a9  mov     rax, [rcx]
0x1802932ac  mov     rax, [rax+308h]
0x1802932b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802932b8  mov     rcx, [rbp+57h+hwnd]
0x1802932bc  mov     ebx, eax
0x1802932be  mov     rax, [rcx]
0x1802932c1  mov     rax, [rax+10h]
0x1802932c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802932ca  jmp     loc_180293385
0x1802932cf  xorps   xmm0, xmm0
0x1802932d2  mov     [rbp+57h+var_50], 0
0x1802932d9  xorps   xmm1, xmm1
0x1802932dc  mov     [rbp+57h+var_48], 0
0x1802932e4  lea     rcx, [rbp+57h+var_70]
0x1802932e8  movdqu  [rbp+57h+var_70], xmm0
0x1802932ed  movdqu  [rbp+57h+var_60], xmm1
0x1802932f2  call    ?Init@?$CBrokerObjectCall@UAsyncIShdocvwBroker@@$1?CLSID_CShdocvwBroker@@3U_GUID@@B$1?IID_AsyncIShdocvwBroker@@3U3@B@@QEAAJXZ; CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBroker,&_GUID const IID_AsyncIShdocvwBroker>::Init(void)
0x1802932f7  xor     r14d, r14d
0x1802932fa  mov     ebx, eax
0x1802932fc  test    rsi, rsi
0x1802932ff  jz      short loc_180293321
0x180293301  lea     edx, [r14+2]; gaFlags
0x180293305  mov     rcx, rsi; hwnd
0x180293308  call    cs:__imp_GetAncestor
0x18029330e  mov     r14, rax
0x180293311  test    rax, rax
0x180293314  jz      short loc_180293321
0x180293316  xor     edx, edx; bEnable
0x180293318  mov     rcx, rax; hWnd
0x18029331b  call    cs:__imp_EnableWindow
0x180293321  test    ebx, ebx
0x180293323  js      short loc_18029336B
0x180293325  mov     rcx, qword ptr [rbp+57h+var_60+8]
0x180293329  mov     r8d, [rbp+57h+var_88]
0x18029332d  mov     rdx, [rcx]
0x180293330  mov     rax, [rdx+5F8h]
0x180293337  mov     rdx, rsi
0x18029333a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029333f  mov     ebx, eax
0x180293341  test    eax, eax
0x180293343  js      short loc_18029336B
0x180293345  xor     edx, edx
0x180293347  lea     rcx, [rbp+57h+var_70]
0x18029334b  call    ?WaitForCallComplete@?$CBrokerObjectCall@UAsyncIShdocvwBroker@@$1?CLSID_CShdocvwBroker@@3U_GUID@@B$1?IID_AsyncIShdocvwBroker@@3U3@B@@QEAAJPEAUHWND__@@I@Z; CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBroker,&_GUID const IID_AsyncIShdocvwBroker>::WaitForCallComplete(HWND__ *,uint)
0x180293350  mov     ebx, eax
0x180293352  test    eax, eax
0x180293354  js      short loc_18029336B
0x180293356  mov     rcx, qword ptr [rbp+57h+var_60+8]
0x18029335a  mov     rax, [rcx]
0x18029335d  mov     rax, [rax+600h]
0x180293364  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180293369  mov     ebx, eax
0x18029336b  test    r14, r14
0x18029336e  jz      short loc_18029337C
0x180293370  mov     edx, r15d; bEnable
0x180293373  mov     rcx, r14; hWnd
0x180293376  call    cs:__imp_EnableWindow
0x18029337c  lea     rcx, [rbp+57h+var_70]
  ... truncated ...
```
