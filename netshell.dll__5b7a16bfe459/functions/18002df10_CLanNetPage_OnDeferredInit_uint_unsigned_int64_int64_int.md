# CLanNetPage::OnDeferredInit(uint,unsigned __int64,__int64,int &)

- ea: `0x18002df10`
- end: `0x18002e24f`
- name: `?OnDeferredInit@CLanNetPage@@QEAA_JI_K_JAEAH@Z`
- size: `831`
- prototype: `__int64 __fastcall(CLanNetPage *__hidden this, unsigned int, unsigned __int64, __int64, int *)`
- caller_count: `3`
- callee_count: `15`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800087a0`
- `0x18002fd40`
- `0x18002fe40`

## callees

- `0x180009930`
- `0x180017714`
- `0x180018d74`
- `0x18001bc10`
- `0x18001e1e0`
- `0x18002bf6c`
- `0x18002c0a8`
- `0x18002c310`
- `0x18002c3e4`
- `0x18002df10`
- `0x180032614`
- `0x1800333cc`
- `0x180034bdc`
- `0x180041440`
- `0x180065010`

## import_xrefs

- `USER32!SetDlgItemTextW` at `0x18002e1f0`
- `USER32!SetDlgItemTextW` at `0x18002e1f0`
- `USER32!UpdateWindow` at `0x18002df8a`
- `USER32!UpdateWindow` at `0x18002e0d2`
- `USER32!UpdateWindow` at `0x18002e216`
- `USER32!UpdateWindow` at `0x18002df8a`
- `USER32!UpdateWindow` at `0x18002e0d2`
- `USER32!UpdateWindow` at `0x18002e216`
- `USER32!ShowWindow` at `0x18002e0c9`
- `USER32!ShowWindow` at `0x18002e0c9`
- `USER32!EnableWindow` at `0x18002df6a`
- `USER32!EnableWindow` at `0x18002df81`
- `USER32!EnableWindow` at `0x18002e074`
- `USER32!EnableWindow` at `0x18002e14b`
- `USER32!EnableWindow` at `0x18002df6a`
- `USER32!EnableWindow` at `0x18002df81`
- `USER32!EnableWindow` at `0x18002e074`
- `USER32!EnableWindow` at `0x18002e14b`
- `USER32!SendDlgItemMessageW` at `0x18002e0ac`
- `USER32!SendDlgItemMessageW` at `0x18002e0ac`
- `ole32!CoTaskMemFree` at `0x18002e155`
- `ole32!CoTaskMemFree` at `0x18002e203`
- `ole32!CoTaskMemFree` at `0x18002e20d`
- `ole32!CoTaskMemFree` at `0x18002e155`
- `ole32!CoTaskMemFree` at `0x18002e203`
- `ole32!CoTaskMemFree` at `0x18002e20d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CLanNetPage::OnDeferredInit(CLanNetPage *this)
{
  HICON v2; // rbx
  HWND *v3; // r14
  HWND v4; // r15
  HWND v5; // rcx
  HWND v6; // rcx
  int Instance; // esi
  int v8; // eax
  HWND *DlgItem; // rax
  HWND *v10; // rax
  unsigned int v11; // r9d
  unsigned int v12; // r8d
  WPARAM wParam; // [rsp+30h] [rbp-50h] BYREF
  NETCON_PROPERTIES *pProps; // [rsp+38h] [rbp-48h] BYREF
  unsigned __int16 *v16; // [rsp+40h] [rbp-40h] BYREF
  HWND v17[2]; // [rsp+48h] [rbp-38h] BYREF
  _BYTE v18[8]; // [rsp+58h] [rbp-28h] BYREF
  LPVOID pv[2]; // [rsp+60h] [rbp-20h] BYREF
  __int64 v20; // [rsp+70h] [rbp-10h]

  v2 = BeginWaitCursor();
  v17[1] = (HWND)v2;
  v3 = (HWND *)((char *)this + 8);
  v4 = *(HWND *)ATL::CWindow::GetParent((char *)this + 8, v18);
  v5 = (HWND)*((_QWORD *)this + 13);
  if ( v5 )
    EnableWindow(v5, 1);
  v6 = (HWND)*((_QWORD *)this + 17);
  if ( v6 )
    EnableWindow(v6, 1);
  UpdateWindow(v4);
  Instance = CNetSetupHelper::CreateInstance((struct INetSetupHelper **)this + 4);
  if ( Instance )
    goto LABEL_25;
  Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 3) + 24LL))(*((_QWORD *)this + 3), 0);
  if ( Instance )
    goto LABEL_25;
  if ( (int)HrQIAndSetProxyBlanketBase(
              *((struct IUnknown **)this + 2),
              &GUID_faedcf54_31fe_11d1_aad2_00805fc1270e,
              (void **)this + 19) < 0 )
    goto LABEL_28;
  *(_OWORD *)pv = 0;
  v20 = 0;
  if ( (*(int (__fastcall **)(_QWORD, __int64, LPVOID *))(**((_QWORD **)this + 19) + 24LL))(
         *((_QWORD *)this + 19),
         255,
         pv) < 0 )
    goto LABEL_28;
  ReleaseObj(*((struct IUnknown **)this + 6));
  if ( (unsigned int)HrPnccFromGuid(
                       *((struct INetCfg **)this + 3),
                       (const struct _GUID *)&pv[1],
                       (struct INetCfgComponent **)this + 6) )
  {
    v8 = (***((__int64 (__fastcall ****)(_QWORD, LPVOID *, char *))this + 4))(
           *((_QWORD *)this + 4),
           &pv[1],
           (char *)this + 48);
    Instance = v8;
    if ( v8 )
    {
      if ( v8 == 1 )
        Instance = -2147024894;
      goto LABEL_24;
    }
    *((_BYTE *)this + 165) = 0;
    DlgItem = (HWND *)ATL::CWindow::GetDlgItem((char *)this + 8, v17, 15031);
    EnableWindow(*DlgItem, 0);
  }
  else
  {
    *((_BYTE *)this + 165) = 1;
  }
  wParam = 0;
  if ( (int)HrGetDeviceIcon((HICON *)&wParam) >= 0 )
  {
    SendDlgItemMessageW(*v3, 16006, 0x170u, wParam, 0);
    v10 = (HWND *)ATL::CWindow::GetDlgItem((char *)this + 8, v17, 16006);
    ShowWindow(*v10, 5);
  }
  UpdateWindow(v4);
  Instance = (*(__int64 (__fastcall **)(CLanNetPage *))(*(_QWORD *)this + 32LL))(this);
  if ( *((_BYTE *)this + 161) )
  {
    v11 = 16041;
  }
  else if ( *((_BYTE *)this + 162) )
  {
    v11 = 16042;
  }
  else
  {
    if ( !*((_BYTE *)this + 144) )
      goto LABEL_24;
    v11 = 16040;
  }
  NcMsgBox(hInst, *v3, 0x3E90u, v11, 0x40u);
