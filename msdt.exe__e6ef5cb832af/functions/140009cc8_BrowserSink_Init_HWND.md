# BrowserSink::Init(HWND__ *)

- ea: `0x140009cc8`
- end: `0x14000a17b`
- name: `?Init@BrowserSink@@QEAAJPEAUHWND__@@@Z`
- size: `1203`
- prototype: `__int64 __fastcall(struct IUnknown *this, HWND)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x14000a184`

## callees

- `0x14000961c`
- `0x140009888`
- `0x140009cc8`
- `0x14000a998`
- `0x140020420`
- `0x140063010`

## import_xrefs

- `USER32!GetWindowLongW` at `0x140009f34`
- `USER32!GetWindowLongW` at `0x140009f34`
- `USER32!SetWindowLongW` at `0x140009f4c`
- `USER32!SetWindowLongW` at `0x140009f4c`
- `OLEAUT32!__imp_SysAllocString` at `0x14000a06b`
- `OLEAUT32!__imp_SysAllocString` at `0x14000a06b`
- `OLEAUT32!__imp_SysFreeString` at `0x14000a105`
- `OLEAUT32!__imp_SysFreeString` at `0x14000a105`
- `ATL!__imp_AtlAxCreateControlEx` at `0x140009db7`
- `ATL!__imp_AtlAxCreateControlEx` at `0x140009db7`
- `ATL!__imp_AtlAxWinInit` at `0x140009d3e`
- `ATL!__imp_AtlAxWinInit` at `0x140009d3e`
- `ole32!CoTaskMemFree` at `0x14000a11a`
- `ole32!CoTaskMemFree` at `0x14000a11a`
- `ole32!StringFromCLSID` at `0x140009d66`
- `ole32!StringFromCLSID` at `0x140009d66`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall BrowserSink::Init(struct IUnknown *this, HWND a2)
{
  OLECHAR *v4; // r14
  unsigned int v5; // esi
  int v6; // r9d
  HRESULT v7; // eax
  struct IUnknown *v8; // r12
  HWND *v9; // rbx
  LONG WindowLongW; // eax
  int v11; // eax
  __int64 (__fastcall ***v13)(_QWORD, GUID *, __int64 *); // [rsp+40h] [rbp-30h] BYREF
  __int64 (__fastcall ***v14)(_QWORD, GUID *, struct IUnknown *); // [rsp+48h] [rbp-28h] BYREF
  __int64 v15; // [rsp+50h] [rbp-20h] BYREF
  __int64 v16; // [rsp+58h] [rbp-18h] BYREF
  _QWORD v17[2]; // [rsp+60h] [rbp-10h] BYREF
  int v18; // [rsp+B8h] [rbp+48h] BYREF
  LPOLESTR lpsz; // [rsp+C0h] [rbp+50h] BYREF
  __int64 v20; // [rsp+C8h] [rbp+58h] BYREF

  v14 = 0;
  v13 = 0;
  v16 = 0;
  v17[0] = 0;
  v15 = 0;
  v20 = 0;
  v4 = 0;
  lpsz = 0;
  v18 = 0;
  if ( !a2 )
  {
    v5 = -2147024809;
    v6 = 275;
LABEL_3:
    v7 = v5;
    goto LABEL_38;
  }
  if ( !(unsigned int)AtlAxWinInit() )
  {
    v5 = -2147467259;
    v6 = 283;
    goto LABEL_3;
  }
  v7 = StringFromCLSID(&CLSID_WebBrowser, &lpsz);
  v5 = v7;
  if ( v7 < 0 )
  {
    v6 = 287;
    goto LABEL_38;
  }
  v7 = AtlAxCreateControlEx(lpsz, a2, 0, &v13, &v14, &DIID_DWebBrowserEvents2, this);
  v5 = v7;
  if ( v7 < 0 )
  {
    v6 = 297;
    goto LABEL_38;
  }
  v8 = this + 7;
  v7 = (**v14)(v14, &IID_IWebBrowser2, this + 7);
  v5 = v7;
  if ( v7 < 0 )
  {
    v6 = 300;
    goto LABEL_38;
  }
  v7 = (**v14)(v14, &IID_IOleInPlaceObject, (struct IUnknown *)&v16);
  v5 = v7;
  if ( v7 < 0 )
  {
    v6 = 305;
    goto LABEL_38;
  }
  v7 = (*(__int64 (__fastcall **)(struct IUnknownVtbl *, GUID *, struct IUnknown *))v8->lpVtbl->QueryInterface)(
         v8->lpVtbl,
         &IID_IOleInPlaceActiveObject,
         this + 8);
  v5 = v7;
  if ( v7 < 0 )
  {
    v6 = 310;
    goto LABEL_38;
  }
  v7 = (**v13)(v13, &IID_IAxWinAmbientDispatch, v17);
  v5 = v7;
  if ( v7 < 0 )
  {
    v6 = 315;
    goto LABEL_38;
  }
  v7 = (**v13)(v13, &IID_IAxWinHostWindow, &v15);
  v5 = v7;
  if ( v7 < 0 )
  {
    v6 = 320;
    goto LABEL_38;
  }
  v9 = (HWND *)&this[6];
  v7 = (*(__int64 (__fastcall **)(__int64, struct IUnknown *))(*(_QWORD *)v16 + 24LL))(v16, this + 6);
  v5 = v7;
  if ( v7 < 0 )
  {
    v6 = 326;
    goto LABEL_38;
  }
  WindowLongW = GetWindowLongW(*v9, -20);
  SetWindowLongW(*v9, -20, WindowLongW | 0x2000);
  v7 = (*(__int64 (__fastcall **)(__int64, struct IUnknown *))(*(_QWORD *)v15 + 64LL))(v15, this);
  v5 = v7;
  if ( v7 < 0 )
  {
    v6 = 338;
    goto LABEL_38;
  }
  v7 = (*(__int64 (__fastcall **)(struct IUnknownVtbl *, GUID *, __int64 *))v8->lpVtbl->QueryInterface)(
         v8->lpVtbl,
         &IID_ITargetFrame2,
         &v20);
  v5 = v7;
  if ( v7 < 0 )
  {
    v6 = 344;
    goto LABEL_38;
  }
  v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v20 + 80LL))(v20, &v18);
  v5 = v7;
  if ( v7 < 0 )
  {
    v6 = 347;
    goto LABEL_38;
  }
  v18 |= 0x14u;
  v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v20 + 72LL))(v20);
  v5 = v7;
  if ( v7 < 0 )
  {
    v6 = 352;
    goto LABEL_38;
  }
  v11 = (*((__int64 (__fastcall **)(struct IUnknownVtbl *, _QWORD))v8->lpVtbl->QueryInterface + 64))(v8->lpVtbl, 0);
  if ( v11 < 0 )
    SdpDebugPrint(1u, "Dwz IGNORED: %s:%d - hr = 0x%08X\n", "BrowserSink::Init", 358, v11);
  v4 = SysAllocString(L"about:blank");
  if ( !v4 )
  {
    v5 = -2147024882;
    v6 = 365;
    goto LABEL_3;
  }
  v7 = (*((__int64 (__fastcall **)(struct IUnknownVtbl *, OLECHAR *, _QWORD, _QWORD, _QWORD, _QWORD))v8->lpVtbl->QueryInterface
        + 11))(
         v8->lpVtbl,
         v4,
         0,
         0,
         0,
         0);
  v5 = v7;
  if ( v7 < 0 )
  {
    v6 = 368;
    goto LABEL_38;
  }
  v7 = BrowserSink::SinkHTMLDocumentEvents(this);
  v5 = v7;
  if ( v7 < 0 )
  {
    v6 = 371;
LABEL_38:
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "BrowserSink::Init", v6, v7);
    BrowserSink::Close((BrowserSink *)this);
    if ( !v4 )
      goto LABEL_42;
    goto LABEL_41;
  }
  v5 = 0;
