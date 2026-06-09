# UnifiedFrameAware_AcquireModalDialogLockAndParent

- ea: `0x1802b5a50`
- end: `0x1802b6122`
- name: `UnifiedFrameAware_AcquireModalDialogLockAndParent`
- size: `1746`
- prototype: `__int64 __fastcall(HWND hwnd)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180265e20`

## callees

- `0x1800cd150`
- `0x1800cd2a4`
- `0x1800cd638`
- `0x1800d42c4`
- `0x1802b4ffc`
- `0x1802b5050`
- `0x1802b5770`
- `0x1802b58a8`
- `0x1802b5a50`
- `0x180421f4c`
- `0x1805261dc`
- `0x180594010`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x1802b6023`
- `KERNEL32!GetCurrentProcessId` at `0x1802b6023`
- `KERNEL32!GetCurrentThreadId` at `0x1802b5ad1`
- `KERNEL32!GetCurrentThreadId` at `0x1802b5ad1`
- `USER32!IsWindow` at `0x1802b6013`
- `USER32!IsWindow` at `0x1802b6013`
- `USER32!DestroyWindow` at `0x1802b5fba`
- `USER32!DestroyWindow` at `0x1802b5fba`
- `USER32!GetPropW` at `0x1802b5beb`
- `USER32!GetPropW` at `0x1802b5beb`
- `USER32!SetPropW` at `0x1802b5c0b`
- `USER32!SetPropW` at `0x1802b5f78`
- `USER32!SetPropW` at `0x1802b5f91`
- `USER32!SetPropW` at `0x1802b5c0b`
- `USER32!SetPropW` at `0x1802b5f78`
- `USER32!SetPropW` at `0x1802b5f91`
- `USER32!GetWindowThreadProcessId` at `0x1802b5d5b`
- `USER32!GetWindowThreadProcessId` at `0x1802b603b`
- `USER32!GetWindowThreadProcessId` at `0x1802b5d5b`
- `USER32!GetWindowThreadProcessId` at `0x1802b603b`
- `USER32!EnableWindow` at `0x1802b5ef1`
- `USER32!EnableWindow` at `0x1802b5f52`
- `USER32!EnableWindow` at `0x1802b5ef1`
- `USER32!EnableWindow` at `0x1802b5f52`
- `USER32!GetAncestor` at `0x1802b5ed8`
- `USER32!GetAncestor` at `0x1802b5ed8`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1802b5de4`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1802b6067`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1802b5de4`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1802b6067`
- `iertutil!__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z` at `0x1802b5c86`
- `iertutil!__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z` at `0x1802b5d7d`
- `iertutil!__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z` at `0x1802b5c86`
- `iertutil!__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z` at `0x1802b5d7d`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeEx` at `0x1802b5aa4`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeEx` at `0x1802b5aa4`
- `api-ms-win-downlevel-ole32-l1-1-0!CoUninitialize` at `0x1802b5fda`
- `api-ms-win-downlevel-ole32-l1-1-0!CoUninitialize` at `0x1802b5fda`

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
0x1802b5a50  mov     rax, rsp
0x1802b5a53  mov     [rax+8], rbx
0x1802b5a57  mov     [rax+20h], r9
0x1802b5a5b  mov     [rax+18h], r8
0x1802b5a5f  mov     [rax+10h], rdx
0x1802b5a63  push    rbp
0x1802b5a64  push    rsi
0x1802b5a65  push    rdi
0x1802b5a66  push    r12
0x1802b5a68  push    r13
0x1802b5a6a  push    r14
0x1802b5a6c  push    r15
0x1802b5a6e  lea     rbp, [rax-5Fh]
0x1802b5a72  sub     rsp, 0A0h
0x1802b5a79  mov     [rbp+57h+var_A0], 0
0x1802b5a7d  mov     rsi, r9
0x1802b5a80  mov     r15, r8
0x1802b5a83  mov     rdi, rcx
0x1802b5a86  mov     ebx, 80070057h
0x1802b5a8b  test    r8, r8
0x1802b5a8e  jz      loc_1802B5FE6
0x1802b5a94  test    r9, r9
0x1802b5a97  jz      loc_1802B5FE6
0x1802b5a9d  mov     edx, 2; dwCoInit
0x1802b5aa2  xor     ecx, ecx; pvReserved
0x1802b5aa4  call    cs:__imp_CoInitializeEx
0x1802b5aab  nop     dword ptr [rax+rax+00h]
0x1802b5ab0  mov     r14d, eax
0x1802b5ab3  mov     eax, 80010106h
0x1802b5ab8  test    r14d, r14d
0x1802b5abb  jns     short loc_1802B5AC9
0x1802b5abd  mov     ebx, r14d
0x1802b5ac0  cmp     r14d, eax
0x1802b5ac3  jnz     loc_1802B5FD5
0x1802b5ac9  cmp     r14d, eax
0x1802b5acc  setnz   al
0x1802b5acf  mov     [rsi], al
0x1802b5ad1  call    cs:__imp_GetCurrentThreadId
0x1802b5ad8  nop     dword ptr [rax+rax+00h]
0x1802b5add  lea     r8, [rbp+57h+var_88]; int *
0x1802b5ae1  mov     [rbp+57h+var_78], 0
0x1802b5ae8  mov     ecx, eax; unsigned int
0x1802b5aea  mov     [rbp+57h+var_88], 0FFFFFFFFh
0x1802b5af1  lea     rdx, [rbp+57h+var_78]; unsigned int *
0x1802b5af5  mov     r13d, eax
0x1802b5af8  call    ?FindTabThreadFromAssociatedThread@@YAJKPEAKPEAJ@Z; FindTabThreadFromAssociatedThread(ulong,ulong *,long *)
0x1802b5afd  lea     rdx, [rbp+57h+var_A0]
0x1802b5b01  mov     rcx, rdi; hwnd
0x1802b5b04  mov     r12d, eax
0x1802b5b07  call    ReparentRequired
0x1802b5b0c  mov     ebx, eax
0x1802b5b0e  test    eax, eax
0x1802b5b10  js      loc_1802B5FD5
0x1802b5b16  cmp     [rbp+57h+var_A0], 0
0x1802b5b1a  jz      loc_1802B6004
0x1802b5b20  xor     r15d, r15d
0x1802b5b23  lea     rdx, [rbp+57h+var_A0]; bool *
0x1802b5b27  xor     r8d, r8d; HWND *
0x1802b5b2a  mov     [rbp+57h+var_A0], r15b
0x1802b5b2e  mov     rcx, rdi; HWND
0x1802b5b31  call    ?IsBrowserTabOrBrowserTabDescendant@@YAJPEAUHWND__@@PEA_NPEAPEAU1@@Z; IsBrowserTabOrBrowserTabDescendant(HWND__ *,bool *,HWND__ * *)
0x1802b5b36  mov     ebx, eax
0x1802b5b38  test    eax, eax
0x1802b5b3a  js      loc_1802B5FD5
0x1802b5b40  cmp     [rbp+57h+var_A0], r15b
0x1802b5b44  jnz     short loc_1802B5BA7
0x1802b5b46  lea     rdx, [rbp+57h+hWndParent]
0x1802b5b4a  mov     [rbp+57h+hWndParent], r15
0x1802b5b4e  mov     rcx, rdi; hWndParent
0x1802b5b51  call    _IsFrameOrFrameDescendant
0x1802b5b56  test    eax, eax
0x1802b5b58  js      loc_1802B5FCC
0x1802b5b5e  mov     rcx, [rbp+57h+hWndParent]; hWndParent
0x1802b5b62  test    rcx, rcx
0x1802b5b65  jz      loc_1802B5FCC
0x1802b5b6b  lea     r8, [rbp+57h+hwnd]
0x1802b5b6f  mov     [rbp+57h+hwnd], r15
0x1802b5b73  lea     rdx, aFrameTab; "Frame Tab"
0x1802b5b7a  call    _FindActiveChildByClass
0x1802b5b7f  test    eax, eax
0x1802b5b81  js      loc_1802B5FCC
0x1802b5b87  mov     rcx, [rbp+57h+hwnd]; hWndParent
0x1802b5b8b  lea     r8, [rbp+57h+hwnd]
0x1802b5b8f  lea     rdx, aTabwindowclass; "TabWindowClass"
0x1802b5b96  call    _FindActiveChildByClass
0x1802b5b9b  test    eax, eax
0x1802b5b9d  js      loc_1802B5FCC
0x1802b5ba3  mov     rdi, [rbp+57h+hwnd]
0x1802b5ba7  test    rdi, rdi
0x1802b5baa  jz      loc_1802B5FCC
0x1802b5bb0  mov     ecx, cs:_tls_index
0x1802b5bb6  mov     rax, gs:58h
0x1802b5bbf  mov     ebx, 10h
0x1802b5bc4  mov     rax, [rax+rcx*8]
0x1802b5bc8  mov     rbx, [rbx+rax]
0x1802b5bcc  test    rbx, rbx
0x1802b5bcf  jz      short loc_1802B5C2C
0x1802b5bd1  mov     rbx, [rbx+0A0h]
0x1802b5bd8  mov     [rbp+57h+hwnd], rbx
0x1802b5bdc  test    rbx, rbx
0x1802b5bdf  jz      short loc_1802B5C30
0x1802b5be1  lea     rdx, aFakemodalrefco; "FakeModalRefCount"
0x1802b5be8  mov     rcx, rbx; hWnd
0x1802b5beb  call    cs:__imp_GetPropW
0x1802b5bf2  nop     dword ptr [rax+rax+00h]
0x1802b5bf7  mov     r15d, 1
0x1802b5bfd  lea     rdx, aFakemodalrefco; "FakeModalRefCount"
0x1802b5c04  mov     rcx, rbx; hWnd
0x1802b5c07  lea     r8, [r15+rax]; hData
0x1802b5c0b  call    cs:__imp_SetPropW
0x1802b5c12  nop     dword ptr [rax+rax+00h]
0x1802b5c17  mov     rax, [rbp+57h+arg_8]
0x1802b5c1b  mov     [rax], r15
0x1802b5c1e  mov     rax, [rbp+57h+dwProcessId]
0x1802b5c22  mov     [rax], rbx
0x1802b5c25  xor     ebx, ebx
0x1802b5c27  jmp     loc_1802B5FD1
0x1802b5c2c  mov     [rbp+57h+hwnd], r15
0x1802b5c30  lea     rdx, [rbp+57h+hwnd]
0x1802b5c34  mov     rcx, rdi; hwnd
0x1802b5c37  call    _CreateModalDialogParentWindow
0x1802b5c3c  mov     ebx, eax
0x1802b5c3e  test    eax, eax
0x1802b5c40  js      loc_1802B5FD5
0x1802b5c46  mov     rsi, [rbp+57h+hwnd]
0x1802b5c4a  mov     r15d, 1
0x1802b5c50  cmp     r14d, 80010106h
0x1802b5c57  jz      loc_1802B5E9F
0x1802b5c5d  test    r12d, r12d
0x1802b5c60  js      loc_1802B5D33
0x1802b5c66  mov     ecx, [rbp+57h+var_78]
0x1802b5c69  cmp     r13d, ecx
0x1802b5c6c  jz      loc_1802B5D33
0x1802b5c72  lea     rdx, [rbp+57h+var_80]
0x1802b5c76  mov     [rbp+57h+hWndParent], 0
0x1802b5c7e  mov     [rbp+57h+var_80], 0
0x1802b5c86  call    cs:__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z; CoCreateUserBrokerForThread(ulong,IEUserBroker * *)
0x1802b5c8d  nop     dword ptr [rax+rax+00h]
0x1802b5c92  mov     ebx, eax
0x1802b5c94  test    eax, eax
0x1802b5c96  js      loc_1802B5FB7
0x1802b5c9c  mov     rcx, [rbp+57h+var_80]
0x1802b5ca0  lea     r9, [rbp+57h+hwnd]
0x1802b5ca4  mov     [rbp+57h+hwnd], 0
0x1802b5cac  lea     r8, IID_IUnknown
0x1802b5cb3  lea     rdx, CLSID_CShdocvwBroker
0x1802b5cba  mov     rax, [rcx]
0x1802b5cbd  mov     rax, [rax+30h]
0x1802b5cc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b5cc6  mov     ebx, eax
0x1802b5cc8  test    eax, eax
0x1802b5cca  js      short loc_1802B5CF8
0x1802b5ccc  mov     rcx, [rbp+57h+hwnd]
0x1802b5cd0  lea     r8, [rbp+57h+hWndParent]
0x1802b5cd4  lea     rdx, IID_IShdocvwBroker
0x1802b5cdb  mov     rax, [rcx]
0x1802b5cde  mov     rax, [rax]
0x1802b5ce1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b5ce6  mov     rcx, [rbp+57h+hwnd]
0x1802b5cea  mov     ebx, eax
0x1802b5cec  mov     rax, [rcx]
0x1802b5cef  mov     rax, [rax+10h]
0x1802b5cf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b5cf8  mov     rcx, [rbp+57h+var_80]
0x1802b5cfc  mov     rax, [rcx]
0x1802b5cff  mov     rax, [rax+10h]
0x1802b5d03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b5d08  test    ebx, ebx
0x1802b5d0a  js      loc_1802B5FB7
0x1802b5d10  mov     rcx, [rbp+57h+hWndParent]
0x1802b5d14  mov     rdx, rsi
0x1802b5d17  mov     r8d, [rbp+57h+var_88]
0x1802b5d1b  mov     rax, [rcx]
0x1802b5d1e  mov     rax, [rax+308h]
0x1802b5d25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b5d2a  mov     rcx, [rbp+57h+hWndParent]
0x1802b5d2e  jmp     loc_1802B5E8C
0x1802b5d33  lea     rdx, [rbp+57h+hWndParent]
0x1802b5d37  mov     [rbp+57h+hWndParent], 0
0x1802b5d3f  mov     rcx, rdi; hWndParent
0x1802b5d42  call    _IsFrameOrFrameDescendant
0x1802b5d47  test    eax, eax
0x1802b5d49  js      loc_1802B5DD0
0x1802b5d4f  cmp     [rbp+57h+hWndParent], 0
0x1802b5d54  jz      short loc_1802B5DD0
0x1802b5d56  xor     edx, edx; lpdwProcessId
0x1802b5d58  mov     rcx, rdi; hWnd
0x1802b5d5b  call    cs:__imp_GetWindowThreadProcessId
0x1802b5d62  nop     dword ptr [rax+rax+00h]
0x1802b5d67  lea     rdx, [rbp+57h+var_80]
0x1802b5d6b  mov     [rbp+57h+hwnd], 0
0x1802b5d73  mov     ecx, eax
0x1802b5d75  mov     [rbp+57h+var_80], 0
0x1802b5d7d  call    cs:__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z; CoCreateUserBrokerForThread(ulong,IEUserBroker * *)
0x1802b5d84  nop     dword ptr [rax+rax+00h]
0x1802b5d89  mov     ebx, eax
0x1802b5d8b  test    eax, eax
0x1802b5d8d  js      loc_1802B5FB7
0x1802b5d93  mov     rcx, [rbp+57h+var_80]
0x1802b5d97  lea     r9, [rbp+57h+hWndParent]
0x1802b5d9b  mov     [rbp+57h+hWndParent], 0
0x1802b5da3  lea     r8, IID_IUnknown
0x1802b5daa  lea     rdx, CLSID_CShdocvwBroker
0x1802b5db1  mov     rax, [rcx]
0x1802b5db4  mov     rax, [rax+30h]
0x1802b5db8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b5dbd  mov     ebx, eax
0x1802b5dbf  test    eax, eax
0x1802b5dc1  js      loc_1802B5E56
0x1802b5dc7  lea     rdx, IID_IShdocvwBroker
0x1802b5dce  jmp     short loc_1802B5E31
0x1802b5dd0  lea     rcx, [rbp+57h+var_80]
0x1802b5dd4  mov     [rbp+57h+hwnd], 0
0x1802b5ddc  mov     [rbp+57h+var_80], 0
0x1802b5de4  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x1802b5deb  nop     dword ptr [rax+rax+00h]
0x1802b5df0  mov     ebx, eax
0x1802b5df2  test    eax, eax
0x1802b5df4  js      loc_1802B5FB7
0x1802b5dfa  mov     rcx, [rbp+57h+var_80]
0x1802b5dfe  lea     r9, [rbp+57h+hWndParent]
0x1802b5e02  mov     [rbp+57h+hWndParent], 0
0x1802b5e0a  lea     r8, IID_IUnknown
0x1802b5e11  lea     rdx, CLSID_CShdocvwBroker
0x1802b5e18  mov     rax, [rcx]
0x1802b5e1b  mov     rax, [rax+30h]
0x1802b5e1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b5e24  mov     ebx, eax
0x1802b5e26  test    eax, eax
0x1802b5e28  js      short loc_1802B5E56
0x1802b5e2a  lea     rdx, _GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42
0x1802b5e31  mov     rcx, [rbp+57h+hWndParent]
0x1802b5e35  lea     r8, [rbp+57h+hwnd]
0x1802b5e39  mov     rax, [rcx]
0x1802b5e3c  mov     rax, [rax]
0x1802b5e3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b5e44  mov     rcx, [rbp+57h+hWndParent]
0x1802b5e48  mov     ebx, eax
0x1802b5e4a  mov     rax, [rcx]
0x1802b5e4d  mov     rax, [rax+10h]
0x1802b5e51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b5e56  mov     rcx, [rbp+57h+var_80]
0x1802b5e5a  mov     rax, [rcx]
0x1802b5e5d  mov     rax, [rax+10h]
0x1802b5e61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b5e66  test    ebx, ebx
0x1802b5e68  js      loc_1802B5FB7
0x1802b5e6e  mov     rcx, [rbp+57h+hwnd]
0x1802b5e72  mov     rdx, rsi
0x1802b5e75  mov     r8d, [rbp+57h+var_88]
0x1802b5e79  mov     rax, [rcx]
0x1802b5e7c  mov     rax, [rax+308h]
0x1802b5e83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b5e88  mov     rcx, [rbp+57h+hwnd]
0x1802b5e8c  mov     ebx, eax
0x1802b5e8e  mov     rax, [rcx]
0x1802b5e91  mov     rax, [rax+10h]
0x1802b5e95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b5e9a  jmp     loc_1802B5F67
0x1802b5e9f  xorps   xmm0, xmm0
0x1802b5ea2  mov     [rbp+57h+var_50], 0
0x1802b5ea9  xorps   xmm1, xmm1
0x1802b5eac  mov     [rbp+57h+var_48], 0
0x1802b5eb4  lea     rcx, [rbp+57h+var_70]
0x1802b5eb8  movdqu  [rbp+57h+var_70], xmm0
0x1802b5ebd  movdqu  [rbp+57h+var_60], xmm1
0x1802b5ec2  call    ?Init@?$CBrokerObjectCall@UAsyncIShdocvwBroker@@$1?CLSID_CShdocvwBroker@@3U_GUID@@B$1?IID_AsyncIShdocvwBroker@@3U3@B@@QEAAJXZ; CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBroker,&_GUID const IID_AsyncIShdocvwBroker>::Init(void)
0x1802b5ec7  xor     r14d, r14d
0x1802b5eca  mov     ebx, eax
0x1802b5ecc  test    rsi, rsi
0x1802b5ecf  jz      short loc_1802B5EFD
0x1802b5ed1  lea     edx, [r14+2]; gaFlags
0x1802b5ed5  mov     rcx, rsi; hwnd
0x1802b5ed8  call    cs:__imp_GetAncestor
0x1802b5edf  nop     dword ptr [rax+rax+00h]
0x1802b5ee4  mov     r14, rax
0x1802b5ee7  test    rax, rax
0x1802b5eea  jz      short loc_1802B5EFD
0x1802b5eec  xor     edx, edx; bEnable
0x1802b5eee  mov     rcx, rax; hWnd
0x1802b5ef1  call    cs:__imp_EnableWindow
0x1802b5ef8  nop     dword ptr [rax+rax+00h]
0x1802b5efd  test    ebx, ebx
0x1802b5eff  js      short loc_1802B5F47
0x1802b5f01  mov     rcx, qword ptr [rbp+57h+var_60+8]
0x1802b5f05  mov     r8d, [rbp+57h+var_88]
0x1802b5f09  mov     rdx, [rcx]
0x1802b5f0c  mov     rax, [rdx+5F8h]
0x1802b5f13  mov     rdx, rsi
0x1802b5f16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b5f1b  mov     ebx, eax
0x1802b5f1d  test    eax, eax
0x1802b5f1f  js      short loc_1802B5F47
0x1802b5f21  xor     edx, edx
0x1802b5f23  lea     rcx, [rbp+57h+var_70]
0x1802b5f27  call    ?WaitForCallComplete@?$CBrokerObjectCall@UAsyncIShdocvwBroker@@$1?CLSID_CShdocvwBroker@@3U_GUID@@B$1?IID_AsyncIShdocvwBroker@@3U3@B@@QEAAJPEAUHWND__@@I@Z; CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBroker,&_GUID const IID_AsyncIShdocvwBroker>::WaitForCallComplete(HWND__ *,uint)
0x1802b5f2c  mov     ebx, eax
0x1802b5f2e  test    eax, eax
0x1802b5f30  js      short loc_1802B5F47
0x1802b5f32  mov     rcx, qword ptr [rbp+57h+var_60+8]
  ... truncated ...
```