LABEL_24:
  EnableWindow(*v3, 1);
  CoTaskMemFree(pv[0]);
LABEL_25:
  if ( Instance >= 0 )
  {
    pProps = 0;
    if ( (*(int (__fastcall **)(_QWORD, NETCON_PROPERTIES **))(**((_QWORD **)this + 2) + 56LL))(
           *((_QWORD *)this + 2),
           &pProps) >= 0 )
    {
      v16 = 0;
      wParam = 0;
      (*(void (__fastcall **)(_QWORD, unsigned __int16 **))(**((_QWORD **)this + 6) + 72LL))(
        *((_QWORD *)this + 6),
        &v16);
      (*(void (__fastcall **)(_QWORD, WPARAM *))(**((_QWORD **)this + 6) + 88LL))(*((_QWORD *)this + 6), &wParam);
      v17[0] = 0;
      CreateDeviceDataTip(*v3, v17, v12, v16, (const unsigned __int16 *)wParam);
      SetDlgItemTextW(*v3, 15003, pProps->pszwDeviceName);
      NcFreeNetconProperties(pProps);
      CoTaskMemFree(v16);
      CoTaskMemFree((LPVOID)wParam);
    }
  }
LABEL_28:
  UpdateWindow(v4);
  EndWaitCursor(v2);
  return 0;
}

