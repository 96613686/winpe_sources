# CLanAdvancedPage::OnKillActive(int,tagNMHDR *,int &)

- ea: `0x18002f0d8`
- end: `0x18002f489`
- name: `?OnKillActive@CLanAdvancedPage@@QEAA_JHPEAUtagNMHDR@@AEAH@Z`
- size: `945`
- prototype: `__int64 __fastcall(CLanAdvancedPage *__hidden this, int, struct tagNMHDR *, int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18002fc20`

## callees

- `0x180002010`
- `0x180009140`
- `0x18001644c`
- `0x180017714`
- `0x180019898`
- `0x18001bc10`
- `0x18001e1e0`
- `0x18001eb7c`
- `0x18002ca9c`
- `0x18002f0d8`
- `0x180065010`

## import_xrefs

- `USER32!SetWindowLongW` at `0x18002f1c9`
- `USER32!SetWindowLongW` at `0x18002f1c9`
- `USER32!SendMessageW` at `0x18002f170`
- `USER32!SendMessageW` at `0x18002f189`
- `USER32!SendMessageW` at `0x18002f170`
- `USER32!SendMessageW` at `0x18002f189`
- `USER32!IsDlgButtonChecked` at `0x18002f119`
- `USER32!IsDlgButtonChecked` at `0x18002f119`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18002f369`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18002f39e`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18002f369`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18002f39e`
- `ole32!CoTaskMemFree` at `0x18002f402`
- `ole32!CoTaskMemFree` at `0x18002f402`
- `WS2_32!WSAAddressToStringW` at `0x18002f2ee`
- `WS2_32!WSAAddressToStringW` at `0x18002f342`
- `WS2_32!WSAAddressToStringW` at `0x18002f2ee`
- `WS2_32!WSAAddressToStringW` at `0x18002f342`
- `WS2_32!__imp_WSAGetLastError` at `0x18002f2f4`
- `WS2_32!__imp_WSAGetLastError` at `0x18002f2f4`
- `WS2_32!__imp_WSAStartup` at `0x18002f31b`
- `WS2_32!__imp_WSAStartup` at `0x18002f31b`
- `WS2_32!__imp_WSACleanup` at `0x18002f348`
- `WS2_32!__imp_WSACleanup` at `0x18002f348`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CLanAdvancedPage::OnKillActive(CLanAdvancedPage *this, __int64 a2, struct tagNMHDR *a3, int *a4)
{
  HWND *v5; // r14
  CLanAdvancedPage *v6; // rcx
  HWND v7; // rdi
  int v8; // eax
  struct IHNetConnection *v9; // rsi
  int v11; // edi
  int v12; // ebx
  IP_ADAPTER_ADDRESSES_LH *v13; // rbx
  ULONG AdaptersAddresses; // eax
  int v15; // edi
  IP_ADAPTER_ADDRESSES_LH *i; // rcx
  PWCHAR FriendlyName; // rax
  char *v18; // r8
  int v19; // r9d
  int v20; // edx
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  ULONG SizePointer; // [rsp+38h] [rbp-C8h] BYREF
  int v23; // [rsp+3Ch] [rbp-C4h] BYREF
  DWORD dwAddressStringLength; // [rsp+40h] [rbp-C0h] BYREF
  int v25; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v26; // [rsp+48h] [rbp-B8h] BYREF
  sockaddr saAddress; // [rsp+50h] [rbp-B0h] BYREF
  WSAData WSAData; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR szAddressString[16]; // [rsp+270h] [rbp+170h] BYREF

  v5 = (HWND *)((char *)this + 8);
  if ( IsDlgButtonChecked(*((HWND *)this + 1), 105)
    && (!*((_DWORD *)this + 8) || *((_DWORD *)this + 14) && *((_DWORD *)this + 19)) )
  {
    if ( *((_DWORD *)this + 19) <= 1u )
    {
      v9 = (struct IHNetConnection *)**((_QWORD **)this + 8);
    }
    else
    {
      v7 = *(HWND *)ATL::CWindow::GetDlgItem(v5, &pv, 107);
      v8 = SendMessageW(v7, 0x147u, 0, 0);
      if ( v8 == -1 )
      {
LABEL_10:
        NcMsgBox(hInst, *v5, 0x3E90u, 0x3EC9u, 0x30u);
LABEL_11:
        SetWindowLongW(*v5, 0, 1);
        return 1;
      }
      v9 = (struct IHNetConnection *)SendMessageW(v7, 0x150u, v8, 0);
    }
    if ( !v9 )
      goto LABEL_10;
    if ( !*((_DWORD *)this + 10) && !(unsigned int)CLanAdvancedPage::IsAdapterDHCPEnabled(v6, v9) )
    {
      v11 = 0;
      memset(szAddressString, 0, sizeof(szAddressString));
      memset_0(&saAddress, 0, 0x80u);
      dwAddressStringLength = 16;
      pv = 0;
      v26 = 0;
      v23 = 0;
      v25 = 0;
      v12 = HrCreateInstanceBase(&CLSID_HNetCfgMgr, 3u, &GUID_85d18b6c_3032_11d4_9348_00c04f8eeb71, &pv);
      if ( v12 >= 0 )
      {
        v12 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))pv)(pv, &IID_IHNetIcsSettings, &v26);
        if ( v12 >= 0 )
        {
          v12 = (*(__int64 (__fastcall **)(__int64, int *, int *))(*(_QWORD *)v26 + 88LL))(v26, &v23, &v25);
          if ( v12 >= 0 )
            v11 = v23;
        }
      }
      ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>(&v26);
      ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>((__int64 *)&pv);
      if ( v12 >= 0 )
      {
        *(_DWORD *)&saAddress.sa_family = 2;
        *(_DWORD *)&saAddress.sa_data[2] = v11;
        *(_QWORD *)&saAddress.sa_data[6] = 0;
        WSAAddressToStringW(&saAddress, 0x80u, 0, szAddressString, &dwAddressStringLength);
        if ( WSAGetLastError() == 10093 )
        {
          memset_0(&WSAData, 0, sizeof(WSAData));
          if ( !WSAStartup(0x202u, &WSAData) )
          {
            WSAAddressToStringW(&saAddress, 0x80u, 0, szAddressString, &dwAddressStringLength);
            WSACleanup();
          }
        }
      }
      v13 = 0;
      SizePointer = 0;
      AdaptersAddresses = GetAdaptersAddresses(2u, 0, 0, 0, &SizePointer);
      if ( AdaptersAddresses == 111 )
      {
        v13 = (IP_ADAPTER_ADDRESSES_LH *)MemAlloc(SizePointer);
        if ( !v13 )
          goto LABEL_37;
        AdaptersAddresses = GetAdaptersAddresses(2u, 0, 0, v13, &SizePointer);
      }
      v15 = 0;
      if ( AdaptersAddresses )
      {
        if ( AdaptersAddresses == 232 )
          goto LABEL_38;
      }
      else
      {
        pv = 0;
        if ( (*(int (__fastcall **)(struct IHNetConnection *, LPVOID *))(*(_QWORD *)v9 + 40LL))(v9, &pv) >= 0 )
        {
          for ( i = v13; i; i = i->Next )
          {
            FriendlyName = i->FriendlyName;
            v18 = (char *)((_BYTE *)pv - (_BYTE *)FriendlyName);
            do
            {
              v19 = *(unsigned __int16 *)&v18[(_QWORD)FriendlyName];
              v20 = *FriendlyName - v19;
              if ( v20 )
                break;
              ++FriendlyName;
            }
            while ( v19 );
            if ( !v20 )
            {
              v15 = 1;
              break;
            }
          }
          CoTaskMemFree(pv);
LABEL_38:
          if ( v13 )
            MemFree(v13);
          if ( v15 == 1 && (unsigned int)NcMsgBox(hInst, *v5, 0x3E90u, 0x3EA1u, 0x44u, szAddressString) == 7 )
            goto LABEL_11;
          return 0;
        }
      }
