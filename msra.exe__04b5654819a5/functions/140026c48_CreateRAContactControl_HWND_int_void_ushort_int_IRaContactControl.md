# CreateRAContactControl(HWND__ *,int,void (*)(ushort *,int),IRaContactControl * *)

- ea: `0x140026c48`
- end: `0x140027090`
- name: `?CreateRAContactControl@@YAJPEAUHWND__@@HP6AXPEAGH@ZPEAPEAUIRaContactControl@@@Z`
- size: `1096`
- prototype: `__int64 __fastcall(HWND hWnd, unsigned int, void (*)(unsigned __int16 *, int), struct IRaContactControl **)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14002c4bc`
- `0x1400328fc`

## callees

- `0x14000f740`
- `0x1400192b8`
- `0x140026c48`
- `0x140034ce4`
- `0x140035888`
- `0x14004d010`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x140026cec`
- `KERNEL32!LoadLibraryW` at `0x140026cec`
- `KERNEL32!GetProcAddress` at `0x140026d55`
- `KERNEL32!GetProcAddress` at `0x140026d55`
- `KERNEL32!GetLastError` at `0x140026d11`
- `KERNEL32!GetLastError` at `0x140026d21`
- `KERNEL32!GetLastError` at `0x140026d11`
- `KERNEL32!GetLastError` at `0x140026d21`
- `USER32!UpdateWindow` at `0x140026f2b`
- `USER32!UpdateWindow` at `0x140026f2b`
- `USER32!GetSysColor` at `0x140026efd`
- `USER32!GetSysColor` at `0x140026efd`
- `OLEAUT32!__imp_SysFreeString` at `0x140027070`
- `OLEAUT32!__imp_SysFreeString` at `0x140027070`

## string_xrefs

- `0x140026cc9`: `base\diagnosis\ra\ui\commonfunc.cpp`
- `0x140026fea`: `base\diagnosis\ra\ui\commonfunc.cpp`
- `0x140026c9a`: `racpldlg.dll`
- `0x140026cb7`: `CreateRAContactControl`
- `0x140026fde`: `CreateRAContactControl`
- `0x140026d47`: `DllGetClassObject`

## pseudocode

```c
__int64 __fastcall CreateRAContactControl(
        HWND hWnd,
        unsigned int a2,
        void (*a3)(unsigned __int16 *, int),
        struct IRaContactControl **a4)
{
  LPCWSTR v7; // rdi
  OLECHAR *v8; // r15
  CEventLogger *v9; // rcx
  signed int DirectoryAsBSTR; // eax
  CEventLogger *v11; // rcx
  int v12; // ebx
  HMODULE LibraryW; // rax
  CEventLogger *v14; // rcx
  signed int LastError; // eax
  FARPROC ProcAddress; // rax
  CEventLogger *v17; // rcx
  signed int v18; // eax
  CEventLogger *v19; // rcx
  unsigned int v20; // r9d
  __int64 v21; // r14
  __int64 v22; // rdx
  CEventLogger *v23; // rcx
  __int64 (__fastcall *v24)(__int64, _QWORD); // rbx
  DWORD SysColor; // eax
  __int64 v27; // [rsp+30h] [rbp-38h] BYREF
  LPCWSTR lpLibFileName; // [rsp+38h] [rbp-30h] BYREF
  __int64 v29; // [rsp+40h] [rbp-28h] BYREF
  __int64 v30; // [rsp+48h] [rbp-20h] BYREF
  _QWORD v31[3]; // [rsp+50h] [rbp-18h] BYREF