```

## disassembly

```asm
0x18002df10  mov     [rsp-28h+arg_8], rbx
0x18002df15  mov     [rsp-28h+arg_10], rsi
0x18002df1a  push    rbp
0x18002df1b  push    rdi
0x18002df1c  push    r12
0x18002df1e  push    r14
0x18002df20  push    r15
0x18002df22  mov     rbp, rsp
0x18002df25  sub     rsp, 80h
0x18002df2c  mov     rax, cs:__security_cookie
0x18002df33  xor     rax, rsp
0x18002df36  mov     [rbp+var_8], rax
0x18002df3a  mov     rdi, rcx
0x18002df3d  call    ?BeginWaitCursor@@YAPEAUHICON__@@XZ; BeginWaitCursor(void)
0x18002df42  mov     rbx, rax
0x18002df45  mov     [rbp+var_30], rax
0x18002df49  lea     r14, [rdi+8]
0x18002df4d  lea     rdx, [rbp+var_28]
0x18002df51  mov     rcx, r14
0x18002df54  call    ?GetParent@CWindow@ATL@@QEBA?AV12@XZ; ATL::CWindow::GetParent(void)
0x18002df59  mov     r15, [rax]
0x18002df5c  mov     rcx, [rdi+68h]; hWnd
0x18002df60  test    rcx, rcx
0x18002df63  jz      short loc_18002DF70
0x18002df65  mov     edx, 1; bEnable
0x18002df6a  call    cs:__imp_EnableWindow
0x18002df70  mov     rcx, [rdi+88h]; hWnd
0x18002df77  test    rcx, rcx
0x18002df7a  jz      short loc_18002DF87
0x18002df7c  mov     edx, 1; bEnable
0x18002df81  call    cs:__imp_EnableWindow
0x18002df87  mov     rcx, r15; hWnd
0x18002df8a  call    cs:__imp_UpdateWindow
0x18002df90  lea     rcx, [rdi+20h]; struct INetSetupHelper **
0x18002df94  call    ?CreateInstance@CNetSetupHelper@@SAJPEAPEAVINetSetupHelper@@@Z; CNetSetupHelper::CreateInstance(INetSetupHelper * *)
0x18002df99  mov     esi, eax
0x18002df9b  test    eax, eax
0x18002df9d  jnz     loc_18002E15B
0x18002dfa3  mov     rcx, [rdi+18h]
0x18002dfa7  mov     rax, [rcx]
0x18002dfaa  xor     edx, edx
0x18002dfac  mov     rax, [rax+18h]
0x18002dfb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dfb5  mov     esi, eax
0x18002dfb7  test    eax, eax
0x18002dfb9  jnz     loc_18002E15B
0x18002dfbf  lea     rsi, [rdi+98h]
0x18002dfc6  mov     r8, rsi; void **
0x18002dfc9  lea     rdx, _GUID_faedcf54_31fe_11d1_aad2_00805fc1270e; struct _GUID *
0x18002dfd0  mov     rcx, [rdi+10h]; struct IUnknown *
0x18002dfd4  call    ?HrQIAndSetProxyBlanketBase@@YAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; HrQIAndSetProxyBlanketBase(IUnknown *,_GUID const &,void * *)
0x18002dfd9  test    eax, eax
0x18002dfdb  js      loc_18002E213
0x18002dfe1  xorps   xmm0, xmm0
0x18002dfe4  xor     eax, eax
0x18002dfe6  movups  xmmword ptr [rbp+pv], xmm0
0x18002dfea  mov     [rbp+var_10], rax
0x18002dfee  mov     rcx, [rsi]
0x18002dff1  mov     rax, [rcx]
0x18002dff4  lea     r8, [rbp+pv]
0x18002dff8  mov     edx, 0FFh
0x18002dffd  mov     rax, [rax+18h]
0x18002e001  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e006  test    eax, eax
0x18002e008  js      loc_18002E213
0x18002e00e  lea     rsi, [rdi+30h]
0x18002e012  mov     rcx, [rsi]; struct IUnknown *
0x18002e015  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x18002e01a  mov     r8, rsi; struct INetCfgComponent **
0x18002e01d  lea     rdx, [rbp+pv+8]; struct _GUID *
0x18002e021  mov     rcx, [rdi+18h]; struct INetCfg *
0x18002e025  call    ?HrPnccFromGuid@@YAJPEAUINetCfg@@AEBU_GUID@@PEAPEAUINetCfgComponent@@@Z; HrPnccFromGuid(INetCfg *,_GUID const &,INetCfgComponent * *)
0x18002e02a  test    eax, eax
0x18002e02c  jnz     short loc_18002E037
0x18002e02e  mov     byte ptr [rdi+0A5h], 1
0x18002e035  jmp     short loc_18002E07A
0x18002e037  mov     rcx, [rdi+20h]
0x18002e03b  mov     rax, [rcx]
0x18002e03e  mov     r8, rsi
0x18002e041  lea     rdx, [rbp+pv+8]
0x18002e045  mov     rax, [rax]
0x18002e048  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e04d  mov     esi, eax
0x18002e04f  test    eax, eax
0x18002e051  jnz     loc_18002E139
0x18002e057  mov     [rdi+0A5h], al
0x18002e05d  mov     r8d, 3AB7h
0x18002e063  lea     rdx, [rbp+var_38]
0x18002e067  mov     rcx, r14
0x18002e06a  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x18002e06f  xor     edx, edx; bEnable
0x18002e071  mov     rcx, [rax]; hWnd
0x18002e074  call    cs:__imp_EnableWindow
0x18002e07a  mov     [rbp+wParam], 0
0x18002e082  lea     rcx, [rbp+wParam]; HICON *
0x18002e086  call    ?HrGetDeviceIcon@@YAJPEAPEAUHICON__@@@Z; HrGetDeviceIcon(HICON__ * *)
0x18002e08b  test    eax, eax
0x18002e08d  js      short loc_18002E0CF
0x18002e08f  mov     [rsp+80h+lParam], 0; lParam
0x18002e098  mov     r9, [rbp+wParam]; wParam
0x18002e09c  mov     esi, 3E86h
0x18002e0a1  mov     r8d, 170h; Msg
0x18002e0a7  mov     edx, esi; nIDDlgItem
0x18002e0a9  mov     rcx, [r14]; hDlg
0x18002e0ac  call    cs:__imp_SendDlgItemMessageW
0x18002e0b2  mov     r8d, esi
0x18002e0b5  lea     rdx, [rbp+var_38]
0x18002e0b9  mov     rcx, r14
0x18002e0bc  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x18002e0c1  mov     edx, 5; nCmdShow
0x18002e0c6  mov     rcx, [rax]; hWnd
0x18002e0c9  call    cs:__imp_ShowWindow
0x18002e0cf  mov     rcx, r15; hWnd
0x18002e0d2  call    cs:__imp_UpdateWindow
0x18002e0d8  mov     rax, [rdi]
0x18002e0db  mov     rcx, rdi
0x18002e0de  mov     rax, [rax+20h]
0x18002e0e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e0e7  mov     esi, eax
0x18002e0e9  cmp     byte ptr [rdi+0A1h], 0
0x18002e0f0  jz      short loc_18002E0FA
0x18002e0f2  mov     r9d, 3EA9h
0x18002e0f8  jmp     short loc_18002E109
0x18002e0fa  cmp     byte ptr [rdi+0A2h], 0
0x18002e101  jz      short loc_18002E128
0x18002e103  mov     r9d, 3EAAh; unsigned int
0x18002e109  mov     dword ptr [rsp+80h+lParam], 40h ; '@'; uType
0x18002e111  mov     r8d, 3E90h; unsigned int
0x18002e117  mov     rdx, [r14]; hWnd
0x18002e11a  mov     rcx, cs:hInst; hModule
0x18002e121  call    ?NcMsgBox@@YAHPEAUHINSTANCE__@@PEAUHWND__@@IIIZZ; NcMsgBox(HINSTANCE__ *,HWND__ *,uint,uint,uint,...)
0x18002e126  jmp     short loc_18002E143
0x18002e128  cmp     byte ptr [rdi+90h], 0
0x18002e12f  jz      short loc_18002E143
0x18002e131  mov     r9d, 3EA8h
0x18002e137  jmp     short loc_18002E109
0x18002e139  cmp     eax, 1
0x18002e13c  jnz     short loc_18002E143
0x18002e13e  mov     esi, 80070002h
0x18002e143  mov     edx, 1; bEnable
0x18002e148  mov     rcx, [r14]; hWnd
0x18002e14b  call    cs:__imp_EnableWindow
0x18002e151  mov     rcx, [rbp+pv]; pv
0x18002e155  call    cs:__imp_CoTaskMemFree
0x18002e15b  test    esi, esi
0x18002e15d  js      loc_18002E213
0x18002e163  mov     [rbp+pProps], 0
0x18002e16b  mov     rcx, [rdi+10h]
0x18002e16f  mov     rax, [rcx]
0x18002e172  lea     rdx, [rbp+pProps]
0x18002e176  mov     rax, [rax+38h]
0x18002e17a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e17f  test    eax, eax
0x18002e181  js      loc_18002E213
0x18002e187  mov     [rbp+var_40], 0
0x18002e18f  mov     [rbp+wParam], 0
0x18002e197  mov     rcx, [rdi+30h]
0x18002e19b  mov     rax, [rcx]
0x18002e19e  lea     rdx, [rbp+var_40]
0x18002e1a2  mov     rax, [rax+48h]
0x18002e1a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e1ab  mov     rcx, [rdi+30h]
0x18002e1af  mov     rax, [rcx]
0x18002e1b2  lea     rdx, [rbp+wParam]
0x18002e1b6  mov     rax, [rax+58h]
0x18002e1ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e1bf  mov     [rbp+var_38], 0
0x18002e1c7  mov     rax, [rbp+wParam]
0x18002e1cb  mov     [rsp+80h+lParam], rax; unsigned __int16 *
0x18002e1d0  mov     r9, [rbp+var_40]; unsigned __int16 *
0x18002e1d4  lea     rdx, [rbp+var_38]; HWND *
0x18002e1d8  mov     rcx, [r14]; hDlg
0x18002e1db  call    ?CreateDeviceDataTip@@YAXPEAUHWND__@@PEAPEAU1@IPEBG2@Z; CreateDeviceDataTip(HWND__ *,HWND__ * *,uint,ushort const *,ushort const *)
0x18002e1e0  mov     r8, [rbp+pProps]
0x18002e1e4  mov     r8, [r8+18h]; lpString
0x18002e1e8  mov     edx, 3A9Bh; nIDDlgItem
0x18002e1ed  mov     rcx, [r14]; hDlg
0x18002e1f0  call    cs:__imp_SetDlgItemTextW
0x18002e1f6  mov     rcx, [rbp+pProps]; pProps
0x18002e1fa  call    NcFreeNetconProperties
0x18002e1ff  mov     rcx, [rbp+var_40]; pv
0x18002e203  call    cs:__imp_CoTaskMemFree
0x18002e209  mov     rcx, [rbp+wParam]; pv
0x18002e20d  call    cs:__imp_CoTaskMemFree
0x18002e213  mov     rcx, r15; hWnd
0x18002e216  call    cs:__imp_UpdateWindow
0x18002e21c  nop
0x18002e21d  mov     rcx, rbx; HICON
0x18002e220  call    ?EndWaitCursor@@YAXPEAUHICON__@@@Z; EndWaitCursor(HICON__ *)
0x18002e225  xor     eax, eax
0x18002e227  mov     rcx, [rbp+var_8]
0x18002e22b  xor     rcx, rsp; StackCookie
0x18002e22e  call    __security_check_cookie
0x18002e233  lea     r11, [rsp+80h+var_s0]
0x18002e23b  mov     rbx, [r11+38h]
0x18002e23f  mov     rsi, [r11+40h]
0x18002e243  mov     rsp, r11
0x18002e246  pop     r15
0x18002e248  pop     r14
0x18002e24a  pop     r12
0x18002e24c  pop     rdi
0x18002e24d  pop     rbp
0x18002e24e  retn
```
