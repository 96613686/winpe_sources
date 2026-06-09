# CFtpProp::_PropertySheetThreadProc(void *)

- ea: `0x18001ebe0`
- end: `0x18001ed62`
- name: `?_PropertySheetThreadProc@CFtpProp@@SAKPEAX@Z`
- size: `386`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180002240`
- `0x180002b60`
- `0x18001ebe0`
- `0x180026e14`
- `0x180026e64`
- `0x180028010`

## import_xrefs

- `SHLWAPI!__imp_SHCreateWorkerWindowW` at `0x18001ec8a`
- `SHLWAPI!__imp_SHCreateWorkerWindowW` at `0x18001ec8a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001ec66`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001ec66`
- `ole32!OleInitialize` at `0x18001ec2f`
- `ole32!OleInitialize` at `0x18001ec2f`
- `ole32!OleUninitialize` at `0x18001ed36`
- `ole32!OleUninitialize` at `0x18001ed36`
- `USER32!DestroyWindow` at `0x18001ed1d`
- `USER32!DestroyWindow` at `0x18001ed1d`

## pseudocode

```c
__int64 __fastcall CFtpProp::_PropertySheetThreadProc(_QWORD *Parameter)
{
  HRESULT v2; // edi
  HWND v3; // rax
  INITCOMMONCONTROLSEX picce; // [rsp+30h] [rbp-D0h] BYREF
  PROPSHEETHEADERW_V2 v6; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v7[14]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR Buffer[264]; // [rsp+110h] [rbp+10h] BYREF

  memset_0(&v6, 0, sizeof(v6));
  memset_0(v7, 0, 0x68u);
  picce.dwSize = 8;
  v2 = OleInitialize(0);
  picce.dwICC = 8704;
  InitCommonControlsEx(&picce);
  LoadStringW(g_hinst, 0x106u, Buffer, 260);
  v3 = (HWND)SHCreateWorkerWindowW(0, Parameter[4], 0, 0, 0, 0);
  v6.dwSize = 96;
  v6.hwndParent = v3;
  v6.hInstance = g_hinst;
  v7[1] = g_hinst;
  v7[5] = CFtpProp::DlgProc;
  v6.pszCaption = Buffer;
  v6.dwFlags = 33554569;
  v6.nPages = 1;
  v6.nStartPage = 0;
  v6.ppsp = (LPCPROPSHEETPAGEW)v7;
  v7[0] = 104;
  v7[2] = 32;
  v7[6] = Parameter;
  if ( g_hActCtx != (HANDLE)-1LL )
  {
    v7[11] = g_hActCtx;
    HIDWORD(v7[0]) = 0x4000;
  }
  PropertySheetW(&v6);
  DestroyWindow(v6.hwndParent);
  (*(void (__fastcall **)(_QWORD *))(*Parameter + 16LL))(Parameter);
  if ( v2 >= 0 )
    OleUninitialize();
  return 0;
}

```

## disassembly

