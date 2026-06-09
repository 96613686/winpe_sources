# CLanNetNetworkBridgePage::OnApply(int,tagNMHDR *,int &)

- ea: `0x18002d4d8`
- end: `0x18002d8ff`
- name: `?OnApply@CLanNetNetworkBridgePage@@QEAA_JHPEAUtagNMHDR@@AEAH@Z`
- size: `1063`
- prototype: `__int64 __fastcall(CLanNetNetworkBridgePage *__hidden this, int, struct tagNMHDR *, int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002fe40`

## callees

- `0x180009930`
- `0x18001644c`
- `0x180018d74`
- `0x180019898`
- `0x18001e1e0`
- `0x18001eb7c`
- `0x18002d4d8`
- `0x18002d908`
- `0x18003ff7c`
- `0x180065010`

## import_xrefs

- `ntdll!WinSqmSetDWORD` at `0x18002d60a`
- `ntdll!WinSqmSetDWORD` at `0x18002d72b`
- `ntdll!WinSqmSetDWORD` at `0x18002d60a`
- `ntdll!WinSqmSetDWORD` at `0x18002d72b`
- `USER32!SendMessageW` at `0x18002d5e5`
- `USER32!SendMessageW` at `0x18002d62c`
- `USER32!SendMessageW` at `0x18002d5e5`
- `USER32!SendMessageW` at `0x18002d62c`
- `ole32!CoCreateInstance` at `0x18002d854`
- `ole32!CoCreateInstance` at `0x18002d854`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CLanNetNetworkBridgePage::OnApply(
        CLanNetNetworkBridgePage *this,
        __int64 a2,
        struct tagNMHDR *a3,
        int *a4)
{
  CLanNetNetworkBridgePage *v4; // r15
  int v5; // esi
  unsigned int v6; // r12d
  int v7; // edx
  struct tagNMHDR *v8; // r8
  int *v9; // r9
  HRESULT Instance; // edi
  unsigned int v11; // ebx
  int v12; // eax
  int v13; // r14d
  __int64 v14; // r8
  __int64 v15; // r13
  int v16; // r15d
  __int64 v17; // rax
  __int64 v18; // rbx
  struct IUnknown *v20; // [rsp+30h] [rbp-D0h] BYREF
  struct IUnknown *ppv; // [rsp+38h] [rbp-C8h] BYREF
  struct IUnknown *v22; // [rsp+40h] [rbp-C0h] BYREF
  struct IUnknown *v23; // [rsp+48h] [rbp-B8h] BYREF
  CLanNetNetworkBridgePage *v24; // [rsp+50h] [rbp-B0h] BYREF
  NETCON_PROPERTIES *pProps; // [rsp+58h] [rbp-A8h] BYREF
  struct IUnknown *v26; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD lParam[3]; // [rsp+70h] [rbp-90h] BYREF
  int v28; // [rsp+7Ch] [rbp-84h]
  int v29; // [rsp+80h] [rbp-80h]
  char *v30; // [rsp+88h] [rbp-78h]
  int v31; // [rsp+90h] [rbp-70h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  _QWORD v34[64]; // [rsp+D0h] [rbp-30h] BYREF
  char v35; // [rsp+2D0h] [rbp+1D0h] BYREF

  v4 = this;
  v24 = this;
  memset_0(v34, 0, 0x1F8u);
  v5 = 0;
  memset_0(lParam, 0, 0x58u);
  v30 = &v35;
  v6 = 255;
  v31 = 255;
  v29 = -1;
  lParam[0] = 15;
  v22 = 0;
  if ( (int)HrCreateInstanceBase(&CLSID_HNetCfgMgr, 3u, &GUID_85d18b6c_3032_11d4_9348_00c04f8eeb71, (void **)&v22) < 0 )
    goto LABEL_27;
  ppv = 0;
  v26 = 0;
  Instance = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, struct IUnknown **))v22->lpVtbl[1].QueryInterface)(
               v22,
               *((_QWORD *)v4 + 2),
               &ppv);
  if ( Instance < 0 )
    goto LABEL_26;
  Instance = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IUnknown **))ppv->lpVtbl[2].Release)(
               ppv,
               &IID_IHNetBridge,
               &v26);
  if ( Instance < 0 )
    goto LABEL_25;
  v11 = 0;
  v12 = SendMessageW(*((HWND *)v4 + 22), 0x1004u, 0, 0);
  v13 = v12;
  if ( v12 <= 255 )
  {
    if ( !v12 )
      goto LABEL_24;
    v14 = (unsigned int)v12;
  }
  else
  {
    v14 = 255;
  }
  WinSqmSetDWORD(0, 1887, v14);
  do
  {
    lParam[1] = --v13;
    if ( (unsigned int)SendMessageW(*((HWND *)v4 + 22), 0x104Bu, 0, (LPARAM)lParam) == 1 )
    {
      pProps = 0;
      v15 = v32;
      v16 = v28 & 0xF000;
      Instance = (*(__int64 (__fastcall **)(__int64, NETCON_PROPERTIES **))(*(_QWORD *)v32 + 56LL))(v32, &pProps);
      if ( Instance < 0 )
      {
LABEL_18:
        v4 = v24;
        continue;
      }
      v20 = 0;
      if ( v16 == 0x2000 )
      {
        if ( (pProps->dwCharacter & 0x200) != 0 )
        {
          ++v11;
          goto LABEL_17;
        }
        Instance = ((__int64 (__fastcall *)(struct IUnknown *, __int64, struct IUnknown **))v22->lpVtbl[1].QueryInterface)(
                     v22,
                     v15,
                     &v20);
        if ( Instance < 0 )
        {
LABEL_17:
          NcFreeNetconProperties(pProps);
          goto LABEL_18;
        }
        v23 = 0;
        Instance = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown *, struct IUnknown **, _QWORD))v26->lpVtbl[1].AddRef)(
                     v26,
                     v20,
                     &v23,
                     0);
        if ( Instance >= 0 )
        {
          ++v11;
          ReleaseObj(v23);
        }
      }
      else
      {
        if ( v16 != 12288 )
          goto LABEL_17;
        if ( (pProps->dwCharacter & 0x200) == 0 )
          goto LABEL_17;
        Instance = ((__int64 (__fastcall *)(struct IUnknown *, __int64, struct IUnknown **))v22->lpVtbl[1].QueryInterface)(
                     v22,
                     v15,
                     &v20);
        if ( Instance < 0 )
          goto LABEL_17;
        v23 = 0;
        Instance = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IUnknown **))v20->lpVtbl[2].Release)(
                     v20,
                     &IID_IHNetBridgedConnection,
                     &v23);
        if ( Instance >= 0 )
        {
          ((void (__fastcall *)(struct IUnknown *, _QWORD))v23->lpVtbl[1].AddRef)(v23, 0);
          if ( v5 < 63 )
          {
            v34[v5++] = v20;
            v20 = 0;
          }
          goto LABEL_17;
        }
      }
      ReleaseObj(v20);
      goto LABEL_17;
    }
    Instance = -2147467259;
  }
  while ( v13 );
  if ( v11 > 0xFF )
    goto LABEL_23;
  if ( v11 )
  {
    v6 = v11;
LABEL_23:
    WinSqmSetDWORD(0, 1886, v6);
  }