LABEL_37:
      v15 = 1;
      goto LABEL_38;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18002f0d8  mov     [rsp-8+arg_8], rbx
0x18002f0dd  mov     [rsp-8+arg_10], rsi
0x18002f0e2  push    rbp
0x18002f0e3  push    rdi
0x18002f0e4  push    r12
0x18002f0e6  push    r13
0x18002f0e8  push    r14
0x18002f0ea  lea     rbp, [rsp-1A0h]
0x18002f0f2  sub     rsp, 2A0h
0x18002f0f9  mov     rax, cs:__security_cookie
0x18002f100  xor     rax, rsp
0x18002f103  mov     [rbp+1C0h+var_30], rax
0x18002f10a  mov     rbx, rcx
0x18002f10d  lea     r14, [rcx+8]
0x18002f111  mov     edx, 69h ; 'i'; nIDButton
0x18002f116  mov     rcx, [r14]; hDlg
0x18002f119  call    cs:__imp_IsDlgButtonChecked
0x18002f11f  test    eax, eax
0x18002f121  jz      loc_18002F45C
0x18002f127  cmp     dword ptr [rbx+20h], 0
0x18002f12b  jz      short loc_18002F141
0x18002f12d  cmp     dword ptr [rbx+38h], 0
0x18002f131  jz      loc_18002F45C
0x18002f137  cmp     dword ptr [rbx+4Ch], 0
0x18002f13b  jz      loc_18002F45C
0x18002f141  mov     r12d, 1
0x18002f147  cmp     [rbx+4Ch], r12d
0x18002f14b  jbe     short loc_18002F194
0x18002f14d  lea     r8d, [r12+6Ah]
0x18002f152  lea     rdx, [rsp+2C0h+pv]
0x18002f157  mov     rcx, r14
0x18002f15a  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x18002f15f  mov     rdi, [rax]
0x18002f162  xor     r9d, r9d; lParam
0x18002f165  xor     r8d, r8d; wParam
0x18002f168  mov     edx, 147h; Msg
0x18002f16d  mov     rcx, rdi; hWnd
0x18002f170  call    cs:__imp_SendMessageW
0x18002f176  cmp     eax, 0FFFFFFFFh
0x18002f179  jz      short loc_18002F1A0
0x18002f17b  movsxd  r8, eax; wParam
0x18002f17e  xor     r9d, r9d; lParam
0x18002f181  mov     edx, 150h; Msg
0x18002f186  mov     rcx, rdi; hWnd
0x18002f189  call    cs:__imp_SendMessageW
0x18002f18f  mov     rsi, rax
0x18002f192  jmp     short loc_18002F19B
0x18002f194  mov     rax, [rbx+40h]
0x18002f198  mov     rsi, [rax]
0x18002f19b  test    rsi, rsi
0x18002f19e  jnz     short loc_18002F1D7
0x18002f1a0  mov     dword ptr [rsp+2C0h+lpdwAddressStringLength], 30h ; '0'; uType
0x18002f1a8  mov     r9d, 3EC9h; unsigned int
0x18002f1ae  lea     r8d, [r9-39h]; unsigned int
0x18002f1b2  mov     rdx, [r14]; hWnd
0x18002f1b5  mov     rcx, cs:hInst; hModule
0x18002f1bc  call    ?NcMsgBox@@YAHPEAUHINSTANCE__@@PEAUHWND__@@IIIZZ; NcMsgBox(HINSTANCE__ *,HWND__ *,uint,uint,uint,...)
0x18002f1c1  mov     r8d, r12d; dwNewLong
0x18002f1c4  xor     edx, edx; nIndex
0x18002f1c6  mov     rcx, [r14]; hWnd
0x18002f1c9  call    cs:__imp_SetWindowLongW
0x18002f1cf  mov     rax, r12
0x18002f1d2  jmp     loc_18002F45E
0x18002f1d7  cmp     dword ptr [rbx+28h], 0
0x18002f1db  jnz     loc_18002F45C
0x18002f1e1  mov     rdx, rsi; struct IHNetConnection *
0x18002f1e4  call    ?IsAdapterDHCPEnabled@CLanAdvancedPage@@AEAAHPEAUIHNetConnection@@@Z; CLanAdvancedPage::IsAdapterDHCPEnabled(IHNetConnection *)
0x18002f1e9  test    eax, eax
0x18002f1eb  jnz     loc_18002F45C
0x18002f1f1  xor     edi, edi
0x18002f1f3  mov     [rbp+1C0h+szAddressString], ax
0x18002f1fa  xorps   xmm0, xmm0
0x18002f1fd  movups  xmmword ptr [rbp+1C0h+var_4E], xmm0
0x18002f204  movups  xmmword ptr [rbp+1C0h+var_4E+0Eh], xmm0
0x18002f20b  xor     edx, edx; Val
0x18002f20d  mov     r8d, 80h; Size
0x18002f213  lea     rcx, [rsp+2C0h+saAddress]; void *
0x18002f218  call    memset_0
0x18002f21d  mov     [rsp+2C0h+dwAddressStringLength], 10h
0x18002f225  mov     [rsp+2C0h+pv], rdi
0x18002f22a  mov     [rsp+2C0h+var_278], rdi
0x18002f22f  mov     [rsp+2C0h+var_284], edi
0x18002f233  mov     [rsp+2C0h+var_27C], edi
0x18002f237  lea     r9, [rsp+2C0h+pv]; void **
0x18002f23c  lea     r8, _GUID_85d18b6c_3032_11d4_9348_00c04f8eeb71; struct _GUID *
0x18002f243  lea     edx, [rdi+3]; unsigned int
0x18002f246  lea     rcx, CLSID_HNetCfgMgr; struct _GUID *
0x18002f24d  call    ?HrCreateInstanceBase@@YAJAEBU_GUID@@K0PEAPEAX@Z; HrCreateInstanceBase(_GUID const &,ulong,_GUID const &,void * *)
0x18002f252  mov     ebx, eax
0x18002f254  test    eax, eax
0x18002f256  js      short loc_18002F29E
0x18002f258  mov     rcx, [rsp+2C0h+pv]
0x18002f25d  mov     rax, [rcx]
0x18002f260  lea     r8, [rsp+2C0h+var_278]
0x18002f265  lea     rdx, IID_IHNetIcsSettings
0x18002f26c  mov     rax, [rax]
0x18002f26f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f274  mov     ebx, eax
0x18002f276  test    eax, eax
0x18002f278  js      short loc_18002F29E
0x18002f27a  mov     rcx, [rsp+2C0h+var_278]
0x18002f27f  mov     rax, [rcx]
0x18002f282  lea     r8, [rsp+2C0h+var_27C]
0x18002f287  lea     rdx, [rsp+2C0h+var_284]
0x18002f28c  mov     rax, [rax+58h]
0x18002f290  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f295  mov     ebx, eax
0x18002f297  test    eax, eax
0x18002f299  cmovns  edi, [rsp+2C0h+var_284]
0x18002f29e  lea     rcx, [rsp+2C0h+var_278]
0x18002f2a3  call    ??1?$CComPtrBase@UIUPnPService@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>(void)
0x18002f2a8  nop
0x18002f2a9  lea     rcx, [rsp+2C0h+pv]
0x18002f2ae  call    ??1?$CComPtrBase@UIUPnPService@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>(void)
0x18002f2b3  mov     r13d, 2
0x18002f2b9  test    ebx, ebx
0x18002f2bb  js      loc_18002F34E
0x18002f2c1  mov     dword ptr [rsp+2C0h+saAddress.sa_family], r13d
0x18002f2c6  mov     dword ptr [rsp+2C0h+saAddress.sa_data+2], edi
0x18002f2ca  xor     eax, eax
0x18002f2cc  mov     qword ptr [rsp+2C0h+saAddress.sa_data+6], rax
0x18002f2d1  lea     rax, [rsp+2C0h+dwAddressStringLength]
0x18002f2d6  mov     [rsp+2C0h+lpdwAddressStringLength], rax; lpdwAddressStringLength
0x18002f2db  lea     r9, [rbp+1C0h+szAddressString]; lpszAddressString
0x18002f2e2  xor     r8d, r8d; lpProtocolInfo
0x18002f2e5  lea     edx, [r13+7Eh]; dwAddressLength
0x18002f2e9  lea     rcx, [rsp+2C0h+saAddress]; lpsaAddress
0x18002f2ee  call    cs:__imp_WSAAddressToStringW
0x18002f2f4  call    cs:__imp_WSAGetLastError
0x18002f2fa  cmp     eax, 276Dh
0x18002f2ff  jnz     short loc_18002F34E
0x18002f301  xor     edx, edx; Val
0x18002f303  mov     r8d, 198h; Size
0x18002f309  lea     rcx, [rbp+1C0h+WSAData]; void *
0x18002f30d  call    memset_0
0x18002f312  mov     ecx, 202h; wVersionRequested
0x18002f317  lea     rdx, [rbp+1C0h+WSAData]; lpWSAData
0x18002f31b  call    cs:__imp_WSAStartup
0x18002f321  test    eax, eax
0x18002f323  jnz     short loc_18002F34E
0x18002f325  lea     rax, [rsp+2C0h+dwAddressStringLength]
0x18002f32a  mov     [rsp+2C0h+lpdwAddressStringLength], rax; lpdwAddressStringLength
0x18002f32f  lea     r9, [rbp+1C0h+szAddressString]; lpszAddressString
0x18002f336  xor     r8d, r8d; lpProtocolInfo
0x18002f339  lea     edx, [r13+7Eh]; dwAddressLength
0x18002f33d  lea     rcx, [rsp+2C0h+saAddress]; lpsaAddress
0x18002f342  call    cs:__imp_WSAAddressToStringW
0x18002f348  call    cs:__imp_WSACleanup
0x18002f34e  xor     ebx, ebx
0x18002f350  mov     [rsp+2C0h+SizePointer], ebx
0x18002f354  lea     rax, [rsp+2C0h+SizePointer]
0x18002f359  mov     [rsp+2C0h+lpdwAddressStringLength], rax; SizePointer
0x18002f35e  xor     r9d, r9d; AdapterAddresses
0x18002f361  xor     r8d, r8d; Reserved
0x18002f364  xor     edx, edx; Flags
0x18002f366  mov     ecx, r13d; Family
0x18002f369  call    cs:__imp_GetAdaptersAddresses
0x18002f36f  cmp     eax, 6Fh ; 'o'
0x18002f372  jnz     short loc_18002F3A4
0x18002f374  mov     ecx, [rsp+2C0h+SizePointer]; unsigned __int64
0x18002f378  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x18002f37d  mov     rbx, rax
0x18002f380  test    rax, rax
0x18002f383  jz      loc_18002F411
0x18002f389  lea     rax, [rsp+2C0h+SizePointer]
0x18002f38e  mov     [rsp+2C0h+lpdwAddressStringLength], rax; SizePointer
0x18002f393  mov     r9, rbx; AdapterAddresses
0x18002f396  xor     r8d, r8d; Reserved
0x18002f399  xor     edx, edx; Flags
0x18002f39b  mov     ecx, r13d; Family
0x18002f39e  call    cs:__imp_GetAdaptersAddresses
0x18002f3a4  xor     edi, edi
0x18002f3a6  test    eax, eax
0x18002f3a8  jnz     short loc_18002F40A
0x18002f3aa  mov     [rsp+2C0h+pv], rdi
0x18002f3af  mov     rax, [rsi]
0x18002f3b2  lea     rdx, [rsp+2C0h+pv]
0x18002f3b7  mov     rcx, rsi
0x18002f3ba  mov     rax, [rax+28h]
0x18002f3be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f3c3  test    eax, eax
0x18002f3c5  js      short loc_18002F411
0x18002f3c7  mov     rcx, rbx
0x18002f3ca  test    rcx, rcx
0x18002f3cd  jz      short loc_18002F3FD
0x18002f3cf  mov     rax, [rcx+48h]
0x18002f3d3  mov     r8, [rsp+2C0h+pv]
0x18002f3d8  sub     r8, rax
0x18002f3db  movzx   edx, word ptr [rax]
0x18002f3de  movzx   r9d, word ptr [rax+r8]
0x18002f3e3  sub     edx, r9d
0x18002f3e6  jnz     short loc_18002F3F0
0x18002f3e8  add     rax, r13
0x18002f3eb  test    r9d, r9d
0x18002f3ee  jnz     short loc_18002F3DB
0x18002f3f0  test    edx, edx
0x18002f3f2  jz      short loc_18002F3FA
0x18002f3f4  mov     rcx, [rcx+8]
0x18002f3f8  jmp     short loc_18002F3CA
0x18002f3fa  mov     edi, r12d
0x18002f3fd  mov     rcx, [rsp+2C0h+pv]; pv
0x18002f402  call    cs:__imp_CoTaskMemFree
0x18002f408  jmp     short loc_18002F414
0x18002f40a  cmp     eax, 0E8h
0x18002f40f  jz      short loc_18002F414
0x18002f411  mov     edi, r12d
0x18002f414  test    rbx, rbx
0x18002f417  jz      short loc_18002F421
0x18002f419  mov     rcx, rbx; lpMem
0x18002f41c  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18002f421  cmp     edi, r12d
0x18002f424  jnz     short loc_18002F45C
0x18002f426  lea     rax, [rbp+1C0h+szAddressString]
0x18002f42d  mov     [rsp+2C0h+var_298], rax
0x18002f432  mov     dword ptr [rsp+2C0h+lpdwAddressStringLength], 44h ; 'D'; uType
0x18002f43a  mov     r9d, 3EA1h; unsigned int
0x18002f440  lea     r8d, [r9-11h]; unsigned int
0x18002f444  mov     rdx, [r14]; hWnd
0x18002f447  mov     rcx, cs:hInst; hModule
0x18002f44e  call    ?NcMsgBox@@YAHPEAUHINSTANCE__@@PEAUHWND__@@IIIZZ; NcMsgBox(HINSTANCE__ *,HWND__ *,uint,uint,uint,...)
0x18002f453  cmp     eax, 7
0x18002f456  jz      loc_18002F1C1
0x18002f45c  xor     eax, eax
0x18002f45e  mov     rcx, [rbp+1C0h+var_30]
0x18002f465  xor     rcx, rsp; StackCookie
0x18002f468  call    __security_check_cookie
0x18002f46d  lea     r11, [rsp+2C0h+var_20]
0x18002f475  mov     rbx, [r11+38h]
0x18002f479  mov     rsi, [r11+40h]
0x18002f47d  mov     rsp, r11
0x18002f480  pop     r14
0x18002f482  pop     r13
0x18002f484  pop     r12
0x18002f486  pop     rdi
0x18002f487  pop     rbp
0x18002f488  retn
```
