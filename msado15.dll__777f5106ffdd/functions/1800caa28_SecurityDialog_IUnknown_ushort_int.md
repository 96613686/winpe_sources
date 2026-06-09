# SecurityDialog(IUnknown *,ushort *,int)

- ea: `0x1800caa28`
- end: `0x1800cae69`
- name: `?SecurityDialog@@YAJPEAUIUnknown@@PEAGH@Z`
- size: `1089`
- prototype: `__int64 __fastcall(struct IUnknown *, unsigned __int16 *, int)`
- caller_count: `7`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180032ac0`
- `0x180046bc8`
- `0x18005dc90`
- `0x18006ef20`
- `0x1800ad8b4`
- `0x1800bdc30`
- `0x1800c0750`

## callees

- `0x180001514`
- `0x1800c8f34`
- `0x1800ca578`
- `0x1800caa28`
- `0x1800cdb20`
- `0x1800cdbe0`
- `0x1800d0010`

## import_xrefs

- `USER32!MessageBoxW` at `0x1800cadea`
- `USER32!MessageBoxW` at `0x1800cadea`
- `USER32!LoadStringW` at `0x1800cada3`
- `USER32!LoadStringW` at `0x1800cadc7`
- `USER32!LoadStringW` at `0x1800cada3`
- `USER32!LoadStringW` at `0x1800cadc7`
- `USER32!GetActiveWindow` at `0x1800cad3c`
- `USER32!GetActiveWindow` at `0x1800cad3c`
- `ole32!CoCreateInstance` at `0x1800caac3`
- `ole32!CoCreateInstance` at `0x1800cab65`
- `ole32!CoCreateInstance` at `0x1800caac3`
- `ole32!CoCreateInstance` at `0x1800cab65`

## string_xrefs

- `0x1800caaef`: `<SecurityDialog|ADO|ERR> 0x%08x{HRESULT} line %d\n`
- `0x1800cad65`: `<SecurityDialog|ADO|ERR>  line %d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SecurityDialog(struct IUnknown *a1, unsigned __int16 *a2, int a3)
{
  HRESULT v6; // eax
  int v7; // ebx
  __int64 v8; // rdx
  bool v9; // zf
  int v10; // eax
  LPVOID *ppv; // [rsp+20h] [rbp-E0h]
  int v13; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v14; // [rsp+44h] [rbp-BCh] BYREF
  LPVOID v15; // [rsp+48h] [rbp-B8h] BYREF
  HWND hWnd; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID v17; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v18; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v19; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Caption[1032]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Buffer[1032]; // [rsp+880h] [rbp+780h] BYREF

  v17 = 0;
  v15 = 0;
  v14 = 0;
  v13 = 0;
  v19 = 0;
  v18 = 0;
  hWnd = 0;
  v6 = CoCreateInstance(&CLSID_InternetSecurityManager, 0, 1u, &IID_IInternetSecurityManager, &v17);
  v7 = v6;
  if ( v6 < 0 )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_44;
    LODWORD(ppv) = 3394;
    v8 = 3475465;
    goto LABEL_4;
  }
  v6 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 *, unsigned int *, _QWORD))(*(_QWORD *)v17 + 40LL))(
         v17,
         a2,
         &v14,
         0);
  v7 = v6;
  if ( v6 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      LODWORD(ppv) = 3397;
      v8 = 3478537;
LABEL_4:
      bidTraceW(off_18012A218[0], v8, L"<SecurityDialog|ADO|ERR> 0x%08x{HRESULT} line %d\n", (unsigned int)v6, ppv);
      goto LABEL_44;
    }
    goto LABEL_44;
  }
  v6 = CoCreateInstance(&CLSID_InternetZoneManager, 0, 1u, &IID_IInternetZoneManager, &v15);
  v7 = v6;
  if ( v6 >= 0 )
  {
    if ( (*(int (__fastcall **)(LPVOID, _QWORD, __int64, int *, int, _DWORD))(*(_QWORD *)v15 + 56LL))(
           v15,
           v14,
           5126,
           &v13,
           4,
           0) >= 0 )
    {
      if ( !v13 )
      {
        if ( !a3 || v14 == 2 )
          goto LABEL_15;
        goto LABEL_17;
      }
      if ( v13 != 1 )
        goto LABEL_17;
      if ( !a3 )
      {
LABEL_21:
        if ( a1 )
        {
          v6 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a1->lpVtbl->QueryInterface)(
                 a1,
                 &IID_IServiceProvider,
                 &v19);
          v7 = v6;
          if ( v6 >= 0 )
          {
            v6 = (*(__int64 (__fastcall **)(__int64, SID *, GUID *, __int64 *))(*(_QWORD *)v19 + 24LL))(
                   v19,
                   &SID_SContainerDispatch,
                   &IID_IOleWindow,
                   &v18);
            v7 = v6;
            if ( v6 >= 0 )
            {
              v7 = (*(__int64 (__fastcall **)(__int64, HWND *))(*(_QWORD *)v18 + 24LL))(v18, &hWnd);
              if ( v7 >= 0 || (hWnd = GetActiveWindow()) != 0 )
              {
                LoadErrorDll();
                LoadStringW(*((HINSTANCE *)g_pStaticGlobals + 1), 0xE85u, Buffer, 1024);
                LoadStringW(*((HINSTANCE *)g_pStaticGlobals + 1), 0xE86u, Caption, 1024);
                v7 = MessageBoxW(hWnd, Buffer, Caption, 0x31u) != 1;
              }
              else if ( (bidGblFlags & 2) != 0 )
              {
                bidTraceW(off_18012A218[0], 3584009, L"<SecurityDialog|ADO|ERR>  line %d\n", 3500);
              }
            }
            else if ( (bidGblFlags & 2) != 0 )
            {
              LODWORD(ppv) = 3495;
              v8 = 3578889;
              goto LABEL_4;
            }
          }
          else if ( (bidGblFlags & 2) != 0 )
          {
            LODWORD(ppv) = 3492;
            v8 = 3575817;
            goto LABEL_4;
          }
          goto LABEL_44;
        }
        goto LABEL_17;
      }
      v9 = v14 == 2;
LABEL_20:
      if ( !v9 )
        goto LABEL_17;
      goto LABEL_21;
    }
    v6 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64, int *, int, _DWORD))(*(_QWORD *)v15 + 56LL))(
           v15,
           v14,
           4609,
           &v13,
           4,
           0);
    v7 = v6;
    if ( v6 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        LODWORD(ppv) = 3456;
        v8 = 3538953;
        goto LABEL_4;
      }
      goto LABEL_44;
    }
    v10 = v13;
    if ( v14 == 1 )
    {
      if ( v13 != 3 )
      {
LABEL_33:
        if ( !v10 )
        {
LABEL_15:
          v7 = 0;
          goto LABEL_44;
        }
        if ( v10 == 3 )
        {
LABEL_17:
          v7 = 1;
          goto LABEL_44;
        }
        v9 = v10 == 1;
        goto LABEL_20;
      }
      v10 = 1;
      v13 = 1;
    }
    if ( !v14 )
    {
      v10 = 0;
      v13 = 0;
    }
    goto LABEL_33;
  }
  if ( (bidGblFlags & 2) != 0 )
  {
    LODWORD(ppv) = 3403;
    v8 = 3484681;
    goto LABEL_4;
  }