LABEL_41:
  SysFreeString(v4);
LABEL_42:
  if ( lpsz )
  {
    CoTaskMemFree(lpsz);
    lpsz = 0;
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v20);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v15);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v17);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v16);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v13);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v14);
  return v5;
}

```

## disassembly

```asm
0x140009cc8  push    rbp
0x140009cca  push    rbx
0x140009ccb  push    rsi
0x140009ccc  push    rdi
0x140009ccd  push    r12
0x140009ccf  push    r14
0x140009cd1  push    r15
0x140009cd3  mov     rbp, rsp
0x140009cd6  sub     rsp, 70h
0x140009cda  mov     rbx, rdx
0x140009cdd  mov     r15, rcx
0x140009ce0  mov     [rbp+var_28], 0
0x140009ce8  mov     [rbp+var_30], 0
0x140009cf0  mov     [rbp+var_18], 0
0x140009cf8  mov     [rbp+var_10], 0
0x140009d00  mov     [rbp+var_20], 0
0x140009d08  mov     [rbp+arg_18], 0
0x140009d10  xor     r14d, r14d
0x140009d13  mov     [rbp+lpsz], r14
0x140009d17  mov     [rbp+arg_8], r14d
0x140009d1b  test    rdx, rdx
0x140009d1e  jnz     short loc_140009D3E
0x140009d20  mov     esi, 80070057h
0x140009d25  mov     r9d, 113h
0x140009d2b  lea     rdi, aBrowsersinkIni; "BrowserSink::Init"
0x140009d32  mov     ebx, 1
0x140009d37  mov     eax, esi
0x140009d39  jmp     loc_14000A0DC
0x140009d3e  call    cs:__imp_AtlAxWinInit
0x140009d45  nop     dword ptr [rax+rax+00h]
0x140009d4a  test    eax, eax
0x140009d4c  jnz     short loc_140009D5B
0x140009d4e  mov     esi, 80004005h
0x140009d53  mov     r9d, 11Bh
0x140009d59  jmp     short loc_140009D2B
0x140009d5b  lea     rdx, [rbp+lpsz]; lplpsz
0x140009d5f  lea     rcx, CLSID_WebBrowser; rclsid
0x140009d66  call    cs:__imp_StringFromCLSID
0x140009d6d  nop     dword ptr [rax+rax+00h]
0x140009d72  mov     esi, eax
0x140009d74  test    eax, eax
0x140009d76  jns     short loc_140009D8F
0x140009d78  mov     ebx, 1
0x140009d7d  lea     rdi, aBrowsersinkIni; "BrowserSink::Init"
0x140009d84  mov     r9d, 11Fh
0x140009d8a  jmp     loc_14000A0DC
0x140009d8f  mov     [rsp+70h+var_40], r15
0x140009d94  lea     rax, DIID_DWebBrowserEvents2
0x140009d9b  mov     [rsp+70h+var_48], rax
0x140009da0  lea     rax, [rbp+var_28]
0x140009da4  mov     [rsp+70h+var_50], rax
0x140009da9  lea     r9, [rbp+var_30]
0x140009dad  xor     r8d, r8d
0x140009db0  mov     rdx, rbx
0x140009db3  mov     rcx, [rbp+lpsz]
0x140009db7  call    cs:__imp_AtlAxCreateControlEx
0x140009dbe  nop     dword ptr [rax+rax+00h]
0x140009dc3  mov     esi, eax
0x140009dc5  test    eax, eax
0x140009dc7  jns     short loc_140009DE0
0x140009dc9  mov     ebx, 1
0x140009dce  lea     rdi, aBrowsersinkIni; "BrowserSink::Init"
0x140009dd5  mov     r9d, 129h
0x140009ddb  jmp     loc_14000A0DC
0x140009de0  mov     rcx, [rbp+var_28]
0x140009de4  lea     r12, [r15+38h]
0x140009de8  mov     rax, [rcx]
0x140009deb  mov     r8, r12
0x140009dee  lea     rdx, IID_IWebBrowser2
0x140009df5  mov     rax, [rax]
0x140009df8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009dfd  mov     esi, eax
0x140009dff  test    eax, eax
0x140009e01  jns     short loc_140009E1A
0x140009e03  mov     ebx, 1
0x140009e08  lea     rdi, aBrowsersinkIni; "BrowserSink::Init"
0x140009e0f  mov     r9d, 12Ch
0x140009e15  jmp     loc_14000A0DC
0x140009e1a  mov     rcx, [rbp+var_28]
0x140009e1e  mov     rax, [rcx]
0x140009e21  lea     r8, [rbp+var_18]
0x140009e25  lea     rdx, IID_IOleInPlaceObject
0x140009e2c  mov     rax, [rax]
0x140009e2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009e34  mov     esi, eax
0x140009e36  test    eax, eax
0x140009e38  jns     short loc_140009E51
0x140009e3a  mov     ebx, 1
0x140009e3f  lea     rdi, aBrowsersinkIni; "BrowserSink::Init"
0x140009e46  mov     r9d, 131h
0x140009e4c  jmp     loc_14000A0DC
0x140009e51  mov     rcx, [r12]
0x140009e55  mov     rax, [rcx]
0x140009e58  lea     r8, [r15+40h]
0x140009e5c  lea     rdx, IID_IOleInPlaceActiveObject
0x140009e63  mov     rax, [rax]
0x140009e66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009e6b  mov     esi, eax
0x140009e6d  test    eax, eax
0x140009e6f  jns     short loc_140009E88
0x140009e71  mov     ebx, 1
0x140009e76  lea     rdi, aBrowsersinkIni; "BrowserSink::Init"
0x140009e7d  mov     r9d, 136h
0x140009e83  jmp     loc_14000A0DC
0x140009e88  mov     rcx, [rbp+var_30]
0x140009e8c  mov     rax, [rcx]
0x140009e8f  lea     r8, [rbp+var_10]
0x140009e93  lea     rdx, IID_IAxWinAmbientDispatch
0x140009e9a  mov     rax, [rax]
0x140009e9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009ea2  mov     esi, eax
0x140009ea4  test    eax, eax
0x140009ea6  jns     short loc_140009EBF
0x140009ea8  mov     ebx, 1
0x140009ead  lea     rdi, aBrowsersinkIni; "BrowserSink::Init"
0x140009eb4  mov     r9d, 13Bh
0x140009eba  jmp     loc_14000A0DC
0x140009ebf  mov     rcx, [rbp+var_30]
0x140009ec3  mov     rax, [rcx]
0x140009ec6  lea     r8, [rbp+var_20]
0x140009eca  lea     rdx, IID_IAxWinHostWindow
0x140009ed1  mov     rax, [rax]
0x140009ed4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009ed9  mov     esi, eax
0x140009edb  test    eax, eax
0x140009edd  jns     short loc_140009EF6
0x140009edf  mov     ebx, 1
0x140009ee4  lea     rdi, aBrowsersinkIni; "BrowserSink::Init"
0x140009eeb  mov     r9d, 140h
0x140009ef1  jmp     loc_14000A0DC
0x140009ef6  mov     rcx, [rbp+var_18]
0x140009efa  lea     rbx, [r15+30h]
0x140009efe  mov     rax, [rcx]
0x140009f01  mov     rdx, rbx
0x140009f04  mov     rax, [rax+18h]
0x140009f08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009f0d  mov     esi, eax
0x140009f0f  test    eax, eax
0x140009f11  jns     short loc_140009F2A
0x140009f13  mov     ebx, 1
0x140009f18  lea     rdi, aBrowsersinkIni; "BrowserSink::Init"
0x140009f1f  mov     r9d, 146h
0x140009f25  jmp     loc_14000A0DC
0x140009f2a  mov     edi, 0FFFFFFECh
0x140009f2f  mov     edx, edi; nIndex
0x140009f31  mov     rcx, [rbx]; hWnd
0x140009f34  call    cs:__imp_GetWindowLongW
0x140009f3b  nop     dword ptr [rax+rax+00h]
0x140009f40  bts     eax, 0Dh
0x140009f44  mov     r8d, eax; dwNewLong
0x140009f47  mov     edx, edi; nIndex
0x140009f49  mov     rcx, [rbx]; hWnd
0x140009f4c  call    cs:__imp_SetWindowLongW
0x140009f53  nop     dword ptr [rax+rax+00h]
0x140009f58  mov     rcx, [rbp+var_20]
0x140009f5c  mov     rax, [rcx]
0x140009f5f  mov     rdx, r15
0x140009f62  mov     rax, [rax+40h]
0x140009f66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009f6b  mov     esi, eax
0x140009f6d  test    eax, eax
0x140009f6f  jns     short loc_140009F86
0x140009f71  lea     ebx, [rdi+15h]
0x140009f74  lea     rdi, aBrowsersinkIni; "BrowserSink::Init"
0x140009f7b  mov     r9d, 152h
0x140009f81  jmp     loc_14000A0DC
0x140009f86  mov     rcx, [r12]
0x140009f8a  mov     rax, [rcx]
0x140009f8d  lea     r8, [rbp+arg_18]
0x140009f91  lea     rdx, IID_ITargetFrame2
0x140009f98  mov     rax, [rax]
0x140009f9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009fa0  mov     esi, eax
0x140009fa2  test    eax, eax
0x140009fa4  jns     short loc_140009FBD
0x140009fa6  mov     ebx, 1
0x140009fab  lea     rdi, aBrowsersinkIni; "BrowserSink::Init"
0x140009fb2  mov     r9d, 158h
0x140009fb8  jmp     loc_14000A0DC
0x140009fbd  mov     rcx, [rbp+arg_18]
0x140009fc1  mov     rax, [rcx]
0x140009fc4  lea     rdx, [rbp+arg_8]
0x140009fc8  mov     rax, [rax+50h]
0x140009fcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009fd1  mov     esi, eax
0x140009fd3  test    eax, eax
0x140009fd5  jns     short loc_140009FEE
0x140009fd7  mov     ebx, 1
0x140009fdc  lea     rdi, aBrowsersinkIni; "BrowserSink::Init"
0x140009fe3  mov     r9d, 15Bh
0x140009fe9  jmp     loc_14000A0DC
0x140009fee  mov     edx, [rbp+arg_8]
0x140009ff1  or      edx, 14h
0x140009ff4  mov     [rbp+arg_8], edx
0x140009ff7  mov     rcx, [rbp+arg_18]
0x140009ffb  mov     rax, [rcx]
0x140009ffe  mov     rax, [rax+48h]
0x14000a002  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a007  mov     esi, eax
0x14000a009  test    eax, eax
0x14000a00b  jns     short loc_14000A024
0x14000a00d  mov     ebx, 1
0x14000a012  lea     rdi, aBrowsersinkIni; "BrowserSink::Init"
0x14000a019  mov     r9d, 160h
0x14000a01f  jmp     loc_14000A0DC
0x14000a024  mov     rcx, [r12]
0x14000a028  mov     rax, [rcx]
0x14000a02b  xor     edx, edx
0x14000a02d  mov     rax, [rax+200h]
0x14000a034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a039  mov     ebx, 1
0x14000a03e  lea     rdi, aBrowsersinkIni; "BrowserSink::Init"
0x14000a045  test    eax, eax
0x14000a047  jns     short loc_14000A064
0x14000a049  mov     dword ptr [rsp+70h+var_50], eax
0x14000a04d  mov     r9d, 166h
0x14000a053  mov     r8, rdi
0x14000a056  lea     rdx, aDwzIgnoredSDHr; "Dwz IGNORED: %s:%d - hr = 0x%08X\n"
0x14000a05d  mov     ecx, ebx; Level
0x14000a05f  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14000a064  lea     rcx, psz; "about:blank"
0x14000a06b  call    cs:__imp_SysAllocString
0x14000a072  nop     dword ptr [rax+rax+00h]
0x14000a077  mov     r14, rax
0x14000a07a  test    rax, rax
0x14000a07d  jnz     short loc_14000A08F
0x14000a07f  mov     esi, 8007000Eh
0x14000a084  mov     r9d, 16Dh
0x14000a08a  jmp     loc_140009D37
0x14000a08f  mov     rcx, [r12]
0x14000a093  mov     rax, [rcx]
0x14000a096  mov     [rsp+70h+var_48], 0
0x14000a09f  mov     [rsp+70h+var_50], 0
0x14000a0a8  xor     r9d, r9d
0x14000a0ab  xor     r8d, r8d
0x14000a0ae  mov     rdx, r14
0x14000a0b1  mov     rax, [rax+58h]
0x14000a0b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a0ba  mov     esi, eax
0x14000a0bc  test    eax, eax
0x14000a0be  jns     short loc_14000A0C8
0x14000a0c0  mov     r9d, 170h
0x14000a0c6  jmp     short loc_14000A0DC
0x14000a0c8  mov     rcx, r15; this
0x14000a0cb  call    ?SinkHTMLDocumentEvents@BrowserSink@@IEAAJXZ; BrowserSink::SinkHTMLDocumentEvents(void)
0x14000a0d0  mov     esi, eax
0x14000a0d2  test    eax, eax
0x14000a0d4  jns     short loc_14000A100
0x14000a0d6  mov     r9d, 173h
0x14000a0dc  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14000a0e3  mov     dword ptr [rsp+70h+var_50], eax
0x14000a0e7  mov     r8, rdi
0x14000a0ea  mov     ecx, ebx; Level
0x14000a0ec  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14000a0f1  mov     rcx, r15; this
0x14000a0f4  call    ?Close@BrowserSink@@QEAAXXZ; BrowserSink::Close(void)
0x14000a0f9  test    r14, r14
0x14000a0fc  jz      short loc_14000A111
0x14000a0fe  jmp     short loc_14000A102
0x14000a100  xor     esi, esi
0x14000a102  mov     rcx, r14; bstrString
0x14000a105  call    cs:__imp_SysFreeString
0x14000a10c  nop     dword ptr [rax+rax+00h]
0x14000a111  mov     rcx, [rbp+lpsz]; pv
0x14000a115  test    rcx, rcx
0x14000a118  jz      short loc_14000A12E
0x14000a11a  call    cs:__imp_CoTaskMemFree
0x14000a121  nop     dword ptr [rax+rax+00h]
0x14000a126  mov     [rbp+lpsz], 0
0x14000a12e  lea     rcx, [rbp+arg_18]
0x14000a132  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14000a137  nop
0x14000a138  lea     rcx, [rbp+var_20]
0x14000a13c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14000a141  nop
0x14000a142  lea     rcx, [rbp+var_10]
0x14000a146  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14000a14b  nop
0x14000a14c  lea     rcx, [rbp+var_18]
0x14000a150  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14000a155  nop
0x14000a156  lea     rcx, [rbp+var_30]
0x14000a15a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14000a15f  nop
0x14000a160  lea     rcx, [rbp+var_28]
0x14000a164  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14000a169  mov     eax, esi
0x14000a16b  add     rsp, 70h
0x14000a16f  pop     r15
0x14000a171  pop     r14
0x14000a173  pop     r12
0x14000a175  pop     rdi
0x14000a176  pop     rsi
0x14000a177  pop     rbx
0x14000a178  pop     rbp
0x14000a179  retn
```