LABEL_24:
  ReleaseObj(v26);
LABEL_25:
  ReleaseObj(ppv);
LABEL_26:
  ReleaseObj(v22);
  if ( Instance >= 0 )
  {
LABEL_27:
    if ( CLanNetPage::OnApply(v4, v7, v8, v9) )
    {
      Instance = -2147467259;
    }
    else
    {
      ppv = 0;
      Instance = CoCreateInstance(&CLSID_ConnectionManager, 0, 0x415u, &IID_INetConnectionRefresh, (LPVOID *)&ppv);
      if ( Instance >= 0 )
      {
        ((void (__fastcall *)(struct IUnknown *))ppv->lpVtbl[1].QueryInterface)(ppv);
        ((void (__fastcall *)(struct IUnknown *))ppv->lpVtbl->Release)(ppv);
      }
    }
    while ( v5 > 0 && (unsigned int)v5 <= 0x3F )
    {
      v17 = (unsigned int)v5;
      v24 = 0;
      --v5;
      v18 = v34[v17 - 1];
      (*(void (__fastcall **)(__int64, CLanNetNetworkBridgePage **))(*(_QWORD *)v18 + 72LL))(v18, &v24);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>((__int64 *)&v24);
    }
  }
  *((_BYTE *)v4 + 145) = 0;
  return LresFromHr(Instance);
}