```asm
0x18001ebe0  mov     [rsp-8+arg_8], rbx
0x18001ebe5  mov     [rsp-8+arg_10], rdi
0x18001ebea  push    rbp
0x18001ebeb  lea     rbp, [rsp-230h]
0x18001ebf3  sub     rsp, 330h
0x18001ebfa  mov     rax, cs:__security_cookie
0x18001ec01  xor     rax, rsp
0x18001ec04  mov     [rbp+230h+var_10], rax
0x18001ec0b  xor     edx, edx; Val
0x18001ec0d  mov     rbx, rcx
0x18001ec10  lea     rcx, [rsp+330h+var_2F0]; void *
0x18001ec15  lea     r8d, [rdx+60h]; Size
0x18001ec19  call    memset_0
0x18001ec1e  xor     edx, edx; Val
0x18001ec20  lea     rcx, [rbp+230h+var_290]; void *
0x18001ec24  lea     r8d, [rdx+68h]; Size
0x18001ec28  call    memset_0
0x18001ec2d  xor     ecx, ecx; pvReserved
0x18001ec2f  call    cs:__imp_OleInitialize
0x18001ec35  lea     rcx, [rsp+330h+picce]; picce
0x18001ec3a  mov     [rsp+330h+picce.dwSize], 8
0x18001ec42  mov     edi, eax
0x18001ec44  mov     [rsp+330h+picce.dwICC], 2200h
0x18001ec4c  call    InitCommonControlsEx
0x18001ec51  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hInstance
0x18001ec58  lea     r8, [rbp+230h+Buffer]; lpBuffer
0x18001ec5c  mov     r9d, 104h; cchBufferMax
0x18001ec62  lea     edx, [r9+2]; uID
0x18001ec66  call    cs:__imp_LoadStringW
0x18001ec6c  mov     rdx, [rbx+20h]
0x18001ec70  xor     r9d, r9d
0x18001ec73  xor     r8d, r8d
0x18001ec76  mov     [rsp+330h+var_308], 0
0x18001ec7f  xor     ecx, ecx
0x18001ec81  mov     [rsp+330h+var_310], 0
0x18001ec8a  call    cs:__imp_SHCreateWorkerWindowW
0x18001ec90  lea     rcx, [rbp+230h+Buffer]
0x18001ec94  mov     [rsp+330h+var_2F0.dwSize], 60h ; '`'
0x18001ec9c  mov     [rsp+330h+var_2F0.hwndParent], rax
0x18001eca1  mov     rax, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hinst
0x18001eca8  mov     [rsp+330h+var_2F0.hInstance], rax
0x18001ecad  mov     [rbp+230h+var_288], rax
0x18001ecb1  lea     rax, ?DlgProc@CFtpProp@@KA_JPEAUHWND__@@I_K_J@Z; CFtpProp::DlgProc(HWND__ *,uint,unsigned __int64,__int64)
0x18001ecb8  mov     [rbp+230h+var_268], rax
0x18001ecbc  mov     rax, cs:g_hActCtx
0x18001ecc3  mov     [rsp+330h+var_2F0.pszCaption], rcx
0x18001ecc8  lea     rcx, [rbp+230h+var_290]
0x18001eccc  mov     [rsp+330h+var_2F0.dwFlags], 2000089h
0x18001ecd4  mov     [rsp+330h+var_2F0.nPages], 1
0x18001ecdc  mov     dword ptr [rsp+330h+var_2F0.30h], 0
0x18001ece4  mov     qword ptr [rsp+330h+var_2F0.38h], rcx
0x18001ece9  mov     [rbp+230h+var_290], 68h ; 'h'
0x18001ecf1  mov     [rbp+230h+var_280], 20h ; ' '
0x18001ecf9  mov     [rbp+230h+var_260], rbx
0x18001ecfd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001ed01  jz      short loc_18001ED0E
0x18001ed03  mov     [rbp+230h+var_238], rax
0x18001ed07  mov     dword ptr [rbp+230h+var_290+4], 4000h
0x18001ed0e  lea     rcx, [rsp+330h+var_2F0]; LPCPROPSHEETHEADERW
0x18001ed13  call    PropertySheetW
0x18001ed18  mov     rcx, [rsp+330h+var_2F0.hwndParent]; hWnd
0x18001ed1d  call    cs:__imp_DestroyWindow
0x18001ed23  mov     rax, [rbx]
0x18001ed26  mov     rcx, rbx
0x18001ed29  mov     rax, [rax+10h]
0x18001ed2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed32  test    edi, edi
0x18001ed34  js      short loc_18001ED3C
0x18001ed36  call    cs:__imp_OleUninitialize
0x18001ed3c  xor     eax, eax
0x18001ed3e  mov     rcx, [rbp+230h+var_10]
0x18001ed45  xor     rcx, rsp; StackCookie
0x18001ed48  call    __security_check_cookie
0x18001ed4d  lea     r11, [rsp+330h+var_s0]
0x18001ed55  mov     rbx, [r11+18h]
0x18001ed59  mov     rdi, [r11+20h]
0x18001ed5d  mov     rsp, r11
0x18001ed60  pop     rbp
0x18001ed61  retn
```