  v30 = 0;
  v29 = 0;
  v7 = 0;
  v27 = 0;
  v8 = 0;
  lpLibFileName = 0;
  v9 = _AtlModule;
  if ( !*((_QWORD *)_AtlModule + 79) )
  {
    DirectoryAsBSTR = GetDirectoryAsBSTR(37, (unsigned __int16 **)&lpLibFileName, L"racpldlg.dll");
    v12 = DirectoryAsBSTR;
    if ( DirectoryAsBSTR < 0 )
    {
      CEventLogger::LogError(
        v11,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
        0x16FAu,
        L"CreateRAContactControl",
        DirectoryAsBSTR);
      v8 = (OLECHAR *)lpLibFileName;
      goto LABEL_49;
    }
    v8 = (OLECHAR *)lpLibFileName;
    LibraryW = LoadLibraryW(lpLibFileName);
    v9 = _AtlModule;
    *((_QWORD *)_AtlModule + 79) = LibraryW;
    if ( (((unsigned __int64)LibraryW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      if ( GetLastError() )
      {
        LastError = GetLastError();
        v12 = LastError;
        if ( LastError > 0 )
          v12 = (unsigned __int16)LastError | 0x80070000;
        if ( v12 >= 0 )
        {
          v9 = _AtlModule;
          goto LABEL_10;
        }
      }
      else
      {
        v12 = -2147467259;
      }
      CEventLogger::LogError(
        v14,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
        0x16FDu,
        L"CreateRAContactControl",
        v12);
      goto LABEL_49;
    }
  }
LABEL_10:
  ProcAddress = GetProcAddress(*((HMODULE *)v9 + 79), "DllGetClassObject");
  if ( !ProcAddress )
  {
    v12 = -2147467261;
    CEventLogger::LogError(
      v17,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      0x1703u,
      L"CreateRAContactControl",
      0x80004003);
    goto LABEL_49;
  }
  v18 = ((__int64 (__fastcall *)(GUID *, GUID *, __int64 *))ProcAddress)(
          &CLSID_RaContactControl,
          &IID_IClassFactory,
          &v30);
  v12 = v18;
  if ( v18 < 0 )
  {
    v20 = 5897;
    goto LABEL_48;
  }
  v18 = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v30 + 24LL))(
          v30,
          0,
          &IID_IUnknown,
          &v29);
  v12 = v18;
  if ( v18 < 0 )
  {
    v20 = 5900;
    goto LABEL_48;
  }
  v21 = v29;
  AtlAxWinInit();
  if ( !v21 )
  {
    v12 = -2147024809;
LABEL_31:
    CEventLogger::LogError(
      v23,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      0x1713u,
      L"CreateRAContactControl",
      v12);
    goto LABEL_49;
  }
  lpLibFileName = 0;
  v12 = ATL::CComCreator<ATL::CComPolyObject<ATL::CAxHostWindow>>::CreateInstance(v23, v22, &lpLibFileName);
  if ( v12 >= 0 )
  {
    v31[0] = 0;
    v12 = (**(__int64 (__fastcall ***)(LPCWSTR, GUID *, _QWORD *))lpLibFileName)(
            lpLibFileName,
            &GUID_b6ea2050_048a_11d1_82b9_00c04fb9942e,
            v31);
    if ( v12 >= 0 )
      v12 = (*(__int64 (__fastcall **)(_QWORD, __int64, HWND))(*(_QWORD *)v31[0] + 40LL))(v31[0], v21, hWnd);
    if ( v31[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v31[0] + 16LL))(v31[0]);
  }
  if ( v12 < 0 )
  {
    v7 = 0;
    v23 = (CEventLogger *)lpLibFileName;
  }
  else
  {
    v7 = lpLibFileName;
    v23 = 0;
    lpLibFileName = 0;
  }
  if ( v23 )
    (*(void (__fastcall **)(CEventLogger *))(*(_QWORD *)v23 + 16LL))(v23);
  if ( v12 < 0 )
    goto LABEL_31;
  v18 = (**(__int64 (__fastcall ***)(LPCWSTR, GUID *, __int64 *))v7)(v7, &IID_IAxWinAmbientDispatch, &v27);
  v12 = v18;
  if ( v18 >= 0 )
  {
    v18 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v27 + 56LL))(v27, 0);
    v12 = v18;
    if ( v18 >= 0 )
    {
      v24 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v27 + 72LL);
      SysColor = GetSysColor(5);
      v18 = v24(v27, SysColor);
      v12 = v18;
      if ( v18 >= 0 )
      {
        UpdateWindow(hWnd);
        if ( *a4 )
        {
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a4 + 16LL))(*a4);
          *a4 = 0;
        }
        v18 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IRaContactControl **))v29)(
                v29,
                &IID_IRaContactControl,
                a4);
        v12 = v18;
        if ( v18 >= 0 )
        {
          v18 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*a4 + 32LL))(*a4, a2);
          v12 = v18;
          if ( v18 >= 0 )
          {
            v18 = (*(__int64 (__fastcall **)(_QWORD, void (*)(unsigned __int16 *, int)))(*(_QWORD *)*a4 + 40LL))(
                    *a4,
                    a3);
            v12 = v18;
            if ( v18 >= 0 )
            {
              v18 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a4 + 64LL))(*a4, 1);
              v12 = v18;
              if ( v18 >= 0 )
                goto LABEL_49;
              v20 = 5935;
            }
            else
            {
              v20 = 5934;
            }
          }
          else
          {
            v20 = 5933;
          }
        }
        else
        {
          v20 = 5928;
        }
      }
      else
      {
        v20 = 5918;
      }
    }
    else
    {
      v20 = 5915;
    }
  }
  else
  {
    v20 = 5912;
  }
