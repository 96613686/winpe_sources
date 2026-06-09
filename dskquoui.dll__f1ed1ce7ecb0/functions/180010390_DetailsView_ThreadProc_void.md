# DetailsView::ThreadProc(void *)

- ea: `0x180010390`
- end: `0x1800104cd`
- name: `?ThreadProc@DetailsView@@CAKPEAX@Z`
- size: `317`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800098ac`
- `0x180010390`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800103e6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800103e6`
- `ole32!OleInitialize` at `0x1800103b8`
- `ole32!OleInitialize` at `0x1800103b8`
- `ole32!OleUninitialize` at `0x18001049c`
- `ole32!OleUninitialize` at `0x18001049c`
- `USER32!PostMessageW` at `0x180010448`
- `USER32!PostMessageW` at `0x180010448`
- `USER32!GetMessageW` at `0x180010492`
- `USER32!GetMessageW` at `0x180010492`
- `USER32!TranslateAcceleratorW` at `0x180010465`
- `USER32!TranslateAcceleratorW` at `0x180010465`
- `USER32!TranslateMessage` at `0x180010474`
- `USER32!TranslateMessage` at `0x180010474`
- `USER32!DispatchMessageW` at `0x18001047f`
- `USER32!DispatchMessageW` at `0x18001047f`

## pseudocode

```c
__int64 __fastcall DetailsView::ThreadProc(HWND *Parameter)
{
  HWND *v1; // rbx
  HRESULT Instance; // eax
  HACCEL v3; // rdx
  HWND DesktopWindow; // rax
  unsigned int v6; // r8d
  tagMSG Msg; // [rsp+30h] [rbp-38h] BYREF

  v1 = Parameter;
  _InterlockedIncrement(&g_cRefThisDll);
  (*((void (__fastcall **)(HWND *))*Parameter + 1))(Parameter);
  if ( OleInitialize(0) >= 0 )
  {
    Instance = CoCreateInstance(&CLSID_DiskQuotaControl, 0, 1u, &IID_IDiskQuotaControl, (LPVOID *)v1 + 22);
    try
    {
      if ( Instance >= 0
        && (*(int (__fastcall **)(HWND, _QWORD, __int64))(*(_QWORD *)v1[22] + 40LL))(v1[22], *(_QWORD *)v1[32], 1) >= 0
        && (int)DetailsView::CreateMainWindow((DetailsView *)v1) >= 0 )
      {
        memset(&Msg, 0, sizeof(Msg));
        PostMessageW(v1[12], 0x5F5u, 0, 0);
        while ( GetMessageW(&Msg, 0, 0, 0) )
        {
          v3 = (HACCEL)v1[20];
          if ( !v3 || !TranslateAcceleratorW(v1[12], v3, &Msg) )
          {
            TranslateMessage(&Msg);
            DispatchMessageW(&Msg);
          }
        }
      }
      OleUninitialize();
    }
    catch ( CAllocException )
    {
      DesktopWindow = GetDesktopWindow();
      DiskQuotaMsgBox(DesktopWindow, 0x9E76u, v6, 0x10u);
      if ( Parameter[21] )
        SetWindowLongPtrW(Parameter[13], -4, (LONG_PTR)Parameter[21]);
      DetailsView::DisconnectEventSink((DetailsView *)Parameter);
      if ( Parameter[22] )
      {
        (*(void (__fastcall **)(HWND))(*(_QWORD *)Parameter[22] + 16LL))(Parameter[22]);
        Parameter[22] = 0;
      }
      if ( Parameter[62] )
      {
        if ( !OleIsCurrentClipboard((LPDATAOBJECT)Parameter[62]) )
          OleFlushClipboard();
      }
      v1 = Parameter;
    }
  }
  (*((void (__fastcall **)(HWND *))*v1 + 2))(v1);
  _InterlockedDecrement(&g_cRefThisDll);
  return 0;
}

```

## disassembly

