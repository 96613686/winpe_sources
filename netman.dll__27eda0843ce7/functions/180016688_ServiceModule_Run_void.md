# ServiceModule::Run(void)

- ea: `0x180016688`
- end: `0x180016953`
- name: `?Run@ServiceModule@@QEAAXXZ`
- size: `715`
- prototype: `void __fastcall(ServiceModule *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800169b4`

## callees

- `0x180001710`
- `0x18000538c`
- `0x180008168`
- `0x18000a8e0`
- `0x180012568`
- `0x180016688`
- `0x180016e1c`
- `0x1800171b8`
- `0x180019200`
- `0x18003060c`
- `0x180036010`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x1800167db`
- `KERNEL32!CreateEventW` at `0x1800167db`
- `KERNEL32!CloseHandle` at `0x1800168e0`
- `KERNEL32!CloseHandle` at `0x1800168e0`
- `KERNEL32!SetEvent` at `0x1800168d7`
- `KERNEL32!SetEvent` at `0x1800168d7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001692a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001692a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016714`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016849`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016714`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016849`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800166a9`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800166a9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ServiceModule::Run(ServiceModule *this)
{
  unsigned int v1; // eax
  int v2; // ebx
  HRESULT Instance; // ebx
  PVOID *v4; // rcx
  HRESULT Win32Error; // ebx
  HANDLE EventW; // rdi
  PVOID *v7; // rcx
  unsigned int v8; // eax
  struct IUnknown *ppv; // [rsp+40h] [rbp-38h] BYREF

  v1 = CoInitializeEx(0, 4u);
  v2 = v1;
  ppv = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_b4d1654223233927dad0a39c06a0afa5_Traceguids, v1);
  if ( v2 >= 0 )
  {
    Instance = CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, (LPVOID *)&ppv);
    if ( Instance >= 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_b4d1654223233927dad0a39c06a0afa5_Traceguids);
      Instance = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int64))ppv->lpVtbl[1].QueryInterface)(ppv, 5, 1);
    }
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        26,
        &WPP_b4d1654223233927dad0a39c06a0afa5_Traceguids,
        (unsigned int)Instance);
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( ppv )
    {
      ATL::AtlComPtrAssign(&ppv, 0);
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( Instance < 0 )
      goto LABEL_38;
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 )
      WPP_SF_(v4[2], 27, &WPP_b4d1654223233927dad0a39c06a0afa5_Traceguids);
    Win32Error = 0;
    EventW = CreateEventW(0, 0, 0, L"Local\\NetmanClassObjectRegistrationEvent");
    if ( !EventW )
      Win32Error = HrFromLastWin32Error();
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_46212a7d52213dfb329f7f718b95424c_Traceguids,
        (unsigned int)Win32Error);
      v7 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( Win32Error < 0 )
    {
LABEL_30:
      if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 8) != 0 )
        WPP_SF_d(v7[2], 28, &WPP_b4d1654223233927dad0a39c06a0afa5_Traceguids, (unsigned int)Win32Error);
      SetEvent(EventW);
      CloseHandle(EventW);
      if ( Win32Error >= 0 && (int)ServiceModule::ServiceStartup((ServiceModule *)v4) >= 0 )
      {
        v8 = NmRegisterStopCallback();
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_b4d1654223233927dad0a39c06a0afa5_Traceguids, v8);
        goto LABEL_39;
      }
LABEL_38:
      ServiceModule::SetServiceStatus((ServiceModule *)v4, 1u);
LABEL_39:
      CoUninitialize();
      goto LABEL_40;
    }
    Win32Error = CoCreateInstance(
                   &CLSID_ContextSwitcher,
                   0,
                   1u,
                   &GUID_000001da_0000_0000_c000_000000000046,
                   &g_pContextSwitcher);
    if ( Win32Error >= 0 )
    {
      Win32Error = (*(__int64 (__fastcall **)(LPVOID, __int64 (__fastcall *)(struct tagComCallData *), _QWORD, GUID *, int, _QWORD))(*(_QWORD *)g_pContextSwitcher + 24LL))(
                     g_pContextSwitcher,
                     EnterConnectCallback,
                     0,
                     &IID_IContextCallback,
                     5,
                     0);
      if ( Win32Error >= 0 )
      {
LABEL_29:
        v7 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_30;
      }
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)g_pContextSwitcher + 16LL))(g_pContextSwitcher);
    }
    g_pContextSwitcher = 0;
    goto LABEL_29;
  }
LABEL_40:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
}

```

## disassembly