```

## disassembly

```asm
0x18002d4d8  push    rbp
0x18002d4da  push    rbx
0x18002d4db  push    rsi
0x18002d4dc  push    rdi
0x18002d4dd  push    r12
0x18002d4df  push    r13
0x18002d4e1  push    r14
0x18002d4e3  push    r15
0x18002d4e5  lea     rbp, [rsp-3E8h]
0x18002d4ed  sub     rsp, 4E8h
0x18002d4f4  mov     rax, cs:__security_cookie
0x18002d4fb  xor     rax, rsp
0x18002d4fe  mov     [rbp+420h+var_50], rax
0x18002d505  mov     r15, rcx
0x18002d508  mov     [rsp+520h+var_4D0], rcx
0x18002d50d  xor     edx, edx; Val
0x18002d50f  mov     r8d, 1F8h; Size
0x18002d515  lea     rcx, [rbp+420h+var_450]; void *
0x18002d519  call    memset_0
0x18002d51e  xor     esi, esi
0x18002d520  xor     edx, edx; Val
0x18002d522  lea     r8d, [rsi+58h]; Size
0x18002d526  lea     rcx, [rsp+520h+lParam]; void *
0x18002d52b  call    memset_0
0x18002d530  lea     rax, [rbp+420h+var_250]
0x18002d537  mov     [rbp+420h+var_498], rax
0x18002d53b  mov     r12d, 0FFh
0x18002d541  mov     [rbp+420h+var_490], r12d
0x18002d545  mov     [rbp+420h+var_4A0], 0FFFFFFFFh
0x18002d54c  mov     [rsp+520h+lParam], 0Fh
0x18002d554  mov     [rsp+520h+var_4E0], rsi
0x18002d559  lea     r9, [rsp+520h+var_4E0]; void **
0x18002d55e  lea     r8, _GUID_85d18b6c_3032_11d4_9348_00c04f8eeb71; struct _GUID *
0x18002d565  lea     edx, [rsi+3]; unsigned int
0x18002d568  lea     rcx, CLSID_HNetCfgMgr; struct _GUID *
0x18002d56f  call    ?HrCreateInstanceBase@@YAJAEBU_GUID@@K0PEAPEAX@Z; HrCreateInstanceBase(_GUID const &,ulong,_GUID const &,void * *)
0x18002d574  test    eax, eax
0x18002d576  js      loc_18002D757
0x18002d57c  mov     [rsp+520h+var_4E8], rsi
0x18002d581  mov     [rsp+520h+var_4C0], rsi
0x18002d586  mov     rcx, [rsp+520h+var_4E0]
0x18002d58b  mov     rax, [rcx]
0x18002d58e  lea     r8, [rsp+520h+var_4E8]
0x18002d593  mov     rdx, [r15+10h]
0x18002d597  mov     rax, [rax+18h]
0x18002d59b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d5a0  mov     edi, eax
0x18002d5a2  test    eax, eax
0x18002d5a4  js      loc_18002D745
0x18002d5aa  mov     rcx, [rsp+520h+var_4E8]
0x18002d5af  mov     rax, [rcx]
0x18002d5b2  lea     r8, [rsp+520h+var_4C0]
0x18002d5b7  lea     rdx, IID_IHNetBridge
0x18002d5be  mov     rax, [rax+40h]
0x18002d5c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d5c7  mov     edi, eax
0x18002d5c9  test    eax, eax
0x18002d5cb  js      loc_18002D73B
0x18002d5d1  xor     ebx, ebx
0x18002d5d3  xor     r9d, r9d; lParam
0x18002d5d6  xor     r8d, r8d; wParam
0x18002d5d9  mov     edx, 1004h; Msg
0x18002d5de  mov     rcx, [r15+0B0h]; hWnd
0x18002d5e5  call    cs:__imp_SendMessageW
0x18002d5eb  mov     r14, rax
0x18002d5ee  cmp     eax, r12d
0x18002d5f1  jle     short loc_18002D5F8
0x18002d5f3  mov     r8d, r12d
0x18002d5f6  jmp     short loc_18002D603
0x18002d5f8  test    eax, eax
0x18002d5fa  jz      loc_18002D731
0x18002d600  mov     r8d, eax
0x18002d603  mov     edx, 75Fh
0x18002d608  xor     ecx, ecx
0x18002d60a  call    cs:__imp_WinSqmSetDWORD
0x18002d610  dec     r14d
0x18002d613  mov     [rsp+520h+lParam+4], r14d
0x18002d618  lea     r9, [rsp+520h+lParam]; lParam
0x18002d61d  xor     r8d, r8d; wParam
0x18002d620  mov     edx, 104Bh; Msg
0x18002d625  mov     rcx, [r15+0B0h]; hWnd
0x18002d62c  call    cs:__imp_SendMessageW
0x18002d632  cmp     eax, 1
0x18002d635  jnz     loc_18002D821
0x18002d63b  mov     [rsp+520h+pProps], 0
0x18002d644  mov     r13, [rbp+420h+var_488]
0x18002d648  mov     r15d, [rsp+520h+var_4A4]
0x18002d64d  and     r15d, 0F000h
0x18002d654  mov     rax, [r13+0]
0x18002d658  lea     rdx, [rsp+520h+pProps]
0x18002d65d  mov     rcx, r13
0x18002d660  mov     rax, [rax+38h]
0x18002d664  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d669  mov     edi, eax
0x18002d66b  test    eax, eax
0x18002d66d  js      loc_18002D707
0x18002d673  mov     [rsp+520h+var_4F0], 0
0x18002d67c  cmp     r15d, 2000h
0x18002d683  jnz     loc_18002D776
0x18002d689  mov     rax, [rsp+520h+pProps]
0x18002d68e  test    dword ptr [rax+28h], 200h
0x18002d695  jnz     loc_18002D772
0x18002d69b  mov     rcx, [rsp+520h+var_4E0]
0x18002d6a0  mov     rax, [rcx]
0x18002d6a3  lea     r8, [rsp+520h+var_4F0]
0x18002d6a8  mov     rdx, r13
0x18002d6ab  mov     rax, [rax+18h]
0x18002d6af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d6b4  mov     edi, eax
0x18002d6b6  test    eax, eax
0x18002d6b8  js      short loc_18002D6FD
0x18002d6ba  mov     [rsp+520h+var_4D8], 0
0x18002d6c3  mov     rcx, [rsp+520h+var_4C0]
0x18002d6c8  mov     rax, [rcx]
0x18002d6cb  xor     r9d, r9d
0x18002d6ce  lea     r8, [rsp+520h+var_4D8]
0x18002d6d3  mov     rdx, [rsp+520h+var_4F0]
0x18002d6d8  mov     rax, [rax+20h]
0x18002d6dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d6e1  mov     edi, eax
0x18002d6e3  test    eax, eax
0x18002d6e5  js      short loc_18002D6F3
0x18002d6e7  inc     ebx
0x18002d6e9  mov     rcx, [rsp+520h+var_4D8]; struct IUnknown *
0x18002d6ee  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x18002d6f3  mov     rcx, [rsp+520h+var_4F0]; struct IUnknown *
0x18002d6f8  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x18002d6fd  mov     rcx, [rsp+520h+pProps]; pProps
0x18002d702  call    NcFreeNetconProperties
0x18002d707  mov     r15, [rsp+520h+var_4D0]
0x18002d70c  test    r14d, r14d
0x18002d70f  jnz     loc_18002D610
0x18002d715  cmp     ebx, r12d
0x18002d718  ja      short loc_18002D721
0x18002d71a  test    ebx, ebx
0x18002d71c  jz      short loc_18002D731
0x18002d71e  mov     r12d, ebx
0x18002d721  mov     r8d, r12d
0x18002d724  mov     edx, 75Eh
0x18002d729  xor     ecx, ecx
0x18002d72b  call    cs:__imp_WinSqmSetDWORD
0x18002d731  mov     rcx, [rsp+520h+var_4C0]; struct IUnknown *
0x18002d736  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x18002d73b  mov     rcx, [rsp+520h+var_4E8]; struct IUnknown *
0x18002d740  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x18002d745  mov     rcx, [rsp+520h+var_4E0]; struct IUnknown *
0x18002d74a  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x18002d74f  test    edi, edi
0x18002d751  js      loc_18002D8CD
0x18002d757  mov     rcx, r15; this
0x18002d75a  call    ?OnApply@CLanNetPage@@QEAA_JHPEAUtagNMHDR@@AEAH@Z; CLanNetPage::OnApply(int,tagNMHDR *,int &)
0x18002d75f  test    rax, rax
0x18002d762  jz      loc_18002D82B
0x18002d768  mov     edi, 80004005h
0x18002d76d  jmp     loc_18002D8C9
0x18002d772  inc     ebx
0x18002d774  jmp     short loc_18002D6FD
0x18002d776  cmp     r15d, 3000h
0x18002d77d  jnz     loc_18002D6FD
0x18002d783  mov     rax, [rsp+520h+pProps]
0x18002d788  test    dword ptr [rax+28h], 200h
0x18002d78f  jz      loc_18002D6FD
0x18002d795  mov     rcx, [rsp+520h+var_4E0]
0x18002d79a  mov     rax, [rcx]
0x18002d79d  lea     r8, [rsp+520h+var_4F0]
0x18002d7a2  mov     rdx, r13
0x18002d7a5  mov     rax, [rax+18h]
0x18002d7a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d7ae  mov     edi, eax
0x18002d7b0  test    eax, eax
0x18002d7b2  js      loc_18002D6FD
0x18002d7b8  mov     [rsp+520h+var_4D8], 0
0x18002d7c1  mov     rcx, [rsp+520h+var_4F0]
0x18002d7c6  mov     rax, [rcx]
0x18002d7c9  lea     r8, [rsp+520h+var_4D8]
0x18002d7ce  lea     rdx, IID_IHNetBridgedConnection
0x18002d7d5  mov     rax, [rax+40h]
0x18002d7d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d7de  mov     edi, eax
0x18002d7e0  test    eax, eax
0x18002d7e2  js      loc_18002D6F3
0x18002d7e8  mov     rcx, [rsp+520h+var_4D8]
0x18002d7ed  mov     rax, [rcx]
0x18002d7f0  xor     edx, edx
0x18002d7f2  mov     rax, [rax+20h]
0x18002d7f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d7fb  cmp     esi, 3Fh ; '?'
0x18002d7fe  jge     loc_18002D6FD
0x18002d804  movsxd  rcx, esi
0x18002d807  mov     rax, [rsp+520h+var_4F0]
0x18002d80c  mov     [rbp+rcx*8+420h+var_450], rax
0x18002d811  inc     esi
0x18002d813  mov     [rsp+520h+var_4F0], 0
0x18002d81c  jmp     loc_18002D6FD
0x18002d821  mov     edi, 80004005h
0x18002d826  jmp     loc_18002D70C
0x18002d82b  mov     [rsp+520h+var_4E8], 0
0x18002d834  lea     rax, [rsp+520h+var_4E8]
0x18002d839  mov     [rsp+520h+ppv], rax; ppv
0x18002d83e  lea     r9, IID_INetConnectionRefresh; riid
0x18002d845  xor     edx, edx; pUnkOuter
0x18002d847  mov     r8d, 415h; dwClsContext
0x18002d84d  lea     rcx, CLSID_ConnectionManager; rclsid
0x18002d854  call    cs:__imp_CoCreateInstance
0x18002d85a  mov     edi, eax
0x18002d85c  test    eax, eax
0x18002d85e  js      short loc_18002D8C9
0x18002d860  mov     rcx, [rsp+520h+var_4E8]
0x18002d865  mov     rdx, [rcx]
0x18002d868  mov     rax, [rdx+18h]
0x18002d86c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d871  mov     rcx, [rsp+520h+var_4E8]
0x18002d876  mov     rdx, [rcx]
0x18002d879  mov     rax, [rdx+10h]
0x18002d87d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d882  jmp     short loc_18002D8C9
0x18002d884  cmp     esi, 3Fh ; '?'
0x18002d887  ja      short loc_18002D8CD
0x18002d889  mov     eax, esi
0x18002d88b  mov     [rsp+520h+var_4D0], 0
0x18002d894  dec     esi
0x18002d896  mov     rbx, [rbp+rax*8+420h+var_458]
0x18002d89b  mov     rax, [rbx]
0x18002d89e  lea     rdx, [rsp+520h+var_4D0]
0x18002d8a3  mov     rcx, rbx
0x18002d8a6  mov     rax, [rax+48h]
0x18002d8aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d8af  mov     rax, [rbx]
0x18002d8b2  mov     rcx, rbx
0x18002d8b5  mov     rax, [rax+10h]
0x18002d8b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d8be  nop
0x18002d8bf  lea     rcx, [rsp+520h+var_4D0]
0x18002d8c4  call    ??1?$CComPtrBase@UIUPnPService@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>(void)
0x18002d8c9  test    esi, esi
0x18002d8cb  jg      short loc_18002D884
0x18002d8cd  mov     byte ptr [r15+91h], 0
0x18002d8d5  mov     ecx, edi; int
0x18002d8d7  call    ?LresFromHr@@YA_JJ@Z; LresFromHr(long)
0x18002d8dc  mov     rcx, [rbp+420h+var_50]
0x18002d8e3  xor     rcx, rsp; StackCookie
0x18002d8e6  call    __security_check_cookie
0x18002d8eb  add     rsp, 4E8h
0x18002d8f2  pop     r15
0x18002d8f4  pop     r14
0x18002d8f6  pop     r13
0x18002d8f8  pop     r12
0x18002d8fa  pop     rdi
0x18002d8fb  pop     rsi
0x18002d8fc  pop     rbx
0x18002d8fd  pop     rbp
0x18002d8fe  retn
```