```asm
0x180010390  mov     [rsp+arg_8], rbx
0x180010395  mov     [rsp+arg_0], rcx
0x18001039a  push    rdi
0x18001039b  sub     rsp, 60h
0x18001039f  mov     rbx, rcx
0x1800103a2  lock inc cs:?g_cRefThisDll@@3JA; long g_cRefThisDll
0x1800103a9  mov     rax, [rcx]
0x1800103ac  mov     rax, [rax+8]
0x1800103b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103b5  nop
0x1800103b6  xor     ecx, ecx; pvReserved
0x1800103b8  call    cs:__imp_OleInitialize
0x1800103be  test    eax, eax
0x1800103c0  js      loc_1800104A3
0x1800103c6  lea     rdi, [rbx+0B0h]
0x1800103cd  mov     [rsp+68h+ppv], rdi; ppv
0x1800103d2  lea     r9, IID_IDiskQuotaControl; riid
0x1800103d9  xor     edx, edx; pUnkOuter
0x1800103db  lea     r8d, [rdx+1]; dwClsContext
0x1800103df  lea     rcx, CLSID_DiskQuotaControl; rclsid
0x1800103e6  call    cs:__imp_CoCreateInstance
0x1800103ec  test    eax, eax
0x1800103ee  js      loc_18001049C
0x1800103f4  mov     rcx, [rdi]
0x1800103f7  mov     rax, [rcx]
0x1800103fa  mov     rdx, [rbx+100h]
0x180010401  mov     r8d, 1
0x180010407  mov     rdx, [rdx]
0x18001040a  mov     rax, [rax+28h]
0x18001040e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010413  test    eax, eax
0x180010415  js      loc_18001049C
0x18001041b  mov     rcx, rbx; this
0x18001041e  call    ?CreateMainWindow@DetailsView@@AEAAJXZ; DetailsView::CreateMainWindow(void)
0x180010423  test    eax, eax
0x180010425  js      short loc_18001049C
0x180010427  xorps   xmm0, xmm0
0x18001042a  movups  xmmword ptr [rsp+68h+Msg.hwnd], xmm0
0x18001042f  movups  xmmword ptr [rsp+68h+Msg.wParam], xmm0
0x180010434  movups  xmmword ptr [rsp+68h+Msg.time], xmm0
0x180010439  xor     r9d, r9d; lParam
0x18001043c  xor     r8d, r8d; wParam
0x18001043f  mov     edx, 5F5h; Msg
0x180010444  mov     rcx, [rbx+60h]; hWnd
0x180010448  call    cs:__imp_PostMessageW
0x18001044e  jmp     short loc_180010485
0x180010450  mov     rdx, [rbx+0A0h]; hAccTable
0x180010457  test    rdx, rdx
0x18001045a  jz      short loc_18001046F
0x18001045c  lea     r8, [rsp+68h+Msg]; lpMsg
0x180010461  mov     rcx, [rbx+60h]; hWnd
0x180010465  call    cs:__imp_TranslateAcceleratorW
0x18001046b  test    eax, eax
0x18001046d  jnz     short loc_180010485
0x18001046f  lea     rcx, [rsp+68h+Msg]; lpMsg
0x180010474  call    cs:__imp_TranslateMessage
0x18001047a  lea     rcx, [rsp+68h+Msg]; lpMsg
0x18001047f  call    cs:__imp_DispatchMessageW
0x180010485  xor     r9d, r9d; wMsgFilterMax
0x180010488  xor     r8d, r8d; wMsgFilterMin
0x18001048b  xor     edx, edx; hWnd
0x18001048d  lea     rcx, [rsp+68h+Msg]; lpMsg
0x180010492  call    cs:__imp_GetMessageW
0x180010498  test    eax, eax
0x18001049a  jnz     short loc_180010450
0x18001049c  call    cs:__imp_OleUninitialize
0x1800104a2  nop
0x1800104a3  jmp     short loc_1800104AA
0x1800104a5  mov     rbx, [rsp+68h+arg_0]
0x1800104aa  mov     rax, [rbx]
0x1800104ad  mov     rcx, rbx
0x1800104b0  mov     rax, [rax+10h]
0x1800104b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104b9  lock dec cs:?g_cRefThisDll@@3JA; long g_cRefThisDll
0x1800104c0  xor     eax, eax
0x1800104c2  mov     rbx, [rsp+68h+arg_8]
0x1800104c7  add     rsp, 60h
0x1800104cb  pop     rdi
0x1800104cc  retn
```