```asm
0x180016688  push    rbx
0x18001668a  push    rdi
0x18001668b  push    r14
0x18001668d  push    r15
0x18001668f  sub     rsp, 58h
0x180016693  mov     rax, cs:__security_cookie
0x18001669a  xor     rax, rsp
0x18001669d  mov     [rsp+78h+var_30], rax
0x1800166a2  mov     edx, 4; dwCoInit
0x1800166a7  xor     ecx, ecx; pvReserved
0x1800166a9  call    cs:__imp_CoInitializeEx
0x1800166af  mov     ebx, eax
0x1800166b1  mov     [rsp+78h+var_38], 0
0x1800166ba  lea     r14, WPP_GLOBAL_Control
0x1800166c1  lea     r15, WPP_b4d1654223233927dad0a39c06a0afa5_Traceguids
0x1800166c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800166cf  cmp     rcx, r14
0x1800166d2  jz      short loc_1800166EE
0x1800166d4  test    byte ptr [rcx+1Ch], 8
0x1800166d8  jz      short loc_1800166EE
0x1800166da  mov     edx, 18h
0x1800166df  mov     r9d, eax
0x1800166e2  mov     r8, r15
0x1800166e5  mov     rcx, [rcx+10h]
0x1800166e9  call    WPP_SF_d
0x1800166ee  test    ebx, ebx
0x1800166f0  js      loc_180016930
0x1800166f6  lea     rax, [rsp+78h+var_38]
0x1800166fb  mov     [rsp+78h+ppv], rax; ppv
0x180016700  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x180016707  xor     edx, edx; pUnkOuter
0x180016709  lea     r8d, [rdx+1]; dwClsContext
0x18001670d  lea     rcx, CLSID_GlobalOptions; rclsid
0x180016714  call    cs:__imp_CoCreateInstance
0x18001671a  mov     ebx, eax
0x18001671c  test    eax, eax
0x18001671e  js      short loc_18001675F
0x180016720  mov     rcx, cs:WPP_GLOBAL_Control
0x180016727  cmp     rcx, r14
0x18001672a  jz      short loc_180016743
0x18001672c  test    byte ptr [rcx+1Ch], 8
0x180016730  jz      short loc_180016743
0x180016732  mov     edx, 19h
0x180016737  mov     r8, r15
0x18001673a  mov     rcx, [rcx+10h]
0x18001673e  call    WPP_SF_
0x180016743  mov     rcx, [rsp+78h+var_38]
0x180016748  mov     rax, [rcx]
0x18001674b  mov     edx, 5
0x180016750  lea     r8d, [rdx-4]
0x180016754  mov     rax, [rax+18h]
0x180016758  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001675d  mov     ebx, eax
0x18001675f  mov     rcx, cs:WPP_GLOBAL_Control
0x180016766  cmp     rcx, r14
0x180016769  jz      short loc_18001678C
0x18001676b  test    byte ptr [rcx+1Ch], 8
0x18001676f  jz      short loc_18001678C
0x180016771  mov     edx, 1Ah
0x180016776  mov     r9d, ebx
0x180016779  mov     r8, r15
0x18001677c  mov     rcx, [rcx+10h]
0x180016780  call    WPP_SF_d
0x180016785  mov     rcx, cs:WPP_GLOBAL_Control
0x18001678c  cmp     [rsp+78h+var_38], 0
0x180016792  jz      short loc_1800167A7
0x180016794  xor     edx, edx; struct IUnknown *
0x180016796  lea     rcx, [rsp+78h+var_38]; struct IUnknown **
0x18001679b  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800167a0  mov     rcx, cs:WPP_GLOBAL_Control; this
0x1800167a7  test    ebx, ebx
0x1800167a9  js      loc_180016920
0x1800167af  cmp     rcx, r14
0x1800167b2  jz      short loc_1800167CB
0x1800167b4  test    byte ptr [rcx+1Ch], 8
0x1800167b8  jz      short loc_1800167CB
0x1800167ba  mov     edx, 1Bh
0x1800167bf  mov     r8, r15
0x1800167c2  mov     rcx, [rcx+10h]
0x1800167c6  call    WPP_SF_
0x1800167cb  xor     ebx, ebx
0x1800167cd  lea     r9, Name; "Local\\NetmanClassObjectRegistrationEve"...
0x1800167d4  xor     r8d, r8d; bInitialState
0x1800167d7  xor     edx, edx; bManualReset
0x1800167d9  xor     ecx, ecx; lpEventAttributes
0x1800167db  call    cs:__imp_CreateEventW
0x1800167e1  mov     rdi, rax
0x1800167e4  test    rax, rax
0x1800167e7  jnz     short loc_1800167F0
0x1800167e9  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x1800167ee  mov     ebx, eax
0x1800167f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800167f7  cmp     rcx, r14
0x1800167fa  jz      short loc_180016821
0x1800167fc  test    byte ptr [rcx+1Ch], 8
0x180016800  jz      short loc_180016821
0x180016802  mov     edx, 0Ah
0x180016807  mov     r9d, ebx
0x18001680a  lea     r8, WPP_46212a7d52213dfb329f7f718b95424c_Traceguids
0x180016811  mov     rcx, [rcx+10h]
0x180016815  call    WPP_SF_d
0x18001681a  mov     rcx, cs:WPP_GLOBAL_Control
0x180016821  test    ebx, ebx
0x180016823  js      loc_1800168B5
0x180016829  lea     rax, ?g_pContextSwitcher@@3PEAUIContextCallback@@EA; IContextCallback * g_pContextSwitcher
0x180016830  mov     [rsp+78h+ppv], rax; ppv
0x180016835  lea     r9, _GUID_000001da_0000_0000_c000_000000000046; riid
0x18001683c  xor     edx, edx; pUnkOuter
0x18001683e  lea     r8d, [rdx+1]; dwClsContext
0x180016842  lea     rcx, CLSID_ContextSwitcher; rclsid
0x180016849  call    cs:__imp_CoCreateInstance
0x18001684f  mov     ebx, eax
0x180016851  test    eax, eax
0x180016853  js      short loc_1800168A3
0x180016855  mov     rcx, cs:?g_pContextSwitcher@@3PEAUIContextCallback@@EA; IContextCallback * g_pContextSwitcher
0x18001685c  mov     rax, [rcx]
0x18001685f  mov     [rsp+78h+var_50], 0
0x180016868  mov     dword ptr [rsp+78h+ppv], 5
0x180016870  lea     r9, IID_IContextCallback
0x180016877  xor     r8d, r8d
0x18001687a  lea     rdx, ?EnterConnectCallback@@YAJPEAUtagComCallData@@@Z; EnterConnectCallback(tagComCallData *)
0x180016881  mov     rax, [rax+18h]
0x180016885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001688a  mov     ebx, eax
0x18001688c  test    eax, eax
0x18001688e  jns     short loc_1800168AE
0x180016890  mov     rcx, cs:?g_pContextSwitcher@@3PEAUIContextCallback@@EA; IContextCallback * g_pContextSwitcher
0x180016897  mov     rax, [rcx]
0x18001689a  mov     rax, [rax+10h]
0x18001689e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168a3  mov     cs:?g_pContextSwitcher@@3PEAUIContextCallback@@EA, 0; IContextCallback * g_pContextSwitcher
0x1800168ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800168b5  cmp     rcx, r14
0x1800168b8  jz      short loc_1800168D4
0x1800168ba  test    byte ptr [rcx+1Ch], 8
0x1800168be  jz      short loc_1800168D4
0x1800168c0  mov     edx, 1Ch
0x1800168c5  mov     r9d, ebx
0x1800168c8  mov     r8, r15
0x1800168cb  mov     rcx, [rcx+10h]
0x1800168cf  call    WPP_SF_d
0x1800168d4  mov     rcx, rdi; hEvent
0x1800168d7  call    cs:__imp_SetEvent
0x1800168dd  mov     rcx, rdi; hObject
0x1800168e0  call    cs:__imp_CloseHandle
0x1800168e6  test    ebx, ebx
0x1800168e8  js      short loc_180016920
0x1800168ea  call    ?ServiceStartup@ServiceModule@@QEAAJXZ; ServiceModule::ServiceStartup(void)
0x1800168ef  test    eax, eax
0x1800168f1  js      short loc_180016920
0x1800168f3  call    ?NmRegisterStopCallback@@YAJXZ; NmRegisterStopCallback(void)
0x1800168f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800168ff  cmp     rcx, r14
0x180016902  jz      short loc_18001692A
0x180016904  test    byte ptr [rcx+1Ch], 8
0x180016908  jz      short loc_18001692A
0x18001690a  mov     edx, 1Dh
0x18001690f  mov     r9d, eax
0x180016912  mov     r8, r15
0x180016915  mov     rcx, [rcx+10h]
0x180016919  call    WPP_SF_d
0x18001691e  jmp     short loc_18001692A
0x180016920  mov     edx, 1; unsigned int
0x180016925  call    ?SetServiceStatus@ServiceModule@@QEAAXK@Z; ServiceModule::SetServiceStatus(ulong)
0x18001692a  call    cs:__imp_CoUninitialize
0x180016930  lea     rcx, [rsp+78h+var_38]
0x180016935  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001693a  nop
0x18001693b  mov     rcx, [rsp+78h+var_30]
0x180016940  xor     rcx, rsp; StackCookie
0x180016943  call    __security_check_cookie
0x180016948  add     rsp, 58h
0x18001694c  pop     r15
0x18001694e  pop     r14
0x180016950  pop     rdi
0x180016951  pop     rbx
0x180016952  retn
```