LABEL_44:
  if ( v17 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v17 + 16LL))(v17);
  if ( v15 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v15 + 16LL))(v15);
  ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(&v18);
  ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(&v19);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800caa28  mov     [rsp-8+arg_10], rbx
0x1800caa2d  push    rbp
0x1800caa2e  push    rsi
0x1800caa2f  push    rdi
0x1800caa30  push    r12
0x1800caa32  push    r14
0x1800caa34  lea     rbp, [rsp-0FA0h]
0x1800caa3c  mov     eax, 10A0h
0x1800caa41  call    _alloca_probe
0x1800caa46  sub     rsp, rax
0x1800caa49  mov     rax, cs:__security_cookie
0x1800caa50  xor     rax, rsp
0x1800caa53  mov     [rbp+0FC0h+var_30], rax
0x1800caa5a  mov     edi, r8d
0x1800caa5d  mov     r14, rdx
0x1800caa60  mov     rsi, rcx
0x1800caa63  mov     [rsp+10C0h+var_1068], 0
0x1800caa6c  mov     [rsp+10C0h+var_1078], 0
0x1800caa75  mov     [rsp+10C0h+var_107C], 0
0x1800caa7d  mov     [rsp+10C0h+var_1080], 0
0x1800caa85  mov     [rsp+10C0h+var_1058], 0
0x1800caa8e  mov     [rsp+10C0h+var_1060], 0
0x1800caa97  mov     [rsp+10C0h+hWnd], 0
0x1800caaa0  lea     rax, [rsp+10C0h+var_1068]
0x1800caaa5  mov     [rsp+10C0h+ppv], rax; ppv
0x1800caaaa  lea     r9, IID_IInternetSecurityManager; riid
0x1800caab1  mov     r12d, 1
0x1800caab7  mov     r8d, r12d; dwClsContext
0x1800caaba  xor     edx, edx; pUnkOuter
0x1800caabc  lea     rcx, CLSID_InternetSecurityManager; rclsid
0x1800caac3  call    cs:__imp_CoCreateInstance
0x1800caaca  nop     dword ptr [rax+rax+00h]
0x1800caacf  mov     ebx, eax
0x1800caad1  test    eax, eax
0x1800caad3  jns     short loc_1800CAB0A
0x1800caad5  test    byte ptr cs:_bidGblFlags, 2
0x1800caadc  jz      loc_1800CADFE
0x1800caae2  mov     dword ptr [rsp+10C0h+ppv], 0D42h
0x1800caaea  mov     edx, 350809h
0x1800caaef  lea     r8, aSecuritydialog_0; "<SecurityDialog|ADO|ERR> 0x%08x{HRESULT"...
0x1800caaf6  mov     r9d, eax
0x1800caaf9  mov     rcx, cs:off_18012A218; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800cab00  call    _bidTraceW
0x1800cab05  jmp     loc_1800CADFE
0x1800cab0a  mov     rcx, [rsp+10C0h+var_1068]
0x1800cab0f  mov     rax, [rcx]
0x1800cab12  xor     r9d, r9d
0x1800cab15  lea     r8, [rsp+10C0h+var_107C]
0x1800cab1a  mov     rdx, r14
0x1800cab1d  mov     rax, [rax+28h]
0x1800cab21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cab26  mov     ebx, eax
0x1800cab28  test    eax, eax
0x1800cab2a  jns     short loc_1800CAB48
0x1800cab2c  test    byte ptr cs:_bidGblFlags, 2
0x1800cab33  jz      loc_1800CADFE
0x1800cab39  mov     dword ptr [rsp+10C0h+ppv], 0D45h
0x1800cab41  mov     edx, 351409h
0x1800cab46  jmp     short loc_1800CAAEF
0x1800cab48  lea     rax, [rsp+10C0h+var_1078]
0x1800cab4d  mov     [rsp+10C0h+ppv], rax; ppv
0x1800cab52  lea     r9, IID_IInternetZoneManager; riid
0x1800cab59  mov     r8d, r12d; dwClsContext
0x1800cab5c  xor     edx, edx; pUnkOuter
0x1800cab5e  lea     rcx, CLSID_InternetZoneManager; rclsid
0x1800cab65  call    cs:__imp_CoCreateInstance
0x1800cab6c  nop     dword ptr [rax+rax+00h]
0x1800cab71  mov     ebx, eax
0x1800cab73  test    eax, eax
0x1800cab75  jns     short loc_1800CAB96
0x1800cab77  test    byte ptr cs:_bidGblFlags, 2
0x1800cab7e  jz      loc_1800CADFE
0x1800cab84  mov     dword ptr [rsp+10C0h+ppv], 0D4Bh
0x1800cab8c  mov     edx, 352C09h
0x1800cab91  jmp     loc_1800CAAEF
0x1800cab96  mov     rcx, [rsp+10C0h+var_1078]
0x1800cab9b  mov     rax, [rcx]
0x1800cab9e  mov     [rsp+10C0h+var_1098], 0
0x1800caba6  mov     ebx, 4
0x1800cabab  mov     dword ptr [rsp+10C0h+ppv], ebx
0x1800cabaf  lea     r9, [rsp+10C0h+var_1080]
0x1800cabb4  mov     r8d, 1406h
0x1800cabba  mov     edx, [rsp+10C0h+var_107C]
0x1800cabbe  mov     rax, [rax+38h]
0x1800cabc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cabc7  test    eax, eax
0x1800cabc9  js      short loc_1800CAC4A
0x1800cabcb  mov     eax, [rsp+10C0h+var_1080]
0x1800cabcf  test    eax, eax
0x1800cabd1  jnz     short loc_1800CABE5
0x1800cabd3  test    edi, edi
0x1800cabd5  jz      short loc_1800CABDE
0x1800cabd7  cmp     [rsp+10C0h+var_107C], 2
0x1800cabdc  jnz     short loc_1800CABEA
0x1800cabde  xor     ebx, ebx
0x1800cabe0  jmp     loc_1800CADFE
0x1800cabe5  cmp     eax, 3
0x1800cabe8  jnz     short loc_1800CABF2
0x1800cabea  mov     ebx, r12d
0x1800cabed  jmp     loc_1800CADFE
0x1800cabf2  cmp     eax, r12d
0x1800cabf5  jnz     short loc_1800CABEA
0x1800cabf7  test    edi, edi
0x1800cabf9  jz      short loc_1800CAC02
0x1800cabfb  cmp     [rsp+10C0h+var_107C], 2
0x1800cac00  jnz     short loc_1800CABEA
0x1800cac02  test    rsi, rsi
0x1800cac05  jz      short loc_1800CABEA
0x1800cac07  mov     rax, [rsi]
0x1800cac0a  lea     r8, [rsp+10C0h+var_1058]
0x1800cac0f  lea     rdx, IID_IServiceProvider
0x1800cac16  mov     rcx, rsi
0x1800cac19  mov     rax, [rax]
0x1800cac1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cac21  mov     ebx, eax
0x1800cac23  test    eax, eax
0x1800cac25  jns     loc_1800CACD7
0x1800cac2b  test    byte ptr cs:_bidGblFlags, 2
0x1800cac32  jz      loc_1800CADFE
0x1800cac38  mov     dword ptr [rsp+10C0h+ppv], 0DA4h
0x1800cac40  mov     edx, 369009h
0x1800cac45  jmp     loc_1800CAAEF
0x1800cac4a  mov     rcx, [rsp+10C0h+var_1078]
0x1800cac4f  mov     rax, [rcx]
0x1800cac52  mov     [rsp+10C0h+var_1098], 0
0x1800cac5a  mov     dword ptr [rsp+10C0h+ppv], ebx
0x1800cac5e  lea     r9, [rsp+10C0h+var_1080]
0x1800cac63  mov     r8d, 1201h
0x1800cac69  mov     edx, [rsp+10C0h+var_107C]
0x1800cac6d  mov     rax, [rax+38h]
0x1800cac71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cac76  mov     ebx, eax
0x1800cac78  test    eax, eax
0x1800cac7a  jns     short loc_1800CAC9B
0x1800cac7c  test    byte ptr cs:_bidGblFlags, 2
0x1800cac83  jz      loc_1800CADFE
0x1800cac89  mov     dword ptr [rsp+10C0h+ppv], 0D80h
0x1800cac91  mov     edx, 360009h
0x1800cac96  jmp     loc_1800CAAEF
0x1800cac9b  mov     ecx, [rsp+10C0h+var_107C]
0x1800cac9f  mov     eax, [rsp+10C0h+var_1080]
0x1800caca3  cmp     ecx, r12d
0x1800caca6  jnz     short loc_1800CACB4
0x1800caca8  cmp     eax, 3
0x1800cacab  jnz     short loc_1800CACBE
0x1800cacad  mov     eax, r12d
0x1800cacb0  mov     [rsp+10C0h+var_1080], eax
0x1800cacb4  test    ecx, ecx
0x1800cacb6  jnz     short loc_1800CACBE
0x1800cacb8  xor     eax, eax
0x1800cacba  mov     [rsp+10C0h+var_1080], eax
0x1800cacbe  test    eax, eax
0x1800cacc0  jz      loc_1800CABDE
0x1800cacc6  cmp     eax, 3
0x1800cacc9  jz      loc_1800CABEA
0x1800caccf  cmp     eax, r12d
0x1800cacd2  jmp     loc_1800CAC00
0x1800cacd7  mov     rcx, [rsp+10C0h+var_1058]
0x1800cacdc  mov     rax, [rcx]
0x1800cacdf  lea     r9, [rsp+10C0h+var_1060]
0x1800cace4  lea     r8, IID_IOleWindow
0x1800caceb  lea     rdx, SID_SContainerDispatch
0x1800cacf2  mov     rax, [rax+18h]
0x1800cacf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cacfb  mov     ebx, eax
0x1800cacfd  test    eax, eax
0x1800cacff  jns     short loc_1800CAD20
0x1800cad01  test    byte ptr cs:_bidGblFlags, 2
0x1800cad08  jz      loc_1800CADFE
0x1800cad0e  mov     dword ptr [rsp+10C0h+ppv], 0DA7h
0x1800cad16  mov     edx, 369C09h
0x1800cad1b  jmp     loc_1800CAAEF
0x1800cad20  mov     rcx, [rsp+10C0h+var_1060]
0x1800cad25  mov     rax, [rcx]
0x1800cad28  lea     rdx, [rsp+10C0h+hWnd]
0x1800cad2d  mov     rax, [rax+18h]
0x1800cad31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cad36  mov     ebx, eax
0x1800cad38  test    eax, eax
0x1800cad3a  jns     short loc_1800CAD7F
0x1800cad3c  call    cs:__imp_GetActiveWindow
0x1800cad43  nop     dword ptr [rax+rax+00h]
0x1800cad48  mov     [rsp+10C0h+hWnd], rax
0x1800cad4d  test    rax, rax
0x1800cad50  jnz     short loc_1800CAD7F
0x1800cad52  test    byte ptr cs:_bidGblFlags, 2
0x1800cad59  jz      loc_1800CADFE
0x1800cad5f  mov     r9d, 0DACh
0x1800cad65  lea     r8, aSecuritydialog; "<SecurityDialog|ADO|ERR>  line %d\n"
0x1800cad6c  mov     edx, 36B009h
0x1800cad71  mov     rcx, cs:off_18012A218; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800cad78  call    _bidTraceW
0x1800cad7d  jmp     short loc_1800CADFE
0x1800cad7f  call    ?LoadErrorDll@@YAXXZ; LoadErrorDll(void)
0x1800cad84  mov     ebx, 400h
0x1800cad89  mov     r9d, ebx; cchBufferMax
0x1800cad8c  lea     r8, [rbp+0FC0h+Buffer]; lpBuffer
0x1800cad93  mov     edx, 0E85h; uID
0x1800cad98  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x1800cad9f  mov     rcx, [rcx+8]; hInstance
0x1800cada3  call    cs:__imp_LoadStringW
0x1800cadaa  nop     dword ptr [rax+rax+00h]
0x1800cadaf  mov     r9d, ebx; cchBufferMax
0x1800cadb2  lea     r8, [rsp+10C0h+Caption]; lpBuffer
0x1800cadb7  mov     edx, 0E86h; uID
0x1800cadbc  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x1800cadc3  mov     rcx, [rcx+8]; hInstance
0x1800cadc7  call    cs:__imp_LoadStringW
0x1800cadce  nop     dword ptr [rax+rax+00h]
0x1800cadd3  mov     r9d, 31h ; '1'; uType
0x1800cadd9  lea     r8, [rsp+10C0h+Caption]; lpCaption
0x1800cadde  lea     rdx, [rbp+0FC0h+Buffer]; lpText
0x1800cade5  mov     rcx, [rsp+10C0h+hWnd]; hWnd
0x1800cadea  call    cs:__imp_MessageBoxW
0x1800cadf1  nop     dword ptr [rax+rax+00h]
0x1800cadf6  xor     ebx, ebx
0x1800cadf8  cmp     eax, r12d
0x1800cadfb  setnz   bl
0x1800cadfe  mov     rcx, [rsp+10C0h+var_1068]
0x1800cae03  test    rcx, rcx
0x1800cae06  jz      short loc_1800CAE14
0x1800cae08  mov     rax, [rcx]
0x1800cae0b  mov     rax, [rax+10h]
0x1800cae0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cae14  mov     rcx, [rsp+10C0h+var_1078]
0x1800cae19  test    rcx, rcx
0x1800cae1c  jz      short loc_1800CAE2B
0x1800cae1e  mov     rax, [rcx]
0x1800cae21  mov     rax, [rax+10h]
0x1800cae25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cae2a  nop
0x1800cae2b  lea     rcx, [rsp+10C0h+var_1060]
0x1800cae30  call    ??1?$CComPtr@UIDBCreateSession@@@ATL@@QEAA@XZ; ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(void)
0x1800cae35  nop
0x1800cae36  lea     rcx, [rsp+10C0h+var_1058]
0x1800cae3b  call    ??1?$CComPtr@UIDBCreateSession@@@ATL@@QEAA@XZ; ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(void)
0x1800cae40  mov     eax, ebx
0x1800cae42  mov     rcx, [rbp+0FC0h+var_30]
0x1800cae49  xor     rcx, rsp; StackCookie
0x1800cae4c  call    __security_check_cookie
0x1800cae51  mov     rbx, [rsp+10C0h+arg_10]
0x1800cae59  add     rsp, 10A0h
0x1800cae60  pop     r14
0x1800cae62  pop     r12
0x1800cae64  pop     rdi
0x1800cae65  pop     rsi
0x1800cae66  pop     rbp
0x1800cae67  retn
```