LABEL_48:
  CEventLogger::LogError(
    v19,
    &Recoverable_Error,
    L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
    v20,
    L"CreateRAContactControl",
    v18);
LABEL_49:
  if ( v30 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    v30 = 0;
  }
  if ( v29 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    v29 = 0;
  }
  if ( v7 )
    (*(void (__fastcall **)(LPCWSTR))(*(_QWORD *)v7 + 16LL))(v7);
  if ( v27 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    v27 = 0;
  }
  if ( v8 )
    SysFreeString(v8);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140026c48  mov     [rsp-40h+arg_10], r8
0x140026c4d  push    rbp
0x140026c4e  push    rbx
0x140026c4f  push    rsi
0x140026c50  push    rdi
0x140026c51  push    r12
0x140026c53  push    r13
0x140026c55  push    r14
0x140026c57  push    r15
0x140026c59  mov     rbp, rsp
0x140026c5c  sub     rsp, 68h
0x140026c60  mov     rsi, r9
0x140026c63  mov     r13d, edx
0x140026c66  mov     r12, rcx
0x140026c69  mov     [rbp+var_20], 0
0x140026c71  mov     [rbp+var_28], 0
0x140026c79  xor     edi, edi
0x140026c7b  mov     [rbp+var_38], rdi
0x140026c7f  xor     r15d, r15d
0x140026c82  mov     [rbp+lpLibFileName], r15
0x140026c86  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140026c8d  cmp     [rcx+278h], rdi
0x140026c94  jnz     loc_140026D47
0x140026c9a  lea     r8, aRacpldlgDll; "racpldlg.dll"
0x140026ca1  lea     rdx, [rbp+lpLibFileName]; unsigned __int16 **
0x140026ca5  lea     ecx, [rdi+25h]; csidl
0x140026ca8  call    ?GetDirectoryAsBSTR@@YAJHPEAPEAGPEAG@Z; GetDirectoryAsBSTR(int,ushort * *,ushort *)
0x140026cad  mov     ebx, eax
0x140026caf  test    eax, eax
0x140026cb1  jns     short loc_140026CE5
0x140026cb3  mov     [rsp+68h+var_40], eax; unsigned int
0x140026cb7  lea     rax, aCreateracontac; "CreateRAContactControl"
0x140026cbe  mov     [rsp+68h+var_48], rax; unsigned __int16 *
0x140026cc3  mov     r9d, 16FAh; unsigned int
0x140026cc9  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x140026cd0  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140026cd7  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140026cdc  mov     r15, [rbp+lpLibFileName]
0x140026ce0  jmp     loc_140026FFD
0x140026ce5  mov     r15, [rbp+lpLibFileName]
0x140026ce9  mov     rcx, r15; lpLibFileName
0x140026cec  call    cs:__imp_LoadLibraryW
0x140026cf3  nop     dword ptr [rax+rax+00h]
0x140026cf8  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140026cff  mov     [rcx+278h], rax
0x140026d06  inc     rax
0x140026d09  test    rax, 0FFFFFFFFFFFFFFFEh
0x140026d0f  jnz     short loc_140026D47
0x140026d11  call    cs:__imp_GetLastError
0x140026d18  nop     dword ptr [rax+rax+00h]
0x140026d1d  test    eax, eax
0x140026d1f  jz      short loc_140026D7E
0x140026d21  call    cs:__imp_GetLastError
0x140026d28  nop     dword ptr [rax+rax+00h]
0x140026d2d  mov     ebx, eax
0x140026d2f  test    eax, eax
0x140026d31  jle     short loc_140026D3C
0x140026d33  movzx   ebx, ax
0x140026d36  or      ebx, 80070000h
0x140026d3c  test    ebx, ebx
0x140026d3e  js      short loc_140026D83
0x140026d40  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140026d47  lea     rdx, aDllgetclassobj; "DllGetClassObject"
0x140026d4e  mov     rcx, [rcx+278h]; hModule
0x140026d55  call    cs:__imp_GetProcAddress
0x140026d5c  nop     dword ptr [rax+rax+00h]
0x140026d61  test    rax, rax
0x140026d64  jnz     short loc_140026D92
0x140026d66  mov     ebx, 80004003h
0x140026d6b  mov     [rsp+68h+var_40], 80004003h
0x140026d73  mov     r9d, 1703h
0x140026d79  jmp     loc_140026FDE
0x140026d7e  mov     ebx, 80004005h
0x140026d83  mov     [rsp+68h+var_40], ebx
0x140026d87  mov     r9d, 16FDh
0x140026d8d  jmp     loc_140026FDE
0x140026d92  lea     r8, [rbp+var_20]
0x140026d96  lea     rdx, IID_IClassFactory
0x140026d9d  lea     rcx, CLSID_RaContactControl
0x140026da4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026da9  mov     ebx, eax
0x140026dab  test    eax, eax
0x140026dad  jns     short loc_140026DBA
0x140026daf  mov     r9d, 1709h
0x140026db5  jmp     loc_140026FDA
0x140026dba  mov     rcx, [rbp+var_20]
0x140026dbe  mov     rax, [rcx]
0x140026dc1  lea     r9, [rbp+var_28]
0x140026dc5  lea     r8, IID_IUnknown
0x140026dcc  xor     edx, edx
0x140026dce  mov     rax, [rax+18h]
0x140026dd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026dd7  mov     ebx, eax
0x140026dd9  test    eax, eax
0x140026ddb  jns     short loc_140026DE8
0x140026ddd  mov     r9d, 170Ch
0x140026de3  jmp     loc_140026FDA
0x140026de8  mov     r14, [rbp+var_28]
0x140026dec  call    AtlAxWinInit
0x140026df1  test    r14, r14
0x140026df4  jnz     short loc_140026E00
0x140026df6  mov     ebx, 80070057h
0x140026dfb  jmp     loc_140026E91
0x140026e00  mov     [rbp+lpLibFileName], rdi
0x140026e04  lea     r8, [rbp+lpLibFileName]
0x140026e08  call    ?CreateInstance@?$CComCreator@V?$CComPolyObject@VCAxHostWindow@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComPolyObject<ATL::CAxHostWindow>>::CreateInstance(void *,_GUID const &,void * *)
0x140026e0d  mov     ebx, eax
0x140026e0f  test    eax, eax
0x140026e11  js      short loc_140026E65
0x140026e13  mov     [rbp+var_18], rdi
0x140026e17  mov     rcx, [rbp+lpLibFileName]
0x140026e1b  mov     rax, [rcx]
0x140026e1e  lea     r8, [rbp+var_18]
0x140026e22  lea     rdx, _GUID_b6ea2050_048a_11d1_82b9_00c04fb9942e
0x140026e29  mov     rax, [rax]
0x140026e2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026e31  mov     ebx, eax
0x140026e33  test    eax, eax
0x140026e35  js      short loc_140026E4F
0x140026e37  mov     rcx, [rbp+var_18]
0x140026e3b  mov     rax, [rcx]
0x140026e3e  mov     r8, r12
0x140026e41  mov     rdx, r14
0x140026e44  mov     rax, [rax+28h]
0x140026e48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026e4d  mov     ebx, eax
0x140026e4f  mov     rcx, [rbp+var_18]
0x140026e53  test    rcx, rcx
0x140026e56  jz      short loc_140026E65
0x140026e58  mov     rax, [rcx]
0x140026e5b  mov     rax, [rax+10h]
0x140026e5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026e64  nop
0x140026e65  test    ebx, ebx
0x140026e67  js      short loc_140026E75
0x140026e69  mov     rdi, [rbp+lpLibFileName]
0x140026e6d  xor     ecx, ecx
0x140026e6f  mov     [rbp+lpLibFileName], rcx
0x140026e73  jmp     short loc_140026E7B
0x140026e75  xor     edi, edi
0x140026e77  mov     rcx, [rbp+lpLibFileName]
0x140026e7b  test    rcx, rcx
0x140026e7e  jz      short loc_140026E8D
0x140026e80  mov     rax, [rcx]
0x140026e83  mov     rax, [rax+10h]
0x140026e87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026e8c  nop
0x140026e8d  test    ebx, ebx
0x140026e8f  jns     short loc_140026EA0
0x140026e91  mov     [rsp+68h+var_40], ebx
0x140026e95  mov     r9d, 1713h
0x140026e9b  jmp     loc_140026FDE
0x140026ea0  mov     rax, [rdi]
0x140026ea3  lea     r8, [rbp+var_38]
0x140026ea7  lea     rdx, IID_IAxWinAmbientDispatch
0x140026eae  mov     rcx, rdi
0x140026eb1  mov     rax, [rax]
0x140026eb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026eb9  mov     ebx, eax
0x140026ebb  test    eax, eax
0x140026ebd  jns     short loc_140026ECA
0x140026ebf  mov     r9d, 1718h
0x140026ec5  jmp     loc_140026FDA
0x140026eca  mov     rcx, [rbp+var_38]
0x140026ece  mov     rax, [rcx]
0x140026ed1  xor     edx, edx
0x140026ed3  mov     rax, [rax+38h]
0x140026ed7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026edc  mov     ebx, eax
0x140026ede  test    eax, eax
0x140026ee0  jns     short loc_140026EED
0x140026ee2  mov     r9d, 171Bh
0x140026ee8  jmp     loc_140026FDA
0x140026eed  mov     rax, [rbp+var_38]
0x140026ef1  mov     rcx, [rax]
0x140026ef4  mov     rbx, [rcx+48h]
0x140026ef8  mov     ecx, 5; nIndex
0x140026efd  call    cs:__imp_GetSysColor
0x140026f04  nop     dword ptr [rax+rax+00h]
0x140026f09  mov     edx, eax
0x140026f0b  mov     rcx, [rbp+var_38]
0x140026f0f  mov     rax, rbx
0x140026f12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026f17  mov     ebx, eax
0x140026f19  test    eax, eax
0x140026f1b  jns     short loc_140026F28
0x140026f1d  mov     r9d, 171Eh
0x140026f23  jmp     loc_140026FDA
0x140026f28  mov     rcx, r12; hWnd
0x140026f2b  call    cs:__imp_UpdateWindow
0x140026f32  nop     dword ptr [rax+rax+00h]
0x140026f37  mov     rcx, [rsi]
0x140026f3a  test    rcx, rcx
0x140026f3d  jz      short loc_140026F52
0x140026f3f  mov     rax, [rcx]
0x140026f42  mov     rax, [rax+10h]
0x140026f46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026f4b  mov     qword ptr [rsi], 0
0x140026f52  mov     rcx, [rbp+var_28]
0x140026f56  mov     rax, [rcx]
0x140026f59  mov     r8, rsi
0x140026f5c  lea     rdx, IID_IRaContactControl
0x140026f63  mov     rax, [rax]
0x140026f66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026f6b  mov     ebx, eax
0x140026f6d  test    eax, eax
0x140026f6f  jns     short loc_140026F79
0x140026f71  mov     r9d, 1728h
0x140026f77  jmp     short loc_140026FDA
0x140026f79  mov     rcx, [rsi]
0x140026f7c  mov     rax, [rcx]
0x140026f7f  mov     edx, r13d
0x140026f82  mov     rax, [rax+20h]
0x140026f86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026f8b  mov     ebx, eax
0x140026f8d  test    eax, eax
0x140026f8f  jns     short loc_140026F99
0x140026f91  mov     r9d, 172Dh
0x140026f97  jmp     short loc_140026FDA
0x140026f99  mov     rcx, [rsi]
0x140026f9c  mov     rax, [rcx]
0x140026f9f  mov     rdx, [rbp+arg_10]
0x140026fa3  mov     rax, [rax+28h]
0x140026fa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026fac  mov     ebx, eax
0x140026fae  test    eax, eax
0x140026fb0  jns     short loc_140026FBA
0x140026fb2  mov     r9d, 172Eh
0x140026fb8  jmp     short loc_140026FDA
0x140026fba  mov     rcx, [rsi]
0x140026fbd  mov     rax, [rcx]
0x140026fc0  mov     edx, 1
0x140026fc5  mov     rax, [rax+40h]
0x140026fc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026fce  mov     ebx, eax
0x140026fd0  test    eax, eax
0x140026fd2  jns     short loc_140026FFD
0x140026fd4  mov     r9d, 172Fh; unsigned int
0x140026fda  mov     [rsp+68h+var_40], eax; unsigned int
0x140026fde  lea     rax, aCreateracontac; "CreateRAContactControl"
0x140026fe5  mov     [rsp+68h+var_48], rax; unsigned __int16 *
0x140026fea  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x140026ff1  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140026ff8  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140026ffd  mov     rcx, [rbp+var_20]
0x140027001  test    rcx, rcx
0x140027004  jz      short loc_14002701A
0x140027006  mov     rax, [rcx]
0x140027009  mov     rax, [rax+10h]
0x14002700d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027012  mov     [rbp+var_20], 0
0x14002701a  mov     rcx, [rbp+var_28]
0x14002701e  test    rcx, rcx
0x140027021  jz      short loc_140027037
0x140027023  mov     rax, [rcx]
0x140027026  mov     rax, [rax+10h]
0x14002702a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002702f  mov     [rbp+var_28], 0
0x140027037  test    rdi, rdi
0x14002703a  jz      short loc_14002704B
0x14002703c  mov     rax, [rdi]
0x14002703f  mov     rcx, rdi
0x140027042  mov     rax, [rax+10h]
0x140027046  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002704b  mov     rcx, [rbp+var_38]
0x14002704f  test    rcx, rcx
0x140027052  jz      short loc_140027068
0x140027054  mov     rax, [rcx]
0x140027057  mov     rax, [rax+10h]
0x14002705b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027060  mov     [rbp+var_38], 0
0x140027068  test    r15, r15
0x14002706b  jz      short loc_14002707C
0x14002706d  mov     rcx, r15; bstrString
0x140027070  call    cs:__imp_SysFreeString
0x140027077  nop     dword ptr [rax+rax+00h]
0x14002707c  mov     eax, ebx
0x14002707e  add     rsp, 68h
0x140027082  pop     r15
0x140027084  pop     r14
0x140027086  pop     r13
0x140027088  pop     r12
0x14002708a  pop     rdi
0x14002708b  pop     rsi
0x14002708c  pop     rbx
0x14002708d  pop     rbp
0x14002708e  retn
```
